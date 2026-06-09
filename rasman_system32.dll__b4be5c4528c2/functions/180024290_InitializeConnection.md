# InitializeConnection

- ea: `0x180024290`
- end: `0x1800244b1`
- name: `InitializeConnection`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180023510`

## callees

- `0x180011440`
- `0x1800235f0`
- `0x180024204`
- `0x18002424c`
- `0x180024290`
- `0x180026ef8`
- `0x180026f3c`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024446`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024378`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002438c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002438c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800242f4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800242f4`
- `RPCRT4!RpcBindingFree` at `0x180024458`
- `RPCRT4!RpcBindingFree` at `0x180024458`
- `rtutils!TracePrintfExA` at `0x180024429`
- `rtutils!TracePrintfExA` at `0x180024482`
- `rtutils!TracePrintfExA` at `0x180024429`
- `rtutils!TracePrintfExA` at `0x180024482`

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
0x180024290  mov     [rsp-28h+arg_10], rbx
0x180024295  push    rbp
0x180024296  push    rsi
0x180024297  push    rdi
0x180024298  push    r14
0x18002429a  push    r15
0x18002429c  mov     rbp, rsp
0x18002429f  sub     rsp, 60h
0x1800242a3  mov     rax, cs:__security_cookie
0x1800242aa  xor     rax, rsp
0x1800242ad  mov     [rbp+var_8], rax
0x1800242b1  mov     [rbp+nSize], 10h
0x1800242b8  xorps   xmm0, xmm0
0x1800242bb  mov     [rbp+Binding], 0
0x1800242c3  mov     r15, rdx
0x1800242c6  mov     [rbp+var_30], 0
0x1800242cd  mov     rbx, rcx
0x1800242d0  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800242d4  movups  [rbp+var_18], xmm0
0x1800242d8  test    rdx, rdx
0x1800242db  jnz     short loc_1800242E7
0x1800242dd  mov     edi, 80070057h
0x1800242e2  jmp     loc_18002448E
0x1800242e7  xor     esi, esi
0x1800242e9  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800242ed  mov     [rdx], rsi
0x1800242f0  lea     rdx, [rbp+nSize]; nSize
0x1800242f4  call    cs:__imp_GetComputerNameW
0x1800242fb  nop     dword ptr [rax+rax+00h]
0x180024300  test    eax, eax
0x180024302  jz      loc_18002438C
0x180024308  test    rbx, rbx
0x18002430b  jz      short loc_180024340
0x18002430d  lea     eax, [rsi+5Ch]
0x180024310  cmp     [rbx], ax
0x180024313  jnz     short loc_180024321
0x180024315  cmp     ax, [rbx+2]
0x180024319  jnz     short loc_180024321
0x18002431b  add     rbx, 4
0x18002431f  jmp     short loc_18002432D
0x180024321  test    rbx, rbx
0x180024324  jz      short loc_180024340
0x180024326  xor     eax, eax
0x180024328  cmp     ax, [rbx]
0x18002432b  jz      short loc_180024340
0x18002432d  lea     rdx, [rbp+Buffer]; lpString2
0x180024331  mov     rcx, rbx; lpString1
0x180024334  xor     r14d, r14d
0x180024337  call    CompareStringWrapW
0x18002433c  test    eax, eax
0x18002433e  jnz     short loc_18002434A
0x180024340  mov     r14d, 1
0x180024346  lea     rbx, [rbp+Buffer]
0x18002434a  mov     r8d, r14d
0x18002434d  lea     rdx, [rbp+Binding]; Binding
0x180024351  mov     rcx, rbx; String1
0x180024354  call    RasRPCBind
0x180024359  mov     edi, eax
0x18002435b  test    eax, eax
0x18002435d  jnz     short loc_1800243A2
0x18002435f  mov     rcx, [rbp+Binding]
0x180024363  lea     rdx, [rbp+var_30]
0x180024367  call    GetServerVersion
0x18002436c  mov     edi, eax
0x18002436e  test    eax, eax
0x180024370  jnz     short loc_1800243A2
0x180024372  lea     edx, [rax+30h]; uBytes
0x180024375  lea     ecx, [rax+40h]; uFlags
0x180024378  call    cs:__imp_LocalAlloc
0x18002437f  nop     dword ptr [rax+rax+00h]
0x180024384  mov     rsi, rax
0x180024387  test    rax, rax
0x18002438a  jnz     short loc_1800243BC
0x18002438c  call    cs:__imp_GetLastError
0x180024393  nop     dword ptr [rax+rax+00h]
0x180024398  mov     edi, eax
0x18002439a  test    eax, eax
0x18002439c  jz      loc_18002448E
0x1800243a2  cmp     [rbp+Binding], 0
0x1800243a7  jz      loc_18002448E
0x1800243ad  mov     eax, cs:Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_featureState
0x1800243b3  test    al, 10h
0x1800243b5  jz      short loc_180024406
0x1800243b7  and     eax, 1
0x1800243ba  jmp     short loc_18002440B
0x1800243bc  mov     rax, [rbp+Binding]
0x1800243c0  mov     ecx, 6
0x1800243c5  mov     [rsi], rax
0x1800243c8  test    r14d, r14d
0x1800243cb  mov     [rsi+8], r14d
0x1800243cf  mov     r8, rbx
0x1800243d2  mov     eax, [rbp+var_30]
0x1800243d5  mov     edx, 10h
0x1800243da  cmovnz  eax, ecx
0x1800243dd  lea     rcx, [rsi+10h]
0x1800243e1  mov     [rsi+0Ch], eax
0x1800243e4  call    StringCchCopyWrapW
0x1800243e9  mov     edi, eax
0x1800243eb  test    eax, eax
0x1800243ed  jnz     short loc_1800243A2
0x1800243ef  mov     eax, cs:Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_featureState
0x1800243f5  test    al, 10h
0x1800243f7  jnz     short loc_1800243FE
0x1800243f9  call    Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_IsEnabledDeviceUsageNoInline
0x1800243fe  mov     [r15], rsi
0x180024401  jmp     loc_18002448E
0x180024406  call    Feature_VPN_BugFixes_25B_Use_After_Free_Fix__private_IsEnabledDeviceUsageNoInline
0x18002440b  test    eax, eax
0x18002440d  jz      short loc_180024454
0x18002440f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024415  cmp     ecx, 0FFFFFFFFh
0x180024418  jz      short loc_180024435
0x18002441a  mov     r9d, edi
0x18002441d  lea     r8, aInitializeconn_0; "InitializeConnection: failed with error"...
0x180024424  mov     edx, 0Ch; dwFlags
0x180024429  call    cs:__imp_TracePrintfExA
0x180024430  nop     dword ptr [rax+rax+00h]
0x180024435  lea     rcx, [rbp+Binding]; Binding
0x180024439  call    RasRpcDisconnect
0x18002443e  test    rsi, rsi
0x180024441  jz      short loc_18002448E
0x180024443  mov     rcx, rsi; hMem
0x180024446  call    cs:__imp_LocalFree
0x18002444d  nop     dword ptr [rax+rax+00h]
0x180024452  jmp     short loc_18002448E
0x180024454  lea     rcx, [rbp+Binding]; Binding
0x180024458  call    cs:__imp_RpcBindingFree
0x18002445f  nop     dword ptr [rax+rax+00h]
0x180024464  test    eax, eax
0x180024466  jz      short loc_18002448E
0x180024468  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002446e  cmp     ecx, 0FFFFFFFFh
0x180024471  jz      short loc_18002448E
0x180024473  mov     r9d, eax
0x180024476  lea     r8, aInitializeconn; "InitializeConnection: RpcBindingFree fa"...
0x18002447d  mov     edx, 0Ch; dwFlags
0x180024482  call    cs:__imp_TracePrintfExA
0x180024489  nop     dword ptr [rax+rax+00h]
0x18002448e  mov     eax, edi
0x180024490  mov     rcx, [rbp+var_8]
0x180024494  xor     rcx, rsp; StackCookie
0x180024497  call    __security_check_cookie
0x18002449c  mov     rbx, [rsp+60h+arg_10]
0x1800244a4  add     rsp, 60h
0x1800244a8  pop     r15
0x1800244aa  pop     r14
0x1800244ac  pop     rdi
0x1800244ad  pop     rsi
0x1800244ae  pop     rbp
0x1800244af  retn
```
