# DhcpUpdateIPv4AddressLifetime

- ea: `0x18000ef2c`
- end: `0x18000f32c`
- name: `DhcpUpdateIPv4AddressLifetime`
- size: `1024`
- prototype: `__int64 __fastcall(_QWORD *, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180017e68`

## callees

- `0x18000ef2c`
- `0x18001cef0`
- `0x18001d826`
- `0x180049168`
- `0x180049404`
- `0x18004cf50`
- `0x18004d1a0`
- `0x18004dbc4`

## import_xrefs

- `NSI!NsiGetAllParametersEx` at `0x18000f053`
- `NSI!NsiGetAllParametersEx` at `0x18000f053`
- `NSI!NsiSetAllParametersEx` at `0x18000f1c0`
- `NSI!NsiSetAllParametersEx` at `0x18000f1c0`

## pseudocode

```c
__int64 __fastcall DhcpUpdateIPv4AddressLifetime(_QWORD *a1, int a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rax
  int v5; // r15d
  char v9; // bl
  int v10; // edx
  int v11; // r8d
  unsigned int AllParameters; // eax
  __int64 v13; // r8
  unsigned int v14; // edi
  char v15; // bl
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // edx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v23; // [rsp+28h] [rbp-140h]
  int v24; // [rsp+50h] [rbp-118h]
  int v25; // [rsp+70h] [rbp-F8h] BYREF
  __int64 v26; // [rsp+80h] [rbp-E8h] BYREF
  int v27; // [rsp+88h] [rbp-E0h]
  const NPI_MODULEID *v28; // [rsp+90h] [rbp-D8h]
  int v29; // [rsp+98h] [rbp-D0h]
  __int64 v30; // [rsp+A0h] [rbp-C8h]
  __int64 *v31; // [rsp+A8h] [rbp-C0h]
  int v32; // [rsp+B0h] [rbp-B8h]
  _DWORD *v33; // [rsp+B8h] [rbp-B0h]
  int v34; // [rsp+C0h] [rbp-A8h]
  __int64 v35; // [rsp+C8h] [rbp-A0h]
  int v36; // [rsp+D0h] [rbp-98h]
  __int64 v37; // [rsp+D8h] [rbp-90h]
  int v38; // [rsp+E0h] [rbp-88h]
  __int64 v39; // [rsp+F0h] [rbp-78h] BYREF
  int v40; // [rsp+F8h] [rbp-70h]
  int v41; // [rsp+FCh] [rbp-6Ch]
  _DWORD v42[8]; // [rsp+100h] [rbp-68h] BYREF

  v4 = *a1;
  v5 = (unsigned __int8)a3;
  memset(v42, 0, 28);
  v25 = 0;
  v41 = 0;
  v39 = v4;
  v40 = a2;
  v9 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    v23 = (unsigned __int8)a3;
    WPP_SF_JDdD(a1, 52, a3, v4, a2);
    v9 = xmmword_1800616A0;
  }
  memset_0(&v26, 0, 0x68u);
  if ( (v9 & 0x10) != 0 )
    WPP_SF_qqLqLLLLdd(
      (unsigned int)&NPI_MS_IPV4_MODULEID,
      v10,
      v11,
      0,
      (char)&NPI_MS_IPV4_MODULEID,
      10,
      (char)&v39,
      16,
      28,
      0,
      0);
  v28 = &NPI_MS_IPV4_MODULEID;
  v31 = &v39;
  v27 = 0;
  v33 = v42;
  v29 = 10;
  v32 = 16;
  v34 = 28;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v30 = 1;
  AllParameters = NsiGetAllParametersEx(&v26);
  v14 = AllParameters;
  v15 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_D(1028, 11, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids, AllParameters);
    v15 = xmmword_1800616A0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_D(1028, 53, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v14);
      v15 = xmmword_1800616A0;
    }
  }
  if ( !v14 )
  {
    v16 = *a1;
    v17 = 0xFFFFFFFFLL;
    v39 = *a1;
    v40 = a2;
    if ( a4 != -1 )
      v17 = a4;
    LOBYTE(v42[4]) = v5;
    v42[1] = v17;
    v42[0] = v17;
    if ( (v15 & 0x10) != 0 )
    {
      v23 = v5;
      WPP_SF_JDdD(v17, 54, v13, v16, a2);
      v15 = xmmword_1800616A0;
    }
    memset_0(&v26, 0, 0x48u);
    if ( (v15 & 0x10) != 0 )
      WPP_SF_qqqLqLLdd(v19, v18, v20, v21, (char)&v25, v23, 10, (char)&v39, 16, 28, v24, 2);
    v27 = v25;
    v28 = &NPI_MS_IPV4_MODULEID;
    v31 = &v39;
    v33 = v42;
    v26 = 0;
    v29 = 10;
    v32 = 16;
    v34 = 28;
    v30 = 0x200000001LL;
    v14 = NsiSetAllParametersEx(&v26);
    if ( !v25 )
      v25 = v27;
    v15 = xmmword_1800616A0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_D(1028, 13, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids, v14);
      v15 = xmmword_1800616A0;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        WPP_SF_D(1028, 55, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v14);
        v15 = xmmword_1800616A0;
      }
    }
    if ( v14 == 5 )
    {
      if ( (v15 & 0x10) != 0 )
        WPP_SF_D(1028, 56, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, 5);
      return 0;
    }
    if ( !v14 )
      return 0;
  }
  if ( (v15 & 2) != 0 )
    WPP_SF_dJ(1025, 57, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v14, *a1);
  return v14;
}

```

## disassembly

```asm
0x18000ef2c  mov     r11, rsp
0x18000ef2f  push    rbx
0x18000ef30  push    rsi
0x18000ef31  push    rdi
0x18000ef32  push    r12
0x18000ef34  push    r13
0x18000ef36  push    r14
0x18000ef38  push    r15
0x18000ef3a  sub     rsp, 130h
0x18000ef41  mov     rax, cs:__security_cookie
0x18000ef48  xor     rax, rsp
0x18000ef4b  mov     [rsp+168h+var_48], rax
0x18000ef53  mov     rax, [rcx]
0x18000ef56  xorps   xmm0, xmm0
0x18000ef59  xor     edi, edi
0x18000ef5b  movzx   r15d, r8b
0x18000ef5f  movups  xmmword ptr [r11-68h], xmm0
0x18000ef64  mov     r12d, r9d
0x18000ef67  mov     r14d, edx
0x18000ef6a  movups  xmmword ptr [r11-5Ch], xmm0
0x18000ef6f  mov     rsi, rcx
0x18000ef72  mov     [rsp+168h+var_F8], edi
0x18000ef76  mov     [r11-6Ch], edi
0x18000ef7a  mov     [r11-78h], rax
0x18000ef7e  mov     [r11-70h], edx
0x18000ef82  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000ef88  lea     r13d, [rdi+10h]
0x18000ef8c  test    r13b, bl
0x18000ef8f  jz      short loc_18000EFB1
0x18000ef91  mov     dword ptr [rsp+168h+var_138], r9d
0x18000ef96  lea     edx, [rdi+34h]
0x18000ef99  mov     [rsp+168h+var_140], r15d
0x18000ef9e  mov     r9, rax
0x18000efa1  mov     dword ptr [rsp+168h+var_148], r14d
0x18000efa6  call    WPP_SF_JDdD
0x18000efab  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000efb1  xor     edx, edx; Val
0x18000efb3  lea     rcx, [rsp+168h+var_E8]; void *
0x18000efbb  lea     r8d, [rdx+68h]; Size
0x18000efbf  call    memset_0
0x18000efc4  lea     rcx, NPI_MS_IPV4_MODULEID
0x18000efcb  test    r13b, bl
0x18000efce  jnz     loc_18000F26D
0x18000efd4  lea     rax, [rsp+168h+var_78]
0x18000efdc  mov     [rsp+168h+var_D8], rcx
0x18000efe4  mov     [rsp+168h+var_C0], rax
0x18000efec  lea     rcx, [rsp+168h+var_E8]
0x18000eff4  lea     rax, [rsp+168h+var_68]
0x18000effc  mov     [rsp+168h+var_E0], edi
0x18000f003  mov     [rsp+168h+var_B0], rax
0x18000f00b  mov     [rsp+168h+var_D0], 0Ah
0x18000f016  mov     [rsp+168h+var_B8], r13d
0x18000f01e  mov     [rsp+168h+var_A8], 1Ch
0x18000f029  mov     [rsp+168h+var_A0], rdi
0x18000f031  mov     [rsp+168h+var_98], edi
0x18000f038  mov     [rsp+168h+var_90], rdi
0x18000f040  mov     [rsp+168h+var_88], edi
0x18000f047  mov     [rsp+168h+var_C8], 1
0x18000f053  call    cs:__imp_NsiGetAllParametersEx
0x18000f059  mov     edi, eax
0x18000f05b  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000f061  test    r13b, bl
0x18000f064  jz      short loc_18000F0A9
0x18000f066  mov     edx, 0Bh
0x18000f06b  lea     r8, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids
0x18000f072  mov     ecx, 404h
0x18000f077  mov     r9d, eax
0x18000f07a  call    WPP_SF_D
0x18000f07f  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000f085  test    r13b, bl
0x18000f088  jz      short loc_18000F0A9
0x18000f08a  mov     edx, 35h ; '5'
0x18000f08f  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18000f096  mov     ecx, 404h
0x18000f09b  mov     r9d, edi
0x18000f09e  call    WPP_SF_D
0x18000f0a3  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000f0a9  test    edi, edi
0x18000f0ab  jnz     loc_18000F260
0x18000f0b1  mov     rax, [rsi]
0x18000f0b4  or      ecx, 0FFFFFFFFh
0x18000f0b7  cmp     r12d, ecx
0x18000f0ba  mov     [rsp+168h+var_78], rax
0x18000f0c2  mov     [rsp+168h+var_70], r14d
0x18000f0ca  cmovnz  ecx, r12d
0x18000f0ce  mov     [rsp+168h+var_58], r15b
0x18000f0d6  mov     [rsp+168h+var_64], ecx
0x18000f0dd  mov     [rsp+168h+var_68], ecx
0x18000f0e4  test    r13b, bl
0x18000f0e7  jnz     loc_18000F2BC
0x18000f0ed  xor     edx, edx; Val
0x18000f0ef  lea     rcx, [rsp+168h+var_E8]; void *
0x18000f0f7  lea     r8d, [rdx+48h]; Size
0x18000f0fb  call    memset_0
0x18000f100  test    r13b, bl
0x18000f103  jz      short loc_18000F13E
0x18000f105  mov     [rsp+168h+var_110], 2
0x18000f10d  lea     rax, [rsp+168h+var_78]
0x18000f115  mov     [rsp+168h+var_120], 1Ch
0x18000f11d  mov     [rsp+168h+var_128], r13d
0x18000f122  mov     [rsp+168h+var_130], rax
0x18000f127  lea     rax, [rsp+168h+var_F8]
0x18000f12c  mov     dword ptr [rsp+168h+var_138], 0Ah
0x18000f134  mov     [rsp+168h+var_148], rax
0x18000f139  call    WPP_SF_qqqLqLLdd
0x18000f13e  mov     eax, [rsp+168h+var_F8]
0x18000f142  lea     rcx, [rsp+168h+var_E8]
0x18000f14a  mov     [rsp+168h+var_E0], eax
0x18000f151  lea     rax, NPI_MS_IPV4_MODULEID
0x18000f158  mov     [rsp+168h+var_D8], rax
0x18000f160  lea     rax, [rsp+168h+var_78]
0x18000f168  mov     [rsp+168h+var_C0], rax
0x18000f170  lea     rax, [rsp+168h+var_68]
0x18000f178  mov     [rsp+168h+var_B0], rax
0x18000f180  mov     [rsp+168h+var_E8], 0
0x18000f18c  mov     [rsp+168h+var_D0], 0Ah
0x18000f197  mov     [rsp+168h+var_B8], r13d
0x18000f19f  mov     [rsp+168h+var_A8], 1Ch
0x18000f1aa  mov     dword ptr [rsp+168h+var_C8], 1
0x18000f1b5  mov     dword ptr [rsp+168h+var_C8+4], 2
0x18000f1c0  call    cs:__imp_NsiSetAllParametersEx
0x18000f1c6  cmp     [rsp+168h+var_F8], 0
0x18000f1cb  mov     edi, eax
0x18000f1cd  jnz     short loc_18000F1DA
0x18000f1cf  mov     eax, [rsp+168h+var_E0]
0x18000f1d6  mov     [rsp+168h+var_F8], eax
0x18000f1da  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000f1e0  test    r13b, bl
0x18000f1e3  jz      short loc_18000F228
0x18000f1e5  mov     edx, 0Dh
0x18000f1ea  lea     r8, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids
0x18000f1f1  mov     ecx, 404h
0x18000f1f6  mov     r9d, edi
0x18000f1f9  call    WPP_SF_D
0x18000f1fe  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000f204  test    r13b, bl
0x18000f207  jz      short loc_18000F228
0x18000f209  mov     edx, 37h ; '7'
0x18000f20e  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18000f215  mov     ecx, 404h
0x18000f21a  mov     r9d, edi
0x18000f21d  call    WPP_SF_D
0x18000f222  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000f228  mov     r9d, 5
0x18000f22e  cmp     edi, r9d
0x18000f231  jz      loc_18000F2E2
0x18000f237  test    edi, edi
0x18000f239  jnz     short loc_18000F260
0x18000f23b  xor     eax, eax
0x18000f23d  mov     rcx, [rsp+168h+var_48]
0x18000f245  xor     rcx, rsp; StackCookie
0x18000f248  call    __security_check_cookie
0x18000f24d  add     rsp, 130h
0x18000f254  pop     r15
0x18000f256  pop     r14
0x18000f258  pop     r13
0x18000f25a  pop     r12
0x18000f25c  pop     rdi
0x18000f25d  pop     rsi
0x18000f25e  pop     rbx
0x18000f25f  retn
0x18000f260  test    bl, 2
0x18000f263  jnz     loc_18000F306
0x18000f269  mov     eax, edi
0x18000f26b  jmp     short loc_18000F23D
0x18000f26d  mov     [rsp+168h+var_108], edi
0x18000f271  lea     rax, [rsp+168h+var_78]
0x18000f279  mov     [rsp+168h+var_110], 1
0x18000f281  xor     r9d, r9d
0x18000f284  mov     [rsp+168h+var_118], edi
0x18000f288  mov     [rsp+168h+var_120], edi
0x18000f28c  mov     [rsp+168h+var_128], 1Ch
0x18000f294  mov     dword ptr [rsp+168h+var_130], r13d
0x18000f299  mov     [rsp+168h+var_138], rax
0x18000f29e  mov     [rsp+168h+var_140], 0Ah
0x18000f2a6  mov     [rsp+168h+var_148], rcx
0x18000f2ab  call    WPP_SF_qqLqLLLLdd
0x18000f2b0  lea     rcx, NPI_MS_IPV4_MODULEID
0x18000f2b7  jmp     loc_18000EFD4
0x18000f2bc  mov     dword ptr [rsp+168h+var_138], ecx
0x18000f2c0  mov     edx, 36h ; '6'
0x18000f2c5  mov     [rsp+168h+var_140], r15d
0x18000f2ca  mov     r9, rax
0x18000f2cd  mov     dword ptr [rsp+168h+var_148], r14d
0x18000f2d2  call    WPP_SF_JDdD
0x18000f2d7  mov     bl, byte ptr cs:xmmword_1800616A0
0x18000f2dd  jmp     loc_18000F0ED
0x18000f2e2  test    r13b, bl
0x18000f2e5  jz      loc_18000F23B
0x18000f2eb  mov     edx, 38h ; '8'
0x18000f2f0  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18000f2f7  mov     ecx, 404h
0x18000f2fc  call    WPP_SF_D
0x18000f301  jmp     loc_18000F23B
0x18000f306  mov     r8, [rsi]
0x18000f309  mov     edx, 39h ; '9'
0x18000f30e  mov     [rsp+168h+var_148], r8
0x18000f313  mov     ecx, 401h
0x18000f318  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18000f31f  mov     r9d, edi
0x18000f322  call    WPP_SF_dJ
0x18000f327  jmp     loc_18000F269
```
