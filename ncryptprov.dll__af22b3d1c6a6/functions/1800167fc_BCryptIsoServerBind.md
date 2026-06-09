# BCryptIsoServerBind

- ea: `0x1800167fc`
- end: `0x180016a2f`
- name: `BCryptIsoServerBind`
- size: `563`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180016550`

## callees

- `0x18000af80`
- `0x1800167fc`
- `0x180016ac8`
- `0x180016b98`
- `0x18001b154`
- `0x18001b634`
- `0x180023bc8`
- `0x18002490c`
- `0x180025ea8`
- `0x180028158`
- `0x18002831c`
- `0x180028d5c`
- `0x18003fd08`
- `0x1800406dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001682c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001682c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800169c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800169c2`
- `RPCRT4!RpcRevertToSelf` at `0x18001690d`
- `RPCRT4!RpcRevertToSelf` at `0x18001690d`
- `RPCRT4!RpcImpersonateClient` at `0x180016970`
- `RPCRT4!RpcImpersonateClient` at `0x1800169d4`
- `RPCRT4!RpcImpersonateClient` at `0x180016970`
- `RPCRT4!RpcImpersonateClient` at `0x1800169d4`

## string_xrefs

- `0x1800168a4`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x180016927`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x180016954`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x18001699d`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`

## pseudocode

```c
__int64 BCryptIsoServerBind()
{
  int v0; // ebp
  int CanLaunchSecureProcess; // esi
  int v2; // ebx
  int v3; // edi
  int inited; // eax
  unsigned int v5; // eax
  __int64 v6; // r9
  int v7; // eax
  int v8; // eax
  int v9; // r8d
  int v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = 0;
  v0 = 0;
  CanLaunchSecureProcess = 0;
  v2 = I_BCryptIsoCheckRpc(0);
  if ( v2 >= 0 )
    goto LABEL_27;
  v3 = 1;
  AcquireSRWLockExclusive(&g_servicingLock);
  v2 = I_BCryptIsoCheckRpc(0);
  if ( v2 < 0 )
  {
    I_BCryptIsoUninitializeRpc();
    g_keyguardRegistryData = BCryptIsoIsDisabledInRegistry();
    if ( g_keyguardRegistryData )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids);
      goto LABEL_7;
    }
    inited = I_BCryptIsoInitUtilitiesOnce();
    v2 = inited;
    if ( inited < 0 )
    {
      DebugTraceError(
        (unsigned int)inited,
        "secStatus",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        1034);
      goto LABEL_25;
    }
    v2 = I_BCryptIsoInitializeRpc();
    if ( v2 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids);
      goto LABEL_25;
    }
    v0 = 1;
    CanLaunchSecureProcess = I_BCryptIsoCanLaunchSecureProcess();
    v5 = RpcRevertToSelf();
    v11 = v5;
    if ( v5 )
    {
      v6 = 1064;
LABEL_16:
      DebugTraceError(v5, "rpcStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp", v6);
      v2 = -2146893792;
      goto LABEL_25;
    }
    v3 = 0;
    v7 = I_BCryptIsoLaunchKeyGuard();
    if ( v7 < 0 )
    {
      DebugTraceError(
        (unsigned int)v7,
        "ntStatus",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        1073);
LABEL_7:
      v2 = -2146893767;
      goto LABEL_25;
    }
    v5 = RpcImpersonateClient(0);
    v11 = v5;
    if ( v5 )
    {
      v6 = 1081;
      goto LABEL_16;
    }
    v8 = I_BCryptIsoInitializeRpc();
    v2 = v8;
    if ( v8 >= 0 )
      BCryptIsoRemoveAndInvalidateAllHandles();
    else
      DebugTraceError(
        (unsigned int)v8,
        "secStatus",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        1094);
    v3 = 1;
  }
LABEL_25:
  ReleaseSRWLockExclusive(&g_servicingLock);
  if ( !v3 )
    RpcImpersonateClient(0);
LABEL_27:
  KGT_LazyInit();
  if ( dword_18007A77C )
    KGT_TrackClient((struct KEYGUARD_TELEMETRY_GLOBAL *)qword_18007A780, v2, v9);
  if ( CanLaunchSecureProcess )
  {
    I_BCryptIsoCheckRpc(&v11);
    KeyGuardTelemetryReportCurrentState(0, v0, g_keyguardRegistryData, v11, v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800167fc  push    rbx
0x1800167fe  push    rbp
0x1800167ff  push    rsi
0x180016800  push    rdi
0x180016801  sub     rsp, 38h
0x180016805  xor     ecx, ecx
0x180016807  mov     [rsp+58h+arg_0], 0
0x18001680f  xor     ebp, ebp
0x180016811  xor     esi, esi
0x180016813  call    I_BCryptIsoCheckRpc
0x180016818  mov     ebx, eax
0x18001681a  test    eax, eax
0x18001681c  jns     loc_1800169E0
0x180016822  lea     rcx, ?g_servicingLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180016829  lea     edi, [rbp+1]
0x18001682c  call    cs:__imp_AcquireSRWLockExclusive
0x180016833  nop     dword ptr [rax+rax+00h]
0x180016838  xor     ecx, ecx
0x18001683a  call    I_BCryptIsoCheckRpc
0x18001683f  mov     ebx, eax
0x180016841  test    eax, eax
0x180016843  jns     loc_1800169BB
0x180016849  call    I_BCryptIsoUninitializeRpc
0x18001684e  call    ?BCryptIsoIsDisabledInRegistry@@YAHXZ; BCryptIsoIsDisabledInRegistry(void)
0x180016853  mov     cs:?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A, eax; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x180016859  test    eax, eax
0x18001685b  jz      short loc_180016893
0x18001685d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016864  lea     rax, WPP_GLOBAL_Control
0x18001686b  cmp     rcx, rax
0x18001686e  jz      short loc_180016889
0x180016870  test    byte ptr [rcx+1Ch], 8
0x180016874  jz      short loc_180016889
0x180016876  mov     rcx, [rcx+10h]
0x18001687a  lea     edx, [rbp+13h]
0x18001687d  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x180016884  call    WPP_SF_
0x180016889  mov     ebx, 80090039h
0x18001688e  jmp     loc_1800169BB
0x180016893  call    I_BCryptIsoInitUtilitiesOnce
0x180016898  mov     ebx, eax
0x18001689a  test    eax, eax
0x18001689c  jns     short loc_1800168BE
0x18001689e  mov     r9d, 40Ah
0x1800168a4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800168ab  lea     rdx, aSecstatus; "secStatus"
0x1800168b2  mov     ecx, eax
0x1800168b4  call    DebugTraceError
0x1800168b9  jmp     loc_1800169BB
0x1800168be  call    I_BCryptIsoInitializeRpc
0x1800168c3  mov     ebx, eax
0x1800168c5  test    eax, eax
0x1800168c7  js      short loc_180016904
0x1800168c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168d0  lea     rax, WPP_GLOBAL_Control
0x1800168d7  cmp     rcx, rax
0x1800168da  jz      loc_1800169BB
0x1800168e0  test    byte ptr [rcx+1Ch], 8
0x1800168e4  jz      loc_1800169BB
0x1800168ea  mov     rcx, [rcx+10h]
0x1800168ee  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x1800168f5  mov     edx, 14h
0x1800168fa  call    WPP_SF_
0x1800168ff  jmp     loc_1800169BB
0x180016904  mov     ebp, edi
0x180016906  call    I_BCryptIsoCanLaunchSecureProcess
0x18001690b  mov     esi, eax
0x18001690d  call    cs:__imp_RpcRevertToSelf
0x180016914  nop     dword ptr [rax+rax+00h]
0x180016919  mov     [rsp+58h+arg_0], eax
0x18001691d  test    eax, eax
0x18001691f  jz      short loc_180016943
0x180016921  mov     r9d, 428h
0x180016927  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001692e  mov     ecx, eax
0x180016930  lea     rdx, aRpcstatus; "rpcStatus"
0x180016937  call    DebugTraceError
0x18001693c  mov     ebx, 80090020h
0x180016941  jmp     short loc_1800169BB
0x180016943  xor     edi, edi
0x180016945  call    I_BCryptIsoLaunchKeyGuard
0x18001694a  test    eax, eax
0x18001694c  jns     short loc_18001696E
0x18001694e  mov     r9d, 431h
0x180016954  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001695b  lea     rdx, aNtstatus; "ntStatus"
0x180016962  mov     ecx, eax
0x180016964  call    DebugTraceError
0x180016969  jmp     loc_180016889
0x18001696e  xor     ecx, ecx; BindingHandle
0x180016970  call    cs:__imp_RpcImpersonateClient
0x180016977  nop     dword ptr [rax+rax+00h]
0x18001697c  mov     [rsp+58h+arg_0], eax
0x180016980  test    eax, eax
0x180016982  jz      short loc_18001698C
0x180016984  mov     r9d, 439h
0x18001698a  jmp     short loc_180016927
0x18001698c  call    I_BCryptIsoInitializeRpc
0x180016991  mov     ebx, eax
0x180016993  test    eax, eax
0x180016995  jns     short loc_1800169B4
0x180016997  mov     r9d, 446h
0x18001699d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800169a4  lea     rdx, aSecstatus; "secStatus"
0x1800169ab  mov     ecx, eax
0x1800169ad  call    DebugTraceError
0x1800169b2  jmp     short loc_1800169B9
0x1800169b4  call    ?BCryptIsoRemoveAndInvalidateAllHandles@@YAXXZ; BCryptIsoRemoveAndInvalidateAllHandles(void)
0x1800169b9  mov     edi, ebp
0x1800169bb  lea     rcx, ?g_servicingLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800169c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800169c9  nop     dword ptr [rax+rax+00h]
0x1800169ce  test    edi, edi
0x1800169d0  jnz     short loc_1800169E0
0x1800169d2  xor     ecx, ecx; BindingHandle
0x1800169d4  call    cs:__imp_RpcImpersonateClient
0x1800169db  nop     dword ptr [rax+rax+00h]
0x1800169e0  call    KGT_LazyInit
0x1800169e5  cmp     cs:dword_18007A77C, 0
0x1800169ec  jz      short loc_1800169FC
0x1800169ee  mov     edx, ebx; int
0x1800169f0  lea     rcx, qword_18007A780; struct KEYGUARD_TELEMETRY_GLOBAL *
0x1800169f7  call    ?KGT_TrackClient@@YAPEAUKEYGUARD_TELEMETRY_IMAGE_T@@PEAUKEYGUARD_TELEMETRY_GLOBAL@@JH@Z; KGT_TrackClient(KEYGUARD_TELEMETRY_GLOBAL *,long,int)
0x1800169fc  test    esi, esi
0x1800169fe  jz      short loc_180016A23
0x180016a00  lea     rcx, [rsp+58h+arg_0]
0x180016a05  call    I_BCryptIsoCheckRpc
0x180016a0a  mov     r9d, [rsp+58h+arg_0]; int
0x180016a0f  mov     edx, ebp; int
0x180016a11  mov     r8d, cs:?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A; int
0x180016a18  xor     ecx, ecx; unsigned __int8
0x180016a1a  mov     [rsp+58h+var_38], ebx; int
0x180016a1e  call    ?KeyGuardTelemetryReportCurrentState@@YAXEHHJJ@Z; KeyGuardTelemetryReportCurrentState(uchar,int,int,long,long)
0x180016a23  mov     eax, ebx
0x180016a25  add     rsp, 38h
0x180016a29  pop     rdi
0x180016a2a  pop     rsi
0x180016a2b  pop     rbp
0x180016a2c  pop     rbx
0x180016a2d  retn
```
