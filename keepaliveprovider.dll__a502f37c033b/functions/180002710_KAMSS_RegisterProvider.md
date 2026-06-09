# KAMSS_RegisterProvider

- ea: `0x180002710`
- end: `0x180002cae`
- name: `KAMSS_RegisterProvider`
- size: `1438`
- prototype: `__int64 __fastcall(CLIENT_CALL_RETURN, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001400`
- `0x180001c7e`
- `0x180001e20`
- `0x180002110`
- `0x180002710`
- `0x1800032c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800027f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800027f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002812`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000289a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000289a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002874`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002874`
- `RPCRT4!RpcBindingBind` at `0x180002a2c`
- `RPCRT4!RpcBindingBind` at `0x180002a2c`
- `RPCRT4!RpcBindingUnbind` at `0x180002c33`
- `RPCRT4!RpcBindingUnbind` at `0x180002c33`
- `RPCRT4!RpcBindingFree` at `0x180002c3c`
- `RPCRT4!RpcBindingFree` at `0x180002c3c`
- `RPCRT4!NdrClientCall3` at `0x180002a84`
- `RPCRT4!NdrClientCall3` at `0x180002b66`
- `RPCRT4!NdrClientCall3` at `0x180002a84`
- `RPCRT4!NdrClientCall3` at `0x180002b66`
- `RPCRT4!RpcBindingCreateW` at `0x180002993`
- `RPCRT4!RpcBindingCreateW` at `0x180002993`
- `RPCRT4!RpcBindingSetOption` at `0x1800029da`
- `RPCRT4!RpcBindingSetOption` at `0x1800029da`

## pseudocode

```c
__int64 __fastcall KAMSS_RegisterProvider(CLIENT_CALL_RETURN a1, __int64 a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rdi
  unsigned int Pointer; // ebx
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rbx
  DWORD LastError; // eax
  __int64 v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  CLIENT_CALL_RETURN v21; // rax
  CLIENT_CALL_RETURN v22; // r8
  unsigned int v23; // eax
  __int64 v24; // r8
  HANDLE v26; // rax
  DWORD cbSid; // [rsp+34h] [rbp-164h] BYREF
  CLIENT_CALL_RETURN v28; // [rsp+38h] [rbp-160h]
  _QWORD *v29; // [rsp+40h] [rbp-158h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+48h] [rbp-150h] BYREF
  CLIENT_CALL_RETURN v31; // [rsp+78h] [rbp-120h]
  __int64 v32; // [rsp+80h] [rbp-118h]
  __int64 v33; // [rsp+88h] [rbp-110h]
  __int128 v34; // [rsp+90h] [rbp-108h] BYREF
  __int128 v35; // [rsp+A0h] [rbp-F8h]
  __int128 v36; // [rsp+B0h] [rbp-E8h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+C0h] [rbp-D8h] BYREF
  _BYTE pSid[80]; // [rsp+100h] [rbp-98h] BYREF

  v32 = a3;
  v33 = a2;
  v28.Pointer = a1.Pointer;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  cbSid = 68;
  memset(&Security, 0, 36);
  memset(&Template, 0, sizeof(Template));
  v34 = 0;
  v35 = 0;
  v36 = 0;
  *a4 = 0;
  *a5 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, 0xE0u);
  v29 = v7;
  Pointer = 8;
  if ( !v7 )
  {
    SetLastError(8u);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_53;
    }
    v11 = 15;
    v12 = 8;
    goto LABEL_10;
  }
  memset_0(v7, 0, 0xE0u);
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_D(v13, 16, v15, LastError);
      v10 = WPP_GLOBAL_Control;
    }
    Pointer = 1337;
    goto LABEL_53;
  }
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  memset(&Template, 0, sizeof(Template));
  v35 = 0u;
  LODWORD(v34) = 4;
  *(_QWORD *)((char *)&v34 + 4) = 17;
  HIDWORD(v34) = 3;
  v36 = (unsigned __int64)pSid;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v34;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  v16 = RpcBindingCreateW(&Template, &Security, 0, (RPC_BINDING_HANDLE *)v7);
  Pointer = v16;
  if ( v16 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_53;
    }
    v11 = 17;
    v12 = v16;
LABEL_10:
    WPP_SF_D(v10[2], v11, v9, v12);
LABEL_52:
    v10 = WPP_GLOBAL_Control;
LABEL_53:
    if ( v7 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v7);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      WPP_SF_D(v10[2], 25, v9, Pointer);
    return Pointer;
  }
  v17 = RpcBindingSetOption((RPC_BINDING_HANDLE)*v7, 9u, 1u);
  Pointer = v17;
  if ( v17 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v20 = 18;
    goto LABEL_27;
  }
  v17 = RpcBindingBind(0, (RPC_BINDING_HANDLE)*v7, qword_180005400);
  Pointer = v17;
  if ( v17 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v20 = 19;
LABEL_27:
    WPP_SF_D(v19[2], v20, v18, v17);
LABEL_51:
    RpcBindingFree((RPC_BINDING_HANDLE *)v7);
    goto LABEL_52;
  }
  v31.Simple = 0;
  v21.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, *v7, v7 + 1).Pointer;
  Pointer = (unsigned int)v21.Pointer;
  v31.Pointer = v21.Pointer;
  if ( LODWORD(v21.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_D)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (CLIENT_CALL_RETURN)v22.Simple,
        LODWORD(v21.Pointer));
    }
LABEL_50:
    RpcBindingUnbind((RPC_BINDING_HANDLE)*v7);
    goto LABEL_51;
  }
  v7[24] = v32;
  v7[23] = v33;
  v7[21] = v28.Simple;
  *a4 = KAMSS_MeasurementUpdateCallback;
  *a5 = v7;
  v23 = InitializeKaMeasurements(v7);
  Pointer = v23;
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v24, v23);
    }
    *a5 = 0;
    v28.Simple = 0;
    v28.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, *v7, v7 + 1).Pointer;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v24, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180002710  push    rbx
0x180002712  push    rsi
0x180002713  push    rdi
0x180002714  push    r12
0x180002716  push    r13
0x180002718  push    r15
0x18000271a  sub     rsp, 168h
0x180002721  mov     rax, cs:__security_cookie
0x180002728  xor     rax, rsp
0x18000272b  mov     [rsp+198h+var_48], rax
0x180002733  mov     r13, r9
0x180002736  mov     [rsp+198h+var_118], r8
0x18000273e  mov     [rsp+198h+var_110], rdx
0x180002746  mov     [rsp+198h+var_160], rcx
0x18000274b  mov     r15, [rsp+198h+arg_20]
0x180002753  lea     rsi, WPP_GLOBAL_Control
0x18000275a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002761  cmp     rcx, rsi
0x180002764  jz      short loc_180002787
0x180002766  test    byte ptr [rcx+1Ch], 1
0x18000276a  jz      short loc_180002787
0x18000276c  cmp     byte ptr [rcx+19h], 6
0x180002770  jb      short loc_180002787
0x180002772  mov     edx, 0Eh
0x180002777  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x18000277e  mov     rcx, [rcx+10h]
0x180002782  call    WPP_SF_
0x180002787  mov     [rsp+198h+cbSid], 44h ; 'D'
0x18000278f  xor     eax, eax
0x180002791  xorps   xmm0, xmm0
0x180002794  movups  xmmword ptr [rsp+198h+Security.Version], xmm0
0x180002799  movups  xmmword ptr [rsp+198h+Security.AuthnLevel], xmm0
0x18000279e  mov     dword ptr [rsp+198h+Security.SecurityQos], eax
0x1800027a2  xorps   xmm1, xmm1
0x1800027a5  movups  xmmword ptr [rsp+198h+Template.Version], xmm1
0x1800027ad  movups  xmmword ptr [rsp+198h+Template.NetworkAddress], xmm1
0x1800027b5  movups  xmmword ptr [rsp+198h+Template.u1], xmm1
0x1800027bd  mov     qword ptr [rsp+198h+Template.ObjectUuid.Data4], rax
0x1800027c5  movups  [rsp+198h+var_108], xmm0
0x1800027cd  movups  [rsp+198h+var_F8], xmm0
0x1800027d5  movups  [rsp+198h+var_E8], xmm0
0x1800027dd  mov     [r13+0], rax
0x1800027e1  mov     [r15], rax
0x1800027e4  call    cs:__imp_GetProcessHeap
0x1800027ea  mov     rcx, rax; hHeap
0x1800027ed  mov     r12d, 0E0h
0x1800027f3  mov     r8d, r12d; dwBytes
0x1800027f6  xor     edx, edx; dwFlags
0x1800027f8  call    cs:__imp_HeapAlloc
0x1800027fe  mov     rdi, rax
0x180002801  mov     [rsp+198h+var_158], rax
0x180002806  mov     ebx, 8
0x18000280b  test    rax, rax
0x18000280e  jnz     short loc_180002818
0x180002810  mov     ecx, ebx; dwErrCode
0x180002812  call    cs:__imp_SetLastError
0x180002818  test    rdi, rdi
0x18000281b  jnz     short loc_180002855
0x18000281d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002824  cmp     rcx, rsi
0x180002827  jz      loc_180002C49
0x18000282d  test    byte ptr [rcx+1Ch], 1
0x180002831  jz      loc_180002C49
0x180002837  cmp     byte ptr [rcx+19h], 2
0x18000283b  jb      loc_180002C49
0x180002841  lea     edx, [rdi+0Fh]
0x180002844  mov     r9d, ebx
0x180002847  mov     rcx, [rcx+10h]
0x18000284b  call    WPP_SF_D
0x180002850  jmp     loc_180002C42
0x180002855  mov     r8, r12; Size
0x180002858  xor     edx, edx; Val
0x18000285a  mov     rcx, rdi; void *
0x18000285d  call    memset_0
0x180002862  lea     r9, [rsp+198h+cbSid]; cbSid
0x180002867  lea     r8, [rsp+198h+pSid]; pSid
0x18000286f  xor     edx, edx; DomainSid
0x180002871  lea     ecx, [rdx+16h]; WellKnownSidType
0x180002874  call    cs:__imp_CreateWellKnownSid
0x18000287a  test    eax, eax
0x18000287c  jnz     short loc_1800028C1
0x18000287e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002885  cmp     rcx, rsi
0x180002888  jz      short loc_1800028B7
0x18000288a  test    byte ptr [rcx+1Ch], 1
0x18000288e  jz      short loc_1800028B7
0x180002890  cmp     byte ptr [rcx+19h], 2
0x180002894  jb      short loc_1800028B7
0x180002896  mov     rbx, [rcx+10h]
0x18000289a  call    cs:__imp_GetLastError
0x1800028a0  mov     r9d, eax
0x1800028a3  mov     edx, 10h
0x1800028a8  mov     rcx, rbx
0x1800028ab  call    WPP_SF_D
0x1800028b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028b7  mov     ebx, 539h
0x1800028bc  jmp     loc_180002C49
0x1800028c1  mov     qword ptr [rsp+198h+Security+4], 0
0x1800028ca  mov     dword ptr [rsp+198h+Security.ServerPrincName+4], 0
0x1800028d2  xorps   xmm0, xmm0
0x1800028d5  xor     eax, eax
0x1800028d7  movups  xmmword ptr [rsp+198h+Template.Version], xmm0
0x1800028df  movups  xmmword ptr [rsp+198h+Template.NetworkAddress], xmm0
0x1800028e7  movups  xmmword ptr [rsp+198h+Template.u1], xmm0
0x1800028ef  mov     qword ptr [rsp+198h+Template.ObjectUuid.Data4], rax
0x1800028f7  mov     qword ptr [rsp+198h+var_F8], rax
0x1800028ff  mov     qword ptr [rsp+198h+var_E8+8], rax
0x180002907  mov     dword ptr [rsp+198h+var_108], 4
0x180002912  lea     r12d, [rax+11h]
0x180002916  mov     qword ptr [rsp+198h+var_108+4], r12
0x18000291e  lea     ecx, [rax+3]
0x180002921  mov     dword ptr [rsp+198h+var_108+0Ch], ecx
0x180002928  mov     qword ptr [rsp+198h+var_F8+8], rax
0x180002930  lea     rax, [rsp+198h+pSid]
0x180002938  mov     qword ptr [rsp+198h+var_E8], rax
0x180002940  mov     [rsp+198h+Security.Version], 1
0x180002948  mov     [rsp+198h+Security.AuthnLevel], 6
0x180002950  mov     [rsp+198h+Security.AuthnSvc], 0Ah
0x180002958  mov     [rsp+198h+Security.AuthIdentity], 0
0x180002961  lea     rax, [rsp+198h+var_108]
0x180002969  mov     [rsp+198h+Security.SecurityQos], rax
0x18000296e  mov     [rsp+198h+Template.Version], 1
0x180002979  mov     [rsp+198h+Template.ProtocolSequence], ecx
0x180002980  mov     r9, rdi; Binding
0x180002983  xor     r8d, r8d; Options
0x180002986  lea     rdx, [rsp+198h+Security]; Security
0x18000298b  lea     rcx, [rsp+198h+Template]; Template
0x180002993  call    cs:__imp_RpcBindingCreateW
0x180002999  mov     ebx, eax
0x18000299b  test    eax, eax
0x18000299d  jz      short loc_1800029CE
0x18000299f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029a6  cmp     rcx, rsi
0x1800029a9  jz      loc_180002C49
0x1800029af  test    byte ptr [rcx+1Ch], 1
0x1800029b3  jz      loc_180002C49
0x1800029b9  cmp     byte ptr [rcx+19h], 2
0x1800029bd  jb      loc_180002C49
0x1800029c3  mov     edx, r12d
0x1800029c6  mov     r9d, eax
0x1800029c9  jmp     loc_180002847
0x1800029ce  mov     edx, 9; option
0x1800029d3  lea     r8d, [rdx-8]; optionValue
0x1800029d7  mov     rcx, [rdi]; hBinding
0x1800029da  call    cs:__imp_RpcBindingSetOption
0x1800029e0  mov     ebx, eax
0x1800029e2  test    eax, eax
0x1800029e4  jz      short loc_180002A20
0x1800029e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029ed  cmp     rcx, rsi
0x1800029f0  jz      loc_180002C39
0x1800029f6  test    byte ptr [rcx+1Ch], 1
0x1800029fa  jz      loc_180002C39
0x180002a00  cmp     byte ptr [rcx+19h], 2
0x180002a04  jb      loc_180002C39
0x180002a0a  mov     edx, 12h
0x180002a0f  mov     r9d, eax
0x180002a12  mov     rcx, [rcx+10h]
0x180002a16  call    WPP_SF_D
0x180002a1b  jmp     loc_180002C39
0x180002a20  lea     r8, qword_180005400; IfSpec
0x180002a27  mov     rdx, [rdi]; Binding
0x180002a2a  xor     ecx, ecx; pAsync
0x180002a2c  call    cs:__imp_RpcBindingBind
0x180002a32  mov     ebx, eax
0x180002a34  test    eax, eax
0x180002a36  jz      short loc_180002A63
0x180002a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a3f  cmp     rcx, rsi
0x180002a42  jz      loc_180002C39
0x180002a48  test    byte ptr [rcx+1Ch], 1
0x180002a4c  jz      loc_180002C39
0x180002a52  cmp     byte ptr [rcx+19h], 2
0x180002a56  jb      loc_180002C39
0x180002a5c  mov     edx, 13h
0x180002a61  jmp     short loc_180002A0F
0x180002a63  mov     [rsp+198h+var_120], 0
0x180002a6c  lea     r12, [rdi+8]
0x180002a70  mov     [rsp+198h+var_178], r12
0x180002a75  mov     r9, [rdi]
0x180002a78  xor     r8d, r8d; pReturnValue
0x180002a7b  xor     edx, edx; nProcNum
0x180002a7d  lea     rcx, pProxyInfo; pProxyInfo
0x180002a84  call    cs:__imp_NdrClientCall3
0x180002a8a  mov     rbx, rax
0x180002a8d  mov     [rsp+198h+var_120], rax
0x180002a92  test    eax, eax
0x180002a94  jz      short loc_180002AC8
0x180002a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a9d  cmp     rcx, rsi
0x180002aa0  jz      short loc_180002ABF
0x180002aa2  test    byte ptr [rcx+1Ch], 1
0x180002aa6  jz      short loc_180002ABF
0x180002aa8  cmp     byte ptr [rcx+19h], 2
0x180002aac  jb      short loc_180002ABF
0x180002aae  mov     edx, 14h
0x180002ab3  mov     r9d, ebx
0x180002ab6  mov     rcx, [rcx+10h]
0x180002aba  call    WPP_SF_D
0x180002abf  mov     [rsp+198h+var_168], ebx
0x180002ac3  jmp     loc_180002C30
0x180002ac8  mov     rax, [rsp+198h+var_118]
0x180002ad0  mov     [rdi+0C0h], rax
0x180002ad7  mov     rax, [rsp+198h+var_110]
0x180002adf  mov     [rdi+0B8h], rax
0x180002ae6  mov     rax, [rsp+198h+var_160]
0x180002aeb  mov     [rdi+0A8h], rax
0x180002af2  lea     rax, KAMSS_MeasurementUpdateCallback
0x180002af9  mov     [r13+0], rax
0x180002afd  mov     [r15], rdi
0x180002b00  mov     rcx, rdi
0x180002b03  call    InitializeKaMeasurements
0x180002b08  mov     ebx, eax
0x180002b0a  mov     [rsp+198h+var_168], eax
0x180002b0e  test    eax, eax
0x180002b10  jz      loc_180002BBE
0x180002b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b1d  cmp     rcx, rsi
0x180002b20  jz      short loc_180002B3F
0x180002b22  test    byte ptr [rcx+1Ch], 1
0x180002b26  jz      short loc_180002B3F
0x180002b28  cmp     byte ptr [rcx+19h], 2
0x180002b2c  jb      short loc_180002B3F
0x180002b2e  mov     edx, 16h
0x180002b33  mov     r9d, eax
0x180002b36  mov     rcx, [rcx+10h]
0x180002b3a  call    WPP_SF_D
0x180002b3f  mov     qword ptr [r15], 0
0x180002b46  nop
0x180002b47  mov     [rsp+198h+var_160], 0
0x180002b50  mov     [rsp+198h+var_178], r12
0x180002b55  mov     r9, [rdi]
0x180002b58  xor     r8d, r8d; pReturnValue
0x180002b5b  lea     edx, [r8+1]; nProcNum
0x180002b5f  lea     rcx, pProxyInfo; pProxyInfo
0x180002b66  call    cs:__imp_NdrClientCall3
0x180002b6c  mov     [rsp+198h+var_160], rax
0x180002b71  jmp     loc_180002C30
0x180002b76  lea     rax, WPP_GLOBAL_Control
0x180002b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b84  cmp     rcx, rax
0x180002b87  jz      short loc_180002BAC
0x180002b89  test    byte ptr [rcx+1Ch], 1
0x180002b8d  jz      short loc_180002BAC
0x180002b8f  cmp     byte ptr [rcx+19h], 2
0x180002b93  jb      short loc_180002BAC
0x180002b95  mov     edx, 18h
0x180002b9a  mov     ebx, [rsp+198h+var_168]
0x180002b9e  mov     r9d, ebx
0x180002ba1  mov     rcx, [rcx+10h]
0x180002ba5  call    WPP_SF_D
0x180002baa  jmp     short loc_180002BB0
0x180002bac  mov     ebx, [rsp+198h+var_168]
0x180002bb0  lea     rsi, WPP_GLOBAL_Control
0x180002bb7  mov     rdi, [rsp+198h+var_158]
0x180002bbc  jmp     short loc_180002C30
0x180002bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bc5  cmp     rcx, rsi
0x180002bc8  jz      short loc_180002BE7
0x180002bca  test    byte ptr [rcx+1Ch], 1
0x180002bce  jz      short loc_180002BE7
0x180002bd0  cmp     byte ptr [rcx+19h], 6
0x180002bd4  jb      short loc_180002BE7
0x180002bd6  mov     edx, 17h
0x180002bdb  xor     r9d, r9d
0x180002bde  mov     rcx, [rcx+10h]
0x180002be2  call    WPP_SF_D
0x180002be7  xor     eax, eax
0x180002be9  jmp     loc_180002C8D
0x180002bee  mov     ebx, eax
0x180002bf0  mov     [rsp+198h+var_168], eax
0x180002bf4  lea     rdx, WPP_GLOBAL_Control
0x180002bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c02  cmp     rcx, rdx
0x180002c05  jz      short loc_180002C24
0x180002c07  test    byte ptr [rcx+1Ch], 1
0x180002c0b  jz      short loc_180002C24
0x180002c0d  cmp     byte ptr [rcx+19h], 2
0x180002c11  jb      short loc_180002C24
0x180002c13  mov     edx, 15h
0x180002c18  mov     r9d, eax
0x180002c1b  mov     rcx, [rcx+10h]
0x180002c1f  call    WPP_SF_D
0x180002c24  lea     rsi, WPP_GLOBAL_Control
0x180002c2b  mov     rdi, [rsp+198h+var_158]
0x180002c30  mov     rcx, [rdi]; Binding
0x180002c33  call    cs:__imp_RpcBindingUnbind
0x180002c39  mov     rcx, rdi; Binding
0x180002c3c  call    cs:__imp_RpcBindingFree
0x180002c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c49  test    rdi, rdi
0x180002c4c  jz      short loc_180002C69
0x180002c4e  call    cs:__imp_GetProcessHeap
0x180002c54  mov     rcx, rax; hHeap
0x180002c57  mov     r8, rdi; lpMem
0x180002c5a  xor     edx, edx; dwFlags
0x180002c5c  call    cs:__imp_HeapFree
0x180002c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c69  cmp     rcx, rsi
0x180002c6c  jz      short loc_180002C8B
  ... truncated ...
```
