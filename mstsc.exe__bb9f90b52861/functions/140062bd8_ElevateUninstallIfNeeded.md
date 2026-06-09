# ElevateUninstallIfNeeded

- ea: `0x140062bd8`
- end: `0x140062fba`
- name: `ElevateUninstallIfNeeded`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14006590c`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14006243c`
- `0x1400626ec`
- `0x140062730`
- `0x140062bd8`
- `0x140113390`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140062c0a`
- `KERNEL32!GetCurrentProcess` at `0x140062c0a`
- `KERNEL32!GetLastError` at `0x140062cd7`
- `KERNEL32!GetLastError` at `0x140062e10`
- `KERNEL32!GetLastError` at `0x140062f24`
- `KERNEL32!GetLastError` at `0x140062cd7`
- `KERNEL32!GetLastError` at `0x140062e10`
- `KERNEL32!GetLastError` at `0x140062f24`
- `SHELL32!ShellExecuteExW` at `0x140062f1a`
- `SHELL32!ShellExecuteExW` at `0x140062f1a`
- `ADVAPI32!GetAce` at `0x140062d64`
- `ADVAPI32!GetAce` at `0x140062d64`
- `ADVAPI32!GetSecurityInfo` at `0x140062c42`
- `ADVAPI32!GetSecurityInfo` at `0x140062c42`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140062d82`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140062d82`
- `ADVAPI32!GetSidSubAuthority` at `0x140062d92`
- `ADVAPI32!GetSidSubAuthority` at `0x140062d92`
- `ADVAPI32!GetAclInformation` at `0x140062ccd`
- `ADVAPI32!GetAclInformation` at `0x140062ccd`

## string_xrefs

- `0x140062f00`: `/uninstall`
- `0x140062eee`: `/uninstall /noPromptBeforeRestart`

## pseudocode

```c
__int64 __fastcall ElevateUninstallIfNeeded(char a1)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // rdx
  signed int SecurityInfo; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  PACL v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rdx
  DWORD v9; // ebx
  BOOL v10; // edi
  char *v11; // rdi
  unsigned int v12; // eax
  unsigned int v13; // eax
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  PACL *ppDacl; // [rsp+28h] [rbp-91h]
  LPVOID pAce; // [rsp+40h] [rbp-79h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-71h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+50h] [rbp-69h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-59h] BYREF
  __int64 pAclInformation; // [rsp+D0h] [rbp+17h] BYREF
  int v23; // [rsp+D8h] [rbp+1Fh]

  pAcl = 0;
  ppSecurityDescriptor[0] = 0;
  CurrentProcess = GetCurrentProcess();
  SecurityInfo = GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 0x10u, 0, 0, 0, &pAcl, ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
        CurrentThreadActivityIdPrefix,
        SecurityInfo);
    }
    if ( SecurityInfo > 0 )
      SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
    goto LABEL_56;
  }
  v6 = pAcl;
  if ( pAcl )
  {
    pAclInformation = 0;
    v23 = 0;
    if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      SecurityInfo = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 38;
LABEL_14:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
          v7,
          SecurityInfo);
      }
LABEL_15:
      if ( SecurityInfo > 0 )
        SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
      if ( SecurityInfo >= 0 )
        SecurityInfo = -2147467259;
      goto LABEL_56;
    }
    v9 = 0;
    v10 = 1;
    if ( (_DWORD)pAclInformation )
    {
      while ( 1 )
      {
        pAce = 0;
        if ( !GetAce(pAcl, v9, &pAce) )
          break;
        if ( *(_BYTE *)pAce == 17 )
        {
          v11 = (char *)pAce + 8;
          if ( *GetSidSubAuthorityCount((char *)pAce + 8) != 1 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                40,
                WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
                v12,
                -2147418113);
            }
            SecurityInfo = -2147418113;
            goto LABEL_56;
          }
          v10 = *GetSidSubAuthority(v11, 0) < 0x3000;
        }
        if ( ++v9 >= (unsigned int)pAclInformation )
        {
          if ( v10 )
            goto LABEL_37;
          SecurityInfo = 1;
          goto LABEL_56;
        }
      }
      SecurityInfo = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 39;
        goto LABEL_14;
      }
      goto LABEL_15;
    }
  }
LABEL_37:
  pAce = 0;
  SecurityInfo = wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
                   v6,
                   v3,
                   &pAce);
  if ( SecurityInfo >= 0 )
  {
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.cbSize = 112;
    pExecInfo.lpVerb = L"runas";
    pExecInfo.lpFile = (LPCWSTR)pAce;
    v14 = L"/uninstall";
    if ( !a1 )
      v14 = L"/uninstall /noPromptBeforeRestart";
    pExecInfo.nShow = 1;
    pExecInfo.lpParameters = v14;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      SecurityInfo = 0;
    }
    else
    {
      SecurityInfo = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
          v15,
          SecurityInfo);
      }
      if ( SecurityInfo > 0 )
        SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
      if ( SecurityInfo >= 0 )
        SecurityInfo = -2147467259;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(ppDacl) = SecurityInfo;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
      v13,
      (__int64)"wil::GetModuleFileNameW failed",
      ppDacl);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pAce);
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ppSecurityDescriptor);
  return (unsigned int)SecurityInfo;
}

```

## disassembly

```asm
0x140062bd8  push    rbp
0x140062bda  push    rbx
0x140062bdb  push    rsi
0x140062bdc  push    rdi
0x140062bdd  lea     rbp, [rsp-3Fh]
0x140062be2  sub     rsp, 0F8h
0x140062be9  mov     rax, cs:__security_cookie
0x140062bf0  xor     rax, rsp
0x140062bf3  mov     [rbp+57h+var_30], rax
0x140062bf7  mov     sil, cl
0x140062bfa  mov     [rbp+57h+pAcl], 0
0x140062c02  mov     [rbp+57h+var_C0], 0
0x140062c0a  call    cs:__imp_GetCurrentProcess
0x140062c10  xor     r9d, r9d; ppsidOwner
0x140062c13  lea     rcx, [rbp+57h+var_C0]
0x140062c17  mov     [rsp+110h+ppSecurityDescriptor], rcx; ppSecurityDescriptor
0x140062c1c  lea     rcx, [rbp+57h+pAcl]
0x140062c20  mov     [rsp+110h+ppSacl], rcx; ppSacl
0x140062c25  mov     rcx, rax; handle
0x140062c28  mov     [rsp+110h+ppDacl], 0; ppDacl
0x140062c31  lea     edx, [r9+6]; ObjectType
0x140062c35  mov     [rsp+110h+ppsidGroup], 0; ppsidGroup
0x140062c3e  lea     r8d, [r9+10h]; SecurityInfo
0x140062c42  call    cs:__imp_GetSecurityInfo
0x140062c48  mov     ebx, eax
0x140062c4a  test    eax, eax
0x140062c4c  jz      short loc_140062CAB
0x140062c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140062c55  lea     rax, WPP_GLOBAL_Control
0x140062c5c  cmp     rcx, rax
0x140062c5f  jz      short loc_140062C95
0x140062c61  test    byte ptr [rcx+1Ch], 8
0x140062c65  jz      short loc_140062C95
0x140062c67  cmp     byte ptr [rcx+19h], 2
0x140062c6b  jb      short loc_140062C95
0x140062c6d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140062c79  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140062c80  mov     edx, 25h ; '%'
0x140062c85  mov     dword ptr [rsp+110h+ppsidGroup], ebx
0x140062c89  mov     r9d, eax
0x140062c8c  mov     rcx, [rcx+10h]
0x140062c90  call    WPP_SF_Dd
0x140062c95  test    ebx, ebx
0x140062c97  jle     loc_140062F97
0x140062c9d  movzx   ebx, bx
0x140062ca0  or      ebx, 80070000h
0x140062ca6  jmp     loc_140062F97
0x140062cab  mov     rcx, [rbp+57h+pAcl]; pAcl
0x140062caf  test    rcx, rcx
0x140062cb2  jz      loc_140062E52
0x140062cb8  xor     eax, eax
0x140062cba  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x140062cbe  mov     [rbp+57h+pAclInformation], rax
0x140062cc2  mov     [rbp+57h+var_38], eax
0x140062cc5  lea     r9d, [rax+2]; dwAclInformationClass
0x140062cc9  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140062ccd  call    cs:__imp_GetAclInformation
0x140062cd3  test    eax, eax
0x140062cd5  jnz     short loc_140062D42
0x140062cd7  call    cs:__imp_GetLastError
0x140062cdd  mov     ebx, eax
0x140062cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140062ce6  lea     rax, WPP_GLOBAL_Control
0x140062ced  cmp     rcx, rax
0x140062cf0  jz      short loc_140062D26
0x140062cf2  test    byte ptr [rcx+1Ch], 8
0x140062cf6  jz      short loc_140062D26
0x140062cf8  cmp     byte ptr [rcx+19h], 2
0x140062cfc  jb      short loc_140062D26
0x140062cfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062d03  mov     edx, 26h ; '&'
0x140062d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140062d0f  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140062d16  mov     r9d, eax
0x140062d19  mov     dword ptr [rsp+110h+ppsidGroup], ebx
0x140062d1d  mov     rcx, [rcx+10h]
0x140062d21  call    WPP_SF_Dd
0x140062d26  test    ebx, ebx
0x140062d28  jle     short loc_140062D33
0x140062d2a  movzx   ebx, bx
0x140062d2d  or      ebx, 80070000h
0x140062d33  test    ebx, ebx
0x140062d35  mov     eax, 80004005h
0x140062d3a  cmovns  ebx, eax
0x140062d3d  jmp     loc_140062F97
0x140062d42  xor     ebx, ebx
0x140062d44  mov     edi, 1
0x140062d49  cmp     dword ptr [rbp+57h+pAclInformation], ebx
0x140062d4c  jbe     loc_140062E52
0x140062d52  mov     rcx, [rbp+57h+pAcl]; pAcl
0x140062d56  lea     r8, [rbp+57h+pAce]; pAce
0x140062d5a  mov     edx, ebx; dwAceIndex
0x140062d5c  mov     [rbp+57h+pAce], 0
0x140062d64  call    cs:__imp_GetAce
0x140062d6a  test    eax, eax
0x140062d6c  jz      loc_140062E10
0x140062d72  mov     rax, [rbp+57h+pAce]
0x140062d76  cmp     byte ptr [rax], 11h
0x140062d79  jnz     short loc_140062DA4
0x140062d7b  lea     rdi, [rax+8]
0x140062d7f  mov     rcx, rdi; pSid
0x140062d82  call    cs:__imp_GetSidSubAuthorityCount
0x140062d88  cmp     byte ptr [rax], 1
0x140062d8b  jnz     short loc_140062DBB
0x140062d8d  xor     edx, edx; nSubAuthority
0x140062d8f  mov     rcx, rdi; pSid
0x140062d92  call    cs:__imp_GetSidSubAuthority
0x140062d98  xor     edi, edi
0x140062d9a  cmp     dword ptr [rax], 3000h
0x140062da0  setb    dil
0x140062da4  inc     ebx
0x140062da6  cmp     ebx, dword ptr [rbp+57h+pAclInformation]
0x140062da9  jb      short loc_140062D52
0x140062dab  test    edi, edi
0x140062dad  jnz     loc_140062E52
0x140062db3  lea     ebx, [rdi+1]
0x140062db6  jmp     loc_140062F97
0x140062dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140062dc2  lea     rax, WPP_GLOBAL_Control
0x140062dc9  cmp     rcx, rax
0x140062dcc  jz      short loc_140062E06
0x140062dce  test    byte ptr [rcx+1Ch], 8
0x140062dd2  jz      short loc_140062E06
0x140062dd4  cmp     byte ptr [rcx+19h], 2
0x140062dd8  jb      short loc_140062E06
0x140062dda  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x140062de6  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140062ded  mov     edx, 28h ; '('
0x140062df2  mov     dword ptr [rsp+110h+ppsidGroup], 8000FFFFh
0x140062dfa  mov     r9d, eax
0x140062dfd  mov     rcx, [rcx+10h]
0x140062e01  call    WPP_SF_Dd
0x140062e06  mov     ebx, 8000FFFFh
0x140062e0b  jmp     loc_140062F97
0x140062e10  call    cs:__imp_GetLastError
0x140062e16  mov     ebx, eax
0x140062e18  mov     rcx, cs:WPP_GLOBAL_Control
0x140062e1f  lea     rax, WPP_GLOBAL_Control
0x140062e26  cmp     rcx, rax
0x140062e29  jz      loc_140062D26
0x140062e2f  test    byte ptr [rcx+1Ch], 8
0x140062e33  jz      loc_140062D26
0x140062e39  cmp     byte ptr [rcx+19h], 2
0x140062e3d  jb      loc_140062D26
0x140062e43  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062e48  mov     edx, 27h ; '''
0x140062e4d  jmp     loc_140062D08
0x140062e52  lea     r8, [rbp+57h+pAce]
0x140062e56  mov     [rbp+57h+pAce], 0
0x140062e5e  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140062e63  mov     ebx, eax
0x140062e65  test    eax, eax
0x140062e67  jns     short loc_140062ECD
0x140062e69  mov     rcx, cs:WPP_GLOBAL_Control
0x140062e70  lea     rax, WPP_GLOBAL_Control
0x140062e77  cmp     rcx, rax
0x140062e7a  jz      loc_140062F8E
0x140062e80  test    byte ptr [rcx+1Ch], 8
0x140062e84  jz      loc_140062F8E
0x140062e8a  cmp     byte ptr [rcx+19h], 2
0x140062e8e  jb      loc_140062F8E
0x140062e94  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062e99  lea     rcx, aWilGetmodulefi; "wil::GetModuleFileNameW failed"
0x140062ea0  mov     dword ptr [rsp+110h+ppDacl], ebx
0x140062ea4  mov     [rsp+110h+ppsidGroup], rcx
0x140062ea9  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140062eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140062eb7  mov     edx, 29h ; ')'
0x140062ebc  mov     r9d, eax
0x140062ebf  mov     rcx, [rcx+10h]
0x140062ec3  call    WPP_SF_DsD
0x140062ec8  jmp     loc_140062F8E
0x140062ecd  mov     ebx, 70h ; 'p'
0x140062ed2  lea     rcx, [rbp+57h+pExecInfo]; void *
0x140062ed6  mov     r8d, ebx; Size
0x140062ed9  xor     edx, edx; Val
0x140062edb  call    memset_0
0x140062ee0  lea     rax, aRunas; "runas"
0x140062ee7  mov     [rbp+57h+pExecInfo.cbSize], ebx
0x140062eea  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x140062eee  lea     rcx, aUninstallNopro; "/uninstall /noPromptBeforeRestart"
0x140062ef5  mov     rax, [rbp+57h+pAce]
0x140062ef9  test    sil, sil
0x140062efc  mov     [rbp+57h+pExecInfo.lpFile], rax
0x140062f00  lea     rax, aUninstall; "/uninstall"
0x140062f07  cmovz   rax, rcx
0x140062f0b  mov     [rbp+57h+pExecInfo.nShow], 1
0x140062f12  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x140062f16  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x140062f1a  call    cs:__imp_ShellExecuteExW
0x140062f20  test    eax, eax
0x140062f22  jnz     short loc_140062F8C
0x140062f24  call    cs:__imp_GetLastError
0x140062f2a  mov     ebx, eax
0x140062f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140062f33  lea     rax, WPP_GLOBAL_Control
0x140062f3a  cmp     rcx, rax
0x140062f3d  jz      short loc_140062F73
0x140062f3f  test    byte ptr [rcx+1Ch], 8
0x140062f43  jz      short loc_140062F73
0x140062f45  cmp     byte ptr [rcx+19h], 2
0x140062f49  jb      short loc_140062F73
0x140062f4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140062f57  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140062f5e  mov     edx, 2Ah ; '*'
0x140062f63  mov     dword ptr [rsp+110h+ppsidGroup], ebx
0x140062f67  mov     r9d, eax
0x140062f6a  mov     rcx, [rcx+10h]
0x140062f6e  call    WPP_SF_Dd
0x140062f73  test    ebx, ebx
0x140062f75  jle     short loc_140062F80
0x140062f77  movzx   ebx, bx
0x140062f7a  or      ebx, 80070000h
0x140062f80  test    ebx, ebx
0x140062f82  mov     eax, 80004005h
0x140062f87  cmovns  ebx, eax
0x140062f8a  jmp     short loc_140062F8E
0x140062f8c  xor     ebx, ebx
0x140062f8e  lea     rcx, [rbp+57h+pAce]
0x140062f92  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140062f97  lea     rcx, [rbp+57h+var_C0]
0x140062f9b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140062fa0  mov     eax, ebx
0x140062fa2  mov     rcx, [rbp+57h+var_30]
0x140062fa6  xor     rcx, rsp; StackCookie
0x140062fa9  call    __security_check_cookie
0x140062fae  add     rsp, 0F8h
0x140062fb5  pop     rdi
0x140062fb6  pop     rsi
0x140062fb7  pop     rbx
0x140062fb8  pop     rbp
0x140062fb9  retn
```
