# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180008360`
- end: `0x180008407`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002670`
- `0x1800061cc`
- `0x180006280`
- `0x180008b38`

## callees

- `0x180005b2c`
- `0x180008360`
- `0x180008410`
- `0x18000b010`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilFailFast(wil::details *this, const struct wil::FailureInfo *a2)
{
  struct _EXCEPTION_RECORD *v3; // rdx
  unsigned int v4; // r9d
  __int64 v5; // rcx
  __int64 v6; // rax
  _DWORD v7[4]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+30h] [rbp-98h]
  int v9; // [rsp+38h] [rbp-90h]
  __int64 v10; // [rsp+40h] [rbp-88h]
  __int64 v11; // [rsp+48h] [rbp-80h]
  __int64 v12; // [rsp+50h] [rbp-78h]

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(this, a2);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(this, a2);
  memset_0(v7, 0, 0x98u);
  v5 = *((_QWORD *)this + 17);
  v9 = 1;
  v7[0] = -1073740791;
  v7[1] = 1;
  v10 = 7;
  if ( !v5 )
    wil::details::WilRaiseFailFastException((wil::details *)v7, v3, (struct _CONTEXT *)1, v4);
  v11 = *((int *)this + 2);
  v6 = *((unsigned int *)this + 16);
  v8 = v5;
  v12 = v6;
  v9 = 3;
  wil::details::WilRaiseFailFastException((wil::details *)v7, v3, 0, v4);
}

```

## disassembly

```asm
0x180008360  push    rbx
0x180008362  sub     rsp, 0C0h
0x180008369  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180008370  mov     rbx, rcx
0x180008373  test    rax, rax
0x180008376  jz      short loc_18000837D
0x180008378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000837d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008384  test    rax, rax
0x180008387  jz      short loc_180008391
0x180008389  mov     rcx, rbx
0x18000838c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008391  xor     edx, edx; Val
0x180008393  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008398  mov     r8d, 98h; Size
0x18000839e  call    memset_0
0x1800083a3  mov     rcx, [rbx+88h]
0x1800083aa  mov     r8d, 1; struct _CONTEXT *
0x1800083b0  mov     [rsp+0C8h+var_90], r8d
0x1800083b5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1800083bd  mov     [rsp+0C8h+var_A4], r8d
0x1800083c2  mov     [rsp+0C8h+var_88], 7
0x1800083cb  test    rcx, rcx
0x1800083ce  jnz     short loc_1800083DB
0x1800083d0  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800083d5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800083db  movsxd  rax, dword ptr [rbx+8]
0x1800083df  xor     r8d, r8d; struct _CONTEXT *
0x1800083e2  mov     [rsp+0C8h+var_80], rax
0x1800083e7  mov     eax, [rbx+40h]
0x1800083ea  mov     [rsp+0C8h+var_98], rcx
0x1800083ef  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800083f4  mov     [rsp+0C8h+var_78], rax
0x1800083f9  mov     [rsp+0C8h+var_90], 3
0x180008401  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
