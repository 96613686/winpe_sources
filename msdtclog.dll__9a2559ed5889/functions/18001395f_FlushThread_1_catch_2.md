# __FlushThread_::_1_::catch$2

- ea: `0x18001395f`
- end: `0x18001398f`
- name: `__FlushThread_::_1_::catch$2`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006dd8`
- `0x18000dc8c`

## string_xrefs

- `0x180013970`: `The FlushThread hit the exception (%d). The process will be terminated`

## pseudocode

```c
void __fastcall __noreturn _FlushThread_::_1_::catch_2(__int64 a1, __int64 a2)
{
  TracedStringCchPrintfW(
    (unsigned __int16 *)(a2 + 48),
    0x200u,
    L"The FlushThread hit the exception (%d). The process will be terminated",
    *(unsigned int *)(a2 + 40));
  DtcInternalErrorW((const unsigned __int16 *)(a2 + 48));
}

```

## disassembly

```asm
0x18001395f  mov     [rsp+arg_8], rdx
0x180013964  push    rbp
0x180013965  sub     rsp, 20h
0x180013969  mov     rbp, rdx
0x18001396c  mov     r9d, [rbp+28h]
0x180013970  lea     r8, aTheFlushthread; "The FlushThread hit the exception (%d)."...
0x180013977  mov     edx, 200h; unsigned __int64
0x18001397c  lea     rcx, [rbp+30h]; unsigned __int16 *
0x180013980  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013985  lea     rcx, [rbp+30h]; unsigned __int16 *
0x180013989  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
