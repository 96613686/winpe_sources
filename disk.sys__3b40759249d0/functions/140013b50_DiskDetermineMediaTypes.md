# DiskDetermineMediaTypes

- ea: `0x140013b50`
- end: `0x140013fdc`
- name: `DiskDetermineMediaTypes`
- size: `1164`
- prototype: `__int64 __fastcall(__int64, __int64, char, char, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013750`

## callees

- `0x14000445c`
- `0x140004500`
- `0x140005b26`
- `0x140013b50`

## pseudocode

```c
__int64 __fastcall DiskDetermineMediaTypes(__int64 a1, __int64 a2, char a3, char a4, char a5, char a6)
{
  _DWORD *v6; // r13
  __int64 v8; // rbp
  _DWORD *v9; // rbx
  unsigned int *v10; // rax
  const char *v11; // rdx
  const char *v12; // r12
  __int64 v13; // rsi
  unsigned __int64 v14; // r8
  int v15; // r15d
  const char *v16; // rcx
  size_t v17; // r8
  const char *v18; // rcx
  size_t v19; // r8
  __int64 v20; // rsi
  char v21; // r12
  size_t v22; // r8
  char **v23; // rdi
  const char *v24; // rcx
  const char *v25; // rcx
  size_t v26; // r8
  const char *v27; // rcx
  size_t v28; // r8
  __int64 v29; // r8
  int v30; // eax
  int v31; // ecx
  __int64 result; // rax
  char *Str2; // [rsp+30h] [rbp-68h]
  char *v34; // [rsp+38h] [rbp-60h]
  char *v35; // [rsp+40h] [rbp-58h]
  __int64 v36; // [rsp+48h] [rbp-50h]
  _DWORD *v37; // [rsp+50h] [rbp-48h]
  int v38; // [rsp+A0h] [rbp+8h]

  v6 = *(_DWORD **)(a2 + 24);
  v8 = *(_QWORD *)(a1 + 64);
  v37 = v6;
  v9 = v6 + 2;
  if ( (*(_DWORD *)(a1 + 52) & 1) == 0 )
  {
    *v6 = 7;
    v6[1] = 1;
    *(_QWORD *)v9 = *(_QWORD *)(v8 + 552);
    v6[4] = 12;
    v6[5] = *(_DWORD *)(v8 + 564);
    v6[6] = *(_DWORD *)(v8 + 568);
    v6[7] = *(_DWORD *)(v8 + 572);
    v6[8] = 1;
    v6[9] = -2147483640;
    if ( !a6 )
      v6[9] = -2147483384;
    goto LABEL_56;
  }
  v36 = *(_QWORD *)(a2 + 184);
  v10 = *(unsigned int **)(v8 + 520);
  v11 = (char *)v10 + v10[3];
  v12 = (char *)v10 + v10[4];
  Str2 = (char *)v11;
  v35 = (char *)v10 + v10[5];
  v34 = (char *)v12;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_ss(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v11, a3, (_DWORD)v11, (__int64)v12);
    v11 = Str2;
  }
  v13 = 0;
  v14 = 0x140000000uLL;
  v15 = 8;
  if ( DiskMediaTypesExclude[0] )
  {
    do
    {
      v16 = DiskMediaTypesExclude[6 * v13];
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      if ( !strncmp_0(v16, v11, v17) )
      {
        v18 = (&off_140008218)[6 * v13];
        if ( !v18 )
          goto LABEL_48;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        if ( !strncmp_0(v18, v12, v19) )
        {
LABEL_48:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_sss(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v11, v14, (_DWORD)Str2, (__int64)v12, (__int64)v35);
          }
          *v6 = 7;
          v6[1] = 1;
          *(_QWORD *)v9 = *(_QWORD *)(v8 + 552);
          v9[2] = 11;
          v9[3] = *(_DWORD *)(v8 + 564);
          v9[4] = *(_DWORD *)(v8 + 568);
          v9[5] = *(_DWORD *)(v8 + 572);
          v9[6] = 1;
          v9[7] = 8;
          if ( a5 )
          {
            v15 = -2147483640;
            v9[7] = -2147483640;
          }
          if ( !a6 )
            v9[7] = v15 | 0x100;
          goto LABEL_56;
        }
      }
      v11 = Str2;
      v14 = 0x140000000uLL;
      v13 = (unsigned int)(v13 + 1);
    }
    while ( DiskMediaTypesExclude[6 * v13] );
  }
  v20 = 0;
  v21 = 0;
  v38 = 0;
  if ( !DiskMediaTypes[0] )
    goto LABEL_47;
  do
  {
    v22 = -1;
    v23 = &DiskMediaTypes[6 * v20];
    v24 = *v23;
    do
      ++v22;
    while ( v24[v22] );
    if ( !strncmp_0(v24, Str2, v22) )
    {
      v25 = v23[1];
      if ( !v25 )
        goto LABEL_25;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      if ( !strncmp_0(v25, v34, v26) )
      {
LABEL_25:
        v27 = v23[2];
        if ( !v27 )
          goto LABEL_29;
        v28 = -1;
        do
          ++v28;
        while ( v27[v28] );
        if ( !strncmp_0(v27, v35, v28) )
        {
LABEL_29:
          LODWORD(v11) = v36;
          *v6 = 7;
          v6[1] = *((_DWORD *)v23 + 6);
          if ( *(_DWORD *)(v36 + 8) < (unsigned int)(32 * *((_DWORD *)v23 + 6) + 8) )
          {
            result = 3221225507LL;
            *(_DWORD *)(a2 + 48) = -1073741789;
            return result;
          }
          v29 = 0;
          v21 = 1;
          if ( !*((_DWORD *)v23 + 6) )
            goto LABEL_45;
          while ( 1 )
          {
            *(_QWORD *)v9 = *(_QWORD *)(v8 + 552);
            v9[3] = *(_DWORD *)(v8 + 564);
            v9[4] = *(_DWORD *)(v8 + 568);
            v9[5] = *(_DWORD *)(v8 + 572);
            v9[6] = *((_DWORD *)v23 + 7);
            v30 = 2;
            LODWORD(v11) = *((_DWORD *)v23 + v29 + 8);
            v9[2] = (_DWORD)v11;
            if ( (_DWORD)v11 != 58 )
              v30 = 8;
            v9[7] = v30;
            if ( !a5 )
              goto LABEL_41;
            if ( a3 == 2 )
            {
              v31 = 58;
            }
            else
            {
              if ( a3 != 3 )
                goto LABEL_40;
              v31 = 65;
              if ( a4 != -121 )
                v31 = 59;
            }
            if ( (_DWORD)v11 == v31 )
            {
LABEL_40:
              v30 |= 0x80000000;
              v9[7] = v30;
            }
LABEL_41:
            if ( !a6 )
              v9[7] = v30 | 0x100;
            v9 += 8;
            v29 = (unsigned int)(v29 + 1);
            if ( (unsigned int)v29 >= *((_DWORD *)v23 + 6) )
            {
              LODWORD(v20) = v38;
              v6 = v37;
              break;
            }
          }
        }
      }
    }
LABEL_45:
    v20 = (unsigned int)(v20 + 1);
    v14 = 0x140000000uLL;
    v38 = v20;
  }
  while ( DiskMediaTypes[6 * v20] );
  if ( !v21 )
  {
LABEL_47:
    v12 = v34;
    goto LABEL_48;
  }
LABEL_56:
  *(_QWORD *)(a2 + 56) = 32LL * (unsigned int)v6[1] + 8;
  return 0;
}

```

## disassembly

```asm
0x140013b50  mov     [rsp+arg_10], rbx
0x140013b55  mov     [rsp+arg_18], r9b
0x140013b5a  mov     [rsp+arg_8], rdx
0x140013b5f  push    rbp
0x140013b60  push    rsi
0x140013b61  push    rdi
0x140013b62  push    r12
0x140013b64  push    r13
0x140013b66  push    r14
0x140013b68  push    r15
0x140013b6a  sub     rsp, 60h
0x140013b6e  mov     r13, [rdx+18h]
0x140013b72  movzx   r14d, r8b
0x140013b76  mov     eax, [rcx+34h]
0x140013b79  mov     rbp, [rcx+40h]
0x140013b7d  mov     [rsp+98h+var_48], r13
0x140013b82  lea     rbx, [r13+8]
0x140013b86  test    al, 1
0x140013b88  jnz     short loc_140013BEE
0x140013b8a  cmp     [rsp+98h+arg_28], 0
0x140013b92  mov     dword ptr [r13+0], 7
0x140013b9a  mov     dword ptr [r13+4], 1
0x140013ba2  mov     rax, [rbp+228h]
0x140013ba9  mov     [rbx], rax
0x140013bac  mov     dword ptr [rbx+8], 0Ch
0x140013bb3  mov     eax, [rbp+234h]
0x140013bb9  mov     [rbx+0Ch], eax
0x140013bbc  mov     eax, [rbp+238h]
0x140013bc2  mov     [rbx+10h], eax
0x140013bc5  mov     eax, [rbp+23Ch]
0x140013bcb  mov     [rbx+14h], eax
0x140013bce  mov     dword ptr [rbx+18h], 1
0x140013bd5  mov     dword ptr [rbx+1Ch], 80000008h
0x140013bdc  jnz     loc_140013F93
0x140013be2  mov     dword ptr [rbx+1Ch], 80000108h
0x140013be9  jmp     loc_140013F93
0x140013bee  mov     rax, [rdx+0B8h]
0x140013bf5  mov     [rsp+98h+var_50], rax
0x140013bfa  mov     rax, [rbp+208h]
0x140013c01  mov     edx, [rax+0Ch]
0x140013c04  mov     r12d, [rax+10h]
0x140013c08  add     rdx, rax
0x140013c0b  mov     ecx, [rax+14h]
0x140013c0e  add     r12, rax
0x140013c11  add     rcx, rax
0x140013c14  mov     [rsp+98h+Str2], rdx
0x140013c19  mov     [rsp+98h+var_58], rcx
0x140013c1e  mov     [rsp+98h+var_60], r12
0x140013c23  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c2a  lea     rax, WPP_GLOBAL_Control
0x140013c31  cmp     rcx, rax
0x140013c34  jz      short loc_140013C59
0x140013c36  mov     eax, [rcx+2Ch]
0x140013c39  test    al, 10h
0x140013c3b  jz      short loc_140013C59
0x140013c3d  cmp     byte ptr [rcx+29h], 4
0x140013c41  jb      short loc_140013C59
0x140013c43  mov     rcx, [rcx+18h]
0x140013c47  mov     r9, rdx
0x140013c4a  mov     [rsp+98h+var_78], r12
0x140013c4f  call    WPP_SF_ss
0x140013c54  mov     rdx, [rsp+98h+Str2]; Str2
0x140013c59  xor     esi, esi
0x140013c5b  lea     r8, cs:140000000h
0x140013c62  cmp     cs:DiskMediaTypesExclude, rsi
0x140013c69  mov     r15d, 8
0x140013c6f  jz      loc_140013D0E
0x140013c75  nop     word ptr [rax+rax+00000000h]
0x140013c80  lea     rdi, [rsi+rsi*2]
0x140013c84  add     rdi, rdi
0x140013c87  mov     rcx, ds:rva DiskMediaTypesExclude[r8+rdi*8]; Str1
0x140013c8f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140013c96  inc     r8; MaxCount
0x140013c99  cmp     byte ptr [rcx+r8], 0
0x140013c9e  jnz     short loc_140013C96
0x140013ca0  call    strncmp_0
0x140013ca5  test    eax, eax
0x140013ca7  jnz     short loc_140013CEA
0x140013ca9  lea     rcx, cs:140000000h
0x140013cb0  mov     rcx, ds:rva off_140008218[rcx+rdi*8]; Str1
0x140013cb8  test    rcx, rcx
0x140013cbb  jz      loc_140013EE8
0x140013cc1  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140013cc8  nop     dword ptr [rax+rax+00000000h]
0x140013cd0  inc     r8; MaxCount
0x140013cd3  cmp     byte ptr [rcx+r8], 0
0x140013cd8  jnz     short loc_140013CD0
0x140013cda  mov     rdx, r12; Str2
0x140013cdd  call    strncmp_0
0x140013ce2  test    eax, eax
0x140013ce4  jz      loc_140013EE8
0x140013cea  mov     rdx, [rsp+98h+Str2]
0x140013cef  lea     r8, cs:140000000h
0x140013cf6  inc     esi
0x140013cf8  lea     rcx, [rsi+rsi*2]
0x140013cfc  add     rcx, rcx
0x140013cff  cmp     ds:rva DiskMediaTypesExclude[r8+rcx*8], 0
0x140013d08  jnz     loc_140013C80
0x140013d0e  xor     esi, esi
0x140013d10  xor     r12b, r12b
0x140013d13  cmp     cs:DiskMediaTypes, rsi
0x140013d1a  mov     [rsp+98h+arg_0], esi
0x140013d21  jz      loc_140013EE3
0x140013d27  nop     word ptr [rax+rax+00000000h]
0x140013d30  lea     rdi, rva DiskMediaTypes[r8]
0x140013d37  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140013d3e  lea     rcx, [rsi+rsi*2]
0x140013d42  shl     rcx, 4
0x140013d46  add     rdi, rcx
0x140013d49  mov     rcx, [rdi]; Str1
0x140013d4c  nop     dword ptr [rax+00h]
0x140013d50  inc     r8; MaxCount
0x140013d53  cmp     byte ptr [rcx+r8], 0
0x140013d58  jnz     short loc_140013D50
0x140013d5a  mov     rdx, [rsp+98h+Str2]; Str2
0x140013d5f  call    strncmp_0
0x140013d64  test    eax, eax
0x140013d66  jnz     loc_140013EB4
0x140013d6c  mov     rcx, [rdi+8]; Str1
0x140013d70  test    rcx, rcx
0x140013d73  jz      short loc_140013D9C
0x140013d75  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140013d7c  nop     dword ptr [rax+00h]
0x140013d80  inc     r8; MaxCount
0x140013d83  cmp     byte ptr [rcx+r8], 0
0x140013d88  jnz     short loc_140013D80
0x140013d8a  mov     rdx, [rsp+98h+var_60]; Str2
0x140013d8f  call    strncmp_0
0x140013d94  test    eax, eax
0x140013d96  jnz     loc_140013EB4
0x140013d9c  mov     rcx, [rdi+10h]; Str1
0x140013da0  test    rcx, rcx
0x140013da3  jz      short loc_140013DCC
0x140013da5  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140013dac  nop     dword ptr [rax+00h]
0x140013db0  inc     r8; MaxCount
0x140013db3  cmp     byte ptr [rcx+r8], 0
0x140013db8  jnz     short loc_140013DB0
0x140013dba  mov     rdx, [rsp+98h+var_58]; Str2
0x140013dbf  call    strncmp_0
0x140013dc4  test    eax, eax
0x140013dc6  jnz     loc_140013EB4
0x140013dcc  mov     rdx, [rsp+98h+var_50]
0x140013dd1  mov     dword ptr [r13+0], 7
0x140013dd9  mov     eax, [rdi+18h]
0x140013ddc  mov     [r13+4], eax
0x140013de0  mov     ecx, [rdi+18h]
0x140013de3  mov     eax, ecx
0x140013de5  shl     eax, 5
0x140013de8  add     eax, r15d
0x140013deb  cmp     [rdx+8], eax
0x140013dee  jb      loc_140013FC6
0x140013df4  xor     r8d, r8d
0x140013df7  mov     r12b, 1
0x140013dfa  test    ecx, ecx
0x140013dfc  jz      loc_140013EB4
0x140013e02  movzx   r13d, [rsp+98h+arg_18]
0x140013e0b  mov     esi, 3Bh ; ';'
0x140013e10  mov     rax, [rbp+228h]
0x140013e17  mov     [rbx], rax
0x140013e1a  mov     eax, [rbp+234h]
0x140013e20  mov     [rbx+0Ch], eax
0x140013e23  mov     eax, [rbp+238h]
0x140013e29  mov     [rbx+10h], eax
0x140013e2c  mov     eax, [rbp+23Ch]
0x140013e32  mov     [rbx+14h], eax
0x140013e35  mov     eax, [rdi+1Ch]
0x140013e38  mov     [rbx+18h], eax
0x140013e3b  mov     eax, 2
0x140013e40  mov     edx, [rdi+r8*4+20h]
0x140013e45  cmp     edx, 3Ah ; ':'
0x140013e48  mov     [rbx+8], edx
0x140013e4b  cmovnz  eax, r15d
0x140013e4f  cmp     [rsp+98h+arg_20], 0
0x140013e57  mov     [rbx+1Ch], eax
0x140013e5a  jz      short loc_140013E86
0x140013e5c  cmp     r14b, 2
0x140013e60  jnz     short loc_140013E69
0x140013e62  mov     ecx, 3Ah ; ':'
0x140013e67  jmp     short loc_140013E7B
0x140013e69  cmp     r14b, 3
0x140013e6d  jnz     short loc_140013E7F
0x140013e6f  cmp     r13b, 87h
0x140013e73  mov     ecx, 41h ; 'A'
0x140013e78  cmovnz  ecx, esi
0x140013e7b  cmp     edx, ecx
0x140013e7d  jnz     short loc_140013E86
0x140013e7f  bts     eax, 1Fh
0x140013e83  mov     [rbx+1Ch], eax
0x140013e86  cmp     [rsp+98h+arg_28], 0
0x140013e8e  jnz     short loc_140013E97
0x140013e90  bts     eax, 8
0x140013e94  mov     [rbx+1Ch], eax
0x140013e97  add     rbx, 20h ; ' '
0x140013e9b  inc     r8d
0x140013e9e  cmp     r8d, [rdi+18h]
0x140013ea2  jb      loc_140013E10
0x140013ea8  mov     esi, [rsp+98h+arg_0]
0x140013eaf  mov     r13, [rsp+98h+var_48]
0x140013eb4  inc     esi
0x140013eb6  lea     r8, cs:140000000h
0x140013ebd  mov     [rsp+98h+arg_0], esi
0x140013ec4  lea     rcx, [rsi+rsi*2]
0x140013ec8  add     rcx, rcx
0x140013ecb  cmp     ds:rva DiskMediaTypes[r8+rcx*8], 0
0x140013ed4  jnz     loc_140013D30
0x140013eda  test    r12b, r12b
0x140013edd  jnz     loc_140013F93
0x140013ee3  mov     r12, [rsp+98h+var_60]
0x140013ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x140013eef  lea     rax, WPP_GLOBAL_Control
0x140013ef6  cmp     rcx, rax
0x140013ef9  jz      short loc_140013F25
0x140013efb  mov     eax, [rcx+2Ch]
0x140013efe  test    al, 10h
0x140013f00  jz      short loc_140013F25
0x140013f02  cmp     byte ptr [rcx+29h], 3
0x140013f06  jb      short loc_140013F25
0x140013f08  mov     rax, [rsp+98h+var_58]
0x140013f0d  mov     r9, [rsp+98h+Str2]
0x140013f12  mov     rcx, [rcx+18h]
0x140013f16  mov     [rsp+98h+var_70], rax
0x140013f1b  mov     [rsp+98h+var_78], r12
0x140013f20  call    WPP_SF_sss
0x140013f25  cmp     [rsp+98h+arg_20], 0
0x140013f2d  mov     dword ptr [r13+0], 7
0x140013f35  mov     dword ptr [r13+4], 1
0x140013f3d  mov     rax, [rbp+228h]
0x140013f44  mov     [rbx], rax
0x140013f47  mov     dword ptr [rbx+8], 0Bh
0x140013f4e  mov     eax, [rbp+234h]
0x140013f54  mov     [rbx+0Ch], eax
0x140013f57  mov     eax, [rbp+238h]
0x140013f5d  mov     [rbx+10h], eax
0x140013f60  mov     eax, [rbp+23Ch]
0x140013f66  mov     [rbx+14h], eax
0x140013f69  mov     dword ptr [rbx+18h], 1
0x140013f70  mov     [rbx+1Ch], r15d
0x140013f74  jz      short loc_140013F80
0x140013f76  mov     r15d, 80000008h
0x140013f7c  mov     [rbx+1Ch], r15d
0x140013f80  cmp     [rsp+98h+arg_28], 0
0x140013f88  jnz     short loc_140013F93
0x140013f8a  bts     r15d, 8
0x140013f8f  mov     [rbx+1Ch], r15d
0x140013f93  mov     eax, [r13+4]
0x140013f97  mov     rcx, [rsp+98h+arg_8]
0x140013f9f  shl     rax, 5
0x140013fa3  add     rax, 8
0x140013fa7  mov     [rcx+38h], rax
0x140013fab  xor     eax, eax
0x140013fad  mov     rbx, [rsp+98h+arg_10]
0x140013fb5  add     rsp, 60h
0x140013fb9  pop     r15
0x140013fbb  pop     r14
0x140013fbd  pop     r13
0x140013fbf  pop     r12
0x140013fc1  pop     rdi
0x140013fc2  pop     rsi
0x140013fc3  pop     rbp
0x140013fc4  retn
0x140013fc6  mov     rcx, [rsp+98h+arg_8]
0x140013fce  mov     eax, 0C0000023h
0x140013fd3  mov     dword ptr [rcx+30h], 0C0000023h
0x140013fda  jmp     short loc_140013FAD
```
