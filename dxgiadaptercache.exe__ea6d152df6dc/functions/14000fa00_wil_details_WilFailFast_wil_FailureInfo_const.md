# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x14000fa00`
- end: `0x14000faa7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140003cd4`
- `0x140003f54`
- `0x1400042ec`
- `0x140004598`
- `0x14000672c`
- `0x14000d500`

## callees

- `0x140002d4c`
- `0x14000fa00`
- `0x14000fb5c`
- `0x140012010`

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
0x14000fa00  push    rbx
0x14000fa02  sub     rsp, 0C0h
0x14000fa09  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x14000fa10  mov     rbx, rcx
0x14000fa13  test    rax, rax
0x14000fa16  jz      short loc_14000FA1D
0x14000fa18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa1d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000fa24  test    rax, rax
0x14000fa27  jz      short loc_14000FA31
0x14000fa29  mov     rcx, rbx
0x14000fa2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa31  xor     edx, edx; Val
0x14000fa33  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000fa38  mov     r8d, 98h; Size
0x14000fa3e  call    memset_0
0x14000fa43  mov     rcx, [rbx+88h]
0x14000fa4a  mov     r8d, 1; struct _CONTEXT *
0x14000fa50  mov     [rsp+0C8h+var_90], r8d
0x14000fa55  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000fa5d  mov     [rsp+0C8h+var_A4], r8d
0x14000fa62  mov     [rsp+0C8h+var_88], 7
0x14000fa6b  test    rcx, rcx
0x14000fa6e  jnz     short loc_14000FA7B
0x14000fa70  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000fa75  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000fa7b  movsxd  rax, dword ptr [rbx+8]
0x14000fa7f  xor     r8d, r8d; struct _CONTEXT *
0x14000fa82  mov     [rsp+0C8h+var_80], rax
0x14000fa87  mov     eax, [rbx+40h]
0x14000fa8a  mov     [rsp+0C8h+var_98], rcx
0x14000fa8f  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000fa94  mov     [rsp+0C8h+var_78], rax
0x14000fa99  mov     [rsp+0C8h+var_90], 3
0x14000faa1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
