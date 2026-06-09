# CFveApiBase::DpapiNgProtectKey(ushort const *,_FVE_DATUM_KEY const *,uchar * *,ulong *)

- ea: `0x180085010`
- end: `0x1800850e3`
- name: `?DpapiNgProtectKey@CFveApiBase@@MEBAJPEBGPEBU_FVE_DATUM_KEY@@PEAPEAEPEAK@Z`
- size: `211`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, const unsigned __int16 *, const struct _FVE_DATUM_KEY *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180085010`
- `0x18011f010`

## import_xrefs

- `ncrypt!NCryptProtectSecret` at `0x1800850a1`
- `ncrypt!NCryptProtectSecret` at `0x1800850a1`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x180085050`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x180085050`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x1800850b9`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180124267`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x1800850b9`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180124267`

## pseudocode

```c
__int64 __fastcall CFveApiBase::DpapiNgProtectKey(
        CFveApiBase *this,
        const unsigned __int16 *a2,
        const struct _FVE_DATUM_KEY *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  int v7; // ebx
  unsigned __int16 v8; // ax
  __int64 v10; // [rsp+40h] [rbp-28h] BYREF

  v10 = 0;
  v7 = NCryptCreateProtectionDescriptor(a2, 0, &v10);
  if ( v7 >= 0 )
  {
    v8 = 0;
    if ( *(_WORD *)a3 >= 0xCu )
      v8 = *(_WORD *)a3 - 12;
    v7 = NCryptProtectSecret(v10, 0, (char *)a3 + 12, v8, &qword_18012C7E0, 0, a4, a5);
  }
  if ( v10 )
    NCryptCloseProtectionDescriptor();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180085010  mov     [rsp+arg_0], rbx
0x180085015  push    rsi
0x180085016  push    rdi
0x180085017  push    r14
0x180085019  sub     rsp, 50h
0x18008501d  mov     rax, cs:__security_cookie
0x180085024  xor     rax, rsp
0x180085027  mov     [rsp+68h+var_20], rax
0x18008502c  mov     rsi, r9
0x18008502f  mov     rdi, r8
0x180085032  mov     rax, rdx
0x180085035  mov     r14, [rsp+68h+arg_20]
0x18008503d  mov     [rsp+68h+var_28], 0
0x180085046  lea     r8, [rsp+68h+var_28]
0x18008504b  xor     edx, edx
0x18008504d  mov     rcx, rax
0x180085050  call    cs:__imp_NCryptCreateProtectionDescriptor
0x180085057  nop     dword ptr [rax+rax+00h]
0x18008505c  mov     ebx, eax
0x18008505e  test    eax, eax
0x180085060  js      short loc_1800850AF
0x180085062  movzx   edx, word ptr [rdi]
0x180085065  sub     dx, 0Ch
0x180085069  xor     eax, eax
0x18008506b  cmp     word ptr [rdi], 0Ch
0x18008506f  cmovnb  ax, dx
0x180085073  movzx   r9d, ax
0x180085077  lea     r8, [rdi+0Ch]
0x18008507b  mov     [rsp+68h+var_30], r14
0x180085080  mov     [rsp+68h+var_38], rsi
0x180085085  mov     [rsp+68h+var_40], 0
0x18008508e  lea     rax, qword_18012C7E0
0x180085095  mov     [rsp+68h+var_48], rax
0x18008509a  xor     edx, edx
0x18008509c  mov     rcx, [rsp+68h+var_28]
0x1800850a1  call    cs:__imp_NCryptProtectSecret
0x1800850a8  nop     dword ptr [rax+rax+00h]
0x1800850ad  mov     ebx, eax
0x1800850af  mov     rcx, [rsp+68h+var_28]
0x1800850b4  test    rcx, rcx
0x1800850b7  jz      short loc_1800850C5
0x1800850b9  call    cs:__imp_NCryptCloseProtectionDescriptor
0x1800850c0  nop     dword ptr [rax+rax+00h]
0x1800850c5  mov     eax, ebx
0x1800850c7  mov     rcx, [rsp+68h+var_20]
0x1800850cc  xor     rcx, rsp; StackCookie
0x1800850cf  call    __security_check_cookie
0x1800850d4  mov     rbx, [rsp+68h+arg_0]
0x1800850d9  add     rsp, 50h
0x1800850dd  pop     r14
0x1800850df  pop     rdi
0x1800850e0  pop     rsi
0x1800850e1  retn
0x180124255  push    rbp
0x180124257  sub     rsp, 40h
0x18012425b  mov     rbp, rdx
0x18012425e  mov     rcx, [rbp+40h]
0x180124262  test    rcx, rcx
0x180124265  jz      short loc_180124274
0x180124267  call    cs:__imp_NCryptCloseProtectionDescriptor
0x18012426e  nop     dword ptr [rax+rax+00h]
0x180124273  nop
0x180124274  add     rsp, 40h
0x180124278  pop     rbp
0x180124279  retn
```
