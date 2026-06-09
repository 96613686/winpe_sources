# _CRASMapi::get_AttachedXMLFile_::_1_::catch$0

- ea: `0x18001adae`
- end: `0x18001adf3`
- name: `_CRASMapi::get_AttachedXMLFile_::_1_::catch$0`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180014660`

## string_xrefs

- `0x18001adc3`: `CRASMapi::get_AttachedXMLFile`

## pseudocode

```c
__int64 __fastcall CRASMapi::get_AttachedXMLFile_::_1_::catch_0(CEventLogger *a1, const struct _EVENT_DESCRIPTOR *a2)
{
  CEventLogger::LogError(
    a1,
    a2,
    L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
    0x217u,
    L"CRASMapi::get_AttachedXMLFile",
    0);
  return 0;
}

```

## disassembly

```asm
0x18001adae  mov     [rsp+arg_8], rdx
0x18001adb3  push    rbp
0x18001adb4  sub     rsp, 30h
0x18001adb8  mov     rbp, rdx
0x18001adbb  mov     [rsp+38h+var_10], 0; unsigned int
0x18001adc3  lea     rax, aCrasmapiGetAtt; "CRASMapi::get_AttachedXMLFile"
0x18001adca  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001adcf  mov     r9d, 217h; unsigned int
0x18001add5  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\rahelperclass\\ras"...
0x18001addc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001ade1  nop
0x18001ade2  mov     rax, 0
0x18001adec  add     rsp, 30h
0x18001adf0  pop     rbp
0x18001adf1  retn
```
