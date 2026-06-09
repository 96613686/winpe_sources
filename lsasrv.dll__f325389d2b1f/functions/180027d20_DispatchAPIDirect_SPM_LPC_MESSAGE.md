# DispatchAPIDirect(_SPM_LPC_MESSAGE *)

- ea: `0x180027d20`
- end: `0x1800283ce`
- name: `?DispatchAPIDirect@@YAJPEAU_SPM_LPC_MESSAGE@@@Z`
- size: `1710`
- prototype: `__int64 __fastcall(struct _SPM_LPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180023e90`
- `0x180027d20`
- `0x1800283d4`
- `0x18002844c`
- `0x1800284d4`
- `0x180028528`
- `0x18005608c`
- `0x180078ab0`
- `0x1800ada18`
- `0x1800b0084`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800ca010`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027dc0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027e63`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027e78`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027e98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002804f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800280c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027dc0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027e63`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027e78`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027e98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002804f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800280c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180027ed2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180027f06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002809a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800280af`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800280e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800283bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180027ed2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180027f06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002809a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800280af`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800280e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800283bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180027f46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002800b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180027f46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002800b`
- `ntdll!NtClose` at `0x1800282d2`
- `ntdll!NtClose` at `0x1800282d2`
- `ntdll!NtSetInformationThread` at `0x1800282bc`
- `ntdll!NtSetInformationThread` at `0x1800282bc`
- `ntdll!NtOpenThreadToken` at `0x180028258`
- `ntdll!NtOpenThreadToken` at `0x180028258`

## pseudocode

```c
__int64 __fastcall DispatchAPIDirect(struct _SPM_LPC_MESSAGE *a1)
{
  struct _LSAP_API_LOG *v2; // rdx
  struct _FILETIME *v3; // rdi
  __int64 v4; // r9
  int v5; // r8d
  unsigned int v6; // r10d
  _DWORD *Value; // r15
  bool v8; // zf
  int v9; // esi
  struct _Session *v10; // r13
  _DWORD *v11; // r15
  LsaHandleCache *v12; // rcx
  __int64 v13; // rdx
  const char *v14; // r8
  __int64 v15; // r8
  int (* near *v16)(struct _SPM_LPC_MESSAGE *); // rax
  unsigned int *v17; // rsi
  struct _FILETIME v18; // rax
  __int64 v19; // rdx
  void *v20; // rdi
  struct _Session *v21; // rdi
  int v23; // ecx
  NTSTATUS v24; // eax
  __int64 v25; // rdi
  __int64 v26; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _SPM_LPC_MESSAGE *TlsValue; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpTlsValue; // [rsp+48h] [rbp-B8h]
  char *v31; // [rsp+50h] [rbp-B0h]
  int UniqueProcess; // [rsp+58h] [rbp-A8h]
  int UniqueThread; // [rsp+5Ch] [rbp-A4h]
  int v34; // [rsp+60h] [rbp-A0h]
  int v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+84h] [rbp-7Ch]
  int v37; // [rsp+158h] [rbp+58h]
  void *DsaThreadState; // [rsp+190h] [rbp+90h]
  void *v39; // [rsp+198h] [rbp+98h]
  LPVOID v40; // [rsp+1A0h] [rbp+A0h]
  LPVOID v41; // [rsp+1A8h] [rbp+A8h]
  LPVOID v42; // [rsp+1B0h] [rbp+B0h]

  memset_0(&TlsValue, 0, 0x1E8u);
  v2 = InternalApiLog;
  *((_DWORD *)a1 + 6) = _InterlockedIncrement(&InternalMessageId);
  v3 = 0;
  if ( v2 )
  {
    v4 = *((unsigned int *)v2 + 1);
    v5 = 2 * *(_DWORD *)v2;
    if ( *((_DWORD *)v2 + 18 * v4 + 5) )
    {
      do
      {
        v6 = v4;
        if ( *((_DWORD *)v2 + 18 * (unsigned int)v4 + 5) == -1 )
          break;
        if ( !v5 )
          goto LABEL_5;
        --v5;
        v26 = *((_DWORD *)v2 + 2) & (unsigned int)(v4 + 1);
        v6 = v26;
        LODWORD(v4) = *((_DWORD *)v2 + 2) & (v4 + 1);
        *((_DWORD *)v2 + 1) = v26;
      }
      while ( *((_DWORD *)v2 + 18 * v26 + 5) );
    }
    else
    {
      v6 = *((_DWORD *)v2 + 1);
    }
    if ( v5 )
    {
      v25 = v6 + 8LL * v6 + 2;
      *((_DWORD *)v2 + 2 * v25 + 1) = 0;
      v3 = (struct _FILETIME *)((char *)v2 + 8 * v25);
      *((_DWORD *)v2 + 1) = *((_DWORD *)v2 + 2) & (*((_DWORD *)v2 + 1) + 1);
    }
  }
LABEL_5:
  Value = TlsGetValue(dwCallInfo);
  memset_0(&TlsValue, 0, 0x1E8u);
  v35 = 1;
  UniqueProcess = (int)NtCurrentTeb()->ClientId.UniqueProcess;
  v8 = *((_DWORD *)a1 + 10) == 1;
  UniqueThread = (int)NtCurrentTeb()->ClientId.UniqueThread;
  if ( v8 && *(_WORD *)a1 == 200 )
    v36 = *((_DWORD *)a1 + 21);
  v9 = LsapCheckCallerSuppliedCallFlags((struct _LSA_CALL_INFO *)&TlsValue);
  if ( v9 < 0 )
    return (unsigned int)v9;
  TlsValue = a1;
  if ( Value )
  {
    if ( Value[16] )
    {
      if ( *(_QWORD *)Value )
      {
        v23 = *((_DWORD *)a1 + 10);
        if ( *(_DWORD *)(*(_QWORD *)Value + 40LL) == v23 && v23 == 1 )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids);
          }
          v34 |= 8u;
        }
      }
    }
  }
  v10 = pDefaultSession;
  lpTlsValue = pDefaultSession;
  TokenHandle = 0;
  v11 = TlsGetValue(dwCallInfo);
  v42 = TlsGetValue(dwSession);
  v40 = v11;
  v41 = TlsGetValue(dwThreadPackage);
  DsaThreadState = 0;
  if ( v35 || (v9 = 0, v11) && (v11[17] & 0x40000) != 0 )
  {
    v24 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x1Cu, 1u, &TokenHandle);
    v9 = v24;
    if ( v24 == -1073741700 )
    {
      v9 = 0;
      TokenHandle = 0;
    }
    else if ( v24 < 0 )
    {
      goto LABEL_13;
    }
    if ( GetDsaThreadState )
      DsaThreadState = GetDsaThreadState();
  }
  TlsSetValue(dwCallInfo, &TlsValue);
  v39 = TokenHandle;
  if ( lpTlsValue )
  {
    _InterlockedIncrement((volatile signed __int32 *)lpTlsValue + 36);
    TlsSetValue(dwSession, lpTlsValue);
  }
  v37 = 1;
LABEL_13:
  if ( v9 < 0 )
    return (unsigned int)v9;
  if ( v3 )
  {
    v3->dwHighDateTime = GetCurrentThreadId();
    v31 = (char *)&v3[6];
    GetSystemTimeAsFileTime(v3 + 4);
  }
  else
  {
    v31 = 0;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v13 = *((int *)a1 + 10);
    if ( (unsigned int)(v13 + 2) >= 0x1E )
      v14 = "[Illegal API Number!]";
    else
      v14 = off_180150800[v13];
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (_DWORD)v14,
      *((_DWORD *)v10 + 4),
      (__int64)v14,
      *((_DWORD *)a1 + 10));
    v12 = WPP_GLOBAL_Control;
  }
  v15 = *((int *)a1 + 10);
  if ( (unsigned int)v15 <= 0x1A && (v16 = (&LpcDispatchTable)[v15]) != 0 )
  {
    ((void (__fastcall *)(struct _SPM_LPC_MESSAGE *))v16)(a1);
    v17 = (unsigned int *)((char *)a1 + 44);
  }
  else
  {
    if ( v12 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)v12 + 2),
        47,
        WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids,
        *((unsigned int *)v10 + 4),
        v15);
    *((_WORD *)a1 + 24) |= 1u;
    v17 = (unsigned int *)((char *)a1 + 44);
    *((_DWORD *)a1 + 11) = -2146893054;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids,
      *((unsigned int *)v10 + 4),
      *v17);
  if ( v3 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v3[5] = (struct _FILETIME)v3->dwHighDateTime;
    v3[2] = (struct _FILETIME)*v17;
    v3[1] = (struct _FILETIME)*((int *)a1 + 10);
    v18 = SystemTimeAsFileTime;
    v3[3] = SystemTimeAsFileTime;
    v3[4] = (struct _FILETIME)(*(_QWORD *)&v18 - *(_QWORD *)&v3[4]);
    v3->dwHighDateTime = -1;
  }
  SystemTimeAsFileTime = 0;
  if ( TlsGetValue(dwCallInfo) != &TlsValue )
    MicrosoftTelemetryAssertTriggeredNoArgs(&TlsValue, v19);
  if ( v37 )
  {
    v20 = v40;
    if ( v35 || v40 && (*((_DWORD *)v40 + 17) & 0x40000) != 0 )
    {
      SystemTimeAsFileTime = (struct _FILETIME)v39;
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &SystemTimeAsFileTime, 8u);
      if ( SystemTimeAsFileTime )
      {
        NtClose(*(HANDLE *)&SystemTimeAsFileTime);
        v39 = 0;
      }
      if ( DsaThreadState )
      {
        ((void (*)(void))RestoreDsaThreadState)();
        DsaThreadState = 0;
      }
    }
    TlsSetValue(dwThreadPackage, v41);
    TlsSetValue(dwCallInfo, v20);
    v40 = 0;
    v21 = (struct _Session *)TlsGetValue(dwSession);
    TlsSetValue(dwSession, v42);
    v42 = 0;
    if ( v21 )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)v21 + 36) < 0 )
      {
        if ( v21 == pDefaultSession )
          *((_DWORD *)v21 + 36) = 1;
        else
          I_DeleteSession((struct _RTL_BALANCED_NODE *)v21);
      }
      lpTlsValue = 0;
    }
    v37 = 0;
  }
  else
  {
    TlsSetValue(dwCallInfo, 0);
  }
  LsapFreeCallInfo((struct _LSA_CALL_INFO *)&TlsValue);
  return 0;
}

```

## disassembly

```asm
0x180027d20  mov     [rsp-8+arg_18], rbx
0x180027d25  push    rbp
0x180027d26  push    rsi
0x180027d27  push    rdi
0x180027d28  push    r14
0x180027d2a  push    r15
0x180027d2c  lea     rbp, [rsp-140h]
0x180027d34  sub     rsp, 240h
0x180027d3b  mov     rax, cs:__security_cookie
0x180027d42  xor     rax, rsp
0x180027d45  mov     [rbp+160h+var_30], rax
0x180027d4c  mov     r14, rcx
0x180027d4f  xor     edx, edx; Val
0x180027d51  lea     rcx, [rsp+260h+TlsValue]; void *
0x180027d56  mov     r8d, 1E8h; Size
0x180027d5c  call    memset_0
0x180027d61  mov     eax, 1
0x180027d66  lock xadd cs:?InternalMessageId@@3JA, eax; long InternalMessageId
0x180027d6e  mov     rdx, cs:?InternalApiLog@@3PEAU_LSAP_API_LOG@@EA; _LSAP_API_LOG * InternalApiLog
0x180027d75  inc     eax
0x180027d77  xor     ebx, ebx
0x180027d79  mov     [r14+18h], eax
0x180027d7d  mov     edi, ebx
0x180027d7f  test    rdx, rdx
0x180027d82  jz      short loc_180027DBA
0x180027d84  mov     r9d, [rdx+4]
0x180027d88  mov     r8d, [rdx]
0x180027d8b  add     r8d, r8d
0x180027d8e  lea     rax, [r9+r9*8]
0x180027d92  cmp     [rdx+rax*8+14h], ebx
0x180027d96  jz      loc_18002830D
0x180027d9c  mov     eax, r9d
0x180027d9f  mov     r10d, r9d
0x180027da2  lea     rcx, [rax+rax*8]
0x180027da6  cmp     dword ptr [rdx+rcx*8+14h], 0FFFFFFFFh
0x180027dab  jz      loc_180028310
0x180027db1  test    r8d, r8d
0x180027db4  jnz     loc_18002835E
0x180027dba  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x180027dc0  call    cs:__imp_TlsGetValue
0x180027dc7  nop     dword ptr [rax+rax+00h]
0x180027dcc  xor     edx, edx; Val
0x180027dce  lea     rcx, [rsp+260h+TlsValue]; void *
0x180027dd3  mov     r8d, 1E8h; Size
0x180027dd9  mov     r15, rax
0x180027ddc  call    memset_0
0x180027de1  mov     [rbp+160h+var_1E0], 1
0x180027de8  mov     rcx, gs:30h
0x180027df1  mov     edx, [rcx+40h]
0x180027df4  mov     [rsp+260h+var_208], edx
0x180027df8  mov     rcx, gs:30h
0x180027e01  cmp     dword ptr [r14+28h], 1
0x180027e06  mov     edx, [rcx+48h]
0x180027e09  mov     [rsp+260h+var_204], edx
0x180027e0d  jz      loc_1800281B1
0x180027e13  mov     [rsp+260h+arg_8], r12
0x180027e1b  lea     rcx, [rsp+260h+TlsValue]; struct _LSA_CALL_INFO *
0x180027e20  mov     [rsp+260h+arg_10], r13
0x180027e28  call    ?LsapCheckCallerSuppliedCallFlags@@YAJPEAU_LSA_CALL_INFO@@@Z; LsapCheckCallerSuppliedCallFlags(_LSA_CALL_INFO *)
0x180027e2d  mov     esi, eax
0x180027e2f  test    eax, eax
0x180027e31  js      loc_180028391
0x180027e37  mov     [rsp+260h+TlsValue], r14
0x180027e3c  lea     r12, WPP_GLOBAL_Control
0x180027e43  test    r15, r15
0x180027e46  jnz     loc_1800281CC
0x180027e4c  mov     r13, cs:?pDefaultSession@@3PEAU_Session@@EA; _Session * pDefaultSession
0x180027e53  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x180027e59  mov     [rsp+260h+lpTlsValue], r13
0x180027e5e  mov     [rsp+260h+TokenHandle], rbx
0x180027e63  call    cs:__imp_TlsGetValue
0x180027e6a  nop     dword ptr [rax+rax+00h]
0x180027e6f  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x180027e75  mov     r15, rax
0x180027e78  call    cs:__imp_TlsGetValue
0x180027e7f  nop     dword ptr [rax+rax+00h]
0x180027e84  mov     ecx, cs:?dwThreadPackage@@3KA; dwTlsIndex
0x180027e8a  mov     [rbp+160h+var_B0], rax
0x180027e91  mov     [rbp+160h+var_C0], r15
0x180027e98  call    cs:__imp_TlsGetValue
0x180027e9f  nop     dword ptr [rax+rax+00h]
0x180027ea4  cmp     [rbp+160h+var_1E0], 0
0x180027ea8  mov     [rbp+160h+var_B8], rax
0x180027eaf  mov     [rbp+160h+var_D0], rbx
0x180027eb6  jnz     loc_180028244
0x180027ebc  mov     esi, ebx
0x180027ebe  test    r15, r15
0x180027ec1  jnz     loc_180028398
0x180027ec7  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x180027ecd  lea     rdx, [rsp+260h+TlsValue]; lpTlsValue
0x180027ed2  call    cs:__imp_TlsSetValue
0x180027ed9  nop     dword ptr [rax+rax+00h]
0x180027ede  mov     rax, [rsp+260h+TokenHandle]
0x180027ee3  mov     [rbp+160h+var_C8], rax
0x180027eea  mov     rax, [rsp+260h+lpTlsValue]
0x180027eef  test    rax, rax
0x180027ef2  jz      short loc_180027F12
0x180027ef4  lock inc dword ptr [rax+90h]
0x180027efb  mov     rdx, [rsp+260h+lpTlsValue]; lpTlsValue
0x180027f00  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x180027f06  call    cs:__imp_TlsSetValue
0x180027f0d  nop     dword ptr [rax+rax+00h]
0x180027f12  mov     [rbp+160h+var_108], 1
0x180027f19  test    esi, esi
0x180027f1b  js      loc_180028391
0x180027f21  test    rdi, rdi
0x180027f24  jz      loc_18002815D
0x180027f2a  call    cs:__imp_GetCurrentThreadId
0x180027f31  nop     dword ptr [rax+rax+00h]
0x180027f36  mov     [rdi+4], eax
0x180027f39  lea     rcx, [rdi+20h]; lpSystemTimeAsFileTime
0x180027f3d  lea     rax, [rdi+30h]
0x180027f41  mov     [rsp+260h+var_210], rax
0x180027f46  call    cs:__imp_GetSystemTimeAsFileTime
0x180027f4d  nop     dword ptr [rax+rax+00h]
0x180027f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f59  lea     rsi, __ImageBase
0x180027f60  cmp     rcx, r12
0x180027f63  jz      short loc_180027FA0
0x180027f65  test    byte ptr [rcx+1Ch], 4
0x180027f69  jz      short loc_180027FA0
0x180027f6b  movsxd  rdx, dword ptr [r14+28h]
0x180027f6f  lea     eax, [rdx+2]
0x180027f72  cmp     eax, 1Eh
0x180027f75  jnb     loc_180028167
0x180027f7b  mov     r8, ds:rva off_180150800[rsi+rdx*8]; "LsaLookupPackage" ...
0x180027f83  mov     r9d, [r13+10h]
0x180027f87  mov     rcx, [rcx+10h]
0x180027f8b  mov     [rsp+260h+var_238], edx
0x180027f8f  mov     [rsp+260h+var_240], r8
0x180027f94  call    WPP_SF_Dsd
0x180027f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fa0  movsxd  r8, dword ptr [r14+28h]
0x180027fa4  cmp     r8d, 1Ah
0x180027fa8  ja      loc_180028173
0x180027fae  mov     rax, ds:(?LpcDispatchTable@@3PAP6AJPEAU_SPM_LPC_MESSAGE@@@ZA - 180000000h)[rsi+r8*8]; long (*near * LpcDispatchTable)(_SPM_LPC_MESSAGE *)
0x180027fb6  test    rax, rax
0x180027fb9  jz      loc_180028173
0x180027fbf  mov     rcx, r14; struct _SPM_LPC_MESSAGE *
0x180027fc2  call    _guard_dispatch_icall$thunk$10345483385596137414; LpcLsaCallPackage(_SPM_LPC_MESSAGE *)
0x180027fc7  lea     rsi, [r14+2Ch]
0x180027fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fd2  cmp     rcx, r12
0x180027fd5  jz      short loc_180027FFC
0x180027fd7  test    byte ptr [rcx+1Ch], 4
0x180027fdb  jz      short loc_180027FFC
0x180027fdd  mov     eax, [rsi]
0x180027fdf  lea     r8, WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids
0x180027fe6  mov     r9d, [r13+10h]
0x180027fea  mov     edx, 30h ; '0'
0x180027fef  mov     rcx, [rcx+10h]
0x180027ff3  mov     dword ptr [rsp+260h+var_240], eax
0x180027ff7  call    WPP_SF_Dd
0x180027ffc  test    rdi, rdi
0x180027fff  jz      short loc_180028044
0x180028001  lea     rcx, [rsp+260h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180028006  mov     qword ptr [rsp+260h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18002800b  call    cs:__imp_GetSystemTimeAsFileTime
0x180028012  nop     dword ptr [rax+rax+00h]
0x180028017  mov     eax, [rdi+4]
0x18002801a  mov     [rdi+28h], rax
0x18002801e  mov     eax, [rsi]
0x180028020  mov     [rdi+10h], rax
0x180028024  movsxd  rax, dword ptr [r14+28h]
0x180028028  mov     [rdi+8], rax
0x18002802c  mov     rax, qword ptr [rsp+260h+SystemTimeAsFileTime.dwLowDateTime]
0x180028031  mov     [rdi+18h], rax
0x180028035  sub     rax, [rdi+20h]
0x180028039  mov     [rdi+20h], rax
0x18002803d  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x180028044  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18002804a  mov     qword ptr [rsp+260h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18002804f  call    cs:__imp_TlsGetValue
0x180028056  nop     dword ptr [rax+rax+00h]
0x18002805b  lea     rcx, [rsp+260h+TlsValue]
0x180028060  cmp     rax, rcx
0x180028063  jnz     loc_1800283AB
0x180028069  cmp     [rbp+160h+var_108], 0
0x18002806d  jz      loc_1800283B5
0x180028073  cmp     [rbp+160h+var_1E0], 0
0x180028077  mov     rdi, [rbp+160h+var_C0]
0x18002807e  jnz     loc_180028299
0x180028084  test    rdi, rdi
0x180028087  jnz     loc_18002834C
0x18002808d  mov     rdx, [rbp+160h+var_B8]; lpTlsValue
0x180028094  mov     ecx, cs:?dwThreadPackage@@3KA; dwTlsIndex
0x18002809a  call    cs:__imp_TlsSetValue
0x1800280a1  nop     dword ptr [rax+rax+00h]
0x1800280a6  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x1800280ac  mov     rdx, rdi; lpTlsValue
0x1800280af  call    cs:__imp_TlsSetValue
0x1800280b6  nop     dword ptr [rax+rax+00h]
0x1800280bb  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x1800280c1  mov     [rbp+160h+var_C0], rbx
0x1800280c8  call    cs:__imp_TlsGetValue
0x1800280cf  nop     dword ptr [rax+rax+00h]
0x1800280d4  mov     rdx, [rbp+160h+var_B0]; lpTlsValue
0x1800280db  mov     rdi, rax
0x1800280de  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x1800280e4  call    cs:__imp_TlsSetValue
0x1800280eb  nop     dword ptr [rax+rax+00h]
0x1800280f0  mov     [rbp+160h+var_B0], rbx
0x1800280f7  test    rdi, rdi
0x1800280fa  jz      short loc_180028117
0x1800280fc  mov     ecx, 0FFFFFFFFh
0x180028101  lock xadd [rdi+90h], ecx
0x180028109  cmp     ecx, 1
0x18002810c  js      loc_18002822A
0x180028112  mov     [rsp+260h+lpTlsValue], rbx
0x180028117  mov     [rbp+160h+var_108], ebx
0x18002811a  lea     rcx, [rsp+260h+TlsValue]; struct _LSA_CALL_INFO *
0x18002811f  call    ?LsapFreeCallInfo@@YAXPEAU_LSA_CALL_INFO@@@Z; LsapFreeCallInfo(_LSA_CALL_INFO *)
0x180028124  xor     eax, eax
0x180028126  mov     r13, [rsp+260h+arg_10]
0x18002812e  mov     r12, [rsp+260h+arg_8]
0x180028136  mov     rcx, [rbp+160h+var_30]
0x18002813d  xor     rcx, rsp; StackCookie
0x180028140  call    __security_check_cookie
0x180028145  mov     rbx, [rsp+260h+arg_18]
0x18002814d  add     rsp, 240h
0x180028154  pop     r15
0x180028156  pop     r14
0x180028158  pop     rdi
0x180028159  pop     rsi
0x18002815a  pop     rbp
0x18002815b  retn
0x18002815d  mov     [rsp+260h+var_210], rbx
0x180028162  jmp     loc_180027F52
0x180028167  lea     r8, aIllegalApiNumb; "[Illegal API Number!]"
0x18002816e  jmp     loc_180027F83
0x180028173  cmp     rcx, r12
0x180028176  jz      short loc_18002819C
0x180028178  test    byte ptr [rcx+1Ch], 1
0x18002817c  jz      short loc_18002819C
0x18002817e  mov     r9d, [r13+10h]
0x180028182  mov     edx, 2Fh ; '/'
0x180028187  mov     rcx, [rcx+10h]
0x18002818b  mov     dword ptr [rsp+260h+var_240], r8d
0x180028190  lea     r8, WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids
0x180028197  call    WPP_SF_Dd
0x18002819c  or      word ptr [r14+30h], 1
0x1800281a2  lea     rsi, [r14+2Ch]
0x1800281a6  mov     dword ptr [rsi], 80090302h
0x1800281ac  jmp     loc_180027FCB
0x1800281b1  mov     eax, 0C8h
0x1800281b6  cmp     [r14], ax
0x1800281ba  jnz     loc_180027E13
0x1800281c0  mov     eax, [r14+54h]
0x1800281c4  mov     [rbp+160h+var_1DC], eax
0x1800281c7  jmp     loc_180027E13
0x1800281cc  cmp     dword ptr [r15+40h], 0
0x1800281d1  jz      loc_180027E4C
0x1800281d7  mov     rax, [r15]
0x1800281da  test    rax, rax
0x1800281dd  jz      loc_180027E4C
0x1800281e3  mov     ecx, [r14+28h]
0x1800281e7  cmp     [rax+28h], ecx
0x1800281ea  jnz     loc_180027E4C
0x1800281f0  cmp     ecx, 1
0x1800281f3  jnz     loc_180027E4C
0x1800281f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180028200  cmp     rcx, r12
0x180028203  jz      short loc_180028220
0x180028205  test    byte ptr [rcx+1Ch], 1
0x180028209  jz      short loc_180028220
0x18002820b  mov     rcx, [rcx+10h]
0x18002820f  lea     r8, WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids
0x180028216  mov     edx, 2Dh ; '-'
0x18002821b  call    WPP_SF_
0x180028220  or      [rsp+260h+var_200], 8
0x180028225  jmp     loc_180027E4C
0x18002822a  cmp     rdi, cs:?pDefaultSession@@3PEAU_Session@@EA; _Session * pDefaultSession
0x180028231  jz      loc_180028382
0x180028237  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x18002823a  call    ?I_DeleteSession@@YAJPEAU_Session@@@Z; I_DeleteSession(_Session *)
0x18002823f  jmp     loc_180028112
0x180028244  lea     r9, [rsp+260h+TokenHandle]; TokenHandle
0x180028249  mov     r8b, 1; OpenAsSelf
0x18002824c  mov     edx, 1Ch; DesiredAccess
0x180028251  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180028258  call    cs:__imp_NtOpenThreadToken
0x18002825f  nop     dword ptr [rax+rax+00h]
0x180028264  mov     esi, eax
0x180028266  cmp     eax, 0C000007Ch
0x18002826b  jnz     loc_18002833F
0x180028271  mov     esi, ebx
0x180028273  mov     [rsp+260h+TokenHandle], rbx
0x180028278  mov     rax, cs:?GetDsaThreadState@@3P6APEAXXZEA; void * (*GetDsaThreadState)(void)
0x18002827f  test    rax, rax
0x180028282  jz      loc_180027EC7
0x180028288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002828d  mov     [rbp+160h+var_D0], rax
0x180028294  jmp     loc_180027EC7
0x180028299  mov     rax, [rbp+160h+var_C8]
0x1800282a0  lea     r8, [rsp+260h+SystemTimeAsFileTime]; ThreadInformation
0x1800282a5  mov     r9d, 8; ThreadInformationLength
0x1800282ab  mov     qword ptr [rsp+260h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800282b0  mov     edx, 5; ThreadInformationClass
0x1800282b5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800282bc  call    cs:__imp_NtSetInformationThread
  ... truncated ...
```
