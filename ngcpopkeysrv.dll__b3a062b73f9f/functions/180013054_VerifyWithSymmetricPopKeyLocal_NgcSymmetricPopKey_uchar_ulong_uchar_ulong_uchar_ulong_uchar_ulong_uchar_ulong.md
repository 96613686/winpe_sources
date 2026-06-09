# VerifyWithSymmetricPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x180013054`
- end: `0x180013111`
- name: `?VerifyWithSymmetricPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1K1K@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct NgcSymmetricPopKey *, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f6b0`

## callees

- `0x18000b0fc`
- `0x180013054`
- `0x180028010`

## string_xrefs

- `0x180013085`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall VerifyWithSymmetricPopKeyLocal(
        struct NgcSymmetricPopKey *a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11)
{
  int v12; // ebx
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *))(*(_QWORD *)a1 + 8LL))(a1, a2);
  if ( v12 < 0 )
  {
    v13 = 86;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
      (const char *)(unsigned int)v12,
      v15);
    return (unsigned int)v12;
  }
  v15 = a11;
  v12 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *, _QWORD, unsigned __int8 *))(*(_QWORD *)a1 + 24LL))(
          a1,
          a8,
          a9,
          a10);
  if ( v12 < 0 )
  {
    v13 = 96;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180013054  mov     [rsp+arg_0], rbx
0x180013059  mov     [rsp+arg_8], rsi
0x18001305e  push    rdi
0x18001305f  sub     rsp, 50h
0x180013063  mov     rax, [rcx]
0x180013066  mov     rsi, r9
0x180013069  mov     rdi, rcx
0x18001306c  mov     rax, [rax+8]
0x180013070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013075  mov     ebx, eax
0x180013077  test    eax, eax
0x180013079  jns     short loc_180013098
0x18001307b  mov     edx, 56h ; 'V'; void *
0x180013080  mov     rcx, [rsp+58h]; this
0x180013085  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001308c  mov     r9d, ebx; char *
0x18001308f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013094  mov     eax, ebx
0x180013096  jmp     short loc_180013101
0x180013098  mov     ecx, [rsp+58h+arg_20]
0x18001309f  mov     rax, [rdi]
0x1800130a2  mov     r9, [rsp+58h+arg_48]
0x1800130aa  mov     r8d, [rsp+58h+arg_40]
0x1800130b2  mov     rdx, [rsp+58h+arg_38]
0x1800130ba  mov     rax, [rax+18h]
0x1800130be  mov     [rsp+58h+var_18], ecx
0x1800130c2  mov     ecx, [rsp+58h+arg_30]
0x1800130c9  mov     [rsp+58h+var_20], rsi
0x1800130ce  mov     [rsp+58h+var_28], ecx
0x1800130d2  mov     rcx, [rsp+58h+arg_28]
0x1800130da  mov     [rsp+58h+var_30], rcx
0x1800130df  mov     ecx, [rsp+58h+arg_50]
0x1800130e6  mov     [rsp+58h+var_38], ecx
0x1800130ea  mov     rcx, rdi
0x1800130ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130f2  mov     ebx, eax
0x1800130f4  test    eax, eax
0x1800130f6  jns     short loc_1800130FF
0x1800130f8  mov     edx, 60h ; '`'
0x1800130fd  jmp     short loc_180013080
0x1800130ff  xor     eax, eax
0x180013101  mov     rbx, [rsp+58h+arg_0]
0x180013106  mov     rsi, [rsp+58h+arg_8]
0x18001310b  add     rsp, 50h
0x18001310f  pop     rdi
0x180013110  retn
```
