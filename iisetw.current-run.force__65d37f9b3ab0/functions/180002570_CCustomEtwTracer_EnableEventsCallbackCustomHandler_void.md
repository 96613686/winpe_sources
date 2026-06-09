# CCustomEtwTracer::EnableEventsCallbackCustomHandler(void)

- ea: `0x180002570`
- end: `0x1800025d5`
- name: `?EnableEventsCallbackCustomHandler@CCustomEtwTracer@@EEAAKXZ`
- size: `101`
- prototype: `unsigned int __fastcall(CCustomEtwTracer *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall CCustomEtwTracer::EnableEventsCallbackCustomHandler(CCustomEtwTracer *this)
{
  __int64 v1; // rax
  char *v3; // [rsp+30h] [rbp-28h] BYREF
  int v4; // [rsp+38h] [rbp-20h]
  int v5; // [rsp+3Ch] [rbp-1Ch]
  __int64 v6; // [rsp+40h] [rbp-18h]

  v6 = 1;
  v3 = (char *)this + 48;
  v4 = *((_DWORD *)this + 10);
  v5 = *((_DWORD *)this + 11);
  v1 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 184LL))(s_pGlobalInfo);
  (*(void (__fastcall **)(__int64, void *, char **, __int64))(*(_QWORD *)v1 + 8LL))(v1, s_pModuleContext, &v3, 1);
  return 0;
}

```

## disassembly

```asm
0x180002570  sub     rsp, 58h
0x180002574  lea     rax, [rcx+30h]
0x180002578  mov     [rsp+58h+var_18], 1
0x180002581  mov     [rsp+58h+var_28], rax
0x180002586  mov     eax, [rcx+28h]
0x180002589  mov     [rsp+58h+var_20], eax
0x18000258d  mov     eax, [rcx+2Ch]
0x180002590  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180002597  mov     [rsp+58h+var_1C], eax
0x18000259b  mov     rax, [rcx]
0x18000259e  mov     rax, [rax+0B8h]
0x1800025a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025aa  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x1800025b1  lea     r8, [rsp+58h+var_28]
0x1800025b6  mov     r10, rax
0x1800025b9  mov     r9d, 1
0x1800025bf  mov     rcx, [rax]
0x1800025c2  mov     rax, [rcx+8]
0x1800025c6  mov     rcx, r10
0x1800025c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ce  xor     eax, eax
0x1800025d0  add     rsp, 58h
0x1800025d4  retn
```
