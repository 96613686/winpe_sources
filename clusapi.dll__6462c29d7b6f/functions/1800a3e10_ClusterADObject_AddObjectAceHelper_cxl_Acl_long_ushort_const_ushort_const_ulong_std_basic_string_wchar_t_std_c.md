# ClusterADObject::AddObjectAceHelper(cxl::Acl &,long,ushort * const &,ushort * const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x1800a3e10`
- end: `0x1800a3f77`
- name: `?AddObjectAceHelper@ClusterADObject@@AEAAJAEAVAcl@cxl@@JAEBQEAG1KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3a0c`

## callees

- `0x180002f50`
- `0x180028f30`
- `0x18009d190`
- `0x18009d510`
- `0x1800a3e10`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1800a3e67`
- `RPCRT4!UuidFromStringW` at `0x1800a3e84`
- `RPCRT4!UuidFromStringW` at `0x1800a3e67`
- `RPCRT4!UuidFromStringW` at `0x1800a3e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3eb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3f4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3f4c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a3ead`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a3ead`

## pseudocode

```c
signed int __fastcall ClusterADObject::AddObjectAceHelper(
        __int64 a1,
        cxl::Acl *a2,
        int a3,
        RPC_WSTR *a4,
        RPC_WSTR *a5,
        DWORD a6,
        __int64 a7,
        DWORD a8)
{
  signed int v10; // ebx
  signed int result; // eax
  const WCHAR *v12; // rax
  PSID Sid; // [rsp+30h] [rbp-58h] BYREF
  __int64 v14; // [rsp+38h] [rbp-50h] BYREF
  const cxl::Exception *v15; // [rsp+40h] [rbp-48h] BYREF
  UUID InheritedObjectTypeGuid; // [rsp+48h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-30h] BYREF

  v10 = 0;
  Uuid = 0;
  InheritedObjectTypeGuid = 0;
  if ( !*a4 || (result = UuidFromStringW(*a4, &Uuid), v10 = result, result >= 0) )
  {
    if ( !*a5 || (result = UuidFromStringW(*a5, &InheritedObjectTypeGuid), v10 = result, result >= 0) )
    {
      Sid = 0;
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a7);
      if ( ConvertStringSidToSidW(v12, &Sid) )
      {
        try
        {
          if ( a3 )
          {
            if ( a3 == 1 )
              cxl::Acl::AddAccessDeniedObjectAce(a2, &Uuid, &InheritedObjectTypeGuid, a6, (struct _SID *)Sid, a8);
          }
          else
          {
            cxl::Acl::AddAccessAllowedObjectAce(a2, &Uuid, &InheritedObjectTypeGuid, a6, (struct _SID *)Sid, a8);
          }
        }
        catch ( const cxl::Exception *v15 )
        {
          v14 = *((_QWORD *)v15 + 11);
          LODWORD(v14) = cxl::ErrorCode::GetHr((cxl::ErrorCode *)&v14);
          v10 = v14;
        }
        if ( Sid )
          LocalFree(Sid);
        return v10;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800a3e10  mov     [rsp+arg_0], rbx
0x1800a3e15  mov     [rsp+arg_10], rsi
0x1800a3e1a  push    rdi
0x1800a3e1b  push    r14
0x1800a3e1d  push    r15
0x1800a3e1f  sub     rsp, 70h
0x1800a3e23  mov     rax, cs:__security_cookie
0x1800a3e2a  xor     rax, rsp
0x1800a3e2d  mov     [rsp+88h+var_20], rax
0x1800a3e32  mov     edi, r8d
0x1800a3e35  mov     rsi, rdx
0x1800a3e38  mov     r14, [rsp+88h+arg_20]
0x1800a3e40  mov     r15, [rsp+88h+arg_30]
0x1800a3e48  xor     ebx, ebx
0x1800a3e4a  xorps   xmm0, xmm0
0x1800a3e4d  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x1800a3e52  xorps   xmm1, xmm1
0x1800a3e55  movups  xmmword ptr [rsp+88h+InheritedObjectTypeGuid.Data1], xmm1
0x1800a3e5a  mov     rcx, [r9]; StringUuid
0x1800a3e5d  test    rcx, rcx
0x1800a3e60  jz      short loc_1800A3E77
0x1800a3e62  lea     rdx, [rsp+88h+Uuid]; Uuid
0x1800a3e67  call    cs:__imp_UuidFromStringW
0x1800a3e6d  mov     ebx, eax
0x1800a3e6f  test    eax, eax
0x1800a3e71  js      loc_1800A3F54
0x1800a3e77  mov     rcx, [r14]; StringUuid
0x1800a3e7a  test    rcx, rcx
0x1800a3e7d  jz      short loc_1800A3E94
0x1800a3e7f  lea     rdx, [rsp+88h+InheritedObjectTypeGuid]; Uuid
0x1800a3e84  call    cs:__imp_UuidFromStringW
0x1800a3e8a  mov     ebx, eax
0x1800a3e8c  test    eax, eax
0x1800a3e8e  js      loc_1800A3F54
0x1800a3e94  mov     [rsp+88h+Sid], 0
0x1800a3e9d  mov     rcx, r15
0x1800a3ea0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800a3ea5  lea     rdx, [rsp+88h+Sid]; Sid
0x1800a3eaa  mov     rcx, rax; StringSid
0x1800a3ead  call    cs:__imp_ConvertStringSidToSidW
0x1800a3eb3  test    eax, eax
0x1800a3eb5  jnz     short loc_1800A3ED2
0x1800a3eb7  call    cs:__imp_GetLastError
0x1800a3ebd  test    eax, eax
0x1800a3ebf  jle     loc_1800A3F54
0x1800a3ec5  movzx   eax, ax
0x1800a3ec8  or      eax, 80070000h
0x1800a3ecd  jmp     loc_1800A3F54
0x1800a3ed2  test    edi, edi
0x1800a3ed4  jz      short loc_1800A3F0C
0x1800a3ed6  cmp     edi, 1
0x1800a3ed9  jnz     short loc_1800A3F3C
0x1800a3edb  mov     eax, [rsp+88h+arg_38]
0x1800a3ee2  mov     [rsp+88h+var_60], eax; unsigned int
0x1800a3ee6  mov     rax, [rsp+88h+Sid]
0x1800a3eeb  mov     [rsp+88h+pSid], rax; pSid
0x1800a3ef0  mov     r9d, [rsp+88h+arg_28]; unsigned int
0x1800a3ef8  lea     r8, [rsp+88h+InheritedObjectTypeGuid]; InheritedObjectTypeGuid
0x1800a3efd  lea     rdx, [rsp+88h+Uuid]; ObjectTypeGuid
0x1800a3f02  mov     rcx, rsi; this
0x1800a3f05  call    ?AddAccessDeniedObjectAce@Acl@cxl@@QEAAXAEBU_GUID@@0KPEBU_SID@@K@Z; cxl::Acl::AddAccessDeniedObjectAce(_GUID const &,_GUID const &,ulong,_SID const *,ulong)
0x1800a3f0a  jmp     short loc_1800A3F3C
0x1800a3f0c  mov     eax, [rsp+88h+arg_38]
0x1800a3f13  mov     [rsp+88h+var_60], eax; unsigned int
0x1800a3f17  mov     rax, [rsp+88h+Sid]
0x1800a3f1c  mov     [rsp+88h+pSid], rax; pSid
0x1800a3f21  mov     r9d, [rsp+88h+arg_28]; unsigned int
0x1800a3f29  lea     r8, [rsp+88h+InheritedObjectTypeGuid]; InheritedObjectTypeGuid
0x1800a3f2e  lea     rdx, [rsp+88h+Uuid]; ObjectTypeGuid
0x1800a3f33  mov     rcx, rsi; this
0x1800a3f36  call    ?AddAccessAllowedObjectAce@Acl@cxl@@QEAAXAEBU_GUID@@0KPEBU_SID@@K@Z; cxl::Acl::AddAccessAllowedObjectAce(_GUID const &,_GUID const &,ulong,_SID const *,ulong)
0x1800a3f3b  nop
0x1800a3f3c  jmp     short loc_1800A3F42
0x1800a3f3e  mov     ebx, dword ptr [rsp+88h+var_50]
0x1800a3f42  mov     rcx, [rsp+88h+Sid]; hMem
0x1800a3f47  test    rcx, rcx
0x1800a3f4a  jz      short loc_1800A3F52
0x1800a3f4c  call    cs:__imp_LocalFree
0x1800a3f52  mov     eax, ebx
0x1800a3f54  mov     rcx, [rsp+88h+var_20]
0x1800a3f59  xor     rcx, rsp; StackCookie
0x1800a3f5c  call    __security_check_cookie
0x1800a3f61  lea     r11, [rsp+88h+var_18]
0x1800a3f66  mov     rbx, [r11+20h]
0x1800a3f6a  mov     rsi, [r11+30h]
0x1800a3f6e  mov     rsp, r11
0x1800a3f71  pop     r15
0x1800a3f73  pop     r14
0x1800a3f75  pop     rdi
0x1800a3f76  retn
```
