# RunTimeInitializer::Start(void)

- ea: `0x1800307e4`
- end: `0x180030871`
- name: `?Start@RunTimeInitializer@@SAXXZ`
- size: `141`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800081a0`
- `0x18000f804`
- `0x18000f8a4`

## callees

- `0x1800307e4`
- `0x180032550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030848`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030848`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030865`

## string_xrefs

- `0x18003081b`: `call RunTimeInitializer::Start or RunTimeInitializer::Stop from DllMain`

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
0x1800307e4  mov     r11, rsp
0x1800307e7  sub     rsp, 58h
0x1800307eb  mov     rax, gs:60h
0x1800307f4  mov     rcx, gs:30h
0x1800307fd  mov     rax, [rax+110h]
0x180030804  mov     rax, [rax+10h]
0x180030808  cmp     [rcx+48h], rax
0x18003080c  jnz     short loc_180030841
0x18003080e  xor     eax, eax
0x180030810  lea     r9, aRuntimeinitial_0; "RunTimeInitializer::Start"
0x180030817  mov     [r11-10h], rax
0x18003081b  lea     rdx, aCallRuntimeini; "call RunTimeInitializer::Start or RunTi"...
0x180030822  mov     [r11-18h], rax
0x180030826  xor     r8d, r8d; unsigned __int64
0x180030829  mov     [r11-20h], rax
0x18003082d  mov     [r11-28h], rax
0x180030831  lea     ecx, [rax+4]; unsigned int
0x180030834  mov     [r11-30h], rax
0x180030838  mov     [r11-38h], rax
0x18003083c  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x180030841  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030848  call    cs:__imp_EnterCriticalSection
0x18003084f  nop     dword ptr [rax+rax+00h]
0x180030854  inc     cs:?refCount@RunTimeInitializer@@0HA; int RunTimeInitializer::refCount
0x18003085a  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION GlobalLockSentry::lock
0x180030861  add     rsp, 58h
0x180030865  jmp     cs:__imp_LeaveCriticalSection
```
