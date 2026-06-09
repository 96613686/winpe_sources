# FwRpcAPIsSecModeAccessCheckForClient

- ea: `0x180032774`
- end: `0x180032a99`
- name: `FwRpcAPIsSecModeAccessCheckForClient`
- size: `805`
- prototype: `__int64 __fastcall(unsigned int, int, void *)`
- caller_count: `143`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800308e0`
- `0x180030f60`
- `0x180031410`
- `0x180031970`
- `0x180031a40`
- `0x1800321c0`
- `0x1800323a0`
- `0x180032500`
- `0x1800339e0`
- `0x180033ab0`
- `0x180040cc0`
- `0x1800509a0`
- `0x180055820`
- `0x180057f20`
- `0x18005af00`
- `0x18006c490`
- `0x18006c560`
- `0x18006d9f0`
- `0x180094b58`
- `0x18009d0c8`
- `0x1800bf450`
- `0x1800bf520`
- `0x1800bf5f0`
- `0x1800bf6c0`
- `0x1800bf790`
- `0x1800bf860`
- `0x1800bf930`
- `0x1800bfa00`
- `0x1800bfad0`
- `0x1800bfba0`
- `0x1800bfc70`
- `0x1800bfd40`
- `0x1800bfe10`
- `0x1800bfee0`
- `0x1800bffb0`
- `0x1800c0080`
- `0x1800c0150`
- `0x1800c0220`
- `0x1800c02f0`
- `0x1800c03c0`
- `0x1800c0490`
- `0x1800c0540`
- `0x1800c0610`
- `0x1800c06e0`
- `0x1800c07b0`
- `0x1800c0860`
- `0x1800c0930`
- `0x1800c0a00`
- `0x1800c0ab0`
- `0x1800c0b80`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x180032774`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003280b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003280b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800327f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800327f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003299d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003299d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329e5`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800328a0`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800328a0`
- `RPCRT4!RpcRevertToSelf` at `0x180032832`
- `RPCRT4!RpcRevertToSelf` at `0x180032832`
- `RPCRT4!RpcImpersonateClient` at `0x1800327e7`
- `RPCRT4!RpcImpersonateClient` at `0x1800327e7`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800327a9`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800327a9`
- `fwbase!FwCloseHandle` at `0x1800328b6`
- `fwbase!FwCloseHandle` at `0x1800328b6`

## string_xrefs

- `0x180032a45`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwRpcAPIsSecModeAccessCheckForClient(unsigned int a1, int a2, void *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  __int64 v6; // rcx
  DWORD v7; // r15d
  void *v8; // r14
  void *v9; // r12
  RPC_STATUS v10; // eax
  unsigned int v11; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v13; // eax
  __int64 v14; // rcx
  WINBOOL v15; // edi
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  signed int LastError; // eax
  signed int v21; // eax
  void *TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+48h] [rbp-21h] BYREF
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-1Dh] BYREF
  DWORD GrantedAccess; // [rsp+50h] [rbp-19h] BYREF
  DWORD PrivilegeSetLength; // [rsp+54h] [rbp-15h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+58h] [rbp-11h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+70h] [rbp+7h] BYREF

  v3 = a1;
  v5 = a2;
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) >= 0 && pfEnabled[0] )
    v6 = 3;
  else
    v6 = 0;
  TokenHandle = 0;
  v7 = *((_DWORD *)&AccessCheckAccessRights + v5);
  v8 = 0;
  v9 = (void *)qword_18012C848[v6 + v3];
  v10 = RpcImpersonateClient(a3);
  v11 = v10;
  if ( !v10 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v8 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v8 = TokenHandle;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
    }
    v13 = RpcRevertToSelf();
    if ( v13 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v13, 0);
    goto LABEL_10;
  }
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
LABEL_10:
    v14 = WPP_GLOBAL_Control;
  }
  if ( (v11 & 0x80000000) != 0 )
  {
    v15 = 0;
    if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
    {
      v19 = 36;
      goto LABEL_26;
    }
  }
  else
  {
    PrivilegeSetLength = 20;
    GrantedAccess = 0;
    AccessStatus = 0;
    GenericMapping = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(v9, v8, v7, &GenericMapping, &PrivilegeSet, &PrivilegeSetLength, &GrantedAccess, &AccessStatus) )
    {
      v15 = AccessStatus;
      v11 = 0;
      goto LABEL_14;
    }
    v21 = GetLastError();
    v11 = v21;
    if ( v21 > 0 )
      v11 = (unsigned __int16)v21 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
      v14 = WPP_GLOBAL_Control;
    }
    v15 = 0;
    if ( (v11 & 0x80000000) != 0 && (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
    {
      v19 = 37;
LABEL_26:
      WPP_SF_d(*(_QWORD *)(v14 + 16), v19, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
    }
  }
LABEL_14:
  FwCloseHandle(v8);
  if ( (v11 & 0x80000000) != 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v18 = 16;
      goto LABEL_20;
    }
  }
  else if ( !v15 )
  {
    v11 = -2147024891;
    v17 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v18 = 17;
LABEL_20:
      WPP_SF_d(*(_QWORD *)(v17 + 16), v18, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v11);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180032774  push    rbp
0x180032776  push    rbx
0x180032777  push    rsi
0x180032778  push    rdi
0x180032779  push    r12
0x18003277b  push    r14
0x18003277d  push    r15
0x18003277f  lea     rbp, [rsp-27h]
0x180032784  sub     rsp, 90h
0x18003278b  mov     rax, cs:__security_cookie
0x180032792  xor     rax, rsp
0x180032795  mov     [rbp+57h+var_40], rax
0x180032799  mov     ebx, ecx
0x18003279b  mov     rsi, r8
0x18003279e  lea     rcx, [rbp+57h+pfEnabled]; pfEnabled
0x1800327a2  movsxd  rdi, edx
0x1800327a5  mov     [rbp+57h+pfEnabled], 0
0x1800327a9  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x1800327af  test    eax, eax
0x1800327b1  js      short loc_1800327BD
0x1800327b3  cmp     [rbp+57h+pfEnabled], 0
0x1800327b7  jnz     loc_180032919
0x1800327bd  xor     ecx, ecx
0x1800327bf  add     rbx, rcx
0x1800327c2  mov     [rbp+57h+TokenHandle], 0
0x1800327ca  lea     r12, __ImageBase
0x1800327d1  mov     rcx, rsi; BindingHandle
0x1800327d4  mov     r15d, ds:rva ?AccessCheckAccessRights@@3PAKA[r12+rdi*4]; ulong near * AccessCheckAccessRights ...
0x1800327dc  xor     r14d, r14d
0x1800327df  mov     r12, rva qword_18012C848[r12+rbx*8]
0x1800327e7  call    cs:__imp_RpcImpersonateClient
0x1800327ed  mov     ebx, eax
0x1800327ef  test    eax, eax
0x1800327f1  jnz     loc_180032953
0x1800327f7  call    cs:__imp_GetCurrentThread
0x1800327fd  mov     rcx, rax; ThreadHandle
0x180032800  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180032804  lea     edx, [rbx+8]; DesiredAccess
0x180032807  lea     r8d, [r14+1]; OpenAsSelf
0x18003280b  call    cs:__imp_OpenThreadToken
0x180032811  mov     edi, 80070000h
0x180032816  lea     rsi, WPP_GLOBAL_Control
0x18003281d  test    eax, eax
0x18003281f  jz      loc_18003299D
0x180032825  mov     r14, [rbp+57h+TokenHandle]
0x180032829  test    r14, r14
0x18003282c  jz      loc_180032A34
0x180032832  call    cs:__imp_RpcRevertToSelf
0x180032838  test    eax, eax
0x18003283a  jnz     loc_180032A42
0x180032840  mov     rcx, cs:WPP_GLOBAL_Control
0x180032847  test    ebx, ebx
0x180032849  js      loc_180032A58
0x18003284f  xor     eax, eax
0x180032851  mov     [rbp+57h+var_6C], 14h
0x180032858  mov     [rbp+57h+var_68.Privilege.Attributes], eax
0x18003285b  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18003285f  mov     [rbp+57h+var_70], eax
0x180032862  xorps   xmm0, xmm0
0x180032865  mov     [rbp+57h+var_74], eax
0x180032868  xorps   xmm1, xmm1
0x18003286b  lea     rax, [rbp+57h+var_74]
0x18003286f  mov     r8d, r15d; DesiredAccess
0x180032872  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x180032877  mov     rdx, r14; ClientToken
0x18003287a  lea     rax, [rbp+57h+var_70]
0x18003287e  mov     rcx, r12; pSecurityDescriptor
0x180032881  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180032886  lea     rax, [rbp+57h+var_6C]
0x18003288a  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003288f  lea     rax, [rbp+57h+var_68]
0x180032893  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x180032898  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18003289c  movups  xmmword ptr [rbp+57h+var_68.PrivilegeCount], xmm1
0x1800328a0  call    cs:__imp_AccessCheck
0x1800328a6  test    eax, eax
0x1800328a8  jz      loc_1800329E5
0x1800328ae  mov     edi, [rbp+57h+var_74]
0x1800328b1  xor     ebx, ebx
0x1800328b3  mov     rcx, r14
0x1800328b6  call    cs:__imp_FwCloseHandle
0x1800328bc  test    ebx, ebx
0x1800328be  js      loc_180032A75
0x1800328c4  test    edi, edi
0x1800328c6  jz      short loc_1800328E8
0x1800328c8  mov     eax, ebx
0x1800328ca  mov     rcx, [rbp+57h+var_40]
0x1800328ce  xor     rcx, rsp; StackCookie
0x1800328d1  call    __security_check_cookie
0x1800328d6  add     rsp, 90h
0x1800328dd  pop     r15
0x1800328df  pop     r14
0x1800328e1  pop     r12
0x1800328e3  pop     rdi
0x1800328e4  pop     rsi
0x1800328e5  pop     rbx
0x1800328e6  pop     rbp
0x1800328e7  retn
0x1800328e8  mov     ebx, 80070005h
0x1800328ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328f4  cmp     rcx, rsi
0x1800328f7  jz      short loc_1800328C8
0x1800328f9  test    byte ptr [rcx+1Ch], 1
0x1800328fd  jz      short loc_1800328C8
0x1800328ff  mov     edx, 11h
0x180032904  mov     rcx, [rcx+10h]
0x180032908  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003290f  mov     r9d, ebx
0x180032912  call    WPP_SF_d
0x180032917  jmp     short loc_1800328C8
0x180032919  mov     ecx, 3
0x18003291e  jmp     loc_1800327BF
0x180032923  xor     edi, edi
0x180032925  test    ebx, ebx
0x180032927  jns     short loc_1800328B3
0x180032929  cmp     rcx, rsi
0x18003292c  jz      short loc_1800328B3
0x18003292e  test    byte ptr [rcx+1Ch], 1
0x180032932  jz      loc_1800328B3
0x180032938  lea     edx, [rdi+25h]
0x18003293b  mov     rcx, [rcx+10h]
0x18003293f  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180032946  mov     r9d, ebx
0x180032949  call    WPP_SF_d
0x18003294e  jmp     loc_1800328B3
0x180032953  mov     edi, 80070000h
0x180032958  jle     short loc_18003295F
0x18003295a  movzx   ebx, ax
0x18003295d  or      ebx, edi
0x18003295f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032966  lea     rsi, WPP_GLOBAL_Control
0x18003296d  cmp     rcx, rsi
0x180032970  jz      loc_180032847
0x180032976  test    byte ptr [rcx+1Ch], 1
0x18003297a  jz      loc_180032847
0x180032980  mov     rcx, [rcx+10h]
0x180032984  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003298b  mov     edx, 22h ; '"'
0x180032990  mov     r9d, ebx
0x180032993  call    WPP_SF_d
0x180032998  jmp     loc_180032840
0x18003299d  call    cs:__imp_GetLastError
0x1800329a3  mov     ebx, eax
0x1800329a5  test    eax, eax
0x1800329a7  jle     short loc_1800329AE
0x1800329a9  movzx   ebx, ax
0x1800329ac  or      ebx, edi
0x1800329ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329b5  cmp     rcx, rsi
0x1800329b8  jz      loc_180032832
0x1800329be  test    byte ptr [rcx+1Ch], 1
0x1800329c2  jz      loc_180032832
0x1800329c8  mov     rcx, [rcx+10h]
0x1800329cc  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800329d3  mov     edx, 23h ; '#'
0x1800329d8  mov     r9d, ebx
0x1800329db  call    WPP_SF_d
0x1800329e0  jmp     loc_180032832
0x1800329e5  call    cs:__imp_GetLastError
0x1800329eb  mov     ebx, eax
0x1800329ed  test    eax, eax
0x1800329ef  jle     short loc_1800329F6
0x1800329f1  movzx   ebx, ax
0x1800329f4  or      ebx, edi
0x1800329f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329fd  cmp     rcx, rsi
0x180032a00  jz      loc_180032923
0x180032a06  test    byte ptr [rcx+1Ch], 1
0x180032a0a  jz      loc_180032923
0x180032a10  mov     rcx, [rcx+10h]
0x180032a14  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180032a1b  mov     edx, 26h ; '&'
0x180032a20  mov     r9d, ebx
0x180032a23  call    WPP_SF_d
0x180032a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a2f  jmp     loc_180032923
0x180032a34  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032a39  mov     r14, [rbp+57h+TokenHandle]
0x180032a3d  jmp     loc_180032832
0x180032a42  xor     r8d, r8d
0x180032a45  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180032a4c  mov     edx, eax
0x180032a4e  call    MicrosoftTelemetryAssertTriggeredArgs
0x180032a53  jmp     loc_180032840
0x180032a58  xor     edi, edi
0x180032a5a  cmp     rcx, rsi
0x180032a5d  jz      loc_1800328B3
0x180032a63  test    byte ptr [rcx+1Ch], 1
0x180032a67  jz      loc_1800328B3
0x180032a6d  lea     edx, [rdi+24h]
0x180032a70  jmp     loc_18003293B
0x180032a75  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a7c  cmp     rcx, rsi
0x180032a7f  jz      loc_1800328C8
0x180032a85  test    byte ptr [rcx+1Ch], 1
0x180032a89  jz      loc_1800328C8
0x180032a8f  mov     edx, 10h
0x180032a94  jmp     loc_180032904
```
