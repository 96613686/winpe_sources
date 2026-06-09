# ElevateUninstallIfNeeded

- ea: `0x140060a68`
- end: `0x140060e4a`
- name: `ElevateUninstallIfNeeded`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14006379c`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400602cc`
- `0x14006057c`
- `0x1400605c0`
- `0x140060a68`
- `0x140111220`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140060a9a`
- `KERNEL32!GetCurrentProcess` at `0x140060a9a`
- `KERNEL32!GetLastError` at `0x140060b67`
- `KERNEL32!GetLastError` at `0x140060ca0`
- `KERNEL32!GetLastError` at `0x140060db4`
- `KERNEL32!GetLastError` at `0x140060b67`
- `KERNEL32!GetLastError` at `0x140060ca0`
- `KERNEL32!GetLastError` at `0x140060db4`
- `SHELL32!ShellExecuteExW` at `0x140060daa`
- `SHELL32!ShellExecuteExW` at `0x140060daa`
- `ADVAPI32!GetAce` at `0x140060bf4`
- `ADVAPI32!GetAce` at `0x140060bf4`
- `ADVAPI32!GetSecurityInfo` at `0x140060ad2`
- `ADVAPI32!GetSecurityInfo` at `0x140060ad2`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140060c12`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140060c12`
- `ADVAPI32!GetSidSubAuthority` at `0x140060c22`
- `ADVAPI32!GetSidSubAuthority` at `0x140060c22`
- `ADVAPI32!GetAclInformation` at `0x140060b5d`
- `ADVAPI32!GetAclInformation` at `0x140060b5d`

## string_xrefs

- `0x140060d90`: `/uninstall`
- `0x140060d7e`: `/uninstall /noPromptBeforeRestart`

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
  LPVOID pAce; // [rsp+40h] [rbp-79h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-71h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+50h] [rbp-69h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-59h] BYREF
  __int64 pAclInformation; // [rsp+D0h] [rbp+17h] BYREF
  int v22; // [rsp+D8h] [rbp+1Fh]

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
    v22 = 0;
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
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids,
      v13,
      (__int64)"wil::GetModuleFileNameW failed",
      SecurityInfo);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pAce);
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ppSecurityDescriptor);
  return (unsigned int)SecurityInfo;
}

```

## disassembly

```asm
0x140060a68  push    rbp
0x140060a6a  push    rbx
0x140060a6b  push    rsi
0x140060a6c  push    rdi
0x140060a6d  lea     rbp, [rsp-3Fh]
0x140060a72  sub     rsp, 0F8h
0x140060a79  mov     rax, cs:__security_cookie
0x140060a80  xor     rax, rsp
0x140060a83  mov     [rbp+57h+var_30], rax
0x140060a87  mov     sil, cl
0x140060a8a  mov     [rbp+57h+pAcl], 0
0x140060a92  mov     [rbp+57h+var_C0], 0
0x140060a9a  call    cs:__imp_GetCurrentProcess
0x140060aa0  xor     r9d, r9d; ppsidOwner
0x140060aa3  lea     rcx, [rbp+57h+var_C0]
0x140060aa7  mov     [rsp+110h+ppSecurityDescriptor], rcx; ppSecurityDescriptor
0x140060aac  lea     rcx, [rbp+57h+pAcl]
0x140060ab0  mov     [rsp+110h+ppSacl], rcx; ppSacl
0x140060ab5  mov     rcx, rax; handle
0x140060ab8  mov     [rsp+110h+ppDacl], 0; ppDacl
0x140060ac1  lea     edx, [r9+6]; ObjectType
0x140060ac5  mov     [rsp+110h+ppsidGroup], 0; ppsidGroup
0x140060ace  lea     r8d, [r9+10h]; SecurityInfo
0x140060ad2  call    cs:__imp_GetSecurityInfo
0x140060ad8  mov     ebx, eax
0x140060ada  test    eax, eax
0x140060adc  jz      short loc_140060B3B
0x140060ade  mov     rcx, cs:WPP_GLOBAL_Control
0x140060ae5  lea     rax, WPP_GLOBAL_Control
0x140060aec  cmp     rcx, rax
0x140060aef  jz      short loc_140060B25
0x140060af1  test    byte ptr [rcx+1Ch], 8
0x140060af5  jz      short loc_140060B25
0x140060af7  cmp     byte ptr [rcx+19h], 2
0x140060afb  jb      short loc_140060B25
0x140060afd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060b02  mov     rcx, cs:WPP_GLOBAL_Control
0x140060b09  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140060b10  mov     edx, 25h ; '%'
0x140060b15  mov     dword ptr [rsp+110h+ppsidGroup], ebx
0x140060b19  mov     r9d, eax
0x140060b1c  mov     rcx, [rcx+10h]
0x140060b20  call    WPP_SF_Dd
0x140060b25  test    ebx, ebx
0x140060b27  jle     loc_140060E27
0x140060b2d  movzx   ebx, bx
0x140060b30  or      ebx, 80070000h
0x140060b36  jmp     loc_140060E27
0x140060b3b  mov     rcx, [rbp+57h+pAcl]; pAcl
0x140060b3f  test    rcx, rcx
0x140060b42  jz      loc_140060CE2
0x140060b48  xor     eax, eax
0x140060b4a  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x140060b4e  mov     [rbp+57h+pAclInformation], rax
0x140060b52  mov     [rbp+57h+var_38], eax
0x140060b55  lea     r9d, [rax+2]; dwAclInformationClass
0x140060b59  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140060b5d  call    cs:__imp_GetAclInformation
0x140060b63  test    eax, eax
0x140060b65  jnz     short loc_140060BD2
0x140060b67  call    cs:__imp_GetLastError
0x140060b6d  mov     ebx, eax
0x140060b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140060b76  lea     rax, WPP_GLOBAL_Control
0x140060b7d  cmp     rcx, rax
0x140060b80  jz      short loc_140060BB6
0x140060b82  test    byte ptr [rcx+1Ch], 8
0x140060b86  jz      short loc_140060BB6
0x140060b88  cmp     byte ptr [rcx+19h], 2
0x140060b8c  jb      short loc_140060BB6
0x140060b8e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060b93  mov     edx, 26h ; '&'
0x140060b98  mov     rcx, cs:WPP_GLOBAL_Control
0x140060b9f  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140060ba6  mov     r9d, eax
0x140060ba9  mov     dword ptr [rsp+110h+ppsidGroup], ebx
0x140060bad  mov     rcx, [rcx+10h]
0x140060bb1  call    WPP_SF_Dd
0x140060bb6  test    ebx, ebx
0x140060bb8  jle     short loc_140060BC3
0x140060bba  movzx   ebx, bx
0x140060bbd  or      ebx, 80070000h
0x140060bc3  test    ebx, ebx
0x140060bc5  mov     eax, 80004005h
0x140060bca  cmovns  ebx, eax
0x140060bcd  jmp     loc_140060E27
0x140060bd2  xor     ebx, ebx
0x140060bd4  mov     edi, 1
0x140060bd9  cmp     dword ptr [rbp+57h+pAclInformation], ebx
0x140060bdc  jbe     loc_140060CE2
0x140060be2  mov     rcx, [rbp+57h+pAcl]; pAcl
0x140060be6  lea     r8, [rbp+57h+pAce]; pAce
0x140060bea  mov     edx, ebx; dwAceIndex
0x140060bec  mov     [rbp+57h+pAce], 0
0x140060bf4  call    cs:__imp_GetAce
0x140060bfa  test    eax, eax
0x140060bfc  jz      loc_140060CA0
0x140060c02  mov     rax, [rbp+57h+pAce]
0x140060c06  cmp     byte ptr [rax], 11h
0x140060c09  jnz     short loc_140060C34
0x140060c0b  lea     rdi, [rax+8]
0x140060c0f  mov     rcx, rdi; pSid
0x140060c12  call    cs:__imp_GetSidSubAuthorityCount
0x140060c18  cmp     byte ptr [rax], 1
0x140060c1b  jnz     short loc_140060C4B
0x140060c1d  xor     edx, edx; nSubAuthority
0x140060c1f  mov     rcx, rdi; pSid
0x140060c22  call    cs:__imp_GetSidSubAuthority
0x140060c28  xor     edi, edi
0x140060c2a  cmp     dword ptr [rax], 3000h
0x140060c30  setb    dil
0x140060c34  inc     ebx
0x140060c36  cmp     ebx, dword ptr [rbp+57h+pAclInformation]
0x140060c39  jb      short loc_140060BE2
0x140060c3b  test    edi, edi
0x140060c3d  jnz     loc_140060CE2
0x140060c43  lea     ebx, [rdi+1]
0x140060c46  jmp     loc_140060E27
0x140060c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140060c52  lea     rax, WPP_GLOBAL_Control
0x140060c59  cmp     rcx, rax
0x140060c5c  jz      short loc_140060C96
0x140060c5e  test    byte ptr [rcx+1Ch], 8
0x140060c62  jz      short loc_140060C96
0x140060c64  cmp     byte ptr [rcx+19h], 2
0x140060c68  jb      short loc_140060C96
0x140060c6a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140060c76  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140060c7d  mov     edx, 28h ; '('
0x140060c82  mov     dword ptr [rsp+110h+ppsidGroup], 8000FFFFh
0x140060c8a  mov     r9d, eax
0x140060c8d  mov     rcx, [rcx+10h]
0x140060c91  call    WPP_SF_Dd
0x140060c96  mov     ebx, 8000FFFFh
0x140060c9b  jmp     loc_140060E27
0x140060ca0  call    cs:__imp_GetLastError
0x140060ca6  mov     ebx, eax
0x140060ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x140060caf  lea     rax, WPP_GLOBAL_Control
0x140060cb6  cmp     rcx, rax
0x140060cb9  jz      loc_140060BB6
0x140060cbf  test    byte ptr [rcx+1Ch], 8
0x140060cc3  jz      loc_140060BB6
0x140060cc9  cmp     byte ptr [rcx+19h], 2
0x140060ccd  jb      loc_140060BB6
0x140060cd3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060cd8  mov     edx, 27h ; '''
0x140060cdd  jmp     loc_140060B98
0x140060ce2  lea     r8, [rbp+57h+pAce]
0x140060ce6  mov     [rbp+57h+pAce], 0
0x140060cee  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140060cf3  mov     ebx, eax
0x140060cf5  test    eax, eax
0x140060cf7  jns     short loc_140060D5D
0x140060cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140060d00  lea     rax, WPP_GLOBAL_Control
0x140060d07  cmp     rcx, rax
0x140060d0a  jz      loc_140060E1E
0x140060d10  test    byte ptr [rcx+1Ch], 8
0x140060d14  jz      loc_140060E1E
0x140060d1a  cmp     byte ptr [rcx+19h], 2
0x140060d1e  jb      loc_140060E1E
0x140060d24  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060d29  lea     rcx, aWilGetmodulefi; "wil::GetModuleFileNameW failed"
0x140060d30  mov     dword ptr [rsp+110h+ppDacl], ebx
0x140060d34  mov     [rsp+110h+ppsidGroup], rcx
0x140060d39  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140060d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140060d47  mov     edx, 29h ; ')'
0x140060d4c  mov     r9d, eax
0x140060d4f  mov     rcx, [rcx+10h]
0x140060d53  call    WPP_SF_DsD
0x140060d58  jmp     loc_140060E1E
0x140060d5d  mov     ebx, 70h ; 'p'
0x140060d62  lea     rcx, [rbp+57h+pExecInfo]; void *
0x140060d66  mov     r8d, ebx; Size
0x140060d69  xor     edx, edx; Val
0x140060d6b  call    memset_0
0x140060d70  lea     rax, aRunas; "runas"
0x140060d77  mov     [rbp+57h+pExecInfo.cbSize], ebx
0x140060d7a  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x140060d7e  lea     rcx, aUninstallNopro; "/uninstall /noPromptBeforeRestart"
0x140060d85  mov     rax, [rbp+57h+pAce]
0x140060d89  test    sil, sil
0x140060d8c  mov     [rbp+57h+pExecInfo.lpFile], rax
0x140060d90  lea     rax, aUninstall; "/uninstall"
0x140060d97  cmovz   rax, rcx
0x140060d9b  mov     [rbp+57h+pExecInfo.nShow], 1
0x140060da2  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x140060da6  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x140060daa  call    cs:__imp_ShellExecuteExW
0x140060db0  test    eax, eax
0x140060db2  jnz     short loc_140060E1C
0x140060db4  call    cs:__imp_GetLastError
0x140060dba  mov     ebx, eax
0x140060dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140060dc3  lea     rax, WPP_GLOBAL_Control
0x140060dca  cmp     rcx, rax
0x140060dcd  jz      short loc_140060E03
0x140060dcf  test    byte ptr [rcx+1Ch], 8
0x140060dd3  jz      short loc_140060E03
0x140060dd5  cmp     byte ptr [rcx+19h], 2
0x140060dd9  jb      short loc_140060E03
0x140060ddb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060de0  mov     rcx, cs:WPP_GLOBAL_Control
0x140060de7  lea     r8, WPP_411c4c6c2608386c617cb4fedebe9afb_Traceguids
0x140060dee  mov     edx, 2Ah ; '*'
0x140060df3  mov     dword ptr [rsp+110h+ppsidGroup], ebx
0x140060df7  mov     r9d, eax
0x140060dfa  mov     rcx, [rcx+10h]
0x140060dfe  call    WPP_SF_Dd
0x140060e03  test    ebx, ebx
0x140060e05  jle     short loc_140060E10
0x140060e07  movzx   ebx, bx
0x140060e0a  or      ebx, 80070000h
0x140060e10  test    ebx, ebx
0x140060e12  mov     eax, 80004005h
0x140060e17  cmovns  ebx, eax
0x140060e1a  jmp     short loc_140060E1E
0x140060e1c  xor     ebx, ebx
0x140060e1e  lea     rcx, [rbp+57h+pAce]
0x140060e22  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140060e27  lea     rcx, [rbp+57h+var_C0]
0x140060e2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140060e30  mov     eax, ebx
0x140060e32  mov     rcx, [rbp+57h+var_30]
0x140060e36  xor     rcx, rsp; StackCookie
0x140060e39  call    __security_check_cookie
0x140060e3e  add     rsp, 0F8h
0x140060e45  pop     rdi
0x140060e46  pop     rsi
0x140060e47  pop     rbx
0x140060e48  pop     rbp
0x140060e49  retn
```
