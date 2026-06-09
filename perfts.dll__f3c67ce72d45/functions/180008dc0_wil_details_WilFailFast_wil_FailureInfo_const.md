# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180008dc0`
- end: `0x180008e67`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003e3c`
- `0x1800040c4`

## callees

- `0x180008dc0`
- `0x180008e70`
- `0x1800098f6`
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
0x180008dc0  push    rbx
0x180008dc2  sub     rsp, 0C0h
0x180008dc9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180008dd0  mov     rbx, rcx
0x180008dd3  test    rax, rax
0x180008dd6  jz      short loc_180008DDD
0x180008dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ddd  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008de4  test    rax, rax
0x180008de7  jz      short loc_180008DF1
0x180008de9  mov     rcx, rbx
0x180008dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df1  xor     edx, edx; Val
0x180008df3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008df8  mov     r8d, 98h; Size
0x180008dfe  call    memset_0
0x180008e03  mov     rcx, [rbx+88h]
0x180008e0a  mov     r8d, 1; struct _CONTEXT *
0x180008e10  mov     [rsp+0C8h+var_90], r8d
0x180008e15  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180008e1d  mov     [rsp+0C8h+var_A4], r8d
0x180008e22  mov     [rsp+0C8h+var_88], 7
0x180008e2b  test    rcx, rcx
0x180008e2e  jnz     short loc_180008E3B
0x180008e30  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008e35  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180008e3b  movsxd  rax, dword ptr [rbx+8]
0x180008e3f  xor     r8d, r8d; struct _CONTEXT *
0x180008e42  mov     [rsp+0C8h+var_80], rax
0x180008e47  mov     eax, [rbx+40h]
0x180008e4a  mov     [rsp+0C8h+var_98], rcx
0x180008e4f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008e54  mov     [rsp+0C8h+var_78], rax
0x180008e59  mov     [rsp+0C8h+var_90], 3
0x180008e61  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
