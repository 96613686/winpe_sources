# ATL::CComBSTR::CComBSTR(_GUID const &)

- ea: `0x180014200`
- end: `0x180014245`
- name: `??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z`
- size: `69`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const struct _GUID *)`
- caller_count: `6`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014e1c`
- `0x180053178`
- `0x180073364`
- `0x180094e10`
- `0x180095490`
- `0x180095920`

## import_xrefs

- `ole32!StringFromCLSID` at `0x18001421d`
- `ole32!StringFromCLSID` at `0x18001421d`
- `ole32!CoTaskMemFree` at `0x180014236`
- `ole32!CoTaskMemFree` at `0x180014236`
- `OLEAUT32!__imp_SysAllocString` at `0x180014228`
- `OLEAUT32!__imp_SysAllocString` at `0x180014228`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const struct _GUID *a2)
{
  BSTR v3; // rax
  LPOLESTR v4; // rcx
  LPOLESTR lpsz; // [rsp+30h] [rbp+8h] BYREF

  lpsz = 0;
  StringFromCLSID(a2, &lpsz);
  v3 = SysAllocString(lpsz);
  v4 = lpsz;
  *(_QWORD *)this = v3;
  CoTaskMemFree(v4);
  return this;
}

```

## disassembly

```asm
0x180014200  push    rbx
0x180014202  sub     rsp, 20h
0x180014206  mov     rax, rdx
0x180014209  mov     [rsp+28h+lpsz], 0
0x180014212  mov     rbx, rcx
0x180014215  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x18001421a  mov     rcx, rax; rclsid
0x18001421d  call    cs:__imp_StringFromCLSID
0x180014223  mov     rcx, [rsp+28h+lpsz]; psz
0x180014228  call    cs:__imp_SysAllocString
0x18001422e  mov     rcx, [rsp+28h+lpsz]; pv
0x180014233  mov     [rbx], rax
0x180014236  call    cs:__imp_CoTaskMemFree
0x18001423c  mov     rax, rbx
0x18001423f  add     rsp, 20h
0x180014243  pop     rbx
0x180014244  retn
```
