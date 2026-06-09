# CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)

- ea: `0x180002284`
- end: `0x180002724`
- name: `?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z`
- size: `1184`
- prototype: `__int64 __fastcall(struct _DAC_CREATE_CONTEXT_PARAMS *, RPC_BINDING_HANDLE **)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x180008880`
- `0x180008950`
- `0x180008a60`
- `0x180008b40`
- `0x180009a00`
- `0x18000a430`
- `0x18000ae00`

## callees

- `0x180002284`
- `0x180002b08`
- `0x180002ca4`
- `0x180002ec8`
- `0x180002f10`
- `0x18000a8b8`
- `0x18000a9e0`
- `0x18000bbc2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002334`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002334`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c022`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c022`
- `RPCRT4!NdrClientCall3` at `0x180002401`
- `RPCRT4!NdrClientCall3` at `0x18000243e`
- `RPCRT4!NdrClientCall3` at `0x18000247f`
- `RPCRT4!NdrClientCall3` at `0x1800024d3`
- `RPCRT4!NdrClientCall3` at `0x180002553`
- `RPCRT4!NdrClientCall3` at `0x1800025b3`
- `RPCRT4!NdrClientCall3` at `0x180002401`
- `RPCRT4!NdrClientCall3` at `0x18000243e`
- `RPCRT4!NdrClientCall3` at `0x18000247f`
- `RPCRT4!NdrClientCall3` at `0x1800024d3`
- `RPCRT4!NdrClientCall3` at `0x180002553`
- `RPCRT4!NdrClientCall3` at `0x1800025b3`
- `RPCRT4!RpcBindingSetOption` at `0x180002609`
- `RPCRT4!RpcBindingSetOption` at `0x180002609`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800022e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800022f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800022f7`

## pseudocode

```c
__int64 __fastcall CreateContext(struct _DAC_CREATE_CONTEXT_PARAMS *a1, RPC_BINDING_HANDLE **a2)
{
  HANDLE ProcessHeap; // rax
  RPC_BINDING_HANDLE *v5; // rax
  RPC_BINDING_HANDLE *v6; // rsi
  int RpcBinding; // ebx
  int v8; // r15d
  __int64 v9; // rdx
  __int64 v10; // r8
  CLIENT_CALL_RETURN v11; // rax
  CLIENT_CALL_RETURN v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  int v16; // edx
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // rcx
  int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rax
  int v23; // ecx
  int v24; // edx
  __int64 v25; // r8
  __int64 v26; // r10
  int v27; // eax
  unsigned int *v28; // rcx
  void **v29; // rcx
  void **v30; // rcx
  unsigned int i; // r14d
  void *v33; // [rsp+78h] [rbp-80h] BYREF
  void *v34; // [rsp+80h] [rbp-78h] BYREF
  CLIENT_CALL_RETURN v35; // [rsp+88h] [rbp-70h]
  CLIENT_CALL_RETURN v36; // [rsp+90h] [rbp-68h]
  CLIENT_CALL_RETURN v37; // [rsp+98h] [rbp-60h]
  CLIENT_CALL_RETURN v38; // [rsp+A0h] [rbp-58h]
  CLIENT_CALL_RETURN v39; // [rsp+A8h] [rbp-50h]
  CLIENT_CALL_RETURN v40; // [rsp+B0h] [rbp-48h]
  RPC_BINDING_HANDLE *v41; // [rsp+B8h] [rbp-40h]
  unsigned int v42; // [rsp+110h] [rbp+18h] BYREF

  v34 = 0;
  v42 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  *a2 = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (RPC_BINDING_HANDLE *)HeapAlloc(ProcessHeap, 0, 0xA8u);
  v6 = v5;
  v41 = v5;
  if ( v5 )
  {
    v8 = 0;
    memset_0(v5, 0, 0xA8u);
    GetSetActivityId((struct _GUID *)v6 + 7);
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 2));
    *((_WORD *)v6 + 4) = 3503;
    v6[7] = 0;
    *((_DWORD *)v6 + 16) = 0;
    v6[9] = 0;
    *((_DWORD *)v6 + 21) = 1;
    *((_DWORD *)v6 + 20) = 1;
    *((_DWORD *)v6 + 24) = *(_DWORD *)a1;
    RpcBinding = DacGetRpcBinding(*(unsigned int *)a1, v6);
    if ( RpcBinding )
      goto LABEL_35;
    if ( *(_DWORD *)a1 == 1 )
    {
      v22 = *((_QWORD *)a1 + 4);
      v23 = *((_DWORD *)a1 + 7);
      v24 = *((_DWORD *)a1 + 6);
      v25 = *((_QWORD *)a1 + 2);
      v26 = *((_QWORD *)a1 + 1);
      v40.Simple = 0;
      v12.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
                      0,
                      0,
                      *v6,
                      v26,
                      v25,
                      v6 + 14,
                      v24,
                      v23,
                      v22,
                      v6 + 7).Pointer;
      v40.Pointer = v12.Pointer;
    }
    else if ( *(_DWORD *)a1 == 2 )
    {
      v18 = *((_DWORD *)a1 + 8);
      v19 = *((_QWORD *)a1 + 3);
      v20 = *((_DWORD *)a1 + 4);
      v21 = *((_QWORD *)a1 + 1);
      v39.Simple = 0;
      v12.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
                      1u,
                      0,
                      *v6,
                      v21,
                      v20,
                      v19,
                      v6 + 14,
                      v18,
                      &v34,
                      v6 + 7,
                      &v42,
                      &v33).Pointer;
      v39.Pointer = v12.Pointer;
    }
    else if ( *(_DWORD *)a1 == 3 )
    {
      v14 = *((_QWORD *)a1 + 4);
      v15 = *((_DWORD *)a1 + 7);
      v16 = *((_DWORD *)a1 + 6);
      v17 = *((_QWORD *)a1 + 2);
      v38.Simple = 0;
      v12.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
                      9u,
                      0,
                      *((_QWORD *)a1 + 1),
                      v17,
                      v16,
                      v15,
                      v14,
                      v6 + 7).Pointer;
      v38.Pointer = v12.Pointer;
    }
    else if ( *(_DWORD *)a1 == 4 )
    {
      v13 = *((_QWORD *)a1 + 1);
      v37.Simple = 0;
      v12.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&DevicePresenceChallenge_ProxyInfo,
                      0,
                      0,
                      *v6,
                      v13,
                      v6 + 14,
                      v6 + 7).Pointer;
      v37.Pointer = v12.Pointer;
    }
    else
    {
      if ( *(_DWORD *)a1 != 5 )
      {
        if ( *(_DWORD *)a1 == 6 )
        {
          v35.Simple = 0;
          v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&Inbound_ProxyInfo, 0, 0, *v6, v6 + 14, v6 + 7).Pointer;
          RpcBinding = (int)v11.Pointer;
          v35.Pointer = v11.Pointer;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *(unsigned int *)a1);
          RpcBinding = -2147467259;
        }
        goto LABEL_24;
      }
      v36.Simple = 0;
      v12.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
                      0xCu,
                      0,
                      *v6,
                      v6 + 14,
                      v6 + 7).Pointer;
      v36.Pointer = v12.Pointer;
    }
    RpcBinding = (int)v12.Pointer;
LABEL_24:
    if ( RpcBinding < 0 )
      goto LABEL_36;
    v27 = RpcBindingSetOption(*v6, 0xDu, 1u);
    if ( v27 )
    {
      if ( v27 >= 0 )
        v27 = (unsigned __int16)v27 | 0x80010000;
      RpcBinding = v27;
    }
    else
    {
      *a2 = v6;
      if ( *(_DWORD *)a1 == 2 )
      {
        **((_QWORD **)a1 + 5) = v34;
        v34 = 0;
        v28 = (unsigned int *)*((_QWORD *)a1 + 6);
        if ( v28 )
          *v28 = v42;
        v29 = (void **)*((_QWORD *)a1 + 7);
        if ( v29 )
          *v29 = v33;
        else
          v8 = 1;
      }
    }
LABEL_35:
    if ( RpcBinding >= 0 )
      goto LABEL_41;
    goto LABEL_36;
  }
  RpcBinding = -2147024882;
LABEL_36:
  if ( v6 )
    ReleaseClientContext((struct _DAC_CLIENT_CONTEXT *)v6);
  if ( v34 )
    MIDL_user_free(v34);
  v8 = 1;
LABEL_41:
  if ( v8 )
  {
    v30 = (void **)v33;
    if ( v33 )
    {
      for ( i = 0; i < v42; ++i )
      {
        if ( v30[6 * i + 5] )
        {
          MIDL_user_free(v30[6 * i + 5]);
          *((_QWORD *)v33 + 6 * i + 5) = 0;
          v30 = (void **)v33;
        }
        if ( v30[6 * i + 3] )
        {
          MIDL_user_free(v30[6 * i + 3]);
          *((_QWORD *)v33 + 6 * i + 3) = 0;
          v30 = (void **)v33;
        }
      }
      MIDL_user_free(v30);
    }
  }
  return (unsigned int)RpcBinding;
}

```

## disassembly

```asm
0x180002284  mov     rax, rsp
0x180002287  mov     [rax+10h], rdx
0x18000228b  mov     [rax+8], rcx
0x18000228f  push    rbx
0x180002290  push    rsi
0x180002291  push    rdi
0x180002292  push    r12
0x180002294  push    r13
0x180002296  push    r14
0x180002298  push    r15
0x18000229a  sub     rsp, 0C0h
0x1800022a1  mov     r12, rdx
0x1800022a4  mov     r14, rcx
0x1800022a7  xor     edi, edi
0x1800022a9  mov     [rax-78h], rdi
0x1800022ad  mov     [rax+18h], edi
0x1800022b0  mov     [rax-80h], rdi
0x1800022b4  lea     rax, WPP_GLOBAL_Control
0x1800022bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022c2  cmp     rcx, rax
0x1800022c5  jz      short loc_1800022E0
0x1800022c7  cmp     byte ptr [rcx+19h], 4
0x1800022cb  jb      short loc_1800022E0
0x1800022cd  lea     edx, [rdi+19h]
0x1800022d0  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x1800022d7  mov     rcx, [rcx+10h]
0x1800022db  call    WPP_SF_s
0x1800022e0  mov     [r12], rdi
0x1800022e4  call    cs:__imp_GetProcessHeap
0x1800022ea  mov     rcx, rax; hHeap
0x1800022ed  mov     ebx, 0A8h
0x1800022f2  mov     r8d, ebx; dwBytes
0x1800022f5  xor     edx, edx; dwFlags
0x1800022f7  call    cs:__imp_HeapAlloc
0x1800022fd  mov     rsi, rax
0x180002300  mov     [rsp+0F8h+var_40], rax
0x180002308  test    rax, rax
0x18000230b  jnz     short loc_180002317
0x18000230d  mov     ebx, 8007000Eh
0x180002312  jmp     loc_180002671
0x180002317  mov     r15d, edi
0x18000231a  mov     r8, rbx; Size
0x18000231d  xor     edx, edx; Val
0x18000231f  mov     rcx, rsi; void *
0x180002322  call    memset_0
0x180002327  lea     rcx, [rsi+70h]; struct _GUID *
0x18000232b  call    ?GetSetActivityId@@YAXPEAU_GUID@@@Z; GetSetActivityId(_GUID *)
0x180002330  lea     rcx, [rsi+10h]; lpCriticalSection
0x180002334  call    cs:__imp_InitializeCriticalSection
0x18000233a  mov     word ptr [rsi+8], 0DAFh
0x180002340  lea     r13, [rsi+38h]
0x180002344  mov     [r13+0], rdi
0x180002348  mov     [rsi+40h], edi
0x18000234b  mov     [rsi+48h], rdi
0x18000234f  mov     dword ptr [rsi+54h], 1
0x180002356  mov     dword ptr [rsi+50h], 1
0x18000235d  mov     eax, [r14]
0x180002360  mov     [rsi+60h], eax
0x180002363  mov     rdx, rsi
0x180002366  mov     ecx, [r14]
0x180002369  call    ?DacGetRpcBinding@@YAJW4DAC_OP_TYPE@@PEAPEAX@Z; DacGetRpcBinding(DAC_OP_TYPE,void * *)
0x18000236e  mov     ebx, eax
0x180002370  test    eax, eax
0x180002372  jnz     loc_18000266D
0x180002378  mov     ecx, [r14]
0x18000237b  sub     ecx, 1
0x18000237e  jz      loc_180002563
0x180002384  sub     ecx, 1
0x180002387  jz      loc_1800024E6
0x18000238d  sub     ecx, 1
0x180002390  jz      loc_180002492
0x180002396  sub     ecx, 1
0x180002399  jz      loc_180002451
0x18000239f  sub     ecx, 1
0x1800023a2  jz      short loc_180002417
0x1800023a4  cmp     ecx, 1
0x1800023a7  jz      short loc_1800023DC
0x1800023a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b0  lea     rax, WPP_GLOBAL_Control
0x1800023b7  cmp     rcx, rax
0x1800023ba  jz      short loc_1800023CE
0x1800023bc  cmp     byte ptr [rcx+19h], 2
0x1800023c0  jb      short loc_1800023CE
0x1800023c2  mov     r9d, [r14]
0x1800023c5  mov     rcx, [rcx+10h]
0x1800023c9  call    WPP_SF_d
0x1800023ce  mov     ebx, 80004005h
0x1800023d3  mov     [rsp+0F8h+var_88], ebx
0x1800023d7  jmp     loc_1800025C7
0x1800023dc  mov     [rsp+0F8h+var_70], rdi
0x1800023e4  mov     [rsp+0F8h+var_D0], r13
0x1800023e9  lea     r9, [rsi+70h]
0x1800023ed  mov     [rsp+0F8h+var_D8], r9
0x1800023f2  mov     r9, [rsi]
0x1800023f5  xor     r8d, r8d; pReturnValue
0x1800023f8  xor     edx, edx; nProcNum
0x1800023fa  lea     rcx, ?Inbound_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002401  call    cs:__imp_NdrClientCall3
0x180002407  mov     rbx, rax
0x18000240a  mov     [rsp+0F8h+var_70], rax
0x180002412  jmp     loc_1800025C3
0x180002417  mov     [rsp+0F8h+var_68], rdi
0x18000241f  mov     [rsp+0F8h+var_D0], r13
0x180002424  lea     r9, [rsi+70h]
0x180002428  mov     [rsp+0F8h+var_D8], r9
0x18000242d  mov     r9, [rsi]
0x180002430  xor     r8d, r8d; pReturnValue
0x180002433  lea     edx, [r8+0Ch]; nProcNum
0x180002437  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000243e  call    cs:__imp_NdrClientCall3
0x180002444  mov     [rsp+0F8h+var_68], rax
0x18000244c  jmp     loc_1800025C1
0x180002451  mov     rax, [r14+8]
0x180002455  mov     [rsp+0F8h+var_60], rdi
0x18000245d  mov     [rsp+0F8h+var_C8], r13
0x180002462  lea     r9, [rsi+70h]
0x180002466  mov     [rsp+0F8h+var_D0], r9
0x18000246b  mov     [rsp+0F8h+var_D8], rax
0x180002470  mov     r9, [rsi]
0x180002473  xor     r8d, r8d; pReturnValue
0x180002476  xor     edx, edx; nProcNum
0x180002478  lea     rcx, ?DevicePresenceChallenge_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000247f  call    cs:__imp_NdrClientCall3
0x180002485  mov     [rsp+0F8h+var_60], rax
0x18000248d  jmp     loc_1800025C1
0x180002492  mov     rax, [r14+20h]
0x180002496  mov     ecx, [r14+1Ch]
0x18000249a  mov     edx, [r14+18h]
0x18000249e  mov     r8, [r14+10h]
0x1800024a2  mov     [rsp+0F8h+var_58], rdi
0x1800024aa  mov     [rsp+0F8h+var_B8], r13
0x1800024af  mov     [rsp+0F8h+var_C0], rax
0x1800024b4  mov     dword ptr [rsp+0F8h+var_C8], ecx
0x1800024b8  mov     dword ptr [rsp+0F8h+var_D0], edx
0x1800024bc  mov     [rsp+0F8h+var_D8], r8
0x1800024c1  mov     r9, [r14+8]
0x1800024c5  xor     r8d, r8d; pReturnValue
0x1800024c8  lea     edx, [r8+9]; nProcNum
0x1800024cc  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800024d3  call    cs:__imp_NdrClientCall3
0x1800024d9  mov     [rsp+0F8h+var_58], rax
0x1800024e1  jmp     loc_1800025C1
0x1800024e6  mov     eax, [r14+20h]
0x1800024ea  mov     rcx, [r14+18h]
0x1800024ee  mov     edx, [r14+10h]
0x1800024f2  mov     r8, [r14+8]
0x1800024f6  mov     [rsp+0F8h+var_50], rdi
0x1800024fe  lea     r9, [rsp+0F8h+var_80]
0x180002503  mov     [rsp+0F8h+var_98], r9
0x180002508  lea     r9, [rsp+0F8h+arg_10]
0x180002510  mov     [rsp+0F8h+var_A0], r9
0x180002515  mov     [rsp+0F8h+var_A8], r13
0x18000251a  lea     r9, [rsp+0F8h+var_78]
0x180002522  mov     [rsp+0F8h+var_B0], r9
0x180002527  mov     dword ptr [rsp+0F8h+var_B8], eax
0x18000252b  lea     r9, [rsi+70h]
0x18000252f  mov     [rsp+0F8h+var_C0], r9
0x180002534  mov     [rsp+0F8h+var_C8], rcx
0x180002539  mov     dword ptr [rsp+0F8h+var_D0], edx
0x18000253d  mov     [rsp+0F8h+var_D8], r8
0x180002542  mov     r9, [rsi]
0x180002545  xor     r8d, r8d; pReturnValue
0x180002548  lea     edx, [r8+1]; nProcNum
0x18000254c  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180002553  call    cs:__imp_NdrClientCall3
0x180002559  mov     [rsp+0F8h+var_50], rax
0x180002561  jmp     short loc_1800025C1
0x180002563  mov     rax, [r14+20h]
0x180002567  mov     ecx, [r14+1Ch]
0x18000256b  mov     edx, [r14+18h]
0x18000256f  mov     r8, [r14+10h]
0x180002573  mov     r10, [r14+8]
0x180002577  mov     [rsp+0F8h+var_48], rdi
0x18000257f  mov     [rsp+0F8h+var_A8], r13
0x180002584  mov     [rsp+0F8h+var_B0], rax
0x180002589  mov     dword ptr [rsp+0F8h+var_B8], ecx
0x18000258d  mov     dword ptr [rsp+0F8h+var_C0], edx
0x180002591  lea     r9, [rsi+70h]
0x180002595  mov     [rsp+0F8h+var_C8], r9
0x18000259a  mov     [rsp+0F8h+var_D0], r8
0x18000259f  mov     [rsp+0F8h+var_D8], r10
0x1800025a4  mov     r9, [rsi]
0x1800025a7  xor     r8d, r8d; pReturnValue
0x1800025aa  xor     edx, edx; nProcNum
0x1800025ac  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800025b3  call    cs:__imp_NdrClientCall3
0x1800025b9  mov     [rsp+0F8h+var_48], rax
0x1800025c1  mov     ebx, eax
0x1800025c3  mov     [rsp+0F8h+var_88], eax
0x1800025c7  jmp     short loc_1800025F9
0x1800025c9  cmp     eax, 1
0x1800025cc  jl      short loc_1800025D6
0x1800025ce  movzx   eax, ax
0x1800025d1  or      eax, 80010000h
0x1800025d6  mov     ebx, eax
0x1800025d8  mov     [rsp+0F8h+var_88], eax
0x1800025dc  xor     edi, edi
0x1800025de  mov     r12, [rsp+0F8h+arg_8]
0x1800025e6  mov     r14, [rsp+0F8h+arg_0]
0x1800025ee  mov     r15d, edi
0x1800025f1  mov     rsi, [rsp+0F8h+var_40]
0x1800025f9  test    ebx, ebx
0x1800025fb  js      short loc_180002671
0x1800025fd  mov     edx, 0Dh; option
0x180002602  lea     r8d, [rdx-0Ch]; optionValue
0x180002606  mov     rcx, [rsi]; hBinding
0x180002609  call    cs:__imp_RpcBindingSetOption
0x18000260f  test    eax, eax
0x180002611  jz      short loc_180002621
0x180002613  js      short loc_18000261D
0x180002615  movzx   eax, ax
0x180002618  or      eax, 80010000h
0x18000261d  mov     ebx, eax
0x18000261f  jmp     short loc_18000266D
0x180002621  mov     [r12], rsi
0x180002625  cmp     dword ptr [r14], 2
0x180002629  jnz     short loc_18000266D
0x18000262b  mov     rcx, [r14+28h]
0x18000262f  mov     rax, [rsp+0F8h+var_78]
0x180002637  mov     [rcx], rax
0x18000263a  mov     [rsp+0F8h+var_78], rdi
0x180002642  mov     rcx, [r14+30h]
0x180002646  test    rcx, rcx
0x180002649  jz      short loc_180002654
0x18000264b  mov     eax, [rsp+0F8h+arg_10]
0x180002652  mov     [rcx], eax
0x180002654  mov     rcx, [r14+38h]
0x180002658  test    rcx, rcx
0x18000265b  jz      short loc_180002667
0x18000265d  mov     rax, [rsp+0F8h+var_80]
0x180002662  mov     [rcx], rax
0x180002665  jmp     short loc_18000266D
0x180002667  mov     r15d, 1
0x18000266d  test    ebx, ebx
0x18000266f  jns     short loc_180002696
0x180002671  test    rsi, rsi
0x180002674  jz      short loc_18000267E
0x180002676  mov     rcx, rsi; struct _DAC_CLIENT_CONTEXT *
0x180002679  call    ?ReleaseClientContext@@YAKPEAU_DAC_CLIENT_CONTEXT@@@Z; ReleaseClientContext(_DAC_CLIENT_CONTEXT *)
0x18000267e  mov     rcx, [rsp+0F8h+var_78]; void *
0x180002686  test    rcx, rcx
0x180002689  jz      short loc_180002690
0x18000268b  call    MIDL_user_free
0x180002690  mov     r15d, 1
0x180002696  test    r15d, r15d
0x180002699  jz      short loc_18000270F
0x18000269b  mov     rcx, [rsp+0F8h+var_80]
0x1800026a0  test    rcx, rcx
0x1800026a3  jz      short loc_18000270F
0x1800026a5  mov     r14d, edi
0x1800026a8  cmp     [rsp+0F8h+arg_10], edi
0x1800026af  jbe     short loc_18000270A
0x1800026b1  mov     eax, r14d
0x1800026b4  lea     rsi, [rax+rax*2]
0x1800026b8  add     rsi, rsi
0x1800026bb  mov     rax, [rcx+rsi*8+28h]
0x1800026c0  test    rax, rax
0x1800026c3  jz      short loc_1800026DC
0x1800026c5  mov     rcx, rax; void *
0x1800026c8  call    MIDL_user_free
0x1800026cd  mov     rax, [rsp+0F8h+var_80]
0x1800026d2  mov     [rax+rsi*8+28h], rdi
0x1800026d7  mov     rcx, [rsp+0F8h+var_80]
0x1800026dc  mov     rax, [rcx+rsi*8+18h]
0x1800026e1  test    rax, rax
0x1800026e4  jz      short loc_1800026FD
0x1800026e6  mov     rcx, rax; void *
0x1800026e9  call    MIDL_user_free
0x1800026ee  mov     rax, [rsp+0F8h+var_80]
0x1800026f3  mov     [rax+rsi*8+18h], rdi
0x1800026f8  mov     rcx, [rsp+0F8h+var_80]; void *
0x1800026fd  inc     r14d
0x180002700  cmp     r14d, [rsp+0F8h+arg_10]
0x180002708  jb      short loc_1800026B1
0x18000270a  call    MIDL_user_free
0x18000270f  mov     eax, ebx
0x180002711  add     rsp, 0C0h
0x180002718  pop     r15
0x18000271a  pop     r14
0x18000271c  pop     r13
0x18000271e  pop     r12
0x180002720  pop     rdi
0x180002721  pop     rsi
0x180002722  pop     rbx
0x180002723  retn
0x18000c014  push    rbp
0x18000c016  sub     rsp, 70h
0x18000c01a  mov     rbp, rdx
0x18000c01d  mov     rcx, [rcx]
0x18000c020  mov     ecx, [rcx]; ExceptionCode
0x18000c022  call    cs:__imp_I_RpcExceptionFilter
0x18000c028  nop
0x18000c029  add     rsp, 70h
0x18000c02d  pop     rbp
0x18000c02e  retn
```
