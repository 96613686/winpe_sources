# decompress

- ea: `0x140033df0`
- end: `0x14003459a`
- name: `decompress`
- size: `1962`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400330a0`

## callees

- `0x140033df0`

## pseudocode

```c
__int64 __fastcall decompress(unsigned __int8 *a1, int a2, int a3, _QWORD *a4, _DWORD *a5, __int64 a6)
{
  unsigned __int8 *v8; // r9
  int v9; // ebp
  unsigned __int64 v10; // r14
  unsigned __int8 *v11; // rdi
  int v12; // edx
  int v13; // r8d
  _BYTE *v14; // r11
  int v15; // r15d
  int v16; // r8d
  int v17; // eax
  int v18; // ecx
  int v19; // r10d
  int v20; // eax
  int v21; // eax
  __int64 result; // rax
  int v23; // eax
  int v24; // r10d
  int v25; // eax
  int v26; // r10d
  unsigned int v27; // ebx
  _BYTE *v28; // rcx
  _BYTE *v29; // r10
  char v30; // al
  char *v31; // rcx
  _BYTE *v32; // r10
  unsigned int i; // ebx
  char v34; // al
  int v35; // eax
  int v36; // ecx
  int v37; // r8d
  int v38; // ebx
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // ebp
  int v43; // ebp
  int v44; // eax
  int v45; // ecx
  int v46; // eax
  int v47; // ebp
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // ecx
  int v52; // r8d
  int v53; // eax
  int v54; // ebx
  int v55; // eax
  int v56; // ecx
  int v57; // r8d
  int v58; // eax
  int v59; // ebx
  int v60; // eax
  int v61; // ecx
  int v62; // r8d
  int v63; // eax
  int v64; // ebx
  int v65; // eax
  int v66; // ecx
  int v67; // r8d
  int v68; // eax
  int v69; // ebx
  int v70; // eax
  int v71; // ecx
  int v72; // r8d
  int v73; // eax
  int v74; // ebx
  int v75; // eax
  int v76; // r10d
  int v77; // eax
  int v78; // ebx
  int v79; // ecx
  int v80; // r8d
  int v81; // eax
  int v82; // eax
  int v83; // ecx
  int v84; // ebx
  int v85; // eax
  int v86; // ecx
  int v87; // r8d
  int v88; // eax
  int v89; // eax
  int v90; // ecx
  int v91; // ebx
  int v92; // ebx
  int v93; // eax
  int v94; // ecx

  if ( (*(_DWORD *)(a6 + 8) & 0x800) != 0 && !a3 )
    return 0;
  v8 = a1 + 1;
  v9 = 0;
  v10 = a6 + *(unsigned int *)(a6 + 12) + 16LL;
  v11 = &a1[a2];
  v12 = a1[1] + (*a1 << 8);
  v13 = 16;
  if ( a3 )
  {
    v14 = (_BYTE *)(a6 + 16);
    *(_QWORD *)a6 = a6 + 16;
  }
  else
  {
    v14 = *(_BYTE **)a6;
  }
  v15 = (int)v14;
  while ( v8 < v11 )
  {
    v16 = v13 - 3;
    v17 = (v12 >> v16) & 7;
    if ( v16 < 9 )
    {
      v18 = *++v8;
      v16 += 8;
      v12 = v18 | (v12 << 8);
    }
    if ( v17 )
    {
      if ( v17 == 1 )
      {
        v13 = v16 - 5;
        v19 = (v12 >> v13) & 0x1F;
        if ( v13 < 9 )
        {
          v21 = *++v8;
          v13 += 8;
          v12 = v21 | (v12 << 8);
        }
        LOBYTE(v19) = v19 + 32;
        goto LABEL_16;
      }
      switch ( v17 )
      {
        case 2:
          v13 = v16 - 5;
          v19 = (v12 >> v13) & 0x1F;
          if ( v13 < 9 )
          {
            v39 = *++v8;
            v13 += 8;
            v12 = v39 | (v12 << 8);
          }
          LOBYTE(v19) = v19 + 64;
          goto LABEL_16;
        case 3:
          v13 = v16 - 5;
          v19 = (v12 >> v13) & 0x1F;
          if ( v13 < 9 )
          {
            v23 = *++v8;
            v13 += 8;
            v12 = v23 | (v12 << 8);
          }
          LOBYTE(v19) = v19 + 96;
          goto LABEL_16;
        case 4:
          v13 = v16 - 6;
          v19 = (v12 >> v13) & 0x3F;
          if ( v13 < 9 )
          {
            v20 = *++v8;
            v13 += 8;
            v12 = v20 | (v12 << 8);
          }
          LOBYTE(v19) = v19 + 0x80;
          goto LABEL_16;
        case 5:
          v13 = v16 - 6;
          v19 = (v12 >> v13) & 0x3F;
          if ( v13 < 9 )
          {
            v40 = *++v8;
            v13 += 8;
            v12 = v40 | (v12 << 8);
          }
          LOBYTE(v19) = v19 - 64;
          goto LABEL_16;
        case 6:
          if ( v16 <= 13 )
          {
            v16 -= 5;
            v43 = (v12 >> v16) & 0x1F;
            if ( v16 < 9 )
            {
              v44 = *++v8;
              v16 += 8;
              v12 = v44 | (v12 << 8);
            }
            ++v8;
            v45 = (unsigned __int8)(v12 >> (v16 - 8));
            v12 = *v8 | (v12 << 8);
            v42 = v45 + (v43 << 8);
          }
          else
          {
            v41 = *++v8;
            v42 = (v12 >> (v16 - 13)) & 0x1FFF;
            v12 = v41 | (v12 << 8);
            v16 = v16 - 13 + 8;
          }
          v9 = v42 + 320;
          break;
        case 7:
          v24 = (v12 >> --v16) & 1;
          if ( v16 < 9 )
          {
            v46 = *++v8;
            v16 = 16;
            v12 = v46 | (v12 << 8);
          }
          if ( v24 )
          {
            v16 -= 6;
            v9 = (v12 >> v16) & 0x3F;
            if ( v16 < 9 )
            {
              v25 = *++v8;
              v16 += 8;
              v12 = v25 | (v12 << 8);
            }
          }
          else
          {
            ++v8;
            v47 = (unsigned __int8)(v12 >> (v16 - 8));
            v12 = *v8 | (v12 << 8);
            v9 = v47 + 64;
          }
          break;
        default:
          break;
      }
      v13 = v16 - 1;
      v26 = (v12 >> v13) & 1;
      if ( v13 < 9 )
      {
        v48 = *++v8;
        v13 = 16;
        v12 = v48 | (v12 << 8);
      }
      if ( v26 )
      {
        v36 = v13 - 1;
        v37 = (v12 >> (v13 - 1)) & 1;
        if ( v36 < 9 )
        {
          v49 = *++v8;
          v36 = 16;
          v12 = v49 | (v12 << 8);
        }
        if ( v37 )
        {
          v51 = v36 - 1;
          v52 = (v12 >> v51) & 1;
          if ( v51 < 9 )
          {
            v53 = *++v8;
            v51 = 16;
            v12 = v53 | (v12 << 8);
          }
          if ( v52 )
          {
            v56 = v51 - 1;
            v57 = (v12 >> v56) & 1;
            if ( v56 < 9 )
            {
              v58 = *++v8;
              v56 = 16;
              v12 = v58 | (v12 << 8);
            }
            if ( v57 )
            {
              v61 = v56 - 1;
              v62 = (v12 >> v61) & 1;
              if ( v61 < 9 )
              {
                v63 = *++v8;
                v61 = 16;
                v12 = v63 | (v12 << 8);
              }
              if ( v62 )
              {
                v66 = v61 - 1;
                v67 = (v12 >> v66) & 1;
                if ( v66 < 9 )
                {
                  v68 = *++v8;
                  v66 = 16;
                  v12 = v68 | (v12 << 8);
                }
                if ( v67 )
                {
                  v71 = v66 - 1;
                  v72 = (v12 >> v71) & 1;
                  if ( v71 < 9 )
                  {
                    v73 = *++v8;
                    v71 = 16;
                    v12 = v73 | (v12 << 8);
                  }
                  if ( v72 )
                  {
                    v13 = v71 - 1;
                    v76 = (v12 >> (v71 - 1)) & 1;
                    if ( v71 - 1 < 9 )
                    {
                      v77 = *++v8;
                      v13 = 16;
                      v12 = v77 | (v12 << 8);
                    }
                    if ( v76 )
                    {
                      v79 = v13 - 1;
                      v80 = (v12 >> (v13 - 1)) & 1;
                      if ( v79 < 9 )
                      {
                        v81 = *++v8;
                        v79 = 16;
                        v12 = v81 | (v12 << 8);
                      }
                      if ( v80 )
                      {
                        v86 = v79 - 1;
                        v87 = (v12 >> v86) & 1;
                        if ( v86 < 9 )
                        {
                          v88 = *++v8;
                          v86 = 16;
                          v12 = v88 | (v12 << 8);
                        }
                        if ( v87 )
                          return 0;
                        if ( (unsigned int)v86 <= 0xA )
                        {
                          v13 = v86 - 2;
                          v92 = (v12 >> (v86 - 2)) & 3;
                          if ( v86 - 2 < 9 )
                          {
                            v93 = *++v8;
                            v13 += 8;
                            v12 = v93 | (v12 << 8);
                          }
                          ++v8;
                          v94 = (unsigned __int8)(v12 >> (v13 - 8));
                          v12 = *v8 | (v12 << 8);
                          v91 = v94 + (v92 << 8);
                        }
                        else
                        {
                          v89 = v8[1];
                          v90 = v86 - 10;
                          ++v8;
                          v91 = (v12 >> v90) & 0x3FF;
                          v12 = v89 | (v12 << 8);
                          v13 = v90 + 8;
                        }
                        v27 = v91 + 1024;
                      }
                      else
                      {
                        v82 = v8[1];
                        v83 = v79 - 9;
                        ++v8;
                        v84 = (v12 >> v83) & 0x1FF;
                        v12 = v82 | (v12 << 8);
                        v13 = v83 + 8;
                        if ( v83 + 8 < 9 )
                        {
                          v85 = *++v8;
                          v13 = v83 + 16;
                          v12 = v85 | (v12 << 8);
                        }
                        v27 = v84 + 512;
                      }
                    }
                    else
                    {
                      ++v8;
                      v78 = (unsigned __int8)(v12 >> (v13 - 8));
                      v12 = *v8 | (v12 << 8);
                      v27 = v78 + 256;
                    }
                  }
                  else
                  {
                    v13 = v71 - 7;
                    v74 = (v12 >> (v71 - 7)) & 0x7F;
                    if ( v71 - 7 < 9 )
                    {
                      v75 = *++v8;
                      v13 += 8;
                      v12 = v75 | (v12 << 8);
                    }
                    v27 = v74 + 128;
                  }
                }
                else
                {
                  v13 = v66 - 6;
                  v69 = (v12 >> (v66 - 6)) & 0x3F;
                  if ( v66 - 6 < 9 )
                  {
                    v70 = *++v8;
                    v13 += 8;
                    v12 = v70 | (v12 << 8);
                  }
                  v27 = v69 + 64;
                }
              }
              else
              {
                v13 = v61 - 5;
                v64 = (v12 >> (v61 - 5)) & 0x1F;
                if ( v61 - 5 < 9 )
                {
                  v65 = *++v8;
                  v13 += 8;
                  v12 = v65 | (v12 << 8);
                }
                v27 = v64 + 32;
              }
            }
            else
            {
              v13 = v56 - 4;
              v59 = (v12 >> (v56 - 4)) & 0xF;
              if ( v56 - 4 < 9 )
              {
                v60 = *++v8;
                v13 += 8;
                v12 = v60 | (v12 << 8);
              }
              v27 = v59 + 16;
            }
          }
          else
          {
            v13 = v51 - 3;
            v54 = (v12 >> (v51 - 3)) & 7;
            if ( v51 - 3 < 9 )
            {
              v55 = *++v8;
              v13 += 8;
              v12 = v55 | (v12 << 8);
            }
            v27 = v54 + 8;
          }
        }
        else
        {
          v13 = v36 - 2;
          v38 = (v12 >> (v36 - 2)) & 3;
          if ( v36 - 2 < 9 )
          {
            v50 = *++v8;
            v13 += 8;
            v12 = v50 | (v12 << 8);
          }
          v27 = v38 + 4;
        }
      }
      else
      {
        v27 = 3;
      }
      v28 = &v14[-v9];
      if ( (*(_DWORD *)(a6 + 8) & 0x800) != 0 )
      {
        if ( (unsigned __int64)v28 < a6 + 16 )
          return 0;
      }
      else
      {
        v28 = (_BYTE *)(a6 + (((_WORD)v28 - (_WORD)a6 - 16) & 0x1FFF) + 16LL);
      }
      v29 = v14;
      v14 += v27;
      if ( (unsigned __int64)v14 >= v10 || (unsigned __int64)&v28[v27] >= v10 )
        return 0;
      *v29 = *v28;
      v30 = v28[1];
      v31 = v28 + 2;
      v29[1] = v30;
      v32 = v29 + 2;
      for ( i = v27 - 2; i; --i )
      {
        v34 = *v31++;
        *v32++ = v34;
      }
    }
    else
    {
      v13 = v16 - 5;
      v19 = (v12 >> v13) & 0x1F;
      if ( v13 < 9 )
      {
        v35 = *++v8;
        v13 += 8;
        v12 = v35 | (v12 << 8);
      }
LABEL_16:
      if ( (unsigned __int64)v14 >= v10 )
        return 0;
      *v14++ = v19;
    }
  }
  if ( (unsigned __int64)v14 >= v10 )
    return 0;
  if ( v13 == 16 && v8 == v11 )
    *v14++ = *(v8 - 1);
  *a5 = (_DWORD)v14 - v15;
  *a4 = *(_QWORD *)a6;
  result = 1;
  *(_QWORD *)a6 = v14;
  return result;
}

```

## disassembly

```asm
0x140033df0  push    rbx
0x140033df2  push    rbp
0x140033df3  push    rsi
0x140033df4  push    rdi
0x140033df5  push    r12
0x140033df7  push    r13
0x140033df9  push    r14
0x140033dfb  push    r15
0x140033dfd  mov     rsi, [rsp+40h+arg_28]
0x140033e02  mov     r12, r9
0x140033e05  mov     r10d, r8d
0x140033e08  test    dword ptr [rsi+8], 800h
0x140033e0f  jnz     loc_14003412B
0x140033e15  mov     r14d, [rsi+0Ch]
0x140033e19  lea     r9, [rcx+1]
0x140033e1d  movzx   eax, byte ptr [r9]
0x140033e21  add     r14, 10h
0x140033e25  movsxd  rdi, edx
0x140033e28  xor     ebp, ebp
0x140033e2a  movzx   edx, byte ptr [rcx]
0x140033e2d  add     r14, rsi
0x140033e30  shl     edx, 8
0x140033e33  add     rdi, rcx
0x140033e36  add     edx, eax
0x140033e38  mov     r8d, 10h
0x140033e3e  test    r10d, r10d
0x140033e41  jz      loc_140033F7E
0x140033e47  lea     r11, [rsi+10h]
0x140033e4b  mov     [rsi], r11
0x140033e4e  mov     r15, r11
0x140033e51  lea     r13, cs:140000000h
0x140033e58  nop     dword ptr [rax+rax+00000000h]
0x140033e60  cmp     r9, rdi
0x140033e63  jnb     loc_140033F41
0x140033e69  add     r8d, 0FFFFFFFDh
0x140033e6d  mov     eax, edx
0x140033e6f  mov     ecx, r8d
0x140033e72  sar     eax, cl
0x140033e74  and     eax, 7
0x140033e77  cmp     r8d, 9
0x140033e7b  jge     short loc_140033E8E
0x140033e7d  movzx   ecx, byte ptr [r9+1]
0x140033e82  inc     r9
0x140033e85  add     r8d, 8
0x140033e89  shl     edx, 8
0x140033e8c  or      edx, ecx
0x140033e8e  test    eax, eax
0x140033e90  jz      short loc_140033EE4
0x140033e92  cmp     eax, 1
0x140033e95  jz      short loc_140033F13
0x140033e97  add     eax, 0FFFFFFFEh; switch 6 cases
0x140033e9a  cmp     eax, 5
0x140033e9d  ja      def_140033EB0; jumptable 0000000140033EB0 default case
0x140033ea3  cdqe
0x140033ea5  mov     ecx, ds:(jpt_140033EB0 - 140000000h)[r13+rax*4]
0x140033ead  add     rcx, r13
0x140033eb0  jmp     rcx; switch jump
0x140033eb6  add     r8d, 0FFFFFFFAh; jumptable 0000000140033EB0 case 4
0x140033eba  mov     r10d, edx
0x140033ebd  mov     ecx, r8d
0x140033ec0  sar     r10d, cl
0x140033ec3  and     r10d, 3Fh
0x140033ec7  cmp     r8d, 9
0x140033ecb  jge     short loc_140033EDE
0x140033ecd  movzx   eax, byte ptr [r9+1]
0x140033ed2  inc     r9
0x140033ed5  add     r8d, 8
0x140033ed9  shl     edx, 8
0x140033edc  or      edx, eax
0x140033ede  sub     r10d, 0FFFFFF80h
0x140033ee2  jmp     short loc_140033EFF
0x140033ee4  add     r8d, 0FFFFFFFBh
0x140033ee8  mov     r10d, edx
0x140033eeb  mov     ecx, r8d
0x140033eee  sar     r10d, cl
0x140033ef1  and     r10d, 1Fh
0x140033ef5  cmp     r8d, 9
0x140033ef9  jl      loc_1400340C5
0x140033eff  cmp     r11, r14
0x140033f02  jnb     loc_14003411B
0x140033f08  mov     [r11], r10b
0x140033f0b  inc     r11
0x140033f0e  jmp     loc_140033E60
0x140033f13  add     r8d, 0FFFFFFFBh
0x140033f17  mov     r10d, edx
0x140033f1a  mov     ecx, r8d
0x140033f1d  sar     r10d, cl
0x140033f20  and     r10d, 1Fh
0x140033f24  cmp     r8d, 9
0x140033f28  jge     short loc_140033F3B
0x140033f2a  movzx   eax, byte ptr [r9+1]
0x140033f2f  inc     r9
0x140033f32  add     r8d, 8
0x140033f36  shl     edx, 8
0x140033f39  or      edx, eax
0x140033f3b  add     r10d, 20h ; ' '
0x140033f3f  jmp     short loc_140033EFF
0x140033f41  cmp     r11, r14
0x140033f44  jnb     loc_14003411B
0x140033f4a  cmp     r8d, 10h
0x140033f4e  jz      loc_140034581
0x140033f54  mov     rax, [rsp+40h+arg_20]
0x140033f59  mov     ecx, r11d
0x140033f5c  sub     ecx, r15d
0x140033f5f  mov     [rax], ecx
0x140033f61  mov     rax, [rsi]
0x140033f64  mov     [r12], rax
0x140033f68  mov     eax, 1
0x140033f6d  mov     [rsi], r11
0x140033f70  pop     r15
0x140033f72  pop     r14
0x140033f74  pop     r13
0x140033f76  pop     r12
0x140033f78  pop     rdi
0x140033f79  pop     rsi
0x140033f7a  pop     rbp
0x140033f7b  pop     rbx
0x140033f7c  retn
0x140033f7e  mov     r11, [rsi]
0x140033f81  jmp     loc_140033E4E
0x140033f86  add     r8d, 0FFFFFFFBh; jumptable 0000000140033EB0 case 3
0x140033f8a  mov     r10d, edx
0x140033f8d  mov     ecx, r8d
0x140033f90  sar     r10d, cl
0x140033f93  and     r10d, 1Fh
0x140033f97  cmp     r8d, 9
0x140033f9b  jge     short loc_140033FAE
0x140033f9d  movzx   eax, byte ptr [r9+1]
0x140033fa2  inc     r9
0x140033fa5  add     r8d, 8
0x140033fa9  shl     edx, 8
0x140033fac  or      edx, eax
0x140033fae  add     r10d, 60h ; '`'
0x140033fb2  jmp     loc_140033EFF
0x140033fb7  add     r8d, 0FFFFFFFAh; jumptable 0000000140033EB0 case 5
0x140033fbb  mov     r10d, edx
0x140033fbe  mov     ecx, r8d
0x140033fc1  sar     r10d, cl
0x140033fc4  and     r10d, 3Fh
0x140033fc8  cmp     r8d, 9
0x140033fcc  jl      loc_140034166
0x140033fd2  add     r10d, 0C0h
0x140033fd9  jmp     loc_140033EFF
0x140033fde  dec     r8d; jumptable 0000000140033EB0 case 7
0x140033fe1  mov     r10d, edx
0x140033fe4  mov     ecx, r8d
0x140033fe7  sar     r10d, cl
0x140033fea  and     r10d, 1
0x140033fee  cmp     r8d, 9
0x140033ff2  jl      loc_1400341ED
0x140033ff8  test    r10d, r10d
0x140033ffb  jz      loc_140034205
0x140034001  add     r8d, 0FFFFFFFAh
0x140034005  mov     ebp, edx
0x140034007  mov     ecx, r8d
0x14003400a  sar     ebp, cl
0x14003400c  and     ebp, 3Fh
0x14003400f  cmp     r8d, 9
0x140034013  jge     short def_140033EB0; jumptable 0000000140033EB0 default case
0x140034015  movzx   eax, byte ptr [r9+1]
0x14003401a  inc     r9
0x14003401d  add     r8d, 8
0x140034021  shl     edx, 8
0x140034024  or      edx, eax
0x140034026  dec     r8d; jumptable 0000000140033EB0 default case
0x140034029  mov     r10d, edx
0x14003402c  mov     ecx, r8d
0x14003402f  sar     r10d, cl
0x140034032  and     r10d, 1
0x140034036  cmp     r8d, 9
0x14003403a  jl      loc_140034224
0x140034040  test    r10d, r10d
0x140034043  jnz     loc_1400340DB
0x140034049  mov     ebx, 3
0x14003404e  movsxd  r10, ebp
0x140034051  mov     rcx, r11
0x140034054  sub     rcx, r10
0x140034057  test    dword ptr [rsi+8], 800h
0x14003405e  jz      loc_140034568
0x140034064  lea     rax, [rsi+10h]
0x140034068  cmp     rcx, rax
0x14003406b  jb      loc_14003411B
0x140034071  mov     eax, ebx
0x140034073  mov     r10, r11
0x140034076  add     r11, rax
0x140034079  cmp     r11, r14
0x14003407c  jnb     loc_14003411B
0x140034082  add     rax, rcx
0x140034085  cmp     rax, r14
0x140034088  jnb     loc_14003411B
0x14003408e  movzx   eax, byte ptr [rcx]
0x140034091  mov     [r10], al
0x140034094  movzx   eax, byte ptr [rcx+1]
0x140034098  add     rcx, 2
0x14003409c  mov     [r10+1], al
0x1400340a0  add     r10, 2
0x1400340a4  sub     ebx, 2
0x1400340a7  jz      loc_140033E60
0x1400340ad  movzx   eax, byte ptr [rcx]
0x1400340b0  lea     rcx, [rcx+1]
0x1400340b4  mov     [r10], al
0x1400340b7  lea     r10, [r10+1]
0x1400340bb  sub     ebx, 1
0x1400340be  jnz     short loc_1400340AD
0x1400340c0  jmp     loc_140033E60
0x1400340c5  movzx   eax, byte ptr [r9+1]
0x1400340ca  inc     r9
0x1400340cd  add     r8d, 8
0x1400340d1  shl     edx, 8
0x1400340d4  or      edx, eax
0x1400340d6  jmp     loc_140033EFF
0x1400340db  lea     ecx, [r8-1]
0x1400340df  mov     r8d, edx
0x1400340e2  sar     r8d, cl
0x1400340e5  and     r8d, 1
0x1400340e9  cmp     ecx, 9
0x1400340ec  jl      loc_14003423C
0x1400340f2  test    r8d, r8d
0x1400340f5  jnz     loc_140034269
0x1400340fb  lea     r8d, [rcx-2]
0x1400340ff  mov     ebx, edx
0x140034101  mov     ecx, r8d
0x140034104  sar     ebx, cl
0x140034106  and     ebx, 3
0x140034109  cmp     r8d, 9
0x14003410d  jl      loc_140034253
0x140034113  add     ebx, 4
0x140034116  jmp     loc_14003404E
0x14003411b  xor     eax, eax
0x14003411d  pop     r15
0x14003411f  pop     r14
0x140034121  pop     r13
0x140034123  pop     r12
0x140034125  pop     rdi
0x140034126  pop     rsi
0x140034127  pop     rbp
0x140034128  pop     rbx
0x140034129  retn
0x14003412b  test    r10d, r10d
0x14003412e  jz      short loc_14003411B
0x140034130  jmp     loc_140033E15
0x140034135  add     r8d, 0FFFFFFFBh; jumptable 0000000140033EB0 case 2
0x140034139  mov     r10d, edx
0x14003413c  mov     ecx, r8d
0x14003413f  sar     r10d, cl
0x140034142  and     r10d, 1Fh
0x140034146  cmp     r8d, 9
0x14003414a  jge     short loc_14003415D
0x14003414c  movzx   eax, byte ptr [r9+1]
0x140034151  inc     r9
0x140034154  add     r8d, 8
0x140034158  shl     edx, 8
0x14003415b  or      edx, eax
0x14003415d  add     r10d, 40h ; '@'
0x140034161  jmp     loc_140033EFF
0x140034166  movzx   eax, byte ptr [r9+1]
0x14003416b  inc     r9
0x14003416e  add     r8d, 8
0x140034172  shl     edx, 8
0x140034175  or      edx, eax
0x140034177  jmp     loc_140033FD2
0x14003417c  mov     ebp, edx; jumptable 0000000140033EB0 case 6
0x14003417e  cmp     r8d, 0Dh
0x140034182  jle     short loc_1400341A3
0x140034184  movzx   eax, byte ptr [r9+1]
0x140034189  lea     ecx, [r8-0Dh]
0x14003418d  inc     r9
0x140034190  sar     ebp, cl
0x140034192  and     ebp, 1FFFh
0x140034198  shl     edx, 8
0x14003419b  or      edx, eax
0x14003419d  lea     r8d, [rcx+8]
0x1400341a1  jmp     short loc_1400341E2
0x1400341a3  add     r8d, 0FFFFFFFBh
0x1400341a7  mov     ecx, r8d
0x1400341aa  sar     ebp, cl
0x1400341ac  and     ebp, 1Fh
0x1400341af  cmp     r8d, 9
0x1400341b3  jge     short loc_1400341C6
0x1400341b5  movzx   eax, byte ptr [r9+1]
0x1400341ba  inc     r9
0x1400341bd  add     r8d, 8
0x1400341c1  shl     edx, 8
0x1400341c4  or      edx, eax
0x1400341c6  mov     eax, edx
0x1400341c8  shl     ebp, 8
0x1400341cb  lea     ecx, [r8-8]
0x1400341cf  shl     edx, 8
0x1400341d2  sar     eax, cl
0x1400341d4  inc     r9
0x1400341d7  movzx   ecx, al
0x1400341da  movzx   eax, byte ptr [r9]
0x1400341de  or      edx, eax
0x1400341e0  add     ebp, ecx
0x1400341e2  add     ebp, 140h
0x1400341e8  jmp     def_140033EB0; jumptable 0000000140033EB0 default case
0x1400341ed  movzx   eax, byte ptr [r9+1]
0x1400341f2  inc     r9
0x1400341f5  shl     edx, 8
0x1400341f8  mov     r8d, 10h
  ... truncated ...
```
