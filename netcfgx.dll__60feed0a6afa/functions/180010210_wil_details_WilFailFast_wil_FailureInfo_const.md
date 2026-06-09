# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180010210`
- end: `0x1800102b7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b9e4`
- `0x18000bc54`
- `0x18000bef0`
- `0x18000c4d8`
- `0x18000f9bc`

## callees

- `0x180002a40`
- `0x180010210`
- `0x18001036c`
- `0x180013010`

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
0x180010210  push    rbx
0x180010212  sub     rsp, 0C0h
0x180010219  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180010220  mov     rbx, rcx
0x180010223  test    rax, rax
0x180010226  jz      short loc_18001022D
0x180010228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010234  test    rax, rax
0x180010237  jz      short loc_180010241
0x180010239  mov     rcx, rbx
0x18001023c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010241  xor     edx, edx; Val
0x180010243  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180010248  mov     r8d, 98h; Size
0x18001024e  call    memset_0
0x180010253  mov     rcx, [rbx+88h]
0x18001025a  mov     r8d, 1; struct _CONTEXT *
0x180010260  mov     [rsp+0C8h+var_90], r8d
0x180010265  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18001026d  mov     [rsp+0C8h+var_A4], r8d
0x180010272  mov     [rsp+0C8h+var_88], 7
0x18001027b  test    rcx, rcx
0x18001027e  jnz     short loc_18001028B
0x180010280  lea     rcx, [rsp+0C8h+var_A8]; this
0x180010285  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18001028b  movsxd  rax, dword ptr [rbx+8]
0x18001028f  xor     r8d, r8d; struct _CONTEXT *
0x180010292  mov     [rsp+0C8h+var_80], rax
0x180010297  mov     eax, [rbx+40h]
0x18001029a  mov     [rsp+0C8h+var_98], rcx
0x18001029f  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800102a4  mov     [rsp+0C8h+var_78], rax
0x1800102a9  mov     [rsp+0C8h+var_90], 3
0x1800102b1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
