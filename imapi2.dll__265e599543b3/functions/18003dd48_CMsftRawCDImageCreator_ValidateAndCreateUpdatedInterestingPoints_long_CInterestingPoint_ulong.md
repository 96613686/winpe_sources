# CMsftRawCDImageCreator::ValidateAndCreateUpdatedInterestingPoints(long,CInterestingPoint * *,ulong *)

- ea: `0x18003dd48`
- end: `0x18003e450`
- name: `?ValidateAndCreateUpdatedInterestingPoints@CMsftRawCDImageCreator@@AEBAJJPEAPEAVCInterestingPoint@@PEAK@Z`
- size: `1800`
- prototype: `__int64 __fastcall(CMsftRawCDImageCreator *__hidden this, int, struct CInterestingPoint **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18003c7f0`
- `0x18003cf30`

## callees

- `0x18000fdc8`
- `0x180010e70`
- `0x1800140f4`
- `0x180014134`
- `0x180014180`
- `0x180016778`
- `0x18003c2b0`
- `0x18003dd48`
- `0x18003f400`
- `0x180041000`

## pseudocode

```c
__int64 __fastcall CMsftRawCDImageCreator::ValidateAndCreateUpdatedInterestingPoints(
        CMsftRawCDImageCreator *this,
        int a2,
        struct CInterestingPoint **a3,
        unsigned int *a4)
{
  int v4; // r15d
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // edi
  unsigned int v9; // r13d
  int v10; // r8d
  int i; // edx
  __int64 v12; // rax
  unsigned int v13; // ebp
  unsigned __int64 v14; // rbx
  __int64 v15; // rax
  bool v16; // cf
  unsigned __int64 v17; // rax
  unsigned __int64 *v18; // rax
  _QWORD *v19; // rbp
  int v20; // eax
  unsigned int v21; // edx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int v24; // ebx
  int v25; // r10d
  int v26; // r12d
  int v27; // eax
  PVOID *v28; // rcx
  int v29; // r11d
  int v30; // r10d
  __int64 v31; // r8
  int v32; // eax
  int v33; // r9d
  int v34; // ebx
  int v35; // ebx
  int v36; // r8d
  int v37; // edx
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  char *v42; // rbx
  unsigned int v44; // [rsp+50h] [rbp-78h]
  int v45; // [rsp+54h] [rbp-74h]
  int v46; // [rsp+58h] [rbp-70h]
  int v47; // [rsp+5Ch] [rbp-6Ch]
  unsigned int v48; // [rsp+60h] [rbp-68h]
  enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING v49; // [rsp+64h] [rbp-64h]
  int v50; // [rsp+68h] [rbp-60h]
  __int64 v51; // [rsp+70h] [rbp-58h]

  v4 = a2;
  if ( a2 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
    {
      return (unsigned int)-2136339965;
    }
    v7 = 83;
LABEL_6:
    WPP_SF_(v6[87], v7, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
    return (unsigned int)-2136339965;
  }
  if ( !a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
    {
      return (unsigned int)-2136339965;
    }
    v7 = 84;
    goto LABEL_6;
  }
  if ( a2 > 99 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 87), 85, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
    }
    return (unsigned int)-2147418113;
  }
  v9 = 2;
  v10 = 2;
  if ( *((_WORD *)this + 42) )
    v10 = a2 + 1;
  for ( i = 1; i <= v4; v10 += *((_DWORD *)this + 108 * v12 + 40) )
    v12 = i++;
  v13 = v10 + 1;
  v14 = (unsigned int)(v10 + 1);
  v15 = 32 * v14;
  v48 = v10 + 1;
  if ( !is_mul_ok(v14, 0x20u) )
    v15 = -1;
  v16 = __CFADD__(v15, 8);
  v17 = v15 + 8;
  if ( v16 )
    v17 = -1;
  v18 = (unsigned __int64 *)operator new[](v17);
  if ( !v18 )
  {
LABEL_97:
    v8 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 87), 86, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, v13, v13);
    }
    return (unsigned int)v8;
  }
  v19 = v18 + 1;
  *v18 = v14;
  `vector constructor iterator'(
    v18 + 1,
    0x20u,
    (unsigned int)v14,
    (void *(*)(void *))CInterestingPoint::CInterestingPoint);
  if ( !v19 )
  {
    v13 = v48;
    goto LABEL_97;
  }
  CTrackData::ValidateInitialized((CMsftRawCDImageCreator *)((char *)this + 560));
  v20 = CInterestingPoint::Init(
          (CInterestingPoint *)v19,
          0,
          0,
          -22650,
          -22500,
          22500,
          0,
          *((_BYTE *)this + 586),
          (enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)*((_DWORD *)this + 147));
  v8 = v20;
  if ( v20 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      v23 = 87;
      goto LABEL_93;
    }
    goto LABEL_94;
  }
  v24 = *((_DWORD *)this + 35);
  CTrackData::ValidateInitialized((CMsftRawCDImageCreator *)((char *)this + 560));
  v20 = CInterestingPoint::Init(
          (CInterestingPoint *)(v19 + 4),
          *((_DWORD *)this + 26),
          0,
          -150,
          -v24,
          v24,
          v24,
          *((_BYTE *)this + 586),
          (enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)*((_DWORD *)this + 147));
  v8 = v20;
  if ( v20 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      v23 = 88;
      goto LABEL_93;
    }
    goto LABEL_94;
  }
  v25 = 1;
  v26 = *((_DWORD *)this + 35) - 150;
  v45 = 1;
  while ( v25 <= v4 )
  {
    v44 = v25 + *((_DWORD *)this + 26) - 1;
    v51 = 432LL * v25;
    v46 = *(_DWORD *)((char *)this + v51 + 140);
    CTrackData::ValidateInitialized((CMsftRawCDImageCreator *)((char *)this + v51 + 128));
    v21 = 0;
    v49 = *(_DWORD *)((char *)this + v51 + 156);
    if ( *((_WORD *)this + 42) && v45 != 1 )
    {
      v27 = CInterestingPoint::Init(
              (CInterestingPoint *)&v19[4 * v9],
              v44,
              0,
              v26,
              -150,
              150,
              150,
              *((_BYTE *)this + v51 + 154),
              (enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)*(_DWORD *)((char *)this + v51 + 156));
      v21 = 0;
      v8 = v27;
      if ( v27 >= 0 )
        goto LABEL_48;
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
      {
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 87),
          89,
          &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids,
          v44,
          v44,
          v27);
        v21 = 0;
LABEL_48:
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      v26 += 150;
      ++v9;
      goto LABEL_51;
    }
    v28 = (PVOID *)WPP_GLOBAL_Control;
LABEL_51:
    if ( v26 + v46 < v26 )
    {
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 708) & 0x10) != 0 && *((_BYTE *)v28 + 705) >= 3u )
      {
        v41 = 90;
LABEL_86:
        WPP_SF_(v28[87], v41, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
      }
LABEL_87:
      v8 = -2136339963;
      goto LABEL_94;
    }
    if ( v26 + v46 > *((_DWORD *)this + 20) )
    {
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 708) & 0x10) != 0 && *((_BYTE *)v28 + 705) >= 3u )
      {
        v41 = 91;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v47 = 0;
    v29 = 0;
    v30 = 0;
    if ( v8 >= 0 )
    {
      v31 = 108LL * v45;
      do
      {
        v32 = *(_DWORD *)((char *)this + v51 + 160);
        if ( v30 >= v32 )
          break;
        v33 = 0;
        if ( v30 == v32 - 1 )
          v34 = v46;
        else
          v34 = *((_DWORD *)this + v30 + v31 + 42);
        v35 = v34 - *((_DWORD *)this + v31 + v30 + 41);
        if ( v30 == v32 - 1 )
        {
          if ( v35 < 150 )
          {
            v36 = v9 - 1;
            v37 = 150 - v35;
            v33 = v35;
            if ( 150 - v35 > 0 )
            {
              do
              {
                if ( v36 <= 0 )
                  break;
                v38 = 4LL * v36;
                if ( LODWORD(v19[v38]) != v44 || HIDWORD(v19[v38 + 2]) )
                  break;
                v39 = v37;
                if ( v37 >= SLODWORD(v19[v38 + 2]) )
                  v39 = v19[v38 + 2];
                --v36;
                v37 -= v39;
                HIDWORD(v19[v38 + 2]) = v39;
              }
              while ( v37 > 0 );
              v4 = a2;
            }
          }
          else
          {
            v33 = 150;
          }
        }
        v50 = v30 + 1;
        v40 = CInterestingPoint::Init(
                (CInterestingPoint *)&v19[4 * v9],
                v44,
                v30 + 1,
                v26,
                v29,
                v35,
                v33,
                *((_BYTE *)this + v51 + 154),
                v49);
        v21 = 0;
        v8 = v40;
        if ( v40 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
        {
          WPP_SF_ddD(
            *((_QWORD *)WPP_GLOBAL_Control + 87),
            92,
            &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids,
            v44,
            v44,
            v40);
          v21 = 0;
        }
        v26 += v35;
        v31 = 108LL * v45;
        v29 = v35 + v47;
        v30 = v50;
        ++v9;
        v47 += v35;
      }
      while ( v8 >= 0 );
    }
    v25 = ++v45;
    if ( v8 < 0 )
      goto LABEL_94;
  }
  v42 = (char *)this + 432 * *((unsigned int *)this + 27);
  CTrackData::ValidateInitialized((CTrackData *)(v42 + 128));
  v20 = CInterestingPoint::Init(
          (CInterestingPoint *)&v19[4 * v9],
          170,
          1,
          v26,
          0,
          6750,
          0,
          v42[154],
          (enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)*((_DWORD *)v42 + 39));
  v8 = v20;
  if ( v20 >= 0 )
  {
    *a3 = (struct CInterestingPoint *)v19;
    *a4 = v48;
  }
  else
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      v23 = 93;
LABEL_93:
      WPP_SF_d(v22[87], v23, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, (unsigned int)v20);
    }
LABEL_94:
    CInterestingPoint::`vector deleting destructor'((CInterestingPoint *)v19, v21);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003dd48  mov     rax, rsp
0x18003dd4b  mov     [rax+8], rbx
0x18003dd4f  mov     [rax+20h], r9
0x18003dd53  mov     [rax+18h], r8
0x18003dd57  mov     [rax+10h], edx
0x18003dd5a  push    rbp
0x18003dd5b  push    rsi
0x18003dd5c  push    rdi
0x18003dd5d  push    r12
0x18003dd5f  push    r13
0x18003dd61  push    r14
0x18003dd63  push    r15
0x18003dd65  sub     rsp, 90h
0x18003dd6c  xor     r12d, r12d
0x18003dd6f  mov     r15d, edx
0x18003dd72  mov     r14, rcx
0x18003dd75  test    edx, edx
0x18003dd77  jns     short loc_18003DDC0
0x18003dd79  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd80  lea     rsi, WPP_GLOBAL_Control
0x18003dd87  cmp     rcx, rsi
0x18003dd8a  jz      short loc_18003DDB6
0x18003dd8c  test    byte ptr [rcx+2C4h], 10h
0x18003dd93  jz      short loc_18003DDB6
0x18003dd95  cmp     byte ptr [rcx+2C1h], 3
0x18003dd9c  jb      short loc_18003DDB6
0x18003dd9e  lea     edx, [r12+53h]
0x18003dda3  mov     rcx, [rcx+2B8h]
0x18003ddaa  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003ddb1  call    WPP_SF_
0x18003ddb6  mov     edi, 80AA0A03h
0x18003ddbb  jmp     loc_18003E433
0x18003ddc0  test    r15d, r15d
0x18003ddc3  jnz     short loc_18003DDF0
0x18003ddc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ddcc  lea     rsi, WPP_GLOBAL_Control
0x18003ddd3  cmp     rcx, rsi
0x18003ddd6  jz      short loc_18003DDB6
0x18003ddd8  test    byte ptr [rcx+2C4h], 10h
0x18003dddf  jz      short loc_18003DDB6
0x18003dde1  cmp     byte ptr [rcx+2C1h], 3
0x18003dde8  jb      short loc_18003DDB6
0x18003ddea  lea     edx, [r15+54h]
0x18003ddee  jmp     short loc_18003DDA3
0x18003ddf0  cmp     r15d, 63h ; 'c'
0x18003ddf4  jle     short loc_18003DE3D
0x18003ddf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ddfd  lea     rsi, WPP_GLOBAL_Control
0x18003de04  cmp     rcx, rsi
0x18003de07  jz      short loc_18003DE33
0x18003de09  test    byte ptr [rcx+2C4h], 10h
0x18003de10  jz      short loc_18003DE33
0x18003de12  cmp     byte ptr [rcx+2C1h], 3
0x18003de19  jb      short loc_18003DE33
0x18003de1b  mov     rcx, [rcx+2B8h]
0x18003de22  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003de29  mov     edx, 55h ; 'U'
0x18003de2e  call    WPP_SF_
0x18003de33  mov     edi, 8000FFFFh
0x18003de38  jmp     loc_18003E433
0x18003de3d  mov     r13d, 2
0x18003de43  mov     r8d, r13d
0x18003de46  cmp     [rcx+54h], r12w
0x18003de4b  jz      short loc_18003DE51
0x18003de4d  lea     r8d, [rdx+1]
0x18003de51  mov     edx, 1
0x18003de56  cmp     r15d, edx
0x18003de59  jl      short loc_18003DE74
0x18003de5b  movsxd  rax, edx
0x18003de5e  inc     edx
0x18003de60  imul    rcx, rax, 1B0h
0x18003de67  add     r8d, [rcx+r14+0A0h]
0x18003de6f  cmp     edx, r15d
0x18003de72  jle     short loc_18003DE5B
0x18003de74  lea     ebp, [r8+1]
0x18003de78  mov     edi, 20h ; ' '
0x18003de7d  mov     ebx, ebp
0x18003de7f  mov     eax, edi
0x18003de81  mul     rbx
0x18003de84  lea     rcx, [rdi-21h]
0x18003de88  mov     [rsp+0C8h+var_68], ebp
0x18003de8c  cmovb   rax, rcx
0x18003de90  add     rax, 8
0x18003de94  cmovb   rax, rcx
0x18003de98  mov     rcx, rax; unsigned __int64
0x18003de9b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003dea0  test    rax, rax
0x18003dea3  jz      loc_18003E3EA
0x18003dea9  lea     rbp, [rax+8]
0x18003dead  mov     [rax], rbx
0x18003deb0  mov     rcx, rbp; void *
0x18003deb3  lea     r9, ??0CInterestingPoint@@QEAA@XZ; void *(*)(void *)
0x18003deba  mov     r8d, ebx; unsigned __int64
0x18003debd  mov     edx, edi; unsigned __int64
0x18003debf  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003dec4  test    rbp, rbp
0x18003dec7  jz      loc_18003E3E6
0x18003decd  lea     rsi, [r14+230h]
0x18003ded4  mov     rcx, rsi; this
0x18003ded7  call    ?ValidateInitialized@CTrackData@@AEBAXXZ; CTrackData::ValidateInitialized(void)
0x18003dedc  mov     eax, [rsi+1Ch]
0x18003dedf  mov     r9d, 0FFFFA786h; int
0x18003dee5  mov     [rsp+0C8h+var_88], eax; enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING
0x18003dee9  xor     r8d, r8d; int
0x18003deec  mov     al, [r14+24Ah]
0x18003def3  xor     edx, edx; int
0x18003def5  mov     [rsp+0C8h+var_90], al; char
0x18003def9  mov     rcx, rbp; this
0x18003defc  mov     [rsp+0C8h+var_98], r12d; int
0x18003df01  mov     [rsp+0C8h+var_A0], 57E4h; int
0x18003df09  mov     [rsp+0C8h+var_A8], 0FFFFA81Ch; int
0x18003df11  call    ?Init@CInterestingPoint@@QEAAJJJJJJJEW4_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING@@@Z; CInterestingPoint::Init(long,long,long,long,long,long,uchar,_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)
0x18003df16  mov     edi, eax
0x18003df18  test    eax, eax
0x18003df1a  jns     short loc_18003DF57
0x18003df1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df23  lea     rsi, WPP_GLOBAL_Control
0x18003df2a  cmp     rcx, rsi
0x18003df2d  jz      loc_18003E3C1
0x18003df33  test    byte ptr [rcx+2C4h], 10h
0x18003df3a  jz      loc_18003E3C1
0x18003df40  cmp     byte ptr [rcx+2C1h], 3
0x18003df47  jb      loc_18003E3C1
0x18003df4d  mov     edx, 57h ; 'W'
0x18003df52  jmp     loc_18003E3AB
0x18003df57  mov     ebx, [r14+8Ch]
0x18003df5e  mov     rcx, rsi; this
0x18003df61  call    ?ValidateInitialized@CTrackData@@AEBAXXZ; CTrackData::ValidateInitialized(void)
0x18003df66  mov     eax, [rsi+1Ch]
0x18003df69  lea     rcx, [rbp+20h]; this
0x18003df6d  mov     [rsp+0C8h+var_88], eax; enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING
0x18003df71  mov     edx, ebx
0x18003df73  mov     al, [r14+24Ah]
0x18003df7a  neg     edx
0x18003df7c  mov     [rsp+0C8h+var_90], al; char
0x18003df80  mov     r9d, 0FFFFFF6Ah; int
0x18003df86  mov     [rsp+0C8h+var_98], ebx; int
0x18003df8a  xor     r8d, r8d; int
0x18003df8d  mov     [rsp+0C8h+var_A0], ebx; int
0x18003df91  mov     [rsp+0C8h+var_A8], edx; int
0x18003df95  mov     edx, [r14+68h]; int
0x18003df99  call    ?Init@CInterestingPoint@@QEAAJJJJJJJEW4_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING@@@Z; CInterestingPoint::Init(long,long,long,long,long,long,uchar,_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)
0x18003df9e  mov     edi, eax
0x18003dfa0  test    eax, eax
0x18003dfa2  jns     short loc_18003DFDF
0x18003dfa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dfab  lea     rsi, WPP_GLOBAL_Control
0x18003dfb2  cmp     rcx, rsi
0x18003dfb5  jz      loc_18003E3C1
0x18003dfbb  test    byte ptr [rcx+2C4h], 10h
0x18003dfc2  jz      loc_18003E3C1
0x18003dfc8  cmp     byte ptr [rcx+2C1h], 3
0x18003dfcf  jb      loc_18003E3C1
0x18003dfd5  mov     edx, 58h ; 'X'
0x18003dfda  jmp     loc_18003E3AB
0x18003dfdf  mov     r12d, [r14+8Ch]
0x18003dfe6  lea     rsi, WPP_GLOBAL_Control
0x18003dfed  mov     r10d, 1
0x18003dff3  sub     r12d, 96h
0x18003dffa  mov     [rsp+0C8h+var_74], r10d
0x18003dfff  cmp     r10d, r15d
0x18003e002  jg      loc_18003E31C
0x18003e008  mov     eax, [r14+68h]
0x18003e00c  dec     eax
0x18003e00e  add     eax, r10d
0x18003e011  mov     [rsp+0C8h+var_78], eax
0x18003e015  movsxd  rax, r10d
0x18003e018  imul    rax, 1B0h
0x18003e01f  mov     [rsp+0C8h+var_58], rax
0x18003e024  mov     ecx, [rax+r14+8Ch]
0x18003e02c  lea     rbx, [rax+r14]
0x18003e030  mov     [rsp+0C8h+var_70], ecx
0x18003e034  lea     rcx, [rbx+80h]; this
0x18003e03b  call    ?ValidateInitialized@CTrackData@@AEBAXXZ; CTrackData::ValidateInitialized(void)
0x18003e040  mov     eax, [rbx+9Ch]
0x18003e046  xor     edx, edx
0x18003e048  mov     ebx, [rsp+0C8h+var_74]
0x18003e04c  mov     [rsp+0C8h+var_64], eax
0x18003e050  cmp     [r14+54h], dx
0x18003e055  jz      loc_18003E109
0x18003e05b  cmp     ebx, 1
0x18003e05e  jz      loc_18003E109
0x18003e064  mov     edx, [rsp+0C8h+var_78]; int
0x18003e068  mov     r9d, r12d; int
0x18003e06b  mov     [rsp+0C8h+var_88], eax; enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING
0x18003e06f  xor     r8d, r8d; int
0x18003e072  mov     rax, [rsp+0C8h+var_58]
0x18003e077  mov     ecx, r13d
0x18003e07a  shl     rcx, 5
0x18003e07e  add     rcx, rbp; this
0x18003e081  mov     al, [rax+r14+9Ah]
0x18003e089  mov     [rsp+0C8h+var_90], al; char
0x18003e08d  mov     eax, 96h
0x18003e092  mov     [rsp+0C8h+var_98], eax; int
0x18003e096  mov     [rsp+0C8h+var_A0], eax; int
0x18003e09a  mov     [rsp+0C8h+var_A8], 0FFFFFF6Ah; int
0x18003e0a2  call    ?Init@CInterestingPoint@@QEAAJJJJJJJEW4_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING@@@Z; CInterestingPoint::Init(long,long,long,long,long,long,uchar,_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)
0x18003e0a7  xor     edx, edx
0x18003e0a9  mov     edi, eax
0x18003e0ab  test    eax, eax
0x18003e0ad  jns     short loc_18003E0F6
0x18003e0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0b6  cmp     rcx, rsi
0x18003e0b9  jz      short loc_18003E0FD
0x18003e0bb  test    byte ptr [rcx+2C4h], 10h
0x18003e0c2  jz      short loc_18003E0FD
0x18003e0c4  cmp     byte ptr [rcx+2C1h], 3
0x18003e0cb  jb      short loc_18003E0FD
0x18003e0cd  mov     rcx, [rcx+2B8h]
0x18003e0d4  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003e0db  mov     [rsp+0C8h+var_A0], eax
0x18003e0df  mov     edx, 59h ; 'Y'
0x18003e0e4  mov     eax, [rsp+0C8h+var_78]
0x18003e0e8  mov     r9d, eax
0x18003e0eb  mov     [rsp+0C8h+var_A8], eax
0x18003e0ef  call    WPP_SF_ddD
0x18003e0f4  xor     edx, edx
0x18003e0f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0fd  add     r12d, 96h
0x18003e104  inc     r13d
0x18003e107  jmp     short loc_18003E110
0x18003e109  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e110  mov     eax, [rsp+0C8h+var_70]
0x18003e114  add     eax, r12d
0x18003e117  cmp     eax, r12d
0x18003e11a  jl      loc_18003E2E3
0x18003e120  cmp     eax, [r14+50h]
0x18003e124  jg      loc_18003E2C5
0x18003e12a  mov     [rsp+0C8h+var_6C], edx
0x18003e12e  mov     r11d, edx
0x18003e131  mov     r10d, edx
0x18003e134  test    edi, edi
0x18003e136  js      loc_18003E2AB
0x18003e13c  movsxd  rax, ebx
0x18003e13f  imul    r8, rax, 6Ch ; 'l'
0x18003e143  mov     [rsp+0C8h+var_50], r8
0x18003e148  mov     rax, [rsp+0C8h+var_58]
0x18003e14d  mov     eax, [rax+r14+0A0h]
0x18003e155  cmp     r10d, eax
0x18003e158  jge     loc_18003E2AB
0x18003e15e  mov     r9d, edx
0x18003e161  movsxd  rcx, r10d
0x18003e164  lea     edx, [rax-1]
0x18003e167  cmp     r10d, edx
0x18003e16a  jnz     short loc_18003E172
0x18003e16c  mov     ebx, [rsp+0C8h+var_70]
0x18003e170  jmp     short loc_18003E17E
0x18003e172  lea     rax, [rcx+r8]
0x18003e176  mov     ebx, [r14+rax*4+0A8h]
0x18003e17e  lea     rax, [r8+rcx]
0x18003e182  sub     ebx, [r14+rax*4+0A4h]
0x18003e18a  cmp     r10d, edx
0x18003e18d  jnz     short loc_18003E1EA
0x18003e18f  mov     eax, 96h
0x18003e194  cmp     ebx, eax
0x18003e196  jl      short loc_18003E19D
0x18003e198  mov     r9d, eax
0x18003e19b  jmp     short loc_18003E1EA
0x18003e19d  mov     edx, eax
0x18003e19f  lea     r8d, [r13-1]
0x18003e1a3  sub     edx, ebx
0x18003e1a5  mov     r9d, ebx
0x18003e1a8  test    edx, edx
0x18003e1aa  jle     short loc_18003E1EA
0x18003e1ac  mov     r15d, [rsp+0C8h+var_78]
0x18003e1b1  test    r8d, r8d
0x18003e1b4  jle     short loc_18003E1E2
0x18003e1b6  movsxd  rcx, r8d
0x18003e1b9  shl     rcx, 5
0x18003e1bd  cmp     [rcx+rbp], r15d
0x18003e1c1  jnz     short loc_18003E1E2
0x18003e1c3  cmp     dword ptr [rcx+rbp+14h], 0
0x18003e1c8  jnz     short loc_18003E1E2
0x18003e1ca  cmp     edx, [rcx+rbp+10h]
0x18003e1ce  mov     eax, edx
0x18003e1d0  cmovge  eax, [rcx+rbp+10h]
0x18003e1d5  dec     r8d
0x18003e1d8  sub     edx, eax
0x18003e1da  mov     [rcx+rbp+14h], eax
0x18003e1de  test    edx, edx
0x18003e1e0  jg      short loc_18003E1B1
0x18003e1e2  mov     r15d, [rsp+0C8h+arg_8]
0x18003e1ea  mov     eax, [rsp+0C8h+var_64]
0x18003e1ee  inc     r10d
0x18003e1f1  mov     edx, [rsp+0C8h+var_78]; int
0x18003e1f5  mov     r8d, r10d; int
0x18003e1f8  mov     [rsp+0C8h+var_88], eax; enum _IMAPI_CD_TRACK_DIGITAL_COPY_SETTING
0x18003e1fc  mov     rax, [rsp+0C8h+var_58]
0x18003e201  mov     ecx, r13d
0x18003e204  shl     rcx, 5
0x18003e208  add     rcx, rbp; this
0x18003e20b  mov     [rsp+0C8h+var_60], r10d
0x18003e210  mov     al, [rax+r14+9Ah]
0x18003e218  mov     [rsp+0C8h+var_90], al; char
0x18003e21c  mov     [rsp+0C8h+var_98], r9d; int
0x18003e221  mov     r9d, r12d; int
0x18003e224  mov     [rsp+0C8h+var_A0], ebx; int
0x18003e228  mov     [rsp+0C8h+var_A8], r11d; int
0x18003e22d  call    ?Init@CInterestingPoint@@QEAAJJJJJJJEW4_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING@@@Z; CInterestingPoint::Init(long,long,long,long,long,long,uchar,_IMAPI_CD_TRACK_DIGITAL_COPY_SETTING)
0x18003e232  xor     edx, edx
  ... truncated ...
```
