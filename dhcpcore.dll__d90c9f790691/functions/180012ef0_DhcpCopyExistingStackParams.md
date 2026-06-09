# DhcpCopyExistingStackParams

- ea: `0x180012ef0`
- end: `0x18001324e`
- name: `DhcpCopyExistingStackParams`
- size: `862`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180021128`
- `0x180024488`
- `0x18002fedc`

## callees

- `0x180006440`
- `0x18000d530`
- `0x180012ef0`
- `0x18001ada0`
- `0x18001bb80`
- `0x18001d7f6`
- `0x18001d826`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800131d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800131d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001304a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001304a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013210`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013210`

## pseudocode

```c
__int64 __fastcall DhcpCopyExistingStackParams(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rcx
  __int64 i; // rsi
  __int64 Option; // rax
  char *v7; // r12
  __int64 v8; // rdi
  void *v9; // rax
  _DWORD *v10; // rax
  unsigned int v11; // ebx
  _BYTE *v12; // r9
  __int64 v13; // r8
  __int64 j; // rdx
  __int128 v15; // xmm1
  __int64 v16; // rax
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  unsigned int v27; // ebx
  __int128 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  __int128 v35; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v37[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h]
  _DWORD v39[2]; // [rsp+100h] [rbp+0h]
  char *v40; // [rsp+108h] [rbp+8h]
  __int64 v41; // [rsp+110h] [rbp+10h]
  int v42; // [rsp+118h] [rbp+18h]
  char *v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+128h] [rbp+28h]
  int v45; // [rsp+130h] [rbp+30h]
  char *v46; // [rsp+138h] [rbp+38h]
  __int64 v47; // [rsp+140h] [rbp+40h]
  int v48; // [rsp+148h] [rbp+48h]
  __int128 *v49; // [rsp+150h] [rbp+50h]
  __int64 v50; // [rsp+158h] [rbp+58h]
  int v51; // [rsp+160h] [rbp+60h]
  __int128 *v52; // [rsp+168h] [rbp+68h]
  char *v53; // [rsp+170h] [rbp+70h]
  int v54; // [rsp+178h] [rbp+78h]
  __int128 *v55; // [rsp+180h] [rbp+80h]
  char *v56; // [rsp+188h] [rbp+88h]
  int v57; // [rsp+190h] [rbp+90h]
  __int128 *v58; // [rsp+198h] [rbp+98h]
  char *v59; // [rsp+1A0h] [rbp+A0h]
  int v60; // [rsp+1A8h] [rbp+A8h]
  __int128 *v61; // [rsp+1B0h] [rbp+B0h]
  char *v62; // [rsp+1B8h] [rbp+B8h]
  int v63; // [rsp+1C0h] [rbp+C0h]
  _OWORD *v64; // [rsp+1C8h] [rbp+C8h]
  char *v65; // [rsp+1D0h] [rbp+D0h]

  memset_0(&v29, 0, 0xC8u);
  v39[0] = 1;
  v40 = (char *)&v30 + 4;
  v43 = (char *)&v30 + 8;
  v46 = (char *)&v30 + 12;
  v49 = &v31;
  v52 = &v32;
  v53 = (char *)&v31 + 12;
  v55 = &v33;
  v56 = (char *)&v32 + 8;
  v58 = &v34;
  v59 = (char *)&v33 + 8;
  v61 = &v36;
  v62 = (char *)&v35 + 8;
  v64 = v37;
  v65 = (char *)&v36 + 8;
  v41 = 0;
  v42 = 51;
  v44 = 0;
  v45 = 58;
  v47 = 0;
  v48 = 59;
  v50 = 0;
  v51 = 3;
  v54 = 33;
  v57 = 121;
  v60 = 6;
  v63 = 15;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 218, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, *(_QWORD *)(a1 + 24));
  AcquireSRWLockShared((PSRWLOCK)(a1 + 672));
  memset_0(a2, 0, 0xC8u);
  for ( i = 0; (unsigned int)i < 9; i = (unsigned int)(i + 1) )
  {
    Option = DhcpFindOption(a1 + 696, LOBYTE(v39[6 * i]), 0, *(_QWORD *)(a1 + 736), *(_DWORD *)(a1 + 744), 0);
    v7 = (&v40)[3 * i];
    v8 = Option;
    if ( Option )
    {
      v9 = DhcpAlloc(*(unsigned int *)(Option + 56));
      *(_QWORD *)v7 = v9;
      if ( !v9 )
      {
        v11 = 8;
        goto LABEL_26;
      }
      memcpy_0(v9, *(const void **)(v8 + 48), *(unsigned int *)(v8 + 56));
      v4 = *(&v41 + 3 * i);
      if ( v4 )
        *(_DWORD *)v4 = *(_DWORD *)(v8 + 56);
    }
    else
    {
      v10 = (_DWORD *)*(&v41 + 3 * i);
      *(_QWORD *)v7 = 0;
      if ( v10 )
        *v10 = 0;
    }
  }
  HIDWORD(v31) >>= 2;
  DWORD2(v32) >>= 3;
  DWORD2(v35) >>= 2;
  v12 = (_BYTE *)v34;
  v13 = 0;
  for ( j = DWORD2(v33); (_DWORD)j; j = (unsigned int)(j - v4) )
  {
    if ( *v12 )
      v4 = (unsigned int)((((unsigned __int8)*v12 - 1) >> 3) + 6);
    else
      v4 = 5;
    if ( (unsigned int)v4 > (unsigned int)j )
      goto LABEL_21;
    v13 = (unsigned int)(v13 + 1);
    v12 += (unsigned int)v4;
  }
  DWORD2(v33) = v13;
LABEL_21:
  if ( a2 )
  {
    v15 = v30;
    v16 = v38;
    *a2 = v29;
    v17 = v31;
    a2[1] = v15;
    v18 = v32;
    a2[2] = v17;
    v19 = v33;
    a2[3] = v18;
    v20 = v34;
    a2[4] = v19;
    v21 = v35;
    a2[5] = v20;
    v22 = v36;
    a2[6] = v21;
    v23 = v37[0];
    a2[7] = v22;
    v24 = v37[1];
    a2[8] = v23;
    v25 = v37[2];
    a2[9] = v24;
    v26 = v37[3];
    a2[10] = v25;
    a2[11] = v26;
    *((_QWORD *)a2 + 24) = v16;
    v27 = 0;
  }
  else
  {
    v27 = 22;
    *(_DWORD *)_o__errno(v4, j, v13) = 22;
    invalid_parameter_noinfo();
  }
  v11 = Win32FromErrno(v27, j, v13);
  if ( !v11 )
    memset_0(&v29, 0, 0xC8u);
LABEL_26:
  DhcpCleanParsedOptions((char *)&v29);
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 672));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 219, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180012ef0  push    rbp
0x180012ef2  push    rbx
0x180012ef3  push    rsi
0x180012ef4  push    rdi
0x180012ef5  push    r12
0x180012ef7  push    r13
0x180012ef9  push    r14
0x180012efb  push    r15
0x180012efd  lea     rbp, [rsp-0E8h]
0x180012f05  sub     rsp, 1E8h
0x180012f0c  mov     rbx, rdx
0x180012f0f  mov     r15, rcx
0x180012f12  mov     edi, 0C8h
0x180012f17  lea     rcx, [rsp+220h+var_1F0]; void *
0x180012f1c  mov     r8d, edi; Size
0x180012f1f  xor     edx, edx; Val
0x180012f21  call    memset_0
0x180012f26  lea     rax, [rsp+220h+var_1DC]
0x180012f2b  mov     [rbp+120h+var_120], 1
0x180012f32  mov     [rbp+120h+var_118], rax
0x180012f36  lea     rax, [rsp+220h+var_1D8]
0x180012f3b  mov     [rbp+120h+var_100], rax
0x180012f3f  lea     rax, [rsp+220h+var_1D4]
0x180012f44  mov     [rbp+120h+var_E8], rax
0x180012f48  lea     rax, [rsp+220h+var_1D0]
0x180012f4d  mov     [rbp+120h+var_D0], rax
0x180012f51  lea     rax, [rsp+220h+var_1C0]
0x180012f56  mov     [rbp+120h+var_B8], rax
0x180012f5a  lea     rax, [rsp+220h+var_1D0+0Ch]
0x180012f5f  mov     [rbp+120h+var_B0], rax
0x180012f63  lea     rax, [rsp+220h+var_1B0]
0x180012f68  mov     [rbp+120h+var_A0], rax
0x180012f6f  lea     rax, [rsp+220h+var_1C0+8]
0x180012f74  mov     [rbp+120h+var_98], rax
0x180012f7b  lea     rax, [rbp+120h+var_1A0]
0x180012f7f  mov     [rbp+120h+var_88], rax
0x180012f86  lea     rax, [rsp+220h+var_1B0+8]
0x180012f8b  mov     [rbp+120h+var_80], rax
0x180012f92  lea     rax, [rbp+120h+var_180]
0x180012f96  mov     [rbp+120h+var_70], rax
0x180012f9d  lea     rax, [rbp+120h+var_188]
0x180012fa1  mov     [rbp+120h+var_68], rax
0x180012fa8  lea     rax, [rbp+120h+var_170]
0x180012fac  mov     [rbp+120h+var_58], rax
0x180012fb3  lea     rax, [rbp+120h+var_180+8]
0x180012fb7  mov     [rbp+120h+var_50], rax
0x180012fbe  mov     [rbp+120h+var_110], 0
0x180012fc6  mov     [rbp+120h+var_108], 33h ; '3'
0x180012fcd  mov     [rbp+120h+var_F8], 0
0x180012fd5  mov     [rbp+120h+var_F0], 3Ah ; ':'
0x180012fdc  mov     [rbp+120h+var_E0], 0
0x180012fe4  mov     [rbp+120h+var_D8], 3Bh ; ';'
0x180012feb  mov     [rbp+120h+var_C8], 0
0x180012ff3  mov     [rbp+120h+var_C0], 3
0x180012ffa  mov     [rbp+120h+var_A8], 21h ; '!'
0x180013001  mov     [rbp+120h+var_90], 79h ; 'y'
0x18001300b  mov     [rbp+120h+var_78], 6
0x180013015  mov     [rbp+120h+var_60], 0Fh
0x18001301f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013026  jz      short loc_180013040
0x180013028  mov     r9, [r15+18h]
0x18001302c  lea     edx, [rdi+12h]
0x18001302f  mov     ecx, 404h
0x180013034  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18001303b  call    WPP_SF_q
0x180013040  lea     r13, [r15+2A0h]
0x180013047  mov     rcx, r13; SRWLock
0x18001304a  call    cs:__imp_AcquireSRWLockShared
0x180013050  mov     r8, rdi; Size
0x180013053  xor     edx, edx; Val
0x180013055  mov     rcx, rbx; void *
0x180013058  call    memset_0
0x18001305d  xor     esi, esi
0x18001305f  cmp     esi, 9
0x180013062  jnb     loc_180013103
0x180013068  mov     eax, [r15+2E8h]
0x18001306f  lea     r14, [rsi+rsi*2]
0x180013073  movzx   edx, byte ptr [rbp+r14*8+120h+var_120]
0x180013079  lea     rcx, [r15+2B8h]
0x180013080  mov     r9, [r15+2E0h]
0x180013087  xor     r8d, r8d
0x18001308a  mov     [rsp+220h+var_1F8], 0
0x180013092  mov     [rsp+220h+var_200], eax
0x180013096  call    DhcpFindOption
0x18001309b  mov     r12, [rbp+r14*8+120h+var_118]
0x1800130a0  mov     rdi, rax
0x1800130a3  test    rax, rax
0x1800130a6  jz      short loc_1800130DA
0x1800130a8  mov     ecx, [rax+38h]
0x1800130ab  call    DhcpAlloc
0x1800130b0  mov     [r12], rax
0x1800130b4  test    rax, rax
0x1800130b7  jz      short loc_1800130F9
0x1800130b9  mov     r8d, [rdi+38h]; Size
0x1800130bd  mov     rcx, rax; void *
0x1800130c0  mov     rdx, [rdi+30h]; Src
0x1800130c4  call    memcpy_0
0x1800130c9  mov     rcx, [rbp+r14*8+120h+var_110]
0x1800130ce  test    rcx, rcx
0x1800130d1  jz      short loc_1800130F2
0x1800130d3  mov     eax, [rdi+38h]
0x1800130d6  mov     [rcx], eax
0x1800130d8  jmp     short loc_1800130F2
0x1800130da  mov     rax, [rbp+r14*8+120h+var_110]
0x1800130df  mov     qword ptr [r12], 0
0x1800130e7  test    rax, rax
0x1800130ea  jz      short loc_1800130F2
0x1800130ec  mov     dword ptr [rax], 0
0x1800130f2  inc     esi
0x1800130f4  jmp     loc_18001305F
0x1800130f9  mov     ebx, 8
0x1800130fe  jmp     loc_180013203
0x180013103  shr     dword ptr [rsp+220h+var_1D0+0Ch], 2
0x180013108  shr     dword ptr [rsp+220h+var_1C0+8], 3
0x18001310d  shr     [rbp+120h+var_188], 2
0x180013111  mov     r9, qword ptr [rbp+120h+var_1A0]
0x180013115  xor     r8d, r8d
0x180013118  mov     edx, dword ptr [rsp+220h+var_1B0+8]
0x18001311c  test    edx, edx
0x18001311e  jz      short loc_180013149
0x180013120  cmp     byte ptr [r9], 0
0x180013124  jz      short loc_180013134
0x180013126  movzx   ecx, byte ptr [r9]
0x18001312a  dec     ecx
0x18001312c  sar     ecx, 3
0x18001312f  add     ecx, 6
0x180013132  jmp     short loc_180013139
0x180013134  mov     ecx, 5
0x180013139  cmp     ecx, edx
0x18001313b  ja      short loc_18001314E
0x18001313d  mov     eax, ecx
0x18001313f  inc     r8d
0x180013142  add     r9, rax
0x180013145  sub     edx, ecx
0x180013147  jmp     short loc_18001311C
0x180013149  mov     dword ptr [rsp+220h+var_1B0+8], r8d
0x18001314e  test    rbx, rbx
0x180013151  jz      short loc_1800131D2
0x180013153  movaps  xmm0, [rsp+220h+var_1F0]
0x180013158  movaps  xmm1, xmmword ptr [rsp+40h]
0x18001315d  mov     rax, [rbp+120h+var_130]
0x180013161  movups  xmmword ptr [rbx], xmm0
0x180013164  movaps  xmm0, [rsp+220h+var_1D0]
0x180013169  movups  xmmword ptr [rbx+10h], xmm1
0x18001316d  movaps  xmm1, [rsp+220h+var_1C0]
0x180013172  movups  xmmword ptr [rbx+20h], xmm0
0x180013176  movaps  xmm0, [rsp+220h+var_1B0]
0x18001317b  movups  xmmword ptr [rbx+30h], xmm1
0x18001317f  movaps  xmm1, [rbp+120h+var_1A0]
0x180013183  movups  xmmword ptr [rbx+40h], xmm0
0x180013187  movaps  xmm0, xmmword ptr [rbp-70h]
0x18001318b  movups  xmmword ptr [rbx+50h], xmm1
0x18001318f  movaps  xmm1, [rbp+120h+var_180]
0x180013193  movups  xmmword ptr [rbx+60h], xmm0
0x180013197  movaps  xmm0, [rbp+120h+var_170]
0x18001319b  movups  xmmword ptr [rbx+70h], xmm1
0x18001319f  movaps  xmm1, [rbp+120h+var_160]
0x1800131a3  movups  xmmword ptr [rbx+80h], xmm0
0x1800131aa  movaps  xmm0, [rbp+120h+var_150]
0x1800131ae  movups  xmmword ptr [rbx+90h], xmm1
0x1800131b5  movaps  xmm1, [rbp+120h+var_140]
0x1800131b9  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800131c0  movups  xmmword ptr [rbx+0B0h], xmm1
0x1800131c7  mov     [rbx+0C0h], rax
0x1800131ce  xor     ebx, ebx
0x1800131d0  jmp     short loc_1800131E4
0x1800131d2  call    cs:__imp__o__errno
0x1800131d8  mov     ebx, 16h
0x1800131dd  mov     [rax], ebx
0x1800131df  call    _invalid_parameter_noinfo
0x1800131e4  mov     ecx, ebx
0x1800131e6  call    Win32FromErrno
0x1800131eb  mov     ebx, eax
0x1800131ed  test    eax, eax
0x1800131ef  jnz     short loc_180013203
0x1800131f1  xor     edx, edx; Val
0x1800131f3  lea     rcx, [rsp+220h+var_1F0]; void *
0x1800131f8  mov     r8d, 0C8h; Size
0x1800131fe  call    memset_0
0x180013203  lea     rcx, [rsp+220h+var_1F0]; void *
0x180013208  call    DhcpCleanParsedOptions
0x18001320d  mov     rcx, r13; SRWLock
0x180013210  call    cs:__imp_ReleaseSRWLockShared
0x180013216  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001321d  jz      short loc_180013238
0x18001321f  mov     edx, 0DBh
0x180013224  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18001322b  mov     ecx, 404h
0x180013230  mov     r9d, ebx
0x180013233  call    WPP_SF_D
0x180013238  mov     eax, ebx
0x18001323a  add     rsp, 1E8h
0x180013241  pop     r15
0x180013243  pop     r14
0x180013245  pop     r13
0x180013247  pop     r12
0x180013249  pop     rdi
0x18001324a  pop     rsi
0x18001324b  pop     rbx
0x18001324c  pop     rbp
0x18001324d  retn
```
