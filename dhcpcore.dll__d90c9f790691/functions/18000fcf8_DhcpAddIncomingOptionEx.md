# DhcpAddIncomingOptionEx

- ea: `0x18000fcf8`
- end: `0x18000fff5`
- name: `DhcpAddIncomingOptionEx`
- size: `765`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, __int64, unsigned int, int, void *Src, int, __int64, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000fc88`
- `0x1800355dc`

## callees

- `0x18000d530`
- `0x18000ee64`
- `0x18000fcf8`
- `0x18000fffc`
- `0x18001b124`
- `0x18001b2bc`
- `0x180040eb4`
- `0x180041224`
- `0x18004d1a0`
- `0x18004d4f8`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fe78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fec8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fe78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fec8`

## pseudocode

```c
__int64 __fastcall DhcpAddIncomingOptionEx(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        void *Src,
        int a9,
        __int64 a10,
        int a11,
        int a12)
{
  unsigned int v15; // esi
  unsigned int v16; // eax
  __int64 v18; // rbx
  __int64 Option; // rbp
  __int64 v20; // rdx
  __int64 v21; // rcx
  ULONGLONG v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  unsigned int v26; // ebp
  const char *v27; // rcx
  size_t Size; // [rsp+38h] [rbp-50h]
  __int64 v29; // [rsp+90h] [rbp+8h]
  int v30; // [rsp+98h] [rbp+10h]

  v30 = a2;
  v29 = a1;
  if ( (BYTE2(xmmword_1800616A0) & 0x20) != 0 )
  {
    WPP_SF_d(1045, 28, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids, a3);
    a1 = v29;
  }
  v15 = a6;
  if ( !a4 && a3 == 43 )
  {
    v16 = DhcpAddIncomingVendorOption(a1, a2, a5, a6, a7, (__int64)Src, a9, a10, a11);
    a1 = 0;
    if ( v16 != 87 )
      a1 = v16;
    if ( (_DWORD)a1 )
      return (unsigned int)a1;
  }
  if ( a6 )
  {
    v18 = DhcpAddClass(a1, a5, a6);
    if ( !v18 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 29, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids, 8);
      return 8;
    }
  }
  else
  {
    v18 = 0;
    v15 = 0;
  }
  Option = DhcpFindOption(a2, a3, a4, v18, v15, a7);
  if ( !Option )
    goto LABEL_36;
  if ( g_fVelocityDhcpv4InformNegativeCacheFix )
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_22;
    v20 = 30;
    v21 = 1028;
  }
  else
  {
    if ( (BYTE2(xmmword_1800616A0) & 0x20) == 0 )
      goto LABEL_22;
    v20 = 31;
    v21 = 1045;
  }
  WPP_SF_d(v21, v20, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids, a3);
LABEL_22:
  if ( !a12 )
  {
    v22 = GetTickCount64() / 0x3E8;
    if ( *(_QWORD *)(Option + 40) > v22 )
    {
      if ( v18 )
        DhcpDelClass(v22, v18, v15);
      return 0;
    }
  }
  v23 = a3 - 121;
  if ( (v23 & 0xFFFFFF7F) == 0 && (!a9 || !Src) && *(_QWORD *)(Option + 40) > GetTickCount64() / 0x3E8 )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_d(1028, 32, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids, a3);
    return 0;
  }
  v24 = *(unsigned int *)(Option + 32);
  if ( (_DWORD)v24 )
    DhcpDelClass(v23, *(_QWORD *)(Option + 24), v24);
  DhcpDelOption(Option);
LABEL_36:
  LODWORD(Size) = a9;
  v26 = DhcpAddOption(v30, a3, a4, v18, v15, a7, Src, Size, a10);
  if ( v26 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
    {
      v27 = "Vendor";
      if ( !a4 )
        v27 = "NotVendor";
      WPP_SF_lsD((_DWORD)v27, 33, (unsigned int)WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids, a3, (__int64)v27, v26);
    }
    if ( v18 )
      DhcpDelClass(v25, v18, v15);
  }
  else if ( !a11 )
  {
    DhcpMarkParamChangeRequests(v29, a3, a4, v18);
  }
  return v26;
}

```

## disassembly

```asm
0x18000fcf8  mov     [rsp+arg_10], rbx
0x18000fcfd  mov     qword ptr [rsp+arg_8], rdx
0x18000fd02  mov     [rsp+arg_0], rcx
0x18000fd07  push    rbp
0x18000fd08  push    rsi
0x18000fd09  push    rdi
0x18000fd0a  push    r12
0x18000fd0c  push    r13
0x18000fd0e  push    r14
0x18000fd10  push    r15
0x18000fd12  sub     rsp, 50h
0x18000fd16  mov     r14d, r9d
0x18000fd19  mov     edi, r8d
0x18000fd1c  mov     rbp, rdx
0x18000fd1f  test    byte ptr cs:xmmword_1800616A0+2, 20h
0x18000fd26  jz      short loc_18000FD49
0x18000fd28  mov     r9d, r8d
0x18000fd2b  mov     edx, 1Ch
0x18000fd30  lea     r8, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids
0x18000fd37  mov     ecx, 415h
0x18000fd3c  call    WPP_SF_d
0x18000fd41  mov     rcx, [rsp+88h+arg_0]
0x18000fd49  mov     r15d, dword ptr [rsp+88h+arg_40]
0x18000fd51  mov     r12, [rsp+88h+arg_38]
0x18000fd59  mov     r13d, [rsp+88h+arg_30]
0x18000fd61  mov     esi, [rsp+88h+arg_28]
0x18000fd68  test    r14d, r14d
0x18000fd6b  jnz     short loc_18000FDBF
0x18000fd6d  cmp     edi, 2Bh ; '+'
0x18000fd70  jnz     short loc_18000FDBF
0x18000fd72  mov     eax, [rsp+88h+arg_50]
0x18000fd79  mov     r9d, esi
0x18000fd7c  mov     r8, [rsp+88h+arg_20]
0x18000fd84  mov     rdx, rbp
0x18000fd87  mov     dword ptr [rsp+88h+var_48], eax
0x18000fd8b  mov     rax, [rsp+88h+arg_48]
0x18000fd93  mov     [rsp+88h+Size], rax
0x18000fd98  mov     dword ptr [rsp+88h+Src], r15d
0x18000fd9d  mov     qword ptr [rsp+88h+var_60], r12
0x18000fda2  mov     [rsp+88h+var_68], r13d
0x18000fda7  call    DhcpAddIncomingVendorOption
0x18000fdac  xor     ecx, ecx
0x18000fdae  cmp     eax, 57h ; 'W'
0x18000fdb1  cmovnz  ecx, eax
0x18000fdb4  test    ecx, ecx
0x18000fdb6  jz      short loc_18000FDBF
0x18000fdb8  mov     eax, ecx
0x18000fdba  jmp     loc_18000FFDD
0x18000fdbf  test    esi, esi
0x18000fdc1  jz      short loc_18000FE05
0x18000fdc3  mov     rdx, [rsp+88h+arg_20]
0x18000fdcb  mov     r8d, esi
0x18000fdce  call    DhcpAddClass
0x18000fdd3  mov     rbx, rax
0x18000fdd6  test    rax, rax
0x18000fdd9  jnz     short loc_18000FE09
0x18000fddb  test    byte ptr cs:xmmword_1800616A0, 2
0x18000fde2  lea     ebx, [rax+8]
0x18000fde5  jz      short loc_18000FDFE
0x18000fde7  lea     edx, [rax+1Dh]
0x18000fdea  mov     ecx, 401h
0x18000fdef  mov     r9d, ebx
0x18000fdf2  lea     r8, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids
0x18000fdf9  call    WPP_SF_D
0x18000fdfe  mov     eax, ebx
0x18000fe00  jmp     loc_18000FFDD
0x18000fe05  xor     ebx, ebx
0x18000fe07  xor     esi, esi
0x18000fe09  mov     [rsp+88h+var_60], r13d
0x18000fe0e  mov     r9, rbx
0x18000fe11  mov     r8d, r14d
0x18000fe14  mov     [rsp+88h+var_68], esi
0x18000fe18  mov     edx, edi
0x18000fe1a  mov     rcx, rbp
0x18000fe1d  call    DhcpFindOption
0x18000fe22  mov     rbp, rax
0x18000fe25  test    rax, rax
0x18000fe28  jz      loc_18000FF34
0x18000fe2e  cmp     cs:g_fVelocityDhcpv4InformNegativeCacheFix, 0
0x18000fe35  jz      short loc_18000FE4C
0x18000fe37  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000fe3e  jz      short loc_18000FE6E
0x18000fe40  mov     edx, 1Eh
0x18000fe45  mov     ecx, 404h
0x18000fe4a  jmp     short loc_18000FE5F
0x18000fe4c  test    byte ptr cs:xmmword_1800616A0+2, 20h
0x18000fe53  jz      short loc_18000FE6E
0x18000fe55  mov     edx, 1Fh
0x18000fe5a  mov     ecx, 415h
0x18000fe5f  mov     r9d, edi
0x18000fe62  lea     r8, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids
0x18000fe69  call    WPP_SF_d
0x18000fe6e  cmp     [rsp+88h+arg_58], 0
0x18000fe76  jnz     short loc_18000FEB3
0x18000fe78  call    cs:__imp_GetTickCount64
0x18000fe7e  mov     rcx, rax
0x18000fe81  mov     rax, 624DD2F1A9FBE77h
0x18000fe8b  mul     rcx
0x18000fe8e  sub     rcx, rdx
0x18000fe91  shr     rcx, 1
0x18000fe94  add     rcx, rdx
0x18000fe97  shr     rcx, 9
0x18000fe9b  cmp     [rbp+28h], rcx
0x18000fe9f  jbe     short loc_18000FEB3
0x18000fea1  test    rbx, rbx
0x18000fea4  jz      short loc_18000FF13
0x18000fea6  mov     r8d, esi
0x18000fea9  mov     rdx, rbx
0x18000feac  call    DhcpDelClass
0x18000feb1  jmp     short loc_18000FF13
0x18000feb3  lea     ecx, [rdi-79h]
0x18000feb6  test    ecx, 0FFFFFF7Fh
0x18000febc  jnz     short loc_18000FF1A
0x18000febe  test    r15d, r15d
0x18000fec1  jz      short loc_18000FEC8
0x18000fec3  test    r12, r12
0x18000fec6  jnz     short loc_18000FF1A
0x18000fec8  call    cs:__imp_GetTickCount64
0x18000fece  mov     r8, rax
0x18000fed1  mov     rax, 624DD2F1A9FBE77h
0x18000fedb  mul     r8
0x18000fede  sub     r8, rdx
0x18000fee1  shr     r8, 1
0x18000fee4  add     r8, rdx
0x18000fee7  shr     r8, 9
0x18000feeb  cmp     [rbp+28h], r8
0x18000feef  jbe     short loc_18000FF1A
0x18000fef1  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000fef8  jz      short loc_18000FF13
0x18000fefa  mov     edx, 20h ; ' '
0x18000feff  lea     r8, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids
0x18000ff06  mov     ecx, 404h
0x18000ff0b  mov     r9d, edi
0x18000ff0e  call    WPP_SF_d
0x18000ff13  xor     eax, eax
0x18000ff15  jmp     loc_18000FFDD
0x18000ff1a  mov     r8d, [rbp+20h]
0x18000ff1e  test    r8d, r8d
0x18000ff21  jz      short loc_18000FF2C
0x18000ff23  mov     rdx, [rbp+18h]
0x18000ff27  call    DhcpDelClass
0x18000ff2c  mov     rcx, rbp
0x18000ff2f  call    DhcpDelOption
0x18000ff34  mov     rax, [rsp+88h+arg_48]
0x18000ff3c  mov     r9, rbx; int
0x18000ff3f  mov     rcx, qword ptr [rsp+88h+arg_8]; int
0x18000ff47  mov     r8d, r14d; int
0x18000ff4a  mov     [rsp+88h+var_48], rax; __int64
0x18000ff4f  mov     edx, edi; int
0x18000ff51  mov     dword ptr [rsp+88h+Size], r15d; Size
0x18000ff56  mov     [rsp+88h+Src], r12; Src
0x18000ff5b  mov     [rsp+88h+var_60], r13d; int
0x18000ff60  mov     [rsp+88h+var_68], esi; int
0x18000ff64  call    DhcpAddOption
0x18000ff69  mov     ebp, eax
0x18000ff6b  test    eax, eax
0x18000ff6d  jz      short loc_18000FFBC
0x18000ff6f  test    byte ptr cs:xmmword_1800616A0, 2
0x18000ff76  jz      short loc_18000FFAA
0x18000ff78  test    r14d, r14d
0x18000ff7b  mov     [rsp+88h+var_60], ebp
0x18000ff7f  lea     rax, aNotvendor; "NotVendor"
0x18000ff86  mov     edx, 21h ; '!'
0x18000ff8b  lea     rcx, aVendor_1; "Vendor"
0x18000ff92  mov     r9d, edi
0x18000ff95  cmovz   rcx, rax
0x18000ff99  lea     r8, WPP_cfa222ec2bef33ea420512b2ea06d7c2_Traceguids
0x18000ffa0  mov     qword ptr [rsp+88h+var_68], rcx
0x18000ffa5  call    WPP_SF_lsD
0x18000ffaa  test    rbx, rbx
0x18000ffad  jz      short loc_18000FFDB
0x18000ffaf  mov     r8d, esi
0x18000ffb2  mov     rdx, rbx
0x18000ffb5  call    DhcpDelClass
0x18000ffba  jmp     short loc_18000FFDB
0x18000ffbc  cmp     [rsp+88h+arg_50], 0
0x18000ffc4  jnz     short loc_18000FFDB
0x18000ffc6  mov     rcx, [rsp+88h+arg_0]
0x18000ffce  mov     r9, rbx
0x18000ffd1  mov     r8d, r14d
0x18000ffd4  mov     edx, edi
0x18000ffd6  call    DhcpMarkParamChangeRequests
0x18000ffdb  mov     eax, ebp
0x18000ffdd  mov     rbx, [rsp+88h+arg_10]
0x18000ffe5  add     rsp, 50h
0x18000ffe9  pop     r15
0x18000ffeb  pop     r14
0x18000ffed  pop     r13
0x18000ffef  pop     r12
0x18000fff1  pop     rdi
0x18000fff2  pop     rsi
0x18000fff3  pop     rbp
0x18000fff4  retn
```
