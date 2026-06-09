# WriteNameRecords

- ea: `0x18000f364`
- end: `0x18000f863`
- name: `WriteNameRecords`
- size: `1279`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800105d0`

## callees

- `0x18000f364`
- `0x180011538`
- `0x180011574`
- `0x18001a2cc`
- `0x18001a7b8`
- `0x18001a808`
- `0x18001abd6`

## import_xrefs

- `msvcrt!qsort` at `0x18000f3c5`
- `msvcrt!qsort` at `0x18000f4bb`
- `msvcrt!qsort` at `0x18000f628`
- `msvcrt!qsort` at `0x18000f3c5`
- `msvcrt!qsort` at `0x18000f4bb`
- `msvcrt!qsort` at `0x18000f628`

## pseudocode

```c
__int64 __fastcall WriteNameRecords(__int64 a1, char *a2, unsigned __int16 a3, int a4, unsigned __int16 a5, _DWORD *a6)
{
  __int64 v6; // rsi
  __int64 v9; // r13
  unsigned int GenericSize; // ebp
  _WORD *v11; // rbx
  unsigned __int16 v13; // r15
  unsigned __int16 v14; // dx
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned __int16 v17; // si
  __int16 v18; // r14
  unsigned __int16 v19; // r12
  __int64 v20; // rax
  void *v21; // r9
  __int64 v22; // rax
  const void *v23; // rdx
  unsigned __int16 v24; // cx
  unsigned __int16 v25; // r14
  __int64 v26; // r9
  unsigned __int16 v27; // si
  unsigned __int16 v28; // r13
  int v29; // ebp
  char *v30; // r12
  unsigned __int16 v31; // si
  __int64 v32; // rcx
  __int64 v33; // r14
  char *v34; // r13
  __int64 v35; // rax
  __int64 v36; // rbp
  __int64 v37; // rdx
  int v38; // esi
  __int16 v39; // cx
  __int64 v40; // rdx
  unsigned __int16 v41; // [rsp+30h] [rbp-68h]
  unsigned int v42; // [rsp+34h] [rbp-64h]
  int v43; // [rsp+38h] [rbp-60h]
  __int16 v44; // [rsp+3Ch] [rbp-5Ch] BYREF
  int v45; // [rsp+3Eh] [rbp-5Ah]
  void *Buf1; // [rsp+48h] [rbp-50h]
  __int64 v47; // [rsp+50h] [rbp-48h]
  __int64 v48; // [rsp+58h] [rbp-40h]
  int v50; // [rsp+A8h] [rbp+10h]

  v6 = a3;
  v45 = 0;
  a5 = 0;
  v9 = a1;
  *a6 = 0;
  if ( !a2 || !a3 )
    return 1000;
  qsort(a2, a3, 0x28u, AscendingNameRecordCompare);
  v44 = 0;
  GenericSize = (unsigned __int16)GetGenericSize(&NAME_HEADER_CONTROL);
  v11 = (_WORD *)Mem_Alloc(8 * v6);
  if ( !v11 )
    return 1005;
  v42 = GenericSize;
  v13 = 0;
  v14 = 0;
  do
  {
    v15 = 40LL * v14;
    if ( !a4 || !*(_DWORD *)&a2[v15 + 32] )
    {
      v16 = v13++;
      v11[4 * v16] = v14;
      v11[4 * v16 + 1] = *(_WORD *)&a2[v15 + 8];
      v11[4 * v16 + 2] = v14;
      v11[4 * v16 + 3] = 0;
      *(_WORD *)&a2[v15 + 10] = 0;
    }
    ++v14;
  }
  while ( v14 < (unsigned __int16)v6 );
  v50 = 0;
  v17 = 0;
  v18 = v13 * GetGenericSize(&NAME_RECORD_CONTROL);
  v41 = GetGenericSize(&NAME_HEADER_CONTROL) + v18;
  HIWORD(v45) = v41;
  if ( v13 )
  {
    qsort(v11, v13, 8u, DescendingStringLengthCompare);
    v19 = 1;
    if ( v13 > 1u )
    {
      while ( 1 )
      {
        v20 = (unsigned __int16)v11[4 * v19];
        v21 = *(void **)&a2[40 * v20 + 24];
        Buf1 = v21;
        if ( !v21 )
        {
          v21 = *(void **)&a2[40 * v20 + 16];
          Buf1 = v21;
        }
        v22 = (unsigned __int16)v11[4 * v19 - 4];
        v23 = *(const void **)&a2[40 * v22 + 24];
        if ( !v23 )
          v23 = *(const void **)&a2[40 * v22 + 16];
        v24 = v11[4 * v19 + 1];
        if ( v24 != v11[4 * v19 - 3] )
          goto LABEL_20;
        if ( memcmp_0(v21, v23, (unsigned __int16)v11[4 * v19 + 1]) )
          break;
        v11[4 * v19 + 2] = v11[4 * v19 - 2];
        v11[4 * v19 + 3] = v11[4 * v19 - 1];
LABEL_31:
        if ( ++v19 >= v13 )
        {
          v17 = 0;
          goto LABEL_33;
        }
      }
      v24 = v11[4 * v19 + 1];
LABEL_20:
      if ( v19 - 1 > 0 )
      {
        v25 = 0;
        while ( 2 )
        {
          v48 = (unsigned __int16)v11[4 * v25 + 2];
          v26 = *(_QWORD *)&a2[40 * v48 + 24];
          v47 = v26;
          if ( !v26 )
          {
            v26 = *(_QWORD *)&a2[40 * v48 + 16];
            v47 = v26;
          }
          v27 = 0;
          v28 = v11[4 * v25 + 1] - v24;
          while ( v27 <= v28 )
          {
            if ( !memcmp_0(Buf1, (const void *)(v26 + v27), v24) )
            {
              v11[4 * v19 + 2] = v48;
              v11[4 * v19 + 3] = v27;
              goto LABEL_31;
            }
            v24 = v11[4 * v19 + 1];
            v26 = v47;
            ++v27;
          }
          if ( ++v25 < v19 - 1 )
            continue;
          break;
        }
      }
      goto LABEL_31;
    }
LABEL_33:
    qsort(v11, v13, 8u, AscendingRecordIndexCompare);
    v43 = 0;
    v29 = 0;
    while ( 1 )
    {
      v32 = (unsigned __int16)v29;
      v48 = (unsigned __int16)v29;
      v33 = (unsigned __int16)v11[4 * (unsigned __int16)v29];
      v34 = &a2[40 * v33];
      if ( *((_WORD *)v34 + 6) )
      {
        LOWORD(v30) = v50;
      }
      else
      {
        if ( (_WORD)v33 == v11[4 * (unsigned __int16)v29 + 2] )
        {
          v40 = *((_QWORD *)v34 + 3);
          *((_WORD *)v34 + 5) = v11[4 * (unsigned __int16)v29 + 3] + v17;
          if ( !v40 )
            v40 = *((_QWORD *)v34 + 2);
          v31 = WriteBytes(a1, v40, v17 + (unsigned int)v41, *((unsigned __int16 *)v34 + 4));
          if ( v31 )
            goto LABEL_36;
          WORD1(v30) = HIWORD(v50);
          LOWORD(v30) = *((_WORD *)v34 + 4) + v50;
          v50 = (int)v30;
        }
        else
        {
          v35 = (unsigned __int16)v11[4 * (unsigned __int16)v29 + 2];
          v36 = 5 * v35;
          v30 = &a2[40 * v35];
          if ( !*((_WORD *)v30 + 6) )
          {
            v37 = *(_QWORD *)&a2[40 * v35 + 24];
            *((_WORD *)v30 + 5) = v17;
            *(_WORD *)&a2[40 * v35 + 12] = 1;
            if ( !v37 )
              v37 = *(_QWORD *)&a2[40 * v35 + 16];
            v31 = WriteBytes(a1, v37, v17 + (unsigned int)v41, *(unsigned __int16 *)&a2[40 * v35 + 8]);
            if ( v31 )
              goto LABEL_36;
            HIWORD(v38) = HIWORD(v50);
            LOWORD(v38) = *(_WORD *)&a2[8 * v36 + 8] + v50;
            v32 = v48;
            v50 = v38;
          }
          v39 = *((_WORD *)v30 + 5) + v11[4 * v32 + 3];
          v29 = v43;
          LOWORD(v30) = v50;
          *(_WORD *)&a2[40 * v33 + 10] = v39;
        }
        *(_WORD *)&a2[40 * v33 + 12] = 1;
      }
      v9 = a1;
      v31 = WriteGeneric(a1, (__int64)&a2[40 * v33], 0xCu, (unsigned __int8 *)&NAME_RECORD_CONTROL, v42, &a5);
      if ( v31 )
        goto LABEL_36;
      LOWORD(v29) = v29 + 1;
      v43 = v29;
      v42 += a5;
      if ( (unsigned __int16)v29 >= v13 )
        break;
      v17 = v50;
    }
  }
  else
  {
    LOWORD(v30) = 0;
  }
  LOWORD(v45) = v13;
  *a6 = (unsigned __int16)v30 + v41;
  v31 = WriteGeneric(v9, (__int64)&v44, 6u, (unsigned __int8 *)&NAME_HEADER_CONTROL, 0, &a5);
LABEL_36:
  Mem_Free(v11);
  return v31;
}

```

## disassembly

```asm
0x18000f364  mov     rax, rsp
0x18000f367  mov     [rax+18h], rbx
0x18000f36b  mov     [rax+8], rcx
0x18000f36f  push    rbp
0x18000f370  push    rsi
0x18000f371  push    rdi
0x18000f372  push    r12
0x18000f374  push    r13
0x18000f376  push    r14
0x18000f378  push    r15
0x18000f37a  sub     rsp, 60h
0x18000f37e  xor     r12d, r12d
0x18000f381  movzx   esi, r8w
0x18000f385  mov     [rax-5Ah], r12d
0x18000f389  mov     r14d, r9d
0x18000f38c  mov     [rax+28h], r12w
0x18000f391  mov     rdi, rdx
0x18000f394  mov     rax, [rsp+98h+arg_28]
0x18000f39c  mov     r13, rcx
0x18000f39f  mov     [rax], r12d
0x18000f3a2  test    rdx, rdx
0x18000f3a5  jz      loc_18000F846
0x18000f3ab  test    si, si
0x18000f3ae  jz      loc_18000F846
0x18000f3b4  lea     r9, AscendingNameRecordCompare; CompareFunction
0x18000f3bb  mov     edx, esi; NumOfElements
0x18000f3bd  lea     r8d, [r12+28h]; SizeOfElements
0x18000f3c2  mov     rcx, rdi; Base
0x18000f3c5  call    cs:__imp_qsort
0x18000f3cb  lea     rcx, NAME_HEADER_CONTROL
0x18000f3d2  mov     [rsp+98h+var_5C], r12w
0x18000f3d8  call    GetGenericSize
0x18000f3dd  lea     rcx, ds:0[rsi*8]; Size
0x18000f3e5  movzx   ebp, ax
0x18000f3e8  call    Mem_Alloc
0x18000f3ed  mov     rbx, rax
0x18000f3f0  test    rax, rax
0x18000f3f3  jnz     short loc_18000F3FF
0x18000f3f5  mov     eax, 3EDh
0x18000f3fa  jmp     loc_18000F84B
0x18000f3ff  mov     [rsp+98h+var_64], ebp
0x18000f403  mov     ebp, 1
0x18000f408  mov     r15d, r12d
0x18000f40b  mov     edx, r12d
0x18000f40e  cmp     r12w, si
0x18000f412  jnb     short loc_18000F45F
0x18000f414  movzx   eax, dx
0x18000f417  lea     rcx, [rax+rax*4]
0x18000f41b  lea     r8, ds:0[rcx*8]
0x18000f423  test    r14d, r14d
0x18000f426  jz      short loc_18000F42F
0x18000f428  cmp     [rdi+r8+20h], r12d
0x18000f42d  jnz     short loc_18000F457
0x18000f42f  movzx   ecx, r15w
0x18000f433  add     r15w, bp
0x18000f437  mov     [rbx+rcx*8], dx
0x18000f43b  movzx   eax, word ptr [r8+rdi+8]
0x18000f441  mov     [rbx+rcx*8+2], ax
0x18000f446  mov     [rbx+rcx*8+4], dx
0x18000f44b  mov     [rbx+rcx*8+6], r12w
0x18000f451  mov     [r8+rdi+0Ah], r12w
0x18000f457  add     dx, bp
0x18000f45a  cmp     dx, si
0x18000f45d  jb      short loc_18000F414
0x18000f45f  lea     rcx, NAME_RECORD_CONTROL
0x18000f466  mov     [rsp+98h+arg_8], r12d
0x18000f46e  mov     esi, r12d
0x18000f471  call    GetGenericSize
0x18000f476  movzx   ecx, r15w
0x18000f47a  movzx   r14d, ax
0x18000f47e  imul    r14d, ecx
0x18000f482  lea     rcx, NAME_HEADER_CONTROL
0x18000f489  call    GetGenericSize
0x18000f48e  add     r14w, ax
0x18000f492  mov     [rsp+98h+var_68], r14d
0x18000f497  mov     [rsp+98h+var_58], r14w
0x18000f49d  test    r15w, r15w
0x18000f4a1  jz      loc_18000F63F
0x18000f4a7  movzx   edx, r15w; NumOfElements
0x18000f4ab  lea     r9, DescendingStringLengthCompare; CompareFunction
0x18000f4b2  mov     r8d, 8; SizeOfElements
0x18000f4b8  mov     rcx, rbx; Base
0x18000f4bb  call    cs:__imp_qsort
0x18000f4c1  movzx   r12d, bp
0x18000f4c5  cmp     bp, r15w
0x18000f4c9  jnb     loc_18000F614
0x18000f4cf  xor     r8d, r8d
0x18000f4d2  movzx   ebp, r12w
0x18000f4d6  movzx   eax, word ptr [rbx+rbp*8]
0x18000f4da  lea     rcx, [rax+rax*4]
0x18000f4de  mov     r9, [rdi+rcx*8+18h]
0x18000f4e3  mov     [rsp+98h+Buf1], r9
0x18000f4e8  test    r9, r9
0x18000f4eb  jnz     short loc_18000F4F7
0x18000f4ed  mov     r9, [rdi+rcx*8+10h]
0x18000f4f2  mov     [rsp+98h+Buf1], r9
0x18000f4f7  movzx   r14d, r12w
0x18000f4fb  movzx   eax, word ptr [rbx+r14*8-8]
0x18000f501  lea     rcx, [rax+rax*4]
0x18000f505  mov     rdx, [rdi+rcx*8+18h]
0x18000f50a  test    rdx, rdx
0x18000f50d  jnz     short loc_18000F514
0x18000f50f  mov     rdx, [rdi+rcx*8+10h]; Buf2
0x18000f514  movzx   ecx, word ptr [rbx+rbp*8+2]
0x18000f519  cmp     cx, [rbx+r14*8-6]
0x18000f51f  jnz     short loc_18000F553
0x18000f521  mov     r8d, ecx; Size
0x18000f524  mov     rcx, r9; Buf1
0x18000f527  call    memcmp_0
0x18000f52c  xor     r8d, r8d
0x18000f52f  test    eax, eax
0x18000f531  jnz     short loc_18000F54E
0x18000f533  movzx   eax, word ptr [rbx+r14*8-4]
0x18000f539  mov     [rbx+rbp*8+4], ax
0x18000f53e  movzx   eax, word ptr [rbx+r14*8-2]
0x18000f544  mov     [rbx+rbp*8+6], ax
0x18000f549  jmp     loc_18000F5F7
0x18000f54e  movzx   ecx, word ptr [rbx+rbp*8+2]
0x18000f553  lea     edx, [r14-1]
0x18000f557  mov     [rsp+98h+var_60], edx
0x18000f55b  test    edx, edx
0x18000f55d  jle     loc_18000F5F7
0x18000f563  mov     r14d, r8d
0x18000f566  movzx   r13d, r14w
0x18000f56a  movzx   eax, word ptr [rbx+r13*8+4]
0x18000f570  mov     [rsp+98h+var_40], rax
0x18000f575  lea     rax, [rax+rax*4]
0x18000f579  mov     r9, [rdi+rax*8+18h]
0x18000f57e  mov     [rsp+98h+var_48], r9
0x18000f583  test    r9, r9
0x18000f586  jnz     short loc_18000F592
0x18000f588  mov     r9, [rdi+rax*8+10h]
0x18000f58d  mov     [rsp+98h+var_48], r9
0x18000f592  movzx   r13d, word ptr [rbx+r13*8+2]
0x18000f598  mov     esi, r8d
0x18000f59b  sub     r13w, cx
0x18000f59f  mov     eax, 1
0x18000f5a4  cmp     si, r13w
0x18000f5a8  ja      short loc_18000F5D8
0x18000f5aa  movzx   r8d, cx; Size
0x18000f5ae  mov     rcx, [rsp+98h+Buf1]; Buf1
0x18000f5b3  movzx   edx, si
0x18000f5b6  add     rdx, r9; Buf2
0x18000f5b9  call    memcmp_0
0x18000f5be  xor     r8d, r8d
0x18000f5c1  test    eax, eax
0x18000f5c3  jz      short loc_18000F5E8
0x18000f5c5  movzx   ecx, word ptr [rbx+rbp*8+2]
0x18000f5ca  lea     eax, [r8+1]
0x18000f5ce  mov     r9, [rsp+98h+var_48]
0x18000f5d3  add     si, ax
0x18000f5d6  jmp     short loc_18000F5A4
0x18000f5d8  add     r14w, ax
0x18000f5dc  movzx   eax, r14w
0x18000f5e0  cmp     eax, [rsp+98h+var_60]
0x18000f5e4  jl      short loc_18000F566
0x18000f5e6  jmp     short loc_18000F5F7
0x18000f5e8  mov     rax, [rsp+98h+var_40]
0x18000f5ed  mov     [rbx+rbp*8+4], ax
0x18000f5f2  mov     [rbx+rbp*8+6], si
0x18000f5f7  inc     r12w
0x18000f5fb  cmp     r12w, r15w
0x18000f5ff  jb      loc_18000F4D2
0x18000f605  mov     esi, [rsp+98h+arg_8]
0x18000f60c  mov     r13, [rsp+98h+arg_0]
0x18000f614  movzx   edx, r15w; NumOfElements
0x18000f618  lea     r9, AscendingRecordIndexCompare; CompareFunction
0x18000f61f  mov     r8d, 8; SizeOfElements
0x18000f625  mov     rcx, rbx; Base
0x18000f628  call    cs:__imp_qsort
0x18000f62e  xor     r8d, r8d
0x18000f631  mov     [rsp+98h+var_60], r8d
0x18000f636  mov     ebp, r8d
0x18000f639  cmp     r8w, r15w
0x18000f63d  jb      short loc_18000F6A9
0x18000f63f  mov     r12d, [rsp+98h+arg_8]
0x18000f647  movzx   ecx, word ptr [rsp+98h+var_68]
0x18000f64c  lea     r9, NAME_HEADER_CONTROL
0x18000f653  movzx   eax, r12w
0x18000f657  lea     rdx, [rsp+98h+var_5C]
0x18000f65c  add     ecx, eax
0x18000f65e  mov     [rsp+98h+var_5A], r15w
0x18000f664  mov     rax, [rsp+98h+arg_28]
0x18000f66c  mov     r8d, 6
0x18000f672  mov     [rax], ecx
0x18000f674  lea     rax, [rsp+98h+arg_20]
0x18000f67c  mov     [rsp+98h+var_70], rax
0x18000f681  mov     rcx, r13
0x18000f684  xor     eax, eax
0x18000f686  mov     [rsp+98h+var_78], eax
0x18000f68a  call    WriteGeneric
0x18000f68f  movzx   esi, ax
0x18000f692  mov     rcx, rbx
0x18000f695  call    Mem_Free
0x18000f69a  movzx   eax, si
0x18000f69d  jmp     loc_18000F84B
0x18000f6a2  mov     esi, [rsp+98h+arg_8]
0x18000f6a9  movzx   ecx, bp
0x18000f6ac  mov     [rsp+98h+var_40], rcx
0x18000f6b1  movzx   r14d, word ptr [rbx+rcx*8]
0x18000f6b6  lea     rax, [r14+r14*4]
0x18000f6ba  lea     r13, [rdi+rax*8]
0x18000f6be  cmp     [rdi+rax*8+0Ch], r8w
0x18000f6c4  jnz     loc_18000F7D2
0x18000f6ca  cmp     r14w, [rbx+rcx*8+4]
0x18000f6d0  jz      loc_18000F76C
0x18000f6d6  movzx   eax, word ptr [rbx+rcx*8+4]
0x18000f6db  lea     rbp, [rax+rax*4]
0x18000f6df  lea     r12, [rdi+rbp*8]
0x18000f6e3  cmp     [rdi+rbp*8+0Ch], r8w
0x18000f6e9  jnz     short loc_18000F74A
0x18000f6eb  mov     rdx, [rdi+rbp*8+18h]
0x18000f6f0  mov     [r12+0Ah], si
0x18000f6f6  mov     word ptr [rdi+rbp*8+0Ch], 1
0x18000f6fd  test    rdx, rdx
0x18000f700  jnz     short loc_18000F707
0x18000f702  mov     rdx, [rdi+rbp*8+10h]
0x18000f707  movzx   r8d, word ptr [rsp+98h+var_68]
0x18000f70d  movzx   r9d, word ptr [rdi+rbp*8+8]
0x18000f713  mov     rcx, [rsp+98h+arg_0]
0x18000f71b  movzx   eax, si
0x18000f71e  add     r8d, eax
0x18000f721  call    WriteBytes
0x18000f726  movzx   esi, ax
0x18000f729  test    ax, ax
0x18000f72c  jnz     loc_18000F692
0x18000f732  mov     esi, [rsp+98h+arg_8]
0x18000f739  add     si, [rdi+rbp*8+8]
0x18000f73e  mov     rcx, [rsp+98h+var_40]
0x18000f743  mov     [rsp+98h+arg_8], esi
0x18000f74a  movzx   ecx, word ptr [rbx+rcx*8+6]
0x18000f74f  lea     rax, [r14+r14*4]
0x18000f753  add     cx, [r12+0Ah]
0x18000f759  mov     ebp, [rsp+98h+var_60]
0x18000f75d  mov     r12d, [rsp+98h+arg_8]
0x18000f765  mov     [rdi+rax*8+0Ah], cx
0x18000f76a  jmp     short loc_18000F7C5
0x18000f76c  mov     rdx, [r13+18h]
0x18000f770  movzx   eax, si
0x18000f773  add     ax, [rbx+rcx*8+6]
0x18000f778  mov     [r13+0Ah], ax
0x18000f77d  test    rdx, rdx
0x18000f780  jnz     short loc_18000F786
0x18000f782  mov     rdx, [r13+10h]
0x18000f786  movzx   r8d, word ptr [rsp+98h+var_68]
0x18000f78c  movzx   r9d, word ptr [r13+8]
0x18000f791  mov     rcx, [rsp+98h+arg_0]
0x18000f799  movzx   eax, si
0x18000f79c  add     r8d, eax
0x18000f79f  call    WriteBytes
0x18000f7a4  movzx   esi, ax
0x18000f7a7  test    ax, ax
0x18000f7aa  jnz     loc_18000F692
0x18000f7b0  mov     r12d, [rsp+98h+arg_8]
0x18000f7b8  add     r12w, [r13+8]
0x18000f7bd  mov     [rsp+98h+arg_8], r12d
0x18000f7c5  lea     rax, [r14+r14*4]
0x18000f7c9  mov     word ptr [rdi+rax*8+0Ch], 1
0x18000f7d0  jmp     short loc_18000F7DA
0x18000f7d2  mov     r12d, [rsp+98h+arg_8]
0x18000f7da  mov     r14d, [rsp+98h+var_64]
0x18000f7df  lea     rax, [rsp+98h+arg_20]
0x18000f7e7  mov     rdx, r13
0x18000f7ea  mov     [rsp+98h+var_70], rax
0x18000f7ef  mov     r13, [rsp+98h+arg_0]
0x18000f7f7  lea     r9, NAME_RECORD_CONTROL
0x18000f7fe  mov     rcx, r13
0x18000f801  mov     [rsp+98h+var_78], r14d
0x18000f806  mov     r8d, 0Ch
0x18000f80c  call    WriteGeneric
0x18000f811  xor     r8d, r8d
0x18000f814  movzx   esi, ax
0x18000f817  test    ax, ax
0x18000f81a  jnz     loc_18000F692
0x18000f820  movzx   eax, [rsp+98h+arg_20]
0x18000f828  inc     bp
0x18000f82b  add     r14d, eax
0x18000f82e  mov     [rsp+98h+var_60], ebp
0x18000f832  mov     [rsp+98h+var_64], r14d
0x18000f837  cmp     bp, r15w
0x18000f83b  jb      loc_18000F6A2
0x18000f841  jmp     loc_18000F647
0x18000f846  mov     eax, 3E8h
0x18000f84b  mov     rbx, [rsp+98h+arg_10]
0x18000f853  add     rsp, 60h
0x18000f857  pop     r15
0x18000f859  pop     r14
0x18000f85b  pop     r13
0x18000f85d  pop     r12
0x18000f85f  pop     rdi
0x18000f860  pop     rsi
0x18000f861  pop     rbp
0x18000f862  retn
```
