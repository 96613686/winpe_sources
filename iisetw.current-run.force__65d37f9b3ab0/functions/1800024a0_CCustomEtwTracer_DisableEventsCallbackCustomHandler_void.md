# CCustomEtwTracer::DisableEventsCallbackCustomHandler(void)

- ea: `0x1800024a0`
- end: `0x1800024fa`
- name: `?DisableEventsCallbackCustomHandler@CCustomEtwTracer@@EEAAKXZ`
- size: `90`
- prototype: `unsigned int __fastcall(CCustomEtwTracer *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall CCustomEtwTracer::DisableEventsCallbackCustomHandler(CCustomEtwTracer *this)
{
  __int64 v1; // rax
  _QWORD v3[5]; // [rsp+30h] [rbp-28h] BYREF

  v3[0] = (char *)this + 48;
  v3[2] = 0;
  v3[1] = 0;
  v1 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 184LL))(s_pGlobalInfo);
  (*(void (__fastcall **)(__int64, void *, _QWORD *, __int64))(*(_QWORD *)v1 + 8LL))(v1, s_pModuleContext, v3, 1);
  return 0;
}

```

## disassembly

```asm
0x1800024a0  sub     rsp, 58h
0x1800024a4  lea     rax, [rcx+30h]
0x1800024a8  xor     edx, edx
0x1800024aa  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800024b1  mov     [rsp+58h+var_28], rax
0x1800024b6  mov     [rsp+58h+var_18], rdx
0x1800024bb  mov     [rsp+58h+var_20], rdx
0x1800024c0  mov     rax, [rcx]
0x1800024c3  mov     rax, [rax+0B8h]
0x1800024ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024cf  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x1800024d6  lea     r8, [rsp+58h+var_28]
0x1800024db  mov     r10, rax
0x1800024de  mov     r9d, 1
0x1800024e4  mov     rcx, [rax]
0x1800024e7  mov     rax, [rcx+8]
0x1800024eb  mov     rcx, r10
0x1800024ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f3  xor     eax, eax
0x1800024f5  add     rsp, 58h
0x1800024f9  retn
```
