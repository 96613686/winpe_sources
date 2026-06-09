# SetupReadWriteTransferPacket

- ea: `0x140003910`
- end: `0x140004072`
- name: `SetupReadWriteTransferPacket`
- size: `1890`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140002fb0`
- `0x14001fc7c`

## callees

- `0x140003910`
- `0x140004080`
- `0x14003e640`

## pseudocode

```c
char __fastcall SetupReadWriteTransferPacket(__int64 a1, __int64 a2, unsigned int a3, unsigned __int64 a4, __int64 a5)
{
  __int64 v10; // r14
  __int64 v11; // rbp
  __int64 v12; // rbx
  _DWORD *v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r12d
  __int64 v23; // r9
  __int64 v24; // rcx
  unsigned __int64 v25; // r11
  int v26; // r13d
  __int64 v27; // r10
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rdx
  char *v31; // r9
  unsigned int v32; // r12d
  __int64 v33; // r11
  __int64 v34; // rcx
  unsigned __int64 v35; // r8
  __int64 v36; // r13
  __int64 v37; // r10
  int v38; // ecx
  unsigned __int64 v39; // rcx
  char v40; // dl
  __int64 v41; // rax
  int v42; // ecx
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // rcx
  _BYTE *v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rax
  char v50; // al
  int v52; // ecx
  char v53; // al
  unsigned int v54; // edx
  unsigned __int64 v55; // r8
  unsigned int *v56; // r11
  char v57; // al
  __int64 v58; // r8
  unsigned int v59; // ecx
  _BYTE *v60; // r8
  unsigned __int8 v61; // cl
  int v62; // r13d
  unsigned int v63; // eax
  __int64 i; // r10
  __int64 v65; // rcx
  unsigned __int64 v66; // r11
  int v67; // r13d
  int v68; // r13d
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rcx
  char v72; // al
  _BYTE *v73; // r8
  int v74; // [rsp+20h] [rbp-68h]
  _BYTE *v75; // [rsp+30h] [rbp-58h]
  unsigned int v78; // [rsp+A8h] [rbp+20h]
  char v79; // [rsp+B0h] [rbp+28h]

  v10 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 64LL);
  v75 = *(_BYTE **)(a5 + 184);
  v11 = *(_QWORD *)(v10 + 1144);
  v79 = *v75;
  v74 = *(_DWORD *)(v10 + 584);
  v12 = a4 >> *(_BYTE *)(v10 + 642);
  v78 = a3 >> *(_BYTE *)(v10 + 642);
  *(_BYTE *)(a1 + 208) = *(_QWORD *)(*(_QWORD *)(v10 + 32) + 384LL) != 0;
  v13 = *(_DWORD **)(v11 + 688);
  if ( *(_BYTE *)(*(_QWORD *)(v10 + 528) + 30LL) == 1 )
    v14 = v13[4];
  else
    v14 = *(unsigned __int16 *)v13;
  memmove(*(void **)(a1 + 288), v13, v14);
  v15 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v15 + 2) == 40 )
    *(_QWORD *)(v15 + 64) = a2;
  else
    *(_QWORD *)(v15 + 24) = a2;
  v16 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v16 + 2) == 40 )
    *(_DWORD *)(v16 + 60) = a3;
  else
    *(_DWORD *)(v16 + 16) = a3;
  v17 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v17 + 2) != 40 )
  {
    *(_DWORD *)(v17 + 64) = v12;
    v17 = *(_QWORD *)(a1 + 288);
  }
  if ( v12 > 0xFFFFFFFFLL && *(_BYTE *)(v17 + 2) != 40 )
    *(_DWORD *)(v17 + 64) = -1;
  v18 = *(_QWORD *)(a1 + 288);
  v19 = *(_QWORD *)(a1 + 32);
  if ( *(_BYTE *)(v18 + 2) == 40 )
    *(_QWORD *)(v18 + 80) = v19;
  else
    *(_QWORD *)(v18 + 48) = v19;
  v20 = *(_QWORD *)(a1 + 288);
  v21 = a1 + 264;
  if ( *(_BYTE *)(v20 + 2) != 40 )
  {
    *(_QWORD *)(v20 + 32) = v21;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(v20 + 20) )
    goto LABEL_21;
  v22 = *(_DWORD *)(v20 + 56);
  v23 = 0;
  if ( !v22 )
    goto LABEL_21;
  while ( 1 )
  {
    v24 = *(unsigned int *)(v20 + 4 * v23 + 120);
    if ( (unsigned int)v24 < 0x80 )
      goto LABEL_61;
    v25 = *(unsigned int *)(v20 + 16);
    if ( (unsigned int)v24 >= (unsigned int)v25 )
      goto LABEL_61;
    v26 = *(_DWORD *)(v24 + v20);
    v27 = v24 + v20;
    if ( v26 == 64 )
    {
      if ( v24 + 40 <= v25 )
        goto LABEL_19;
      goto LABEL_61;
    }
    v62 = v26 - 65;
    if ( v62 )
      break;
    if ( v24 + 56 <= v25 )
    {
LABEL_19:
      *(_QWORD *)(v27 + 16) = v21;
      goto LABEL_21;
    }
LABEL_61:
    v23 = (unsigned int)(v23 + 1);
    if ( (unsigned int)v23 >= v22 )
      goto LABEL_21;
  }
  if ( v62 != 1 || v24 + 40 > v25 )
    goto LABEL_61;
  *(_QWORD *)(v27 + 24) = v21;
LABEL_21:
  if ( (*(_DWORD *)(v11 + 664) & 0x20) != 0 )
    v28 = *(_DWORD *)(v11 + 668);
  else
    v28 = v74;
  v29 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v29 + 2) == 40 )
    *(_DWORD *)(v29 + 40) = v28;
  else
    *(_DWORD *)(v29 + 20) = v28;
  v30 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v30 + 2) != 40 )
  {
    v31 = (char *)(v30 + 72);
    goto LABEL_37;
  }
  v31 = 0;
  if ( !*(_DWORD *)(v30 + 20) )
  {
    v32 = *(_DWORD *)(v30 + 56);
    if ( v32 )
    {
      v33 = 0;
      while ( 1 )
      {
        v34 = *(unsigned int *)(v30 + 4 * v33 + 120);
        if ( (unsigned int)v34 < 0x80 )
          goto LABEL_34;
        v35 = *(unsigned int *)(v30 + 16);
        if ( (unsigned int)v34 >= (unsigned int)v35 )
          goto LABEL_34;
        v36 = v34 + v30;
        v37 = (unsigned int)v34;
        v38 = *(_DWORD *)(v34 + v30);
        if ( v38 == 64 )
          break;
        v52 = v38 - 65;
        if ( !v52 )
        {
          v39 = v37 + 56;
LABEL_33:
          if ( v39 <= v35 )
          {
            if ( *(_BYTE *)(v36 + 10) )
              v31 = (char *)(v36 + 24);
            goto LABEL_37;
          }
          goto LABEL_34;
        }
        if ( v52 == 1 && v37 + 40 <= v35 )
        {
          if ( *(_DWORD *)(v36 + 12) )
            v31 = (char *)(v36 + 32);
          goto LABEL_37;
        }
LABEL_34:
        v33 = (unsigned int)(v33 + 1);
        if ( (unsigned int)v33 >= v32 )
          goto LABEL_37;
      }
      v39 = v37 + 40;
      goto LABEL_33;
    }
  }
LABEL_37:
  if ( !v31 )
    goto LABEL_38;
  v40 = v79;
  if ( (*(_WORD *)(v10 + 640) & 0x20) != 0 )
  {
    v31[8] = BYTE1(v12);
    v31[7] = BYTE2(v12);
    v31[6] = BYTE3(v12);
    v31[5] = BYTE4(v12);
    v31[4] = BYTE5(v12);
    v31[3] = BYTE6(v12);
    v31[2] = HIBYTE(v12);
    v31[13] = v78;
    v31[12] = BYTE1(v78);
    v31[11] = BYTE2(v78);
    v31[10] = HIBYTE(v78);
    v57 = -120;
    v31[9] = v12;
    if ( v79 != 3 )
      v57 = -118;
    *v31 = v57;
    v58 = *(_QWORD *)(a1 + 288);
    if ( *(_BYTE *)(v58 + 2) != 40 )
    {
      *(_BYTE *)(v58 + 10) = 16;
      goto LABEL_93;
    }
    if ( !*(_DWORD *)(v58 + 20) )
    {
      v63 = *(_DWORD *)(v58 + 56);
      for ( i = 0; (unsigned int)i < v63; i = (unsigned int)(i + 1) )
      {
        v65 = *(unsigned int *)(v58 + 4 * i + 120);
        if ( (unsigned int)v65 >= 0x80 )
        {
          v66 = *(unsigned int *)(v58 + 16);
          if ( (unsigned int)v65 < (unsigned int)v66 )
          {
            v67 = *(_DWORD *)(v65 + v58);
            if ( v67 == 64 )
            {
              if ( v65 + 40 <= v66 )
                goto LABEL_113;
            }
            else
            {
              v68 = v67 - 65;
              if ( v68 )
              {
                if ( v68 == 1 && v65 + 40 <= v66 )
                  break;
              }
              else if ( v65 + 56 <= v66 )
              {
LABEL_113:
                *(_BYTE *)(v65 + v58 + 10) = 16;
                break;
              }
            }
          }
        }
      }
    }
LABEL_93:
    if ( ((*(_DWORD *)(a5 + 16) >> 17) & 7) != 0 )
    {
      v59 = ((*(_DWORD *)(a5 + 16) >> 17) & 7) - 1;
      if ( v59 > 6 )
        goto LABEL_39;
    }
    else
    {
      v59 = 2;
    }
    if ( *v31 == -120 )
    {
      v60 = (_BYTE *)(*(_QWORD *)(v10 + 1144) + 112LL);
    }
    else
    {
      if ( *v31 != -118 )
        goto LABEL_39;
      v60 = (_BYTE *)(*(_QWORD *)(v10 + 1144) + 284LL);
    }
    if ( (*v60 & 4) != 0 )
    {
      if ( v60[v59 + 2] >= 7u )
      {
        v61 = 7;
      }
      else
      {
        _mm_lfence();
        v61 = v60[v59 + 2];
      }
      v71 = 5LL * v61;
      v72 = v60[4 * v71 + 12] >> 2;
      v73 = &v60[4 * v71];
      v31[1] ^= (v31[1] ^ v72) & 1;
      LOBYTE(v71) = v31[14] & 0x7F | ((v73[12] & 0xFE) << 6);
      v31[14] = v71;
      v31[14] = v71 ^ (v71 ^ (v73[12] << 6)) & 0x40;
LABEL_38:
      v40 = v79;
    }
  }
  else
  {
    v31[2] = BYTE3(v12);
    v31[3] = BYTE2(v12);
    v31[4] = BYTE1(v12);
    v31[7] = BYTE1(v78);
    v31[8] = v78;
    v53 = 40;
    if ( v79 != 3 )
      v53 = 42;
    v31[5] = v12;
    *v31 = v53;
  }
LABEL_39:
  v41 = *(_QWORD *)(a1 + 288);
  v42 = *(_DWORD *)(v10 + 592);
  if ( *(_BYTE *)(v41 + 2) == 40 )
    *(_DWORD *)(v41 + 24) = v42;
  else
    *(_DWORD *)(v41 + 12) = v42;
  if ( (*(_DWORD *)(a5 + 16) & 0x42) != 0 )
  {
    v43 = *(_QWORD *)(a1 + 288);
    if ( *(_BYTE *)(v43 + 2) == 40 )
      *(_DWORD *)(v43 + 24) |= 0x40000000u;
    else
      *(_DWORD *)(v43 + 12) |= 0x40000000u;
  }
  v44 = 64;
  if ( v40 != 3 )
    v44 = 128;
  v45 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v45 + 2) == 40 )
    *(_DWORD *)(v45 + 24) |= v44;
  else
    *(_DWORD *)(v45 + 12) |= v44;
  if ( v40 == 4 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v10 + 1152) + 16LL) & 0xF8000000) == 0xA0000000 )
    {
      v54 = 0;
      v55 = 0;
      while ( v54 < *(_DWORD *)(v11 + 628) )
      {
        v56 = (unsigned int *)(*(_QWORD *)(v11 + 632) + 16LL * v54);
        v55 += *((_QWORD *)v56 + 1) * *v56;
        if ( v12 * (unsigned __int64)*(unsigned int *)(v10 + 572) < v55 )
        {
          if ( v56[1] == 2 )
          {
            v69 = *(_QWORD *)(a1 + 288);
            if ( *(_BYTE *)(v69 + 2) == 40 )
              *(_DWORD *)(v69 + 24) |= 0x1000u;
            else
              *(_DWORD *)(v69 + 12) |= 0x1000u;
          }
          break;
        }
        ++v54;
      }
    }
    v46 = v75;
    if ( (v75[2] & 4) != 0 && v31 )
    {
      v31[1] ^= (v31[1] ^ (8 * *(_BYTE *)(v10 + 643))) & 8;
      goto LABEL_52;
    }
  }
  else
  {
    v46 = v75;
  }
  v47 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v47 + 2) == 40 )
    *(_DWORD *)(v47 + 24) |= 0x200u;
  else
    *(_DWORD *)(v47 + 12) |= 0x200u;
LABEL_52:
  if ( (v46[2] & 0x40) != 0 )
  {
    v70 = *(_QWORD *)(a1 + 288);
    if ( *(_BYTE *)(v70 + 2) == 40 )
      *(_DWORD *)(v70 + 24) |= 0x4000u;
    else
      *(_DWORD *)(v70 + 12) |= 0x4000u;
  }
  v48 = *(_QWORD *)(a1 + 288);
  *(_QWORD *)(a1 + 240) = a2;
  *(_DWORD *)(a1 + 248) = a3;
  *(_QWORD *)(a1 + 256) = a4;
  *(_QWORD *)(a1 + 48) = a5;
  *(_QWORD *)(a1 + 200) = 0;
  *(_BYTE *)(a1 + 56) = 1;
  *(_BYTE *)(a1 + 59) = *(_BYTE *)(v11 + 660);
  v49 = 24;
  *(_BYTE *)(a1 + 58) = 0;
  if ( *(_BYTE *)(v48 + 2) != 40 )
    v49 = 12;
  if ( (*(_DWORD *)(v49 + v48) & 0x1000) != 0 )
    v50 = 0;
  else
    v50 = *(_BYTE *)(v11 + 660);
  *(_BYTE *)(a1 + 57) = v50;
  *(_BYTE *)(a1 + 59) = *(_BYTE *)(v11 + 662);
  return SetupReadWriteExtraInfo(a1, a5);
}

```

## disassembly

```asm
0x140003910  mov     [rsp+arg_10], r8d
0x140003915  mov     [rsp+arg_8], rdx
0x14000391a  push    rbx
0x14000391b  push    rbp
0x14000391c  push    rsi
0x14000391d  push    rdi
0x14000391e  push    r12
0x140003920  push    r13
0x140003922  push    r14
0x140003924  push    r15
0x140003926  sub     rsp, 48h
0x14000392a  mov     rax, [rcx+28h]
0x14000392e  mov     rsi, rcx
0x140003931  mov     r15, [rsp+88h+arg_20]
0x140003939  mov     rbx, r9
0x14000393c  mov     r13, rdx
0x14000393f  mov     rdi, r9
0x140003942  mov     r12d, r8d
0x140003945  mov     r14, [rax+40h]
0x140003949  mov     rax, [r15+0B8h]
0x140003950  mov     [rsp+88h+var_58], rax
0x140003955  movzx   ecx, byte ptr [r14+282h]
0x14000395d  movzx   eax, byte ptr [rax]
0x140003960  mov     rbp, [r14+478h]
0x140003967  mov     byte ptr [rsp+88h+arg_20], al
0x14000396e  mov     eax, [r14+248h]
0x140003975  mov     [rsp+88h+var_68], eax
0x140003979  mov     eax, r8d
0x14000397c  shr     rbx, cl
0x14000397f  movzx   ecx, byte ptr [r14+282h]
0x140003987  shr     eax, cl
0x140003989  mov     [rsp+88h+arg_18], eax
0x140003990  mov     [rsp+88h+arg_0], eax
0x140003997  mov     rax, [r14+20h]
0x14000399b  mov     [rsp+88h+var_60], rbx
0x1400039a0  cmp     qword ptr [rax+180h], 0
0x1400039a8  setnz   al
0x1400039ab  mov     [rsi+0D0h], al
0x1400039b1  mov     rax, [r14+210h]
0x1400039b8  mov     rdx, [rbp+2B0h]; Src
0x1400039bf  cmp     byte ptr [rax+1Eh], 1
0x1400039c3  jnz     loc_140003E1A
0x1400039c9  mov     eax, [rdx+10h]
0x1400039cc  mov     rcx, [rsi+120h]; void *
0x1400039d3  mov     r8d, eax; Size
0x1400039d6  call    memmove
0x1400039db  mov     rax, [rsi+120h]
0x1400039e2  cmp     byte ptr [rax+2], 28h ; '('
0x1400039e6  jnz     loc_140003CB2
0x1400039ec  mov     [rax+40h], r13
0x1400039f0  mov     rax, [rsi+120h]
0x1400039f7  cmp     byte ptr [rax+2], 28h ; '('
0x1400039fb  jnz     loc_140003CD4
0x140003a01  mov     [rax+3Ch], r12d
0x140003a05  mov     rax, [rsi+120h]
0x140003a0c  cmp     byte ptr [rax+2], 28h ; '('
0x140003a10  jz      short loc_140003A1C
0x140003a12  mov     [rax+40h], ebx
0x140003a15  mov     rax, [rsi+120h]
0x140003a1c  mov     ecx, 0FFFFFFFFh
0x140003a21  cmp     rbx, rcx
0x140003a24  jg      loc_140003FF4
0x140003a2a  mov     rax, [rsi+120h]
0x140003a31  mov     rcx, [rsi+20h]
0x140003a35  cmp     byte ptr [rax+2], 28h ; '('
0x140003a39  jnz     loc_140003CBB
0x140003a3f  mov     [rax+50h], rcx
0x140003a43  mov     rdx, [rsi+120h]
0x140003a4a  lea     r8, [rsi+108h]
0x140003a51  mov     r10d, 80h
0x140003a57  cmp     byte ptr [rdx+2], 28h ; '('
0x140003a5b  jnz     short loc_140003AAF
0x140003a5d  cmp     dword ptr [rdx+14h], 0
0x140003a61  jnz     short loc_140003AB3
0x140003a63  mov     r12d, [rdx+38h]
0x140003a67  xor     r9d, r9d
0x140003a6a  test    r12d, r12d
0x140003a6d  jz      short loc_140003AB3
0x140003a6f  mov     ecx, [rdx+r9*4+78h]
0x140003a74  cmp     ecx, r10d
0x140003a77  jb      loc_140003CA1
0x140003a7d  mov     r11d, [rdx+10h]
0x140003a81  cmp     ecx, r11d
0x140003a84  jnb     loc_140003CA1
0x140003a8a  mov     r13d, [rcx+rdx]
0x140003a8e  lea     r10, [rcx+rdx]
0x140003a92  cmp     r13d, 40h ; '@'
0x140003a96  jnz     loc_140003F36
0x140003a9c  add     rcx, 28h ; '('
0x140003aa0  cmp     rcx, r11
0x140003aa3  ja      loc_140003C9B
0x140003aa9  mov     [r10+10h], r8
0x140003aad  jmp     short loc_140003AB3
0x140003aaf  mov     [rdx+20h], r8
0x140003ab3  mov     eax, [rbp+298h]
0x140003ab9  test    al, 20h
0x140003abb  jnz     loc_140004050
0x140003ac1  mov     ecx, [rsp+88h+var_68]
0x140003ac5  mov     rax, [rsi+120h]
0x140003acc  cmp     byte ptr [rax+2], 28h ; '('
0x140003ad0  jnz     loc_140003CCC
0x140003ad6  mov     [rax+28h], ecx
0x140003ad9  mov     rdx, [rsi+120h]
0x140003ae0  cmp     byte ptr [rdx+2], 28h ; '('
0x140003ae4  jnz     short loc_140003B3C
0x140003ae6  xor     r9d, r9d
0x140003ae9  cmp     [rdx+14h], r9d
0x140003aed  jnz     short loc_140003B40
0x140003aef  mov     r12d, [rdx+38h]
0x140003af3  test    r12d, r12d
0x140003af6  jz      short loc_140003B40
0x140003af8  xor     r11d, r11d
0x140003afb  mov     ecx, [rdx+r11*4+78h]
0x140003b00  cmp     ecx, 80h
0x140003b06  jb      short loc_140003B32
0x140003b08  mov     r8d, [rdx+10h]
0x140003b0c  cmp     ecx, r8d
0x140003b0f  jnb     short loc_140003B32
0x140003b11  lea     r13, [rcx+rdx]
0x140003b15  mov     r10d, ecx
0x140003b18  mov     ecx, [r13+0]
0x140003b1c  cmp     ecx, 40h ; '@'
0x140003b1f  jnz     loc_140003CDD
0x140003b25  lea     rcx, [r10+28h]
0x140003b29  cmp     rcx, r8
0x140003b2c  jbe     loc_140003E07
0x140003b32  inc     r11d
0x140003b35  cmp     r11d, r12d
0x140003b38  jb      short loc_140003AFB
0x140003b3a  jmp     short loc_140003B40
0x140003b3c  lea     r9, [rdx+48h]
0x140003b40  test    r9, r9
0x140003b43  jnz     loc_140003D0F
0x140003b49  movzx   edx, byte ptr [rsp+88h+arg_20]
0x140003b51  mov     rax, [rsi+120h]
0x140003b58  mov     ecx, [r14+250h]
0x140003b5f  cmp     byte ptr [rax+2], 28h ; '('
0x140003b63  jnz     loc_140003CC4
0x140003b69  mov     [rax+18h], ecx
0x140003b6c  mov     eax, [r15+10h]
0x140003b70  test    al, 42h
0x140003b72  jz      short loc_140003B8C
0x140003b74  mov     rax, [rsi+120h]
0x140003b7b  cmp     byte ptr [rax+2], 28h ; '('
0x140003b7f  jnz     loc_140003E22
0x140003b85  or      dword ptr [rax+18h], 40000000h
0x140003b8c  cmp     dl, 3
0x140003b8f  mov     ecx, 80h
0x140003b94  mov     eax, 40h ; '@'
0x140003b99  cmovnz  eax, ecx
0x140003b9c  mov     rcx, [rsi+120h]
0x140003ba3  cmp     byte ptr [rcx+2], 28h ; '('
0x140003ba7  jnz     loc_140003C7A
0x140003bad  or      [rcx+18h], eax
0x140003bb0  cmp     dl, 4
0x140003bb3  jz      loc_140003D75
0x140003bb9  mov     rdx, [rsp+88h+var_58]
0x140003bbe  mov     rax, [rsi+120h]
0x140003bc5  cmp     byte ptr [rax+2], 28h ; '('
0x140003bc9  jnz     loc_140003C82
0x140003bcf  or      dword ptr [rax+18h], 200h
0x140003bd6  test    byte ptr [rdx+2], 40h
0x140003bda  jnz     loc_14000402B
0x140003be0  mov     rax, [rsp+88h+arg_8]
0x140003be8  mov     edx, 0Ch
0x140003bed  mov     rcx, [rsi+120h]
0x140003bf4  mov     [rsi+0F0h], rax
0x140003bfb  mov     eax, [rsp+88h+arg_10]
0x140003c02  mov     [rsi+0F8h], eax
0x140003c08  mov     [rsi+100h], rdi
0x140003c0f  mov     [rsi+30h], r15
0x140003c13  mov     qword ptr [rsi+0C8h], 0
0x140003c1e  mov     byte ptr [rsi+38h], 1
0x140003c22  movzx   eax, byte ptr [rbp+294h]
0x140003c29  mov     [rsi+3Bh], al
0x140003c2c  mov     eax, 18h
0x140003c31  mov     byte ptr [rsi+3Ah], 0
0x140003c35  cmp     byte ptr [rcx+2], 28h ; '('
0x140003c39  cmovnz  eax, edx
0x140003c3c  test    dword ptr [rax+rcx], 1000h
0x140003c43  jnz     loc_14000406B
0x140003c49  movzx   eax, byte ptr [rbp+294h]
0x140003c50  mov     [rsi+39h], al
0x140003c53  mov     rdx, r15
0x140003c56  movzx   eax, byte ptr [rbp+296h]
0x140003c5d  mov     rcx, rsi
0x140003c60  mov     [rsi+3Bh], al
0x140003c63  call    SetupReadWriteExtraInfo
0x140003c68  add     rsp, 48h
0x140003c6c  pop     r15
0x140003c6e  pop     r14
0x140003c70  pop     r13
0x140003c72  pop     r12
0x140003c74  pop     rdi
0x140003c75  pop     rsi
0x140003c76  pop     rbp
0x140003c77  pop     rbx
0x140003c78  retn
0x140003c7a  or      [rcx+0Ch], eax
0x140003c7d  jmp     loc_140003BB0
0x140003c82  or      dword ptr [rax+0Ch], 200h
0x140003c89  jmp     loc_140003BD6
0x140003c8e  add     rcx, 38h ; '8'
0x140003c92  cmp     rcx, r11
0x140003c95  jbe     loc_140003AA9
0x140003c9b  mov     r10d, 80h
0x140003ca1  inc     r9d
0x140003ca4  cmp     r9d, r12d
0x140003ca7  jnb     loc_140003AB3
0x140003cad  jmp     loc_140003A6F
0x140003cb2  mov     [rax+18h], r13
0x140003cb6  jmp     loc_1400039F0
0x140003cbb  mov     [rax+30h], rcx
0x140003cbf  jmp     loc_140003A43
0x140003cc4  mov     [rax+0Ch], ecx
0x140003cc7  jmp     loc_140003B6C
0x140003ccc  mov     [rax+14h], ecx
0x140003ccf  jmp     loc_140003AD9
0x140003cd4  mov     [rax+10h], r12d
0x140003cd8  jmp     loc_140003A05
0x140003cdd  sub     ecx, 41h ; 'A'
0x140003ce0  jz      loc_140003F67
0x140003ce6  cmp     ecx, 1
0x140003ce9  jnz     loc_140003B32
0x140003cef  lea     rcx, [r10+28h]
0x140003cf3  cmp     rcx, r8
0x140003cf6  ja      loc_140003B32
0x140003cfc  cmp     [r13+0Ch], r9d
0x140003d00  jbe     loc_140003B40
0x140003d06  lea     r9, [r13+20h]
0x140003d0a  jmp     loc_140003B40
0x140003d0f  movzx   eax, word ptr [r14+280h]
0x140003d17  movzx   edx, byte ptr [rsp+88h+arg_20]
0x140003d1f  test    al, 20h
0x140003d21  jnz     loc_140003E2E
0x140003d27  movzx   eax, byte ptr [rsp+88h+var_60+3]
0x140003d2c  cmp     dl, 3
0x140003d2f  mov     [r9+2], al
0x140003d33  mov     ecx, 2Ah ; '*'
0x140003d38  movzx   eax, byte ptr [rsp+88h+var_60+2]
0x140003d3d  mov     [r9+3], al
0x140003d41  movzx   eax, byte ptr [rsp+88h+var_60+1]
0x140003d46  mov     [r9+4], al
0x140003d4a  movzx   eax, byte ptr [rsp+88h+arg_0+1]
0x140003d52  mov     [r9+7], al
0x140003d56  mov     eax, [rsp+88h+arg_18]
0x140003d5d  mov     [r9+8], al
0x140003d61  mov     eax, 28h ; '('
0x140003d66  cmovnz  eax, ecx
0x140003d69  mov     [r9+5], bl
0x140003d6d  mov     [r9], al
0x140003d70  jmp     loc_140003B51
0x140003d75  mov     rax, [r14+480h]
0x140003d7c  mov     ecx, [rax+10h]
0x140003d7f  and     ecx, 0F8000000h
0x140003d85  cmp     ecx, 0A0000000h
0x140003d8b  jz      short loc_140003DC5
0x140003d8d  mov     rdx, [rsp+88h+var_58]
0x140003d92  test    byte ptr [rdx+2], 4
0x140003d96  jz      loc_140003BBE
0x140003d9c  test    r9, r9
0x140003d9f  jz      loc_140003BBE
0x140003da5  movzx   eax, byte ptr [r9+1]
0x140003daa  movzx   ecx, byte ptr [r14+283h]
0x140003db2  shl     cl, 3
0x140003db5  xor     cl, al
0x140003db7  and     cl, 8
0x140003dba  xor     cl, al
0x140003dbc  mov     [r9+1], cl
0x140003dc0  jmp     loc_140003BD6
0x140003dc5  mov     r10d, [rbp+274h]
0x140003dcc  xor     edx, edx
0x140003dce  xor     r8d, r8d
0x140003dd1  cmp     edx, r10d
0x140003dd4  jnb     short loc_140003D8D
0x140003dd6  mov     r11d, edx
0x140003dd9  shl     r11, 4
0x140003ddd  add     r11, [rbp+278h]
0x140003de4  mov     eax, [r11]
0x140003de7  imul    rax, [r11+8]
0x140003dec  add     r8, rax
0x140003def  mov     eax, [r14+23Ch]
0x140003df6  imul    rax, rbx
0x140003dfa  cmp     rax, r8
0x140003dfd  jb      loc_14003F068
0x140003e03  inc     edx
0x140003e05  jmp     short loc_140003DD1
0x140003e07  cmp     [r13+0Ah], r9b
0x140003e0b  jbe     loc_140003B40
0x140003e11  lea     r9, [r13+18h]
0x140003e15  jmp     loc_140003B40
0x140003e1a  movzx   eax, word ptr [rdx]
0x140003e1d  jmp     loc_1400039CC
0x140003e22  or      dword ptr [rax+0Ch], 40000000h
0x140003e29  jmp     loc_140003B8C
0x140003e2e  movzx   eax, byte ptr [rsp+88h+var_60+1]
0x140003e33  cmp     dl, 3
0x140003e36  mov     [r9+8], al
0x140003e3a  mov     ecx, 8Ah
0x140003e3f  movzx   eax, byte ptr [rsp+88h+var_60+2]
  ... truncated ...
```
