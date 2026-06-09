# NetworkIsolationGetEnterpriseIdAsync

- ea: `0x180010180`
- end: `0x180010607`
- name: `NetworkIsolationGetEnterpriseIdAsync`
- size: `1159`
- prototype: `DWORD __stdcall(LPCWSTR wszServerName, DWORD dwFlags, void *context, PNETISO_EDP_ID_CALLBACK_FN callback, HANDLE *hOperation)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800100f0`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180010180`
- `0x180010610`
- `0x1800108f4`
- `0x180026798`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x18004c0f0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fb26`
- `RPCRT4!RpcExceptionFilter` at `0x18005fb26`
- `RPCRT4!RpcBindingSetOption` at `0x1800102a1`
- `RPCRT4!RpcBindingSetOption` at `0x1800102a1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180010408`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180010408`
- `RPCRT4!RpcBindingFree` at `0x1800105a3`
- `RPCRT4!RpcBindingFree` at `0x1800105a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800102f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001031f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800102f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001031f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001035a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001035a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800103b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800103b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800101ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800101ec`
- `fwbase!FwBaseAlloc` at `0x180010203`
- `fwbase!FwBaseAlloc` at `0x180010203`

## pseudocode

```c
DWORD __stdcall NetworkIsolationGetEnterpriseIdAsync(
        LPCWSTR wszServerName,
        DWORD dwFlags,
        void *context,
        PNETISO_EDP_ID_CALLBACK_FN callback,
        HANDLE *hOperation)
{
  RPC_BINDING_HANDLE *v7; // rax
  RPC_BINDING_HANDLE *v8; // rsi
  __int64 v9; // r9
  unsigned int v10; // ebx
  FwPolicy2 *v11; // rcx
  unsigned int inited; // eax
  HANDLE EventW; // rax
  HANDLE v15; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rcx
  RPC_BINDING_HANDLE hBinding; // [rsp+78h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 537, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  hBinding = 0;
  GetTickCount64();
  *hOperation = 0;
  v7 = (RPC_BINDING_HANDLE *)FwBaseAlloc(192);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 14;
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 538;
      goto LABEL_18;
    }
    goto LABEL_6;
  }
  memset_0(v7, 0, 0xC0u);
  inited = Int_FWLocalRpcBindingCreate(&hBinding);
  v10 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v17 = 539;
LABEL_26:
    v9 = inited;
    goto LABEL_18;
  }
  inited = RpcBindingSetOption(hBinding, 9u, 1u);
  v10 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v17 = 540;
    goto LABEL_26;
  }
  *v8 = hBinding;
  hBinding = 0;
  v8[16] = callback;
  v8[17] = context;
  *((_DWORD *)v8 + 44) = 1;
  _InterlockedExchange((volatile __int32 *)v8 + 45, 1);
  EventW = CreateEventW(0, 0, 0, 0);
  v8[18] = EventW;
  if ( !EventW )
  {
    v9 = 14;
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 541;
      goto LABEL_18;
    }
    goto LABEL_6;
  }
  v15 = CreateEventW(0, 1, 0, 0);
  v8[23] = v15;
  if ( !v15 )
  {
    v9 = 14;
    v10 = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 542;
      goto LABEL_18;
    }
    goto LABEL_6;
  }
  inited = Int_NetworkIsolationInitOperationRpcAsync((struct FW_INTCLIENT_OP_HANDLE_ *)v8);
  v10 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v17 = 543;
    goto LABEL_26;
  }
  ThreadpoolWait = CreateThreadpoolWait(Int_NetworkIsolationAsyncOpCallback, v8, 0);
  v8[19] = ThreadpoolWait;
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, v8[7], 0);
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
      1u,
      0,
      v8 + 1,
      *v8,
      wszServerName,
      dwFlags,
      v8 + 20,
      v8 + 21);
    _InterlockedIncrement((volatile signed __int32 *)v8 + 44);
    *hOperation = v8;
    goto LABEL_20;
  }
  v9 = v10 + 14;
  v10 += 14;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 544;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v11 + 2), v17, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v9);
LABEL_20:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_6:
  if ( v10 )
  {
    FwTelemetryEventWriteError("NetworkIsolationGetEnterpriseIdAsync", v10);
    if ( hBinding )
    {
      v18 = RpcBindingFree(&hBinding);
      if ( v18 )
        MicrosoftTelemetryAssertTriggeredArgs(v19, v18);
      hBinding = 0;
    }
    if ( v8 )
    {
      _InterlockedExchange((volatile __int32 *)v8 + 45, 0);
      NetworkIsolationGetEnterpriseIdClose(v8, 0);
    }
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v11 + 2), 546, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180010180  mov     [rsp+arg_10], rbx
0x180010185  mov     [rsp+arg_18], rsi
0x18001018a  push    rdi
0x18001018b  push    r12
0x18001018d  push    r13
0x18001018f  push    r14
0x180010191  push    r15
0x180010193  sub     rsp, 90h
0x18001019a  mov     rax, cs:__security_cookie
0x1800101a1  xor     rax, rsp
0x1800101a4  mov     [rsp+0B8h+var_38], rax
0x1800101ac  mov     r15, r9
0x1800101af  mov     r13, r8
0x1800101b2  mov     [rsp+0B8h+var_68], edx
0x1800101b6  mov     [rsp+0B8h+var_58], rcx
0x1800101bb  mov     r12, [rsp+0B8h+hOperation]
0x1800101c3  mov     [rsp+0B8h+var_50], r12
0x1800101c8  lea     r14, WPP_GLOBAL_Control
0x1800101cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101d6  cmp     rcx, r14
0x1800101d9  jz      short loc_1800101E5
0x1800101db  test    byte ptr [rcx+1Ch], 8
0x1800101df  jnz     loc_180010493
0x1800101e5  xor     edi, edi
0x1800101e7  mov     [rsp+0B8h+hBinding], rdi
0x1800101ec  call    cs:__imp_GetTickCount64
0x1800101f3  nop     dword ptr [rax+rax+00h]
0x1800101f8  mov     [r12], rdi
0x1800101fc  mov     ebx, 0C0h
0x180010201  mov     ecx, ebx
0x180010203  call    cs:__imp_FwBaseAlloc
0x18001020a  nop     dword ptr [rax+rax+00h]
0x18001020f  mov     rsi, rax
0x180010212  mov     [rsp+0B8h+var_60], rax
0x180010217  test    rax, rax
0x18001021a  jnz     short loc_180010274
0x18001021c  lea     r9d, [rdi+0Eh]
0x180010220  mov     ebx, r9d
0x180010223  mov     rcx, cs:WPP_GLOBAL_Control
0x18001022a  cmp     rcx, r14
0x18001022d  jnz     loc_1800104AD
0x180010233  test    ebx, ebx
0x180010235  jnz     loc_180010589
0x18001023b  cmp     rcx, r14
0x18001023e  jnz     loc_1800105E0
0x180010244  mov     eax, ebx
0x180010246  mov     rcx, [rsp+0B8h+var_38]
0x18001024e  xor     rcx, rsp; StackCookie
0x180010251  call    __security_check_cookie
0x180010256  lea     r11, [rsp+0B8h+var_28]
0x18001025e  mov     rbx, [r11+40h]
0x180010262  mov     rsi, [r11+48h]
0x180010266  mov     rsp, r11
0x180010269  pop     r15
0x18001026b  pop     r14
0x18001026d  pop     r13
0x18001026f  pop     r12
0x180010271  pop     rdi
0x180010272  retn
0x180010274  mov     r8, rbx; Size
0x180010277  xor     edx, edx; Val
0x180010279  mov     rcx, rsi; void *
0x18001027c  call    memset_0
0x180010281  lea     rcx, [rsp+0B8h+hBinding]
0x180010286  call    Int_FWLocalRpcBindingCreate
0x18001028b  mov     ebx, eax
0x18001028d  test    eax, eax
0x18001028f  jnz     loc_1800104C1
0x180010295  lea     edx, [rax+9]; option
0x180010298  lea     r8d, [rax+1]; optionValue
0x18001029c  mov     rcx, [rsp+0B8h+hBinding]; hBinding
0x1800102a1  call    cs:__imp_RpcBindingSetOption
0x1800102a8  nop     dword ptr [rax+rax+00h]
0x1800102ad  mov     ebx, eax
0x1800102af  test    eax, eax
0x1800102b1  jnz     loc_1800104EF
0x1800102b7  mov     rax, [rsp+0B8h+hBinding]
0x1800102bc  mov     [rsi], rax
0x1800102bf  mov     [rsp+0B8h+hBinding], rdi
0x1800102c4  mov     [rsi+80h], r15
0x1800102cb  mov     [rsi+88h], r13
0x1800102d2  lea     r15, [rsi+0B0h]
0x1800102d9  mov     [rsp+0B8h+var_48], r15
0x1800102de  mov     dword ptr [r15], 1
0x1800102e5  lea     eax, [rbx+1]
0x1800102e8  xchg    eax, [rsi+0B4h]
0x1800102ee  xor     r9d, r9d; lpName
0x1800102f1  xor     r8d, r8d; bInitialState
0x1800102f4  xor     edx, edx; bManualReset
0x1800102f6  xor     ecx, ecx; lpEventAttributes
0x1800102f8  call    cs:__imp_CreateEventW
0x1800102ff  nop     dword ptr [rax+rax+00h]
0x180010304  mov     [rsi+90h], rax
0x18001030b  test    rax, rax
0x18001030e  jz      loc_180010510
0x180010314  xor     r9d, r9d; lpName
0x180010317  xor     r8d, r8d; bInitialState
0x18001031a  lea     edx, [rbx+1]; bManualReset
0x18001031d  xor     ecx, ecx; lpEventAttributes
0x18001031f  call    cs:__imp_CreateEventW
0x180010326  nop     dword ptr [rax+rax+00h]
0x18001032b  mov     [rsi+0B8h], rax
0x180010332  test    rax, rax
0x180010335  jz      loc_18001053D
0x18001033b  mov     rcx, rsi; struct FW_INTCLIENT_OP_HANDLE_ *
0x18001033e  call    ?Int_NetworkIsolationInitOperationRpcAsync@@YAKPEAUFW_INTCLIENT_OP_HANDLE_@@@Z; Int_NetworkIsolationInitOperationRpcAsync(FW_INTCLIENT_OP_HANDLE_ *)
0x180010343  mov     ebx, eax
0x180010345  test    eax, eax
0x180010347  jnz     loc_18001056A
0x18001034d  xor     r8d, r8d; pcbe
0x180010350  mov     rdx, rsi; pv
0x180010353  lea     rcx, ?Int_NetworkIsolationAsyncOpCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001035a  call    cs:__imp_CreateThreadpoolWait
0x180010361  nop     dword ptr [rax+rax+00h]
0x180010366  mov     [rsi+98h], rax
0x18001036d  test    rax, rax
0x180010370  jnz     short loc_1800103AD
0x180010372  lea     r9d, [rbx+0Eh]
0x180010376  mov     ebx, r9d
0x180010379  mov     rcx, cs:WPP_GLOBAL_Control
0x180010380  cmp     rcx, r14
0x180010383  jz      loc_180010233
0x180010389  test    byte ptr [rcx+1Ch], 1
0x18001038d  jz      loc_180010233
0x180010393  mov     edx, 220h
0x180010398  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001039f  mov     rcx, [rcx+10h]
0x1800103a3  call    WPP_SF_d
0x1800103a8  jmp     loc_180010487
0x1800103ad  xor     r8d, r8d; pftTimeout
0x1800103b0  mov     rdx, [rsi+38h]; h
0x1800103b4  mov     rcx, rax; pwa
0x1800103b7  call    cs:__imp_SetThreadpoolWait
0x1800103be  nop     dword ptr [rax+rax+00h]
0x1800103c3  nop
0x1800103c4  lea     rax, [rsi+0A8h]
0x1800103cb  lea     rcx, [rsi+0A0h]
0x1800103d2  mov     [rsp+0B8h+var_78], rax
0x1800103d7  mov     [rsp+0B8h+var_80], rcx
0x1800103dc  mov     eax, [rsp+0B8h+var_68]
0x1800103e0  mov     [rsp+0B8h+var_88], eax
0x1800103e4  mov     rax, [rsp+0B8h+var_58]
0x1800103e9  mov     [rsp+0B8h+var_90], rax
0x1800103ee  mov     rax, [rsi]
0x1800103f1  mov     [rsp+0B8h+var_98], rax
0x1800103f6  lea     r9, [rsi+8]
0x1800103fa  xor     r8d, r8d; pReturnValue
0x1800103fd  lea     edx, [r8+1]; nProcNum
0x180010401  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180010408  call    cs:__imp_Ndr64AsyncClientCall
0x18001040f  nop     dword ptr [rax+rax+00h]
0x180010414  jmp     short loc_18001047F
0x180010416  mov     ebx, eax
0x180010418  test    eax, eax
0x18001041a  jz      short loc_180010467
0x18001041c  lea     rax, WPP_GLOBAL_Control
0x180010423  mov     rcx, cs:WPP_GLOBAL_Control
0x18001042a  cmp     rcx, rax
0x18001042d  jz      short loc_180010454
0x18001042f  test    byte ptr [rcx+1Ch], 1
0x180010433  jz      short loc_180010454
0x180010435  mov     edx, 221h
0x18001043a  mov     r9d, ebx
0x18001043d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180010444  mov     rcx, [rcx+10h]
0x180010448  call    WPP_SF_d
0x18001044d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010454  lea     r14, WPP_GLOBAL_Control
0x18001045b  xor     edi, edi
0x18001045d  mov     rsi, [rsp+0B8h+var_60]
0x180010462  jmp     loc_180010233
0x180010467  lea     r14, WPP_GLOBAL_Control
0x18001046e  xor     edi, edi
0x180010470  mov     r12, [rsp+0B8h+var_50]
0x180010475  mov     rsi, [rsp+0B8h+var_60]
0x18001047a  mov     r15, [rsp+0B8h+var_48]
0x18001047f  lock inc dword ptr [r15]
0x180010483  mov     [r12], rsi
0x180010487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001048e  jmp     loc_180010233
0x180010493  mov     edx, 219h
0x180010498  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001049f  mov     rcx, [rcx+10h]
0x1800104a3  call    WPP_SF_
0x1800104a8  jmp     loc_1800101E5
0x1800104ad  test    byte ptr [rcx+1Ch], 1
0x1800104b1  jz      loc_180010233
0x1800104b7  mov     edx, 21Ah
0x1800104bc  jmp     loc_180010398
0x1800104c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104c8  cmp     rcx, r14
0x1800104cb  jz      loc_180010233
0x1800104d1  test    byte ptr [rcx+1Ch], 1
0x1800104d5  jz      loc_180010233
0x1800104db  mov     edx, 21Bh
0x1800104e0  jmp     short loc_1800104E7
0x1800104e2  mov     edx, 21Fh
0x1800104e7  mov     r9d, eax
0x1800104ea  jmp     loc_180010398
0x1800104ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104f6  cmp     rcx, r14
0x1800104f9  jz      loc_180010233
0x1800104ff  test    byte ptr [rcx+1Ch], 1
0x180010503  jz      loc_180010233
0x180010509  mov     edx, 21Ch
0x18001050e  jmp     short loc_1800104E7
0x180010510  mov     r9d, 0Eh
0x180010516  mov     ebx, r9d
0x180010519  mov     rcx, cs:WPP_GLOBAL_Control
0x180010520  cmp     rcx, r14
0x180010523  jz      loc_180010233
0x180010529  test    byte ptr [rcx+1Ch], 1
0x18001052d  jz      loc_180010233
0x180010533  mov     edx, 21Dh
0x180010538  jmp     loc_180010398
0x18001053d  mov     r9d, 0Eh
0x180010543  mov     ebx, r9d
0x180010546  mov     rcx, cs:WPP_GLOBAL_Control
0x18001054d  cmp     rcx, r14
0x180010550  jz      loc_180010233
0x180010556  test    byte ptr [rcx+1Ch], 1
0x18001055a  jz      loc_180010233
0x180010560  mov     edx, 21Eh
0x180010565  jmp     loc_180010398
0x18001056a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010571  cmp     rcx, r14
0x180010574  jz      loc_180010233
0x18001057a  test    byte ptr [rcx+1Ch], 1
0x18001057e  jz      loc_180010233
0x180010584  jmp     loc_1800104E2
0x180010589  mov     edx, ebx; unsigned int
0x18001058b  lea     rcx, aNetworkisolati_29; "NetworkIsolationGetEnterpriseIdAsync"
0x180010592  call    ?FwTelemetryEventWriteError@@YAXQEADI@Z; FwTelemetryEventWriteError(char * const,uint)
0x180010597  cmp     [rsp+0B8h+hBinding], rdi
0x18001059c  jz      short loc_1800105BF
0x18001059e  lea     rcx, [rsp+0B8h+hBinding]; Binding
0x1800105a3  call    cs:__imp_RpcBindingFree
0x1800105aa  nop     dword ptr [rax+rax+00h]
0x1800105af  test    eax, eax
0x1800105b1  jz      short loc_1800105BA
0x1800105b3  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x1800105b5  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800105ba  mov     [rsp+0B8h+hBinding], rdi
0x1800105bf  test    rsi, rsi
0x1800105c2  jz      short loc_1800105D4
0x1800105c4  xchg    edi, [rsi+0B4h]
0x1800105ca  xor     edx, edx; bWaitForOperation
0x1800105cc  mov     rcx, rsi; hOperation
0x1800105cf  call    NetworkIsolationGetEnterpriseIdClose
0x1800105d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105db  jmp     loc_18001023B
0x1800105e0  test    byte ptr [rcx+1Ch], 8
0x1800105e4  jz      loc_180010244
0x1800105ea  mov     edx, 222h
0x1800105ef  mov     r9d, ebx
0x1800105f2  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800105f9  mov     rcx, [rcx+10h]
0x1800105fd  call    WPP_SF_d
0x180010602  jmp     loc_180010244
0x18005fb18  push    rbp
0x18005fb1a  sub     rsp, 50h
0x18005fb1e  mov     rbp, rdx
0x18005fb21  mov     rcx, [rcx]
0x18005fb24  mov     ecx, [rcx]; ExceptionCode
0x18005fb26  call    cs:__imp_RpcExceptionFilter
0x18005fb2d  nop     dword ptr [rax+rax+00h]
0x18005fb32  nop
0x18005fb33  add     rsp, 50h
0x18005fb37  pop     rbp
0x18005fb38  retn
```
