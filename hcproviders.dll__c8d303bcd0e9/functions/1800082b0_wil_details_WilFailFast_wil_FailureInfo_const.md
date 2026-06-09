# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800082b0`
- end: `0x180008357`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005ec0`
- `0x180005f74`
- `0x180006224`

## callees

- `0x1800082b0`
- `0x1800083ac`
- `0x180009e16`
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
0x1800082b0  push    rbx
0x1800082b2  sub     rsp, 0C0h
0x1800082b9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1800082c0  mov     rbx, rcx
0x1800082c3  test    rax, rax
0x1800082c6  jz      short loc_1800082CD
0x1800082c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082cd  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800082d4  test    rax, rax
0x1800082d7  jz      short loc_1800082E1
0x1800082d9  mov     rcx, rbx
0x1800082dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e1  xor     edx, edx; Val
0x1800082e3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800082e8  mov     r8d, 98h; Size
0x1800082ee  call    memset_0
0x1800082f3  mov     rcx, [rbx+88h]
0x1800082fa  mov     r8d, 1; struct _CONTEXT *
0x180008300  mov     [rsp+0C8h+var_90], r8d
0x180008305  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000830d  mov     [rsp+0C8h+var_A4], r8d
0x180008312  mov     [rsp+0C8h+var_88], 7
0x18000831b  test    rcx, rcx
0x18000831e  jnz     short loc_18000832B
0x180008320  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008325  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000832b  movsxd  rax, dword ptr [rbx+8]
0x18000832f  xor     r8d, r8d; struct _CONTEXT *
0x180008332  mov     [rsp+0C8h+var_80], rax
0x180008337  mov     eax, [rbx+40h]
0x18000833a  mov     [rsp+0C8h+var_98], rcx
0x18000833f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008344  mov     [rsp+0C8h+var_78], rax
0x180008349  mov     [rsp+0C8h+var_90], 3
0x180008351  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
