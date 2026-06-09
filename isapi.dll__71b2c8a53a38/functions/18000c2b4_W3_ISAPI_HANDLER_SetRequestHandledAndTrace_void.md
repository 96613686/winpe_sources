# W3_ISAPI_HANDLER::SetRequestHandledAndTrace(void)

- ea: `0x18000c2b4`
- end: `0x18000c31c`
- name: `?SetRequestHandledAndTrace@W3_ISAPI_HANDLER@@AEAAJXZ`
- size: `104`
- prototype: `__int64 __fastcall(W3_ISAPI_HANDLER *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b3d0`
- `0x18000bd8c`
- `0x18000f440`

## callees

- `0x18000b360`
- `0x18000c00c`
- `0x18000c2b4`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall W3_ISAPI_HANDLER::SetRequestHandledAndTrace(W3_ISAPI_HANDLER *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  struct IHttpTraceContext *v4; // rax
  const struct _GUID *v5; // rdx

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 272LL))(v2);
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v3, 0, 0) )
    {
      v4 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 272LL))(*((_QWORD *)this + 1));
      IISISAPIEvents::ISAPI_END::RaiseEvent(v4, v5);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 200LL))(*((_QWORD *)this + 1));
  }
  return 0;
}

```

## disassembly

```asm
0x18000c2b4  push    rbx
0x18000c2b6  sub     rsp, 20h
0x18000c2ba  mov     rbx, rcx
0x18000c2bd  mov     rcx, [rcx+8]
0x18000c2c1  test    rcx, rcx
0x18000c2c4  jz      short loc_18000C314
0x18000c2c6  mov     rax, [rcx]
0x18000c2c9  mov     rax, [rax+110h]
0x18000c2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d5  xor     r8d, r8d
0x18000c2d8  xor     edx, edx
0x18000c2da  mov     rcx, rax
0x18000c2dd  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000c2e2  test    eax, eax
0x18000c2e4  jz      short loc_18000C301
0x18000c2e6  mov     rcx, [rbx+8]
0x18000c2ea  mov     rax, [rcx]
0x18000c2ed  mov     rax, [rax+110h]
0x18000c2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2f9  mov     rcx, rax; struct IHttpTraceContext *
0x18000c2fc  call    ?RaiseEvent@ISAPI_END@IISISAPIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISISAPIEvents::ISAPI_END::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000c301  mov     rcx, [rbx+8]
0x18000c305  mov     rax, [rcx]
0x18000c308  mov     rax, [rax+0C8h]
0x18000c30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c314  xor     eax, eax
0x18000c316  add     rsp, 20h
0x18000c31a  pop     rbx
0x18000c31b  retn
```
