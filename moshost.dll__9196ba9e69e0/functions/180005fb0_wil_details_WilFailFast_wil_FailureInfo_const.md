# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180005fb0`
- end: `0x180006057`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002c90`
- `0x180002ef8`
- `0x180003194`

## callees

- `0x180002722`
- `0x180005fb0`
- `0x180006060`
- `0x18000d010`

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
0x180005fb0  push    rbx
0x180005fb2  sub     rsp, 0C0h
0x180005fb9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180005fc0  mov     rbx, rcx
0x180005fc3  test    rax, rax
0x180005fc6  jz      short loc_180005FCD
0x180005fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fcd  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005fd4  test    rax, rax
0x180005fd7  jz      short loc_180005FE1
0x180005fd9  mov     rcx, rbx
0x180005fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe1  xor     edx, edx; Val
0x180005fe3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180005fe8  mov     r8d, 98h; Size
0x180005fee  call    memset_0
0x180005ff3  mov     rcx, [rbx+88h]
0x180005ffa  mov     r8d, 1; struct _CONTEXT *
0x180006000  mov     [rsp+0C8h+var_90], r8d
0x180006005  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000600d  mov     [rsp+0C8h+var_A4], r8d
0x180006012  mov     [rsp+0C8h+var_88], 7
0x18000601b  test    rcx, rcx
0x18000601e  jnz     short loc_18000602B
0x180006020  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006025  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000602b  movsxd  rax, dword ptr [rbx+8]
0x18000602f  xor     r8d, r8d; struct _CONTEXT *
0x180006032  mov     [rsp+0C8h+var_80], rax
0x180006037  mov     eax, [rbx+40h]
0x18000603a  mov     [rsp+0C8h+var_98], rcx
0x18000603f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180006044  mov     [rsp+0C8h+var_78], rax
0x180006049  mov     [rsp+0C8h+var_90], 3
0x180006051  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
