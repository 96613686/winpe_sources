# CCustomEtwTracerV2::EnableEventsCallbackCustomHandler(void)

- ea: `0x1800025e0`
- end: `0x180002654`
- name: `?EnableEventsCallbackCustomHandler@CCustomEtwTracerV2@@UEAAKXZ`
- size: `116`
- prototype: `unsigned int __fastcall(CCustomEtwTracerV2 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003020`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CCustomEtwTracerV2::EnableEventsCallbackCustomHandler(CCustomEtwTracerV2 *this)
{
  __int64 v1; // rcx
  __int64 v2; // rax
  __int128 v4; // [rsp+30h] [rbp-28h] BYREF
  __int64 v5; // [rsp+40h] [rbp-18h]

  v4 = 0;
  v5 = 0;
  *(_QWORD *)&v4 = CCustomEtwTracerV2::QueryIISProviderGUID(this);
  *((_QWORD *)&v4 + 1) = *(_QWORD *)(v1 + 20);
  LODWORD(v5) = 1;
  v2 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 184LL))(s_pGlobalInfo);
  (*(void (__fastcall **)(__int64, void *, __int128 *, __int64))(*(_QWORD *)v2 + 8LL))(v2, s_pModuleContext, &v4, 1);
  return 0;
}

```

## disassembly

```asm
0x1800025e0  sub     rsp, 58h
0x1800025e4  xor     eax, eax
0x1800025e6  xorps   xmm0, xmm0
0x1800025e9  movups  [rsp+58h+var_28], xmm0
0x1800025ee  mov     [rsp+58h+var_18], rax
0x1800025f3  call    ?QueryIISProviderGUID@CCustomEtwTracerV2@@QEAAPEBU_GUID@@XZ; CCustomEtwTracerV2::QueryIISProviderGUID(void)
0x1800025f8  mov     qword ptr [rsp+58h+var_28], rax
0x1800025fd  mov     eax, [rcx+14h]
0x180002600  mov     dword ptr [rsp+58h+var_28+8], eax
0x180002604  mov     eax, [rcx+18h]
0x180002607  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000260e  mov     dword ptr [rsp+58h+var_28+0Ch], eax
0x180002612  mov     dword ptr [rsp+58h+var_18], 1
0x18000261a  mov     rax, [rcx]
0x18000261d  mov     rax, [rax+0B8h]
0x180002624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002629  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002630  lea     r8, [rsp+58h+var_28]
0x180002635  mov     r10, rax
0x180002638  mov     r9d, 1
0x18000263e  mov     rcx, [rax]
0x180002641  mov     rax, [rcx+8]
0x180002645  mov     rcx, r10
0x180002648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264d  xor     eax, eax
0x18000264f  add     rsp, 58h
0x180002653  retn
```
