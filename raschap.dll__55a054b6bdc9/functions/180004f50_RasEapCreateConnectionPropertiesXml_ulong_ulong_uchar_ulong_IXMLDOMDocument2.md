# RasEapCreateConnectionPropertiesXml(ulong,ulong,uchar *,ulong,IXMLDOMDocument2 * *)

- ea: `0x180004f50`
- end: `0x180005424`
- name: `?RasEapCreateConnectionPropertiesXml@@YAKKKPEAEKPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1236`
- prototype: `unsigned int(unsigned int, unsigned int, unsigned __int8 *, unsigned int, struct IXMLDOMDocument2 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800014c0`
- `0x180003bd0`
- `0x1800047a0`
- `0x180004df0`
- `0x180004f50`
- `0x180005430`
- `0x180006a20`
- `0x1800147cc`
- `0x180025efc`
- `0x180027010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180004fea`
- `ntdll!NtQueryInformationToken` at `0x180004fea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005267`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000532d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005267`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000532d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000519a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000522a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000519a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000522a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005012`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000502e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005113`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000502e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005113`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050ad`
- `SspiCli!FreeContextBuffer` at `0x180005207`
- `SspiCli!FreeContextBuffer` at `0x180005207`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800051e9`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800051e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800053a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800053a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004fc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004fc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004fae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004fae`
- `rtutils!TraceDeregisterExA` at `0x1800050fc`
- `rtutils!TraceDeregisterExA` at `0x1800050fc`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x1800052b4`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x1800052b4`

## pseudocode

```c
__int64 __fastcall RasEapCreateConnectionPropertiesXml(
        unsigned int a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        LPVOID *ppv)
{
  struct _EAPMSCHAPv2_CONN_PROPERTIES *v7; // rbp
  SIZE_T v9; // r14
  BOOL v10; // edi
  HANDLE CurrentProcess; // rax
  _QWORD *v12; // rax
  unsigned int v13; // ebx
  int v14; // eax
  LPVOID *v16; // rdi
  struct _EAPMSCHAPv2_CONN_PROPERTIES *v17; // rax
  struct _EAPMSCHAPv2_CONN_PROPERTIES *v18; // rsi
  DWORD LastError; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // ebx
  struct _EAPMSCHAPv2_CONN_PROPERTIES *v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // ebx
  unsigned int Instance; // eax
  unsigned int v29; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-30h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  v9 = a4;
  EnterCriticalSection(&g_criticalSection);
  if ( !g_dwDebuggingRefCount )
  {
    TokenHandle = 0;
    v10 = 0;
    ReturnLength = 0;
    TokenInformation = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      if ( NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) >= 0 )
        v10 = TokenInformation != 0;
    }
    else
    {
      GetLastError();
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( !v10 )
      DebugInitEx();
  }
  ++g_dwDebuggingRefCount;
  LeaveCriticalSection(&g_criticalSection);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    v12 = WPP_GLOBAL_Control;
  }
  if ( a1 != 26 )
  {
    if ( v12 != &WPP_GLOBAL_Control )
      WPP_SF_d(v12[2], 29, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    v13 = 50;
    goto LABEL_19;
  }
  if ( a3 )
  {
    if ( !(_DWORD)v9 )
      goto LABEL_18;
  }
  else if ( (_DWORD)v9 )
  {
LABEL_18:
    v13 = 160;
    goto LABEL_19;
  }
  v16 = ppv;
  if ( !ppv )
    goto LABEL_18;
  if ( *ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 16LL))(*ppv);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control )
    WPP_SF_(v12[2], 10, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  if ( (unsigned int)v9 >= 8 && a3 )
  {
    v17 = (struct _EAPMSCHAPv2_CONN_PROPERTIES *)LocalAlloc(0x40u, v9);
    v18 = v17;
    if ( !v17 )
    {
      LastError = GetLastError();
      v13 = LastError;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_45;
      v21 = 14;
      goto LABEL_44;
    }
    memcpy_0(v17, a3, v9);
    TokenHandle = 0;
    if ( !QuerySecurityPackageInfoW((LPWSTR)L"NTLM", (PSecPkgInfoW *)&TokenHandle) )
    {
      if ( TokenHandle )
      {
        v22 = *(_DWORD *)TokenHandle;
        FreeContextBuffer(TokenHandle);
        if ( (v22 & 0x1000000) != 0 )
          *((_DWORD *)v18 + 1) &= ~2u;
      }
    }
LABEL_61:
    v7 = v18;
    LocalFree(0);
    goto LABEL_62;
  }
  v23 = (struct _EAPMSCHAPv2_CONN_PROPERTIES *)LocalAlloc(0x40u, 8u);
  v18 = v23;
  if ( v23 )
  {
    v27 = 0;
    *(_DWORD *)v23 = 1;
    if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
    {
      if ( !(unsigned int)RasChapExt_GetConfigForceNotDomainJoined() )
        v27 = isMachineJoinedToDomain();
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
    }
    if ( (a2 & 0x80u) != 0 && ((a2 & 0x20) != 0 || v27) && (unsigned int)IsLogonCredAllowed() )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
      *((_DWORD *)v18 + 1) = 2;
    }
    goto LABEL_61;
  }
  LastError = GetLastError();
  v13 = LastError;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_45;
  v21 = 11;
LABEL_44:
  WPP_SF_d(v20[2], v21, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, LastError);
LABEL_45:
  LocalFree(0);
  if ( v13 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_19;
    v25 = 30;
    v26 = v13;
    goto LABEL_48;
  }
LABEL_62:
  if ( *(_DWORD *)v7 != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, 26);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument3, v16);
  v13 = Instance;
  if ( Instance )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_19;
    v25 = 33;
    v26 = Instance;
LABEL_48:
    WPP_SF_d(v24[2], v25, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v26);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
  v29 = PopulateXMLDomFromMsChapBlob(a2, v7, (struct IXMLDOMDocument2 **)v16);
  v13 = v29;
  if ( v29 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v25 = 35;
      v26 = v29;
      goto LABEL_48;
    }
  }
LABEL_19:
  EnterCriticalSection(&g_criticalSection);
  v14 = g_dwDebuggingRefCount;
  if ( !g_dwDebuggingRefCount || (--g_dwDebuggingRefCount, v14 == 1) )
  {
    if ( g_dwTraceId != -1 )
    {
      TraceDeregisterExA(g_dwTraceId, 4u);
      g_dwTraceId = -1;
    }
  }
  LeaveCriticalSection(&g_criticalSection);
  if ( v7 )
    LocalFree(v7);
  return v13;
}

```

## disassembly

```asm
0x180004f50  mov     rax, rsp
0x180004f53  push    rbx
0x180004f54  push    rbp
0x180004f55  sub     rsp, 58h
0x180004f59  mov     [rax+10h], rsi
0x180004f5d  mov     rbx, r8
0x180004f60  mov     [rax+18h], rdi
0x180004f64  mov     esi, ecx
0x180004f66  mov     [rax+20h], r12
0x180004f6a  lea     rcx, g_criticalSection; lpCriticalSection
0x180004f71  mov     [rax-18h], r13
0x180004f75  xor     r13d, r13d
0x180004f78  mov     [rax-20h], r14
0x180004f7c  mov     ebp, r13d
0x180004f7f  mov     [rax-28h], r15
0x180004f83  mov     r15d, edx
0x180004f86  mov     r14d, r9d
0x180004f89  call    cs:__imp_EnterCriticalSection
0x180004f8f  cmp     cs:g_dwDebuggingRefCount, r13d
0x180004f96  jnz     loc_180005021
0x180004f9c  mov     [rsp+68h+TokenHandle], r13
0x180004fa1  mov     edi, r13d
0x180004fa4  mov     [rsp+68h+var_38], r13d
0x180004fa9  mov     [rsp+68h+TokenInformation], r13d
0x180004fae  call    cs:__imp_GetCurrentProcess
0x180004fb4  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180004fb9  mov     edx, 8; DesiredAccess
0x180004fbe  mov     rcx, rax; ProcessHandle
0x180004fc1  call    cs:__imp_OpenProcessToken
0x180004fc7  test    eax, eax
0x180004fc9  jz      short loc_180005002
0x180004fcb  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x180004fd0  lea     rax, [rsp+68h+var_38]
0x180004fd5  mov     r9d, 4; TokenInformationLength
0x180004fdb  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180004fe0  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x180004fe5  mov     edx, 1Dh; TokenInformationClass
0x180004fea  call    cs:__imp_NtQueryInformationToken
0x180004ff0  test    eax, eax
0x180004ff2  js      short loc_180005008
0x180004ff4  cmp     [rsp+68h+TokenInformation], r13d
0x180004ff9  jz      short loc_180005008
0x180004ffb  mov     edi, 1
0x180005000  jmp     short loc_180005008
0x180005002  call    cs:__imp_GetLastError
0x180005008  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18000500d  test    rcx, rcx
0x180005010  jz      short loc_180005018
0x180005012  call    cs:__imp_CloseHandle
0x180005018  test    edi, edi
0x18000501a  jnz     short loc_180005021
0x18000501c  call    DebugInitEx
0x180005021  inc     cs:g_dwDebuggingRefCount
0x180005027  lea     rcx, g_criticalSection; lpCriticalSection
0x18000502e  call    cs:__imp_LeaveCriticalSection
0x180005034  mov     rax, cs:WPP_GLOBAL_Control
0x18000503b  lea     r12, WPP_GLOBAL_Control
0x180005042  cmp     rax, r12
0x180005045  jz      short loc_180005066
0x180005047  mov     rcx, [rax+10h]
0x18000504b  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180005052  mov     edx, 1Ch
0x180005057  mov     r9d, esi
0x18000505a  call    WPP_SF_d
0x18000505f  mov     rax, cs:WPP_GLOBAL_Control
0x180005066  cmp     esi, 1Ah
0x180005069  jz      short loc_18000508F
0x18000506b  cmp     rax, r12
0x18000506e  jz      short loc_180005088
0x180005070  mov     rcx, [rax+10h]
0x180005074  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18000507b  mov     edx, 1Dh
0x180005080  mov     r9d, esi
0x180005083  call    WPP_SF_d
0x180005088  mov     ebx, 32h ; '2'
0x18000508d  jmp     short loc_1800050A6
0x18000508f  test    rbx, rbx
0x180005092  jnz     loc_180005130
0x180005098  test    r14d, r14d
0x18000509b  jz      loc_180005139
0x1800050a1  mov     ebx, 0A0h
0x1800050a6  lea     rcx, g_criticalSection; lpCriticalSection
0x1800050ad  call    cs:__imp_EnterCriticalSection
0x1800050b3  mov     eax, cs:g_dwDebuggingRefCount
0x1800050b9  mov     r15, [rsp+68h+var_28]
0x1800050be  mov     r14, [rsp+68h+var_20]
0x1800050c3  mov     r13, [rsp+68h+var_18]
0x1800050c8  mov     r12, [rsp+68h+arg_18]
0x1800050d0  mov     rdi, [rsp+68h+arg_10]
0x1800050d8  mov     rsi, [rsp+68h+arg_8]
0x1800050dd  test    eax, eax
0x1800050df  jz      short loc_1800050EC
0x1800050e1  add     eax, 0FFFFFFFFh
0x1800050e4  mov     cs:g_dwDebuggingRefCount, eax
0x1800050ea  jnz     short loc_18000510C
0x1800050ec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800050f2  cmp     ecx, 0FFFFFFFFh
0x1800050f5  jz      short loc_18000510C
0x1800050f7  mov     edx, 4; dwFlags
0x1800050fc  call    cs:__imp_TraceDeregisterExA
0x180005102  mov     cs:g_dwTraceId, 0FFFFFFFFh
0x18000510c  lea     rcx, g_criticalSection; lpCriticalSection
0x180005113  call    cs:__imp_LeaveCriticalSection
0x180005119  test    rbp, rbp
0x18000511c  jz      short loc_180005127
0x18000511e  mov     rcx, rbp; hMem
0x180005121  call    cs:__imp_LocalFree
0x180005127  mov     eax, ebx
0x180005129  add     rsp, 58h
0x18000512d  pop     rbp
0x18000512e  pop     rbx
0x18000512f  retn
0x180005130  test    r14d, r14d
0x180005133  jz      loc_1800050A1
0x180005139  mov     rdi, [rsp+68h+ppv]
0x180005141  test    rdi, rdi
0x180005144  jz      loc_1800050A1
0x18000514a  mov     rcx, [rdi]
0x18000514d  test    rcx, rcx
0x180005150  jz      short loc_180005165
0x180005152  mov     rax, [rcx]
0x180005155  mov     rax, [rax+10h]
0x180005159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000515e  mov     rax, cs:WPP_GLOBAL_Control
0x180005165  cmp     rax, r12
0x180005168  jz      short loc_18000517F
0x18000516a  mov     rcx, [rax+10h]
0x18000516e  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180005175  mov     edx, 0Ah
0x18000517a  call    WPP_SF_
0x18000517f  cmp     r14d, 8
0x180005183  jb      loc_180005220
0x180005189  test    rbx, rbx
0x18000518c  jz      loc_180005220
0x180005192  mov     rdx, r14; uBytes
0x180005195  mov     ecx, 40h ; '@'; uFlags
0x18000519a  call    cs:__imp_LocalAlloc
0x1800051a0  mov     rsi, rax
0x1800051a3  test    rax, rax
0x1800051a6  jnz     short loc_1800051CA
0x1800051a8  call    cs:__imp_GetLastError
0x1800051ae  mov     ebx, eax
0x1800051b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051b7  cmp     rcx, r12
0x1800051ba  jz      loc_180005264
0x1800051c0  mov     edx, 0Eh
0x1800051c5  jmp     loc_180005251
0x1800051ca  mov     r8, r14; Size
0x1800051cd  mov     rdx, rbx; Src
0x1800051d0  mov     rcx, rsi; void *
0x1800051d3  call    memcpy_0
0x1800051d8  lea     rdx, [rsp+68h+TokenHandle]; ppPackageInfo
0x1800051dd  mov     [rsp+68h+TokenHandle], r13
0x1800051e2  lea     rcx, pszPackageName; "NTLM"
0x1800051e9  call    cs:__imp_QuerySecurityPackageInfoW
0x1800051ef  test    eax, eax
0x1800051f1  jnz     loc_180005328
0x1800051f7  mov     rcx, [rsp+68h+TokenHandle]; pvContextBuffer
0x1800051fc  test    rcx, rcx
0x1800051ff  jz      loc_180005328
0x180005205  mov     ebx, [rcx]
0x180005207  call    cs:__imp_FreeContextBuffer
0x18000520d  bt      ebx, 18h
0x180005211  jnb     loc_180005328
0x180005217  and     dword ptr [rsi+4], 0FFFFFFFDh
0x18000521b  jmp     loc_180005328
0x180005220  mov     edx, 8; uBytes
0x180005225  mov     ecx, 40h ; '@'; uFlags
0x18000522a  call    cs:__imp_LocalAlloc
0x180005230  mov     rsi, rax
0x180005233  test    rax, rax
0x180005236  jnz     short loc_1800052A2
0x180005238  call    cs:__imp_GetLastError
0x18000523e  mov     ebx, eax
0x180005240  mov     rcx, cs:WPP_GLOBAL_Control
0x180005247  cmp     rcx, r12
0x18000524a  jz      short loc_180005264
0x18000524c  mov     edx, 0Bh
0x180005251  mov     rcx, [rcx+10h]
0x180005255  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x18000525c  mov     r9d, eax
0x18000525f  call    WPP_SF_d
0x180005264  mov     rcx, rsi; hMem
0x180005267  call    cs:__imp_LocalFree
0x18000526d  test    ebx, ebx
0x18000526f  jz      loc_180005333
0x180005275  mov     rcx, cs:WPP_GLOBAL_Control
0x18000527c  cmp     rcx, r12
0x18000527f  jz      loc_1800050A6
0x180005285  mov     edx, 1Eh
0x18000528a  mov     r9d, ebx
0x18000528d  mov     rcx, [rcx+10h]
0x180005291  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180005298  call    WPP_SF_d
0x18000529d  jmp     loc_1800050A6
0x1800052a2  mov     ebx, r13d
0x1800052a5  mov     dword ptr [rax], 1
0x1800052ab  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x1800052b0  test    al, al
0x1800052b2  jz      short loc_1800052C7
0x1800052b4  call    cs:__imp_RasChapExt_GetConfigForceNotDomainJoined
0x1800052ba  test    eax, eax
0x1800052bc  jnz     short loc_1800052E8
0x1800052be  call    isMachineJoinedToDomain
0x1800052c3  mov     ebx, eax
0x1800052c5  jmp     short loc_1800052E8
0x1800052c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052ce  cmp     rcx, r12
0x1800052d1  jz      short loc_1800052E8
0x1800052d3  mov     rcx, [rcx+10h]
0x1800052d7  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x1800052de  mov     edx, 0Ch
0x1800052e3  call    WPP_SF_
0x1800052e8  test    r15b, r15b
0x1800052eb  jns     short loc_180005328
0x1800052ed  test    r15b, 20h
0x1800052f1  jnz     short loc_1800052F7
0x1800052f3  test    ebx, ebx
0x1800052f5  jz      short loc_180005328
0x1800052f7  call    IsLogonCredAllowed
0x1800052fc  test    eax, eax
0x1800052fe  jz      short loc_180005328
0x180005300  mov     rcx, cs:WPP_GLOBAL_Control
0x180005307  cmp     rcx, r12
0x18000530a  jz      short loc_180005321
0x18000530c  mov     rcx, [rcx+10h]
0x180005310  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180005317  mov     edx, 0Dh
0x18000531c  call    WPP_SF_
0x180005321  mov     dword ptr [rsi+4], 2
0x180005328  xor     ecx, ecx; hMem
0x18000532a  mov     rbp, rsi
0x18000532d  call    cs:__imp_LocalFree
0x180005333  cmp     dword ptr [rbp+0], 1
0x180005337  jz      short loc_180005369
0x180005339  mov     rcx, cs:WPP_GLOBAL_Control
0x180005340  cmp     rcx, r12
0x180005343  jz      loc_1800050A1
0x180005349  mov     rcx, [rcx+10h]
0x18000534d  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180005354  mov     edx, 1Fh
0x180005359  mov     r9d, 1Ah
0x18000535f  call    WPP_SF_d
0x180005364  jmp     loc_1800050A1
0x180005369  mov     rcx, cs:WPP_GLOBAL_Control
0x180005370  cmp     rcx, r12
0x180005373  jz      short loc_18000538A
0x180005375  mov     rcx, [rcx+10h]
0x180005379  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180005380  mov     edx, 20h ; ' '
0x180005385  call    WPP_SF_
0x18000538a  lea     r9, IID_IXMLDOMDocument3; riid
0x180005391  mov     [rsp+68h+ReturnLength], rdi; ppv
0x180005396  xor     edx, edx; pUnkOuter
0x180005398  lea     rcx, CLSID_DOMDocument60; rclsid
0x18000539f  mov     r8d, 1; dwClsContext
0x1800053a5  call    cs:__imp_CoCreateInstance
0x1800053ab  mov     ebx, eax
0x1800053ad  test    eax, eax
0x1800053af  jz      short loc_1800053CE
0x1800053b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053b8  cmp     rcx, r12
0x1800053bb  jz      loc_1800050A6
0x1800053c1  mov     edx, 21h ; '!'
0x1800053c6  mov     r9d, eax
0x1800053c9  jmp     loc_18000528D
0x1800053ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053d5  cmp     rcx, r12
0x1800053d8  jz      short loc_1800053EF
0x1800053da  mov     rcx, [rcx+10h]
0x1800053de  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x1800053e5  mov     edx, 22h ; '"'
0x1800053ea  call    WPP_SF_
0x1800053ef  mov     r8, rdi; struct IXMLDOMDocument2 **
0x1800053f2  mov     rdx, rbp; struct _EAPMSCHAPv2_CONN_PROPERTIES *
0x1800053f5  mov     ecx, r15d; unsigned int
0x1800053f8  call    ?PopulateXMLDomFromMsChapBlob@@YAJKPEAU_EAPMSCHAPv2_CONN_PROPERTIES@@PEAPEAUIXMLDOMDocument2@@@Z; PopulateXMLDomFromMsChapBlob(ulong,_EAPMSCHAPv2_CONN_PROPERTIES *,IXMLDOMDocument2 * *)
0x1800053fd  mov     ebx, eax
0x1800053ff  test    eax, eax
0x180005401  jz      loc_1800050A6
0x180005407  mov     rcx, cs:WPP_GLOBAL_Control
0x18000540e  cmp     rcx, r12
0x180005411  jz      loc_1800050A6
0x180005417  mov     edx, 23h ; '#'
0x18000541c  mov     r9d, eax
0x18000541f  jmp     loc_18000528D
```
