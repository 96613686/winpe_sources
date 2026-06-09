# LdrpAccessResourceDataNoMultipleLanguage

- ea: `0x1800559c0`
- end: `0x180056087`
- name: `LdrpAccessResourceDataNoMultipleLanguage`
- size: `1735`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180056800`
- `0x180056d70`
- `0x180056ec0`
- `0x180057760`
- `0x1800579d0`
- `0x1800a2790`
- `0x1800fa8f8`

## callees

- `0x18001f070`
- `0x1800559c0`
- `0x180056090`
- `0x1800680b0`
- `0x18015e730`

## pseudocode

```c
__int64 __fastcall LdrpAccessResourceDataNoMultipleLanguage(
        unsigned __int64 a1,
        unsigned int *a2,
        unsigned __int64 *a3,
        _DWORD *a4)
{
  unsigned __int64 v5; // r14
  bool v6; // di
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r15
  int v9; // edx
  __int16 v10; // ax
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // ebx
  __int64 FileSizeFromLoadAsDataTable; // rdi
  int v15; // eax
  __int16 v16; // ax
  unsigned int v17; // r8d
  unsigned __int64 v18; // rsi
  _DWORD *v19; // rax
  unsigned int v20; // r10d
  unsigned int v21; // r9d
  unsigned int v22; // edx
  unsigned int v23; // edx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  __int64 v26; // r10
  _DWORD *v27; // rdx
  unsigned int v28; // r11d
  unsigned int v29; // r8d
  unsigned int v30; // ecx
  __int64 v31; // r8
  int v32; // eax
  __int16 v33; // cx
  __int64 v34; // rbx
  __int64 v35; // r8
  unsigned int v36; // r10d
  unsigned int j; // r9d
  unsigned int v38; // ecx
  __int64 v39; // r10
  unsigned int v40; // r9d
  _DWORD *v41; // rdx
  unsigned int v42; // r11d
  unsigned int v43; // ecx
  __int64 v44; // rdx
  int v45; // ecx
  __int64 v47; // [rsp+40h] [rbp-D8h]
  __int64 v48; // [rsp+60h] [rbp-B8h] BYREF
  int v49; // [rsp+68h] [rbp-B0h]
  unsigned int v50; // [rsp+6Ch] [rbp-ACh]
  unsigned int v51; // [rsp+70h] [rbp-A8h]
  unsigned int i; // [rsp+74h] [rbp-A4h]
  int v53; // [rsp+78h] [rbp-A0h]
  __int64 v54; // [rsp+80h] [rbp-98h] BYREF
  _DWORD *v55; // [rsp+88h] [rbp-90h]
  __int64 v56; // [rsp+90h] [rbp-88h] BYREF
  _DWORD *v57; // [rsp+98h] [rbp-80h]
  __int64 v58; // [rsp+A0h] [rbp-78h]
  _DWORD *v59; // [rsp+A8h] [rbp-70h]
  unsigned __int64 v60; // [rsp+B0h] [rbp-68h]
  __int128 v61; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v62; // [rsp+C8h] [rbp-50h]
  __int128 v63; // [rsp+D8h] [rbp-40h]

  v5 = a1;
  v6 = 1;
  v7 = a1;
  v60 = a1;
  v54 = 0;
  v47 = 0;
  if ( (a1 & 2) != 0 || (a1 & 1) != 0 )
  {
    v6 = (a1 & 1) == 0;
    v7 = a1 & 0xFFFFFFFFFFFFFFFCuLL;
    v60 = a1 & 0xFFFFFFFFFFFFFFFCuLL;
    v8 = a1 & 0xFFFFFFFFFFFFFFFCuLL;
  }
  else
  {
    v8 = a1 & 0xFFFFFFFFFFFFFFFCuLL;
  }
  v9 = RtlImageNtHeaderEx(1, v7, 0, &v54);
  if ( !v54 )
    goto LABEL_11;
  v10 = *(_WORD *)(v54 + 24);
  if ( v10 == 267 )
  {
    if ( *(_DWORD *)(v54 + 116) > 2u )
    {
      v26 = *(unsigned int *)(v54 + 136);
      if ( (_DWORD)v26 )
      {
        if ( v6 || (unsigned int)v26 < *(_DWORD *)(v54 + 84) )
        {
          v12 = v7 + v26;
          v47 = v7 + v26;
          v9 = 0;
          goto LABEL_12;
        }
        v49 = 0;
        v55 = 0;
        v27 = (_DWORD *)(v54 + *(unsigned __int16 *)(v54 + 20) + 24LL);
        v55 = v27;
        v28 = *(unsigned __int16 *)(v54 + 6);
        v29 = 0;
        v49 = 0;
        while ( v29 < v28 )
        {
          v30 = v27[3];
          if ( (unsigned int)v26 >= v30 && (unsigned int)v26 < v27[4] + v30 )
          {
            if ( v27 )
            {
              v31 = v26 + v7 + (unsigned int)v27[5] - (unsigned __int64)(unsigned int)v27[3];
              v47 = v31;
              goto LABEL_63;
            }
            break;
          }
          v27 += 10;
          v55 = v27;
          v49 = ++v29;
        }
        v31 = 0;
        v47 = 0;
LABEL_63:
        v32 = 0;
        if ( !v31 )
          v32 = -1073741811;
        v9 = v32;
      }
      else
      {
        v9 = -1073741822;
      }
      goto LABEL_11;
    }
    goto LABEL_80;
  }
  if ( v10 != 523 || *(_DWORD *)(v54 + 132) <= 2u )
  {
LABEL_80:
    v9 = -1073741811;
    goto LABEL_11;
  }
  v11 = *(unsigned int *)(v54 + 152);
  if ( !(_DWORD)v11 )
  {
    v9 = -1073741822;
    goto LABEL_11;
  }
  if ( v6 || (unsigned int)v11 < *(_DWORD *)(v54 + 84) )
  {
    v47 = v7 + v11;
    v9 = 0;
LABEL_11:
    v12 = v47;
    goto LABEL_12;
  }
  v12 = RtlAddressInSectionTable(v54, v7, (unsigned int)v11);
  v47 = v12;
  v45 = 0;
  if ( !v12 )
    v45 = -1073741811;
  v9 = v45;
LABEL_12:
  if ( v9 < 0 || !v12 )
    return 3221225609LL;
  v13 = 0;
  FileSizeFromLoadAsDataTable = 0;
  v56 = 0;
  RtlImageNtHeaderEx(1, v8, 0, &v56);
  if ( !v56 )
  {
LABEL_96:
    v13 = -1073741701;
    goto LABEL_19;
  }
  if ( (v5 & 1) == 0 )
  {
    v33 = *(_WORD *)(v56 + 24);
    if ( v33 == 267 )
    {
      FileSizeFromLoadAsDataTable = *(unsigned int *)(v56 + 80);
      goto LABEL_19;
    }
    if ( v33 == 523 )
    {
      FileSizeFromLoadAsDataTable = *(unsigned int *)(v56 + 80);
      goto LABEL_19;
    }
    goto LABEL_96;
  }
  FileSizeFromLoadAsDataTable = LdrpGetFileSizeFromLoadAsDataTable(v5);
  if ( !FileSizeFromLoadAsDataTable )
  {
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v13 = ZwQueryVirtualMemory(-1, v8, 3, &v61, 48, 0);
    if ( v13 < 0 )
      v13 = -1073741793;
    else
      FileSizeFromLoadAsDataTable = v62;
  }
LABEL_19:
  if ( v13 < 0 )
    return (unsigned int)v13;
  if ( (unsigned __int64)a2 < v8
    || a2 + 4 < a2
    || FileSizeFromLoadAsDataTable && (unsigned __int64)(a2 + 4) > v8 + FileSizeFromLoadAsDataTable )
  {
    return (unsigned int)-1073741701;
  }
  v13 = 0;
  v15 = 0;
  v53 = 0;
  if ( (v5 & 2) != 0 || (v5 & 1) != 0 )
  {
    if ( (v5 & 1) != 0 )
      v15 = 1;
    v53 = v15;
    v5 = v8;
  }
  if ( v15 == 1 )
  {
    v48 = 0;
    RtlImageNtHeaderEx(1, v5, 0, &v48);
    if ( !v48 )
      return (unsigned int)-1073741687;
    v16 = *(_WORD *)(v48 + 24);
    if ( v16 == 267 )
    {
      v17 = *(_DWORD *)(v48 + 136);
    }
    else
    {
      if ( v16 != 523 )
        return (unsigned int)-1073741687;
      v17 = *(_DWORD *)(v48 + 152);
    }
    if ( v17 )
    {
      v18 = v5 + v17 - v47;
      i = 0;
      v59 = 0;
      v19 = (_DWORD *)(v48 + *(unsigned __int16 *)(v48 + 20) + 24LL);
      v59 = v19;
      v20 = *(unsigned __int16 *)(v48 + 6);
      v21 = 0;
      for ( i = 0; ; i = v21 )
      {
        if ( v21 >= v20 )
          return (unsigned int)-1073741687;
        v22 = v19[3];
        if ( v17 >= v22 && v17 < v19[4] + v22 )
          break;
        v19 += 10;
        v59 = v19;
        ++v21;
      }
      if ( !v19 )
        return (unsigned int)-1073741687;
      v23 = *a2;
      if ( *a2 > v19[2] )
      {
        v34 = (unsigned int)v19[3];
        v51 = 0;
        v58 = 0;
        v35 = v48 + *(unsigned __int16 *)(v48 + 20) + 24LL;
        v58 = v35;
        v36 = *(unsigned __int16 *)(v48 + 6);
        for ( j = 0; ; ++j )
        {
          v51 = j;
          if ( j >= v36 )
            return (unsigned int)-1073741687;
          v38 = *(_DWORD *)(v35 + 12);
          if ( v23 >= v38 && v23 < *(_DWORD *)(v35 + 16) + v38 )
            break;
          v35 += 40;
          v58 = v35;
        }
        if ( !v35 )
          return (unsigned int)-1073741687;
        v39 = *(unsigned int *)(v35 + 12);
        v40 = 0;
        v50 = 0;
        v57 = 0;
        v41 = (_DWORD *)(v48 + *(unsigned __int16 *)(v48 + 20) + 24LL);
        v57 = v41;
        v42 = *(unsigned __int16 *)(v48 + 6);
        while ( 1 )
        {
          v50 = v40;
          if ( v40 >= v42 )
            break;
          v43 = v41[3];
          if ( (unsigned int)v39 >= v43 && (unsigned int)v39 < v41[4] + v43 )
          {
            if ( v41 )
            {
              v44 = v39 + v5 + (unsigned int)v41[5] - (unsigned __int64)(unsigned int)v41[3];
              goto LABEL_83;
            }
            break;
          }
          v41 += 10;
          v57 = v41;
          ++v40;
        }
        v44 = 0;
LABEL_83:
        v18 += v47 + *(unsigned int *)(v35 + 12) - v34 - v44;
        v13 = 0;
      }
      goto LABEL_40;
    }
    return (unsigned int)-1073741687;
  }
  v18 = 0;
LABEL_40:
  if ( !a3 )
    goto LABEL_46;
  v24 = v5 + *a2 - v18;
  if ( v24 >= v8 )
  {
    v25 = v24 + a2[1];
    if ( v25 >= v24 && (!FileSizeFromLoadAsDataTable || v25 <= v8 + FileSizeFromLoadAsDataTable) )
    {
      *a3 = v24;
LABEL_46:
      if ( a4 )
        *a4 = a2[1];
      return (unsigned int)v13;
    }
  }
  return (unsigned int)-1073741701;
}

```

## disassembly

```asm
0x1800559c0  mov     [rsp+arg_0], rbx
0x1800559c5  mov     [rsp+arg_8], rsi
0x1800559ca  mov     [rsp+arg_18], r9
0x1800559cf  mov     [rsp+arg_10], r8
0x1800559d4  push    rdi
0x1800559d5  push    r12
0x1800559d7  push    r13
0x1800559d9  push    r14
0x1800559db  push    r15
0x1800559dd  sub     rsp, 0F0h
0x1800559e4  mov     r13, rdx
0x1800559e7  mov     r14, rcx
0x1800559ea  xor     ecx, ecx
0x1800559ec  mov     [rsp+118h+var_C8], rcx
0x1800559f1  mov     dil, 1
0x1800559f4  mov     [rsp+118h+var_E8], dil
0x1800559f9  mov     rbx, r14
0x1800559fc  mov     [rsp+118h+var_68], rbx
0x180055a04  mov     [rsp+118h+var_98], rcx
0x180055a0c  mov     [rsp+118h+var_D8], rcx
0x180055a11  mov     [rsp+118h+var_C8], rcx
0x180055a16  mov     r12, r14
0x180055a19  and     r12d, 2
0x180055a1d  mov     rsi, r14
0x180055a20  and     esi, 1
0x180055a23  test    r12, r12
0x180055a26  jnz     loc_180056030
0x180055a2c  test    rsi, rsi
0x180055a2f  jnz     loc_180056030
0x180055a35  mov     r15, r14
0x180055a38  and     r15, 0FFFFFFFFFFFFFFFCh
0x180055a3c  lea     r9, [rsp+118h+var_98]
0x180055a44  xor     r8d, r8d
0x180055a47  mov     rdx, rbx
0x180055a4a  mov     ecx, 1
0x180055a4f  call    RtlImageNtHeaderEx
0x180055a54  mov     edx, eax
0x180055a56  mov     r9, [rsp+118h+var_98]
0x180055a5e  test    r9, r9
0x180055a61  jz      short loc_180055AB9
0x180055a63  movzx   eax, word ptr [r9+18h]
0x180055a68  mov     ecx, 10Bh
0x180055a6d  cmp     ax, cx
0x180055a70  jz      loc_180055D36
0x180055a76  mov     ecx, 20Bh
0x180055a7b  cmp     ax, cx
0x180055a7e  jnz     loc_180055EEC
0x180055a84  cmp     dword ptr [r9+84h], 2
0x180055a8c  jbe     loc_180055EEC
0x180055a92  mov     eax, [r9+98h]
0x180055a99  test    eax, eax
0x180055a9b  jz      loc_180055F48
0x180055aa1  test    dil, dil
0x180055aa4  jz      loc_180055F5F
0x180055aaa  add     rax, rbx
0x180055aad  mov     [rsp+118h+var_D8], rax
0x180055ab2  mov     [rsp+118h+var_C8], rax
0x180055ab7  xor     edx, edx
0x180055ab9  mov     rax, [rsp+118h+var_D8]
0x180055abe  test    edx, edx
0x180055ac0  js      loc_18005601E
0x180055ac6  test    rax, rax
0x180055ac9  jz      loc_180056027
0x180055acf  xor     eax, eax
0x180055ad1  mov     [rsp+118h+var_D0], eax
0x180055ad5  mov     [rsp+118h+var_C0], rax
0x180055ada  mov     ebx, eax
0x180055adc  mov     [rsp+118h+var_D0], eax
0x180055ae0  mov     edi, eax
0x180055ae2  mov     [rsp+118h+var_C0], rax
0x180055ae7  mov     [rsp+118h+var_88], rax
0x180055aef  lea     r9, [rsp+118h+var_88]
0x180055af7  xor     r8d, r8d
0x180055afa  mov     rdx, r15
0x180055afd  mov     ecx, 1
0x180055b02  call    RtlImageNtHeaderEx
0x180055b07  mov     rax, [rsp+118h+var_88]
0x180055b0f  test    rax, rax
0x180055b12  jz      loc_180055FCB
0x180055b18  test    rsi, rsi
0x180055b1b  jz      loc_180055DF8
0x180055b21  mov     rcx, r14
0x180055b24  call    LdrpGetFileSizeFromLoadAsDataTable
0x180055b29  mov     rdi, rax
0x180055b2c  mov     [rsp+118h+var_C0], rax
0x180055b31  test    rax, rax
0x180055b34  jnz     short loc_180055B97
0x180055b36  xorps   xmm0, xmm0
0x180055b39  movups  [rsp+118h+var_60], xmm0
0x180055b41  movups  [rsp+118h+var_50], xmm0
0x180055b49  movups  [rsp+118h+var_40], xmm0
0x180055b51  mov     [rsp+118h+var_F0], rbx
0x180055b56  mov     [rsp+118h+var_F8], 30h ; '0'
0x180055b5f  lea     r9, [rsp+118h+var_60]
0x180055b67  mov     r8d, 3
0x180055b6d  mov     rdx, r15
0x180055b70  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180055b77  call    ZwQueryVirtualMemory
0x180055b7c  mov     ebx, eax
0x180055b7e  mov     [rsp+118h+var_D0], eax
0x180055b82  test    eax, eax
0x180055b84  js      loc_180056010
0x180055b8a  mov     rdi, qword ptr [rsp+118h+var_50]
0x180055b92  mov     [rsp+118h+var_C0], rdi
0x180055b97  mov     [rsp+118h+var_E0], ebx
0x180055b9b  test    ebx, ebx
0x180055b9d  js      loc_18005602E
0x180055ba3  cmp     r13, r15
0x180055ba6  jb      loc_180056056
0x180055bac  lea     rcx, [r13+10h]
0x180055bb0  cmp     rcx, r13
0x180055bb3  jb      loc_180056056
0x180055bb9  test    rdi, rdi
0x180055bbc  jz      short loc_180055BCB
0x180055bbe  lea     rax, [r15+rdi]
0x180055bc2  cmp     rcx, rax
0x180055bc5  ja      loc_180056056
0x180055bcb  xor     ebx, ebx
0x180055bcd  mov     eax, ebx
0x180055bcf  mov     [rsp+118h+var_A0], ebx
0x180055bd3  test    r12, r12
0x180055bd6  jz      loc_180055D15
0x180055bdc  test    rsi, rsi
0x180055bdf  mov     ecx, 1
0x180055be4  cmovnz  eax, ecx
0x180055be7  mov     [rsp+118h+var_A0], eax
0x180055beb  mov     r14, r15
0x180055bee  cmp     eax, 1
0x180055bf1  jnz     loc_180055F26
0x180055bf7  mov     [rsp+118h+var_B8], rbx
0x180055bfc  lea     r9, [rsp+118h+var_B8]
0x180055c01  xor     r8d, r8d
0x180055c04  mov     rdx, r14
0x180055c07  call    RtlImageNtHeaderEx
0x180055c0c  mov     r11, [rsp+118h+var_B8]
0x180055c11  test    r11, r11
0x180055c14  jz      loc_180055FE7
0x180055c1a  movzx   eax, word ptr [r11+18h]
0x180055c1f  mov     ecx, 10Bh
0x180055c24  cmp     ax, cx
0x180055c27  jnz     loc_180055F2E
0x180055c2d  mov     r8d, [r11+88h]
0x180055c34  test    r8d, r8d
0x180055c37  jz      loc_180055FD9
0x180055c3d  mov     esi, r8d
0x180055c40  mov     r12, [rsp+118h+var_D8]
0x180055c45  sub     rsi, r12
0x180055c48  add     rsi, r14
0x180055c4b  mov     [rsp+118h+var_A4], ebx
0x180055c4f  mov     [rsp+118h+var_70], rbx
0x180055c57  movzx   eax, word ptr [r11+14h]
0x180055c5c  add     rax, 18h
0x180055c60  add     rax, r11
0x180055c63  mov     [rsp+118h+var_70], rax
0x180055c6b  movzx   r10d, word ptr [r11+6]
0x180055c70  mov     r9d, ebx
0x180055c73  mov     [rsp+118h+var_A4], ebx
0x180055c77  cmp     r9d, r10d
0x180055c7a  jnb     loc_180055D28
0x180055c80  mov     edx, [rax+0Ch]
0x180055c83  cmp     r8d, edx
0x180055c86  jb      short loc_180055C90
0x180055c88  add     edx, [rax+10h]
0x180055c8b  cmp     r8d, edx
0x180055c8e  jb      short loc_180055CA6
0x180055c90  add     rax, 28h ; '('
0x180055c94  mov     [rsp+118h+var_70], rax
0x180055c9c  inc     r9d
0x180055c9f  mov     [rsp+118h+var_A4], r9d
0x180055ca4  jmp     short loc_180055C77
0x180055ca6  test    rax, rax
0x180055ca9  jz      short loc_180055D28
0x180055cab  mov     edx, [r13+0]
0x180055caf  cmp     edx, [rax+8]
0x180055cb2  ja      loc_180055E25
0x180055cb8  mov     r8, [rsp+118h+arg_10]
0x180055cc0  test    r8, r8
0x180055cc3  jz      short loc_180055CFD
0x180055cc5  mov     ecx, [r13+0]
0x180055cc9  sub     rcx, rsi
0x180055ccc  add     rcx, r14
0x180055ccf  cmp     rcx, r15
0x180055cd2  jb      loc_180055FA3
0x180055cd8  mov     edx, [r13+4]
0x180055cdc  add     rdx, rcx
0x180055cdf  cmp     rdx, rcx
0x180055ce2  jb      loc_180055FA3
0x180055ce8  test    rdi, rdi
0x180055ceb  jz      short loc_180055CFA
0x180055ced  lea     rax, [r15+rdi]
0x180055cf1  cmp     rdx, rax
0x180055cf4  ja      loc_180055FA3
0x180055cfa  mov     [r8], rcx
0x180055cfd  mov     rcx, [rsp+118h+arg_18]
0x180055d05  test    rcx, rcx
0x180055d08  jz      short loc_180055D10
0x180055d0a  mov     eax, [r13+4]
0x180055d0e  mov     [rcx], eax
0x180055d10  jmp     loc_180056067
0x180055d15  test    rsi, rsi
0x180055d18  jnz     loc_180055BDC
0x180055d1e  mov     ecx, 1
0x180055d23  jmp     loc_180055BEE
0x180055d28  mov     ebx, 0C0000089h
0x180055d2d  mov     [rsp+118h+var_E0], ebx
0x180055d31  jmp     loc_180056067
0x180055d36  cmp     dword ptr [r9+74h], 2
0x180055d3b  jbe     loc_180055EEC
0x180055d41  mov     r10d, [r9+88h]
0x180055d48  test    r10d, r10d
0x180055d4b  jz      loc_180055FFF
0x180055d51  test    dil, dil
0x180055d54  jnz     loc_180055FB1
0x180055d5a  cmp     r10d, [r9+54h]
0x180055d5e  jb      loc_180055FB1
0x180055d64  xor     edi, edi
0x180055d66  mov     [rsp+118h+var_B0], edi
0x180055d6a  mov     [rsp+118h+var_90], rdi
0x180055d72  movzx   edx, word ptr [r9+14h]
0x180055d77  add     rdx, 18h
0x180055d7b  add     rdx, r9
0x180055d7e  mov     [rsp+118h+var_90], rdx
0x180055d86  movzx   r11d, word ptr [r9+6]
0x180055d8b  mov     r8d, edi
0x180055d8e  mov     [rsp+118h+var_B0], edi
0x180055d92  cmp     r8d, r11d
0x180055d95  jnb     loc_180055FF2
0x180055d9b  mov     ecx, [rdx+0Ch]
0x180055d9e  cmp     r10d, ecx
0x180055da1  jb      short loc_180055DAB
0x180055da3  add     ecx, [rdx+10h]
0x180055da6  cmp     r10d, ecx
0x180055da9  jb      short loc_180055DC1
0x180055dab  add     rdx, 28h ; '('
0x180055daf  mov     [rsp+118h+var_90], rdx
0x180055db7  inc     r8d
0x180055dba  mov     [rsp+118h+var_B0], r8d
0x180055dbf  jmp     short loc_180055D92
0x180055dc1  test    rdx, rdx
0x180055dc4  jz      loc_180055FF2
0x180055dca  mov     r8d, [rdx+14h]
0x180055dce  mov     eax, [rdx+0Ch]
0x180055dd1  sub     r8, rax
0x180055dd4  add     r8, rbx
0x180055dd7  add     r8, r10
0x180055dda  mov     [rsp+118h+var_D8], r8
0x180055ddf  mov     [rsp+118h+var_C8], r8
0x180055de4  mov     eax, edi
0x180055de6  mov     edx, 0C000000Dh
0x180055deb  test    r8, r8
0x180055dee  cmovz   eax, edx
0x180055df1  mov     edx, eax
0x180055df3  jmp     loc_180055AB9
0x180055df8  movzx   ecx, word ptr [rax+18h]
0x180055dfc  mov     edx, 10Bh
0x180055e01  cmp     cx, dx
0x180055e04  jz      loc_180055F52
0x180055e0a  mov     edx, 20Bh
0x180055e0f  cmp     cx, dx
0x180055e12  jnz     loc_180055FC6
0x180055e18  mov     edi, [rax+50h]
0x180055e1b  mov     [rsp+118h+var_C0], rdi
0x180055e20  jmp     loc_180055B97
0x180055e25  mov     ebx, [rax+0Ch]
0x180055e28  mov     [rsp+118h+var_A8], 0
0x180055e30  mov     [rsp+118h+var_78], 0
0x180055e3c  movzx   r8d, word ptr [r11+14h]
0x180055e41  add     r8, 18h
0x180055e45  add     r8, r11
0x180055e48  mov     [rsp+118h+var_78], r8
0x180055e50  movzx   r10d, word ptr [r11+6]
0x180055e55  xor     r9d, r9d
0x180055e58  mov     [rsp+118h+var_A8], r9d
0x180055e5d  cmp     r9d, r10d
0x180055e60  jnb     loc_180055F95
0x180055e66  mov     ecx, [r8+0Ch]
0x180055e6a  cmp     edx, ecx
0x180055e6c  jb      short loc_180055E76
0x180055e6e  add     ecx, [r8+10h]
0x180055e72  cmp     edx, ecx
0x180055e74  jb      short loc_180055E87
0x180055e76  add     r8, 28h ; '('
0x180055e7a  mov     [rsp+118h+var_78], r8
0x180055e82  inc     r9d
0x180055e85  jmp     short loc_180055E58
0x180055e87  test    r8, r8
0x180055e8a  jz      loc_180055F95
0x180055e90  mov     r10d, [r8+0Ch]
0x180055e94  xor     r9d, r9d
0x180055e97  mov     [rsp+118h+var_AC], r9d
0x180055e9c  mov     [rsp+118h+var_80], r9
0x180055ea4  movzx   edx, word ptr [r11+14h]
0x180055ea9  add     rdx, 18h
0x180055ead  add     rdx, r11
0x180055eb0  mov     [rsp+118h+var_80], rdx
0x180055eb8  movzx   r11d, word ptr [r11+6]
0x180055ebd  mov     [rsp+118h+var_AC], r9d
0x180055ec2  cmp     r9d, r11d
0x180055ec5  jnb     loc_180056009
0x180055ecb  mov     ecx, [rdx+0Ch]
  ... truncated ...
```
