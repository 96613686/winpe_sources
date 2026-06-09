# CWsServiceProxy::OpenServiceProxy(IClientCred *,ushort const *,_WS_ERROR *)

- ea: `0x18001418c`
- end: `0x1800142bf`
- name: `?OpenServiceProxy@CWsServiceProxy@@QEAAJPEAUIClientCred@@PEBGPEAU_WS_ERROR@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(WS_SERVICE_PROXY **serviceProxy, struct IClientCred *, const unsigned __int16 *, struct _WS_ERROR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800156e4`

## callees

- `0x18001418c`
- `0x18003f010`

## import_xrefs

- `webservices!WsCreateServiceProxy` at `0x180014265`
- `webservices!WsCreateServiceProxy` at `0x180014265`
- `webservices!WsOpenServiceProxy` at `0x18001428e`
- `webservices!WsOpenServiceProxy` at `0x18001428e`
- `webservices!WsFreeServiceProxy` at `0x18001429d`
- `webservices!WsFreeServiceProxy` at `0x18001429d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180014278`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180014278`

## pseudocode

```c
__int64 __fastcall CWsServiceProxy::OpenServiceProxy(
        WS_SERVICE_PROXY **serviceProxy,
        __int64 (__fastcall ***a2)(struct IClientCred *, WS_SERVICE_PROXY **),
        WCHAR *a3,
        struct _WS_ERROR *a4)
{
  __int64 v5; // rax
  __int64 (__fastcall **v7)(struct IClientCred *, WS_SERVICE_PROXY **); // rax
  WS_SERVICE_PROXY *v8; // rax
  HRESULT v9; // eax
  HRESULT v10; // ebx
  HRESULT v11; // edx
  unsigned int v12; // ecx
  WS_ENDPOINT_ADDRESS address; // [rsp+50h] [rbp-58h] BYREF

  *(&address.url.length + 1) = 0;
  memset(&address.headers, 0, 24);
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  address.url.length = v5;
  v7 = *a2;
  address.url.chars = a3;
  v8 = (WS_SERVICE_PROXY *)(*v7)((struct IClientCred *)a2, serviceProxy + 1);
  serviceProxy[23] = v8;
  serviceProxy[22] = (WS_SERVICE_PROXY *)(serviceProxy + 24);
  serviceProxy[18] = (WS_SERVICE_PROXY *)(serviceProxy + 22);
  *((_DWORD *)serviceProxy + 48) = 1;
  *((_DWORD *)serviceProxy + 38) = (v8 != 0) + 1;
  if ( v8 && *(_DWORD *)v8 == 4 )
  {
    *((_DWORD *)serviceProxy + 42) = 1;
    serviceProxy[20] = (WS_SERVICE_PROXY *)&securityProperties;
  }
  v9 = WsCreateServiceProxy(
         WS_CHANNEL_TYPE_REQUEST,
         WS_HTTP_CHANNEL_BINDING,
         (const WS_SECURITY_DESCRIPTION *)(serviceProxy + 18),
         0,
         0,
         &channelPropertiesArray,
         4u,
         serviceProxy,
         a4);
  v10 = v9;
  if ( v9 )
  {
    v11 = v9;
    v12 = 5704640;
  }
  else
  {
    v10 = WsOpenServiceProxy(*serviceProxy, &address, 0, a4);
    if ( v10 >= 0 )
      return 0;
    WsFreeServiceProxy(*serviceProxy);
    v11 = v10;
    *serviceProxy = 0;
    v12 = 6163392;
  }
  CSPrintErrorLineFile(v12, v11);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001418c  push    rbx
0x18001418e  push    rbp
0x18001418f  push    rsi
0x180014190  push    rdi
0x180014191  sub     rsp, 88h
0x180014198  xor     ebp, ebp
0x18001419a  xorps   xmm0, xmm0
0x18001419d  mov     rsi, r9
0x1800141a0  mov     dword ptr [rsp+0A8h+address.url+4], ebp
0x1800141a4  movdqu  xmmword ptr [rsp+0A8h+address.headers], xmm0
0x1800141aa  mov     [rsp+0A8h+address.identity], rbp
0x1800141af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800141b3  mov     r9, rdx
0x1800141b6  mov     rdi, rcx
0x1800141b9  inc     rax
0x1800141bc  cmp     [r8+rax*2], bp
0x1800141c1  jnz     short loc_1800141B9
0x1800141c3  mov     [rsp+0A8h+address.url.length], eax
0x1800141c7  mov     rax, [rdx]
0x1800141ca  lea     rdx, [rcx+8]
0x1800141ce  mov     rcx, r9
0x1800141d1  mov     [rsp+0A8h+address.url.chars], r8
0x1800141d6  mov     rax, [rax]
0x1800141d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141de  lea     rcx, [rdi+0C0h]
0x1800141e5  mov     [rdi+0B8h], rax
0x1800141ec  lea     rdx, [rdi+0B0h]
0x1800141f3  mov     r9d, 1
0x1800141f9  mov     [rdx], rcx
0x1800141fc  lea     r8, [rdi+90h]; securityDescription
0x180014203  mov     [r8], rdx
0x180014206  mov     [rcx], r9d
0x180014209  mov     rcx, rax
0x18001420c  neg     rcx
0x18001420f  sbb     edx, edx
0x180014211  neg     edx
0x180014213  add     edx, r9d
0x180014216  mov     [rdi+98h], edx
0x18001421c  test    rax, rax
0x18001421f  jz      short loc_18001423B
0x180014221  cmp     dword ptr [rax], 4
0x180014224  jnz     short loc_18001423B
0x180014226  lea     rax, ?securityProperties@@3PAU_WS_SECURITY_PROPERTY@@A; _WS_SECURITY_PROPERTY near * securityProperties
0x18001422d  mov     [rdi+0A8h], r9d
0x180014234  mov     [rdi+0A0h], rax
0x18001423b  mov     [rsp+0A8h+error], rsi; error
0x180014240  lea     rax, ?channelPropertiesArray@@3PAU_WS_CHANNEL_PROPERTY@@A; _WS_CHANNEL_PROPERTY near * channelPropertiesArray
0x180014247  mov     [rsp+0A8h+serviceProxy], rdi; serviceProxy
0x18001424c  xor     edx, edx; channelBinding
0x18001424e  mov     [rsp+0A8h+channelPropertyCount], 4; channelPropertyCount
0x180014256  xor     r9d, r9d; properties
0x180014259  mov     [rsp+0A8h+channelProperties], rax; channelProperties
0x18001425e  mov     [rsp+0A8h+propertyCount], ebp; propertyCount
0x180014262  lea     ecx, [rdx+8]; channelType
0x180014265  call    cs:__imp_WsCreateServiceProxy
0x18001426b  mov     ebx, eax
0x18001426d  test    eax, eax
0x18001426f  jz      short loc_180014280
0x180014271  mov     edx, eax
0x180014273  mov     ecx, 570BC0h
0x180014278  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001427e  jmp     short loc_1800142B1
0x180014280  mov     rcx, [rdi]; serviceProxy
0x180014283  lea     rdx, [rsp+0A8h+address]; address
0x180014288  mov     r9, rsi; error
0x18001428b  xor     r8d, r8d; asyncContext
0x18001428e  call    cs:__imp_WsOpenServiceProxy
0x180014294  mov     ebx, eax
0x180014296  test    eax, eax
0x180014298  jns     short loc_1800142AF
0x18001429a  mov     rcx, [rdi]; serviceProxy
0x18001429d  call    cs:__imp_WsFreeServiceProxy
0x1800142a3  mov     edx, ebx
0x1800142a5  mov     [rdi], rbp
0x1800142a8  mov     ecx, 5E0BC0h
0x1800142ad  jmp     short loc_180014278
0x1800142af  mov     ebx, ebp
0x1800142b1  mov     eax, ebx
0x1800142b3  add     rsp, 88h
0x1800142ba  pop     rdi
0x1800142bb  pop     rsi
0x1800142bc  pop     rbp
0x1800142bd  pop     rbx
0x1800142be  retn
```
