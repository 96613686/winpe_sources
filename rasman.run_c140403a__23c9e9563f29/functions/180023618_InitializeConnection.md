# InitializeConnection

- ea: `0x180023618`
- end: `0x180023807`
- name: `InitializeConnection`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180022970`

## callees

- `0x180010cc0`
- `0x180022a50`
- `0x180023590`
- `0x1800235d4`
- `0x180023618`
- `0x180025f5c`
- `0x180025f98`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800237af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800237af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800236f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800236f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023704`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002367c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002367c`
- `RPCRT4!RpcBindingFree` at `0x1800237bb`
- `RPCRT4!RpcBindingFree` at `0x1800237bb`
- `rtutils!TracePrintfExA` at `0x180023798`
- `rtutils!TracePrintfExA` at `0x1800237df`
- `rtutils!TracePrintfExA` at `0x180023798`
- `rtutils!TracePrintfExA` at `0x1800237df`

## pseudocode

```c
__int64 __fastcall InitializeConnection(WCHAR *a1, _QWORD *a2)
{
  DWORD ServerVersion; // edi
  _DWORD *v5; // rsi
  int v6; // r14d
  __int64 v7; // rcx
  _DWORD *v8; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  int v10; // eax
  RPC_STATUS v11; // eax
  DWORD nSize; // [rsp+20h] [rbp-40h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-38h] BYREF
  int v15; // [rsp+30h] [rbp-30h] BYREF
  WCHAR Buffer[8]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v17; // [rsp+48h] [rbp-18h]

  nSize = 16;
  Binding = 0;
  v15 = 0;
  *(_OWORD *)Buffer = 0;
  v17 = 0;
  if ( !a2 )
    return (DWORD)-2147024809;
  v5 = 0;
  *a2 = 0;
  if ( !GetComputerNameW(Buffer, &nSize) )
    goto LABEL_14;
  if ( a1 )
  {
    if ( *a1 == 92 && a1[1] == 92 )
    {
      a1 += 2;
      goto LABEL_9;
    }
    if ( *a1 )
    {
LABEL_9:
      v6 = 0;
      if ( (unsigned int)CompareStringWrapW(a1, Buffer) )
        goto LABEL_11;
    }
  }
  v6 = 1;
  a1 = Buffer;
LABEL_11:
  ServerVersion = RasRPCBind(a1, &Binding);
  if ( ServerVersion )
    goto LABEL_15;
  ServerVersion = GetServerVersion(Binding, &v15);
  if ( ServerVersion )
    goto LABEL_15;
  v8 = LocalAlloc(0x40u, 0x30u);
  v5 = v8;
  if ( !v8 )
  {
LABEL_14:
    ServerVersion = GetLastError();
    if ( !ServerVersion )
      return ServerVersion;
    goto LABEL_15;
  }
  *(_QWORD *)v8 = Binding;
  v8[2] = v6;
  v10 = v15;
  if ( v6 )
    v10 = 6;
  v5[3] = v10;
  ServerVersion = StringCchCopyWrapW(v5 + 4, 16, a1);
  if ( ServerVersion )
  {
LABEL_15:
    if ( Binding )
    {
      if ( (Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_IsEnabledDeviceUsageNoInline(v7);
      if ( IsEnabledDeviceUsageNoInline )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "InitializeConnection: failed with error %#x", ServerVersion);
        RasRpcDisconnect(&Binding);
        if ( v5 )
          LocalFree(v5);
      }
      else
      {
        v11 = RpcBindingFree(&Binding);
        if ( v11 && g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "InitializeConnection: RpcBindingFree failed with error %#x", v11);
      }
    }
    return ServerVersion;
  }
  if ( (Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_featureState & 0x10) == 0 )
    Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_IsEnabledDeviceUsageNoInline(v7);
  *a2 = v5;
  return ServerVersion;
}

```

## disassembly

```asm
0x180023618  mov     [rsp-28h+arg_10], rbx
0x18002361d  push    rbp
0x18002361e  push    rsi
0x18002361f  push    rdi
0x180023620  push    r14
0x180023622  push    r15
0x180023624  mov     rbp, rsp
0x180023627  sub     rsp, 60h
0x18002362b  mov     rax, cs:__security_cookie
0x180023632  xor     rax, rsp
0x180023635  mov     [rbp+var_8], rax
0x180023639  mov     [rbp+nSize], 10h
0x180023640  xorps   xmm0, xmm0
0x180023643  mov     [rbp+Binding], 0
0x18002364b  mov     r15, rdx
0x18002364e  mov     [rbp+var_30], 0
0x180023655  mov     rbx, rcx
0x180023658  movups  xmmword ptr [rbp+Buffer], xmm0
0x18002365c  movups  [rbp+var_18], xmm0
0x180023660  test    rdx, rdx
0x180023663  jnz     short loc_18002366F
0x180023665  mov     edi, 80070057h
0x18002366a  jmp     loc_1800237E5
0x18002366f  xor     esi, esi
0x180023671  lea     rcx, [rbp+Buffer]; lpBuffer
0x180023675  mov     [rdx], rsi
0x180023678  lea     rdx, [rbp+nSize]; nSize
0x18002367c  call    cs:__imp_GetComputerNameW
0x180023682  test    eax, eax
0x180023684  jz      short loc_180023704
0x180023686  test    rbx, rbx
0x180023689  jz      short loc_1800236BE
0x18002368b  lea     eax, [rsi+5Ch]
0x18002368e  cmp     [rbx], ax
0x180023691  jnz     short loc_18002369F
0x180023693  cmp     ax, [rbx+2]
0x180023697  jnz     short loc_18002369F
0x180023699  add     rbx, 4
0x18002369d  jmp     short loc_1800236AB
0x18002369f  test    rbx, rbx
0x1800236a2  jz      short loc_1800236BE
0x1800236a4  xor     eax, eax
0x1800236a6  cmp     ax, [rbx]
0x1800236a9  jz      short loc_1800236BE
0x1800236ab  lea     rdx, [rbp+Buffer]; lpString2
0x1800236af  mov     rcx, rbx; lpString1
0x1800236b2  xor     r14d, r14d
0x1800236b5  call    CompareStringWrapW
0x1800236ba  test    eax, eax
0x1800236bc  jnz     short loc_1800236C8
0x1800236be  mov     r14d, 1
0x1800236c4  lea     rbx, [rbp+Buffer]
0x1800236c8  mov     r8d, r14d
0x1800236cb  lea     rdx, [rbp+Binding]; Binding
0x1800236cf  mov     rcx, rbx; String1
0x1800236d2  call    RasRPCBind
0x1800236d7  mov     edi, eax
0x1800236d9  test    eax, eax
0x1800236db  jnz     short loc_180023714
0x1800236dd  mov     rcx, [rbp+Binding]
0x1800236e1  lea     rdx, [rbp+var_30]
0x1800236e5  call    GetServerVersion
0x1800236ea  mov     edi, eax
0x1800236ec  test    eax, eax
0x1800236ee  jnz     short loc_180023714
0x1800236f0  lea     edx, [rax+30h]; uBytes
0x1800236f3  lea     ecx, [rax+40h]; uFlags
0x1800236f6  call    cs:__imp_LocalAlloc
0x1800236fc  mov     rsi, rax
0x1800236ff  test    rax, rax
0x180023702  jnz     short loc_18002372E
0x180023704  call    cs:__imp_GetLastError
0x18002370a  mov     edi, eax
0x18002370c  test    eax, eax
0x18002370e  jz      loc_1800237E5
0x180023714  cmp     [rbp+Binding], 0
0x180023719  jz      loc_1800237E5
0x18002371f  mov     eax, cs:Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_featureState
0x180023725  test    al, 10h
0x180023727  jz      short loc_180023775
0x180023729  and     eax, 1
0x18002372c  jmp     short loc_18002377A
0x18002372e  mov     rax, [rbp+Binding]
0x180023732  mov     ecx, 6
0x180023737  mov     [rsi], rax
0x18002373a  test    r14d, r14d
0x18002373d  mov     [rsi+8], r14d
0x180023741  mov     r8, rbx
0x180023744  mov     eax, [rbp+var_30]
0x180023747  mov     edx, 10h
0x18002374c  cmovnz  eax, ecx
0x18002374f  lea     rcx, [rsi+10h]
0x180023753  mov     [rsi+0Ch], eax
0x180023756  call    StringCchCopyWrapW
0x18002375b  mov     edi, eax
0x18002375d  test    eax, eax
0x18002375f  jnz     short loc_180023714
0x180023761  mov     eax, cs:Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_featureState
0x180023767  test    al, 10h
0x180023769  jnz     short loc_180023770
0x18002376b  call    Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_IsEnabledDeviceUsageNoInline
0x180023770  mov     [r15], rsi
0x180023773  jmp     short loc_1800237E5
0x180023775  call    Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_IsEnabledDeviceUsageNoInline
0x18002377a  test    eax, eax
0x18002377c  jz      short loc_1800237B7
0x18002377e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180023784  cmp     ecx, 0FFFFFFFFh
0x180023787  jz      short loc_18002379E
0x180023789  mov     r9d, edi
0x18002378c  lea     r8, aInitializeconn_0; "InitializeConnection: failed with error"...
0x180023793  mov     edx, 0Ch; dwFlags
0x180023798  call    cs:__imp_TracePrintfExA
0x18002379e  lea     rcx, [rbp+Binding]; Binding
0x1800237a2  call    RasRpcDisconnect
0x1800237a7  test    rsi, rsi
0x1800237aa  jz      short loc_1800237E5
0x1800237ac  mov     rcx, rsi; hMem
0x1800237af  call    cs:__imp_LocalFree
0x1800237b5  jmp     short loc_1800237E5
0x1800237b7  lea     rcx, [rbp+Binding]; Binding
0x1800237bb  call    cs:__imp_RpcBindingFree
0x1800237c1  test    eax, eax
0x1800237c3  jz      short loc_1800237E5
0x1800237c5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800237cb  cmp     ecx, 0FFFFFFFFh
0x1800237ce  jz      short loc_1800237E5
0x1800237d0  mov     r9d, eax
0x1800237d3  lea     r8, aInitializeconn; "InitializeConnection: RpcBindingFree fa"...
0x1800237da  mov     edx, 0Ch; dwFlags
0x1800237df  call    cs:__imp_TracePrintfExA
0x1800237e5  mov     eax, edi
0x1800237e7  mov     rcx, [rbp+var_8]
0x1800237eb  xor     rcx, rsp; StackCookie
0x1800237ee  call    __security_check_cookie
0x1800237f3  mov     rbx, [rsp+60h+arg_10]
0x1800237fb  add     rsp, 60h
0x1800237ff  pop     r15
0x180023801  pop     r14
0x180023803  pop     rdi
0x180023804  pop     rsi
0x180023805  pop     rbp
0x180023806  retn
```
