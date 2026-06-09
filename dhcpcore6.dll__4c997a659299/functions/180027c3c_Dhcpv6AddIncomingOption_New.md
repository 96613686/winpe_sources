# Dhcpv6AddIncomingOption_New

- ea: `0x180027c3c`
- end: `0x180027e19`
- name: `Dhcpv6AddIncomingOption_New`
- size: `477`
- prototype: `__int64 __fastcall(__int64 *, int, int, __int64, unsigned int, _OWORD *, __int64, size_t, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003cc0`

## callees

- `0x180017bc4`
- `0x180018864`
- `0x180018fa4`
- `0x180027c3c`
- `0x18002836c`
- `0x180028410`
- `0x180032460`
- `0x1800338c0`

## pseudocode

```c
__int64 __fastcall Dhcpv6AddIncomingOption_New(
        __int64 *a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        _OWORD *a6,
        __int64 a7,
        size_t a8,
        __int64 a9,
        int a10)
{
  __int64 *v10; // r10
  unsigned int v12; // ebx
  _BOOL8 v13; // rcx
  __int64 v14; // rdi
  unsigned int v15; // ebp
  int v16; // esi
  _QWORD *v17; // rdx
  __int64 v18; // rcx
  int v19; // r8d
  size_t Size; // [rsp+38h] [rbp-70h]
  __int64 v22; // [rsp+50h] [rbp-58h] BYREF
  __int64 *v23; // [rsp+58h] [rbp-50h]
  __int64 v24[2]; // [rsp+60h] [rbp-48h] BYREF

  v10 = a1;
  v22 = (__int64)&v22;
  v23 = &v22;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_dlqdqdl((unsigned int)&v22, a2, a3, a2, a3, a4, a5, a7, a8, a10, v22, v23);
    v10 = a1;
  }
  if ( !v10 || (v13 = a4 == 0, v13 != (a5 == 0)) || (_DWORD)a8 && !a7 )
  {
    v12 = 87;
    goto LABEL_20;
  }
  v14 = 0;
  v15 = 0;
  if ( a4 )
  {
    v14 = Dhcpv6AddClass(v13, a4, a5);
    if ( !v14 )
    {
      v12 = 8;
      goto LABEL_20;
    }
    LODWORD(v10) = (_DWORD)a1;
    v15 = a5;
  }
  if ( !a10 )
  {
    v16 = a3;
    goto LABEL_17;
  }
  v16 = a3;
  v12 = Dhcpv6FilterMatchingOptions((_DWORD)v10, a2, a3, a4, a5, (__int64)&v22);
  if ( !v12 )
  {
    v12 = Dhcpv6DestroyOptionsList(&v22, v17, v19);
    if ( !v12 )
    {
LABEL_17:
      LODWORD(Size) = a8;
      *(_OWORD *)v24 = *a6;
      v12 = Dhcpv6AddOptionToList(a1, a2, v16, v14, v15, v24, (void *)(a7 & -(__int64)((_DWORD)a8 != 0)), Size, a9);
      if ( !v12 )
        goto LABEL_20;
    }
  }
  if ( v14 )
    Dhcpv6DelClass(v18, v14, v15);
LABEL_20:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 40, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180027c3c  mov     rax, rsp
0x180027c3f  mov     [rax+20h], rbx
0x180027c43  mov     [rax+18h], r8d
0x180027c47  mov     [rax+10h], edx
0x180027c4a  mov     [rax+8], rcx
0x180027c4e  push    rbp
0x180027c4f  push    rsi
0x180027c50  push    rdi
0x180027c51  push    r12
0x180027c53  push    r13
0x180027c55  push    r14
0x180027c57  push    r15
0x180027c59  sub     rsp, 70h
0x180027c5d  mov     r10, rcx
0x180027c60  mov     rbx, r9
0x180027c63  lea     rcx, [rax-58h]
0x180027c67  mov     [rax-58h], rcx
0x180027c6b  lea     rcx, [rax-58h]
0x180027c6f  mov     [rax-50h], rcx
0x180027c73  test    byte ptr cs:xmmword_1800423E0, 10h
0x180027c7a  mov     r13d, [rsp+0A8h+arg_48]
0x180027c82  mov     r14d, dword ptr [rsp+0A8h+arg_38]
0x180027c8a  mov     r15, [rsp+0A8h+arg_30]
0x180027c92  mov     esi, [rsp+0A8h+arg_20]
0x180027c99  jz      short loc_180027CC3
0x180027c9b  mov     [rax-60h], r13d
0x180027c9f  mov     r9d, edx
0x180027ca2  mov     [rax-68h], r14d
0x180027ca6  mov     [rax-70h], r15
0x180027caa  mov     [rax-78h], esi
0x180027cad  mov     [rax-80h], rbx
0x180027cb1  mov     [rsp+0A8h+var_88], r8d
0x180027cb6  call    WPP_SF_dlqdqdl
0x180027cbb  mov     r10, qword ptr [rsp+0A8h+arg_0]
0x180027cc3  test    r10, r10
0x180027cc6  jnz     short loc_180027CD2
0x180027cc8  mov     ebx, 57h ; 'W'
0x180027ccd  jmp     loc_180027DDC
0x180027cd2  xor     ecx, ecx
0x180027cd4  test    rbx, rbx
0x180027cd7  setz    cl
0x180027cda  xor     eax, eax
0x180027cdc  test    esi, esi
0x180027cde  setz    al
0x180027ce1  cmp     ecx, eax
0x180027ce3  jnz     short loc_180027CC8
0x180027ce5  test    r14d, r14d
0x180027ce8  jz      short loc_180027CEF
0x180027cea  test    r15, r15
0x180027ced  jz      short loc_180027CC8
0x180027cef  xor     edi, edi
0x180027cf1  xor     ebp, ebp
0x180027cf3  test    rbx, rbx
0x180027cf6  jz      short loc_180027D1D
0x180027cf8  mov     r8d, esi
0x180027cfb  mov     rdx, rbx
0x180027cfe  call    Dhcpv6AddClass
0x180027d03  mov     rdi, rax
0x180027d06  test    rax, rax
0x180027d09  jnz     short loc_180027D13
0x180027d0b  lea     ebx, [rbp+8]
0x180027d0e  jmp     loc_180027DDC
0x180027d13  mov     r10, qword ptr [rsp+0A8h+arg_0]
0x180027d1b  mov     ebp, esi
0x180027d1d  mov     eax, r14d
0x180027d20  neg     eax
0x180027d22  sbb     r12, r12
0x180027d25  and     r12, r15
0x180027d28  mov     r15d, [rsp+0A8h+arg_8]
0x180027d30  test    r13d, r13d
0x180027d33  jz      short loc_180027D73
0x180027d35  lea     rax, [rsp+0A8h+var_58]
0x180027d3a  mov     r9, rbx
0x180027d3d  mov     [rsp+0A8h+var_80], rax
0x180027d42  mov     edx, r15d
0x180027d45  mov     [rsp+0A8h+var_88], esi
0x180027d49  mov     rcx, r10
0x180027d4c  mov     esi, [rsp+0A8h+arg_10]
0x180027d53  mov     r8d, esi
0x180027d56  call    Dhcpv6FilterMatchingOptions
0x180027d5b  mov     ebx, eax
0x180027d5d  test    eax, eax
0x180027d5f  jnz     short loc_180027DCC
0x180027d61  lea     rcx, [rsp+0A8h+var_58]
0x180027d66  call    Dhcpv6DestroyOptionsList
0x180027d6b  mov     ebx, eax
0x180027d6d  test    eax, eax
0x180027d6f  jnz     short loc_180027DCC
0x180027d71  jmp     short loc_180027D7A
0x180027d73  mov     esi, [rsp+0A8h+arg_10]
0x180027d7a  mov     rax, [rsp+0A8h+arg_28]
0x180027d82  mov     r9, rdi; int
0x180027d85  mov     rcx, qword ptr [rsp+0A8h+arg_0]; int
0x180027d8d  mov     r8d, esi; int
0x180027d90  mov     edx, r15d; int
0x180027d93  movaps  xmm0, xmmword ptr [rax]
0x180027d96  mov     rax, [rsp+0A8h+arg_40]
0x180027d9e  mov     [rsp+0A8h+var_68], rax; __int64
0x180027da3  lea     rax, [rsp+0A8h+var_48]
0x180027da8  mov     dword ptr [rsp+0A8h+Size], r14d; Size
0x180027dad  mov     [rsp+0A8h+Src], r12; Src
0x180027db2  mov     [rsp+0A8h+var_80], rax; __int64
0x180027db7  mov     [rsp+0A8h+var_88], ebp; int
0x180027dbb  movdqa  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180027dc1  call    Dhcpv6AddOptionToList
0x180027dc6  mov     ebx, eax
0x180027dc8  test    eax, eax
0x180027dca  jz      short loc_180027DDC
0x180027dcc  test    rdi, rdi
0x180027dcf  jz      short loc_180027DDC
0x180027dd1  mov     r8d, ebp
0x180027dd4  mov     rdx, rdi
0x180027dd7  call    Dhcpv6DelClass
0x180027ddc  test    byte ptr cs:xmmword_1800423E0, 10h
0x180027de3  jz      short loc_180027DFE
0x180027de5  mov     edx, 28h ; '('
0x180027dea  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x180027df1  mov     ecx, 404h
0x180027df6  mov     r9d, ebx
0x180027df9  call    WPP_SF_D
0x180027dfe  mov     eax, ebx
0x180027e00  mov     rbx, [rsp+0A8h+arg_18]
0x180027e08  add     rsp, 70h
0x180027e0c  pop     r15
0x180027e0e  pop     r14
0x180027e10  pop     r13
0x180027e12  pop     r12
0x180027e14  pop     rdi
0x180027e15  pop     rsi
0x180027e16  pop     rbp
0x180027e17  retn
```
