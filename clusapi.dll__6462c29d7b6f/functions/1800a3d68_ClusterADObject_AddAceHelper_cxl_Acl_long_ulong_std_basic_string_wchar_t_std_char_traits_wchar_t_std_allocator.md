# ClusterADObject::AddAceHelper(cxl::Acl &,long,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x1800a3d68`
- end: `0x1800a3e08`
- name: `?AddAceHelper@ClusterADObject@@AEAAJAEAVAcl@cxl@@JKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3a0c`

## callees

- `0x180028f30`
- `0x18009cfe0`
- `0x18009d360`
- `0x1800a3d68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3da5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3df6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3df6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a3d9b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a3d9b`

## pseudocode

```c
signed int __fastcall ClusterADObject::AddAceHelper(__int64 a1, cxl::Acl *a2, int a3, DWORD a4, __int64 a5, int Hr)
{
  int v9; // edi
  const WCHAR *v10; // rax
  signed int result; // eax
  const cxl::Exception *v12; // [rsp+20h] [rbp-38h] BYREF
  PSID Sid; // [rsp+60h] [rbp+8h] BYREF

  v9 = 0;
  Sid = 0;
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a5);
  if ( ConvertStringSidToSidW(v10, &Sid) )
  {
    try
    {
      if ( a3 )
      {
        if ( a3 == 1 )
          cxl::Acl::AddAccessDeniedAce(a2, a4, (struct _SID *)Sid);
      }
      else
      {
        cxl::Acl::AddAccessAllowedAce(a2, a4, (struct _SID *)Sid);
      }
    }
    catch ( const cxl::Exception *v12 )
    {
      a5 = *((_QWORD *)v12 + 11);
      Hr = cxl::ErrorCode::GetHr((cxl::ErrorCode *)&a5);
      v9 = Hr;
    }
    if ( Sid )
      LocalFree(Sid);
    return v9;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800a3d68  mov     [rsp+Sid], rcx
0x1800a3d6d  push    rbx
0x1800a3d6e  push    rsi
0x1800a3d6f  push    rdi
0x1800a3d70  push    r14
0x1800a3d72  sub     rsp, 38h
0x1800a3d76  mov     esi, r9d
0x1800a3d79  mov     ebx, r8d
0x1800a3d7c  mov     r14, rdx
0x1800a3d7f  xor     edi, edi
0x1800a3d81  mov     [rsp+58h+Sid], rdi
0x1800a3d86  mov     rcx, [rsp+58h+arg_20]
0x1800a3d8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800a3d93  lea     rdx, [rsp+58h+Sid]; Sid
0x1800a3d98  mov     rcx, rax; StringSid
0x1800a3d9b  call    cs:__imp_ConvertStringSidToSidW
0x1800a3da1  test    eax, eax
0x1800a3da3  jnz     short loc_1800A3DB9
0x1800a3da5  call    cs:__imp_GetLastError
0x1800a3dab  test    eax, eax
0x1800a3dad  jle     short loc_1800A3DFE
0x1800a3daf  movzx   eax, ax
0x1800a3db2  or      eax, 80070000h
0x1800a3db7  jmp     short loc_1800A3DFE
0x1800a3db9  test    ebx, ebx
0x1800a3dbb  jz      short loc_1800A3DD3
0x1800a3dbd  cmp     ebx, 1
0x1800a3dc0  jnz     short loc_1800A3DE3
0x1800a3dc2  mov     r8, [rsp+58h+Sid]; struct _SID *
0x1800a3dc7  mov     edx, esi; AccessMask
0x1800a3dc9  mov     rcx, r14; this
0x1800a3dcc  call    ?AddAccessDeniedAce@Acl@cxl@@QEAAXKPEBU_SID@@K@Z; cxl::Acl::AddAccessDeniedAce(ulong,_SID const *,ulong)
0x1800a3dd1  jmp     short loc_1800A3DE3
0x1800a3dd3  mov     r8, [rsp+58h+Sid]; struct _SID *
0x1800a3dd8  mov     edx, esi; AccessMask
0x1800a3dda  mov     rcx, r14; this
0x1800a3ddd  call    ?AddAccessAllowedAce@Acl@cxl@@QEAAXKPEBU_SID@@K@Z; cxl::Acl::AddAccessAllowedAce(ulong,_SID const *,ulong)
0x1800a3de2  nop
0x1800a3de3  jmp     short loc_1800A3DEC
0x1800a3de5  mov     edi, [rsp+58h+arg_28]
0x1800a3dec  mov     rcx, [rsp+58h+Sid]; hMem
0x1800a3df1  test    rcx, rcx
0x1800a3df4  jz      short loc_1800A3DFC
0x1800a3df6  call    cs:__imp_LocalFree
0x1800a3dfc  mov     eax, edi
0x1800a3dfe  add     rsp, 38h
0x1800a3e02  pop     r14
0x1800a3e04  pop     rdi
0x1800a3e05  pop     rsi
0x1800a3e06  pop     rbx
0x1800a3e07  retn
```
