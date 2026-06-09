# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140009b3c`
- end: `0x140009be3`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140003090`
- `0x14000330c`
- `0x1400035b4`
- `0x140014d88`

## callees

- `0x14000271f`
- `0x140009b3c`
- `0x140009bec`
- `0x140017010`

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
0x140009b3c  push    rbx
0x140009b3e  sub     rsp, 0C0h
0x140009b45  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140009b4c  mov     rbx, rcx
0x140009b4f  test    rax, rax
0x140009b52  jz      short loc_140009B59
0x140009b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b59  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009b60  test    rax, rax
0x140009b63  jz      short loc_140009B6D
0x140009b65  mov     rcx, rbx
0x140009b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b6d  xor     edx, edx; Val
0x140009b6f  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140009b74  mov     r8d, 98h; Size
0x140009b7a  call    memset_0
0x140009b7f  mov     rcx, [rbx+88h]
0x140009b86  mov     r8d, 1; struct _CONTEXT *
0x140009b8c  mov     [rsp+0C8h+var_90], r8d
0x140009b91  mov     [rsp+0C8h+var_A8], 0C0000409h
0x140009b99  mov     [rsp+0C8h+var_A4], r8d
0x140009b9e  mov     [rsp+0C8h+var_88], 7
0x140009ba7  test    rcx, rcx
0x140009baa  jnz     short loc_140009BB7
0x140009bac  lea     rcx, [rsp+0C8h+var_A8]; this
0x140009bb1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140009bb7  movsxd  rax, dword ptr [rbx+8]
0x140009bbb  xor     r8d, r8d; struct _CONTEXT *
0x140009bbe  mov     [rsp+0C8h+var_80], rax
0x140009bc3  mov     eax, [rbx+40h]
0x140009bc6  mov     [rsp+0C8h+var_98], rcx
0x140009bcb  lea     rcx, [rsp+0C8h+var_A8]; this
0x140009bd0  mov     [rsp+0C8h+var_78], rax
0x140009bd5  mov     [rsp+0C8h+var_90], 3
0x140009bdd  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
