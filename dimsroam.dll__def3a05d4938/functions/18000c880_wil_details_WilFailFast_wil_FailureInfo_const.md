# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000c880`
- end: `0x18000c927`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800079d0`
- `0x180007c38`
- `0x180007ed4`

## callees

- `0x18000c880`
- `0x18000c930`
- `0x18000d89e`
- `0x18000e010`

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
0x18000c880  push    rbx
0x18000c882  sub     rsp, 0C0h
0x18000c889  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000c890  mov     rbx, rcx
0x18000c893  test    rax, rax
0x18000c896  jz      short loc_18000C89D
0x18000c898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c89d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c8a4  test    rax, rax
0x18000c8a7  jz      short loc_18000C8B1
0x18000c8a9  mov     rcx, rbx
0x18000c8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b1  xor     edx, edx; Val
0x18000c8b3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000c8b8  mov     r8d, 98h; Size
0x18000c8be  call    memset_0
0x18000c8c3  mov     rcx, [rbx+88h]
0x18000c8ca  mov     r8d, 1; struct _CONTEXT *
0x18000c8d0  mov     [rsp+0C8h+var_90], r8d
0x18000c8d5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000c8dd  mov     [rsp+0C8h+var_A4], r8d
0x18000c8e2  mov     [rsp+0C8h+var_88], 7
0x18000c8eb  test    rcx, rcx
0x18000c8ee  jnz     short loc_18000C8FB
0x18000c8f0  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000c8f5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000c8fb  movsxd  rax, dword ptr [rbx+8]
0x18000c8ff  xor     r8d, r8d; struct _CONTEXT *
0x18000c902  mov     [rsp+0C8h+var_80], rax
0x18000c907  mov     eax, [rbx+40h]
0x18000c90a  mov     [rsp+0C8h+var_98], rcx
0x18000c90f  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000c914  mov     [rsp+0C8h+var_78], rax
0x18000c919  mov     [rsp+0C8h+var_90], 3
0x18000c921  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
