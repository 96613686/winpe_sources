# _anonymous_namespace_::GetSecurityDescriptor

- ea: `0x18003c5dc`
- end: `0x18003c6fb`
- name: `_anonymous_namespace_::GetSecurityDescriptor`
- size: `287`
- prototype: `unsigned int __fastcall(const Registry::REGISTRY_ACCESS_PERMISSIONS pSD, void **AccessPermissions)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003c06c`

## callees

- `0x180002790`
- `0x18000866c`
- `0x18000b0a0`
- `0x180011844`
- `0x180011cfc`
- `0x180012400`
- `0x180012770`
- `0x1800127cc`
- `0x18003c5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003c67d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003c67d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::GetSecurityDescriptor(
        const Registry::REGISTRY_ACCESS_PERMISSIONS pSD,
        void **AccessPermissions)
{
  unsigned __int64 v3; // rax
  const wchar_t *v4; // rcx
  const wchar_t *v5; // rax
  __int64 v6; // r10
  const WCHAR *v7; // rax
  DWORD LastError; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  unsigned int secDescSize; // [rsp+20h] [rbp-38h] BYREF
  std::wstring strSecurityDescriptor; // [rsp+28h] [rbp-30h] BYREF

  std::wstring::wstring(&strSecurityDescriptor);
  v3 = std::_WChar_traits<unsigned short>::length(L"D:PAI(A;CI;CCDCLCSWRPWPSDRCKA;;;LS)(A;CI;CCDCLCSWRPWPSDRCKA;;;BU)(A;CI;KR;;;BA)");
  std::wstring::_Assign<unsigned short>(&strSecurityDescriptor, v4, v3);
  secDescSize = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&strSecurityDescriptor._Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v6 + 16), 0xAu, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids, v5);
  }
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&strSecurityDescriptor._Mypair._Myval2);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, AccessPermissions, &secDescSize) )
  {
    v10 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids, LastError);
    }
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  std::wstring::_Tidy_deallocate(&strSecurityDescriptor);
  return v10;
}

```

## disassembly

```asm
0x18003c5dc  mov     [rsp+arg_0], rbx
0x18003c5e1  push    rdi
0x18003c5e2  sub     rsp, 50h
0x18003c5e6  mov     rax, cs:__security_cookie
0x18003c5ed  xor     rax, rsp
0x18003c5f0  mov     [rsp+58h+var_10], rax
0x18003c5f5  mov     rbx, pSD
0x18003c5f8  lea     rcx, [rsp+58h+strSecurityDescriptor]; this
0x18003c5fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003c602  nop
0x18003c603  lea     rcx, aDPaiACiCcdclcs; "D:PAI(A;CI;CCDCLCSWRPWPSDRCKA;;;LS)(A;C"...
0x18003c60a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003c60f  mov     r8, rax; _Count
0x18003c612  mov     pSD, rcx; _Ptr
0x18003c615  lea     rcx, [rsp+58h+strSecurityDescriptor]; this
0x18003c61a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003c61f  mov     [rsp+58h+secDescSize], 0
0x18003c627  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c62e  mov     r10, cs:WPP_GLOBAL_Control
0x18003c635  cmp     r10, rdi
0x18003c638  jz      short loc_18003C663
0x18003c63a  test    byte ptr [r10+1Ch], 10h
0x18003c63f  jz      short loc_18003C663
0x18003c641  lea     rcx, [rsp+58h+strSecurityDescriptor]; this
0x18003c646  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c64b  mov     r9, rax; _a1
0x18003c64e  mov     edx, 0Ah; id
0x18003c653  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003c65a  mov     rcx, [r10+10h]; Logger
0x18003c65e  call    WPP_SF_S
0x18003c663  lea     rcx, [rsp+58h+strSecurityDescriptor]; this
0x18003c668  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c66d  mov     rcx, rax; StringSecurityDescriptor
0x18003c670  lea     r9, [rsp+58h+secDescSize]; SecurityDescriptorSize
0x18003c675  mov     r8, rbx; SecurityDescriptor
0x18003c678  mov     edx, 1; StringSDRevision
0x18003c67d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003c683  test    eax, eax
0x18003c685  jnz     short loc_18003C6D5
0x18003c687  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c68e  cmp     rax, rdi
0x18003c691  jz      short loc_18003C6BE
0x18003c693  test    byte ptr [rax+1Ch], 2
0x18003c697  jz      short loc_18003C6BE
0x18003c699  call    cs:__imp_GetLastError
0x18003c69f  mov     edx, 0Bh; id
0x18003c6a4  mov     r9d, eax; _a1
0x18003c6a7  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003c6ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c6b5  mov     rcx, [rcx+10h]; Logger
0x18003c6b9  call    WPP_SF_d
0x18003c6be  call    cs:__imp_GetLastError
0x18003c6c4  mov     ebx, eax
0x18003c6c6  test    eax, eax
0x18003c6c8  jle     short loc_18003C6D7
0x18003c6ca  movzx   ebx, ax
0x18003c6cd  or      ebx, 80070000h
0x18003c6d3  jmp     short loc_18003C6D7
0x18003c6d5  xor     ebx, ebx
0x18003c6d7  lea     rcx, [rsp+58h+strSecurityDescriptor]; this
0x18003c6dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c6e1  mov     eax, ebx
0x18003c6e3  mov     rcx, [rsp+58h+var_10]
0x18003c6e8  xor     rcx, rsp; StackCookie
0x18003c6eb  call    __security_check_cookie
0x18003c6f0  mov     rbx, [rsp+58h+arg_0]
0x18003c6f5  add     rsp, 50h
0x18003c6f9  pop     rdi
0x18003c6fa  retn
```
