# RasEapCreateConnectionProperties

- ea: `0x180004ac0`
- end: `0x180004de8`
- name: `RasEapCreateConnectionProperties`
- size: `808`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003bd0`
- `0x1800047a0`
- `0x180004ac0`
- `0x180005df0`
- `0x180027010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180004b56`
- `ntdll!NtQueryInformationToken` at `0x180004b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004aeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004aeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004bf4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d6d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004b26`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004b26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004b13`
- `rtutils!TraceDeregisterExA` at `0x180004c1f`
- `rtutils!TraceDeregisterExA` at `0x180004c1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RasEapCreateConnectionProperties(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        struct _EAPMSCHAPv2_CONN_PROPERTIES *a4,
        unsigned int a5,
        struct _EAPMSCHAPv2_CONN_PROPERTIES **a6,
        unsigned int *a7)
{
  BOOL v11; // edi
  HANDLE CurrentProcess; // rax
  _QWORD *v13; // rcx
  struct _EAPMSCHAPv2_CONN_PROPERTIES **v14; // rbx
  unsigned int ConnectionProperties; // edi
  int v16; // eax
  unsigned int *v18; // rsi
  unsigned int v19; // ebp
  LPVOID v20; // rcx
  ULONG ReturnLength; // [rsp+30h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-60h] BYREF
  void *TokenHandle[11]; // [rsp+40h] [rbp-58h] BYREF
  int TokenInformation; // [rsp+A0h] [rbp+8h] BYREF

  ppv = 0;
  EnterCriticalSection(&g_criticalSection);
  if ( !g_dwDebuggingRefCount )
  {
    TokenHandle[0] = 0;
    ReturnLength = 0;
    TokenInformation = 0;
    v11 = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    {
      if ( NtQueryInformationToken(TokenHandle[0], TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) >= 0 )
        v11 = TokenInformation != 0;
    }
    else
    {
      GetLastError();
    }
    if ( TokenHandle[0] )
      CloseHandle(TokenHandle[0]);
    if ( !v11 )
      DebugInitEx();
  }
  ++g_dwDebuggingRefCount;
  LeaveCriticalSection(&g_criticalSection);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    v13 = WPP_GLOBAL_Control;
  }
  if ( a1 == 26 )
  {
    v14 = a6;
    if ( a6 && (v18 = a7) != 0 && a3 )
    {
      ConnectionProperties = 0;
      *a6 = 0;
      *v18 = 0;
      TokenHandle[0] = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)a3 + 192LL))(
              a3,
              0xFFFFFFFFLL,
              TokenHandle);
      if ( !v19 )
      {
        v20 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v19 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
        if ( !v19 )
          v19 = (*(__int64 (__fastcall **)(LPVOID, void *, _QWORD))(*(_QWORD *)ppv + 168LL))(ppv, TokenHandle[0], 0);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v19);
      if ( TokenHandle[0] )
        (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle[0] + 16LL))(TokenHandle[0]);
      if ( !v19 )
        ConnectionProperties = MsChapV2CreateConnectionProperties(a2, (struct IXMLDOMDocument2 *)ppv, a4, a5, v14, v18);
    }
    else
    {
      ConnectionProperties = 160;
    }
  }
  else
  {
    if ( v13 != &WPP_GLOBAL_Control )
      WPP_SF_d(v13[2], 37, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    ConnectionProperties = 50;
  }
  EnterCriticalSection(&g_criticalSection);
  v16 = g_dwDebuggingRefCount;
  if ( !g_dwDebuggingRefCount || (--g_dwDebuggingRefCount, v16 == 1) )
  {
    if ( g_dwTraceId != -1 )
    {
      TraceDeregisterExA(g_dwTraceId, 4u);
      g_dwTraceId = -1;
    }
  }
  LeaveCriticalSection(&g_criticalSection);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return ConnectionProperties;
}

```

## disassembly

```asm
0x180004ac0  push    rbx
0x180004ac2  push    rbp
0x180004ac3  push    rsi
0x180004ac4  push    rdi
0x180004ac5  push    r12
0x180004ac7  push    r13
0x180004ac9  push    r14
0x180004acb  push    r15
0x180004acd  sub     rsp, 58h
0x180004ad1  mov     r15, r9
0x180004ad4  mov     r14, r8
0x180004ad7  mov     r12d, edx
0x180004ada  mov     ebx, ecx
0x180004adc  xor     r13d, r13d
0x180004adf  mov     [rsp+98h+ppv], r13
0x180004ae4  lea     rcx, g_criticalSection; lpCriticalSection
0x180004aeb  call    cs:__imp_EnterCriticalSection
0x180004af1  cmp     cs:g_dwDebuggingRefCount, r13d
0x180004af8  jnz     loc_180004B86
0x180004afe  mov     [rsp+98h+TokenHandle], r13
0x180004b03  mov     [rsp+98h+var_68], r13d
0x180004b08  mov     [rsp+98h+TokenInformation], r13d
0x180004b10  mov     edi, r13d
0x180004b13  call    cs:__imp_GetCurrentProcess
0x180004b19  mov     rcx, rax; ProcessHandle
0x180004b1c  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x180004b21  mov     edx, 8; DesiredAccess
0x180004b26  call    cs:__imp_OpenProcessToken
0x180004b2c  test    eax, eax
0x180004b2e  jz      loc_180004D34
0x180004b34  lea     rax, [rsp+98h+var_68]
0x180004b39  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180004b3e  mov     r9d, 4; TokenInformationLength
0x180004b44  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x180004b4c  mov     edx, 1Dh; TokenInformationClass
0x180004b51  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x180004b56  call    cs:__imp_NtQueryInformationToken
0x180004b5c  test    eax, eax
0x180004b5e  js      short loc_180004B6E
0x180004b60  cmp     [rsp+98h+TokenInformation], r13d
0x180004b68  jnz     loc_180004DA0
0x180004b6e  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x180004b73  test    rcx, rcx
0x180004b76  jz      short loc_180004B7E
0x180004b78  call    cs:__imp_CloseHandle
0x180004b7e  test    edi, edi
0x180004b80  jz      loc_180004D10
0x180004b86  inc     cs:g_dwDebuggingRefCount
0x180004b8c  lea     rcx, g_criticalSection; lpCriticalSection
0x180004b93  call    cs:__imp_LeaveCriticalSection
0x180004b99  lea     rax, WPP_GLOBAL_Control
0x180004ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ba7  cmp     rcx, rax
0x180004baa  jz      short loc_180004BD2
0x180004bac  mov     edx, 24h ; '$'
0x180004bb1  mov     r9d, ebx
0x180004bb4  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180004bbb  mov     rcx, [rcx+10h]
0x180004bbf  call    WPP_SF_d
0x180004bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bcb  lea     rax, WPP_GLOBAL_Control
0x180004bd2  cmp     ebx, 1Ah
0x180004bd5  jnz     loc_180004DAA
0x180004bdb  mov     rbx, [rsp+98h+arg_28]
0x180004be3  test    rbx, rbx
0x180004be6  jnz     short loc_180004C67
0x180004be8  mov     edi, 0A0h
0x180004bed  lea     rcx, g_criticalSection; lpCriticalSection
0x180004bf4  call    cs:__imp_EnterCriticalSection
0x180004bfa  mov     eax, cs:g_dwDebuggingRefCount
0x180004c00  test    eax, eax
0x180004c02  jz      short loc_180004C0F
0x180004c04  add     eax, 0FFFFFFFFh
0x180004c07  mov     cs:g_dwDebuggingRefCount, eax
0x180004c0d  jnz     short loc_180004C2F
0x180004c0f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180004c15  cmp     ecx, 0FFFFFFFFh
0x180004c18  jz      short loc_180004C2F
0x180004c1a  mov     edx, 4; dwFlags
0x180004c1f  call    cs:__imp_TraceDeregisterExA
0x180004c25  mov     cs:g_dwTraceId, 0FFFFFFFFh
0x180004c2f  lea     rcx, g_criticalSection; lpCriticalSection
0x180004c36  call    cs:__imp_LeaveCriticalSection
0x180004c3c  nop
0x180004c3d  mov     rcx, [rsp+98h+ppv]
0x180004c42  test    rcx, rcx
0x180004c45  jz      short loc_180004C54
0x180004c47  mov     rax, [rcx]
0x180004c4a  mov     rax, [rax+10h]
0x180004c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c53  nop
0x180004c54  mov     eax, edi
0x180004c56  add     rsp, 58h
0x180004c5a  pop     r15
0x180004c5c  pop     r14
0x180004c5e  pop     r13
0x180004c60  pop     r12
0x180004c62  pop     rdi
0x180004c63  pop     rsi
0x180004c64  pop     rbp
0x180004c65  pop     rbx
0x180004c66  retn
0x180004c67  mov     rsi, [rsp+98h+arg_30]
0x180004c6f  test    rsi, rsi
0x180004c72  jz      loc_180004BE8
0x180004c78  test    r14, r14
0x180004c7b  jz      loc_180004BE8
0x180004c81  mov     edi, r13d
0x180004c84  mov     [rbx], r13
0x180004c87  mov     [rsi], r13d
0x180004c8a  mov     [rsp+98h+TokenHandle], r13
0x180004c8f  mov     rax, [r14]
0x180004c92  mov     edx, 0FFFFFFFFh
0x180004c97  lea     r8, [rsp+98h+TokenHandle]
0x180004c9c  mov     rcx, r14
0x180004c9f  mov     rax, [rax+0C0h]
0x180004ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cab  mov     ebp, eax
0x180004cad  test    eax, eax
0x180004caf  jz      loc_180004D3F
0x180004cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cbc  lea     rax, WPP_GLOBAL_Control
0x180004cc3  cmp     rcx, rax
0x180004cc6  jnz     short loc_180004D1A
0x180004cc8  mov     rcx, [rsp+98h+TokenHandle]
0x180004ccd  test    rcx, rcx
0x180004cd0  jz      short loc_180004CDF
0x180004cd2  mov     rax, [rcx]
0x180004cd5  mov     rax, [rax+10h]
0x180004cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cde  nop
0x180004cdf  test    ebp, ebp
0x180004ce1  jnz     loc_180004BED
0x180004ce7  mov     [rsp+98h+var_70], rsi; unsigned int *
0x180004cec  mov     [rsp+98h+ReturnLength], rbx; struct _EAPMSCHAPv2_CONN_PROPERTIES **
0x180004cf1  mov     r9d, [rsp+98h+arg_20]; unsigned int
0x180004cf9  mov     r8, r15; struct _EAPMSCHAPv2_CONN_PROPERTIES *
0x180004cfc  mov     rdx, [rsp+98h+ppv]; struct IXMLDOMDocument2 *
0x180004d01  mov     ecx, r12d; unsigned int
0x180004d04  call    ?MsChapV2CreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@KPEAPEAU2@PEAK@Z; MsChapV2CreateConnectionProperties(ulong,IXMLDOMDocument2 *,_EAPMSCHAPv2_CONN_PROPERTIES *,ulong,_EAPMSCHAPv2_CONN_PROPERTIES * *,ulong *)
0x180004d09  mov     edi, eax
0x180004d0b  jmp     loc_180004BED
0x180004d10  call    DebugInitEx
0x180004d15  jmp     loc_180004B86
0x180004d1a  mov     edx, 3Ah ; ':'
0x180004d1f  mov     r9d, ebp
0x180004d22  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180004d29  mov     rcx, [rcx+10h]
0x180004d2d  call    WPP_SF_d
0x180004d32  jmp     short loc_180004CC8
0x180004d34  call    cs:__imp_GetLastError
0x180004d3a  jmp     loc_180004B6E
0x180004d3f  mov     rcx, [rsp+98h+ppv]
0x180004d44  test    rcx, rcx
0x180004d47  jnz     loc_180004DD1
0x180004d4d  lea     rax, [rsp+98h+ppv]
0x180004d52  mov     [rsp+98h+ReturnLength], rax; ppv
0x180004d57  lea     r9, IID_IXMLDOMDocument2; riid
0x180004d5e  xor     edx, edx; pUnkOuter
0x180004d60  mov     r8d, 1; dwClsContext
0x180004d66  lea     rcx, CLSID_DOMDocument60; rclsid
0x180004d6d  call    cs:__imp_CoCreateInstance
0x180004d73  mov     ebp, eax
0x180004d75  test    eax, eax
0x180004d77  jnz     loc_180004CB5
0x180004d7d  mov     rcx, [rsp+98h+ppv]
0x180004d82  mov     rax, [rcx]
0x180004d85  xor     r8d, r8d
0x180004d88  mov     rdx, [rsp+98h+TokenHandle]
0x180004d8d  mov     rax, [rax+0A8h]
0x180004d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d99  mov     ebp, eax
0x180004d9b  jmp     loc_180004CB5
0x180004da0  mov     edi, 1
0x180004da5  jmp     loc_180004B6E
0x180004daa  cmp     rcx, rax
0x180004dad  jz      short loc_180004DC7
0x180004daf  mov     edx, 25h ; '%'
0x180004db4  mov     r9d, ebx
0x180004db7  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180004dbe  mov     rcx, [rcx+10h]
0x180004dc2  call    WPP_SF_d
0x180004dc7  mov     edi, 32h ; '2'
0x180004dcc  jmp     loc_180004BED
0x180004dd1  mov     [rsp+98h+ppv], r13
0x180004dd6  mov     rax, [rcx]
0x180004dd9  mov     rax, [rax+10h]
0x180004ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de2  jmp     loc_180004D4D
```
