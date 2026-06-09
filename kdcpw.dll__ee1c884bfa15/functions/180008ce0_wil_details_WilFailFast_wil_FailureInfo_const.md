# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180008ce0`
- end: `0x180008d87`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002b14`
- `0x180002d7c`
- `0x180003018`

## callees

- `0x180001f88`
- `0x180008ce0`
- `0x180008d90`
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
0x180008ce0  push    rbx
0x180008ce2  sub     rsp, 0C0h
0x180008ce9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180008cf0  mov     rbx, rcx
0x180008cf3  test    rax, rax
0x180008cf6  jz      short loc_180008CFD
0x180008cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfd  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008d04  test    rax, rax
0x180008d07  jz      short loc_180008D11
0x180008d09  mov     rcx, rbx
0x180008d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d11  xor     edx, edx; Val
0x180008d13  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008d18  mov     r8d, 98h; Size
0x180008d1e  call    memset_0
0x180008d23  mov     rcx, [rbx+88h]
0x180008d2a  mov     r8d, 1; struct _CONTEXT *
0x180008d30  mov     [rsp+0C8h+var_90], r8d
0x180008d35  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180008d3d  mov     [rsp+0C8h+var_A4], r8d
0x180008d42  mov     [rsp+0C8h+var_88], 7
0x180008d4b  test    rcx, rcx
0x180008d4e  jnz     short loc_180008D5B
0x180008d50  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008d55  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180008d5b  movsxd  rax, dword ptr [rbx+8]
0x180008d5f  xor     r8d, r8d; struct _CONTEXT *
0x180008d62  mov     [rsp+0C8h+var_80], rax
0x180008d67  mov     eax, [rbx+40h]
0x180008d6a  mov     [rsp+0C8h+var_98], rcx
0x180008d6f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008d74  mov     [rsp+0C8h+var_78], rax
0x180008d79  mov     [rsp+0C8h+var_90], 3
0x180008d81  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
