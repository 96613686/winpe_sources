# CIRootCauseInfo::get_NetworkInterfaceID(ushort * *)

- ea: `0x1800166a0`
- end: `0x18001670c`
- name: `?get_NetworkInterfaceID@CIRootCauseInfo@@UEAAJPEAPEAG@Z`
- size: `108`
- prototype: `__int64 __fastcall(CIRootCauseInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800166a0`

## import_xrefs

- `ole32!StringFromCLSID` at `0x1800166cf`
- `ole32!StringFromCLSID` at `0x1800166cf`
- `ole32!CoTaskMemFree` at `0x1800166f9`
- `ole32!CoTaskMemFree` at `0x1800166f9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800166e0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800166e0`

## pseudocode

```c
__int64 __fastcall CIRootCauseInfo::get_NetworkInterfaceID(CIRootCauseInfo *this, unsigned __int16 **a2)
{
  __int64 v2; // rcx
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  LPOLESTR lpsz; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 9);
  if ( !v2 )
    return 2147942421LL;
  lpsz = 0;
  v5 = StringFromCLSID((const IID *const)(v2 + 28), &lpsz);
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
0x1800166a0  mov     [rsp+arg_8], rbx
0x1800166a5  push    rdi
0x1800166a6  sub     rsp, 20h
0x1800166aa  mov     rcx, [rcx+48h]
0x1800166ae  mov     rdi, rdx
0x1800166b1  test    rcx, rcx
0x1800166b4  jnz     short loc_1800166BD
0x1800166b6  mov     eax, 80070015h
0x1800166bb  jmp     short loc_180016701
0x1800166bd  add     rcx, 1Ch; rclsid
0x1800166c1  mov     [rsp+28h+lpsz], 0
0x1800166ca  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x1800166cf  call    cs:__imp_StringFromCLSID
0x1800166d5  mov     ebx, eax
0x1800166d7  test    eax, eax
0x1800166d9  jnz     short loc_1800166FF
0x1800166db  mov     rcx, [rsp+28h+lpsz]; psz
0x1800166e0  call    cs:__imp_SysAllocString
0x1800166e6  test    rax, rax
0x1800166e9  mov     [rdi], rax
0x1800166ec  mov     ecx, 8007000Eh
0x1800166f1  cmovz   ebx, ecx
0x1800166f4  mov     rcx, [rsp+28h+lpsz]; pv
0x1800166f9  call    cs:__imp_CoTaskMemFree
0x1800166ff  mov     eax, ebx
0x180016701  mov     rbx, [rsp+28h+arg_8]
0x180016706  add     rsp, 20h
0x18001670a  pop     rdi
0x18001670b  retn
```
