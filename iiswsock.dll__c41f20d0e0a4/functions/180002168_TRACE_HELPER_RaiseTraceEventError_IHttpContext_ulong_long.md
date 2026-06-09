# TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)

- ea: `0x180002168`
- end: `0x1800024fa`
- name: `?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z`
- size: `914`
- prototype: `void __fastcall(TRACE_HELPER *__hidden this, struct IHttpContext *, unsigned int, int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ae8`
- `0x180005fd0`
- `0x1800060c0`
- `0x1800063d0`
- `0x180006790`
- `0x180006c98`
- `0x180007420`

## callees

- `0x180002168`
- `0x180009010`

## string_xrefs

- `0x1800022fe`: `WEBSOCKET_WRITE_FRAGMENT_END_NOT_SUCCESS`
- `0x1800023a9`: `WEBSOCKET_READ_FRAGMENT_END_NOT_SUCCESS`

## pseudocode

```c
void __fastcall TRACE_HELPER::RaiseTraceEventError(TRACE_HELPER *this, struct IHttpContext *a2, int a3, int a4)
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
  int (__fastcall ***v17)(_QWORD, GUID **); // rax
  int (__fastcall **v18)(_QWORD, GUID **); // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  void (__fastcall *v21)(__int64 *, _QWORD *); // rax
  GUID *v22; // [rsp+20h] [rbp-99h] BYREF
  __int128 v23; // [rsp+28h] [rbp-91h]
  _QWORD v24[2]; // [rsp+40h] [rbp-79h] BYREF
  GUID *v25; // [rsp+50h] [rbp-69h]
  __int64 v26; // [rsp+58h] [rbp-61h]
  const wchar_t *v27; // [rsp+60h] [rbp-59h]
  int v28; // [rsp+68h] [rbp-51h]
  int v29; // [rsp+6Ch] [rbp-4Dh]
  __int128 v30; // [rsp+70h] [rbp-49h]
  int v31; // [rsp+80h] [rbp-39h]
  int v32; // [rsp+84h] [rbp-35h]
  __int64 v33; // [rsp+88h] [rbp-31h]
  const wchar_t **v34; // [rsp+90h] [rbp-29h]
  const wchar_t *v35; // [rsp+A0h] [rbp-19h] BYREF
  int v36; // [rsp+A8h] [rbp-11h]
  __int64 v37; // [rsp+B0h] [rbp-9h]
  int v38; // [rsp+B8h] [rbp-1h]
  __int64 v39; // [rsp+C0h] [rbp+7h]
  const wchar_t *v40; // [rsp+C8h] [rbp+Fh]
  int v41; // [rsp+D0h] [rbp+17h]
  int *v42; // [rsp+D8h] [rbp+1Fh]
  int v43; // [rsp+E0h] [rbp+27h]
  __int64 v44; // [rsp+E8h] [rbp+2Fh]
  int v45; // [rsp+130h] [rbp+77h] BYREF

  switch ( a3 )
  {
    case 3:
      v17 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v22 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v18 = *v17;
      v23 = 0;
      if ( (*v18)(v17, &v22) >= 0 && DWORD2(v23) && DWORD1(v23) >= 4 && ((_DWORD)v23 == 0x4000 || (v23 & 0x4000) != 0) )
      {
        v19 = *(_QWORD *)a2;
        v45 = a4;
        v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v19 + 272))(a2);
        v26 = 4;
        v25 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
        v10 = L"WEBSOCKET_HANDSHAKE_NOT_SUCCESS";
        goto LABEL_29;
      }
      break;
    case 19:
      v14 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v22 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v15 = *v14;
      v23 = 0;
      if ( (*v15)(v14, &v22) >= 0 && DWORD2(v23) && DWORD1(v23) >= 4 && ((_DWORD)v23 == 0x4000 || (v23 & 0x4000) != 0) )
      {
        v16 = *(_QWORD *)a2;
        v45 = a4;
        v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v16 + 272))(a2);
        v26 = 8;
        v25 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
        v10 = L"WEBSOCKET_READ_FRAGMENT_END_NOT_SUCCESS";
        goto LABEL_29;
      }
      break;
    case 35:
      v11 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v22 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v12 = *v11;
      v23 = 0;
      if ( (*v12)(v11, &v22) >= 0 && DWORD2(v23) && DWORD1(v23) >= 4 && ((_DWORD)v23 == 0x4000 || (v23 & 0x4000) != 0) )
      {
        v13 = *(_QWORD *)a2;
        v45 = a4;
        v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v13 + 272))(a2);
        v26 = 12;
        v25 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
        v10 = L"WEBSOCKET_WRITE_FRAGMENT_END_NOT_SUCCESS";
        goto LABEL_29;
      }
      break;
    case 51:
      v6 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v22 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v7 = *v6;
      v23 = 0;
      if ( (*v7)(v6, &v22) >= 0 && DWORD2(v23) && DWORD1(v23) >= 4 && ((_DWORD)v23 == 0x4000 || (v23 & 0x4000) != 0) )
      {
        v8 = *(_QWORD *)a2;
        v45 = a4;
        v9 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 272))(a2);
        v26 = 20;
        v25 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
        v10 = L"WEBSOCKET_SEND_CLOSE_END_NOT_SUCCESS";
LABEL_29:
        v27 = v10;
        v24[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v28 = 1;
        v32 = 1;
        v35 = L"ContextId";
        v40 = L"ErrorCode";
        v42 = &v45;
        v34 = &v35;
        v20 = *v9;
        v33 = 2;
        v24[1] = 0x4000;
        v29 = 4;
        v21 = *(void (__fastcall **)(__int64 *, _QWORD *))(v20 + 16);
        v30 = 0;
        v31 = 0;
        v36 = 72;
        v37 = 0;
        v38 = 16;
        v39 = 0;
        v41 = 19;
        v43 = 4;
        v44 = 0;
        v21(v9, v24);
      }
      break;
  }
}

```

## disassembly

```asm
0x180002168  mov     [rsp-8+arg_0], rbx
0x18000216d  mov     [rsp-8+arg_8], rsi
0x180002172  push    rbp
0x180002173  push    rdi
0x180002174  push    r13
0x180002176  push    r14
0x180002178  push    r15
0x18000217a  lea     rbp, [rsp-37h]
0x18000217f  sub     rsp, 0F0h
0x180002186  mov     r13d, r9d
0x180002189  mov     r14, rdx
0x18000218c  cmp     r8d, 3
0x180002190  jz      loc_1800023B5
0x180002196  cmp     r8d, 13h
0x18000219a  jz      loc_18000230A
0x1800021a0  cmp     r8d, 23h ; '#'
0x1800021a4  jz      loc_18000225F
0x1800021aa  cmp     r8d, 33h ; '3'
0x1800021ae  jnz     loc_1800024DE
0x1800021b4  mov     rax, [rdx]
0x1800021b7  mov     rcx, rdx
0x1800021ba  mov     rax, [rax+110h]
0x1800021c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021c6  mov     r8, rax
0x1800021c9  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800021d0  xorps   xmm0, xmm0
0x1800021d3  mov     [rsp+110h+var_F0], r15
0x1800021d8  lea     rdx, [rsp+110h+var_F0]
0x1800021dd  mov     rcx, [rax]
0x1800021e0  movdqu  [rsp+110h+var_E8], xmm0
0x1800021e6  mov     rax, [rcx]
0x1800021e9  mov     rcx, r8
0x1800021ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021f1  xor     edi, edi
0x1800021f3  test    eax, eax
0x1800021f5  js      loc_1800024DE
0x1800021fb  cmp     dword ptr [rsp+110h+var_E8+8], edi
0x1800021ff  jz      loc_1800024DE
0x180002205  lea     esi, [rdi+4]
0x180002208  cmp     dword ptr [rsp+110h+var_E8+4], esi
0x18000220c  jb      loc_1800024DE
0x180002212  mov     ebx, 4000h
0x180002217  cmp     dword ptr [rsp+110h+var_E8], ebx
0x18000221b  jz      short loc_180002227
0x18000221d  test    dword ptr [rsp+110h+var_E8], ebx
0x180002221  jz      loc_1800024DE
0x180002227  mov     rax, [r14]
0x18000222a  mov     rcx, r14
0x18000222d  mov     [rbp+57h+arg_10], r13d
0x180002231  mov     rax, [rax+110h]
0x180002238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000223d  mov     rcx, rax
0x180002240  mov     [rbp+57h+var_B8], 14h
0x180002248  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000224f  mov     [rbp+57h+var_C0], rax
0x180002253  lea     rax, aWebsocketSendC_1; "WEBSOCKET_SEND_CLOSE_END_NOT_SUCCESS"
0x18000225a  jmp     loc_180002457
0x18000225f  mov     rax, [rdx]
0x180002262  mov     rcx, r14
0x180002265  mov     rax, [rax+110h]
0x18000226c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002271  mov     r8, rax
0x180002274  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000227b  xorps   xmm0, xmm0
0x18000227e  mov     [rsp+110h+var_F0], r15
0x180002283  lea     rdx, [rsp+110h+var_F0]
0x180002288  mov     rcx, [rax]
0x18000228b  movdqu  [rsp+110h+var_E8], xmm0
0x180002291  mov     rax, [rcx]
0x180002294  mov     rcx, r8
0x180002297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000229c  xor     edi, edi
0x18000229e  test    eax, eax
0x1800022a0  js      loc_1800024DE
0x1800022a6  cmp     dword ptr [rsp+110h+var_E8+8], edi
0x1800022aa  jz      loc_1800024DE
0x1800022b0  lea     esi, [rdi+4]
0x1800022b3  cmp     dword ptr [rsp+110h+var_E8+4], esi
0x1800022b7  jb      loc_1800024DE
0x1800022bd  mov     ebx, 4000h
0x1800022c2  cmp     dword ptr [rsp+110h+var_E8], ebx
0x1800022c6  jz      short loc_1800022D2
0x1800022c8  test    dword ptr [rsp+110h+var_E8], ebx
0x1800022cc  jz      loc_1800024DE
0x1800022d2  mov     rax, [r14]
0x1800022d5  mov     rcx, r14
0x1800022d8  mov     [rbp+57h+arg_10], r13d
0x1800022dc  mov     rax, [rax+110h]
0x1800022e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e8  mov     rcx, rax
0x1800022eb  mov     [rbp+57h+var_B8], 0Ch
0x1800022f3  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800022fa  mov     [rbp+57h+var_C0], rax
0x1800022fe  lea     rax, aWebsocketWrite_2; "WEBSOCKET_WRITE_FRAGMENT_END_NOT_SUCCES"...
0x180002305  jmp     loc_180002457
0x18000230a  mov     rax, [rdx]
0x18000230d  mov     rcx, r14
0x180002310  mov     rax, [rax+110h]
0x180002317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000231c  mov     r8, rax
0x18000231f  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002326  xorps   xmm0, xmm0
0x180002329  mov     [rsp+110h+var_F0], r15
0x18000232e  lea     rdx, [rsp+110h+var_F0]
0x180002333  mov     rcx, [rax]
0x180002336  movdqu  [rsp+110h+var_E8], xmm0
0x18000233c  mov     rax, [rcx]
0x18000233f  mov     rcx, r8
0x180002342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002347  xor     edi, edi
0x180002349  test    eax, eax
0x18000234b  js      loc_1800024DE
0x180002351  cmp     dword ptr [rsp+110h+var_E8+8], edi
0x180002355  jz      loc_1800024DE
0x18000235b  lea     esi, [rdi+4]
0x18000235e  cmp     dword ptr [rsp+110h+var_E8+4], esi
0x180002362  jb      loc_1800024DE
0x180002368  mov     ebx, 4000h
0x18000236d  cmp     dword ptr [rsp+110h+var_E8], ebx
0x180002371  jz      short loc_18000237D
0x180002373  test    dword ptr [rsp+110h+var_E8], ebx
0x180002377  jz      loc_1800024DE
0x18000237d  mov     rax, [r14]
0x180002380  mov     rcx, r14
0x180002383  mov     [rbp+57h+arg_10], r13d
0x180002387  mov     rax, [rax+110h]
0x18000238e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002393  mov     rcx, rax
0x180002396  mov     [rbp+57h+var_B8], 8
0x18000239e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800023a5  mov     [rbp+57h+var_C0], rax
0x1800023a9  lea     rax, aWebsocketReadF_0; "WEBSOCKET_READ_FRAGMENT_END_NOT_SUCCESS"
0x1800023b0  jmp     loc_180002457
0x1800023b5  mov     rax, [rdx]
0x1800023b8  mov     rcx, r14
0x1800023bb  mov     rax, [rax+110h]
0x1800023c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c7  mov     r8, rax
0x1800023ca  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800023d1  xorps   xmm0, xmm0
0x1800023d4  mov     [rsp+110h+var_F0], r15
0x1800023d9  lea     rdx, [rsp+110h+var_F0]
0x1800023de  mov     rcx, [rax]
0x1800023e1  movdqu  [rsp+110h+var_E8], xmm0
0x1800023e7  mov     rax, [rcx]
0x1800023ea  mov     rcx, r8
0x1800023ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f2  xor     edi, edi
0x1800023f4  test    eax, eax
0x1800023f6  js      loc_1800024DE
0x1800023fc  cmp     dword ptr [rsp+110h+var_E8+8], edi
0x180002400  jz      loc_1800024DE
0x180002406  lea     esi, [rdi+4]
0x180002409  cmp     dword ptr [rsp+110h+var_E8+4], esi
0x18000240d  jb      loc_1800024DE
0x180002413  mov     ebx, 4000h
0x180002418  cmp     dword ptr [rsp+110h+var_E8], ebx
0x18000241c  jz      short loc_180002428
0x18000241e  test    dword ptr [rsp+110h+var_E8], ebx
0x180002422  jz      loc_1800024DE
0x180002428  mov     rax, [r14]
0x18000242b  mov     rcx, r14
0x18000242e  mov     [rbp+57h+arg_10], r13d
0x180002432  mov     rax, [rax+110h]
0x180002439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000243e  mov     rcx, rax
0x180002441  mov     [rbp+57h+var_B8], rsi
0x180002445  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000244c  mov     [rbp+57h+var_C0], rax
0x180002450  lea     rax, aWebsocketHands_1; "WEBSOCKET_HANDSHAKE_NOT_SUCCESS"
0x180002457  mov     [rbp+57h+var_B0], rax
0x18000245b  lea     rdx, [rbp+57h+var_D0]
0x18000245f  mov     eax, 1
0x180002464  mov     [rbp+57h+var_D0], r15
0x180002468  mov     [rbp+57h+var_A8], eax
0x18000246b  xorps   xmm0, xmm0
0x18000246e  mov     [rbp+57h+var_8C], eax
0x180002471  lea     rax, aContextid; "ContextId"
0x180002478  mov     [rbp+57h+var_70], rax
0x18000247c  lea     rax, aErrorcode; "ErrorCode"
0x180002483  mov     [rbp+57h+var_48], rax
0x180002487  lea     rax, [rbp+57h+arg_10]
0x18000248b  mov     [rbp+57h+var_38], rax
0x18000248f  lea     rax, [rbp+57h+var_70]
0x180002493  mov     [rbp+57h+var_80], rax
0x180002497  mov     rax, [rcx]
0x18000249a  mov     [rbp+57h+var_88], 2
0x1800024a2  mov     [rbp+57h+var_C8], rbx
0x1800024a6  mov     [rbp+57h+var_A4], esi
0x1800024a9  mov     rax, [rax+10h]
0x1800024ad  movdqa  [rbp+57h+var_A0], xmm0
0x1800024b2  mov     [rbp+57h+var_90], edi
0x1800024b5  mov     [rbp+57h+var_68], 48h ; 'H'
0x1800024bc  mov     [rbp+57h+var_60], rdi
0x1800024c0  mov     [rbp+57h+var_58], 10h
0x1800024c7  mov     [rbp+57h+var_50], rdi
0x1800024cb  mov     [rbp+57h+var_40], 13h
0x1800024d2  mov     [rbp+57h+var_30], esi
0x1800024d5  mov     [rbp+57h+var_28], rdi
0x1800024d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024de  lea     r11, [rsp+110h+var_20]
0x1800024e6  mov     rbx, [r11+30h]
0x1800024ea  mov     rsi, [r11+38h]
0x1800024ee  mov     rsp, r11
0x1800024f1  pop     r15
0x1800024f3  pop     r14
0x1800024f5  pop     r13
0x1800024f7  pop     rdi
0x1800024f8  pop     rbp
0x1800024f9  retn
```
