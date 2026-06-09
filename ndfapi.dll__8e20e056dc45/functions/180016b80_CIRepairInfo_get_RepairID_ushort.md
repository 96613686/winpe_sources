# CIRepairInfo::get_RepairID(ushort * *)

- ea: `0x180016b80`
- end: `0x180016be8`
- name: `?get_RepairID@CIRepairInfo@@UEAAJPEAPEAG@Z`
- size: `104`
- prototype: `__int64 __fastcall(CIRepairInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180016b80`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180016bab`
- `ole32!StringFromCLSID` at `0x180016bab`
- `ole32!CoTaskMemFree` at `0x180016bd5`
- `ole32!CoTaskMemFree` at `0x180016bd5`
- `OLEAUT32!__imp_SysAllocString` at `0x180016bbc`
- `OLEAUT32!__imp_SysAllocString` at `0x180016bbc`

## pseudocode

```c
__int64 __fastcall CIRepairInfo::get_RepairID(CIRepairInfo *this, unsigned __int16 **a2)
{
  const IID *v2; // rcx
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  LPOLESTR lpsz; // [rsp+30h] [rbp+8h] BYREF

  v2 = (const IID *)*((_QWORD *)this + 10);
  if ( !v2 )
    return 2147942421LL;
  lpsz = 0;
  v5 = StringFromCLSID(v2, &lpsz);
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
0x180016b80  mov     [rsp+arg_8], rbx
0x180016b85  push    rdi
0x180016b86  sub     rsp, 20h
0x180016b8a  mov     rcx, [rcx+50h]; rclsid
0x180016b8e  mov     rdi, rdx
0x180016b91  test    rcx, rcx
0x180016b94  jnz     short loc_180016B9D
0x180016b96  mov     eax, 80070015h
0x180016b9b  jmp     short loc_180016BDD
0x180016b9d  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x180016ba2  mov     [rsp+28h+lpsz], 0
0x180016bab  call    cs:__imp_StringFromCLSID
0x180016bb1  mov     ebx, eax
0x180016bb3  test    eax, eax
0x180016bb5  jnz     short loc_180016BDB
0x180016bb7  mov     rcx, [rsp+28h+lpsz]; psz
0x180016bbc  call    cs:__imp_SysAllocString
0x180016bc2  test    rax, rax
0x180016bc5  mov     [rdi], rax
0x180016bc8  mov     ecx, 8007000Eh
0x180016bcd  cmovz   ebx, ecx
0x180016bd0  mov     rcx, [rsp+28h+lpsz]; pv
0x180016bd5  call    cs:__imp_CoTaskMemFree
0x180016bdb  mov     eax, ebx
0x180016bdd  mov     rbx, [rsp+28h+arg_8]
0x180016be2  add     rsp, 20h
0x180016be6  pop     rdi
0x180016be7  retn
```
