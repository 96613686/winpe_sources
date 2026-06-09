# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800054fc`
- end: `0x1800055a3`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800023a0`
- `0x180002624`
- `0x1800028d4`

## callees

- `0x180001fea`
- `0x1800054fc`
- `0x1800055ac`
- `0x180007010`

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
0x1800054fc  push    rbx
0x1800054fe  sub     rsp, 0C0h
0x180005505  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000550c  mov     rbx, rcx
0x18000550f  test    rax, rax
0x180005512  jz      short loc_180005519
0x180005514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005519  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005520  test    rax, rax
0x180005523  jz      short loc_18000552D
0x180005525  mov     rcx, rbx
0x180005528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552d  xor     edx, edx; Val
0x18000552f  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180005534  mov     r8d, 98h; Size
0x18000553a  call    memset_0
0x18000553f  mov     rcx, [rbx+88h]
0x180005546  mov     r8d, 1; struct _CONTEXT *
0x18000554c  mov     [rsp+0C8h+var_90], r8d
0x180005551  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180005559  mov     [rsp+0C8h+var_A4], r8d
0x18000555e  mov     [rsp+0C8h+var_88], 7
0x180005567  test    rcx, rcx
0x18000556a  jnz     short loc_180005577
0x18000556c  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005571  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180005577  movsxd  rax, dword ptr [rbx+8]
0x18000557b  xor     r8d, r8d; struct _CONTEXT *
0x18000557e  mov     [rsp+0C8h+var_80], rax
0x180005583  mov     eax, [rbx+40h]
0x180005586  mov     [rsp+0C8h+var_98], rcx
0x18000558b  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005590  mov     [rsp+0C8h+var_78], rax
0x180005595  mov     [rsp+0C8h+var_90], 3
0x18000559d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
