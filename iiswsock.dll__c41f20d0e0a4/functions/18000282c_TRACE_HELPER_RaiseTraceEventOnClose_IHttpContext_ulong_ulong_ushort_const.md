# TRACE_HELPER::RaiseTraceEventOnClose(IHttpContext *,ulong,ulong,ushort const *)

- ea: `0x18000282c`
- end: `0x18000296e`
- name: `?RaiseTraceEventOnClose@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KKPEBG@Z`
- size: `322`
- prototype: `void(TRACE_HELPER *__hidden this, struct IHttpContext *, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180006284`
- `0x180006790`

## callees

- `0x180001928`
- `0x180001a70`
- `0x18000282c`
- `0x180009010`

## pseudocode

```c
void __fastcall TRACE_HELPER::RaiseTraceEventOnClose(
        TRACE_HELPER *this,
        struct IHttpContext *a2,
        int a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  int v7; // r8d
  int (__fastcall ***v8)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v9; // rax
  const struct _GUID *v10; // rdx
  int (__fastcall ***v11)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v12; // rax
  const struct _GUID *v13; // rdx
  GUID *v14; // [rsp+20h] [rbp-20h] BYREF
  __int128 v15; // [rsp+28h] [rbp-18h]

  v7 = a3 - 48;
  if ( v7 )
  {
    if ( v7 == 1 )
    {
      v8 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      v14 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v15 = 0;
      if ( (**v8)(v8, &v14) >= 0 && DWORD2(v15) && DWORD1(v15) >= 5 && ((_DWORD)v15 == 0x4000 || (v15 & 0x4000) != 0) )
      {
        v9 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
        IISWebSocketEvents::WEBSOCKET_SEND_CLOSE_START::RaiseEvent(v9, v10, a4, a5);
      }
    }
  }
  else
  {
    v11 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v14 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v15 = 0;
    if ( (**v11)(v11, &v14) >= 0 && DWORD2(v15) && DWORD1(v15) >= 5 && ((_DWORD)v15 == 0x4000 || (v15 & 0x4000) != 0) )
    {
      v12 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
      IISWebSocketEvents::WEBSOCKET_RECEIVED_CLOSE::RaiseEvent(v12, v13, a4, a5);
    }
  }
}

```

## disassembly

```asm
0x18000282c  mov     [rsp-8+arg_0], rbx
0x180002831  mov     [rsp-8+arg_8], rdi
0x180002836  push    rbp
0x180002837  mov     rbp, rsp
0x18000283a  sub     rsp, 40h
0x18000283e  mov     edi, r9d
0x180002841  mov     rbx, rdx
0x180002844  sub     r8d, 30h ; '0'
0x180002848  jz      loc_1800028E4
0x18000284e  cmp     r8d, 1
0x180002852  jnz     loc_18000295E
0x180002858  mov     rax, [rdx]
0x18000285b  mov     rcx, rdx
0x18000285e  mov     rax, [rax+110h]
0x180002865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000286a  mov     r8, rax
0x18000286d  lea     rdx, [rbp+var_20]
0x180002871  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002878  xorps   xmm0, xmm0
0x18000287b  mov     [rbp+var_20], rax
0x18000287f  movdqu  [rbp+var_18], xmm0
0x180002884  mov     rcx, [r8]
0x180002887  mov     rax, [rcx]
0x18000288a  mov     rcx, r8
0x18000288d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002892  test    eax, eax
0x180002894  js      loc_18000295E
0x18000289a  cmp     dword ptr [rbp+var_18+8], 0
0x18000289e  jz      loc_18000295E
0x1800028a4  cmp     dword ptr [rbp+var_18+4], 5
0x1800028a8  jb      loc_18000295E
0x1800028ae  mov     eax, 4000h
0x1800028b3  cmp     dword ptr [rbp+var_18], eax
0x1800028b6  jz      short loc_1800028C1
0x1800028b8  test    dword ptr [rbp+var_18], eax
0x1800028bb  jz      loc_18000295E
0x1800028c1  mov     rax, [rbx]
0x1800028c4  mov     rcx, rbx
0x1800028c7  mov     rax, [rax+110h]
0x1800028ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d3  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x1800028d7  mov     rcx, rax; struct IHttpTraceContext *
0x1800028da  mov     r8d, edi; unsigned int
0x1800028dd  call    ?RaiseEvent@WEBSOCKET_SEND_CLOSE_START@IISWebSocketEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KPEBG@Z; IISWebSocketEvents::WEBSOCKET_SEND_CLOSE_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort const *)
0x1800028e2  jmp     short loc_18000295E
0x1800028e4  mov     rax, [rdx]
0x1800028e7  mov     rcx, rbx
0x1800028ea  mov     rax, [rax+110h]
0x1800028f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f6  mov     r8, rax
0x1800028f9  lea     rdx, [rbp+var_20]
0x1800028fd  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002904  xorps   xmm0, xmm0
0x180002907  mov     [rbp+var_20], rax
0x18000290b  movdqu  [rbp+var_18], xmm0
0x180002910  mov     rcx, [r8]
0x180002913  mov     rax, [rcx]
0x180002916  mov     rcx, r8
0x180002919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291e  test    eax, eax
0x180002920  js      short loc_18000295E
0x180002922  cmp     dword ptr [rbp+var_18+8], 0
0x180002926  jz      short loc_18000295E
0x180002928  cmp     dword ptr [rbp+var_18+4], 5
0x18000292c  jb      short loc_18000295E
0x18000292e  mov     eax, 4000h
0x180002933  cmp     dword ptr [rbp+var_18], eax
0x180002936  jz      short loc_18000293D
0x180002938  test    dword ptr [rbp+var_18], eax
0x18000293b  jz      short loc_18000295E
0x18000293d  mov     rax, [rbx]
0x180002940  mov     rcx, rbx
0x180002943  mov     rax, [rax+110h]
0x18000294a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294f  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x180002953  mov     rcx, rax; struct IHttpTraceContext *
0x180002956  mov     r8d, edi; unsigned int
0x180002959  call    ?RaiseEvent@WEBSOCKET_RECEIVED_CLOSE@IISWebSocketEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KPEBG@Z; IISWebSocketEvents::WEBSOCKET_RECEIVED_CLOSE::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort const *)
0x18000295e  mov     rbx, [rsp+40h+arg_0]
0x180002963  mov     rdi, [rsp+40h+arg_8]
0x180002968  add     rsp, 40h
0x18000296c  pop     rbp
0x18000296d  retn
```
