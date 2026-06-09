# TRACE_HELPER::RaiseTraceEvent(IHttpContext *,ulong)

- ea: `0x180001ce0`
- end: `0x180002160`
- name: `?RaiseTraceEvent@TRACE_HELPER@@QEAAXPEAVIHttpContext@@K@Z`
- size: `1152`
- prototype: `void __fastcall(TRACE_HELPER *__hidden this, struct IHttpContext *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a50`
- `0x180005fd0`
- `0x180006c98`
- `0x180007674`

## callees

- `0x180001ce0`
- `0x180009010`

## string_xrefs

- `0x180001f07`: `WEBSOCKET_WRITE_FRAGMENT_END_PENDING`
- `0x180001fa5`: `WEBSOCKET_READ_FRAGMENT_END_PENDING`

## pseudocode

```c
void __fastcall TRACE_HELPER::RaiseTraceEvent(TRACE_HELPER *this, struct IHttpContext *a2, int a3)
{
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int (__fastcall ***v9)(_QWORD, GUID **); // rax
  int (__fastcall **v10)(_QWORD, GUID **); // rcx
  __int64 *v11; // rcx
  const wchar_t *v12; // rax
  int (__fastcall ***v13)(_QWORD, GUID **); // rax
  int (__fastcall **v14)(_QWORD, GUID **); // rcx
  int (__fastcall ***v15)(_QWORD, GUID **); // rax
  int (__fastcall **v16)(_QWORD, GUID **); // rcx
  int (__fastcall ***v17)(_QWORD, GUID **); // rax
  int (__fastcall **v18)(_QWORD, GUID **); // rcx
  int (__fastcall ***v19)(_QWORD, GUID **); // rax
  int (__fastcall **v20)(_QWORD, GUID **); // rcx
  int (__fastcall ***v21)(_QWORD, GUID **); // rax
  int (__fastcall **v22)(_QWORD, GUID **); // rcx
  __int64 v23; // rax
  void (__fastcall *v24)(__int64 *, _QWORD *); // rax
  GUID *v25; // [rsp+20h] [rbp-59h] BYREF
  __int128 v26; // [rsp+28h] [rbp-51h]
  int v27; // [rsp+38h] [rbp-41h]
  __int64 v28; // [rsp+40h] [rbp-39h]
  _QWORD v29[2]; // [rsp+50h] [rbp-29h] BYREF
  GUID *v30; // [rsp+60h] [rbp-19h]
  __int64 v31; // [rsp+68h] [rbp-11h]
  const wchar_t *v32; // [rsp+70h] [rbp-9h]
  int v33; // [rsp+78h] [rbp-1h]
  int v34; // [rsp+7Ch] [rbp+3h]
  __int128 v35; // [rsp+80h] [rbp+7h]
  int v36; // [rsp+90h] [rbp+17h]
  int v37; // [rsp+94h] [rbp+1Bh]
  __int64 v38; // [rsp+98h] [rbp+1Fh]
  GUID **v39; // [rsp+A0h] [rbp+27h]

  v4 = a3 - 1;
  if ( !v4 )
  {
    v21 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v25 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v22 = *v21;
    v26 = 0;
    if ( (*v22)(v21, &v25) < 0 || !DWORD2(v26) || DWORD1(v26) < 5 || (_DWORD)v26 != 0x4000 && (v26 & 0x4000) == 0 )
      return;
    v11 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v31 = 2;
    v30 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
    v12 = L"WEBSOCKET_HANDSHAKE_START";
LABEL_43:
    v34 = 5;
    goto LABEL_44;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v19 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v25 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v20 = *v19;
    v26 = 0;
    if ( (*v20)(v19, &v25) < 0 || !DWORD2(v26) || DWORD1(v26) < 5 || (_DWORD)v26 != 0x4000 && (v26 & 0x4000) == 0 )
      return;
    v11 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v31 = 3;
    v30 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
    v12 = L"WEBSOCKET_HANDSHAKE_SUCCESS";
    goto LABEL_43;
  }
  v6 = v5 - 15;
  if ( !v6 )
  {
    v17 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v25 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v18 = *v17;
    v26 = 0;
    if ( (*v18)(v17, &v25) < 0 || !DWORD2(v26) || DWORD1(v26) < 5 || (_DWORD)v26 != 0x4000 && (v26 & 0x4000) == 0 )
      return;
    v11 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v31 = 6;
    v30 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
    v12 = L"WEBSOCKET_READ_FRAGMENT_END_PENDING";
    goto LABEL_43;
  }
  v7 = v6 - 16;
  if ( !v7 )
  {
    v15 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v25 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v16 = *v15;
    v26 = 0;
    if ( (*v16)(v15, &v25) < 0 || !DWORD2(v26) || DWORD1(v26) < 5 || (_DWORD)v26 != 0x4000 && (v26 & 0x4000) == 0 )
      return;
    v11 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v31 = 10;
    v30 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
    v12 = L"WEBSOCKET_WRITE_FRAGMENT_END_PENDING";
    goto LABEL_43;
  }
  v8 = v7 - 17;
  if ( !v8 )
  {
    v13 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v25 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v14 = *v13;
    v26 = 0;
    if ( (*v14)(v13, &v25) < 0 || !DWORD2(v26) || DWORD1(v26) < 5 || (_DWORD)v26 != 0x4000 && (v26 & 0x4000) == 0 )
      return;
    v11 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v31 = 19;
    v30 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
    v12 = L"WEBSOCKET_SEND_CLOSE_END_SUCCESS";
    goto LABEL_43;
  }
  if ( v8 == 14 )
  {
    v9 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v25 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v10 = *v9;
    v26 = 0;
    if ( (*v10)(v9, &v25) >= 0 && DWORD2(v26) && DWORD1(v26) >= 4 && ((_DWORD)v26 == 0x4000 || (v26 & 0x4000) != 0) )
    {
      v11 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v31 = 13;
      v34 = 4;
      v30 = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
      v12 = L"WEBSOCKET_APPLICATION_CLOSE_CONNECTION";
LABEL_44:
      v32 = v12;
      v29[1] = 0x4000;
      v33 = 1;
      v37 = 1;
      v25 = (GUID *)L"ContextId";
      v39 = &v25;
      v23 = *v11;
      v38 = 1;
      v29[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v35 = 0;
      v24 = *(void (__fastcall **)(__int64 *, _QWORD *))(v23 + 16);
      v36 = 0;
      LODWORD(v26) = 72;
      *((_QWORD *)&v26 + 1) = 0;
      v27 = 16;
      v28 = 0;
      v24(v11, v29);
    }
  }
}

```

## disassembly

```asm
0x180001ce0  push    rbp
0x180001ce2  push    rbx
0x180001ce3  push    rsi
0x180001ce4  push    rdi
0x180001ce5  push    r14
0x180001ce7  lea     rbp, [rsp-37h]
0x180001cec  sub     rsp, 0B0h
0x180001cf3  mov     rsi, rdx
0x180001cf6  sub     r8d, 1
0x180001cfa  jz      loc_18000204F
0x180001d00  sub     r8d, 1
0x180001d04  jz      loc_180001FB1
0x180001d0a  sub     r8d, 0Fh
0x180001d0e  jz      loc_180001F13
0x180001d14  sub     r8d, 10h
0x180001d18  jz      loc_180001E75
0x180001d1e  sub     r8d, 11h
0x180001d22  jz      loc_180001DD7
0x180001d28  cmp     r8d, 0Eh
0x180001d2c  jnz     loc_180002152
0x180001d32  mov     rax, [rdx]
0x180001d35  mov     rcx, rdx
0x180001d38  mov     rax, [rax+110h]
0x180001d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d44  mov     r8, rax
0x180001d47  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001d4e  xorps   xmm0, xmm0
0x180001d51  mov     [rbp+57h+var_B0], r14
0x180001d55  lea     rdx, [rbp+57h+var_B0]
0x180001d59  mov     rcx, [rax]
0x180001d5c  movdqu  [rbp+57h+var_A8], xmm0
0x180001d61  mov     rax, [rcx]
0x180001d64  mov     rcx, r8
0x180001d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d6c  xor     edi, edi
0x180001d6e  test    eax, eax
0x180001d70  js      loc_180002152
0x180001d76  cmp     dword ptr [rbp+57h+var_A8+8], edi
0x180001d79  jz      loc_180002152
0x180001d7f  cmp     dword ptr [rbp+57h+var_A8+4], 4
0x180001d83  jb      loc_180002152
0x180001d89  mov     ebx, 4000h
0x180001d8e  cmp     dword ptr [rbp+57h+var_A8], ebx
0x180001d91  jz      short loc_180001D9C
0x180001d93  test    dword ptr [rbp+57h+var_A8], ebx
0x180001d96  jz      loc_180002152
0x180001d9c  mov     rax, [rsi]
0x180001d9f  mov     rcx, rsi
0x180001da2  mov     rax, [rax+110h]
0x180001da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dae  mov     rcx, rax
0x180001db1  mov     [rbp+57h+var_68], 0Dh
0x180001db9  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180001dc0  mov     [rbp+57h+var_54], 4
0x180001dc7  mov     [rbp+57h+var_70], rax
0x180001dcb  lea     rax, aWebsocketAppli; "WEBSOCKET_APPLICATION_CLOSE_CONNECTION"
0x180001dd2  jmp     loc_1800020EF
0x180001dd7  mov     rax, [rdx]
0x180001dda  mov     rcx, rsi
0x180001ddd  mov     rax, [rax+110h]
0x180001de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001de9  mov     r8, rax
0x180001dec  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001df3  xorps   xmm0, xmm0
0x180001df6  mov     [rbp+57h+var_B0], r14
0x180001dfa  lea     rdx, [rbp+57h+var_B0]
0x180001dfe  mov     rcx, [rax]
0x180001e01  movdqu  [rbp+57h+var_A8], xmm0
0x180001e06  mov     rax, [rcx]
0x180001e09  mov     rcx, r8
0x180001e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e11  xor     edi, edi
0x180001e13  test    eax, eax
0x180001e15  js      loc_180002152
0x180001e1b  cmp     dword ptr [rbp+57h+var_A8+8], edi
0x180001e1e  jz      loc_180002152
0x180001e24  cmp     dword ptr [rbp+57h+var_A8+4], 5
0x180001e28  jb      loc_180002152
0x180001e2e  mov     ebx, 4000h
0x180001e33  cmp     dword ptr [rbp+57h+var_A8], ebx
0x180001e36  jz      short loc_180001E41
0x180001e38  test    dword ptr [rbp+57h+var_A8], ebx
0x180001e3b  jz      loc_180002152
0x180001e41  mov     rax, [rsi]
0x180001e44  mov     rcx, rsi
0x180001e47  mov     rax, [rax+110h]
0x180001e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e53  mov     rcx, rax
0x180001e56  mov     [rbp+57h+var_68], 13h
0x180001e5e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180001e65  mov     [rbp+57h+var_70], rax
0x180001e69  lea     rax, aWebsocketSendC; "WEBSOCKET_SEND_CLOSE_END_SUCCESS"
0x180001e70  jmp     loc_1800020E8
0x180001e75  mov     rax, [rdx]
0x180001e78  mov     rcx, rsi
0x180001e7b  mov     rax, [rax+110h]
0x180001e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e87  mov     r8, rax
0x180001e8a  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001e91  xorps   xmm0, xmm0
0x180001e94  mov     [rbp+57h+var_B0], r14
0x180001e98  lea     rdx, [rbp+57h+var_B0]
0x180001e9c  mov     rcx, [rax]
0x180001e9f  movdqu  [rbp+57h+var_A8], xmm0
0x180001ea4  mov     rax, [rcx]
0x180001ea7  mov     rcx, r8
0x180001eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eaf  xor     edi, edi
0x180001eb1  test    eax, eax
0x180001eb3  js      loc_180002152
0x180001eb9  cmp     dword ptr [rbp+57h+var_A8+8], edi
0x180001ebc  jz      loc_180002152
0x180001ec2  cmp     dword ptr [rbp+57h+var_A8+4], 5
0x180001ec6  jb      loc_180002152
0x180001ecc  mov     ebx, 4000h
0x180001ed1  cmp     dword ptr [rbp+57h+var_A8], ebx
0x180001ed4  jz      short loc_180001EDF
0x180001ed6  test    dword ptr [rbp+57h+var_A8], ebx
0x180001ed9  jz      loc_180002152
0x180001edf  mov     rax, [rsi]
0x180001ee2  mov     rcx, rsi
0x180001ee5  mov     rax, [rax+110h]
0x180001eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef1  mov     rcx, rax
0x180001ef4  mov     [rbp+57h+var_68], 0Ah
0x180001efc  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180001f03  mov     [rbp+57h+var_70], rax
0x180001f07  lea     rax, aWebsocketWrite; "WEBSOCKET_WRITE_FRAGMENT_END_PENDING"
0x180001f0e  jmp     loc_1800020E8
0x180001f13  mov     rax, [rdx]
0x180001f16  mov     rcx, rsi
0x180001f19  mov     rax, [rax+110h]
0x180001f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f25  mov     r8, rax
0x180001f28  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001f2f  xorps   xmm0, xmm0
0x180001f32  mov     [rbp+57h+var_B0], r14
0x180001f36  lea     rdx, [rbp+57h+var_B0]
0x180001f3a  mov     rcx, [rax]
0x180001f3d  movdqu  [rbp+57h+var_A8], xmm0
0x180001f42  mov     rax, [rcx]
0x180001f45  mov     rcx, r8
0x180001f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f4d  xor     edi, edi
0x180001f4f  test    eax, eax
0x180001f51  js      loc_180002152
0x180001f57  cmp     dword ptr [rbp+57h+var_A8+8], edi
0x180001f5a  jz      loc_180002152
0x180001f60  cmp     dword ptr [rbp+57h+var_A8+4], 5
0x180001f64  jb      loc_180002152
0x180001f6a  mov     ebx, 4000h
0x180001f6f  cmp     dword ptr [rbp+57h+var_A8], ebx
0x180001f72  jz      short loc_180001F7D
0x180001f74  test    dword ptr [rbp+57h+var_A8], ebx
0x180001f77  jz      loc_180002152
0x180001f7d  mov     rax, [rsi]
0x180001f80  mov     rcx, rsi
0x180001f83  mov     rax, [rax+110h]
0x180001f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f8f  mov     rcx, rax
0x180001f92  mov     [rbp+57h+var_68], 6
0x180001f9a  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180001fa1  mov     [rbp+57h+var_70], rax
0x180001fa5  lea     rax, aWebsocketReadF_1; "WEBSOCKET_READ_FRAGMENT_END_PENDING"
0x180001fac  jmp     loc_1800020E8
0x180001fb1  mov     rax, [rdx]
0x180001fb4  mov     rcx, rsi
0x180001fb7  mov     rax, [rax+110h]
0x180001fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc3  mov     r8, rax
0x180001fc6  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001fcd  xorps   xmm0, xmm0
0x180001fd0  mov     [rbp+57h+var_B0], r14
0x180001fd4  lea     rdx, [rbp+57h+var_B0]
0x180001fd8  mov     rcx, [rax]
0x180001fdb  movdqu  [rbp+57h+var_A8], xmm0
0x180001fe0  mov     rax, [rcx]
0x180001fe3  mov     rcx, r8
0x180001fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001feb  xor     edi, edi
0x180001fed  test    eax, eax
0x180001fef  js      loc_180002152
0x180001ff5  cmp     dword ptr [rbp+57h+var_A8+8], edi
0x180001ff8  jz      loc_180002152
0x180001ffe  cmp     dword ptr [rbp+57h+var_A8+4], 5
0x180002002  jb      loc_180002152
0x180002008  mov     ebx, 4000h
0x18000200d  cmp     dword ptr [rbp+57h+var_A8], ebx
0x180002010  jz      short loc_18000201B
0x180002012  test    dword ptr [rbp+57h+var_A8], ebx
0x180002015  jz      loc_180002152
0x18000201b  mov     rax, [rsi]
0x18000201e  mov     rcx, rsi
0x180002021  mov     rax, [rax+110h]
0x180002028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000202d  mov     rcx, rax
0x180002030  mov     [rbp+57h+var_68], 3
0x180002038  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000203f  mov     [rbp+57h+var_70], rax
0x180002043  lea     rax, aWebsocketHands; "WEBSOCKET_HANDSHAKE_SUCCESS"
0x18000204a  jmp     loc_1800020E8
0x18000204f  mov     rax, [rdx]
0x180002052  mov     rcx, rsi
0x180002055  mov     rax, [rax+110h]
0x18000205c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002061  mov     r8, rax
0x180002064  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000206b  xorps   xmm0, xmm0
0x18000206e  mov     [rbp+57h+var_B0], r14
0x180002072  lea     rdx, [rbp+57h+var_B0]
0x180002076  mov     rcx, [rax]
0x180002079  movdqu  [rbp+57h+var_A8], xmm0
0x18000207e  mov     rax, [rcx]
0x180002081  mov     rcx, r8
0x180002084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002089  xor     edi, edi
0x18000208b  test    eax, eax
0x18000208d  js      loc_180002152
0x180002093  cmp     dword ptr [rbp+57h+var_A8+8], edi
0x180002096  jz      loc_180002152
0x18000209c  cmp     dword ptr [rbp+57h+var_A8+4], 5
0x1800020a0  jb      loc_180002152
0x1800020a6  mov     ebx, 4000h
0x1800020ab  cmp     dword ptr [rbp+57h+var_A8], ebx
0x1800020ae  jz      short loc_1800020B9
0x1800020b0  test    dword ptr [rbp+57h+var_A8], ebx
0x1800020b3  jz      loc_180002152
0x1800020b9  mov     rax, [rsi]
0x1800020bc  mov     rcx, rsi
0x1800020bf  mov     rax, [rax+110h]
0x1800020c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cb  mov     rcx, rax
0x1800020ce  mov     [rbp+57h+var_68], 2
0x1800020d6  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800020dd  mov     [rbp+57h+var_70], rax
0x1800020e1  lea     rax, aWebsocketHands_0; "WEBSOCKET_HANDSHAKE_START"
0x1800020e8  mov     [rbp+57h+var_54], 5
0x1800020ef  mov     [rbp+57h+var_60], rax
0x1800020f3  lea     rdx, [rbp+57h+var_80]
0x1800020f7  mov     eax, 1
0x1800020fc  mov     [rbp+57h+var_78], rbx
0x180002100  mov     [rbp+57h+var_58], eax
0x180002103  xorps   xmm0, xmm0
0x180002106  mov     [rbp+57h+var_3C], eax
0x180002109  lea     rax, aContextid; "ContextId"
0x180002110  mov     [rbp+57h+var_B0], rax
0x180002114  lea     rax, [rbp+57h+var_B0]
0x180002118  mov     [rbp+57h+var_30], rax
0x18000211c  mov     rax, [rcx]
0x18000211f  mov     [rbp+57h+var_38], 1
0x180002127  mov     [rbp+57h+var_80], r14
0x18000212b  movdqa  [rbp+57h+var_50], xmm0
0x180002130  mov     rax, [rax+10h]
0x180002134  mov     [rbp+57h+var_40], edi
0x180002137  mov     dword ptr [rbp+57h+var_A8], 48h ; 'H'
0x18000213e  mov     qword ptr [rbp+57h+var_A8+8], rdi
0x180002142  mov     [rbp+57h+var_98], 10h
0x180002149  mov     [rbp+57h+var_90], rdi
0x18000214d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002152  add     rsp, 0B0h
0x180002159  pop     r14
0x18000215b  pop     rdi
0x18000215c  pop     rsi
0x18000215d  pop     rbx
0x18000215e  pop     rbp
0x18000215f  retn
```
