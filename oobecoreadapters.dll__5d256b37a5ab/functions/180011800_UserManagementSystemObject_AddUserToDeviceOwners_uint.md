# UserManagementSystemObject::AddUserToDeviceOwners(uint)

- ea: `0x180011800`
- end: `0x1800119ee`
- name: `?AddUserToDeviceOwners@UserManagementSystemObject@@UEAAJI@Z`
- size: `494`
- prototype: `__int64 __fastcall(UserManagementSystemObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002b60`
- `0x1800036e4`
- `0x1800076b4`
- `0x1800076d4`
- `0x1800097f4`
- `0x1800117dc`
- `0x180011800`
- `0x180011af8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800118a2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800118a2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180011930`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180011930`
- `samcli!NetLocalGroupAddMembers` at `0x180011960`
- `samcli!NetLocalGroupAddMembers` at `0x180011960`

## string_xrefs

- `0x18001184c`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`
- `0x1800118af`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`
- `0x180011979`: `shellcommon\shell\oobe\core\components\com\usermanagement.cpp`

## pseudocode

```c
__int64 __fastcall UserManagementSystemObject::AddUserToDeviceOwners(UserManagementSystemObject *this, unsigned int a2)
{
  int UserSidFromUserId; // eax
  unsigned int LastError; // ebx
  const char *v4; // r9
  __int64 v5; // rdx
  signed int v6; // eax
  __int64 v7; // rdx
  int nSubAuthority2; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2a; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  _SID_NAME_USE peUse; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchReferencedDomainName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  void *v15; // [rsp+78h] [rbp-88h] BYREF
  BYTE buf[8]; // [rsp+80h] [rbp-80h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v19; // [rsp+A0h] [rbp-60h]
  WCHAR Name[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v15 = 0;
  UserSidFromUserId = UserManagementSystemObject::GetUserSidFromUserId(this, a2, &v15);
  LastError = UserSidFromUserId;
  if ( UserSidFromUserId >= 0 )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    Sid = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x247u, 0, 0, 0, 0, 0, 0, &Sid) )
    {
      cchName = 256;
      memset_0(Name, 0, 0x202u);
      cchReferencedDomainName = 15;
      *(_OWORD *)ReferencedDomainName = 0;
      v19 = 0;
      peUse = 0;
      if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        *(_QWORD *)buf = v15;
        v6 = NetLocalGroupAddMembers(0, Name, 0, buf, 1u);
        LastError = v6;
        if ( v6 == 2220 )
        {
          LastError = -2147023728;
          v7 = 51;
        }
        else
        {
          if ( !v6 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
            LastError = 0;
            goto LABEL_18;
          }
          if ( v6 > 0 )
            LastError = (unsigned __int16)v6 | 0x80070000;
          if ( (LastError & 0x80000000) == 0 )
            goto LABEL_6;
          v7 = 52;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
          (const char *)LastError,
          nSubAuthority2a);
LABEL_6:
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
        goto LABEL_18;
      }
      v5 = 45;
    }
    else
    {
      v5 = 37;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
                  v4);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\usermanagement.cpp",
    (const char *)(unsigned int)UserSidFromUserId,
    nSubAuthority2);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x180011800  mov     [rsp-8+arg_0], rbx
0x180011805  mov     [rsp-8+arg_10], rdi
0x18001180a  push    rbp
0x18001180b  lea     rbp, [rsp-1D0h]
0x180011813  sub     rsp, 2D0h
0x18001181a  mov     rax, cs:__security_cookie
0x180011821  xor     rax, rsp
0x180011824  mov     [rbp+1D0h+var_10], rax
0x18001182b  xor     edi, edi
0x18001182d  mov     [rsp+2D0h+var_258], rdi
0x180011832  lea     r8, [rsp+2D0h+var_258]; void **
0x180011837  call    ?GetUserSidFromUserId@UserManagementSystemObject@@AEAAJIPEAPEAX@Z; UserManagementSystemObject::GetUserSidFromUserId(uint,void * *)
0x18001183c  mov     ebx, eax
0x18001183e  test    eax, eax
0x180011840  jns     short loc_180011860
0x180011842  mov     rcx, [rbp+1D8h]; this
0x180011849  mov     r9d, eax; char *
0x18001184c  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x180011853  lea     edx, [rdi+18h]; void *
0x180011856  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001185b  jmp     loc_1800119BE
0x180011860  mov     dword ptr [rbp+1D0h+pIdentifierAuthority.Value], edi
0x180011863  mov     word ptr [rbp+1D0h+pIdentifierAuthority.Value+4], 500h
0x180011869  mov     [rsp+2D0h+Sid], rdi
0x18001186e  lea     rax, [rsp+2D0h+Sid]
0x180011873  mov     [rsp+2D0h+pSid], rax; pSid
0x180011878  mov     [rsp+2D0h+nSubAuthority7], edi; nSubAuthority7
0x18001187c  mov     [rsp+2D0h+nSubAuthority6], edi; nSubAuthority6
0x180011880  mov     [rsp+2D0h+nSubAuthority5], edi; nSubAuthority5
0x180011884  mov     [rsp+2D0h+nSubAuthority4], edi; nSubAuthority4
0x180011888  mov     [rsp+2D0h+nSubAuthority3], edi; nSubAuthority3
0x18001188c  mov     [rsp+2D0h+nSubAuthority2], edi; nSubAuthority2
0x180011890  mov     r9d, 247h; nSubAuthority1
0x180011896  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001189c  mov     dl, 2; nSubAuthorityCount
0x18001189e  lea     rcx, [rbp+1D0h+pIdentifierAuthority]; pIdentifierAuthority
0x1800118a2  call    cs:__imp_AllocateAndInitializeSid
0x1800118a8  test    eax, eax
0x1800118aa  jnz     short loc_1800118D3
0x1800118ac  lea     edx, [rax+25h]; void *
0x1800118af  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800118b6  mov     rcx, [rbp+1D8h]; this
0x1800118bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800118c2  mov     ebx, eax
0x1800118c4  lea     rcx, [rsp+2D0h+Sid]
0x1800118c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800118ce  jmp     loc_1800119BE
0x1800118d3  mov     [rsp+2D0h+cchName], 100h
0x1800118db  xor     edx, edx; Val
0x1800118dd  mov     r8d, 202h; Size
0x1800118e3  lea     rcx, [rbp+1D0h+Name]; void *
0x1800118e7  call    memset_0
0x1800118ec  mov     [rsp+2D0h+cchReferencedDomainName], 0Fh
0x1800118f4  xorps   xmm0, xmm0
0x1800118f7  movups  xmmword ptr [rbp+1D0h+ReferencedDomainName], xmm0
0x1800118fb  movups  [rbp+1D0h+var_230], xmm0
0x1800118ff  mov     [rsp+2D0h+peUse], edi
0x180011903  lea     rax, [rsp+2D0h+peUse]
0x180011908  mov     qword ptr [rsp+2D0h+nSubAuthority4], rax; peUse
0x18001190d  lea     rax, [rsp+2D0h+cchReferencedDomainName]
0x180011912  mov     qword ptr [rsp+2D0h+nSubAuthority3], rax; cchReferencedDomainName
0x180011917  lea     rax, [rbp+1D0h+ReferencedDomainName]
0x18001191b  mov     qword ptr [rsp+2D0h+nSubAuthority2], rax; ReferencedDomainName
0x180011920  lea     r9, [rsp+2D0h+cchName]; cchName
0x180011925  lea     r8, [rbp+1D0h+Name]; Name
0x180011929  mov     rdx, [rsp+2D0h+Sid]; Sid
0x18001192e  xor     ecx, ecx; lpSystemName
0x180011930  call    cs:__imp_LookupAccountSidW
0x180011936  test    eax, eax
0x180011938  jnz     short loc_180011942
0x18001193a  lea     edx, [rax+2Dh]
0x18001193d  jmp     loc_1800118AF
0x180011942  mov     rax, [rsp+2D0h+var_258]
0x180011947  mov     qword ptr [rbp+1D0h+buf], rax
0x18001194b  mov     [rsp+2D0h+nSubAuthority2], 1; int
0x180011953  lea     r9, [rbp+1D0h+buf]; buf
0x180011957  xor     r8d, r8d; level
0x18001195a  lea     rdx, [rbp+1D0h+Name]; groupname
0x18001195e  xor     ecx, ecx; servername
0x180011960  call    cs:__imp_NetLocalGroupAddMembers
0x180011966  mov     ebx, eax
0x180011968  cmp     eax, 8ACh
0x18001196d  jnz     short loc_180011994
0x18001196f  mov     ebx, 80070490h
0x180011974  mov     edx, 33h ; '3'; void *
0x180011979  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\oobe\\core\\compone"...
0x180011980  mov     r9d, ebx; char *
0x180011983  mov     rcx, [rbp+1D8h]; this
0x18001198a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001198f  jmp     loc_1800118C4
0x180011994  test    eax, eax
0x180011996  jz      short loc_1800119B2
0x180011998  jle     short loc_1800119A3
0x18001199a  movzx   ebx, ax
0x18001199d  or      ebx, 80070000h
0x1800119a3  test    ebx, ebx
0x1800119a5  jns     loc_1800118C4
0x1800119ab  mov     edx, 34h ; '4'
0x1800119b0  jmp     short loc_180011979
0x1800119b2  lea     rcx, [rsp+2D0h+Sid]
0x1800119b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800119bc  mov     ebx, edi
0x1800119be  lea     rcx, [rsp+2D0h+var_258]
0x1800119c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800119c8  mov     eax, ebx
0x1800119ca  mov     rcx, [rbp+1D0h+var_10]
0x1800119d1  xor     rcx, rsp; StackCookie
0x1800119d4  call    __security_check_cookie
0x1800119d9  lea     r11, [rsp+2D0h+var_s0]
0x1800119e1  mov     rbx, [r11+10h]
0x1800119e5  mov     rdi, [r11+20h]
0x1800119e9  mov     rsp, r11
0x1800119ec  pop     rbp
0x1800119ed  retn
```
