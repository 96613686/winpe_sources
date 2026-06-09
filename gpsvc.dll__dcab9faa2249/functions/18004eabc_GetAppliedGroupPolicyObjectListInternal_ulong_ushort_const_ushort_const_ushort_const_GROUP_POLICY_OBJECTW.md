# GetAppliedGroupPolicyObjectListInternal(ulong,ushort const *,ushort const *,ushort const *,_GROUP_POLICY_OBJECTW * *)

- ea: `0x18004eabc`
- end: `0x18004ef6e`
- name: `?GetAppliedGroupPolicyObjectListInternal@@YAKKPEBG00PEAPEAU_GROUP_POLICY_OBJECTW@@@Z`
- size: `1202`
- prototype: `unsigned int(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _GROUP_POLICY_OBJECTW **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ea20`

## callees

- `0x180001830`
- `0x180003770`
- `0x180003800`
- `0x1800246a8`
- `0x180030944`
- `0x18004eabc`
- `0x18006b2f8`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004eb96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ebbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004eb96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ebbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ec3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ec3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ec18`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ec18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ec00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ec00`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ec4e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ec4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004eccf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004eccf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004edca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ee24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004eeb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004eeff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ef34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004edca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ee24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004eeb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004eeff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ef34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ed86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004eeee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ed86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004eeee`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18004edf2`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18004ee5a`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18004eec9`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18004edf2`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18004ee5a`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18004eec9`

## string_xrefs

- `0x18004eb25`: `GetAppliedGroupPolicyObjectListInternal: Entering. Extension = %ws`
- `0x18004eb4c`: `GetAppliedGroupPolicyObjectListInternal: Entering. Extension = %ws`
- `0x18004ec76`: `GetAppliedGroupPolicyObjectListInternal:  Failed to get user token with  %d`
- `0x18004eca7`: `GetAppliedGroupPolicyObjectListInternal:  Failed to get user token with  %d`
- `0x18004ecef`: `GetAppliedGroupPolicyObjectListInternal: GetSidString failed.`
- `0x18004ed12`: `GetAppliedGroupPolicyObjectListInternal: GetSidString failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall GetAppliedGroupPolicyObjectListInternal(
        char a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _GROUP_POLICY_OBJECTW **a5)
{
  int v8; // ebx
  DWORD LastError; // ebx
  int v10; // eax
  int v11; // edi
  bool v12; // cf
  LSTATUS result; // eax
  int HasPerUserLocalSetting; // eax
  int v15; // r15d
  const unsigned __int16 *SidString; // rbx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void (*v19)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v20; // eax
  DWORD v21; // eax
  int v22; // ebx
  HKEY v23; // rcx
  int GPOList; // ebx
  LSTATUS v25; // ebx
  struct _GPOINFO *v26; // [rsp+30h] [rbp-D0h]
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v30[400]; // [rsp+60h] [rbp-A0h] BYREF

  if ( !a4 )
    return 87;
  v8 = a1 & 1;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"GetAppliedGroupPolicyObjectListInternal: Entering. Extension = %ws", a4);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"GetAppliedGroupPolicyObjectListInternal: Entering. Extension = %ws", a4);
    }
  }
  if ( a2 )
  {
    if ( v8 )
    {
      hKey = 0;
      result = RegConnectRegistryExW(a2, HKEY_LOCAL_MACHINE, 0, &hKey);
      if ( !result )
      {
        GPOList = ReadGPOList(a4, hKey, hKey, 0, 0, a5, v26);
        RegCloseKey(hKey);
        return GPOList == 0 ? 0x80004005 : 0;
      }
      return result;
    }
    TokenHandle = 0;
    if ( a3 )
    {
      result = RegConnectRegistryExW(a2, HKEY_LOCAL_MACHINE, 0, (PHKEY)&TokenHandle);
      if ( result )
        return result;
      if ( ExtensionHasPerUserLocalSetting(a4, (HKEY)TokenHandle) )
      {
        v22 = ReadGPOList(a4, (HKEY)TokenHandle, (HKEY)TokenHandle, a3, 0, a5, v26);
        v23 = (HKEY)TokenHandle;
        goto LABEL_42;
      }
      hKey = 0;
      phkResult = 0;
      RegCloseKey((HKEY)TokenHandle);
      result = RegConnectRegistryExW(a2, HKEY_USERS, 0, &hKey);
      if ( result )
        return result;
      v25 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
      if ( v25 )
      {
        RegCloseKey(hKey);
        if ( v25 == 2 )
          return 0;
        return v25;
      }
      v22 = ReadGPOList(a4, phkResult, phkResult, 0, 0, a5, v26);
      RegCloseKey(phkResult);
LABEL_41:
      v23 = hKey;
LABEL_42:
      RegCloseKey(v23);
      v12 = v22 != 0;
      return v12 ? 0 : 0x80004005;
    }
    return 87;
  }
  if ( v8 )
  {
    LastError = GetLastError();
    LODWORD(TokenHandle) = LastError;
    v10 = StringCchPrintfW(v30, 0x190u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\History\\%ws", a4);
    if ( v10 >= 0 )
    {
      v11 = ReadGPOList(HKEY_LOCAL_MACHINE, v30, a5, 0);
      SetLastError(LastError);
    }
    else
    {
      SetLastError((unsigned __int16)v10);
      v11 = 0;
    }
LABEL_13:
    v12 = v11 != 0;
    return v12 ? 0 : 0x80004005;
  }
  HasPerUserLocalSetting = ExtensionHasPerUserLocalSetting(a4, HKEY_LOCAL_MACHINE);
  v15 = HasPerUserLocalSetting;
  if ( a3 )
  {
    hKey = 0;
    result = RegOpenKeyExW(HKEY_USERS, a3, 0, 0x20019u, &hKey);
    if ( result )
    {
      if ( result == 2 )
        return 0;
      return result;
    }
    v22 = ReadGPOList(
            a4,
            hKey,
            HKEY_LOCAL_MACHINE,
            (const unsigned __int16 *)((unsigned __int64)a3 & -(__int64)(v15 != 0)),
            0,
            a5,
            v26);
    goto LABEL_41;
  }
  SidString = 0;
  if ( !HasPerUserLocalSetting )
    goto LABEL_35;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return GetLastError();
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v19 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v20 = GetLastError();
          v19(2u, L"GetAppliedGroupPolicyObjectListInternal:  Failed to get user token with  %d", v20);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v21 = GetLastError();
          RedirectDebugMsg(2u, L"GetAppliedGroupPolicyObjectListInternal:  Failed to get user token with  %d", v21);
        }
      }
      return GetLastError();
    }
  }
  SidString = GetSidString(TokenHandle);
  CloseHandle(TokenHandle);
  if ( SidString )
  {
LABEL_35:
    v11 = ReadGPOList(a4, HKEY_CURRENT_USER, HKEY_LOCAL_MACHINE, SidString, 0, a5, v26);
    if ( SidString )
      DeleteSidString(SidString);
    goto LABEL_13;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"GetAppliedGroupPolicyObjectListInternal: GetSidString failed.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"GetAppliedGroupPolicyObjectListInternal: GetSidString failed.");
    }
  }
  return -2147467259;
}

```

## disassembly

```asm
0x18004eabc  mov     [rsp-8+arg_0], rbx
0x18004eac1  push    rbp
0x18004eac2  push    rsi
0x18004eac3  push    rdi
0x18004eac4  push    r12
0x18004eac6  push    r13
0x18004eac8  push    r14
0x18004eaca  push    r15
0x18004eacc  lea     rbp, [rsp-290h]
0x18004ead4  sub     rsp, 390h
0x18004eadb  mov     rax, cs:__security_cookie
0x18004eae2  xor     rax, rsp
0x18004eae5  mov     [rbp+2C0h+var_40], rax
0x18004eaec  mov     rsi, r9
0x18004eaef  mov     r14, r8
0x18004eaf2  mov     r15, rdx
0x18004eaf5  mov     ebx, ecx
0x18004eaf7  mov     r12, [rbp+2C0h+arg_20]
0x18004eafe  xor     r13d, r13d
0x18004eb01  test    r9, r9
0x18004eb04  jz      loc_18004EF3F
0x18004eb0a  and     ebx, 1
0x18004eb0d  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004eb14  jz      short loc_18004EB5D
0x18004eb16  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004eb1d  test    rax, rax
0x18004eb20  jz      short loc_18004EB37
0x18004eb22  mov     r8, r9
0x18004eb25  lea     rdx, aGetappliedgrou; "GetAppliedGroupPolicyObjectListInternal"...
0x18004eb2c  lea     ecx, [r13+4]
0x18004eb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb35  jmp     short loc_18004EB5D
0x18004eb37  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004eb3e  jz      short loc_18004EB5D
0x18004eb40  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004eb47  jz      short loc_18004EB5D
0x18004eb49  mov     r8, rsi
0x18004eb4c  lea     rdx, aGetappliedgrou; "GetAppliedGroupPolicyObjectListInternal"...
0x18004eb53  mov     ecx, 4; unsigned int
0x18004eb58  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004eb5d  test    r15, r15
0x18004eb60  jnz     loc_18004EDD7
0x18004eb66  test    ebx, ebx
0x18004eb68  jz      short loc_18004EBD2
0x18004eb6a  call    cs:__imp_GetLastError
0x18004eb70  mov     ebx, eax
0x18004eb72  mov     dword ptr [rsp+3C0h+TokenHandle], eax
0x18004eb76  mov     r9, rsi
0x18004eb79  lea     r8, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004eb80  mov     edx, 190h; unsigned __int64
0x18004eb85  lea     rcx, [rsp+3C0h+var_360]; unsigned __int16 *
0x18004eb8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004eb8f  test    eax, eax
0x18004eb91  jns     short loc_18004EBA1
0x18004eb93  movzx   ecx, ax; dwErrCode
0x18004eb96  call    cs:__imp_SetLastError
0x18004eb9c  mov     edi, r13d
0x18004eb9f  jmp     short loc_18004EBC2
0x18004eba1  xor     r9d, r9d; struct _GPOINFO *
0x18004eba4  mov     r8, r12; struct _GROUP_POLICY_OBJECTW **
0x18004eba7  lea     rdx, [rsp+3C0h+var_360]; unsigned __int16 *
0x18004ebac  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18004ebb3  call    ?ReadGPOList@@YAHPEAUHKEY__@@PEAGPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(HKEY__ *,ushort *,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x18004ebb8  mov     edi, eax
0x18004ebba  mov     ecx, ebx; dwErrCode
0x18004ebbc  call    cs:__imp_SetLastError
0x18004ebc2  neg     edi
0x18004ebc4  sbb     eax, eax
0x18004ebc6  not     eax
0x18004ebc8  and     eax, 80004005h
0x18004ebcd  jmp     loc_18004EF44
0x18004ebd2  mov     rdi, 0FFFFFFFF80000002h
0x18004ebd9  mov     rdx, rdi; HKEY
0x18004ebdc  mov     rcx, rsi; unsigned __int16 *
0x18004ebdf  call    ?ExtensionHasPerUserLocalSetting@@YAHPEBGPEAUHKEY__@@@Z; ExtensionHasPerUserLocalSetting(ushort const *,HKEY__ *)
0x18004ebe4  mov     r15d, eax
0x18004ebe7  test    r14, r14
0x18004ebea  jnz     loc_18004ED64
0x18004ebf0  mov     rbx, r13
0x18004ebf3  test    eax, eax
0x18004ebf5  jz      loc_18004ED2D
0x18004ebfb  mov     [rsp+3C0h+TokenHandle], r13
0x18004ec00  call    cs:__imp_GetCurrentThread
0x18004ec06  mov     rcx, rax; ThreadHandle
0x18004ec09  lea     r9, [rsp+3C0h+TokenHandle]; TokenHandle
0x18004ec0e  lea     ebx, [r14+8]
0x18004ec12  lea     r8d, [r14+1]; OpenAsSelf
0x18004ec16  mov     edx, ebx; DesiredAccess
0x18004ec18  call    cs:__imp_OpenThreadToken
0x18004ec1e  test    eax, eax
0x18004ec20  jnz     loc_18004ECBD
0x18004ec26  call    cs:__imp_GetLastError
0x18004ec2c  cmp     eax, 3F0h
0x18004ec31  jz      short loc_18004EC3E
0x18004ec33  call    cs:__imp_GetLastError
0x18004ec39  jmp     loc_18004EF44
0x18004ec3e  call    cs:__imp_GetCurrentProcess
0x18004ec44  mov     rcx, rax; ProcessHandle
0x18004ec47  lea     r8, [rsp+3C0h+TokenHandle]; TokenHandle
0x18004ec4c  mov     edx, ebx; DesiredAccess
0x18004ec4e  call    cs:__imp_OpenProcessToken
0x18004ec54  test    eax, eax
0x18004ec56  jnz     short loc_18004ECBD
0x18004ec58  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004ec5f  jz      short loc_18004EC33
0x18004ec61  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004ec68  test    rbx, rbx
0x18004ec6b  jz      short loc_18004EC8C
0x18004ec6d  call    cs:__imp_GetLastError
0x18004ec73  mov     r8d, eax
0x18004ec76  lea     rdx, aGetappliedgrou_2; "GetAppliedGroupPolicyObjectListInternal"...
0x18004ec7d  mov     ecx, 2
0x18004ec82  mov     rax, rbx
0x18004ec85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec8a  jmp     short loc_18004EC33
0x18004ec8c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004ec93  jz      short loc_18004EC33
0x18004ec95  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004ec9c  jz      short loc_18004EC33
0x18004ec9e  call    cs:__imp_GetLastError
0x18004eca4  mov     r8d, eax
0x18004eca7  lea     rdx, aGetappliedgrou_2; "GetAppliedGroupPolicyObjectListInternal"...
0x18004ecae  mov     ecx, 2; unsigned int
0x18004ecb3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004ecb8  jmp     loc_18004EC33
0x18004ecbd  mov     rcx, [rsp+3C0h+TokenHandle]; void *
0x18004ecc2  call    ?GetSidString@@YAPEAGPEAX@Z; GetSidString(void *)
0x18004ecc7  mov     rbx, rax
0x18004ecca  mov     rcx, [rsp+3C0h+TokenHandle]; hObject
0x18004eccf  call    cs:__imp_CloseHandle
0x18004ecd5  test    rbx, rbx
0x18004ecd8  jnz     short loc_18004ED2D
0x18004ecda  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004ece1  jz      short loc_18004ED23
0x18004ece3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004ecea  test    rax, rax
0x18004eced  jz      short loc_18004ED00
0x18004ecef  lea     rdx, aGetappliedgrou_0; "GetAppliedGroupPolicyObjectListInternal"...
0x18004ecf6  lea     ecx, [rbx+2]
0x18004ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecfe  jmp     short loc_18004ED23
0x18004ed00  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004ed07  jz      short loc_18004ED23
0x18004ed09  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004ed10  jz      short loc_18004ED23
0x18004ed12  lea     rdx, aGetappliedgrou_0; "GetAppliedGroupPolicyObjectListInternal"...
0x18004ed19  mov     ecx, 2; unsigned int
0x18004ed1e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004ed23  mov     eax, 80004005h
0x18004ed28  jmp     loc_18004EF44
0x18004ed2d  mov     [rsp+3C0h+var_398], r12; struct _GROUP_POLICY_OBJECTW **
0x18004ed32  mov     dword ptr [rsp+3C0h+phkResult], r13d; int
0x18004ed37  mov     r9, rbx; unsigned __int16 *
0x18004ed3a  mov     r8, rdi; HKEY
0x18004ed3d  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x18004ed44  mov     rcx, rsi; unsigned __int16 *
0x18004ed47  call    ?ReadGPOList@@YAHPEBGPEAUHKEY__@@10HPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(ushort const *,HKEY__ *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x18004ed4c  mov     edi, eax
0x18004ed4e  test    rbx, rbx
0x18004ed51  jz      loc_18004EBC2
0x18004ed57  mov     rcx, rbx; SourceString
0x18004ed5a  call    ?DeleteSidString@@YAXPEAG@Z; DeleteSidString(ushort *)
0x18004ed5f  jmp     loc_18004EBC2
0x18004ed64  mov     [rsp+3C0h+hKey], r13
0x18004ed69  lea     rax, [rsp+3C0h+hKey]
0x18004ed6e  mov     [rsp+3C0h+phkResult], rax; phkResult
0x18004ed73  mov     r9d, 20019h; samDesired
0x18004ed79  xor     r8d, r8d; ulOptions
0x18004ed7c  mov     rdx, r14; lpSubKey
0x18004ed7f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18004ed86  call    cs:__imp_RegOpenKeyExW
0x18004ed8c  test    eax, eax
0x18004ed8e  jz      short loc_18004EDA0
0x18004ed90  cmp     eax, 2
0x18004ed93  jnz     loc_18004EF44
0x18004ed99  xor     eax, eax
0x18004ed9b  jmp     loc_18004EF44
0x18004eda0  neg     r15d
0x18004eda3  sbb     r9, r9
0x18004eda6  and     r9, r14; unsigned __int16 *
0x18004eda9  mov     [rsp+3C0h+var_398], r12; struct _GROUP_POLICY_OBJECTW **
0x18004edae  mov     dword ptr [rsp+3C0h+phkResult], r13d; int
0x18004edb3  mov     r8, rdi; HKEY
0x18004edb6  mov     rdx, [rsp+3C0h+hKey]; HKEY
0x18004edbb  mov     rcx, rsi; unsigned __int16 *
0x18004edbe  call    ?ReadGPOList@@YAHPEBGPEAUHKEY__@@10HPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(ushort const *,HKEY__ *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x18004edc3  mov     ebx, eax
0x18004edc5  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18004edca  call    cs:__imp_RegCloseKey
0x18004edd0  neg     ebx
0x18004edd2  jmp     loc_18004EBC4
0x18004edd7  test    ebx, ebx
0x18004edd9  jz      short loc_18004EE3A
0x18004eddb  mov     [rsp+3C0h+hKey], r13
0x18004ede0  lea     r9, [rsp+3C0h+hKey]; phkResult
0x18004ede5  xor     r8d, r8d; Flags
0x18004ede8  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18004edef  mov     rcx, r15; lpMachineName
0x18004edf2  call    cs:__imp_RegConnectRegistryExW
0x18004edf8  test    eax, eax
0x18004edfa  jnz     loc_18004EF44
0x18004ee00  mov     rdx, [rsp+3C0h+hKey]; HKEY
0x18004ee05  mov     [rsp+3C0h+var_398], r12; struct _GROUP_POLICY_OBJECTW **
0x18004ee0a  mov     dword ptr [rsp+3C0h+phkResult], r13d; int
0x18004ee0f  xor     r9d, r9d; unsigned __int16 *
0x18004ee12  mov     r8, rdx; HKEY
0x18004ee15  mov     rcx, rsi; unsigned __int16 *
0x18004ee18  call    ?ReadGPOList@@YAHPEBGPEAUHKEY__@@10HPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(ushort const *,HKEY__ *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x18004ee1d  mov     ebx, eax
0x18004ee1f  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18004ee24  call    cs:__imp_RegCloseKey
0x18004ee2a  neg     ebx
0x18004ee2c  sbb     eax, eax
0x18004ee2e  not     eax
0x18004ee30  and     eax, 80004005h
0x18004ee35  jmp     loc_18004EF44
0x18004ee3a  mov     [rsp+3C0h+TokenHandle], r13
0x18004ee3f  test    r14, r14
0x18004ee42  jz      loc_18004EF3F
0x18004ee48  lea     r9, [rsp+3C0h+TokenHandle]; phkResult
0x18004ee4d  xor     r8d, r8d; Flags
0x18004ee50  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18004ee57  mov     rcx, r15; lpMachineName
0x18004ee5a  call    cs:__imp_RegConnectRegistryExW
0x18004ee60  test    eax, eax
0x18004ee62  jnz     loc_18004EF44
0x18004ee68  mov     rdx, [rsp+3C0h+TokenHandle]; HKEY
0x18004ee6d  mov     rcx, rsi; unsigned __int16 *
0x18004ee70  call    ?ExtensionHasPerUserLocalSetting@@YAHPEBGPEAUHKEY__@@@Z; ExtensionHasPerUserLocalSetting(ushort const *,HKEY__ *)
0x18004ee75  test    eax, eax
0x18004ee77  jz      short loc_18004EEA2
0x18004ee79  mov     rdx, [rsp+3C0h+TokenHandle]; HKEY
0x18004ee7e  mov     [rsp+3C0h+var_398], r12; struct _GROUP_POLICY_OBJECTW **
0x18004ee83  mov     dword ptr [rsp+3C0h+phkResult], r13d; int
0x18004ee88  mov     r9, r14; unsigned __int16 *
0x18004ee8b  mov     r8, rdx; HKEY
0x18004ee8e  mov     rcx, rsi; unsigned __int16 *
0x18004ee91  call    ?ReadGPOList@@YAHPEBGPEAUHKEY__@@10HPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(ushort const *,HKEY__ *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x18004ee96  mov     ebx, eax
0x18004ee98  mov     rcx, [rsp+3C0h+TokenHandle]
0x18004ee9d  jmp     loc_18004EDCA
0x18004eea2  mov     [rsp+3C0h+hKey], r13
0x18004eea7  mov     [rsp+3C0h+var_370], r13
0x18004eeac  mov     rcx, [rsp+3C0h+TokenHandle]; hKey
0x18004eeb1  call    cs:__imp_RegCloseKey
0x18004eeb7  lea     r9, [rsp+3C0h+hKey]; phkResult
0x18004eebc  xor     r8d, r8d; Flags
0x18004eebf  mov     rdx, 0FFFFFFFF80000003h; hKey
0x18004eec6  mov     rcx, r15; lpMachineName
0x18004eec9  call    cs:__imp_RegConnectRegistryExW
0x18004eecf  test    eax, eax
0x18004eed1  jnz     short loc_18004EF44
0x18004eed3  lea     rax, [rsp+3C0h+var_370]
0x18004eed8  mov     [rsp+3C0h+phkResult], rax; phkResult
0x18004eedd  mov     r9d, 20019h; samDesired
0x18004eee3  xor     r8d, r8d; ulOptions
0x18004eee6  mov     rdx, r14; lpSubKey
0x18004eee9  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18004eeee  call    cs:__imp_RegOpenKeyExW
0x18004eef4  mov     ebx, eax
0x18004eef6  test    eax, eax
0x18004eef8  jz      short loc_18004EF10
0x18004eefa  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18004eeff  call    cs:__imp_RegCloseKey
0x18004ef05  cmp     ebx, 2
0x18004ef08  cmovz   ebx, r13d
0x18004ef0c  mov     eax, ebx
0x18004ef0e  jmp     short loc_18004EF44
0x18004ef10  mov     rdx, [rsp+3C0h+var_370]; HKEY
0x18004ef15  mov     [rsp+3C0h+var_398], r12; struct _GROUP_POLICY_OBJECTW **
0x18004ef1a  mov     dword ptr [rsp+3C0h+phkResult], r13d; int
0x18004ef1f  xor     r9d, r9d; unsigned __int16 *
0x18004ef22  mov     r8, rdx; HKEY
0x18004ef25  mov     rcx, rsi; unsigned __int16 *
0x18004ef28  call    ?ReadGPOList@@YAHPEBGPEAUHKEY__@@10HPEAPEAU_GROUP_POLICY_OBJECTW@@PEAU_GPOINFO@@@Z; ReadGPOList(ushort const *,HKEY__ *,HKEY__ *,ushort const *,int,_GROUP_POLICY_OBJECTW * *,_GPOINFO *)
0x18004ef2d  mov     ebx, eax
0x18004ef2f  mov     rcx, [rsp+3C0h+var_370]; hKey
0x18004ef34  call    cs:__imp_RegCloseKey
0x18004ef3a  jmp     loc_18004EDC5
0x18004ef3f  mov     eax, 57h ; 'W'
0x18004ef44  mov     rcx, [rbp+2C0h+var_40]
0x18004ef4b  xor     rcx, rsp; StackCookie
0x18004ef4e  call    __security_check_cookie
0x18004ef53  mov     rbx, [rsp+3C0h+arg_0]
0x18004ef5b  add     rsp, 390h
0x18004ef62  pop     r15
0x18004ef64  pop     r14
0x18004ef66  pop     r13
0x18004ef68  pop     r12
0x18004ef6a  pop     rdi
0x18004ef6b  pop     rsi
0x18004ef6c  pop     rbp
0x18004ef6d  retn
```
