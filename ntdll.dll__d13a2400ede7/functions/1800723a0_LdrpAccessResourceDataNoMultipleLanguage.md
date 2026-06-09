# LdrpAccessResourceDataNoMultipleLanguage

- ea: `0x1800723a0`
- end: `0x180072a67`
- name: `LdrpAccessResourceDataNoMultipleLanguage`
- size: `1735`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800731e0`
- `0x180073750`
- `0x1800738a0`
- `0x180074140`
- `0x1800743b0`
- `0x1800ab160`
- `0x1800fb630`

## callees

- `0x18001f070`
- `0x1800723a0`
- `0x180072a70`
- `0x180084a90`
- `0x18015ef40`

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
0x1800723a0  mov     [rsp+arg_0], rbx
0x1800723a5  mov     [rsp+arg_8], rsi
0x1800723aa  mov     [rsp+arg_18], r9
0x1800723af  mov     [rsp+arg_10], r8
0x1800723b4  push    rdi
0x1800723b5  push    r12
0x1800723b7  push    r13
0x1800723b9  push    r14
0x1800723bb  push    r15
0x1800723bd  sub     rsp, 0F0h
0x1800723c4  mov     r13, rdx
0x1800723c7  mov     r14, rcx
0x1800723ca  xor     ecx, ecx
0x1800723cc  mov     [rsp+118h+var_C8], rcx
0x1800723d1  mov     dil, 1
0x1800723d4  mov     [rsp+118h+var_E8], dil
0x1800723d9  mov     rbx, r14
0x1800723dc  mov     [rsp+118h+var_68], rbx
0x1800723e4  mov     [rsp+118h+var_98], rcx
0x1800723ec  mov     [rsp+118h+var_D8], rcx
0x1800723f1  mov     [rsp+118h+var_C8], rcx
0x1800723f6  mov     r12, r14
0x1800723f9  and     r12d, 2
0x1800723fd  mov     rsi, r14
0x180072400  and     esi, 1
0x180072403  test    r12, r12
0x180072406  jnz     loc_180072A10
0x18007240c  test    rsi, rsi
0x18007240f  jnz     loc_180072A10
0x180072415  mov     r15, r14
0x180072418  and     r15, 0FFFFFFFFFFFFFFFCh
0x18007241c  lea     r9, [rsp+118h+var_98]
0x180072424  xor     r8d, r8d
0x180072427  mov     rdx, rbx
0x18007242a  mov     ecx, 1
0x18007242f  call    RtlImageNtHeaderEx
0x180072434  mov     edx, eax
0x180072436  mov     r9, [rsp+118h+var_98]
0x18007243e  test    r9, r9
0x180072441  jz      short loc_180072499
0x180072443  movzx   eax, word ptr [r9+18h]
0x180072448  mov     ecx, 10Bh
0x18007244d  cmp     ax, cx
0x180072450  jz      loc_180072716
0x180072456  mov     ecx, 20Bh
0x18007245b  cmp     ax, cx
0x18007245e  jnz     loc_1800728CC
0x180072464  cmp     dword ptr [r9+84h], 2
0x18007246c  jbe     loc_1800728CC
0x180072472  mov     eax, [r9+98h]
0x180072479  test    eax, eax
0x18007247b  jz      loc_180072928
0x180072481  test    dil, dil
0x180072484  jz      loc_18007293F
0x18007248a  add     rax, rbx
0x18007248d  mov     [rsp+118h+var_D8], rax
0x180072492  mov     [rsp+118h+var_C8], rax
0x180072497  xor     edx, edx
0x180072499  mov     rax, [rsp+118h+var_D8]
0x18007249e  test    edx, edx
0x1800724a0  js      loc_1800729FE
0x1800724a6  test    rax, rax
0x1800724a9  jz      loc_180072A07
0x1800724af  xor     eax, eax
0x1800724b1  mov     [rsp+118h+var_D0], eax
0x1800724b5  mov     [rsp+118h+var_C0], rax
0x1800724ba  mov     ebx, eax
0x1800724bc  mov     [rsp+118h+var_D0], eax
0x1800724c0  mov     edi, eax
0x1800724c2  mov     [rsp+118h+var_C0], rax
0x1800724c7  mov     [rsp+118h+var_88], rax
0x1800724cf  lea     r9, [rsp+118h+var_88]
0x1800724d7  xor     r8d, r8d
0x1800724da  mov     rdx, r15
0x1800724dd  mov     ecx, 1
0x1800724e2  call    RtlImageNtHeaderEx
0x1800724e7  mov     rax, [rsp+118h+var_88]
0x1800724ef  test    rax, rax
0x1800724f2  jz      loc_1800729AB
0x1800724f8  test    rsi, rsi
0x1800724fb  jz      loc_1800727D8
0x180072501  mov     rcx, r14
0x180072504  call    LdrpGetFileSizeFromLoadAsDataTable
0x180072509  mov     rdi, rax
0x18007250c  mov     [rsp+118h+var_C0], rax
0x180072511  test    rax, rax
0x180072514  jnz     short loc_180072577
0x180072516  xorps   xmm0, xmm0
0x180072519  movups  [rsp+118h+var_60], xmm0
0x180072521  movups  [rsp+118h+var_50], xmm0
0x180072529  movups  [rsp+118h+var_40], xmm0
0x180072531  mov     [rsp+118h+var_F0], rbx
0x180072536  mov     [rsp+118h+var_F8], 30h ; '0'
0x18007253f  lea     r9, [rsp+118h+var_60]
0x180072547  mov     r8d, 3
0x18007254d  mov     rdx, r15
0x180072550  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180072557  call    ZwQueryVirtualMemory
0x18007255c  mov     ebx, eax
0x18007255e  mov     [rsp+118h+var_D0], eax
0x180072562  test    eax, eax
0x180072564  js      loc_1800729F0
0x18007256a  mov     rdi, qword ptr [rsp+118h+var_50]
0x180072572  mov     [rsp+118h+var_C0], rdi
0x180072577  mov     [rsp+118h+var_E0], ebx
0x18007257b  test    ebx, ebx
0x18007257d  js      loc_180072A0E
0x180072583  cmp     r13, r15
0x180072586  jb      loc_180072A36
0x18007258c  lea     rcx, [r13+10h]
0x180072590  cmp     rcx, r13
0x180072593  jb      loc_180072A36
0x180072599  test    rdi, rdi
0x18007259c  jz      short loc_1800725AB
0x18007259e  lea     rax, [r15+rdi]
0x1800725a2  cmp     rcx, rax
0x1800725a5  ja      loc_180072A36
0x1800725ab  xor     ebx, ebx
0x1800725ad  mov     eax, ebx
0x1800725af  mov     [rsp+118h+var_A0], ebx
0x1800725b3  test    r12, r12
0x1800725b6  jz      loc_1800726F5
0x1800725bc  test    rsi, rsi
0x1800725bf  mov     ecx, 1
0x1800725c4  cmovnz  eax, ecx
0x1800725c7  mov     [rsp+118h+var_A0], eax
0x1800725cb  mov     r14, r15
0x1800725ce  cmp     eax, 1
0x1800725d1  jnz     loc_180072906
0x1800725d7  mov     [rsp+118h+var_B8], rbx
0x1800725dc  lea     r9, [rsp+118h+var_B8]
0x1800725e1  xor     r8d, r8d
0x1800725e4  mov     rdx, r14
0x1800725e7  call    RtlImageNtHeaderEx
0x1800725ec  mov     r11, [rsp+118h+var_B8]
0x1800725f1  test    r11, r11
0x1800725f4  jz      loc_1800729C7
0x1800725fa  movzx   eax, word ptr [r11+18h]
0x1800725ff  mov     ecx, 10Bh
0x180072604  cmp     ax, cx
0x180072607  jnz     loc_18007290E
0x18007260d  mov     r8d, [r11+88h]
0x180072614  test    r8d, r8d
0x180072617  jz      loc_1800729B9
0x18007261d  mov     esi, r8d
0x180072620  mov     r12, [rsp+118h+var_D8]
0x180072625  sub     rsi, r12
0x180072628  add     rsi, r14
0x18007262b  mov     [rsp+118h+var_A4], ebx
0x18007262f  mov     [rsp+118h+var_70], rbx
0x180072637  movzx   eax, word ptr [r11+14h]
0x18007263c  add     rax, 18h
0x180072640  add     rax, r11
0x180072643  mov     [rsp+118h+var_70], rax
0x18007264b  movzx   r10d, word ptr [r11+6]
0x180072650  mov     r9d, ebx
0x180072653  mov     [rsp+118h+var_A4], ebx
0x180072657  cmp     r9d, r10d
0x18007265a  jnb     loc_180072708
0x180072660  mov     edx, [rax+0Ch]
0x180072663  cmp     r8d, edx
0x180072666  jb      short loc_180072670
0x180072668  add     edx, [rax+10h]
0x18007266b  cmp     r8d, edx
0x18007266e  jb      short loc_180072686
0x180072670  add     rax, 28h ; '('
0x180072674  mov     [rsp+118h+var_70], rax
0x18007267c  inc     r9d
0x18007267f  mov     [rsp+118h+var_A4], r9d
0x180072684  jmp     short loc_180072657
0x180072686  test    rax, rax
0x180072689  jz      short loc_180072708
0x18007268b  mov     edx, [r13+0]
0x18007268f  cmp     edx, [rax+8]
0x180072692  ja      loc_180072805
0x180072698  mov     r8, [rsp+118h+arg_10]
0x1800726a0  test    r8, r8
0x1800726a3  jz      short loc_1800726DD
0x1800726a5  mov     ecx, [r13+0]
0x1800726a9  sub     rcx, rsi
0x1800726ac  add     rcx, r14
0x1800726af  cmp     rcx, r15
0x1800726b2  jb      loc_180072983
0x1800726b8  mov     edx, [r13+4]
0x1800726bc  add     rdx, rcx
0x1800726bf  cmp     rdx, rcx
0x1800726c2  jb      loc_180072983
0x1800726c8  test    rdi, rdi
0x1800726cb  jz      short loc_1800726DA
0x1800726cd  lea     rax, [r15+rdi]
0x1800726d1  cmp     rdx, rax
0x1800726d4  ja      loc_180072983
0x1800726da  mov     [r8], rcx
0x1800726dd  mov     rcx, [rsp+118h+arg_18]
0x1800726e5  test    rcx, rcx
0x1800726e8  jz      short loc_1800726F0
0x1800726ea  mov     eax, [r13+4]
0x1800726ee  mov     [rcx], eax
0x1800726f0  jmp     loc_180072A47
0x1800726f5  test    rsi, rsi
0x1800726f8  jnz     loc_1800725BC
0x1800726fe  mov     ecx, 1
0x180072703  jmp     loc_1800725CE
0x180072708  mov     ebx, 0C0000089h
0x18007270d  mov     [rsp+118h+var_E0], ebx
0x180072711  jmp     loc_180072A47
0x180072716  cmp     dword ptr [r9+74h], 2
0x18007271b  jbe     loc_1800728CC
0x180072721  mov     r10d, [r9+88h]
0x180072728  test    r10d, r10d
0x18007272b  jz      loc_1800729DF
0x180072731  test    dil, dil
0x180072734  jnz     loc_180072991
0x18007273a  cmp     r10d, [r9+54h]
0x18007273e  jb      loc_180072991
0x180072744  xor     edi, edi
0x180072746  mov     [rsp+118h+var_B0], edi
0x18007274a  mov     [rsp+118h+var_90], rdi
0x180072752  movzx   edx, word ptr [r9+14h]
0x180072757  add     rdx, 18h
0x18007275b  add     rdx, r9
0x18007275e  mov     [rsp+118h+var_90], rdx
0x180072766  movzx   r11d, word ptr [r9+6]
0x18007276b  mov     r8d, edi
0x18007276e  mov     [rsp+118h+var_B0], edi
0x180072772  cmp     r8d, r11d
0x180072775  jnb     loc_1800729D2
0x18007277b  mov     ecx, [rdx+0Ch]
0x18007277e  cmp     r10d, ecx
0x180072781  jb      short loc_18007278B
0x180072783  add     ecx, [rdx+10h]
0x180072786  cmp     r10d, ecx
0x180072789  jb      short loc_1800727A1
0x18007278b  add     rdx, 28h ; '('
0x18007278f  mov     [rsp+118h+var_90], rdx
0x180072797  inc     r8d
0x18007279a  mov     [rsp+118h+var_B0], r8d
0x18007279f  jmp     short loc_180072772
0x1800727a1  test    rdx, rdx
0x1800727a4  jz      loc_1800729D2
0x1800727aa  mov     r8d, [rdx+14h]
0x1800727ae  mov     eax, [rdx+0Ch]
0x1800727b1  sub     r8, rax
0x1800727b4  add     r8, rbx
0x1800727b7  add     r8, r10
0x1800727ba  mov     [rsp+118h+var_D8], r8
0x1800727bf  mov     [rsp+118h+var_C8], r8
0x1800727c4  mov     eax, edi
0x1800727c6  mov     edx, 0C000000Dh
0x1800727cb  test    r8, r8
0x1800727ce  cmovz   eax, edx
0x1800727d1  mov     edx, eax
0x1800727d3  jmp     loc_180072499
0x1800727d8  movzx   ecx, word ptr [rax+18h]
0x1800727dc  mov     edx, 10Bh
0x1800727e1  cmp     cx, dx
0x1800727e4  jz      loc_180072932
0x1800727ea  mov     edx, 20Bh
0x1800727ef  cmp     cx, dx
0x1800727f2  jnz     loc_1800729A6
0x1800727f8  mov     edi, [rax+50h]
0x1800727fb  mov     [rsp+118h+var_C0], rdi
0x180072800  jmp     loc_180072577
0x180072805  mov     ebx, [rax+0Ch]
0x180072808  mov     [rsp+118h+var_A8], 0
0x180072810  mov     [rsp+118h+var_78], 0
0x18007281c  movzx   r8d, word ptr [r11+14h]
0x180072821  add     r8, 18h
0x180072825  add     r8, r11
0x180072828  mov     [rsp+118h+var_78], r8
0x180072830  movzx   r10d, word ptr [r11+6]
0x180072835  xor     r9d, r9d
0x180072838  mov     [rsp+118h+var_A8], r9d
0x18007283d  cmp     r9d, r10d
0x180072840  jnb     loc_180072975
0x180072846  mov     ecx, [r8+0Ch]
0x18007284a  cmp     edx, ecx
0x18007284c  jb      short loc_180072856
0x18007284e  add     ecx, [r8+10h]
0x180072852  cmp     edx, ecx
0x180072854  jb      short loc_180072867
0x180072856  add     r8, 28h ; '('
0x18007285a  mov     [rsp+118h+var_78], r8
0x180072862  inc     r9d
0x180072865  jmp     short loc_180072838
0x180072867  test    r8, r8
0x18007286a  jz      loc_180072975
0x180072870  mov     r10d, [r8+0Ch]
0x180072874  xor     r9d, r9d
0x180072877  mov     [rsp+118h+var_AC], r9d
0x18007287c  mov     [rsp+118h+var_80], r9
0x180072884  movzx   edx, word ptr [r11+14h]
0x180072889  add     rdx, 18h
0x18007288d  add     rdx, r11
0x180072890  mov     [rsp+118h+var_80], rdx
0x180072898  movzx   r11d, word ptr [r11+6]
0x18007289d  mov     [rsp+118h+var_AC], r9d
0x1800728a2  cmp     r9d, r11d
0x1800728a5  jnb     loc_1800729E9
0x1800728ab  mov     ecx, [rdx+0Ch]
  ... truncated ...
```
