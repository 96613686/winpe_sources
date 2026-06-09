# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x14000cad0`
- end: `0x14000cb77`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140003bd8`
- `0x140003e58`
- `0x140004104`
- `0x140005580`
- `0x14000d8b8`

## callees

- `0x140002c2c`
- `0x14000cad0`
- `0x14000cc2c`
- `0x140011010`

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
0x14000cad0  push    rbx
0x14000cad2  sub     rsp, 0C0h
0x14000cad9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x14000cae0  mov     rbx, rcx
0x14000cae3  test    rax, rax
0x14000cae6  jz      short loc_14000CAED
0x14000cae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000caed  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000caf4  test    rax, rax
0x14000caf7  jz      short loc_14000CB01
0x14000caf9  mov     rcx, rbx
0x14000cafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb01  xor     edx, edx; Val
0x14000cb03  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000cb08  mov     r8d, 98h; Size
0x14000cb0e  call    memset_0
0x14000cb13  mov     rcx, [rbx+88h]
0x14000cb1a  mov     r8d, 1; struct _CONTEXT *
0x14000cb20  mov     [rsp+0C8h+var_90], r8d
0x14000cb25  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000cb2d  mov     [rsp+0C8h+var_A4], r8d
0x14000cb32  mov     [rsp+0C8h+var_88], 7
0x14000cb3b  test    rcx, rcx
0x14000cb3e  jnz     short loc_14000CB4B
0x14000cb40  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000cb45  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000cb4b  movsxd  rax, dword ptr [rbx+8]
0x14000cb4f  xor     r8d, r8d; struct _CONTEXT *
0x14000cb52  mov     [rsp+0C8h+var_80], rax
0x14000cb57  mov     eax, [rbx+40h]
0x14000cb5a  mov     [rsp+0C8h+var_98], rcx
0x14000cb5f  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000cb64  mov     [rsp+0C8h+var_78], rax
0x14000cb69  mov     [rsp+0C8h+var_90], 3
0x14000cb71  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
