# ClasspBuildRequestEx

- ea: `0x140038294`
- end: `0x140038766`
- name: `ClasspBuildRequestEx`
- size: `1234`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140037db0`

## callees

- `0x14000f3e0`
- `0x140012e18`
- `0x14001feac`
- `0x140038294`
- `0x14003e940`

## pseudocode

```c
void __fastcall ClasspBuildRequestEx(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v7; // rbp
  char v8; // dl
  __int64 v9; // r8
  int v10; // ecx
  _SENSE_DATA *SenseData; // r9
  char v12; // r11
  __int64 i; // r10
  __int64 v14; // rcx
  unsigned __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // ecx
  UCHAR v19; // al
  char v20; // r11
  __int64 v21; // r10
  __int64 v22; // rcx
  unsigned __int64 v23; // r8
  __int64 v24; // rdx
  int v25; // ecx
  int v26; // ecx
  char v27; // cl
  __int64 v28; // rax
  unsigned int v29; // edx
  bool v30; // zf
  char v31; // r10
  __int64 j; // r9
  __int64 v33; // rcx
  unsigned __int64 v34; // r8
  __int64 v35; // rdx
  int v36; // ecx
  int v37; // ecx
  char *v38; // rdi
  unsigned int v39; // r11d
  __int64 v40; // r9
  char v41; // r10
  __int64 v42; // rcx
  unsigned __int64 v43; // r8
  __int64 v44; // rdx
  int v45; // ecx
  int v46; // ecx
  char *v47; // rcx
  volatile unsigned __int8 SectorShift; // cl
  unsigned int v49; // edx
  unsigned int v50; // edx
  char v51; // al
  _DWORD *v52; // rdx
  char v53; // r8
  _DWORD *v54; // rcx
  unsigned int SrbFlags; // eax
  __int64 v56; // rax

  if ( a3 )
  {
    v3 = *(_QWORD *)(a2 + 184);
    v7 = *(_QWORD *)(v3 + 24) >> FdoExtension->SectorShift;
    if ( FdoExtension->AdapterDescriptor->SrbType == 1 )
    {
      if ( (int)InitializeStorageRequestBlock(a3) < 0 )
        return;
      *(_DWORD *)(a3 + 20) = 0;
    }
    else
    {
      memset((void *)(a3 + 3), 0, 0x55u);
      *(_WORD *)a3 = 88;
      *(_BYTE *)(a3 + 2) = 0;
    }
    v8 = *(_BYTE *)(a3 + 2);
    if ( v8 == 40 )
      *(_QWORD *)(a3 + 80) = a2;
    else
      *(_QWORD *)(a3 + 48) = a2;
    v9 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 32LL) + *(unsigned int *)(*(_QWORD *)(a2 + 8) + 44LL);
    if ( v8 == 40 )
      *(_QWORD *)(a3 + 64) = v9;
    else
      *(_QWORD *)(a3 + 24) = v9;
    v10 = *(_DWORD *)(v3 + 8);
    if ( v8 == 40 )
    {
      *(_DWORD *)(a3 + 60) = v10;
      *(_WORD *)(a3 + 38) = 32;
    }
    else
    {
      *(_DWORD *)(a3 + 16) = v10;
      *(_BYTE *)(a3 + 9) = 32;
      *(_DWORD *)(a3 + 64) = v7;
    }
    SenseData = FdoExtension->SenseData;
    if ( v8 == 40 )
    {
      if ( !*(_DWORD *)(a3 + 20) )
      {
        v12 = 0;
        for ( i = 0; (unsigned int)i < *(_DWORD *)(a3 + 56); i = (unsigned int)(i + 1) )
        {
          v14 = *(unsigned int *)(a3 + 4 * i + 120);
          if ( (unsigned int)v14 >= 0x80 )
          {
            v15 = *(unsigned int *)(a3 + 16);
            if ( (unsigned int)v14 < (unsigned int)v15 )
            {
              v16 = (unsigned int)v14;
              v17 = *(_DWORD *)(v14 + a3) - 64;
              if ( v17 )
              {
                v18 = v17 - 1;
                if ( v18 )
                {
                  if ( v18 == 1 && v16 + 40 <= v15 )
                  {
                    *(_QWORD *)(v16 + a3 + 24) = SenseData;
                    break;
                  }
                }
                else if ( v16 + 56 <= v15 )
                {
                  v12 = 1;
                  *(_QWORD *)(v16 + a3 + 16) = SenseData;
                }
              }
              else if ( v16 + 40 <= v15 )
              {
                *(_QWORD *)(v16 + a3 + 16) = SenseData;
                break;
              }
              if ( v12 )
                break;
            }
          }
        }
      }
    }
    else
    {
      *(_QWORD *)(a3 + 32) = SenseData;
    }
    v19 = GET_FDO_EXTENSON_SENSE_DATA_LENGTH(FdoExtension);
    if ( *(_BYTE *)(a3 + 2) == 40 )
    {
      if ( !*(_DWORD *)(a3 + 20) )
      {
        v20 = 0;
        v21 = 0;
        if ( *(_DWORD *)(a3 + 56) )
        {
          while ( 1 )
          {
            v22 = *(unsigned int *)(a3 + 4 * v21 + 120);
            if ( (unsigned int)v22 >= 0x80 )
            {
              v23 = *(unsigned int *)(a3 + 16);
              if ( (unsigned int)v22 < (unsigned int)v23 )
                break;
            }
LABEL_43:
            v21 = (unsigned int)(v21 + 1);
            if ( (unsigned int)v21 >= *(_DWORD *)(a3 + 56) )
              goto LABEL_49;
          }
          v24 = (unsigned int)v22;
          v25 = *(_DWORD *)(v22 + a3) - 64;
          if ( !v25 )
            goto LABEL_41;
          v26 = v25 - 1;
          if ( v26 )
          {
            if ( v26 == 1 )
            {
LABEL_41:
              if ( v24 + 40 <= v23 )
              {
                *(_BYTE *)(v24 + a3 + 9) = v19;
                goto LABEL_49;
              }
            }
          }
          else if ( v24 + 56 <= v23 )
          {
            v20 = 1;
            *(_BYTE *)(v24 + a3 + 9) = v19;
          }
          if ( v20 )
            goto LABEL_49;
          goto LABEL_43;
        }
      }
    }
    else
    {
      *(_BYTE *)(a3 + 11) = v19;
    }
LABEL_49:
    v27 = *(_BYTE *)(a3 + 2);
    v28 = 60;
    if ( v27 != 40 )
      v28 = 16;
    v29 = FdoExtension->TimeOutValue * ((unsigned int)(*(_DWORD *)(v28 + a3) + 0xFFFF) >> 16);
    if ( v27 == 40 )
    {
      v30 = *(_DWORD *)(a3 + 20) == 0;
      *(_DWORD *)(a3 + 40) = v29;
      if ( v30 )
      {
        v31 = 0;
        for ( j = 0; (unsigned int)j < *(_DWORD *)(a3 + 56); j = (unsigned int)(j + 1) )
        {
          v33 = *(unsigned int *)(a3 + 4 * j + 120);
          if ( (unsigned int)v33 >= 0x80 )
          {
            v34 = *(unsigned int *)(a3 + 16);
            if ( (unsigned int)v33 < (unsigned int)v34 )
            {
              v35 = (unsigned int)v33;
              v36 = *(_DWORD *)(v33 + a3) - 64;
              if ( v36 )
              {
                v37 = v36 - 1;
                if ( v37 )
                {
                  if ( v37 == 1 && v35 + 40 <= v34 )
                    break;
                }
                else if ( v35 + 56 <= v34 )
                {
                  v31 = 1;
                  *(_BYTE *)(v35 + a3 + 10) = 10;
                }
              }
              else if ( v35 + 40 <= v34 )
              {
                *(_BYTE *)(v35 + a3 + 10) = 10;
                break;
              }
              if ( v31 )
                break;
            }
          }
        }
      }
    }
    else
    {
      *(_DWORD *)(a3 + 20) = v29;
      *(_BYTE *)(a3 + 10) = 10;
    }
    if ( *(_BYTE *)(a3 + 2) != 40 )
    {
      v38 = (char *)(a3 + 72);
      goto LABEL_92;
    }
    v38 = 0;
    if ( !*(_DWORD *)(a3 + 20) )
    {
      v39 = *(_DWORD *)(a3 + 56);
      if ( v39 )
      {
        v40 = 0;
        v41 = 0;
        do
        {
          v42 = *(unsigned int *)(a3 + 4 * v40 + 120);
          if ( (unsigned int)v42 >= 0x80 )
          {
            v43 = *(unsigned int *)(a3 + 16);
            if ( (unsigned int)v42 < (unsigned int)v43 )
            {
              v44 = (unsigned int)v42;
              v45 = *(_DWORD *)(v42 + a3) - 64;
              if ( v45 )
              {
                v46 = v45 - 1;
                if ( v46 )
                {
                  if ( v46 == 1 && v44 + 40 <= v43 )
                  {
                    v47 = (char *)(v44 + a3 + 32);
                    if ( !*(_DWORD *)(v44 + a3 + 12) )
                      v47 = v38;
                    v38 = v47;
                    break;
                  }
                }
                else if ( v44 + 56 <= v43 )
                {
                  if ( !*(_BYTE *)(v44 + a3 + 10) )
                    break;
                  v41 = 1;
                  v38 = (char *)(v44 + a3 + 24);
                }
              }
              else if ( v44 + 40 <= v43 )
              {
                if ( *(_BYTE *)(v44 + a3 + 10) )
                  v38 = (char *)(v44 + a3 + 24);
                break;
              }
              if ( v41 )
                break;
            }
          }
          v40 = (unsigned int)(v40 + 1);
        }
        while ( (unsigned int)v40 < v39 );
      }
    }
LABEL_92:
    SectorShift = FdoExtension->SectorShift;
    v49 = *(_DWORD *)(v3 + 8);
    v38[2] = BYTE3(v7);
    v38[3] = BYTE2(v7);
    v50 = v49 >> SectorShift;
    v38[4] = BYTE1(v7);
    v38[7] = BYTE1(v50);
    v38[5] = v7;
    v38[8] = v50;
    if ( *(_BYTE *)v3 == 3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids);
      }
      if ( *(_BYTE *)(a3 + 2) == 40 )
        *(_DWORD *)(a3 + 24) |= 0x40u;
      else
        *(_DWORD *)(a3 + 12) |= 0x40u;
      v51 = 40;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids);
      }
      if ( *(_BYTE *)(a3 + 2) == 40 )
        *(_DWORD *)(a3 + 24) |= 0x80u;
      else
        *(_DWORD *)(a3 + 12) |= 0x80u;
      v51 = 42;
    }
    *v38 = v51;
    v52 = (_DWORD *)(a3 + 12);
    if ( (*(_BYTE *)(v3 + 2) & 4) != 0 )
    {
      v38[1] ^= (v38[1] ^ (8 * FdoExtension->CdbForceUnitAccess)) & 8;
      v54 = (_DWORD *)(a3 + 24);
      v53 = *(_BYTE *)(a3 + 2);
    }
    else
    {
      v53 = *(_BYTE *)(a3 + 2);
      v54 = (_DWORD *)(a3 + 24);
      if ( v53 == 40 )
        *v54 |= 0x200u;
      else
        *v52 |= 0x200u;
    }
    if ( (*(_DWORD *)(a2 + 16) & 0x42) != 0 )
    {
      if ( v53 == 40 )
      {
        v54 = (_DWORD *)(a3 + 24);
        v53 = 40;
        *(_DWORD *)(a3 + 24) |= 0x40000000u;
      }
      else
      {
        v52 = (_DWORD *)(a3 + 12);
        *(_DWORD *)(a3 + 12) |= 0x40000000u;
      }
    }
    SrbFlags = FdoExtension->SrbFlags;
    if ( v53 == 40 )
      *v54 |= SrbFlags;
    else
      *v52 |= SrbFlags;
    *(_BYTE *)(v3 - 72) = 15;
    *(_QWORD *)(v3 - 64) = a3;
    *(_QWORD *)(v3 + 32) = 4;
    v56 = *(_QWORD *)(a2 + 184);
    *(_QWORD *)(v56 - 16) = ClassIoComplete;
    *(_QWORD *)(v56 - 8) = a3;
    *(_BYTE *)(v56 - 69) = -32;
  }
}

```

## disassembly

```asm
0x140038294  test    r8, r8
0x140038297  jz      locret_140038764
0x14003829d  mov     [rsp+arg_0], rbx
0x1400382a2  mov     [rsp+arg_10], rbp
0x1400382a7  push    rsi
0x1400382a8  push    rdi
0x1400382a9  push    r13
0x1400382ab  push    r14
0x1400382ad  push    r15
0x1400382af  sub     rsp, 30h
0x1400382b3  mov     rsi, [rdx+0B8h]
0x1400382ba  mov     r14, rcx
0x1400382bd  mov     cl, [rcx+282h]
0x1400382c3  mov     edi, 1
0x1400382c8  mov     rbx, r8
0x1400382cb  mov     r15, rdx
0x1400382ce  mov     rax, [r14+210h]
0x1400382d5  mov     rbp, [rsi+18h]
0x1400382d9  shr     rbp, cl
0x1400382dc  mov     [rsp+58h+arg_8], ebp
0x1400382e0  cmp     [rax+1Eh], dil
0x1400382e4  jnz     short loc_140038315
0x1400382e6  xor     eax, eax
0x1400382e8  mov     [rsp+58h+var_38], 40h ; '@'
0x1400382f0  movzx   edx, ax
0x1400382f3  mov     r9d, edi
0x1400382f6  mov     r8d, 0B8h
0x1400382fc  mov     rcx, rbx
0x1400382ff  call    InitializeStorageRequestBlock
0x140038304  test    eax, eax
0x140038306  js      loc_14003874E
0x14003830c  mov     dword ptr [rbx+14h], 0
0x140038313  jmp     short loc_14003832D
0x140038315  xor     edx, edx; Val
0x140038317  lea     rcx, [r8+3]; void *
0x14003831b  lea     r8d, [rdx+55h]; Size
0x14003831f  call    memset
0x140038324  mov     word ptr [rbx], 58h ; 'X'
0x140038329  mov     byte ptr [rbx+2], 0
0x14003832d  mov     dl, [rbx+2]
0x140038330  mov     r13b, 28h ; '('
0x140038333  cmp     dl, r13b
0x140038336  jnz     short loc_14003833E
0x140038338  mov     [rbx+50h], r15
0x14003833c  jmp     short loc_140038342
0x14003833e  mov     [rbx+30h], r15
0x140038342  mov     rax, [r15+8]
0x140038346  mov     r8d, [rax+2Ch]
0x14003834a  add     r8, [rax+20h]
0x14003834e  cmp     dl, r13b
0x140038351  jnz     short loc_140038359
0x140038353  mov     [rbx+40h], r8
0x140038357  jmp     short loc_14003835D
0x140038359  mov     [rbx+18h], r8
0x14003835d  mov     ecx, [rsi+8]
0x140038360  jnz     short loc_14003836D
0x140038362  mov     [rbx+3Ch], ecx
0x140038365  mov     word ptr [rbx+26h], 20h ; ' '
0x14003836b  jmp     short loc_140038377
0x14003836d  mov     [rbx+10h], ecx
0x140038370  mov     byte ptr [rbx+9], 20h ; ' '
0x140038374  mov     [rbx+40h], ebp
0x140038377  mov     r9, [r14+240h]
0x14003837e  jnz     short loc_1400383FD
0x140038380  cmp     dword ptr [rbx+14h], 0
0x140038384  jnz     short loc_140038401
0x140038386  xor     r11b, r11b
0x140038389  xor     r10d, r10d
0x14003838c  cmp     [rbx+38h], r10d
0x140038390  jbe     short loc_140038401
0x140038392  mov     ecx, [rbx+r10*4+78h]
0x140038397  cmp     ecx, 80h
0x14003839d  jb      short loc_1400383EB
0x14003839f  mov     r8d, [rbx+10h]
0x1400383a3  cmp     ecx, r8d
0x1400383a6  jnb     short loc_1400383EB
0x1400383a8  mov     edx, ecx
0x1400383aa  mov     ecx, [rcx+rbx]
0x1400383ad  sub     ecx, 40h ; '@'
0x1400383b0  jz      short loc_1400383DD
0x1400383b2  sub     ecx, edi
0x1400383b4  jz      short loc_1400383CA
0x1400383b6  cmp     ecx, edi
0x1400383b8  jnz     short loc_1400383E6
0x1400383ba  lea     rcx, [rdx+28h]
0x1400383be  cmp     rcx, r8
0x1400383c1  ja      short loc_1400383E6
0x1400383c3  mov     [rdx+rbx+18h], r9
0x1400383c8  jmp     short loc_140038401
0x1400383ca  lea     rcx, [rdx+38h]
0x1400383ce  cmp     rcx, r8
0x1400383d1  ja      short loc_1400383E6
0x1400383d3  mov     r11b, dil
0x1400383d6  mov     [rdx+rbx+10h], r9
0x1400383db  jmp     short loc_1400383E6
0x1400383dd  lea     rcx, [rdx+28h]
0x1400383e1  cmp     rcx, r8
0x1400383e4  jbe     short loc_1400383F6
0x1400383e6  test    r11b, r11b
0x1400383e9  jnz     short loc_140038401
0x1400383eb  add     r10d, edi
0x1400383ee  cmp     r10d, [rbx+38h]
0x1400383f2  jb      short loc_140038392
0x1400383f4  jmp     short loc_140038401
0x1400383f6  mov     [rdx+rbx+10h], r9
0x1400383fb  jmp     short loc_140038401
0x1400383fd  mov     [rbx+20h], r9
0x140038401  mov     rcx, r14; FdoExtension
0x140038404  call    GET_FDO_EXTENSON_SENSE_DATA_LENGTH
0x140038409  cmp     [rbx+2], r13b
0x14003840d  jnz     short loc_14003847A
0x14003840f  cmp     dword ptr [rbx+14h], 0
0x140038413  jnz     short loc_14003847D
0x140038415  xor     r11b, r11b
0x140038418  xor     r10d, r10d
0x14003841b  cmp     [rbx+38h], r10d
0x14003841f  jbe     short loc_14003847D
0x140038421  mov     ecx, [rbx+r10*4+78h]
0x140038426  cmp     ecx, 80h
0x14003842c  jb      short loc_140038457
0x14003842e  mov     r8d, [rbx+10h]
0x140038432  cmp     ecx, r8d
0x140038435  jnb     short loc_140038457
0x140038437  mov     edx, ecx
0x140038439  mov     ecx, [rcx+rbx]
0x14003843c  sub     ecx, 40h ; '@'
0x14003843f  jz      short loc_140038449
0x140038441  sub     ecx, edi
0x140038443  jz      short loc_140038462
0x140038445  cmp     ecx, edi
0x140038447  jnz     short loc_140038452
0x140038449  lea     rcx, [rdx+28h]
0x14003844d  cmp     rcx, r8
0x140038450  jbe     short loc_140038474
0x140038452  test    r11b, r11b
0x140038455  jnz     short loc_14003847D
0x140038457  add     r10d, edi
0x14003845a  cmp     r10d, [rbx+38h]
0x14003845e  jb      short loc_140038421
0x140038460  jmp     short loc_14003847D
0x140038462  lea     rcx, [rdx+38h]
0x140038466  cmp     rcx, r8
0x140038469  ja      short loc_140038452
0x14003846b  mov     r11b, dil
0x14003846e  mov     [rdx+rbx+9], al
0x140038472  jmp     short loc_140038452
0x140038474  mov     [rdx+rbx+9], al
0x140038478  jmp     short loc_14003847D
0x14003847a  mov     [rbx+0Bh], al
0x14003847d  mov     cl, [rbx+2]
0x140038480  mov     eax, 3Ch ; '<'
0x140038485  cmp     cl, r13b
0x140038488  lea     edx, [rax-2Ch]
0x14003848b  cmovnz  eax, edx
0x14003848e  mov     edx, [rax+rbx]
0x140038491  add     edx, 0FFFFh
0x140038497  shr     edx, 10h
0x14003849a  imul    edx, [r14+248h]
0x1400384a2  cmp     cl, r13b
0x1400384a5  jnz     short loc_140038522
0x1400384a7  cmp     dword ptr [rbx+14h], 0
0x1400384ab  mov     [rbx+28h], edx
0x1400384ae  jnz     short loc_140038529
0x1400384b0  xor     r10b, r10b
0x1400384b3  xor     r9d, r9d
0x1400384b6  cmp     [rbx+38h], r9d
0x1400384ba  jbe     short loc_140038529
0x1400384bc  mov     ecx, [rbx+r9*4+78h]
0x1400384c1  cmp     ecx, 80h
0x1400384c7  jb      short loc_140038510
0x1400384c9  mov     r8d, [rbx+10h]
0x1400384cd  cmp     ecx, r8d
0x1400384d0  jnb     short loc_140038510
0x1400384d2  mov     edx, ecx
0x1400384d4  mov     ecx, [rcx+rbx]
0x1400384d7  sub     ecx, 40h ; '@'
0x1400384da  jz      short loc_140038502
0x1400384dc  sub     ecx, edi
0x1400384de  jz      short loc_1400384EF
0x1400384e0  cmp     ecx, edi
0x1400384e2  jnz     short loc_14003850B
0x1400384e4  lea     rcx, [rdx+28h]
0x1400384e8  cmp     rcx, r8
0x1400384eb  jbe     short loc_140038529
0x1400384ed  jmp     short loc_14003850B
0x1400384ef  lea     rcx, [rdx+38h]
0x1400384f3  cmp     rcx, r8
0x1400384f6  ja      short loc_14003850B
0x1400384f8  mov     r10b, dil
0x1400384fb  mov     byte ptr [rdx+rbx+0Ah], 0Ah
0x140038500  jmp     short loc_14003850B
0x140038502  lea     rcx, [rdx+28h]
0x140038506  cmp     rcx, r8
0x140038509  jbe     short loc_14003851B
0x14003850b  test    r10b, r10b
0x14003850e  jnz     short loc_140038529
0x140038510  add     r9d, edi
0x140038513  cmp     r9d, [rbx+38h]
0x140038517  jb      short loc_1400384BC
0x140038519  jmp     short loc_140038529
0x14003851b  mov     byte ptr [rdx+rbx+0Ah], 0Ah
0x140038520  jmp     short loc_140038529
0x140038522  mov     [rbx+14h], edx
0x140038525  mov     byte ptr [rbx+0Ah], 0Ah
0x140038529  cmp     [rbx+2], r13b
0x14003852d  jnz     loc_1400385DD
0x140038533  xor     edi, edi
0x140038535  cmp     [rbx+14h], edi
0x140038538  jnz     loc_1400385E1
0x14003853e  mov     r11d, [rbx+38h]
0x140038542  test    r11d, r11d
0x140038545  jz      loc_1400385E1
0x14003854b  xor     r9d, r9d
0x14003854e  xor     r10b, r10b
0x140038551  mov     ecx, [rbx+r9*4+78h]
0x140038556  cmp     ecx, 80h
0x14003855c  jb      short loc_1400385C3
0x14003855e  mov     r8d, [rbx+10h]
0x140038562  cmp     ecx, r8d
0x140038565  jnb     short loc_1400385C3
0x140038567  mov     edx, ecx
0x140038569  mov     ecx, [rcx+rbx]
0x14003856c  sub     ecx, 40h ; '@'
0x14003856f  jz      short loc_1400385B5
0x140038571  sub     ecx, 1
0x140038574  jz      short loc_140038599
0x140038576  cmp     ecx, 1
0x140038579  jnz     short loc_1400385BE
0x14003857b  lea     rcx, [rdx+28h]
0x14003857f  cmp     rcx, r8
0x140038582  ja      short loc_1400385BE
0x140038584  lea     rcx, [rbx+20h]
0x140038588  add     rcx, rdx
0x14003858b  cmp     dword ptr [rdx+rbx+0Ch], 0
0x140038590  cmovz   rcx, rdi
0x140038594  mov     rdi, rcx
0x140038597  jmp     short loc_1400385E1
0x140038599  lea     rcx, [rdx+38h]
0x14003859d  cmp     rcx, r8
0x1400385a0  ja      short loc_1400385BE
0x1400385a2  cmp     byte ptr [rdx+rbx+0Ah], 0
0x1400385a7  jbe     short loc_1400385E1
0x1400385a9  lea     rdi, [rbx+18h]
0x1400385ad  mov     r10b, 1
0x1400385b0  add     rdi, rdx
0x1400385b3  jmp     short loc_1400385BE
0x1400385b5  lea     rcx, [rdx+28h]
0x1400385b9  cmp     rcx, r8
0x1400385bc  jbe     short loc_1400385CD
0x1400385be  test    r10b, r10b
0x1400385c1  jnz     short loc_1400385E1
0x1400385c3  inc     r9d
0x1400385c6  cmp     r9d, r11d
0x1400385c9  jb      short loc_140038551
0x1400385cb  jmp     short loc_1400385E1
0x1400385cd  cmp     byte ptr [rdx+rbx+0Ah], 0
0x1400385d2  jbe     short loc_1400385E1
0x1400385d4  lea     rdi, [rbx+18h]
0x1400385d8  add     rdi, rdx
0x1400385db  jmp     short loc_1400385E1
0x1400385dd  lea     rdi, [rbx+48h]
0x1400385e1  movzx   ecx, byte ptr [r14+282h]
0x1400385e9  mov     edx, [rsi+8]
0x1400385ec  mov     al, byte ptr [rsp+58h+arg_8+3]
0x1400385f0  mov     [rdi+2], al
0x1400385f3  mov     al, byte ptr [rsp+58h+arg_8+2]
0x1400385f7  mov     [rdi+3], al
0x1400385fa  mov     al, byte ptr [rsp+58h+arg_8+1]
0x1400385fe  shr     edx, cl
0x140038600  mov     [rdi+4], al
0x140038603  movzx   eax, dx
0x140038606  shr     ax, 8
0x14003860a  mov     [rdi+7], al
0x14003860d  mov     [rdi+5], bpl
0x140038611  mov     [rdi+8], dl
0x140038614  cmp     byte ptr [rsi], 3
0x140038617  jnz     short loc_140038663
0x140038619  mov     rcx, cs:WPP_GLOBAL_Control
0x140038620  lea     rax, WPP_GLOBAL_Control
0x140038627  cmp     rcx, rax
0x14003862a  jz      short loc_14003864E
0x14003862c  mov     eax, [rcx+2Ch]
0x14003862f  test    al, 8
0x140038631  jz      short loc_14003864E
0x140038633  cmp     byte ptr [rcx+29h], 4
0x140038637  jb      short loc_14003864E
0x140038639  mov     rcx, [rcx+18h]
0x14003863d  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x140038644  mov     edx, 12h
0x140038649  call    WPP_SF_
0x14003864e  cmp     [rbx+2], r13b
0x140038652  jnz     short loc_14003865A
0x140038654  or      dword ptr [rbx+18h], 40h
0x140038658  jmp     short loc_14003865E
0x14003865a  or      dword ptr [rbx+0Ch], 40h
0x14003865e  mov     al, r13b
0x140038661  jmp     short loc_1400386AC
0x140038663  mov     rcx, cs:WPP_GLOBAL_Control
0x14003866a  lea     rax, WPP_GLOBAL_Control
0x140038671  cmp     rcx, rax
  ... truncated ...
```
