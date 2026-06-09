# CIRootCauseInfo::get_RootCauseID(ushort * *)

- ea: `0x180016dd0`
- end: `0x180016e3c`
- name: `?get_RootCauseID@CIRootCauseInfo@@UEAAJPEAPEAG@Z`
- size: `108`
- prototype: `__int64 __fastcall(CIRootCauseInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180016dd0`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180016dff`
- `ole32!StringFromCLSID` at `0x180016dff`
- `ole32!CoTaskMemFree` at `0x180016e29`
- `ole32!CoTaskMemFree` at `0x180016e29`
- `OLEAUT32!__imp_SysAllocString` at `0x180016e10`
- `OLEAUT32!__imp_SysAllocString` at `0x180016e10`

## pseudocode

```c
__int64 __fastcall CIRootCauseInfo::get_RootCauseID(CIRootCauseInfo *this, unsigned __int16 **a2)
{
  __int64 v2; // rcx
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  LPOLESTR lpsz; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 9);
  if ( !v2 )
    return 2147942421LL;
  lpsz = 0;
  v5 = StringFromCLSID((const IID *const)(v2 + 8), &lpsz);
  if ( !v5 )
  {
    v6 = SysAllocString(lpsz);
    *a2 = v6;
    if ( !v6 )
      v5 = -2147024882;
    CoTaskMemFree(lpsz);
  }
  return v5;
}

```

## disassembly

```asm
0x180016dd0  mov     [rsp+arg_8], rbx
0x180016dd5  push    rdi
0x180016dd6  sub     rsp, 20h
0x180016dda  mov     rcx, [rcx+48h]
0x180016dde  mov     rdi, rdx
0x180016de1  test    rcx, rcx
0x180016de4  jnz     short loc_180016DED
0x180016de6  mov     eax, 80070015h
0x180016deb  jmp     short loc_180016E31
0x180016ded  add     rcx, 8; rclsid
0x180016df1  mov     [rsp+28h+lpsz], 0
0x180016dfa  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x180016dff  call    cs:__imp_StringFromCLSID
0x180016e05  mov     ebx, eax
0x180016e07  test    eax, eax
0x180016e09  jnz     short loc_180016E2F
0x180016e0b  mov     rcx, [rsp+28h+lpsz]; psz
0x180016e10  call    cs:__imp_SysAllocString
0x180016e16  test    rax, rax
0x180016e19  mov     [rdi], rax
0x180016e1c  mov     ecx, 8007000Eh
0x180016e21  cmovz   ebx, ecx
0x180016e24  mov     rcx, [rsp+28h+lpsz]; pv
0x180016e29  call    cs:__imp_CoTaskMemFree
0x180016e2f  mov     eax, ebx
0x180016e31  mov     rbx, [rsp+28h+arg_8]
0x180016e36  add     rsp, 20h
0x180016e3a  pop     rdi
0x180016e3b  retn
```
