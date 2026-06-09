# SoftwareSymmetricPopKey::DeriveKey(uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x18001f2d0`
- end: `0x18001f39a`
- name: `?DeriveKey@SoftwareSymmetricPopKey@@MEAAJPEAEK0K0K@Z`
- size: `202`
- prototype: `int __fastcall(SoftwareSymmetricPopKey *this, unsigned __int8 *, int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004de0`
- `0x18001368c`
- `0x18001f2d0`

## import_xrefs

- `bcrypt!BCryptKeyDerivation` at `0x18001f35f`
- `bcrypt!BCryptKeyDerivation` at `0x18001f35f`

## string_xrefs

- `0x18001f36d`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\softwaresymmetricpopkey.cpp`

## pseudocode

```c
int __fastcall SoftwareSymmetricPopKey::DeriveKey(
        SoftwareSymmetricPopKey *this,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  __int64 v7; // rcx
  int v8; // eax
  int v10; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v11[2]; // [rsp+38h] [rbp-48h] BYREF
  _QWORD *v12; // [rsp+40h] [rbp-40h]
  _QWORD v13[2]; // [rsp+48h] [rbp-38h] BYREF
  int v14; // [rsp+58h] [rbp-28h]
  int v15; // [rsp+5Ch] [rbp-24h]
  unsigned __int8 *v16; // [rsp+60h] [rbp-20h]
  unsigned int v17; // [rsp+68h] [rbp-18h]
  int v18; // [rsp+6Ch] [rbp-14h]
  unsigned __int8 *v19; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v7 = *((_QWORD *)this + 1);
  v12 = v13;
  v13[1] = L"SHA256";
  v15 = 14;
  v17 = a5;
  v16 = a2;
  v14 = a3;
  v19 = a4;
  v11[0] = 0;
  v11[1] = 3;
  v13[0] = 14;
  v18 = 13;
  v10 = 0;
  v8 = BCryptKeyDerivation(v7, v11, a6, a7);
  if ( v8 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x49,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\softwaresymmetricpopkey.cpp",
             (const char *)(unsigned int)v8,
             (int)&v10);
}

```

## disassembly

```asm
0x18001f2d0  push    rbp
0x18001f2d2  mov     rbp, rsp
0x18001f2d5  sub     rsp, 80h
0x18001f2dc  mov     rax, cs:__security_cookie
0x18001f2e3  xor     rax, rsp
0x18001f2e6  mov     [rbp+var_8], rax
0x18001f2ea  mov     r10, [rbp+arg_28]
0x18001f2ee  lea     rax, [rbp+var_38]
0x18001f2f2  mov     rcx, [rcx+8]
0x18001f2f6  mov     [rbp+var_40], rax
0x18001f2fa  lea     rax, aSha256; "SHA256"
0x18001f301  mov     [rbp+var_30], rax
0x18001f305  mov     eax, 0Eh
0x18001f30a  mov     [rbp+var_24], eax
0x18001f30d  mov     eax, [rbp+arg_20]
0x18001f310  mov     [rbp+var_18], eax
0x18001f313  lea     rax, [rbp+var_50]
0x18001f317  mov     [rbp+var_20], rdx
0x18001f31b  lea     rdx, [rbp+var_48]
0x18001f31f  mov     [rbp+var_28], r8d
0x18001f323  mov     r8, r10
0x18001f326  mov     [rbp+var_10], r9
0x18001f32a  mov     r9d, [rbp+arg_30]
0x18001f32e  mov     [rsp+80h+var_58], 0
0x18001f336  mov     qword ptr [rsp+80h+var_60], rax; int
0x18001f33b  mov     [rbp+var_48], 0
0x18001f342  mov     [rbp+var_44], 3
0x18001f349  mov     [rbp+var_38], 0Eh
0x18001f351  mov     [rbp+var_14], 0Dh
0x18001f358  mov     [rbp+var_50], 0
0x18001f35f  call    cs:__imp_BCryptKeyDerivation
0x18001f365  test    eax, eax
0x18001f367  jns     short loc_18001F383
0x18001f369  mov     rcx, [rbp+8]; this
0x18001f36d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001f374  mov     r9d, eax; char *
0x18001f377  mov     edx, 49h ; 'I'; void *
0x18001f37c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f381  jmp     short loc_18001F385
0x18001f383  xor     eax, eax
0x18001f385  mov     rcx, [rbp+var_8]
0x18001f389  xor     rcx, rsp; StackCookie
0x18001f38c  call    __security_check_cookie
0x18001f391  add     rsp, 80h
0x18001f398  pop     rbp
0x18001f399  retn
```
