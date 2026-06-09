# CNetworkDiagnostics::get_IncidentID(ushort * *)

- ea: `0x1800165c0`
- end: `0x18001665f`
- name: `?get_IncidentID@CNetworkDiagnostics@@UEAAJPEAPEAG@Z`
- size: `159`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800165c0`
- `0x18001f690`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180016615`
- `ole32!StringFromCLSID` at `0x180016615`
- `ole32!CoTaskMemFree` at `0x18001663f`
- `ole32!CoTaskMemFree` at `0x18001663f`
- `OLEAUT32!__imp_SysAllocString` at `0x180016626`
- `OLEAUT32!__imp_SysAllocString` at `0x180016626`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::get_IncidentID(CNetworkDiagnostics *this, unsigned __int16 **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  LPOLESTR lpsz; // [rsp+20h] [rbp-28h] BYREF
  IID rclsid; // [rsp+28h] [rbp-20h] BYREF

  if ( *((int *)this + 30) < 3 )
    return 2147943176LL;
  v4 = *((_QWORD *)this + 2);
  lpsz = 0;
  rclsid = 0;
  rclsid = *(IID *)(v4 + 3048);
  v5 = StringFromCLSID(&rclsid, &lpsz);
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
0x1800165c0  mov     [rsp+arg_10], rbx
0x1800165c5  push    rdi
0x1800165c6  sub     rsp, 40h
0x1800165ca  mov     rax, cs:__security_cookie
0x1800165d1  xor     rax, rsp
0x1800165d4  mov     [rsp+48h+var_10], rax
0x1800165d9  cmp     dword ptr [rcx+78h], 3
0x1800165dd  mov     rdi, rdx
0x1800165e0  jge     short loc_1800165E9
0x1800165e2  mov     eax, 80070308h
0x1800165e7  jmp     short loc_180016647
0x1800165e9  mov     rax, [rcx+10h]
0x1800165ed  lea     rdx, [rsp+48h+lpsz]; lplpsz
0x1800165f2  xorps   xmm0, xmm0
0x1800165f5  mov     [rsp+48h+lpsz], 0
0x1800165fe  movups  xmmword ptr [rsp+48h+rclsid.Data1], xmm0
0x180016603  lea     rcx, [rsp+48h+rclsid]; rclsid
0x180016608  movups  xmm1, xmmword ptr [rax+0BE8h]
0x18001660f  movdqu  xmmword ptr [rsp+48h+rclsid.Data1], xmm1
0x180016615  call    cs:__imp_StringFromCLSID
0x18001661b  mov     ebx, eax
0x18001661d  test    eax, eax
0x18001661f  jnz     short loc_180016645
0x180016621  mov     rcx, [rsp+48h+lpsz]; psz
0x180016626  call    cs:__imp_SysAllocString
0x18001662c  test    rax, rax
0x18001662f  mov     [rdi], rax
0x180016632  mov     ecx, 8007000Eh
0x180016637  cmovz   ebx, ecx
0x18001663a  mov     rcx, [rsp+48h+lpsz]; pv
0x18001663f  call    cs:__imp_CoTaskMemFree
0x180016645  mov     eax, ebx
0x180016647  mov     rcx, [rsp+48h+var_10]
0x18001664c  xor     rcx, rsp; StackCookie
0x18001664f  call    __security_check_cookie
0x180016654  mov     rbx, [rsp+48h+arg_10]
0x180016659  add     rsp, 40h
0x18001665d  pop     rdi
0x18001665e  retn
```
