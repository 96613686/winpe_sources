# win_musl::CriticalSection::Enter(void)

- ea: `0x180031600`
- end: `0x18003162b`
- name: `?Enter@CriticalSection@win_musl@@QEAAXXZ`
- size: `43`
- prototype: `void __fastcall(win_musl::CriticalSection *__hidden this)`
- caller_count: `64`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015c8`
- `0x180001980`
- `0x1800021c0`
- `0x180003520`
- `0x1800289c0`
- `0x18002d49c`
- `0x18002e534`
- `0x18002ec54`
- `0x18002f81c`
- `0x180030a44`
- `0x180030d84`
- `0x180031218`
- `0x180031440`
- `0x180031b10`
- `0x180031c4c`
- `0x1800347e4`
- `0x180039a78`
- `0x180039cf0`
- `0x18003a3a4`
- `0x18003a53c`
- `0x18003b5a4`
- `0x18003b654`
- `0x1800444f0`
- `0x18004b26c`
- `0x18004b87c`
- `0x18004d2ec`
- `0x18004d34c`
- `0x18004d4f0`
- `0x18004d778`
- `0x18004e088`
- `0x18004e5c8`
- `0x180053328`
- `0x1800670a8`
- `0x180067550`
- `0x180067e18`
- `0x180068170`
- `0x180068a0c`
- `0x180068c04`
- `0x180068d78`
- `0x180068f04`
- `0x18006a760`
- `0x18006adc8`
- `0x18006b330`
- `0x18006b8cc`
- `0x18006e12c`
- `0x18007832c`
- `0x180085e24`
- `0x180086d30`
- `0x18008a2f0`
- `0x18008a3bc`

## callees

- `0x180031600`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003161c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003161c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031609`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031609`

## pseudocode

```c
void __fastcall win_musl::CriticalSection::Enter(struct _RTL_CRITICAL_SECTION *this)
{
  int DebugInfo_high; // edx

  EnterCriticalSection(this);
  DebugInfo_high = HIDWORD(this[1].DebugInfo);
  HIDWORD(this[1].DebugInfo) = DebugInfo_high + 1;
  if ( !DebugInfo_high )
    LODWORD(this[1].DebugInfo) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x180031600  push    rbx
0x180031602  sub     rsp, 20h
0x180031606  mov     rbx, rcx
0x180031609  call    cs:__imp_EnterCriticalSection
0x18003160f  mov     edx, [rbx+2Ch]
0x180031612  lea     eax, [rdx+1]
0x180031615  mov     [rbx+2Ch], eax
0x180031618  test    edx, edx
0x18003161a  jnz     short loc_180031625
0x18003161c  call    cs:__imp_GetCurrentThreadId
0x180031622  mov     [rbx+28h], eax
0x180031625  add     rsp, 20h
0x180031629  pop     rbx
0x18003162a  retn
```
