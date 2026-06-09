# OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)

- ea: `0x18001b190`
- end: `0x18001b291`
- name: `?OpenDataHandler@@YAXPEBVCMediaType@@PEAUIUnknown@@PEAPEAUIKsDataTypeHandler@@PEAPEAU2@@Z`
- size: `257`
- prototype: `void __fastcall(const _AMMediaType *rclsid, LPUNKNOWN pUnkOuter, IUnknown **, LPVOID *ppv)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800192a0`
- `0x180020f2c`
- `0x180028eb4`
- `0x18002998c`
- `0x1800315e0`

## callees

- `0x18001b190`
- `0x180045010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001b1ca`
- `ole32!CoCreateInstance` at `0x18001b1f5`
- `ole32!CoCreateInstance` at `0x18001b21f`
- `ole32!CoCreateInstance` at `0x18001b1ca`
- `ole32!CoCreateInstance` at `0x18001b1f5`
- `ole32!CoCreateInstance` at `0x18001b21f`

## pseudocode

```c
void __fastcall OpenDataHandler(const _AMMediaType *rclsid, LPUNKNOWN pUnkOuter, IUnknown **a3, LPVOID *ppv)
{
  *a3 = 0;
  *ppv = 0;
  CoCreateInstance(&rclsid->formattype, pUnkOuter, 0x401u, &GUID_00000000_0000_0000_c000_000000000046, ppv);
  if ( !*ppv )
  {
    CoCreateInstance(&rclsid->subtype, pUnkOuter, 0x401u, &GUID_00000000_0000_0000_c000_000000000046, ppv);
    if ( !*ppv )
      CoCreateInstance(&rclsid->majortype, pUnkOuter, 0x401u, &GUID_00000000_0000_0000_c000_000000000046, ppv);
  }
  if ( *ppv )
  {
    (**(void (__fastcall ***)(LPVOID, GUID *, IUnknown **))*ppv)(*ppv, &GUID_5ffbaa02_49a3_11d0_9f36_00aa00a216a1, a3);
    if ( *a3 )
    {
      (*a3)->Release(*a3);
      ((void (__fastcall *)(IUnknown *, const _AMMediaType *))(*a3)->__vftable[2].AddRef)(*a3, rclsid);
    }
    else
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 16LL))(*ppv);
      *ppv = 0;
    }
  }
}

```

## disassembly

```asm
0x18001b190  push    rbx
0x18001b192  push    rsi
0x18001b193  push    rdi
0x18001b194  push    r14
0x18001b196  sub     rsp, 38h
0x18001b19a  mov     qword ptr [r8], 0
0x18001b1a1  mov     rbx, r9
0x18001b1a4  mov     qword ptr [r9], 0
0x18001b1ab  mov     r14, r8
0x18001b1ae  mov     rdi, rcx
0x18001b1b1  mov     [rsp+58h+ppv], rbx; ppv
0x18001b1b6  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001b1bd  add     rcx, 2Ch ; ','; rclsid
0x18001b1c1  mov     r8d, 401h; dwClsContext
0x18001b1c7  mov     rsi, rdx
0x18001b1ca  call    cs:__imp_CoCreateInstance
0x18001b1d1  nop     dword ptr [rax+rax+00h]
0x18001b1d6  cmp     qword ptr [rbx], 0
0x18001b1da  jnz     short loc_18001B22B
0x18001b1dc  lea     rcx, [rdi+10h]; rclsid
0x18001b1e0  mov     [rsp+58h+ppv], rbx; ppv
0x18001b1e5  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001b1ec  mov     r8d, 401h; dwClsContext
0x18001b1f2  mov     rdx, rsi; pUnkOuter
0x18001b1f5  call    cs:__imp_CoCreateInstance
0x18001b1fc  nop     dword ptr [rax+rax+00h]
0x18001b201  cmp     qword ptr [rbx], 0
0x18001b205  jnz     short loc_18001B22B
0x18001b207  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001b20e  mov     [rsp+58h+ppv], rbx; ppv
0x18001b213  mov     r8d, 401h; dwClsContext
0x18001b219  mov     rdx, rsi; pUnkOuter
0x18001b21c  mov     rcx, rdi; rclsid
0x18001b21f  call    cs:__imp_CoCreateInstance
0x18001b226  nop     dword ptr [rax+rax+00h]
0x18001b22b  mov     rcx, [rbx]
0x18001b22e  test    rcx, rcx
0x18001b231  jz      short loc_18001B286
0x18001b233  mov     rax, [rcx]
0x18001b236  lea     rdx, _GUID_5ffbaa02_49a3_11d0_9f36_00aa00a216a1
0x18001b23d  mov     r8, r14
0x18001b240  mov     rax, [rax]
0x18001b243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b248  mov     rcx, [r14]
0x18001b24b  test    rcx, rcx
0x18001b24e  jz      short loc_18001B270
0x18001b250  mov     rax, [rcx]
0x18001b253  mov     rax, [rax+10h]
0x18001b257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b25c  mov     rcx, [r14]
0x18001b25f  mov     rdx, rdi
0x18001b262  mov     rax, [rcx]
0x18001b265  mov     rax, [rax+38h]
0x18001b269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b26e  jmp     short loc_18001B286
0x18001b270  mov     rcx, [rbx]
0x18001b273  mov     rax, [rcx]
0x18001b276  mov     rax, [rax+10h]
0x18001b27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b27f  mov     qword ptr [rbx], 0
0x18001b286  add     rsp, 38h
0x18001b28a  pop     r14
0x18001b28c  pop     rdi
0x18001b28d  pop     rsi
0x18001b28e  pop     rbx
0x18001b28f  retn
```
