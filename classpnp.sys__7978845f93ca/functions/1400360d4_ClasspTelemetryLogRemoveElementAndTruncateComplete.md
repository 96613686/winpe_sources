# ClasspTelemetryLogRemoveElementAndTruncateComplete

- ea: `0x1400360d4`
- end: `0x140036546`
- name: `ClasspTelemetryLogRemoveElementAndTruncateComplete`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140016350`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x1400360d4`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall ClasspTelemetryLogRemoveElementAndTruncateComplete(__int64 a1, __int64 a2, int a3, int a4)
{
  bool v4; // zf
  _DWORD *v5; // rbx
  __int64 v6; // r13
  _BYTE *v8; // r8
  unsigned int v9; // edi
  __int64 v10; // r11
  char v11; // si
  __int64 v12; // rcx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // r8
  char v18; // di
  char v19; // r12
  char v20; // r15
  unsigned __int64 v21; // rcx
  unsigned int v22; // esi
  __int64 v23; // r11
  char v24; // r14
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  int v27; // ecx
  unsigned int v28; // esi
  _BYTE *v29; // rdx
  __int64 v30; // rbx
  char v31; // r14
  unsigned __int64 v32; // r11
  __int64 v33; // r9
  int v34; // ecx
  char v35; // cl
  bool v36; // cf
  unsigned int v37; // eax
  NTSTATUS result; // eax
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // r10
  __int64 v42; // rcx
  char v43; // [rsp+30h] [rbp-D0h] BYREF
  char v44; // [rsp+31h] [rbp-CFh] BYREF
  char v45; // [rsp+32h] [rbp-CEh] BYREF
  char v46; // [rsp+33h] [rbp-CDh] BYREF
  _BYTE v47[4]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v48[8]; // [rsp+38h] [rbp-C8h] BYREF
  int v49; // [rsp+40h] [rbp-C0h] BYREF
  int v50; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v51; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  int *v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  char *v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  int *v59; // [rsp+A0h] [rbp-60h]
  __int64 v60; // [rsp+A8h] [rbp-58h]
  _BYTE *v61; // [rsp+B0h] [rbp-50h]
  __int64 v62; // [rsp+B8h] [rbp-48h]
  _BYTE *v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+C8h] [rbp-38h]
  char *v65; // [rsp+D0h] [rbp-30h]
  __int64 v66; // [rsp+D8h] [rbp-28h]
  char *v67; // [rsp+E0h] [rbp-20h]
  __int64 v68; // [rsp+E8h] [rbp-18h]
  char *v69; // [rsp+F0h] [rbp-10h]
  __int64 v70; // [rsp+F8h] [rbp-8h]

  v4 = *(_BYTE *)(a2 + 2) == 40;
  v5 = (_DWORD *)(a2 + 20);
  v6 = *(_QWORD *)(a1 + 64);
  v50 = a4;
  v49 = a3;
  if ( !v4 )
  {
    v8 = (_BYTE *)(a2 + 72);
    goto LABEL_24;
  }
  v8 = 0;
  if ( !*v5 )
  {
    v9 = *(_DWORD *)(a2 + 56);
    if ( v9 )
    {
      v10 = 0;
      v11 = 0;
      do
      {
        v12 = *(unsigned int *)(a2 + 4 * v10 + 120);
        if ( (unsigned int)v12 >= 0x80 )
        {
          v13 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v12 < (unsigned int)v13 )
          {
            v14 = (unsigned int)v12;
            v15 = *(_DWORD *)(v12 + a2) - 64;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( v16 == 1 && v14 + 40 <= v13 )
                {
                  if ( !*(_DWORD *)(v14 + a2 + 12) )
                    break;
                  v17 = a2 + 32;
                  goto LABEL_22;
                }
              }
              else if ( v14 + 56 <= v13 )
              {
                if ( !*(_BYTE *)(v14 + a2 + 10) )
                  break;
                v11 = 1;
                v8 = (_BYTE *)(v14 + a2 + 24);
              }
            }
            else if ( v14 + 40 <= v13 )
            {
              if ( !*(_BYTE *)(v14 + a2 + 10) )
                break;
              v17 = a2 + 24;
LABEL_22:
              v8 = (_BYTE *)(v14 + v17);
              break;
            }
            if ( v11 )
              break;
          }
        }
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (unsigned int)v10 < v9 );
    }
  }
LABEL_24:
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = *(_QWORD *)(v6 + 1144);
  *(_QWORD *)(v21 + 704) = MEMORY[0xFFFFF78000000008] - *(_QWORD *)(v21 + 704);
  v48[7] = v8[2];
  v48[6] = v8[3];
  v48[5] = v8[4];
  v48[4] = v8[5];
  v48[3] = v8[6];
  v48[2] = v8[7];
  v48[1] = v8[8];
  v48[0] = v8[9];
  v47[3] = v8[10];
  v47[2] = v8[11];
  v47[1] = v8[12];
  v47[0] = v8[13];
  if ( *(char *)(a2 + 3) >= 0 )
    goto LABEL_73;
  if ( *(_BYTE *)(a2 + 2) != 40 )
  {
    v29 = *(_BYTE **)(a2 + 32);
    LOBYTE(v8) = *(_BYTE *)(a2 + 11);
    goto LABEL_60;
  }
  LOBYTE(v8) = 0;
  if ( *v5 )
    goto LABEL_58;
  v22 = *(_DWORD *)(a2 + 56);
  if ( !v22 )
    goto LABEL_41;
  v23 = 0;
  v24 = 0;
  while ( 1 )
  {
    v21 = *(unsigned int *)(a2 + 4 * v23 + 120);
    if ( (unsigned int)v21 >= 0x80 )
    {
      v25 = *(unsigned int *)(a2 + 16);
      if ( (unsigned int)v21 < (unsigned int)v25 )
        break;
    }
LABEL_36:
    v23 = (unsigned int)(v23 + 1);
    if ( (unsigned int)v23 >= v22 )
      goto LABEL_41;
  }
  v26 = (unsigned int)v21;
  v27 = *(_DWORD *)(v21 + a2) - 64;
  if ( v27 )
  {
    v21 = (unsigned int)(v27 - 1);
    if ( !(_DWORD)v21 )
    {
      v21 = v26 + 56;
      if ( v26 + 56 <= v25 )
      {
        LOBYTE(v8) = *(_BYTE *)(v26 + a2 + 9);
        v24 = 1;
      }
LABEL_35:
      if ( v24 )
        goto LABEL_41;
      goto LABEL_36;
    }
    if ( (_DWORD)v21 != 1 )
      goto LABEL_35;
  }
  v21 = v26 + 40;
  if ( v26 + 40 > v25 )
    goto LABEL_35;
  LOBYTE(v8) = *(_BYTE *)(v26 + a2 + 9);
LABEL_41:
  if ( *v5 )
  {
LABEL_58:
    v29 = 0;
LABEL_60:
    if ( v29 && (_BYTE)v8 )
    {
      v35 = *v29 & 0x7F;
      if ( (unsigned __int8)(v35 - 114) <= 1u )
      {
        v21 = (unsigned __int64)&v29[(unsigned __int8)v8];
        if ( (unsigned __int64)(v29 + 8) <= v21 )
        {
          v19 = v29[2];
          v18 = v29[1] & 0xF;
          v20 = v29[3];
        }
      }
      else
      {
        v36 = v35 == 112;
        LOBYTE(v21) = v35 - 112;
        if ( v36 || (_BYTE)v21 == 1 )
        {
          v21 = (unsigned __int64)&v29[(unsigned __int8)v8];
          if ( (unsigned __int64)(v29 + 8) <= v21 )
          {
            v37 = (unsigned __int8)v8;
            v18 = v29[2] & 0xF;
            if ( (unsigned int)(unsigned __int8)v29[7] + 8 <= (unsigned __int8)v8 )
              v37 = (unsigned __int8)v29[7] + 8;
            v21 = (unsigned __int64)(v29 + 13);
            v8 = &v29[v37];
            if ( v29 + 13 <= v8 )
              v19 = v29[12];
            if ( v29 + 14 <= v8 )
              v20 = *(_BYTE *)v21;
          }
        }
      }
    }
    goto LABEL_73;
  }
  v28 = *(_DWORD *)(a2 + 56);
  if ( v28 )
  {
    v29 = 0;
    v30 = 0;
    v31 = 0;
    while ( 1 )
    {
      v21 = *(unsigned int *)(a2 + 4 * v30 + 120);
      if ( (unsigned int)v21 >= 0x80 )
      {
        v32 = *(unsigned int *)(a2 + 16);
        if ( (unsigned int)v21 < (unsigned int)v32 )
        {
          v33 = (unsigned int)v21;
          v34 = *(_DWORD *)(v21 + a2) - 64;
          if ( v34 )
          {
            v21 = (unsigned int)(v34 - 1);
            if ( (_DWORD)v21 )
            {
              if ( (_DWORD)v21 == 1 )
              {
                v21 = v33 + 40;
                if ( v33 + 40 <= v32 )
                {
                  v29 = *(_BYTE **)(v33 + a2 + 24);
                  goto LABEL_60;
                }
              }
            }
            else
            {
              v21 = v33 + 56;
              if ( v33 + 56 <= v32 )
              {
                v29 = *(_BYTE **)(v33 + a2 + 16);
                v31 = 1;
              }
            }
          }
          else
          {
            v21 = v33 + 40;
            if ( v33 + 40 <= v32 )
            {
              v29 = *(_BYTE **)(v33 + a2 + 16);
              goto LABEL_60;
            }
          }
          if ( v31 )
            goto LABEL_60;
        }
      }
      v30 = (unsigned int)(v30 + 1);
      if ( (unsigned int)v30 >= v28 )
        goto LABEL_60;
    }
  }
LABEL_73:
  result = dword_14004D060;
  if ( (unsigned int)dword_14004D060 > 5 )
  {
    result = tlgKeywordOn(v21, 0x400000000000LL, v8);
    if ( (_BYTE)result )
    {
      v42 = *(_QWORD *)(*(_QWORD *)(v6 + 1144) + 704LL);
      v53 = &v51;
      v55 = &v49;
      v43 = *(_BYTE *)(v41 + 3);
      v57 = &v43;
      v59 = &v50;
      v61 = v47;
      v63 = v48;
      v65 = &v44;
      v67 = &v45;
      v69 = &v46;
      v51 = v42;
      v54 = 8;
      v56 = 4;
      v58 = 1;
      v60 = 4;
      v62 = 4;
      v64 = 8;
      v44 = v18;
      v66 = 1;
      v45 = v19;
      v68 = 1;
      v46 = v20;
      v70 = 1;
      return tlgWriteTransfer_EtwWriteTransfer(v42, (unsigned __int8 *)&byte_140048C2D, v39, v40, 0xBu, &v52);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400360d4  push    rbp
0x1400360d6  push    rbx
0x1400360d7  push    rsi
0x1400360d8  push    rdi
0x1400360d9  push    r12
0x1400360db  push    r13
0x1400360dd  push    r14
0x1400360df  push    r15
0x1400360e1  lea     rbp, [rsp-18h]
0x1400360e6  sub     rsp, 118h
0x1400360ed  mov     rax, cs:__security_cookie
0x1400360f4  xor     rax, rsp
0x1400360f7  mov     [rbp+50h+var_50], rax
0x1400360fb  cmp     byte ptr [rdx+2], 28h ; '('
0x1400360ff  lea     rbx, [rdx+14h]
0x140036103  mov     r13, [rcx+40h]
0x140036107  mov     r10, rdx
0x14003610a  mov     [rsp+150h+var_10C], r9d
0x14003610f  mov     [rsp+150h+var_110], r8d
0x140036114  jnz     loc_1400361BF
0x14003611a  xor     r8d, r8d
0x14003611d  cmp     [rbx], r8d
0x140036120  jnz     loc_1400361C3
0x140036126  mov     edi, [rdx+38h]
0x140036129  test    edi, edi
0x14003612b  jz      loc_1400361C3
0x140036131  xor     r11d, r11d
0x140036134  xor     sil, sil
0x140036137  mov     ecx, [r10+r11*4+78h]
0x14003613c  cmp     ecx, 80h
0x140036142  jb      short loc_1400361A4
0x140036144  mov     r9d, [r10+10h]
0x140036148  cmp     ecx, r9d
0x14003614b  jnb     short loc_1400361A4
0x14003614d  mov     edx, ecx
0x14003614f  mov     ecx, [rcx+r10]
0x140036153  sub     ecx, 40h ; '@'
0x140036156  jz      short loc_140036196
0x140036158  sub     ecx, 1
0x14003615b  jz      short loc_140036179
0x14003615d  cmp     ecx, 1
0x140036160  jnz     short loc_14003619F
0x140036162  lea     rcx, [rdx+28h]
0x140036166  cmp     rcx, r9
0x140036169  ja      short loc_14003619F
0x14003616b  cmp     dword ptr [rdx+r10+0Ch], 0
0x140036171  jbe     short loc_1400361C3
0x140036173  lea     r8, [r10+20h]
0x140036177  jmp     short loc_1400361BA
0x140036179  lea     rcx, [rdx+38h]
0x14003617d  cmp     rcx, r9
0x140036180  ja      short loc_14003619F
0x140036182  cmp     byte ptr [rdx+r10+0Ah], 0
0x140036188  jbe     short loc_1400361C3
0x14003618a  lea     r8, [r10+18h]
0x14003618e  mov     sil, 1
0x140036191  add     r8, rdx
0x140036194  jmp     short loc_14003619F
0x140036196  lea     rcx, [rdx+28h]
0x14003619a  cmp     rcx, r9
0x14003619d  jbe     short loc_1400361AE
0x14003619f  test    sil, sil
0x1400361a2  jnz     short loc_1400361C3
0x1400361a4  inc     r11d
0x1400361a7  cmp     r11d, edi
0x1400361aa  jb      short loc_140036137
0x1400361ac  jmp     short loc_1400361C3
0x1400361ae  cmp     byte ptr [rdx+r10+0Ah], 0
0x1400361b4  jbe     short loc_1400361C3
0x1400361b6  lea     r8, [r10+18h]
0x1400361ba  add     r8, rdx
0x1400361bd  jmp     short loc_1400361C3
0x1400361bf  lea     r8, [rdx+48h]
0x1400361c3  mov     rax, [r13+478h]
0x1400361ca  xor     dil, dil
0x1400361cd  xor     r12b, r12b
0x1400361d0  xor     r15b, r15b
0x1400361d3  mov     rcx, [rax+2C0h]
0x1400361da  mov     rax, ds:0FFFFF78000000008h
0x1400361e4  sub     rax, rcx
0x1400361e7  mov     rcx, [r13+478h]
0x1400361ee  mov     [rcx+2C0h], rax
0x1400361f5  mov     al, [r8+2]
0x1400361f9  mov     byte ptr [rsp+150h+var_118+7], al
0x1400361fd  mov     al, [r8+3]
0x140036201  mov     byte ptr [rsp+150h+var_118+6], al
0x140036205  mov     al, [r8+4]
0x140036209  mov     byte ptr [rsp+150h+var_118+5], al
0x14003620d  mov     al, [r8+5]
0x140036211  mov     byte ptr [rsp+150h+var_118+4], al
0x140036215  mov     al, [r8+6]
0x140036219  mov     byte ptr [rsp+150h+var_118+3], al
0x14003621d  mov     al, [r8+7]
0x140036221  mov     byte ptr [rsp+150h+var_118+2], al
0x140036225  mov     al, [r8+8]
0x140036229  mov     byte ptr [rsp+150h+var_118+1], al
0x14003622d  mov     al, [r8+9]
0x140036231  mov     byte ptr [rsp+150h+var_118], al
0x140036235  mov     al, [r8+0Ah]
0x140036239  mov     byte ptr [rsp+150h+var_11C+3], al
0x14003623d  mov     al, [r8+0Bh]
0x140036241  mov     byte ptr [rsp+150h+var_11C+2], al
0x140036245  mov     al, [r8+0Ch]
0x140036249  mov     byte ptr [rsp+150h+var_11C+1], al
0x14003624d  mov     al, [r8+0Dh]
0x140036251  mov     byte ptr [rsp+150h+var_11C], al
0x140036255  cmp     [r10+3], dil
0x140036259  jge     loc_1400363FA
0x14003625f  cmp     byte ptr [r10+2], 28h ; '('
0x140036264  jnz     loc_140036367
0x14003626a  xor     r8b, r8b
0x14003626d  cmp     dword ptr [rbx], 0
0x140036270  jnz     loc_140036363
0x140036276  mov     esi, [r10+38h]
0x14003627a  test    esi, esi
0x14003627c  jz      short loc_1400362DF
0x14003627e  xor     r11d, r11d
0x140036281  xor     r14b, r14b
0x140036284  mov     ecx, [r10+r11*4+78h]
0x140036289  cmp     ecx, 80h
0x14003628f  jb      short loc_1400362BD
0x140036291  mov     r9d, [r10+10h]
0x140036295  cmp     ecx, r9d
0x140036298  jnb     short loc_1400362BD
0x14003629a  mov     edx, ecx
0x14003629c  mov     ecx, [rcx+r10]
0x1400362a0  sub     ecx, 40h ; '@'
0x1400362a3  jz      short loc_1400362AF
0x1400362a5  sub     ecx, 1
0x1400362a8  jz      short loc_1400362C7
0x1400362aa  cmp     ecx, 1
0x1400362ad  jnz     short loc_1400362B8
0x1400362af  lea     rcx, [rdx+28h]
0x1400362b3  cmp     rcx, r9
0x1400362b6  jbe     short loc_1400362DA
0x1400362b8  test    r14b, r14b
0x1400362bb  jnz     short loc_1400362DF
0x1400362bd  inc     r11d
0x1400362c0  cmp     r11d, esi
0x1400362c3  jb      short loc_140036284
0x1400362c5  jmp     short loc_1400362DF
0x1400362c7  lea     rcx, [rdx+38h]
0x1400362cb  cmp     rcx, r9
0x1400362ce  ja      short loc_1400362B8
0x1400362d0  mov     r8b, [rdx+r10+9]
0x1400362d5  mov     r14b, 1
0x1400362d8  jmp     short loc_1400362B8
0x1400362da  mov     r8b, [rdx+r10+9]
0x1400362df  cmp     dword ptr [rbx], 0
0x1400362e2  jnz     short loc_140036363
0x1400362e4  mov     esi, [r10+38h]
0x1400362e8  test    esi, esi
0x1400362ea  jz      loc_1400363FA
0x1400362f0  xor     edx, edx
0x1400362f2  xor     ebx, ebx
0x1400362f4  xor     r14b, r14b
0x1400362f7  mov     ecx, [r10+rbx*4+78h]
0x1400362fc  cmp     ecx, 80h
0x140036302  jb      short loc_140036354
0x140036304  mov     r11d, [r10+10h]
0x140036308  cmp     ecx, r11d
0x14003630b  jnb     short loc_140036354
0x14003630d  mov     r9d, ecx
0x140036310  mov     ecx, [rcx+r10]
0x140036314  sub     ecx, 40h ; '@'
0x140036317  jz      short loc_140036346
0x140036319  sub     ecx, 1
0x14003631c  jz      short loc_140036333
0x14003631e  cmp     ecx, 1
0x140036321  jnz     short loc_14003634F
0x140036323  lea     rcx, [r9+28h]
0x140036327  cmp     rcx, r11
0x14003632a  ja      short loc_14003634F
0x14003632c  mov     rdx, [r9+r10+18h]
0x140036331  jmp     short loc_14003636F
0x140036333  lea     rcx, [r9+38h]
0x140036337  cmp     rcx, r11
0x14003633a  ja      short loc_14003634F
0x14003633c  mov     rdx, [r9+r10+10h]
0x140036341  mov     r14b, 1
0x140036344  jmp     short loc_14003634F
0x140036346  lea     rcx, [r9+28h]
0x14003634a  cmp     rcx, r11
0x14003634d  jbe     short loc_14003635C
0x14003634f  test    r14b, r14b
0x140036352  jnz     short loc_14003636F
0x140036354  inc     ebx
0x140036356  cmp     ebx, esi
0x140036358  jb      short loc_1400362F7
0x14003635a  jmp     short loc_14003636F
0x14003635c  mov     rdx, [r9+r10+10h]
0x140036361  jmp     short loc_14003636F
0x140036363  xor     edx, edx
0x140036365  jmp     short loc_14003636F
0x140036367  mov     rdx, [r10+20h]
0x14003636b  mov     r8b, [r10+0Bh]
0x14003636f  test    rdx, rdx
0x140036372  jz      loc_1400363FA
0x140036378  test    r8b, r8b
0x14003637b  jz      short loc_1400363FA
0x14003637d  mov     cl, [rdx]
0x14003637f  and     cl, 7Fh
0x140036382  lea     eax, [rcx-72h]
0x140036385  cmp     al, 1
0x140036387  jbe     short loc_1400363DA
0x140036389  sub     cl, 70h ; 'p'
0x14003638c  cmp     cl, 1
0x14003638f  ja      short loc_1400363FA
0x140036391  movzx   ecx, r8b
0x140036395  lea     rax, [rdx+8]
0x140036399  add     rcx, rdx
0x14003639c  cmp     rax, rcx
0x14003639f  ja      short loc_1400363FA
0x1400363a1  movzx   ecx, byte ptr [rdx+7]
0x1400363a5  mov     dil, [rdx+2]
0x1400363a9  add     ecx, 8
0x1400363ac  movzx   eax, r8b
0x1400363b0  and     dil, 0Fh
0x1400363b4  cmp     ecx, eax
0x1400363b6  cmovbe  eax, ecx
0x1400363b9  lea     rcx, [rdx+0Dh]
0x1400363bd  mov     r8d, eax
0x1400363c0  add     r8, rdx
0x1400363c3  cmp     rcx, r8
0x1400363c6  ja      short loc_1400363CC
0x1400363c8  mov     r12b, [rdx+0Ch]
0x1400363cc  lea     rax, [rdx+0Eh]
0x1400363d0  cmp     rax, r8
0x1400363d3  ja      short loc_1400363FA
0x1400363d5  mov     r15b, [rcx]
0x1400363d8  jmp     short loc_1400363FA
0x1400363da  movzx   ecx, r8b
0x1400363de  lea     rax, [rdx+8]
0x1400363e2  add     rcx, rdx
0x1400363e5  cmp     rax, rcx
0x1400363e8  ja      short loc_1400363FA
0x1400363ea  mov     dil, [rdx+1]
0x1400363ee  mov     r12b, [rdx+2]
0x1400363f2  and     dil, 0Fh
0x1400363f6  mov     r15b, [rdx+3]
0x1400363fa  mov     eax, cs:dword_14004D060
0x140036400  cmp     eax, 5
0x140036403  jbe     loc_140036525
0x140036409  mov     rdx, 400000000000h
0x140036413  call    _tlgKeywordOn
0x140036418  test    al, al
0x14003641a  jz      loc_140036525
0x140036420  mov     rax, [r13+478h]
0x140036427  lea     rdx, byte_140048C2D; int
0x14003642e  mov     rcx, [rax+2C0h]; int
0x140036435  lea     rax, [rsp+150h+var_108]
0x14003643a  mov     [rsp+150h+var_E0], rax
0x14003643f  mov     eax, [rsp+150h+var_110]
0x140036443  mov     [rsp+150h+var_110], eax
0x140036447  lea     rax, [rsp+150h+var_110]
0x14003644c  mov     [rbp+50h+var_D0], rax
0x140036450  mov     al, [r10+3]
0x140036454  mov     [rsp+150h+var_120], al
0x140036458  lea     rax, [rsp+150h+var_120]
0x14003645d  mov     [rbp+50h+var_C0], rax
0x140036461  mov     eax, [rsp+150h+var_10C]
0x140036465  mov     [rsp+150h+var_10C], eax
0x140036469  lea     rax, [rsp+150h+var_10C]
0x14003646e  mov     [rbp+50h+var_B0], rax
0x140036472  mov     eax, [rsp+150h+var_11C]
0x140036476  mov     [rsp+150h+var_11C], eax
0x14003647a  lea     rax, [rsp+150h+var_11C]
0x14003647f  mov     [rbp+50h+var_A0], rax
0x140036483  mov     rax, [rsp+150h+var_118]
0x140036488  mov     [rsp+150h+var_118], rax
0x14003648d  lea     rax, [rsp+150h+var_118]
0x140036492  mov     [rbp+50h+var_90], rax
0x140036496  lea     rax, [rsp+150h+var_11F]
0x14003649b  mov     [rbp+50h+var_80], rax
0x14003649f  lea     rax, [rsp+150h+var_11E]
0x1400364a4  mov     [rbp+50h+var_70], rax
0x1400364a8  lea     rax, [rsp+150h+var_11D]
0x1400364ad  mov     [rbp+50h+var_60], rax
0x1400364b1  lea     rax, [rsp+150h+var_100]
0x1400364b6  mov     [rsp+150h+var_128], rax; __int64
0x1400364bb  mov     [rsp+150h+var_130], 0Bh; ULONG
0x1400364c3  mov     [rsp+150h+var_108], rcx
0x1400364c8  mov     [rsp+150h+var_D8], 8
0x1400364d1  mov     [rbp+50h+var_C8], 4
0x1400364d9  mov     [rbp+50h+var_B8], 1
0x1400364e1  mov     [rbp+50h+var_A8], 4
0x1400364e9  mov     [rbp+50h+var_98], 4
0x1400364f1  mov     [rbp+50h+var_88], 8
0x1400364f9  mov     [rsp+150h+var_11F], dil
0x1400364fe  mov     [rbp+50h+var_78], 1
0x140036506  mov     [rsp+150h+var_11E], r12b
0x14003650b  mov     [rbp+50h+var_68], 1
0x140036513  mov     [rsp+150h+var_11D], r15b
0x140036518  mov     [rbp+50h+var_58], 1
0x140036520  call    _tlgWriteTransfer_EtwWriteTransfer
0x140036525  mov     rcx, [rbp+50h+var_50]
0x140036529  xor     rcx, rsp; StackCookie
0x14003652c  call    __security_check_cookie
0x140036531  add     rsp, 118h
0x140036538  pop     r15
  ... truncated ...
```
