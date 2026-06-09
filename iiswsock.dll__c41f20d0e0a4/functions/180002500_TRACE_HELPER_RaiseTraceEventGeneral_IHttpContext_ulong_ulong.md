# TRACE_HELPER::RaiseTraceEventGeneral(IHttpContext *,ulong,ulong)

- ea: `0x180002500`
- end: `0x180002826`
- name: `?RaiseTraceEventGeneral@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KK@Z`
- size: `806`
- prototype: `void __fastcall(TRACE_HELPER *__hidden this, struct IHttpContext *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ae8`
- `0x1800060c0`
- `0x1800063d0`
- `0x180007674`

## callees

- `0x180002500`
- `0x180009010`

## string_xrefs

- `0x1800025d9`: `WEBSOCKET_WRITE_FRAGMENT_END_SUCCESS`
- `0x1800026a0`: `WEBSOCKET_READ_FRAGMENT_END_SUCCESS`
- `0x180002767`: `WEBSOCKET_READ_FRAGMENT_START`

## pseudocode

```c
void __fastcall TRACE_HELPER::RaiseTraceEventGeneral(TRACE_HELPER *this, struct IHttpContext *a2, int a3, int a4)
{
  int (__fastcall ***v6)(_QWORD, GUID **); // rax
  int (__fastcall **v7)(_QWORD, GUID **); // rcx
  __int64 v8; // rax
  __int64 *v9; // rcx
  const wchar_t *v10; // rax
  int (__fastcall ***v11)(_QWORD, GUID **); // rax
  int (__fastcall **v12)(_QWORD, GUID **); // rcx
  __int64 v13; // rax
  int (__fastcall ***v14)(_QWORD, GUID **); // rax
  int (__fastcall **v15)(_QWORD, GUID **); // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  void (__fastcall *v18)(__int64 *, _QWORD *); // rax
  GUID *v19; // [rsp+20h] [rbp-89h] BYREF
  __int128 v20; // [rsp+28h] [rbp-81h]
  _QWORD v21[2]; // [rsp+40h] [rbp-69h] BYREF
  GUID *v22; // [rsp+50h] [rbp-59h]
  __int64 v23; // [rsp+58h] [rbp-51h]
  const wchar_t *v24; // [rsp+60h] [rbp-49h]
  int v25; // [rsp+68h] [rbp-41h]
  int v26; // [rsp+6Ch] [rbp-3Dh]
  __int128 v27; // [rsp+70h] [rbp-39h]
  int v28; // [rsp+80h] [rbp-29h]
  int v29; // [rsp+84h] [rbp-25h]
  __int64 v30; // [rsp+88h] [rbp-21h]
  const wchar_t **v31; // [rsp+90h] [rbp-19h]
  const wchar_t *v32; // [rsp+A0h] [rbp-9h] BYREF
  int v33; // [rsp+A8h] [rbp-1h]
  __int64 v34; // [rsp+B0h] [rbp+7h]
  int v35; // [rsp+B8h] [rbp+Fh]
  __int64 v36; // [rsp+C0h] [rbp+17h]
  const wchar_t *v37; // [rsp+C8h] [rbp+1Fh]
  int v38; // [rsp+D0h] [rbp+27h]
  int *v39; // [rsp+D8h] [rbp+2Fh]
  int v40; // [rsp+E0h] [rbp+37h]
  __int64 v41; // [rsp+E8h] [rbp+3Fh]
  int v42; // [rsp+120h] [rbp+77h] BYREF

  switch ( a3 )
  {
    case 16:
      v14 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v19 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v15 = *v14;
      v20 = 0;
      if ( (*v15)(v14, &v19) >= 0 && DWORD2(v20) && DWORD1(v20) >= 5 && ((_DWORD)v20 == 0x4000 || (v20 & 0x4000) != 0) )
      {
        v16 = *(_QWORD *)a2;
        v42 = a4;
        v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v16 + 272))(a2);
        v23 = 5;
        v22 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
        v24 = L"WEBSOCKET_READ_FRAGMENT_START";
        v25 = 1;
        v29 = 1;
        v32 = L"ContextId";
        v10 = L"BufferSize";
        goto LABEL_22;
      }
      break;
    case 18:
      v11 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v19 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v12 = *v11;
      v20 = 0;
      if ( (*v12)(v11, &v19) >= 0 && DWORD2(v20) && DWORD1(v20) >= 5 && ((_DWORD)v20 == 0x4000 || (v20 & 0x4000) != 0) )
      {
        v13 = *(_QWORD *)a2;
        v42 = a4;
        v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v13 + 272))(a2);
        v23 = 7;
        v22 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
        v24 = L"WEBSOCKET_READ_FRAGMENT_END_SUCCESS";
        v25 = 1;
        v29 = 1;
        v32 = L"ContextId";
        v10 = L"BytesReceived";
        goto LABEL_22;
      }
      break;
    case 34:
      v6 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v19 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v7 = *v6;
      v20 = 0;
      if ( (*v7)(v6, &v19) >= 0 && DWORD2(v20) && DWORD1(v20) >= 5 && ((_DWORD)v20 == 0x4000 || (v20 & 0x4000) != 0) )
      {
        v8 = *(_QWORD *)a2;
        v42 = a4;
        v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 272))(a2);
        v23 = 11;
        v22 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
        v24 = L"WEBSOCKET_WRITE_FRAGMENT_END_SUCCESS";
        v25 = 1;
        v29 = 1;
        v32 = L"ContextId";
        v10 = L"BytesSent";
LABEL_22:
        v37 = v10;
        v21[1] = 0x4000;
        v39 = &v42;
        v30 = 2;
        v31 = &v32;
        v17 = *v9;
        v21[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v26 = 5;
        v27 = 0;
        v18 = *(void (__fastcall **)(__int64 *, _QWORD *))(v17 + 16);
        v28 = 0;
        v33 = 72;
        v34 = 0;
        v35 = 16;
        v36 = 0;
        v38 = 19;
        v40 = 4;
        v41 = 0;
        v18(v9, v21);
      }
      break;
  }
}

```

## disassembly

```asm
0x180002500  mov     [rsp-8+arg_0], rbx
0x180002505  mov     [rsp-8+arg_8], rsi
0x18000250a  push    rbp
0x18000250b  push    r14
0x18000250d  push    r15
0x18000250f  lea     rbp, [rsp-47h]
0x180002514  sub     rsp, 0F0h
0x18000251b  mov     r15d, r9d
0x18000251e  mov     rsi, rdx
0x180002521  cmp     r8d, 10h
0x180002525  jz      loc_1800026CD
0x18000252b  cmp     r8d, 12h
0x18000252f  jz      loc_180002606
0x180002535  cmp     r8d, 22h ; '"'
0x180002539  jnz     loc_18000280D
0x18000253f  mov     rax, [rdx]
0x180002542  mov     rcx, rdx
0x180002545  mov     rax, [rax+110h]
0x18000254c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002551  mov     r8, rax
0x180002554  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000255b  xorps   xmm0, xmm0
0x18000255e  mov     [rsp+100h+var_E0], r14
0x180002563  lea     rdx, [rsp+100h+var_E0]
0x180002568  mov     rcx, [rax]
0x18000256b  movdqu  [rsp+100h+var_D8], xmm0
0x180002571  mov     rax, [rcx]
0x180002574  mov     rcx, r8
0x180002577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257c  test    eax, eax
0x18000257e  js      loc_18000280D
0x180002584  cmp     dword ptr [rbp+57h+var_D8+8], 0
0x180002588  jz      loc_18000280D
0x18000258e  cmp     dword ptr [rbp+57h+var_D8+4], 5
0x180002592  jb      loc_18000280D
0x180002598  mov     ebx, 4000h
0x18000259d  cmp     dword ptr [rsp+100h+var_D8], ebx
0x1800025a1  jz      short loc_1800025AD
0x1800025a3  test    dword ptr [rsp+100h+var_D8], ebx
0x1800025a7  jz      loc_18000280D
0x1800025ad  mov     rax, [rsi]
0x1800025b0  mov     rcx, rsi
0x1800025b3  mov     [rbp+57h+arg_10], r15d
0x1800025b7  mov     rax, [rax+110h]
0x1800025be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c3  mov     rcx, rax
0x1800025c6  mov     [rbp+57h+var_A8], 0Bh
0x1800025ce  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800025d5  mov     [rbp+57h+var_B0], rax
0x1800025d9  lea     rax, aWebsocketWrite_1; "WEBSOCKET_WRITE_FRAGMENT_END_SUCCESS"
0x1800025e0  mov     [rbp+57h+var_A0], rax
0x1800025e4  mov     eax, 1
0x1800025e9  mov     [rbp+57h+var_98], eax
0x1800025ec  mov     [rbp+57h+var_7C], eax
0x1800025ef  lea     rax, aContextid; "ContextId"
0x1800025f6  mov     [rbp+57h+var_60], rax
0x1800025fa  lea     rax, aBytessent; "BytesSent"
0x180002601  jmp     loc_18000278F
0x180002606  mov     rax, [rdx]
0x180002609  mov     rcx, rsi
0x18000260c  mov     rax, [rax+110h]
0x180002613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002618  mov     r8, rax
0x18000261b  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002622  xorps   xmm0, xmm0
0x180002625  mov     [rsp+100h+var_E0], r14
0x18000262a  lea     rdx, [rsp+100h+var_E0]
0x18000262f  mov     rcx, [rax]
0x180002632  movdqu  [rsp+100h+var_D8], xmm0
0x180002638  mov     rax, [rcx]
0x18000263b  mov     rcx, r8
0x18000263e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002643  test    eax, eax
0x180002645  js      loc_18000280D
0x18000264b  cmp     dword ptr [rbp+57h+var_D8+8], 0
0x18000264f  jz      loc_18000280D
0x180002655  cmp     dword ptr [rbp+57h+var_D8+4], 5
0x180002659  jb      loc_18000280D
0x18000265f  mov     ebx, 4000h
0x180002664  cmp     dword ptr [rsp+100h+var_D8], ebx
0x180002668  jz      short loc_180002674
0x18000266a  test    dword ptr [rsp+100h+var_D8], ebx
0x18000266e  jz      loc_18000280D
0x180002674  mov     rax, [rsi]
0x180002677  mov     rcx, rsi
0x18000267a  mov     [rbp+57h+arg_10], r15d
0x18000267e  mov     rax, [rax+110h]
0x180002685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268a  mov     rcx, rax
0x18000268d  mov     [rbp+57h+var_A8], 7
0x180002695  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000269c  mov     [rbp+57h+var_B0], rax
0x1800026a0  lea     rax, aWebsocketReadF_2; "WEBSOCKET_READ_FRAGMENT_END_SUCCESS"
0x1800026a7  mov     [rbp+57h+var_A0], rax
0x1800026ab  mov     eax, 1
0x1800026b0  mov     [rbp+57h+var_98], eax
0x1800026b3  mov     [rbp+57h+var_7C], eax
0x1800026b6  lea     rax, aContextid; "ContextId"
0x1800026bd  mov     [rbp+57h+var_60], rax
0x1800026c1  lea     rax, aBytesreceived; "BytesReceived"
0x1800026c8  jmp     loc_18000278F
0x1800026cd  mov     rax, [rdx]
0x1800026d0  mov     rcx, rsi
0x1800026d3  mov     rax, [rax+110h]
0x1800026da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026df  mov     r8, rax
0x1800026e2  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800026e9  xorps   xmm0, xmm0
0x1800026ec  mov     [rsp+100h+var_E0], r14
0x1800026f1  lea     rdx, [rsp+100h+var_E0]
0x1800026f6  mov     rcx, [rax]
0x1800026f9  movdqu  [rsp+100h+var_D8], xmm0
0x1800026ff  mov     rax, [rcx]
0x180002702  mov     rcx, r8
0x180002705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000270a  test    eax, eax
0x18000270c  js      loc_18000280D
0x180002712  cmp     dword ptr [rbp+57h+var_D8+8], 0
0x180002716  jz      loc_18000280D
0x18000271c  cmp     dword ptr [rbp+57h+var_D8+4], 5
0x180002720  jb      loc_18000280D
0x180002726  mov     ebx, 4000h
0x18000272b  cmp     dword ptr [rsp+100h+var_D8], ebx
0x18000272f  jz      short loc_18000273B
0x180002731  test    dword ptr [rsp+100h+var_D8], ebx
0x180002735  jz      loc_18000280D
0x18000273b  mov     rax, [rsi]
0x18000273e  mov     rcx, rsi
0x180002741  mov     [rbp+57h+arg_10], r15d
0x180002745  mov     rax, [rax+110h]
0x18000274c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002751  mov     rcx, rax
0x180002754  mov     [rbp+57h+var_A8], 5
0x18000275c  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180002763  mov     [rbp+57h+var_B0], rax
0x180002767  lea     rax, aWebsocketReadF; "WEBSOCKET_READ_FRAGMENT_START"
0x18000276e  mov     [rbp+57h+var_A0], rax
0x180002772  mov     eax, 1
0x180002777  mov     [rbp+57h+var_98], eax
0x18000277a  mov     [rbp+57h+var_7C], eax
0x18000277d  lea     rax, aContextid; "ContextId"
0x180002784  mov     [rbp+57h+var_60], rax
0x180002788  lea     rax, aBuffersize; "BufferSize"
0x18000278f  mov     [rbp+57h+var_38], rax
0x180002793  lea     rdx, [rbp+57h+var_C0]
0x180002797  lea     rax, [rbp+57h+arg_10]
0x18000279b  mov     [rbp+57h+var_B8], rbx
0x18000279f  mov     [rbp+57h+var_28], rax
0x1800027a3  xorps   xmm0, xmm0
0x1800027a6  lea     rax, [rbp+57h+var_60]
0x1800027aa  mov     [rbp+57h+var_78], 2
0x1800027b2  mov     [rbp+57h+var_70], rax
0x1800027b6  mov     rax, [rcx]
0x1800027b9  mov     [rbp+57h+var_C0], r14
0x1800027bd  mov     [rbp+57h+var_94], 5
0x1800027c4  movdqa  [rbp+57h+var_90], xmm0
0x1800027c9  mov     rax, [rax+10h]
0x1800027cd  mov     [rbp+57h+var_80], 0
0x1800027d4  mov     [rbp+57h+var_58], 48h ; 'H'
0x1800027db  mov     [rbp+57h+var_50], 0
0x1800027e3  mov     [rbp+57h+var_48], 10h
0x1800027ea  mov     [rbp+57h+var_40], 0
0x1800027f2  mov     [rbp+57h+var_30], 13h
0x1800027f9  mov     [rbp+57h+var_20], 4
0x180002800  mov     [rbp+57h+var_18], 0
0x180002808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280d  lea     r11, [rsp+100h+var_10]
0x180002815  mov     rbx, [r11+20h]
0x180002819  mov     rsi, [r11+28h]
0x18000281d  mov     rsp, r11
0x180002820  pop     r15
0x180002822  pop     r14
0x180002824  pop     rbp
0x180002825  retn
```
