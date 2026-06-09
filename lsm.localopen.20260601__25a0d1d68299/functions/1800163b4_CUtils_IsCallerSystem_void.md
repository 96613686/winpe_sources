# CUtils::IsCallerSystem(void)

- ea: `0x1800163b4`
- end: `0x18001673a`
- name: `?IsCallerSystem@CUtils@@SAJXZ`
- size: `902`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015510`
- `0x180016960`
- `0x180024500`
- `0x18004bc10`

## callees

- `0x1800077a0`
- `0x1800163b4`
- `0x180022920`
- `0x180040f54`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001642b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001642b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016678`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016495`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016418`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016418`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800163fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800163fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800165ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800165ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016711`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180016591`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180016642`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180016591`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180016642`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x1800164a5`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x1800164a5`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001653e`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001653e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800164f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800164f7`

## string_xrefs

- `0x18001668f`: `IsCallerSystem: Token access denied %x`
- `0x180016446`: `IsCallerSystem: Could not open thread token %x`
- `0x18001651e`: `IsCallerSystem: Could not convert security descriptor string %x`
- `0x180016669`: `IsCallerSystem: Token access check failed %x`
- `0x1800166bd`: `IsCallerSystem: Token is restricted %x`
- `0x1800164d9`: `IsCallerSystem: IsTokenRestricted failed %x`
- `0x1800165c4`: `IsCallerSystem: Token access check probe failed %x`
- `0x180016606`: `IsCallerSystem: Failed to allocate privilege set %x`
- `0x1800165dc`: `IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x`
- `0x18001669e`: `IsCallerSystem: Token missing required right`
- `0x18001647f`: `IsTokenSid( System ) failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::IsCallerSystem(void)
{
  struct _PRIVILEGE_SET *v0; // rsi
  HANDLE CurrentThread; // rax
  signed int v2; // eax
  unsigned int v3; // ebx
  void *v4; // rdx
  int IsTokenSid; // eax
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  DWORD PrivilegeSetLength; // [rsp+40h] [rbp-19h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-15h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-11h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-Dh] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-1h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+7h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+17h] BYREF

  v0 = 0;
  TokenHandle = 0;
  PrivilegeSetLength = 0;
  GrantedAccess = 0;
  SecurityDescriptor = 0;
  AccessMask = 0x40000000;
  CurrentThread = GetCurrentThread();
  AccessStatus = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( AccessStatus )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl'::`2'::impl) )
    {
      SetLastError(0);
      if ( IsTokenRestricted(TokenHandle) )
      {
        v3 = -2147024891;
        _DbgPrintMessage(8, "IsCallerSystem: Token is restricted %x", 2147942405LL);
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 )
        {
          _DbgPrintMessage(8, "IsCallerSystem: IsTokenRestricted failed %x", v3);
          goto LABEL_38;
        }
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
               L"O:SYG:BAD:(A;;0x1;;;SY)",
               1u,
               &SecurityDescriptor,
               0) )
        {
          GenericMapping = (struct _GENERIC_MAPPING)xmmword_1800A8408;
          MapGenericMask(&AccessMask, &GenericMapping);
          memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
          PrivilegeSetLength = 20;
          if ( AccessCheck(
                 SecurityDescriptor,
                 TokenHandle,
                 AccessMask,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
            goto LABEL_30;
          }
          v8 = GetLastError();
          v3 = v8;
          if ( v8 > 0 )
            v3 = (unsigned __int16)v8 | 0x80070000;
          if ( v3 != -2147024774 )
          {
            _DbgPrintMessage(8, "IsCallerSystem: Token access check probe failed %x", v3);
            goto LABEL_38;
          }
          if ( !PrivilegeSetLength )
          {
            v3 = -2147418113;
            _DbgPrintMessage(
              8,
              "IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x",
              2147549183LL);
            goto LABEL_38;
          }
          v0 = (struct _PRIVILEGE_SET *)LocalAlloc(0, PrivilegeSetLength);
          if ( !v0 )
          {
            v3 = -2147024882;
            _DbgPrintMessage(8, "IsCallerSystem: Failed to allocate privilege set %x", 2147942414LL);
            goto LABEL_38;
          }
          if ( AccessCheck(
                 SecurityDescriptor,
                 TokenHandle,
                 AccessMask,
                 &GenericMapping,
                 v0,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus) )
          {
LABEL_30:
            if ( AccessStatus )
            {
              if ( (GrantedAccess & 1) != 0 )
              {
                v3 = 0;
              }
              else
              {
                v3 = 1;
                _DbgPrintMessage(8, "IsCallerSystem: Token missing required right");
              }
            }
            else
            {
              v10 = GetLastError();
              v3 = v10;
              if ( v10 > 0 )
                v3 = (unsigned __int16)v10 | 0x80070000;
              _DbgPrintMessage(8, "IsCallerSystem: Token access denied %x", v3);
            }
          }
          else
          {
            v9 = GetLastError();
            v3 = v9;
            if ( v9 > 0 )
              v3 = (unsigned __int16)v9 | 0x80070000;
            _DbgPrintMessage(8, "IsCallerSystem: Token access check failed %x", v3);
          }
        }
        else
        {
          v7 = GetLastError();
          v3 = v7;
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
          _DbgPrintMessage(8, "IsCallerSystem: Could not convert security descriptor string %x", v3);
        }
      }
    }
    else
    {
      IsTokenSid = CUtils::IsTokenSid(TokenHandle, v4);
      v3 = IsTokenSid;
      if ( IsTokenSid < 0 )
        _DbgPrintMessage(8, "IsTokenSid( System ) failed: 0x%x in %s", IsTokenSid, "CUtils::IsCallerSystem");
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    _DbgPrintMessage(8, "IsCallerSystem: Could not open thread token %x", v3);
  }
LABEL_38:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl'::`2'::impl) )
  {
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    if ( v0 )
      LocalFree(v0);
  }
  return v3;
}

```

## disassembly

```asm
0x1800163b4  push    rbp
0x1800163b6  push    rbx
0x1800163b7  push    rsi
0x1800163b8  push    rdi
0x1800163b9  push    r15
0x1800163bb  lea     rbp, [rsp-37h]
0x1800163c0  sub     rsp, 90h
0x1800163c7  mov     rax, cs:__security_cookie
0x1800163ce  xor     rax, rsp
0x1800163d1  mov     [rbp+57h+var_28], rax
0x1800163d5  xor     esi, esi
0x1800163d7  mov     [rbp+57h+TokenHandle], 0
0x1800163df  mov     [rbp+57h+var_70], esi
0x1800163e2  mov     [rbp+57h+var_64], esi
0x1800163e5  mov     [rbp+57h+var_6C], 0
0x1800163ec  mov     [rbp+57h+SecurityDescriptor], 0
0x1800163f4  mov     [rbp+57h+AccessMask], 40000000h
0x1800163fb  call    cs:__imp_GetCurrentThread
0x180016402  nop     dword ptr [rax+rax+00h]
0x180016407  lea     r15d, [rsi+8]
0x18001640b  xor     r8d, r8d; OpenAsSelf
0x18001640e  mov     rcx, rax; ThreadHandle
0x180016411  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180016415  mov     edx, r15d; DesiredAccess
0x180016418  call    cs:__imp_OpenThreadToken
0x18001641f  nop     dword ptr [rax+rax+00h]
0x180016424  mov     [rbp+57h+var_6C], eax
0x180016427  test    eax, eax
0x180016429  jnz     short loc_180016452
0x18001642b  call    cs:__imp_GetLastError
0x180016432  nop     dword ptr [rax+rax+00h]
0x180016437  mov     ebx, eax
0x180016439  test    eax, eax
0x18001643b  jle     short loc_180016446
0x18001643d  movzx   ebx, ax
0x180016440  or      ebx, 80070000h
0x180016446  lea     rdx, aIscallersystem_1; "IsCallerSystem: Could not open thread t"...
0x18001644d  jmp     loc_1800166C4
0x180016452  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck> `wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl(void)'::`2'::impl
0x180016459  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(void)
0x18001645e  test    al, al
0x180016460  jnz     short loc_180016493
0x180016462  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180016466  call    ?IsTokenSid@CUtils@@CAJPEAX0@Z; CUtils::IsTokenSid(void *,void *)
0x18001646b  mov     ebx, eax
0x18001646d  test    eax, eax
0x18001646f  jns     loc_1800166CF
0x180016475  lea     r9, aCutilsIscaller; "CUtils::IsCallerSystem"
0x18001647c  mov     r8d, eax
0x18001647f  lea     rdx, aIstokensidSyst; "IsTokenSid( System ) failed: 0x%x in %s"
0x180016486  mov     ecx, r15d; int
0x180016489  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001648e  jmp     loc_1800166CF
0x180016493  xor     ecx, ecx; dwErrCode
0x180016495  call    cs:__imp_SetLastError
0x18001649c  nop     dword ptr [rax+rax+00h]
0x1800164a1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800164a5  call    cs:__imp_IsTokenRestricted
0x1800164ac  nop     dword ptr [rax+rax+00h]
0x1800164b1  test    eax, eax
0x1800164b3  jnz     loc_1800166B8
0x1800164b9  call    cs:__imp_GetLastError
0x1800164c0  nop     dword ptr [rax+rax+00h]
0x1800164c5  mov     ebx, eax
0x1800164c7  mov     edi, 80070000h
0x1800164cc  test    eax, eax
0x1800164ce  jle     short loc_1800164D5
0x1800164d0  movzx   ebx, ax
0x1800164d3  or      ebx, edi
0x1800164d5  test    ebx, ebx
0x1800164d7  jz      short loc_1800164E5
0x1800164d9  lea     rdx, aIscallersystem_6; "IsCallerSystem: IsTokenRestricted faile"...
0x1800164e0  jmp     loc_1800166C4
0x1800164e5  xor     r9d, r9d; SecurityDescriptorSize
0x1800164e8  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800164ec  lea     rcx, StringSecurityDescriptor; "O:SYG:BAD:(A;;0x1;;;SY)"
0x1800164f3  lea     edx, [r9+1]; StringSDRevision
0x1800164f7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800164fe  nop     dword ptr [rax+rax+00h]
0x180016503  test    eax, eax
0x180016505  jnz     short loc_18001652A
0x180016507  call    cs:__imp_GetLastError
0x18001650e  nop     dword ptr [rax+rax+00h]
0x180016513  mov     ebx, eax
0x180016515  test    eax, eax
0x180016517  jle     short loc_18001651E
0x180016519  movzx   ebx, ax
0x18001651c  or      ebx, edi
0x18001651e  lea     rdx, aIscallersystem_3; "IsCallerSystem: Could not convert secur"...
0x180016525  jmp     loc_1800166C4
0x18001652a  movups  xmm0, cs:xmmword_1800A8408
0x180016531  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x180016535  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180016539  movdqu  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18001653e  call    cs:__imp_MapGenericMask
0x180016545  nop     dword ptr [rax+rax+00h]
0x18001654a  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18001654e  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180016552  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x180016556  xor     eax, eax
0x180016558  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18001655c  xorps   xmm0, xmm0
0x18001655f  mov     [rbp+57h+var_40.Privilege.Attributes], eax
0x180016562  lea     rax, [rbp+57h+var_6C]
0x180016566  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18001656b  lea     rax, [rbp+57h+var_64]
0x18001656f  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180016574  lea     rax, [rbp+57h+var_70]
0x180016578  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001657d  lea     rax, [rbp+57h+var_40]
0x180016581  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x180016586  movups  xmmword ptr [rbp+57h+var_40.PrivilegeCount], xmm0
0x18001658a  mov     [rbp+57h+var_70], 14h
0x180016591  call    cs:__imp_AccessCheck
0x180016598  nop     dword ptr [rax+rax+00h]
0x18001659d  test    eax, eax
0x18001659f  jnz     loc_180016672
0x1800165a5  call    cs:__imp_GetLastError
0x1800165ac  nop     dword ptr [rax+rax+00h]
0x1800165b1  mov     ebx, eax
0x1800165b3  test    eax, eax
0x1800165b5  jle     short loc_1800165BC
0x1800165b7  movzx   ebx, ax
0x1800165ba  or      ebx, edi
0x1800165bc  cmp     ebx, 8007007Ah
0x1800165c2  jz      short loc_1800165D0
0x1800165c4  lea     rdx, aIscallersystem_2; "IsCallerSystem: Token access check prob"...
0x1800165cb  jmp     loc_1800166C4
0x1800165d0  mov     eax, [rbp+57h+var_70]
0x1800165d3  test    eax, eax
0x1800165d5  jnz     short loc_1800165E8
0x1800165d7  mov     ebx, 8000FFFFh
0x1800165dc  lea     rdx, aIscallersystem_8; "IsCallerSystem: AccessCheck probe retur"...
0x1800165e3  jmp     loc_1800166C4
0x1800165e8  mov     rdx, rax; uBytes
0x1800165eb  xor     ecx, ecx; uFlags
0x1800165ed  call    cs:__imp_LocalAlloc
0x1800165f4  nop     dword ptr [rax+rax+00h]
0x1800165f9  mov     rsi, rax
0x1800165fc  test    rax, rax
0x1800165ff  jnz     short loc_180016612
0x180016601  mov     ebx, 8007000Eh
0x180016606  lea     rdx, aIscallersystem_7; "IsCallerSystem: Failed to allocate priv"...
0x18001660d  jmp     loc_1800166C4
0x180016612  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x180016616  lea     rax, [rbp+57h+var_6C]
0x18001661a  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18001661e  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180016622  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180016626  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18001662b  lea     rax, [rbp+57h+var_64]
0x18001662f  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180016634  lea     rax, [rbp+57h+var_70]
0x180016638  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001663d  mov     [rsp+0B0h+PrivilegeSet], rsi; PrivilegeSet
0x180016642  call    cs:__imp_AccessCheck
0x180016649  nop     dword ptr [rax+rax+00h]
0x18001664e  test    eax, eax
0x180016650  jnz     short loc_180016672
0x180016652  call    cs:__imp_GetLastError
0x180016659  nop     dword ptr [rax+rax+00h]
0x18001665e  mov     ebx, eax
0x180016660  test    eax, eax
0x180016662  jle     short loc_180016669
0x180016664  movzx   ebx, ax
0x180016667  or      ebx, edi
0x180016669  lea     rdx, aIscallersystem_5; "IsCallerSystem: Token access check fail"...
0x180016670  jmp     short loc_1800166C4
0x180016672  cmp     [rbp+57h+var_6C], 0
0x180016676  jnz     short loc_180016698
0x180016678  call    cs:__imp_GetLastError
0x18001667f  nop     dword ptr [rax+rax+00h]
0x180016684  mov     ebx, eax
0x180016686  test    eax, eax
0x180016688  jle     short loc_18001668F
0x18001668a  movzx   ebx, ax
0x18001668d  or      ebx, edi
0x18001668f  lea     rdx, aIscallersystem_0; "IsCallerSystem: Token access denied %x"
0x180016696  jmp     short loc_1800166C4
0x180016698  test    byte ptr [rbp+57h+var_64], 1
0x18001669c  jnz     short loc_1800166B4
0x18001669e  lea     rdx, aIscallersystem_4; "IsCallerSystem: Token missing required "...
0x1800166a5  mov     ecx, r15d; int
0x1800166a8  mov     ebx, 1
0x1800166ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800166b2  jmp     short loc_1800166CF
0x1800166b4  xor     ebx, ebx
0x1800166b6  jmp     short loc_1800166CF
0x1800166b8  mov     ebx, 80070005h
0x1800166bd  lea     rdx, aIscallersystem; "IsCallerSystem: Token is restricted %x"
0x1800166c4  mov     r8d, ebx
0x1800166c7  mov     ecx, r15d; int
0x1800166ca  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800166cf  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800166d3  test    rcx, rcx
0x1800166d6  jz      short loc_1800166E4
0x1800166d8  call    cs:__imp_CloseHandle
0x1800166df  nop     dword ptr [rax+rax+00h]
0x1800166e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck> `wil::Feature<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::GetImpl(void)'::`2'::impl
0x1800166eb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IsCallerSystemAccessCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsCallerSystemAccessCheck>::__private_IsEnabled(void)
0x1800166f0  test    al, al
0x1800166f2  jz      short loc_18001671D
0x1800166f4  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800166f8  test    rcx, rcx
0x1800166fb  jz      short loc_180016709
0x1800166fd  call    cs:__imp_LocalFree
0x180016704  nop     dword ptr [rax+rax+00h]
0x180016709  test    rsi, rsi
0x18001670c  jz      short loc_18001671D
0x18001670e  mov     rcx, rsi; hMem
0x180016711  call    cs:__imp_LocalFree
0x180016718  nop     dword ptr [rax+rax+00h]
0x18001671d  mov     eax, ebx
0x18001671f  mov     rcx, [rbp+57h+var_28]
0x180016723  xor     rcx, rsp; StackCookie
0x180016726  call    __security_check_cookie
0x18001672b  add     rsp, 90h
0x180016732  pop     r15
0x180016734  pop     rdi
0x180016735  pop     rsi
0x180016736  pop     rbx
0x180016737  pop     rbp
0x180016738  retn
```
