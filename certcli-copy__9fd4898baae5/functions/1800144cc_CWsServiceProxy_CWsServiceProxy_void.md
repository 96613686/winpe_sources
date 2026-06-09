# CWsServiceProxy::~CWsServiceProxy(void)

- ea: `0x1800144cc`
- end: `0x1800144f8`
- name: `??1CWsServiceProxy@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CWsServiceProxy *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800156e4`

## callees

- `0x1800144cc`

## import_xrefs

- `webservices!WsFreeServiceProxy` at `0x1800144eb`
- `webservices!WsFreeServiceProxy` at `0x1800144eb`
- `webservices!WsCloseServiceProxy` at `0x1800144e2`
- `webservices!WsCloseServiceProxy` at `0x1800144e2`

## pseudocode

```c
void __fastcall CWsServiceProxy::~CWsServiceProxy(WS_SERVICE_PROXY **this)
{
  WS_SERVICE_PROXY *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    WsCloseServiceProxy(v2, 0, 0);
    WsFreeServiceProxy(*this);
  }
}

```

## disassembly

```asm
0x1800144cc  push    rbx
0x1800144ce  sub     rsp, 20h
0x1800144d2  mov     rbx, rcx
0x1800144d5  mov     rcx, [rcx]; serviceProxy
0x1800144d8  test    rcx, rcx
0x1800144db  jz      short loc_1800144F2
0x1800144dd  xor     r8d, r8d; error
0x1800144e0  xor     edx, edx; asyncContext
0x1800144e2  call    cs:__imp_WsCloseServiceProxy
0x1800144e8  mov     rcx, [rbx]; serviceProxy
0x1800144eb  call    cs:__imp_WsFreeServiceProxy
0x1800144f1  nop
0x1800144f2  add     rsp, 20h
0x1800144f6  pop     rbx
0x1800144f7  retn
```
