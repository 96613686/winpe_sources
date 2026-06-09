# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180008860`
- end: `0x180008907`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000562c`
- `0x18000589c`
- `0x180005b30`

## callees

- `0x180008860`
- `0x180008910`
- `0x18000b8b0`
- `0x18000d010`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilFailFast(wil::details *this, const struct wil::FailureInfo *a2)
{
  struct _EXCEPTION_RECORD *v3; // rdx
  unsigned int v4; // r9d
  __int64 v5; // rcx
  __int64 v6; // rax
  _QWORD v7[21]; // [rsp+20h] [rbp-A8h] BYREF

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(this, a2);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(this, a2);
  memset(v7, 0, 0x98u);
  v5 = *((_QWORD *)this + 17);
  LODWORD(v7[3]) = 1;
  v7[0] = 0x1C0000409LL;
  v7[4] = 7;
  if ( !v5 )
    wil::details::WilRaiseFailFastException((wil::details *)v7, v3, (struct _CONTEXT *)1, v4);
  v7[5] = *((int *)this + 2);
  v6 = *((unsigned int *)this + 16);
  v7[2] = v5;
  v7[6] = v6;
  LODWORD(v7[3]) = 3;
  wil::details::WilRaiseFailFastException((wil::details *)v7, v3, 0, v4);
}

```

## disassembly

```asm
0x180008860  push    rbx
0x180008862  sub     rsp, 0C0h
0x180008869  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180008870  mov     rbx, rcx
0x180008873  test    rax, rax
0x180008876  jz      short loc_18000887D
0x180008878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000887d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008884  test    rax, rax
0x180008887  jz      short loc_180008891
0x180008889  mov     rcx, rbx
0x18000888c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008891  xor     edx, edx; Val
0x180008893  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008898  mov     r8d, 98h; Size
0x18000889e  call    memset
0x1800088a3  mov     rcx, [rbx+88h]
0x1800088aa  mov     r8d, 1; struct _CONTEXT *
0x1800088b0  mov     [rsp+0C8h+var_90], r8d
0x1800088b5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1800088bd  mov     [rsp+0C8h+var_A4], r8d
0x1800088c2  mov     [rsp+0C8h+var_88], 7
0x1800088cb  test    rcx, rcx
0x1800088ce  jnz     short loc_1800088DB
0x1800088d0  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800088d5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800088db  movsxd  rax, dword ptr [rbx+8]
0x1800088df  xor     r8d, r8d; struct _CONTEXT *
0x1800088e2  mov     [rsp+0C8h+var_80], rax
0x1800088e7  mov     eax, [rbx+40h]
0x1800088ea  mov     [rsp+0C8h+var_98], rcx
0x1800088ef  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800088f4  mov     [rsp+0C8h+var_78], rax
0x1800088f9  mov     [rsp+0C8h+var_90], 3
0x180008901  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
