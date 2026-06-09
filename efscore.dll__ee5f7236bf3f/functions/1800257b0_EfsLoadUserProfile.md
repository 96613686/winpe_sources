# EfsLoadUserProfile

- ea: `0x1800257b0`
- end: `0x180025cc7`
- name: `EfsLoadUserProfile`
- size: `1303`
- prototype: `__int64 __fastcall(struct _EFS_USER_INFO *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010860`
- `0x18001581c`
- `0x18001f0fc`
- `0x1800392a0`

## callees

- `0x1800248cc`
- `0x180024ab4`
- `0x180024b40`
- `0x180024bc4`
- `0x1800257b0`
- `0x180034e70`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002598a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025ca6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002598a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025c63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259b9`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180025c18`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180025c18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025a27`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025a27`
- `USERENV!UnloadUserProfile` at `0x180025c26`
- `USERENV!UnloadUserProfile` at `0x180025c26`
- `USERENV!LoadUserProfileW` at `0x180025b59`
- `USERENV!LoadUserProfileW` at `0x180025b59`
- `netutils!NetApiBufferFree` at `0x180025c73`
- `netutils!NetApiBufferFree` at `0x180025c83`
- `netutils!NetApiBufferFree` at `0x180025c73`
- `netutils!NetApiBufferFree` at `0x180025c83`
- `ntdll!NtClose` at `0x180025c96`
- `ntdll!NtClose` at `0x180025c96`
- `ntdll!NtSetInformationThread` at `0x180025be1`
- `ntdll!NtSetInformationThread` at `0x180025be1`
- `ntdll!NtOpenThreadToken` at `0x180025952`
- `ntdll!NtOpenThreadToken` at `0x180025952`
- `ntdll!RtlNtStatusToDosError` at `0x180025982`
- `ntdll!RtlNtStatusToDosError` at `0x180025c39`
- `ntdll!RtlNtStatusToDosError` at `0x180025982`
- `ntdll!RtlNtStatusToDosError` at `0x180025c39`
- `logoncli!DsGetDcNameW` at `0x180025a8a`
- `logoncli!DsGetDcNameW` at `0x180025a8a`
- `samcli!NetUserGetInfo` at `0x180025b00`
- `samcli!NetUserGetInfo` at `0x180025b00`

## pseudocode

```c
__int64 __fastcall EfsLoadUserProfile(struct _EFS_USER_INFO *a1, char a2)
{
  DWORD v4; // esi
  const WCHAR *v5; // r12
  char v6; // bl
  int AllUsersProfiles; // r14d
  int v8; // eax
  __int64 v9; // rcx
  WCHAR *v10; // rbx
  HANDLE *v11; // r13
  HANDLE *v12; // r12
  DWORD LastError; // eax
  char v14; // r14
  int v15; // eax
  char v16; // r14
  NTSTATUS v17; // eax
  NTSTATUS v18; // esi
  DWORD v19; // eax
  WCHAR *v20; // r14
  DWORD DcNameW; // eax
  const WCHAR *DomainControllerName; // rax
  DWORD Info; // eax
  NTSTATUS v24; // eax
  NTSTATUS v25; // r14d
  void *v26; // rcx
  const WCHAR *v28; // [rsp+30h] [rbp-B8h]
  int v29; // [rsp+38h] [rbp-B0h]
  const WCHAR *username; // [rsp+40h] [rbp-A8h]
  LPBYTE bufptr; // [rsp+50h] [rbp-98h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+58h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-88h] BYREF
  WCHAR *v34; // [rsp+68h] [rbp-80h]
  LPCWSTR DomainName; // [rsp+70h] [rbp-78h]
  char *v36; // [rsp+78h] [rbp-70h]
  char *v37; // [rsp+80h] [rbp-68h]
  _PROFILEINFOW ProfileInfo; // [rsp+88h] [rbp-60h] BYREF
  char v39; // [rsp+100h] [rbp+18h]
  const WCHAR *lpSubKey; // [rsp+108h] [rbp+20h]

  v4 = 0;
  v5 = 0;
  v28 = 0;
  bufptr = 0;
  v39 = *((_BYTE *)a1 + 92);
  v6 = *((_BYTE *)a1 + 93);
  DomainName = (LPCWSTR)*((_QWORD *)a1 + 1);
  v34 = (WCHAR *)*((_QWORD *)a1 + 2);
  username = *(const WCHAR **)a1;
  lpSubKey = (const WCHAR *)*((_QWORD *)a1 + 3);
  DomainControllerInfo = 0;
  hKey = 0;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  AllUsersProfiles = EfspLoadAllUsersProfiles();
  v8 = EfspCacheUserProfiles();
  v29 = v8;
  if ( v6
    || *((_DWORD *)a1 + 22) == 2 && !AllUsersProfiles
    || !a2 && *((_QWORD *)a1 + 6) && !AllUsersProfiles
    || (v11 = (HANDLE *)((char *)a1 + 64), v36 = (char *)a1 + 64, *((_QWORD *)a1 + 8)) )
  {
    LODWORD(v10) = 1;
    goto LABEL_50;
  }
  v10 = 0;
  v12 = (HANDLE *)((char *)a1 + 56);
  v37 = (char *)a1 + 56;
  if ( *((_QWORD *)a1 + 7) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
    v8 = v29;
  }
  *v12 = 0;
  *((_QWORD *)a1 + 12) = 0;
  if ( !v8 )
    goto LABEL_21;
  if ( !(unsigned __int8)EfsEnsureUserHasCacheNode(a1) )
  {
    LastError = GetLastError();
    v4 = LastError;
    v14 = 33;
LABEL_14:
    v15 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 3, v14);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v15, 3, v14);
LABEL_15:
    v5 = 0;
    goto LABEL_50;
  }
  LastError = EfspLookupUserProfileInCache(a1);
  v4 = LastError;
  if ( LastError )
  {
    if ( LastError != 1168 )
    {
      v14 = 44;
      goto LABEL_14;
    }
LABEL_21:
    v16 = 1;
    v17 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xEu, 1u, (PHANDLE)a1 + 7);
    v18 = v17;
    if ( v17 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v17, 3, 71);
      v19 = RtlNtStatusToDosError(v18);
      SetLastError(v19);
      v4 = 0;
      goto LABEL_15;
    }
    v4 = 0;
    if ( !RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x2000000u, &hKey) )
      goto LABEL_26;
    if ( v34 )
    {
      v10 = v34;
      goto LABEL_26;
    }
    if ( v39 )
    {
      DcNameW = DsGetDcNameW(0, DomainName, 0, 0, 0, &DomainControllerInfo);
      v4 = DcNameW;
      if ( DcNameW )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, DcNameW, 3, 140);
        v16 = 0;
        DomainControllerName = 0;
        goto LABEL_35;
      }
      DomainControllerName = DomainControllerInfo->DomainControllerName;
    }
    else
    {
      DomainControllerName = 0;
    }
    v28 = DomainControllerName;
LABEL_35:
    if ( v16 )
    {
      v20 = (WCHAR *)username;
      Info = NetUserGetInfo(DomainControllerName, username, 3u, &bufptr);
      v4 = Info;
      if ( Info )
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, Info, 3, 164);
      else
        v10 = (WCHAR *)*((_QWORD *)bufptr + 20);
LABEL_27:
      memset(&ProfileInfo.lpDefaultPath, 0, 32);
      ProfileInfo.dwSize = 56;
      ProfileInfo.lpUserName = v20;
      ProfileInfo.lpProfilePath = v10;
      ProfileInfo.dwFlags = 4;
      if ( RevertToSelf() )
      {
        LODWORD(v10) = LoadUserProfileW(*v12, &ProfileInfo);
        if ( (_DWORD)v10 )
        {
          *v11 = ProfileInfo.hProfile;
        }
        else
        {
          v4 = GetLastError();
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v4, 3, 212);
        }
        v24 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, (char *)a1 + 56, 8u);
        v25 = v24;
        if ( v24 < 0 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v24, 3, 229);
          if ( (_DWORD)v10 )
          {
            CertFreeCertificateChainEngine(0);
            UnloadUserProfile(*v12, *v11);
            *v11 = 0;
          }
          LODWORD(v10) = 0;
          v4 = RtlNtStatusToDosError(v25);
        }
        if ( (_DWORD)v10 && v29 )
          EfspTryAddUserProfileToCache(a1);
      }
      else
      {
        LODWORD(v10) = 0;
        v4 = GetLastError();
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v4, 3, 196);
      }
      goto LABEL_49;
    }
LABEL_26:
    v20 = (WCHAR *)username;
    goto LABEL_27;
  }
  LODWORD(v10) = 1;
LABEL_49:
  v5 = v28;
LABEL_50:
  if ( hKey )
    RegCloseKey(hKey);
  if ( bufptr )
    NetApiBufferFree(bufptr);
  if ( v5 )
    NetApiBufferFree(DomainControllerInfo);
  if ( !(_DWORD)v10 )
  {
    v26 = (void *)*((_QWORD *)a1 + 7);
    if ( v26 )
    {
      NtClose(v26);
      *((_QWORD *)a1 + 7) = 0;
    }
  }
  SetLastError(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800257b0  mov     r11, rsp
0x1800257b3  mov     [r11+10h], rbx
0x1800257b7  mov     [r11+8], rcx
0x1800257bb  push    rsi
0x1800257bc  push    r12
0x1800257be  push    r13
0x1800257c0  push    r14
0x1800257c2  push    r15
0x1800257c4  sub     rsp, 0C0h
0x1800257cb  mov     r13b, dl
0x1800257ce  mov     r15, rcx
0x1800257d1  xor     esi, esi
0x1800257d3  xor     r12d, r12d
0x1800257d6  mov     [rsp+0E8h+var_B8], r12
0x1800257db  mov     [rsp+0E8h+bufptr], rsi
0x1800257e0  mov     al, [rcx+5Ch]
0x1800257e3  mov     [rsp+0E8h+arg_10], al
0x1800257ea  mov     bl, [rcx+5Dh]
0x1800257ed  mov     rax, [rcx+8]
0x1800257f1  mov     [rsp+0E8h+DomainName], rax
0x1800257f6  mov     rax, [rcx+10h]
0x1800257fa  mov     [rsp+0E8h+var_80], rax
0x1800257ff  mov     rax, [rcx]
0x180025802  mov     [rsp+0E8h+username], rax
0x180025807  mov     rax, [rcx+18h]
0x18002580b  mov     [rsp+0E8h+lpSubKey], rax
0x180025813  mov     [rsp+0E8h+var_90], rsi
0x180025818  mov     [rsp+0E8h+hKey], rsi
0x18002581d  xorps   xmm0, xmm0
0x180025820  xor     eax, eax
0x180025822  movups  xmmword ptr [r11-60h], xmm0
0x180025827  movups  xmmword ptr [r11-50h], xmm0
0x18002582c  movups  xmmword ptr [r11-40h], xmm0
0x180025831  mov     [r11-30h], rax
0x180025835  call    ?EfspLoadAllUsersProfiles@@YAHXZ; EfspLoadAllUsersProfiles(void)
0x18002583a  mov     r14d, eax
0x18002583d  call    ?EfspCacheUserProfiles@@YAHXZ; EfspCacheUserProfiles(void)
0x180025842  mov     [rsp+0E8h+var_B0], eax
0x180025846  test    bl, bl
0x180025848  jz      short loc_180025854
0x18002584a  mov     ebx, 1
0x18002584f  jmp     loc_180025C59
0x180025854  cmp     dword ptr [r15+58h], 2
0x180025859  jnz     short loc_180025860
0x18002585b  test    r14d, r14d
0x18002585e  jz      short loc_18002584A
0x180025860  test    r13b, r13b
0x180025863  jnz     short loc_180025870
0x180025865  cmp     [r15+30h], rsi
0x180025869  jz      short loc_180025870
0x18002586b  test    r14d, r14d
0x18002586e  jz      short loc_18002584A
0x180025870  lea     r13, [r15+40h]
0x180025874  mov     [rsp+0E8h+var_70], r13
0x180025879  cmp     [r13+0], rsi
0x18002587d  jnz     short loc_18002584A
0x18002587f  xor     ebx, ebx
0x180025881  lea     r12, [r15+38h]
0x180025885  mov     [rsp+0E8h+var_68], r12
0x18002588d  cmp     [r12], rbx
0x180025891  jz      short loc_18002589C
0x180025893  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pEfsUserInfo->hThreadToken == NULL")
0x180025898  mov     eax, [rsp+0E8h+var_B0]
0x18002589c  mov     [r12], rbx
0x1800258a0  mov     [r15+60h], rbx
0x1800258a4  test    eax, eax
0x1800258a6  jz      loc_18002593B
0x1800258ac  mov     rcx, r15
0x1800258af  call    EfsEnsureUserHasCacheNode
0x1800258b4  test    al, al
0x1800258b6  jnz     short loc_180025910
0x1800258b8  call    cs:__imp_GetLastError
0x1800258be  mov     esi, eax
0x1800258c0  mov     r14d, 621h
0x1800258c6  mov     dword ptr [rsp+0E8h+phkResult], r14d
0x1800258cb  mov     r9d, 3
0x1800258d1  mov     r8d, eax
0x1800258d4  lea     rdx, EFS_API_ERROR
0x1800258db  mov     rcx, cs:g_hPublisher
0x1800258e2  call    fnEfsLogTrace1
0x1800258e7  mov     dword ptr [rsp+0E8h+phkResult], r14d
0x1800258ec  mov     r9d, 3
0x1800258f2  mov     r8d, eax
0x1800258f5  lea     rdx, EFS_TRACE_ERROR
0x1800258fc  mov     rcx, cs:g_hPublisher
0x180025903  call    fnEfsLogTrace1
0x180025908  mov     r12, rbx
0x18002590b  jmp     loc_180025C59
0x180025910  mov     rcx, r15; struct _EFS_USER_INFO *
0x180025913  call    ?EfspLookupUserProfileInCache@@YAKPEAU_EFS_USER_INFO@@@Z; EfspLookupUserProfileInCache(_EFS_USER_INFO *)
0x180025918  mov     esi, eax
0x18002591a  test    eax, eax
0x18002591c  jz      short loc_180025931
0x18002591e  cmp     eax, 490h
0x180025923  jz      short loc_18002592D
0x180025925  mov     r14d, 62Ch
0x18002592b  jmp     short loc_1800258C6
0x18002592d  test    eax, eax
0x18002592f  jnz     short loc_18002593B
0x180025931  mov     ebx, 1
0x180025936  jmp     loc_180025C54
0x18002593b  mov     r9, r12; TokenHandle
0x18002593e  mov     r14d, 1
0x180025944  mov     r8b, r14b; OpenAsSelf
0x180025947  lea     edx, [r14+0Dh]; DesiredAccess
0x18002594b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180025952  call    cs:__imp_NtOpenThreadToken
0x180025958  mov     esi, eax
0x18002595a  test    eax, eax
0x18002595c  jns     short loc_180025997
0x18002595e  mov     dword ptr [rsp+0E8h+phkResult], 647h
0x180025966  lea     r9d, [r14+2]
0x18002596a  mov     r8d, eax
0x18002596d  lea     rdx, EFS_API_ERROR
0x180025974  mov     rcx, cs:g_hPublisher
0x18002597b  call    fnEfsLogTrace1
0x180025980  mov     ecx, esi; Status
0x180025982  call    cs:__imp_RtlNtStatusToDosError
0x180025988  mov     ecx, eax; dwErrCode
0x18002598a  call    cs:__imp_SetLastError
0x180025990  xor     esi, esi
0x180025992  jmp     loc_180025908
0x180025997  lea     rax, [rsp+0E8h+hKey]
0x18002599c  mov     [rsp+0E8h+phkResult], rax; phkResult
0x1800259a1  mov     r9d, 2000000h; samDesired
0x1800259a7  xor     r8d, r8d; ulOptions
0x1800259aa  mov     rdx, [rsp+0E8h+lpSubKey]; lpSubKey
0x1800259b2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800259b9  call    cs:__imp_RegOpenKeyExW
0x1800259bf  xor     esi, esi
0x1800259c1  mov     dword ptr [rsp+0E8h+lpSubKey], esi
0x1800259c8  test    eax, eax
0x1800259ca  jz      short loc_1800259E4
0x1800259cc  mov     rax, [rsp+0E8h+var_80]
0x1800259d1  test    rax, rax
0x1800259d4  jz      loc_180025A66
0x1800259da  mov     rbx, rax
0x1800259dd  mov     dword ptr [rsp+0E8h+lpSubKey], esi
0x1800259e4  mov     r14, [rsp+0E8h+username]
0x1800259e9  xorps   xmm0, xmm0
0x1800259ec  movdqu  xmmword ptr [rsp+0E8h+ProfileInfo.lpDefaultPath], xmm0
0x1800259f5  xorps   xmm1, xmm1
0x1800259f8  movdqu  xmmword ptr [rsp+0E8h+ProfileInfo.lpPolicyPath], xmm1
0x180025a01  mov     [rsp+0E8h+ProfileInfo.dwSize], 38h ; '8'
0x180025a0c  mov     [rsp+0E8h+ProfileInfo.lpUserName], r14
0x180025a14  mov     [rsp+0E8h+ProfileInfo.lpProfilePath], rbx
0x180025a1c  mov     [rsp+0E8h+ProfileInfo.dwFlags], 4
0x180025a27  call    cs:__imp_RevertToSelf
0x180025a2d  test    eax, eax
0x180025a2f  jnz     loc_180025B4D
0x180025a35  xor     ebx, ebx
0x180025a37  call    cs:__imp_GetLastError
0x180025a3d  mov     esi, eax
0x180025a3f  mov     dword ptr [rsp+0E8h+phkResult], 6C4h
0x180025a47  lea     r9d, [rbx+3]
0x180025a4b  mov     r8d, eax
0x180025a4e  lea     rdx, EFS_TRACE_ERROR
0x180025a55  mov     rcx, cs:g_hPublisher
0x180025a5c  call    fnEfsLogTrace1
0x180025a61  jmp     loc_180025C54
0x180025a66  cmp     [rsp+0E8h+arg_10], bl
0x180025a6d  jz      short loc_180025AD3
0x180025a6f  lea     rax, [rsp+0E8h+var_90]
0x180025a74  mov     [rsp+0E8h+DomainControllerInfo], rax; DomainControllerInfo
0x180025a79  mov     dword ptr [rsp+0E8h+phkResult], ebx; Flags
0x180025a7d  xor     r9d, r9d; SiteName
0x180025a80  xor     r8d, r8d; DomainGuid
0x180025a83  mov     rdx, [rsp+0E8h+DomainName]; DomainName
0x180025a88  xor     ecx, ecx; ComputerName
0x180025a8a  call    cs:__imp_DsGetDcNameW
0x180025a90  mov     esi, eax
0x180025a92  mov     dword ptr [rsp+0E8h+lpSubKey], eax
0x180025a99  test    eax, eax
0x180025a9b  jnz     short loc_180025AA7
0x180025a9d  mov     rax, [rsp+0E8h+var_90]
0x180025aa2  mov     rax, [rax]
0x180025aa5  jmp     short loc_180025ADC
0x180025aa7  mov     dword ptr [rsp+0E8h+phkResult], 68Ch
0x180025aaf  mov     r9d, 3
0x180025ab5  mov     r8d, eax
0x180025ab8  lea     rdx, EFS_API_ERROR
0x180025abf  mov     rcx, cs:g_hPublisher
0x180025ac6  call    fnEfsLogTrace1
0x180025acb  xor     r14b, r14b
0x180025ace  mov     rax, rbx
0x180025ad1  jmp     short loc_180025AE1
0x180025ad3  xor     eax, eax
0x180025ad5  mov     dword ptr [rsp+0E8h+lpSubKey], esi
0x180025adc  mov     [rsp+0E8h+var_B8], rax
0x180025ae1  test    r14b, r14b
0x180025ae4  jz      loc_1800259E4
0x180025aea  lea     r9, [rsp+0E8h+bufptr]; bufptr
0x180025aef  mov     r8d, 3; level
0x180025af5  mov     r14, [rsp+0E8h+username]
0x180025afa  mov     rdx, r14; username
0x180025afd  mov     rcx, rax; servername
0x180025b00  call    cs:__imp_NetUserGetInfo
0x180025b06  mov     esi, eax
0x180025b08  mov     dword ptr [rsp+0E8h+lpSubKey], eax
0x180025b0f  test    eax, eax
0x180025b11  jnz     short loc_180025B24
0x180025b13  mov     rax, [rsp+0E8h+bufptr]
0x180025b18  mov     rbx, [rax+0A0h]
0x180025b1f  jmp     loc_1800259E9
0x180025b24  mov     dword ptr [rsp+0E8h+phkResult], 6A4h
0x180025b2c  mov     r9d, 3
0x180025b32  mov     r8d, eax
0x180025b35  lea     rdx, EFS_API_ERROR
0x180025b3c  mov     rcx, cs:g_hPublisher
0x180025b43  call    fnEfsLogTrace1
0x180025b48  jmp     loc_1800259E9
0x180025b4d  lea     rdx, [rsp+0E8h+ProfileInfo]; lpProfileInfo
0x180025b55  mov     rcx, [r12]; hToken
0x180025b59  call    cs:__imp_LoadUserProfileW
0x180025b5f  mov     ebx, eax
0x180025b61  mov     [rsp+0E8h+var_A0], eax
0x180025b65  jmp     short loc_180025B91
0x180025b67  xor     ebx, ebx
0x180025b69  mov     [rsp+0E8h+var_A0], ebx
0x180025b6d  mov     ecx, eax; dwErrCode
0x180025b6f  call    cs:__imp_SetLastError
0x180025b75  mov     r15, [rsp+0E8h+arg_0]
0x180025b7d  mov     esi, dword ptr [rsp+0E8h+lpSubKey]
0x180025b84  mov     r13, [rsp+0E8h+var_70]
0x180025b89  mov     r12, [rsp+0E8h+var_68]
0x180025b91  test    ebx, ebx
0x180025b93  jnz     short loc_180025BC1
0x180025b95  call    cs:__imp_GetLastError
0x180025b9b  mov     esi, eax
0x180025b9d  mov     dword ptr [rsp+0E8h+phkResult], 6D4h
0x180025ba5  lea     r9d, [rbx+3]
0x180025ba9  mov     r8d, eax
0x180025bac  lea     rdx, EFS_API_ERROR
0x180025bb3  mov     rcx, cs:g_hPublisher
0x180025bba  call    fnEfsLogTrace1
0x180025bbf  jmp     short loc_180025BCD
0x180025bc1  mov     rax, [rsp+0E8h+ProfileInfo.hProfile]
0x180025bc9  mov     [r13+0], rax
0x180025bcd  mov     r9d, 8; ThreadInformationLength
0x180025bd3  mov     r8, r12; ThreadInformation
0x180025bd6  lea     edx, [r9-3]; ThreadInformationClass
0x180025bda  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180025be1  call    cs:__imp_NtSetInformationThread
0x180025be7  mov     r14d, eax
0x180025bea  test    eax, eax
0x180025bec  jns     short loc_180025C41
0x180025bee  mov     dword ptr [rsp+0E8h+phkResult], 6E5h
0x180025bf6  mov     r9d, 3
0x180025bfc  mov     r8d, eax
0x180025bff  lea     rdx, EFS_API_ERROR
0x180025c06  mov     rcx, cs:g_hPublisher
0x180025c0d  call    fnEfsLogTrace1
0x180025c12  test    ebx, ebx
0x180025c14  jz      short loc_180025C34
0x180025c16  xor     ecx, ecx; hChainEngine
0x180025c18  call    cs:__imp_CertFreeCertificateChainEngine
0x180025c1e  mov     rdx, [r13+0]; hProfile
0x180025c22  mov     rcx, [r12]; hToken
0x180025c26  call    cs:__imp_UnloadUserProfile
0x180025c2c  mov     qword ptr [r13+0], 0
0x180025c34  xor     ebx, ebx
0x180025c36  mov     ecx, r14d; Status
0x180025c39  call    cs:__imp_RtlNtStatusToDosError
0x180025c3f  mov     esi, eax
0x180025c41  test    ebx, ebx
0x180025c43  jz      short loc_180025C54
0x180025c45  cmp     [rsp+0E8h+var_B0], 0
0x180025c4a  jz      short loc_180025C54
0x180025c4c  mov     rcx, r15; struct _EFS_USER_INFO *
0x180025c4f  call    ?EfspTryAddUserProfileToCache@@YAKPEAU_EFS_USER_INFO@@@Z; EfspTryAddUserProfileToCache(_EFS_USER_INFO *)
0x180025c54  mov     r12, [rsp+0E8h+var_B8]
0x180025c59  mov     rcx, [rsp+0E8h+hKey]; hKey
0x180025c5e  test    rcx, rcx
0x180025c61  jz      short loc_180025C69
0x180025c63  call    cs:__imp_RegCloseKey
0x180025c69  mov     rcx, [rsp+0E8h+bufptr]; Buffer
0x180025c6e  test    rcx, rcx
0x180025c71  jz      short loc_180025C79
0x180025c73  call    cs:__imp_NetApiBufferFree
0x180025c79  test    r12, r12
0x180025c7c  jz      short loc_180025C89
0x180025c7e  mov     rcx, [rsp+0E8h+var_90]; Buffer
0x180025c83  call    cs:__imp_NetApiBufferFree
0x180025c89  test    ebx, ebx
0x180025c8b  jnz     short loc_180025CA4
0x180025c8d  mov     rcx, [r15+38h]; Handle
0x180025c91  test    rcx, rcx
0x180025c94  jz      short loc_180025CA4
0x180025c96  call    cs:__imp_NtClose
0x180025c9c  mov     qword ptr [r15+38h], 0
0x180025ca4  mov     ecx, esi; dwErrCode
0x180025ca6  call    cs:__imp_SetLastError
0x180025cac  mov     eax, ebx
0x180025cae  mov     rbx, [rsp+0E8h+arg_8]
0x180025cb6  add     rsp, 0C0h
0x180025cbd  pop     r15
0x180025cbf  pop     r14
0x180025cc1  pop     r13
0x180025cc3  pop     r12
0x180025cc5  pop     rsi
  ... truncated ...
```
