# ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))

- ea: `0x14000cb44`
- end: `0x14000cebd`
- name: `?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z`
- size: `889`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))`
- caller_count: `17`
- callee_count: `5`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000a254`
- `0x14000d63c`
- `0x140015f00`
- `0x140019458`
- `0x1400200e8`
- `0x140020af0`
- `0x1400210c0`
- `0x1400212b0`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x140033548`

## callees

- `0x14000cb44`
- `0x14002fbd4`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000cdec`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000cdec`
- `watchdog!WdLogSingleEntry0` at `0x14000cdd3`
- `watchdog!WdLogSingleEntry0` at `0x14000cdd3`
- `WIN32K!CLIPOBJ_bEnum` at `0x14000cd4e`
- `WIN32K!CLIPOBJ_bEnum` at `0x14000cd4e`
- `WIN32K!CLIPOBJ_cEnumStart` at `0x14000cc6a`
- `WIN32K!CLIPOBJ_cEnumStart` at `0x14000cc6a`

## pseudocode

```c
__int64 __fastcall ClipDstRects(
        struct CLIP_RECTS_DATA *a1,
        int (*a2)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))
{
  __int64 v2; // r15
  char v6; // r14
  _DWORD *v7; // rcx
  _DWORD *v8; // rdx
  ULONG v9; // edi
  _DWORD *v10; // rax
  BOOL v11; // r12d
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // edx
  unsigned int v15; // edi
  ULONG v16; // r14d
  signed int *v17; // r10
  signed int v18; // eax
  signed int v19; // r8d
  signed int v20; // r9d
  signed int v21; // ecx
  unsigned int v22; // edi
  __int128 v23; // xmm0
  __int64 v24; // rcx
  ULONG v25; // r9d
  ULONG v26; // r11d
  ULONG v27; // r13d
  bool v28; // zf
  __int64 v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  _DWORD *v32; // rcx
  int v33; // edx
  unsigned int v34; // r8d
  LONG v35; // eax
  struct CddBitmapStagingApertureMem *v36; // rdx
  LONG v37; // eax
  struct CDDPDEV *v38; // rcx
  int v39; // [rsp+30h] [rbp-D0h]
  int v40; // [rsp+34h] [rbp-CCh]
  int v41; // [rsp+38h] [rbp-C8h]
  int v42; // [rsp+3Ch] [rbp-C4h]
  struct tagRECT v43; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+50h] [rbp-B0h]
  int (*v45)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *); // [rsp+58h] [rbp-A8h]
  ULONG pul[84]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = *(_QWORD *)a1;
  v45 = a2;
  v44 = v2;
  if ( v2 && (v6 = *(_BYTE *)(v2 + 20)) != 0 )
  {
    v40 = 0;
    memset(pul, 0, 0x144u);
    v7 = (_DWORD *)*((_QWORD *)a1 + 2);
    v8 = (_DWORD *)*((_QWORD *)a1 + 3);
    v41 = *v8 - *v7;
    v42 = v8[1] - v7[1];
    if ( v6 == 1 )
    {
      v23 = *(_OWORD *)(v2 + 4);
      v11 = 0;
      pul[0] = 1;
      v39 = 0;
      *(_OWORD *)&pul[1] = v23;
    }
    else
    {
      v9 = 3;
      if ( v6 != 3 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1828;
        v31 = (_QWORD *)WdLogNewEntry5_WdAssertion(v30, v29);
        v31[3] = gCddImageInfo;
        v31[4] = (unsigned int)dword_14003E570;
        v31[5] = 215857758;
        WdLogGlobalForLineNumber = 1828;
      }
      v10 = (_DWORD *)*((_QWORD *)a1 + 2);
      v11 = 1;
      v12 = (_DWORD *)*((_QWORD *)a1 + 1);
      v39 = 1;
      v13 = v10[1];
      v14 = v12[1];
      if ( *v12 >= *v10 )
      {
        v9 = 0;
        if ( v14 < v13 )
          v9 = 2;
      }
      else if ( v14 >= v13 )
      {
        v9 = 1;
      }
      CLIPOBJ_cEnumStart((CLIPOBJ *)v2, 0, 0, v9, 0x14u);
    }
    if ( v11 )
      goto LABEL_30;
    while ( 1 )
    {
      v15 = 0;
      v16 = 0;
      if ( !pul[0] )
        goto LABEL_28;
      do
      {
        v17 = (signed int *)*((_QWORD *)a1 + 2);
        v18 = *v17;
        if ( (int)pul[4 * v16 + 1] < *v17 )
          pul[4 * v16 + 1] = v18;
        else
          v18 = pul[4 * v16 + 1];
        v19 = v17[2];
        if ( (int)pul[4 * v16 + 3] > v19 )
          pul[4 * v16 + 3] = v19;
        else
          v19 = pul[4 * v16 + 3];
        v20 = v17[1];
        if ( (int)pul[4 * v16 + 2] >= v20 )
          v20 = pul[4 * v16 + 2];
        else
          pul[4 * v16 + 2] = v20;
        v21 = v17[3];
        if ( (int)pul[4 * v16 + 4] > v21 )
          pul[4 * v16 + 4] = v21;
        else
          v21 = pul[4 * v16 + 4];
        if ( v20 < v21 && v18 < v19 )
        {
          v24 = 2LL * v15;
          pul[2 * v24 + 1] = v18 + v41;
          v25 = v41 + pul[4 * v16 + 3];
          pul[2 * v24 + 3] = v25;
          v26 = v42 + pul[4 * v16 + 2];
          pul[2 * v24 + 2] = v26;
          v27 = v42 + pul[4 * v16 + 4];
          v28 = *((_BYTE *)a1 + 48) == 0;
          pul[2 * v24 + 4] = v27;
          if ( !v28 )
          {
            v32 = (_DWORD *)*((_QWORD *)a1 + 1);
            v33 = *v32 - *v17;
            LODWORD(v32) = v32[1] - v17[1];
            v34 = *((_DWORD *)a1 + 16);
            v43.left = v33 + v18 + v41;
            v43.top = (_DWORD)v32 + v26;
            v35 = v33 + v25;
            v36 = (struct CddBitmapStagingApertureMem *)*((_QWORD *)a1 + 7);
            v43.right = v35;
            v37 = (_DWORD)v32 + v27;
            v38 = (struct CDDPDEV *)*((_QWORD *)a1 + 9);
            v43.bottom = v37;
            FlushCpuCache(v38, v36, v34, &v43);
          }
          ++v15;
        }
        ++v16;
      }
      while ( v16 < pul[0] );
      v2 = v44;
      v11 = v39;
      if ( v15 )
      {
        v40 = ((__int64 (__fastcall *)(struct CLIP_RECTS_DATA *, _QWORD, ULONG *))v45)(a1, v15, &pul[1]);
        v22 = v40;
        if ( v40 < 0 )
          return v22;
      }
      else
      {
LABEL_28:
        v22 = v40;
      }
      if ( !v11 )
        return v22;
LABEL_30:
      v11 = CLIPOBJ_bEnum((CLIPOBJ *)v2, 0x144u, pul);
      v39 = v11;
    }
  }
  else
  {
    if ( *((_BYTE *)a1 + 48) )
      FlushCpuCache(
        *((struct CDDPDEV **)a1 + 9),
        *((struct CddBitmapStagingApertureMem **)a1 + 7),
        *((_DWORD *)a1 + 16),
        *((const struct tagRECT **)a1 + 1));
    return ((__int64 (__fastcall *)(struct CLIP_RECTS_DATA *, __int64, _QWORD))a2)(a1, 1, *((_QWORD *)a1 + 3));
  }
}

```

## disassembly

```asm
0x14000cb44  mov     [rsp-8+arg_10], rbx
0x14000cb49  push    rbp
0x14000cb4a  push    rsi
0x14000cb4b  push    rdi
0x14000cb4c  push    r12
0x14000cb4e  push    r13
0x14000cb50  push    r14
0x14000cb52  push    r15
0x14000cb54  lea     rbp, [rsp-0C0h]
0x14000cb5c  sub     rsp, 1C0h
0x14000cb63  mov     rax, cs:__security_cookie
0x14000cb6a  xor     rax, rsp
0x14000cb6d  mov     [rbp+0F0h+var_40], rax
0x14000cb74  mov     r15, [rcx]
0x14000cb77  mov     rdi, rdx
0x14000cb7a  mov     [rsp+1F0h+var_198], rdx
0x14000cb7f  mov     rbx, rcx
0x14000cb82  mov     [rsp+1F0h+var_1A0], r15
0x14000cb87  test    r15, r15
0x14000cb8a  jnz     short loc_14000CBD5
0x14000cb8c  cmp     byte ptr [rcx+30h], 0
0x14000cb90  jnz     loc_14000CEA3
0x14000cb96  mov     r8, [rbx+18h]
0x14000cb9a  mov     edx, 1
0x14000cb9f  mov     rcx, rbx
0x14000cba2  mov     rax, rdi
0x14000cba5  call    _guard_dispatch_icall
0x14000cbaa  mov     rcx, [rbp+0F0h+var_40]
0x14000cbb1  xor     rcx, rsp; StackCookie
0x14000cbb4  call    __security_check_cookie
0x14000cbb9  mov     rbx, [rsp+1F0h+arg_10]
0x14000cbc1  add     rsp, 1C0h
0x14000cbc8  pop     r15
0x14000cbca  pop     r14
0x14000cbcc  pop     r13
0x14000cbce  pop     r12
0x14000cbd0  pop     rdi
0x14000cbd1  pop     rsi
0x14000cbd2  pop     rbp
0x14000cbd3  retn
0x14000cbd5  mov     r14b, [r15+14h]
0x14000cbd9  test    r14b, r14b
0x14000cbdc  jz      short loc_14000CB8C
0x14000cbde  xor     edx, edx; Val
0x14000cbe0  mov     [rsp+1F0h+var_1BC], 0
0x14000cbe8  mov     r8d, 144h; Size
0x14000cbee  lea     rcx, [rsp+1F0h+pul]; void *
0x14000cbf3  call    memset
0x14000cbf8  mov     rcx, [rbx+10h]
0x14000cbfc  mov     esi, 1
0x14000cc01  mov     rdx, [rbx+18h]
0x14000cc05  mov     eax, [rcx+4]
0x14000cc08  mov     r8d, [rdx]
0x14000cc0b  sub     r8d, [rcx]
0x14000cc0e  mov     ecx, [rdx+4]
0x14000cc11  sub     ecx, eax
0x14000cc13  mov     [rsp+1F0h+var_1B8], r8d
0x14000cc18  mov     [rsp+1F0h+var_1B4], ecx
0x14000cc1c  cmp     r14b, sil
0x14000cc1f  jz      loc_14000CD66
0x14000cc25  lea     edi, [rsi+2]
0x14000cc28  cmp     r14b, dil
0x14000cc2b  jnz     loc_14000CDD1
0x14000cc31  mov     rax, [rbx+10h]
0x14000cc35  mov     r12d, esi
0x14000cc38  mov     rcx, [rbx+8]
0x14000cc3c  mov     [rsp+1F0h+var_1C0], esi
0x14000cc40  mov     r8d, [rax+4]
0x14000cc44  mov     eax, [rax]
0x14000cc46  mov     edx, [rcx+4]
0x14000cc49  cmp     [rcx], eax
0x14000cc4b  jge     loc_14000CE24
0x14000cc51  cmp     edx, r8d
0x14000cc54  cmovge  edi, esi
0x14000cc57  mov     r9d, edi; iDirection
0x14000cc5a  mov     [rsp+1F0h+cLimit], 14h; unsigned __int8
0x14000cc62  xor     r8d, r8d; iType
0x14000cc65  xor     edx, edx; bAll
0x14000cc67  mov     rcx, r15; pco
0x14000cc6a  call    cs:__imp_CLIPOBJ_cEnumStart
0x14000cc71  nop     dword ptr [rax+rax+00h]
0x14000cc76  test    r12d, r12d
0x14000cc79  jnz     loc_14000CD41
0x14000cc7f  xor     edi, edi
0x14000cc81  xor     r14d, r14d
0x14000cc84  cmp     [rsp+1F0h+pul], edi
0x14000cc88  jbe     loc_14000CD38
0x14000cc8e  mov     r15d, [rsp+1F0h+var_1B8]
0x14000cc93  mov     r12d, [rsp+1F0h+var_1B4]
0x14000cc98  mov     r10, [rbx+10h]
0x14000cc9c  mov     edx, r14d
0x14000cc9f  add     rdx, rdx
0x14000cca2  mov     eax, [r10]
0x14000cca5  mov     ecx, dword ptr [rsp+rdx*8+1F0h+var_18C]
0x14000cca9  cmp     ecx, eax
0x14000ccab  jl      loc_14000CE34
0x14000ccb1  mov     eax, ecx
0x14000ccb3  mov     r8d, [r10+8]
0x14000ccb7  mov     ecx, dword ptr [rsp+rdx*8+1F0h+var_18C+8]
0x14000ccbb  cmp     ecx, r8d
0x14000ccbe  jg      loc_14000CE3D
0x14000ccc4  mov     r8d, ecx
0x14000ccc7  mov     r9d, [r10+4]
0x14000cccb  mov     ecx, dword ptr [rsp+rdx*8+1F0h+var_18C+4]
0x14000cccf  cmp     ecx, r9d
0x14000ccd2  jge     loc_14000CE47
0x14000ccd8  mov     dword ptr [rsp+rdx*8+1F0h+var_18C+4], r9d
0x14000ccdd  mov     ecx, [r10+0Ch]
0x14000cce1  mov     r11d, dword ptr [rsp+rdx*8+1F0h+var_18C+0Ch]
0x14000cce6  cmp     r11d, ecx
0x14000cce9  jg      loc_14000CE4F
0x14000ccef  mov     ecx, r11d
0x14000ccf2  cmp     r9d, ecx
0x14000ccf5  jl      loc_14000CD82
0x14000ccfb  add     r14d, esi
0x14000ccfe  cmp     r14d, [rsp+1F0h+pul]
0x14000cd03  jb      short loc_14000CC98
0x14000cd05  mov     r15, [rsp+1F0h+var_1A0]
0x14000cd0a  mov     r12d, [rsp+1F0h+var_1C0]
0x14000cd0f  test    edi, edi
0x14000cd11  jz      short loc_14000CD38
0x14000cd13  mov     rax, [rsp+1F0h+var_198]
0x14000cd18  lea     r8, [rsp+1F0h+var_18C]
0x14000cd1d  mov     edx, edi
0x14000cd1f  mov     rcx, rbx
0x14000cd22  call    _guard_dispatch_icall
0x14000cd27  mov     [rsp+1F0h+var_1BC], eax
0x14000cd2b  mov     edi, eax
0x14000cd2d  test    eax, eax
0x14000cd2f  jns     short loc_14000CD3C
0x14000cd31  mov     eax, edi
0x14000cd33  jmp     loc_14000CBAA
0x14000cd38  mov     edi, [rsp+1F0h+var_1BC]
0x14000cd3c  test    r12d, r12d
0x14000cd3f  jz      short loc_14000CD31
0x14000cd41  lea     r8, [rsp+1F0h+pul]; pul
0x14000cd46  mov     edx, 144h; cj
0x14000cd4b  mov     rcx, r15; pco
0x14000cd4e  call    cs:__imp_CLIPOBJ_bEnum
0x14000cd55  nop     dword ptr [rax+rax+00h]
0x14000cd5a  mov     r12d, eax
0x14000cd5d  mov     [rsp+1F0h+var_1C0], eax
0x14000cd61  jmp     loc_14000CC7F
0x14000cd66  movups  xmm0, xmmword ptr [r15+4]
0x14000cd6b  xor     r12d, r12d
0x14000cd6e  mov     [rsp+1F0h+pul], esi
0x14000cd72  mov     [rsp+1F0h+var_1C0], r12d
0x14000cd77  movdqu  [rsp+1F0h+var_18C], xmm0
0x14000cd7d  jmp     loc_14000CC76
0x14000cd82  cmp     eax, r8d
0x14000cd85  jge     loc_14000CCFB
0x14000cd8b  mov     ecx, edi
0x14000cd8d  lea     r8d, [rax+r15]
0x14000cd91  add     rcx, rcx
0x14000cd94  mov     dword ptr [rsp+rcx*8+1F0h+var_18C], r8d
0x14000cd99  mov     r9d, dword ptr [rsp+rdx*8+1F0h+var_18C+8]
0x14000cd9e  add     r9d, r15d
0x14000cda1  mov     dword ptr [rsp+rcx*8+1F0h+var_18C+8], r9d
0x14000cda6  mov     r11d, dword ptr [rsp+rdx*8+1F0h+var_18C+4]
0x14000cdab  add     r11d, r12d
0x14000cdae  mov     dword ptr [rsp+rcx*8+1F0h+var_18C+4], r11d
0x14000cdb3  mov     r13d, dword ptr [rsp+rdx*8+1F0h+var_18C+0Ch]
0x14000cdb8  add     r13d, r12d
0x14000cdbb  cmp     byte ptr [rbx+30h], 0
0x14000cdbf  mov     dword ptr [rsp+rcx*8+1F0h+var_18C+0Ch], r13d
0x14000cdc4  jnz     loc_14000CE58
0x14000cdca  add     edi, esi
0x14000cdcc  jmp     loc_14000CCFB
0x14000cdd1  mov     ecx, esi
0x14000cdd3  call    cs:__imp_WdLogSingleEntry0
0x14000cdda  nop     dword ptr [rax+rax+00h]
0x14000cddf  mov     r14d, 724h
0x14000cde5  mov     cs:WdLogGlobalForLineNumber, r14d
0x14000cdec  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000cdf3  nop     dword ptr [rax+rax+00h]
0x14000cdf8  mov     rcx, rax
0x14000cdfb  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000ce02  mov     [rcx+18h], rax
0x14000ce06  mov     eax, cs:dword_14003E570
0x14000ce0c  mov     [rcx+20h], rax
0x14000ce10  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x14000ce18  mov     cs:WdLogGlobalForLineNumber, r14d
0x14000ce1f  jmp     loc_14000CC31
0x14000ce24  xor     edi, edi
0x14000ce26  cmp     edx, r8d
0x14000ce29  lea     eax, [rdi+2]
0x14000ce2c  cmovl   edi, eax
0x14000ce2f  jmp     loc_14000CC57
0x14000ce34  mov     dword ptr [rsp+rdx*8+1F0h+var_18C], eax
0x14000ce38  jmp     loc_14000CCB3
0x14000ce3d  mov     dword ptr [rsp+rdx*8+1F0h+var_18C+8], r8d
0x14000ce42  jmp     loc_14000CCC7
0x14000ce47  mov     r9d, ecx
0x14000ce4a  jmp     loc_14000CCDD
0x14000ce4f  mov     dword ptr [rsp+rdx*8+1F0h+var_18C+0Ch], ecx
0x14000ce53  jmp     loc_14000CCF2
0x14000ce58  mov     rcx, [rbx+8]
0x14000ce5c  mov     edx, [rcx]
0x14000ce5e  sub     edx, [r10]
0x14000ce61  mov     ecx, [rcx+4]
0x14000ce64  sub     ecx, [r10+4]
0x14000ce68  lea     eax, [rdx+r8]
0x14000ce6c  mov     r8d, [rbx+40h]; unsigned int
0x14000ce70  mov     [rsp+1F0h+var_1B0.left], eax
0x14000ce74  lea     eax, [rcx+r11]
0x14000ce78  mov     [rsp+1F0h+var_1B0.top], eax
0x14000ce7c  lea     eax, [rdx+r9]
0x14000ce80  mov     rdx, [rbx+38h]; this
0x14000ce84  lea     r9, [rsp+1F0h+var_1B0]; struct tagRECT *
0x14000ce89  mov     [rsp+1F0h+var_1B0.right], eax
0x14000ce8d  lea     eax, [rcx+r13]
0x14000ce91  mov     rcx, [rbx+48h]; struct CDDPDEV *
0x14000ce95  mov     [rsp+1F0h+var_1B0.bottom], eax
0x14000ce99  call    ?FlushCpuCache@@YAXPEAUCDDPDEV@@PEAVCddBitmapStagingApertureMem@@IPEBUtagRECT@@E@Z; FlushCpuCache(CDDPDEV *,CddBitmapStagingApertureMem *,uint,tagRECT const *,uchar)
0x14000ce9e  jmp     loc_14000CDCA
0x14000cea3  mov     r9, [rcx+8]; struct tagRECT *
0x14000cea7  mov     r8d, [rcx+40h]; unsigned int
0x14000ceab  mov     rdx, [rcx+38h]; this
0x14000ceaf  mov     rcx, [rcx+48h]; struct CDDPDEV *
0x14000ceb3  call    ?FlushCpuCache@@YAXPEAUCDDPDEV@@PEAVCddBitmapStagingApertureMem@@IPEBUtagRECT@@E@Z; FlushCpuCache(CDDPDEV *,CddBitmapStagingApertureMem *,uint,tagRECT const *,uchar)
0x14000ceb8  jmp     loc_14000CB96
```
