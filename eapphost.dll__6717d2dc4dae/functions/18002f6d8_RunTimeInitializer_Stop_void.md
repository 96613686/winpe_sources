# RunTimeInitializer::Stop(void)

- ea: `0x18002f6d8`
- end: `0x18002f79f`
- name: `?Stop@RunTimeInitializer@@SAXXZ`
- size: `199`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004f70`
- `0x180009430`
- `0x18000f200`
- `0x18000f29c`

## callees

- `0x18002f6d8`
- `0x180031368`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f753`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f753`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f798`

## string_xrefs

- `0x18002f719`: `call RunTimeInitializer::Start or RunTimeInitializer::Stop from DllMain`

## pseudocode

```c
void RunTimeInitializer::Stop(void)
{
  struct OnStopCallback *i; // rcx

  if ( NtCurrentTeb()->ClientId.UniqueThread == NtCurrentPeb()->LoaderLock->OwningThread )
    VerifierStop(
      4u,
      "call RunTimeInitializer::Start or RunTimeInitializer::Stop from DllMain",
      0,
      "RunTimeInitializer::Stop",
      0,
      0,
      0,
      0,
      0,
      0);
  EnterCriticalSection(&GlobalLockSentry::lock);
  if ( !--RunTimeInitializer::refCount )
  {
    for ( i = RunTimeInitializer::atStop; i; RunTimeInitializer::atStop = i )
    {
      (**(void (__fastcall ***)(struct OnStopCallback *))i)(i);
      i = (struct OnStopCallback *)*((_QWORD *)RunTimeInitializer::atStop + 1);
    }
  }
  LeaveCriticalSection(&GlobalLockSentry::lock);
}

```

## disassembly

```asm
0x18002f6d8  mov     r11, rsp
0x18002f6db  sub     rsp, 58h
0x18002f6df  mov     rax, gs:60h
0x18002f6e8  mov     rdx, gs:30h
0x18002f6f1  mov     rcx, [rax+110h]
0x18002f6f8  mov     rax, [rcx+10h]
0x18002f6fc  cmp     [rdx+48h], rax
0x18002f700  jnz     short loc_18002F74C
0x18002f702  mov     qword ptr [r11-10h], 0
0x18002f70a  lea     r9, aRuntimeinitial; "RunTimeInitializer::Stop"
0x18002f711  mov     qword ptr [r11-18h], 0
0x18002f719  lea     rdx, aCallRuntimeini; "call RunTimeInitializer::Start or RunTi"...
0x18002f720  mov     qword ptr [r11-20h], 0
0x18002f728  xor     r8d, r8d; unsigned __int64
0x18002f72b  mov     qword ptr [r11-28h], 0
0x18002f733  mov     qword ptr [r11-30h], 0
0x18002f73b  mov     qword ptr [r11-38h], 0
0x18002f743  lea     ecx, [r8+4]; unsigned int
0x18002f747  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x18002f74c  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f753  call    cs:__imp_EnterCriticalSection
0x18002f759  sub     cs:?refCount@RunTimeInitializer@@0HA, 1; int RunTimeInitializer::refCount
0x18002f760  jnz     short loc_18002F78D
0x18002f762  mov     rcx, cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x18002f769  jmp     short loc_18002F788
0x18002f76b  mov     rax, [rcx]
0x18002f76e  mov     rax, [rax]
0x18002f771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f776  mov     rax, cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x18002f77d  mov     rcx, [rax+8]
0x18002f781  mov     cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA, rcx; OnStopCallback * RunTimeInitializer::atStop
0x18002f788  test    rcx, rcx
0x18002f78b  jnz     short loc_18002F76B
0x18002f78d  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION GlobalLockSentry::lock
0x18002f794  add     rsp, 58h
0x18002f798  jmp     cs:__imp_LeaveCriticalSection
```
