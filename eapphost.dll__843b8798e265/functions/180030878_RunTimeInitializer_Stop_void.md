# RunTimeInitializer::Stop(void)

- ea: `0x180030878`
- end: `0x18003094a`
- name: `?Stop@RunTimeInitializer@@SAXXZ`
- size: `210`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800050b8`
- `0x180009808`
- `0x18000f804`
- `0x18000f8a4`

## callees

- `0x180030878`
- `0x180032550`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800308f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800308f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003093e`

## string_xrefs

- `0x1800308b9`: `call RunTimeInitializer::Start or RunTimeInitializer::Stop from DllMain`

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
0x180030878  mov     r11, rsp
0x18003087b  sub     rsp, 58h
0x18003087f  mov     rax, gs:60h
0x180030888  mov     rdx, gs:30h
0x180030891  mov     rcx, [rax+110h]
0x180030898  mov     rax, [rcx+10h]
0x18003089c  cmp     [rdx+48h], rax
0x1800308a0  jnz     short loc_1800308EC
0x1800308a2  mov     qword ptr [r11-10h], 0
0x1800308aa  lea     r9, aRuntimeinitial; "RunTimeInitializer::Stop"
0x1800308b1  mov     qword ptr [r11-18h], 0
0x1800308b9  lea     rdx, aCallRuntimeini; "call RunTimeInitializer::Start or RunTi"...
0x1800308c0  mov     qword ptr [r11-20h], 0
0x1800308c8  xor     r8d, r8d; unsigned __int64
0x1800308cb  mov     qword ptr [r11-28h], 0
0x1800308d3  mov     qword ptr [r11-30h], 0
0x1800308db  mov     qword ptr [r11-38h], 0
0x1800308e3  lea     ecx, [r8+4]; unsigned int
0x1800308e7  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x1800308ec  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800308f3  call    cs:__imp_EnterCriticalSection
0x1800308fa  nop     dword ptr [rax+rax+00h]
0x1800308ff  sub     cs:?refCount@RunTimeInitializer@@0HA, 1; int RunTimeInitializer::refCount
0x180030906  jnz     short loc_180030933
0x180030908  mov     rcx, cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x18003090f  jmp     short loc_18003092E
0x180030911  mov     rax, [rcx]
0x180030914  mov     rax, [rax]
0x180030917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003091c  mov     rax, cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x180030923  mov     rcx, [rax+8]
0x180030927  mov     cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA, rcx; OnStopCallback * RunTimeInitializer::atStop
0x18003092e  test    rcx, rcx
0x180030931  jnz     short loc_180030911
0x180030933  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION GlobalLockSentry::lock
0x18003093a  add     rsp, 58h
0x18003093e  jmp     cs:__imp_LeaveCriticalSection
```
