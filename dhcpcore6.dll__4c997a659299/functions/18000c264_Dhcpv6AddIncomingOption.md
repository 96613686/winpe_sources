# Dhcpv6AddIncomingOption

- ea: `0x18000c264`
- end: `0x18000c416`
- name: `Dhcpv6AddIncomingOption`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, __int64, unsigned int, _OWORD *, void *Src, int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003cc0`

## callees

- `0x18000c264`
- `0x18000c41c`
- `0x18000c508`
- `0x180017bc4`
- `0x180018fa4`
- `0x18002836c`
- `0x180033900`
- `0x180033de4`
- `0x180034948`

## pseudocode

```c
__int64 __fastcall Dhcpv6AddIncomingOption(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        _OWORD *a7,
        void *Src,
        int a9,
        __int64 a10)
{
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 Option; // rsi
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned int v18; // esi
  int v19; // r8d
  const char *v21; // rcx
  size_t Size; // [rsp+38h] [rbp-60h]
  __int64 v23[2]; // [rsp+50h] [rbp-48h] BYREF

  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 35, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, a3);
  if ( !a6 )
  {
    v13 = 0;
LABEL_5:
    Option = Dhcpv6FindOption(a2, a3, a4, v13, a6);
    if ( Option )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_d(1025, 37, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, a3);
      v16 = *(unsigned int *)(Option + 32);
      if ( (_DWORD)v16 )
        Dhcpv6DelClass(v14, *(_QWORD *)(Option + 24), v16);
      Dhcpv6DelOption(Option);
    }
    LODWORD(Size) = a9;
    *(_OWORD *)v23 = *a7;
    v18 = Dhcpv6AddOptionToList(a2, a3, a4, v13, a6, (__int64)v23, Src, Size, a10);
    if ( v18 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
      {
        v21 = "Vendor";
        if ( !a4 )
          v21 = "NotVendor";
        WPP_SF_lsD((_DWORD)v21, 38, v19, a3, (__int64)v21, v18);
      }
      if ( v13 )
        Dhcpv6DelClass(v17, v13, a6);
    }
    return v18;
  }
  v13 = Dhcpv6AddClass(a1, a5, a6);
  if ( v13 )
    goto LABEL_5;
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_(1025, 36, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids);
  return 8;
}

```

## disassembly

```asm
0x18000c264  push    rbx
0x18000c266  push    rbp
0x18000c267  push    rsi
0x18000c268  push    rdi
0x18000c269  push    r14
0x18000c26b  push    r15
0x18000c26d  sub     rsp, 68h
0x18000c271  mov     r14d, r9d
0x18000c274  mov     ebp, r8d
0x18000c277  mov     r15, rdx
0x18000c27a  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000c281  jz      short loc_18000C29C
0x18000c283  mov     r9d, r8d
0x18000c286  mov     edx, 23h ; '#'
0x18000c28b  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x18000c292  mov     ecx, 404h
0x18000c297  call    WPP_SF_d
0x18000c29c  mov     ebx, [rsp+98h+arg_28]
0x18000c2a3  test    ebx, ebx
0x18000c2a5  jnz     loc_18000C377
0x18000c2ab  xor     edi, edi
0x18000c2ad  mov     r9, rdi
0x18000c2b0  mov     [rsp+98h+var_78], ebx
0x18000c2b4  mov     r8d, r14d
0x18000c2b7  mov     edx, ebp
0x18000c2b9  mov     rcx, r15
0x18000c2bc  call    Dhcpv6FindOption
0x18000c2c1  mov     rsi, rax
0x18000c2c4  test    rax, rax
0x18000c2c7  jz      short loc_18000C2EB
0x18000c2c9  test    byte ptr cs:xmmword_1800423E0, 2
0x18000c2d0  jnz     loc_18000C359
0x18000c2d6  mov     r8d, [rsi+20h]
0x18000c2da  test    r8d, r8d
0x18000c2dd  jnz     loc_18000C3BB
0x18000c2e3  mov     rcx, rsi
0x18000c2e6  call    Dhcpv6DelOption
0x18000c2eb  mov     rax, [rsp+98h+arg_30]
0x18000c2f3  mov     r9, rdi; int
0x18000c2f6  mov     r8d, r14d; int
0x18000c2f9  mov     edx, ebp; int
0x18000c2fb  mov     rcx, r15; int
0x18000c2fe  movaps  xmm0, xmmword ptr [rax]
0x18000c301  mov     rax, [rsp+98h+arg_48]
0x18000c309  mov     [rsp+98h+var_58], rax; __int64
0x18000c30e  mov     eax, dword ptr [rsp+98h+arg_40]
0x18000c315  mov     dword ptr [rsp+98h+Size], eax; Size
0x18000c319  mov     rax, [rsp+98h+arg_38]
0x18000c321  mov     [rsp+98h+Src], rax; Src
0x18000c326  lea     rax, [rsp+98h+var_48]
0x18000c32b  mov     [rsp+98h+var_70], rax; __int64
0x18000c330  mov     [rsp+98h+var_78], ebx; int
0x18000c334  movdqa  xmmword ptr [rsp+98h+var_48], xmm0
0x18000c33a  call    Dhcpv6AddOptionToList
0x18000c33f  mov     esi, eax
0x18000c341  test    eax, eax
0x18000c343  jnz     loc_18000C3C9
0x18000c349  mov     eax, esi
0x18000c34b  add     rsp, 68h
0x18000c34f  pop     r15
0x18000c351  pop     r14
0x18000c353  pop     rdi
0x18000c354  pop     rsi
0x18000c355  pop     rbp
0x18000c356  pop     rbx
0x18000c357  retn
0x18000c359  mov     edx, 25h ; '%'
0x18000c35e  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x18000c365  mov     ecx, 401h
0x18000c36a  mov     r9d, ebp
0x18000c36d  call    WPP_SF_d
0x18000c372  jmp     loc_18000C2D6
0x18000c377  mov     rdx, [rsp+98h+arg_20]
0x18000c37f  mov     r8d, ebx
0x18000c382  call    Dhcpv6AddClass
0x18000c387  mov     rdi, rax
0x18000c38a  test    rax, rax
0x18000c38d  jnz     loc_18000C2AD
0x18000c393  test    byte ptr cs:xmmword_1800423E0, 2
0x18000c39a  jnz     short loc_18000C3A3
0x18000c39c  mov     eax, 8
0x18000c3a1  jmp     short loc_18000C34B
0x18000c3a3  mov     edx, 24h ; '$'
0x18000c3a8  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x18000c3af  mov     ecx, 401h
0x18000c3b4  call    WPP_SF_
0x18000c3b9  jmp     short loc_18000C39C
0x18000c3bb  mov     rdx, [rsi+18h]
0x18000c3bf  call    Dhcpv6DelClass
0x18000c3c4  jmp     loc_18000C2E3
0x18000c3c9  test    byte ptr cs:xmmword_1800423E0, 2
0x18000c3d0  jz      short loc_18000C3FD
0x18000c3d2  test    r14d, r14d
0x18000c3d5  mov     dword ptr [rsp+98h+var_70], esi
0x18000c3d9  lea     rax, aNotvendor; "NotVendor"
0x18000c3e0  mov     edx, 26h ; '&'
0x18000c3e5  lea     rcx, aVendor_1; "Vendor"
0x18000c3ec  mov     r9d, ebp
0x18000c3ef  cmovz   rcx, rax
0x18000c3f3  mov     qword ptr [rsp+98h+var_78], rcx
0x18000c3f8  call    WPP_SF_lsD
0x18000c3fd  test    rdi, rdi
0x18000c400  jz      loc_18000C349
0x18000c406  mov     r8d, ebx
0x18000c409  mov     rdx, rdi
0x18000c40c  call    Dhcpv6DelClass
0x18000c411  jmp     loc_18000C349
```
