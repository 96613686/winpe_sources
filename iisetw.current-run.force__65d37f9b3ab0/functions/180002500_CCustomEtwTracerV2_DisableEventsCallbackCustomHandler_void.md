# CCustomEtwTracerV2::DisableEventsCallbackCustomHandler(void)

- ea: `0x180002500`
- end: `0x180002569`
- name: `?DisableEventsCallbackCustomHandler@CCustomEtwTracerV2@@UEAAKXZ`
- size: `105`
- prototype: `unsigned int __fastcall(CCustomEtwTracerV2 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003020`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CCustomEtwTracerV2::DisableEventsCallbackCustomHandler(CCustomEtwTracerV2 *this)
{
  __int64 v1; // rax
  __int128 IISProviderGUID; // [rsp+30h] [rbp-28h] BYREF
  __int64 v4; // [rsp+40h] [rbp-18h]

  IISProviderGUID = (unsigned __int64)CCustomEtwTracerV2::QueryIISProviderGUID(this);
  v4 = 0;
  v1 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 184LL))(s_pGlobalInfo);
  (*(void (__fastcall **)(__int64, void *, __int128 *, __int64))(*(_QWORD *)v1 + 8LL))(
    v1,
    s_pModuleContext,
    &IISProviderGUID,
    1);
  return 0;
}

```

## disassembly

```asm
0x180002500  sub     rsp, 58h
0x180002504  xor     eax, eax
0x180002506  xorps   xmm0, xmm0
0x180002509  movups  [rsp+58h+var_28], xmm0
0x18000250e  mov     [rsp+58h+var_18], rax
0x180002513  call    ?QueryIISProviderGUID@CCustomEtwTracerV2@@QEAAPEBU_GUID@@XZ; CCustomEtwTracerV2::QueryIISProviderGUID(void)
0x180002518  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000251f  mov     qword ptr [rsp+58h+var_28], rax
0x180002524  xor     eax, eax
0x180002526  mov     qword ptr [rsp+58h+var_28+8], rax
0x18000252b  mov     dword ptr [rsp+58h+var_18], eax
0x18000252f  mov     rax, [rcx]
0x180002532  mov     rax, [rax+0B8h]
0x180002539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000253e  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x180002545  lea     r8, [rsp+58h+var_28]
0x18000254a  mov     r10, rax
0x18000254d  mov     r9d, 1
0x180002553  mov     rcx, [rax]
0x180002556  mov     rax, [rcx+8]
0x18000255a  mov     rcx, r10
0x18000255d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002562  xor     eax, eax
0x180002564  add     rsp, 58h
0x180002568  retn
```
