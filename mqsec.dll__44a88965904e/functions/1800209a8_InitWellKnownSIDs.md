# InitWellKnownSIDs

- ea: `0x1800209a8`
- end: `0x180020fd8`
- name: `InitWellKnownSIDs`
- size: `1584`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x1800207c4`

## callees

- `0x180004074`
- `0x1800041cc`
- `0x1800049ac`
- `0x1800139dc`
- `0x18001722c`
- `0x180017430`
- `0x18001f3e0`
- `0x180020680`
- `0x1800209a8`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!free` at `0x180020e15`
- `msvcrt!free` at `0x180020eb0`
- `msvcrt!free` at `0x180020f9a`
- `msvcrt!free` at `0x180020fa9`
- `msvcrt!free` at `0x180020e15`
- `msvcrt!free` at `0x180020eb0`
- `msvcrt!free` at `0x180020f9a`
- `msvcrt!free` at `0x180020fa9`
- `ADVAPI32!CopySid` at `0x180020e47`
- `ADVAPI32!CopySid` at `0x180020e47`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020a14`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020aad`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020b43`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020be1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020f38`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020a14`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020aad`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020b43`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020be1`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180020f38`
- `ADVAPI32!GetTokenInformation` at `0x180020cbb`
- `ADVAPI32!GetTokenInformation` at `0x180020dac`
- `ADVAPI32!GetTokenInformation` at `0x180020cbb`
- `ADVAPI32!GetTokenInformation` at `0x180020dac`
- `ADVAPI32!GetLengthSid` at `0x180020e27`
- `ADVAPI32!GetLengthSid` at `0x180020e27`
- `KERNEL32!GetLastError` at `0x180020a1e`
- `KERNEL32!GetLastError` at `0x180020a59`
- `KERNEL32!GetLastError` at `0x180020ab7`
- `KERNEL32!GetLastError` at `0x180020af2`
- `KERNEL32!GetLastError` at `0x180020b4d`
- `KERNEL32!GetLastError` at `0x180020b87`
- `KERNEL32!GetLastError` at `0x180020beb`
- `KERNEL32!GetLastError` at `0x180020c27`
- `KERNEL32!GetLastError` at `0x180020cc1`
- `KERNEL32!GetLastError` at `0x180020db6`
- `KERNEL32!GetLastError` at `0x180020df3`
- `KERNEL32!GetLastError` at `0x180020e51`
- `KERNEL32!GetLastError` at `0x180020e8e`
- `KERNEL32!GetLastError` at `0x180020f42`
- `KERNEL32!GetLastError` at `0x180020f78`
- `KERNEL32!GetLastError` at `0x180020a1e`
- `KERNEL32!GetLastError` at `0x180020a59`
- `KERNEL32!GetLastError` at `0x180020ab7`
- `KERNEL32!GetLastError` at `0x180020af2`
- `KERNEL32!GetLastError` at `0x180020b4d`
- `KERNEL32!GetLastError` at `0x180020b87`
- `KERNEL32!GetLastError` at `0x180020beb`
- `KERNEL32!GetLastError` at `0x180020c27`
- `KERNEL32!GetLastError` at `0x180020cc1`
- `KERNEL32!GetLastError` at `0x180020db6`
- `KERNEL32!GetLastError` at `0x180020df3`
- `KERNEL32!GetLastError` at `0x180020e51`
- `KERNEL32!GetLastError` at `0x180020e8e`
- `KERNEL32!GetLastError` at `0x180020f42`
- `KERNEL32!GetLastError` at `0x180020f78`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char InitWellKnownSIDs()
{
  char v0; // si
  DWORD LastError; // eax
  DWORD v2; // eax
  unsigned __int16 v3; // r8
  DWORD v4; // eax
  DWORD v5; // eax
  unsigned int v6; // r8d
  DWORD v7; // eax
  unsigned int AccessToken; // eax
  unsigned int v10; // ebx
  __int16 v11; // ax
  DWORD v12; // eax
  unsigned int v13; // eax
  PSID *v14; // rbx
  DWORD v15; // eax
  DWORD v16; // eax
  PSID v17; // rdi
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  __int16 v22; // [rsp+60h] [rbp-19h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-11h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-9h] BYREF
  PSID *v25; // [rsp+78h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v27; // [rsp+88h] [rbp+Fh] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v0 = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, &g_pAnonymSid) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 16, WPP_efe327766876393cacc144e0c735893e_Traceguids, LastError);
    v2 = GetLastError();
    if ( !v2 )
      return 0;
    v3 = 60;
    goto LABEL_25;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &g_pSystemSid) )
  {
    v4 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 17, WPP_efe327766876393cacc144e0c735893e_Traceguids, v4);
    v2 = GetLastError();
    if ( !v2 )
      return 0;
    v3 = 61;
    goto LABEL_25;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &g_pNetworkServiceSid) )
  {
    v5 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 18, WPP_efe327766876393cacc144e0c735893e_Traceguids, v5);
    v2 = GetLastError();
    if ( !v2 )
      return 0;
    v3 = 62;
    goto LABEL_25;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &g_pAdminSid) )
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 19, WPP_efe327766876393cacc144e0c735893e_Traceguids, v7);
    v2 = GetLastError();
    if ( !v2 )
      return 0;
    v3 = 63;
LABEL_25:
    LogMsgNTStatus(v2, (wchar_t *)L"acssctrl/acssinit", v3);
    return 0;
  }
  ReturnLength = 0;
  TokenHandle = 0;
  AccessToken = GetAccessToken(&TokenHandle, 0, v6, 0);
  v10 = AccessToken;
  if ( AccessToken )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 20, WPP_efe327766876393cacc144e0c735893e_Traceguids, AccessToken);
    v11 = 64;
LABEL_38:
    LODWORD(v25) = v10;
    v22 = v11;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v13 = mqwcslen(L"acssctrl/acssinit");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        2,
        2LL * (v13 + 1),
        L"acssctrl/acssinit",
        2,
        &v22,
        4,
        &v25,
        0,
        0);
    }
    goto LABEL_40;
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength);
  v12 = GetLastError();
  v10 = v12;
  if ( v12 != 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 21, WPP_efe327766876393cacc144e0c735893e_Traceguids, v12);
    if ( !v10 )
      goto LABEL_40;
    v11 = 65;
    goto LABEL_38;
  }
  v14 = (PSID *)MmAllocate(ReturnLength);
  v25 = v14;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v14, ReturnLength, &ReturnLength) )
  {
    v15 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 22, WPP_efe327766876393cacc144e0c735893e_Traceguids, v15);
    v16 = GetLastError();
    if ( v16 )
      LogMsgNTStatus(v16, (wchar_t *)L"acssctrl/acssinit", 0x42u);
LABEL_47:
    free(v14);
LABEL_40:
    CHandle::~CHandle((CHandle *)&TokenHandle);
    return 0;
  }
  v17 = *v14;
  ReturnLength = GetLengthSid(*v14);
  g_pProcessSid = MmAllocate(ReturnLength);
  if ( !CopySid(ReturnLength, g_pProcessSid, v17) )
  {
    v18 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 23, WPP_efe327766876393cacc144e0c735893e_Traceguids, v18);
    v19 = GetLastError();
    if ( v19 )
      LogMsgNTStatus(v19, (wchar_t *)L"acssctrl/acssinit", 0x43u);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
  *(_DWORD *)v27.Value = 0;
  *(_WORD *)&v27.Value[4] = 256;
  if ( AllocateAndInitializeSid(&v27, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &g_pWorldSid) )
  {
    free(v14);
  }
  else
  {
    v20 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 26, WPP_efe327766876393cacc144e0c735893e_Traceguids, v20);
    v21 = GetLastError();
    if ( v21 )
      LogMsgNTStatus(v21, (wchar_t *)L"acssctrl/acssinit", 0x45u);
    free(v14);
    v0 = 0;
  }
  CHandle::~CHandle((CHandle *)&TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1800209a8  push    rbp
0x1800209aa  push    rbx
0x1800209ab  push    rsi
0x1800209ac  push    rdi
0x1800209ad  push    r14
0x1800209af  push    r15
0x1800209b1  lea     rbp, [rsp-2Fh]
0x1800209b6  sub     rsp, 0A8h
0x1800209bd  mov     rax, cs:__security_cookie
0x1800209c4  xor     rax, rsp
0x1800209c7  mov     [rbp+57h+var_40], rax
0x1800209cb  xor     r14d, r14d
0x1800209ce  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800209d2  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800209d8  lea     rax, ?g_pAnonymSid@@3PEAXEA; void * g_pAnonymSid
0x1800209df  mov     [rsp+0D0h+pSid], rax; pSid
0x1800209e4  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x1800209e9  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x1800209ee  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x1800209f3  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x1800209f8  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x1800209fd  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x180020a02  xor     r9d, r9d; nSubAuthority1
0x180020a05  lea     esi, [r14+1]
0x180020a09  lea     r8d, [r14+7]; nSubAuthority0
0x180020a0d  mov     dl, sil; nSubAuthorityCount
0x180020a10  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180020a14  call    cs:__imp_AllocateAndInitializeSid
0x180020a1a  test    eax, eax
0x180020a1c  jnz     short loc_180020A72
0x180020a1e  call    cs:__imp_GetLastError
0x180020a24  lea     rdi, WPP_GLOBAL_Control
0x180020a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a32  cmp     rcx, rdi
0x180020a35  jz      short loc_180020A59
0x180020a37  test    [rcx+10Ch], sil
0x180020a3e  jz      short loc_180020A59
0x180020a40  lea     edx, [rsi+0Fh]
0x180020a43  mov     r9d, eax
0x180020a46  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020a4d  mov     rcx, [rcx+100h]
0x180020a54  call    WPP_SF_d
0x180020a59  call    cs:__imp_GetLastError
0x180020a5f  test    eax, eax
0x180020a61  jz      loc_180020C45
0x180020a67  mov     r8d, 3Ch ; '<'
0x180020a6d  jmp     loc_180020C37
0x180020a72  lea     rax, ?g_pSystemSid@@3PEAXEA; void * g_pSystemSid
0x180020a79  mov     [rsp+0D0h+pSid], rax; pSid
0x180020a7e  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x180020a83  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x180020a88  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x180020a8d  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x180020a92  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x180020a97  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x180020a9c  xor     r9d, r9d; nSubAuthority1
0x180020a9f  lea     ebx, [r9+12h]
0x180020aa3  mov     r8d, ebx; nSubAuthority0
0x180020aa6  mov     dl, sil; nSubAuthorityCount
0x180020aa9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180020aad  call    cs:__imp_AllocateAndInitializeSid
0x180020ab3  test    eax, eax
0x180020ab5  jnz     short loc_180020B0B
0x180020ab7  call    cs:__imp_GetLastError
0x180020abd  lea     rdi, WPP_GLOBAL_Control
0x180020ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180020acb  cmp     rcx, rdi
0x180020ace  jz      short loc_180020AF2
0x180020ad0  test    [rcx+10Ch], sil
0x180020ad7  jz      short loc_180020AF2
0x180020ad9  lea     edx, [rbx-1]
0x180020adc  mov     r9d, eax
0x180020adf  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020ae6  mov     rcx, [rcx+100h]
0x180020aed  call    WPP_SF_d
0x180020af2  call    cs:__imp_GetLastError
0x180020af8  test    eax, eax
0x180020afa  jz      loc_180020C45
0x180020b00  mov     r8d, 3Dh ; '='
0x180020b06  jmp     loc_180020C37
0x180020b0b  lea     rax, ?g_pNetworkServiceSid@@3PEAXEA; void * g_pNetworkServiceSid
0x180020b12  mov     [rsp+0D0h+pSid], rax; pSid
0x180020b17  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x180020b1c  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x180020b21  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x180020b26  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x180020b2b  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x180020b30  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x180020b35  xor     r9d, r9d; nSubAuthority1
0x180020b38  lea     r8d, [r9+14h]; nSubAuthority0
0x180020b3c  mov     dl, sil; nSubAuthorityCount
0x180020b3f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180020b43  call    cs:__imp_AllocateAndInitializeSid
0x180020b49  test    eax, eax
0x180020b4b  jnz     short loc_180020BA0
0x180020b4d  call    cs:__imp_GetLastError
0x180020b53  lea     rdi, WPP_GLOBAL_Control
0x180020b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b61  cmp     rcx, rdi
0x180020b64  jz      short loc_180020B87
0x180020b66  test    [rcx+10Ch], sil
0x180020b6d  jz      short loc_180020B87
0x180020b6f  mov     edx, ebx
0x180020b71  mov     r9d, eax
0x180020b74  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020b7b  mov     rcx, [rcx+100h]
0x180020b82  call    WPP_SF_d
0x180020b87  call    cs:__imp_GetLastError
0x180020b8d  test    eax, eax
0x180020b8f  jz      loc_180020C45
0x180020b95  mov     r8d, 3Eh ; '>'
0x180020b9b  jmp     loc_180020C37
0x180020ba0  lea     rax, ?g_pAdminSid@@3PEAXEA; void * g_pAdminSid
0x180020ba7  mov     [rsp+0D0h+pSid], rax; pSid
0x180020bac  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x180020bb1  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x180020bb6  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x180020bbb  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x180020bc0  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x180020bc5  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x180020bca  mov     r9d, 220h; nSubAuthority1
0x180020bd0  mov     r8d, 20h ; ' '; nSubAuthority0
0x180020bd6  lea     r15d, [r8-1Eh]
0x180020bda  mov     dl, r15b; nSubAuthorityCount
0x180020bdd  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180020be1  call    cs:__imp_AllocateAndInitializeSid
0x180020be7  test    eax, eax
0x180020be9  jnz     short loc_180020C4C
0x180020beb  call    cs:__imp_GetLastError
0x180020bf1  lea     rdi, WPP_GLOBAL_Control
0x180020bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bff  cmp     rcx, rdi
0x180020c02  jz      short loc_180020C27
0x180020c04  test    [rcx+10Ch], sil
0x180020c0b  jz      short loc_180020C27
0x180020c0d  lea     edx, [r15+11h]
0x180020c11  mov     r9d, eax
0x180020c14  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020c1b  mov     rcx, [rcx+100h]
0x180020c22  call    WPP_SF_d
0x180020c27  call    cs:__imp_GetLastError
0x180020c2d  test    eax, eax
0x180020c2f  jz      short loc_180020C45
0x180020c31  mov     r8d, 3Fh ; '?'; unsigned __int16
0x180020c37  lea     rdx, aAcssctrlAcssin; "acssctrl/acssinit"
0x180020c3e  mov     ecx, eax; int
0x180020c40  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180020c45  xor     al, al
0x180020c47  jmp     loc_180020FBC
0x180020c4c  mov     [rbp+57h+ReturnLength], r14d
0x180020c50  mov     [rbp+57h+TokenHandle], r14
0x180020c54  xor     r9d, r9d; int
0x180020c57  xor     edx, edx; int
0x180020c59  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180020c5d  call    ?GetAccessToken@@YAKPEAPEAXHKH@Z; GetAccessToken(void * *,int,ulong,int)
0x180020c62  mov     ebx, eax
0x180020c64  test    eax, eax
0x180020c66  jz      short loc_180020CA6
0x180020c68  lea     rdi, WPP_GLOBAL_Control
0x180020c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c76  cmp     rcx, rdi
0x180020c79  jz      short loc_180020C9F
0x180020c7b  test    [rcx+10Ch], sil
0x180020c82  jz      short loc_180020C9F
0x180020c84  mov     edx, 14h
0x180020c89  mov     r9d, eax
0x180020c8c  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020c93  mov     rcx, [rcx+100h]
0x180020c9a  call    WPP_SF_d
0x180020c9f  mov     eax, 40h ; '@'
0x180020ca4  jmp     short loc_180020D12
0x180020ca6  lea     rax, [rbp+57h+ReturnLength]
0x180020caa  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax; ReturnLength
0x180020caf  xor     r9d, r9d; TokenInformationLength
0x180020cb2  xor     r8d, r8d; TokenInformation
0x180020cb5  mov     edx, esi; TokenInformationClass
0x180020cb7  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180020cbb  call    cs:__imp_GetTokenInformation
0x180020cc1  call    cs:__imp_GetLastError
0x180020cc7  mov     ebx, eax
0x180020cc9  cmp     eax, 7Ah ; 'z'
0x180020ccc  jz      loc_180020D87
0x180020cd2  lea     rdi, WPP_GLOBAL_Control
0x180020cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ce0  cmp     rcx, rdi
0x180020ce3  jz      short loc_180020D09
0x180020ce5  test    [rcx+10Ch], sil
0x180020cec  jz      short loc_180020D09
0x180020cee  mov     edx, 15h
0x180020cf3  mov     r9d, eax
0x180020cf6  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020cfd  mov     rcx, [rcx+100h]
0x180020d04  call    WPP_SF_d
0x180020d09  test    ebx, ebx
0x180020d0b  jz      short loc_180020D79
0x180020d0d  mov     eax, 41h ; 'A'
0x180020d12  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r14; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180020d19  mov     dword ptr [rbp+57h+var_58], ebx
0x180020d1c  mov     [rbp+57h+var_70], ax
0x180020d20  jz      short loc_180020D79
0x180020d22  lea     rdi, aAcssctrlAcssin; "acssctrl/acssinit"
0x180020d29  mov     rcx, rdi; wchar_t *
0x180020d2c  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180020d31  mov     [rsp+0D0h+pSid], r14
0x180020d36  lea     r9d, [rsi+rax]
0x180020d3a  mov     qword ptr [rsp+0D0h+nSubAuthority7], r14
0x180020d3f  lea     rax, [rbp+57h+var_58]
0x180020d43  mov     qword ptr [rsp+0D0h+nSubAuthority6], rax
0x180020d48  mov     qword ptr [rsp+0D0h+nSubAuthority5], 4
0x180020d51  lea     rax, [rbp+57h+var_70]
0x180020d55  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x180020d5a  mov     qword ptr [rsp+0D0h+nSubAuthority3], r15
0x180020d5f  mov     qword ptr [rsp+0D0h+nSubAuthority2], rdi
0x180020d64  add     r9, r9
0x180020d67  mov     r8d, r15d
0x180020d6a  mov     edx, esi
0x180020d6c  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180020d73  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180020d78  nop
0x180020d79  lea     rcx, [rbp+57h+TokenHandle]; this
0x180020d7d  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180020d82  jmp     loc_180020C45
0x180020d87  mov     ecx, [rbp+57h+ReturnLength]; unsigned __int64
0x180020d8a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180020d8f  mov     rbx, rax
0x180020d92  mov     [rbp+57h+var_58], rax
0x180020d96  lea     rax, [rbp+57h+ReturnLength]
0x180020d9a  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax; ReturnLength
0x180020d9f  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x180020da3  mov     r8, rbx; TokenInformation
0x180020da6  mov     edx, esi; TokenInformationClass
0x180020da8  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180020dac  call    cs:__imp_GetTokenInformation
0x180020db2  test    eax, eax
0x180020db4  jnz     short loc_180020E21
0x180020db6  call    cs:__imp_GetLastError
0x180020dbc  lea     rdi, WPP_GLOBAL_Control
0x180020dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dca  cmp     rcx, rdi
0x180020dcd  jz      short loc_180020DF3
0x180020dcf  test    [rcx+10Ch], sil
0x180020dd6  jz      short loc_180020DF3
0x180020dd8  mov     edx, 16h
0x180020ddd  mov     r9d, eax
0x180020de0  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020de7  mov     rcx, [rcx+100h]
0x180020dee  call    WPP_SF_d
0x180020df3  call    cs:__imp_GetLastError
0x180020df9  test    eax, eax
0x180020dfb  jz      short loc_180020E12
0x180020dfd  mov     r8d, 42h ; 'B'; unsigned __int16
0x180020e03  lea     rdx, aAcssctrlAcssin; "acssctrl/acssinit"
0x180020e0a  mov     ecx, eax; int
0x180020e0c  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180020e11  nop
0x180020e12  mov     rcx, rbx; Block
0x180020e15  call    cs:__imp_free
0x180020e1b  nop
0x180020e1c  jmp     loc_180020D79
0x180020e21  mov     rdi, [rbx]
0x180020e24  mov     rcx, rdi; pSid
0x180020e27  call    cs:__imp_GetLengthSid
0x180020e2d  mov     ecx, eax; unsigned __int64
0x180020e2f  mov     [rbp+57h+ReturnLength], ecx
0x180020e32  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180020e37  mov     cs:?g_pProcessSid@@3PEAXEA, rax; void * g_pProcessSid
0x180020e3e  mov     r8, rdi; pSourceSid
0x180020e41  mov     rdx, rax; pDestinationSid
0x180020e44  mov     ecx, [rbp+57h+ReturnLength]; nDestinationSidLength
0x180020e47  call    cs:__imp_CopySid
0x180020e4d  test    eax, eax
0x180020e4f  jnz     short loc_180020EBC
0x180020e51  call    cs:__imp_GetLastError
0x180020e57  lea     rdi, WPP_GLOBAL_Control
0x180020e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e65  cmp     rcx, rdi
0x180020e68  jz      short loc_180020E8E
0x180020e6a  test    [rcx+10Ch], sil
0x180020e71  jz      short loc_180020E8E
0x180020e73  mov     edx, 17h
0x180020e78  mov     r9d, eax
0x180020e7b  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180020e82  mov     rcx, [rcx+100h]
0x180020e89  call    WPP_SF_d
0x180020e8e  call    cs:__imp_GetLastError
0x180020e94  test    eax, eax
0x180020e96  jz      short loc_180020EAD
0x180020e98  mov     r8d, 43h ; 'C'; unsigned __int16
0x180020e9e  lea     rdx, aAcssctrlAcssin; "acssctrl/acssinit"
0x180020ea5  mov     ecx, eax; int
0x180020ea7  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180020eac  nop
0x180020ead  mov     rcx, rbx; Block
0x180020eb0  call    cs:__imp_free
0x180020eb6  nop
0x180020eb7  jmp     loc_180020D79
0x180020ebc  lea     rdi, WPP_GLOBAL_Control
0x180020ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180020eca  cmp     rcx, rdi
0x180020ecd  jz      short loc_180020EF7
  ... truncated ...
```
