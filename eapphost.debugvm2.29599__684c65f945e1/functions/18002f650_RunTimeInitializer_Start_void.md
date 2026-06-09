# RunTimeInitializer::Start(void)

- ea: `0x18002f650`
- end: `0x18002f6d2`
- name: `?Start@RunTimeInitializer@@SAXXZ`
- size: `130`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007e88`
- `0x18000f200`
- `0x18000f29c`

## callees

- `0x18002f650`
- `0x180031368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f6b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f6cb`

## string_xrefs

- `0x18002f687`: `call RunTimeInitializer::Start or RunTimeInitializer::Stop from DllMain`

## pseudocode

```c
void RunTimeInitializer::Start(void)
{
  if ( NtCurrentTeb()->ClientId.UniqueThread == NtCurrentPeb()->LoaderLock->OwningThread )
    VerifierStop(
      4u,
      "call RunTimeInitializer::Start or RunTimeInitializer::Stop from DllMain",
      0,
      "RunTimeInitializer::Start",
      0,
      0,
      0,
      0,
      0,
      0);
  EnterCriticalSection(&GlobalLockSentry::lock);
  ++RunTimeInitializer::refCount;
  LeaveCriticalSection(&GlobalLockSentry::lock);
}

```

## disassembly

```asm
0x18002f650  mov     r11, rsp
0x18002f653  sub     rsp, 58h
0x18002f657  mov     rax, gs:60h
0x18002f660  mov     rcx, gs:30h
0x18002f669  mov     rax, [rax+110h]
0x18002f670  mov     rax, [rax+10h]
0x18002f674  cmp     [rcx+48h], rax
0x18002f678  jnz     short loc_18002F6AD
0x18002f67a  xor     eax, eax
0x18002f67c  lea     r9, aRuntimeinitial_0; "RunTimeInitializer::Start"
0x18002f683  mov     [r11-10h], rax
0x18002f687  lea     rdx, aCallRuntimeini; "call RunTimeInitializer::Start or RunTi"...
0x18002f68e  mov     [r11-18h], rax
0x18002f692  xor     r8d, r8d; unsigned __int64
0x18002f695  mov     [r11-20h], rax
0x18002f699  mov     [r11-28h], rax
0x18002f69d  lea     ecx, [rax+4]; unsigned int
0x18002f6a0  mov     [r11-30h], rax
0x18002f6a4  mov     [r11-38h], rax
0x18002f6a8  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x18002f6ad  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f6b4  call    cs:__imp_EnterCriticalSection
0x18002f6ba  inc     cs:?refCount@RunTimeInitializer@@0HA; int RunTimeInitializer::refCount
0x18002f6c0  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION GlobalLockSentry::lock
0x18002f6c7  add     rsp, 58h
0x18002f6cb  jmp     cs:__imp_LeaveCriticalSection
```
