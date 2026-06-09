# UxpSslPrepareSendBuffer

- ea: `0x14004bdc0`
- end: `0x14004c5c0`
- name: `UxpSslPrepareSendBuffer`
- size: `2048`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14013b124`
- `0x14013b1dc`

## callees

- `0x140049d08`
- `0x14004ba70`
- `0x14004bdc0`
- `0x14004d130`
- `0x1400513f0`
- `0x1401678f0`
- `0x140167940`
- `0x1401c3f78`
- `0x1401d5a48`
- `0x1401d5b20`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c0d1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c0d1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004bf1a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c1f4`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c2b8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004bf1a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c1f4`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c2b8`
- `ntoskrnl!MmSizeOfMdl` at `0x14004be9f`
- `ntoskrnl!MmSizeOfMdl` at `0x14004be9f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c410`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c441`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c472`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c4a3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c410`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c441`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c472`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c4a3`
- `ntoskrnl!ExAllocatePool3` at `0x140176544`
- `ntoskrnl!ExAllocatePool3` at `0x140176544`

## pseudocode

```c
__int64 __fastcall UxpSslPrepareSendBuffer(
        unsigned int *a1,
        __int64 *a2,
        int *a3,
        unsigned int a4,
        unsigned __int8 a5,
        _QWORD *a6)
{
  __int64 v7; // r15
  _QWORD *v8; // rsi
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // r13d
  __int64 v12; // rcx
  SIZE_T v13; // rdi
  _DWORD *v14; // rbx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // r8d
  unsigned int v18; // esi
  unsigned int v19; // eax
  int v20; // ebp
  unsigned __int64 v21; // rbx
  char *v22; // rax
  int v23; // eax
  __int64 v24; // rbp
  int v25; // edi
  unsigned int v26; // r12d
  unsigned int v28; // esi
  int *v29; // rdi
  char *v30; // r9
  int v31; // r12d
  char *v32; // rax
  unsigned int v33; // ebp
  char *v34; // rdx
  int v35; // r9d
  int v36; // eax
  int v37; // ebp
  unsigned __int64 v38; // rbx
  char *v39; // rax
  int LockArray_high; // ebp
  unsigned __int64 v41; // rbx
  char *v42; // rax
  unsigned int v43; // ebp
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rbx
  USHORT v48; // ax
  __int64 v49; // rbx
  USHORT CurrentNodeNumber; // ax
  __int64 v51; // rbx
  USHORT v52; // ax
  __int64 v53; // rbx
  __int64 Pool3; // rax
  __int64 v55; // [rsp+48h] [rbp-80h]
  unsigned int v56; // [rsp+60h] [rbp-68h]
  unsigned int v57; // [rsp+64h] [rbp-64h]
  unsigned int Size; // [rsp+68h] [rbp-60h]
  unsigned int Size_4; // [rsp+6Ch] [rbp-5Ch]
  char *v60; // [rsp+70h] [rbp-58h]
  __int64 v61; // [rsp+78h] [rbp-50h]
  unsigned int v62; // [rsp+D0h] [rbp+8h] BYREF
  __int64 *v63; // [rsp+D8h] [rbp+10h]
  int *v64; // [rsp+E0h] [rbp+18h]
  unsigned int v65; // [rsp+E8h] [rbp+20h]

  v65 = a4;
  v64 = a3;
  v63 = a2;
  v7 = a4;
  v62 = 0;
  v8 = a6;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqqLlq((_DWORD)a1, (_DWORD)a2, (_DWORD)a3, (_DWORD)a1, (char)a2, (char)a3, a4, a5, a6);
  *v8 = 0;
  v9 = a1[114];
  if ( (unsigned int)v9 >= 0x10000 || (v10 = a1[115], (unsigned int)v10 >= 0x10000) )
  {
    v25 = -1073741811;
    goto LABEL_26;
  }
  Size = a1[116];
  v11 = (unsigned int)v7 / Size + ((unsigned int)v7 % Size != 0);
  v12 = v7 + v11 * (v9 + v10);
  v13 = (unsigned int)v12;
  if ( (unsigned int)v12 != v12 )
  {
    v25 = -1073741675;
    goto LABEL_26;
  }
  v14 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, (unsigned int)v12);
  v15 = MmSizeOfMdl((PVOID)0xFFF, v13);
  if ( (unsigned int)v13 < 0xFFFFFFB0 )
  {
    v18 = (v15 + 7) & 0xFFFFFFF8;
    v19 = v13 + v18 + 80;
    if ( v19 >= v18 )
    {
      if ( (unsigned int)v13 > 0x905 )
      {
        if ( (unsigned int)v13 <= 0x2105 )
        {
          LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
          if ( UxDebugDisableLookaside )
          {
            v42 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0660)(
                            (unsigned int)dword_1401A0648,
                            qword_1401A0650,
                            (unsigned int)dword_1401A0658,
                            0);
          }
          else if ( UxCompactMode )
          {
            v49 = qword_1401A0640;
            CurrentNodeNumber = KeGetCurrentNodeNumber();
            v42 = (char *)PplAllocateFromLookasideListProcessor(v49, CurrentNodeNumber);
          }
          else
          {
            v41 = qword_1401A0640 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
            if ( !*(_BYTE *)(v41 + 176) )
              PplpLazyInitializeLookasideList(qword_1401A0640, v41 + 64);
            v42 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v41 + 64));
          }
          v14 = v42;
          if ( !v42 )
            goto LABEL_19;
          *(_QWORD *)(v42 + 4) = 0;
          *((_DWORD *)v42 + 3) = 0;
          *((_QWORD *)v42 + 3) = 0;
          *((_QWORD *)v42 + 4) = 0;
          *((_QWORD *)v42 + 5) = 0;
          *((_QWORD *)v42 + 6) = 0;
          *((_DWORD *)v42 + 14) = 0;
          *((_QWORD *)v42 + 9) = 0;
          *(_DWORD *)v42 = LockArray_high;
          v23 = 1;
        }
        else if ( (unsigned int)v13 > 0x4105 )
        {
          if ( UxSslLargeBufferEnabled && (unsigned int)v13 <= 0x820A )
          {
            v43 = HIDWORD(KeGetPcr()[1].LockArray);
            if ( UxDebugDisableLookaside )
            {
              v46 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A06C0)(
                      (unsigned int)dword_1401A06A8,
                      qword_1401A06B0,
                      (unsigned int)dword_1401A06B8,
                      0);
            }
            else
            {
              if ( UxCompactMode )
              {
                v53 = qword_1401A06A0;
                v45 = KeGetCurrentNodeNumber();
                v44 = v53;
              }
              else
              {
                v44 = qword_1401A06A0;
                v45 = v43;
              }
              v46 = PplAllocateFromLookasideListProcessor(v44, v45);
            }
            v14 = (_DWORD *)v46;
            if ( !v46 )
              goto LABEL_19;
            *(_QWORD *)(v46 + 4) = 0;
            *(_DWORD *)(v46 + 12) = 0;
            *(_QWORD *)(v46 + 24) = 0;
            *(_QWORD *)(v46 + 32) = 0;
            *(_QWORD *)(v46 + 40) = 0;
            *(_QWORD *)(v46 + 48) = 0;
            *(_DWORD *)(v46 + 56) = 0;
            *(_QWORD *)(v46 + 72) = 0;
            *(_DWORD *)v46 = v43;
            v23 = 3;
          }
          else
          {
            Pool3 = ExAllocatePool3(66, v19, 1397979221, UxLowPriorityPool, 1);
            v14 = (_DWORD *)Pool3;
            if ( !Pool3 )
              goto LABEL_19;
            *(_QWORD *)Pool3 = 0;
            *(_QWORD *)(Pool3 + 8) = 0;
            *(_QWORD *)(Pool3 + 24) = 0;
            *(_QWORD *)(Pool3 + 32) = 0;
            *(_QWORD *)(Pool3 + 40) = 0;
            *(_QWORD *)(Pool3 + 48) = 0;
            *(_DWORD *)(Pool3 + 56) = 0;
            *(_QWORD *)(Pool3 + 72) = 0;
            v23 = 4;
          }
        }
        else
        {
          v37 = HIDWORD(KeGetPcr()[1].LockArray);
          if ( UxDebugDisableLookaside )
          {
            v39 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0690)(
                            (unsigned int)dword_1401A0678,
                            qword_1401A0680,
                            (unsigned int)dword_1401A0688,
                            0);
          }
          else if ( UxCompactMode )
          {
            v51 = qword_1401A0670;
            v52 = KeGetCurrentNodeNumber();
            v39 = (char *)PplAllocateFromLookasideListProcessor(v51, v52);
          }
          else
          {
            v38 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(v37 + 1) << 7);
            if ( !*(_BYTE *)(v38 + 176) )
              PplpLazyInitializeLookasideList(qword_1401A0670, v38 + 64);
            v39 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v38 + 64));
          }
          v14 = v39;
          if ( !v39 )
            goto LABEL_19;
          *(_QWORD *)(v39 + 4) = 0;
          *((_DWORD *)v39 + 3) = 0;
          *((_QWORD *)v39 + 3) = 0;
          *((_QWORD *)v39 + 4) = 0;
          *((_QWORD *)v39 + 5) = 0;
          *((_QWORD *)v39 + 6) = 0;
          *((_DWORD *)v39 + 14) = 0;
          *((_QWORD *)v39 + 9) = 0;
          *(_DWORD *)v39 = v37;
          v23 = 2;
        }
      }
      else
      {
        v20 = HIDWORD(KeGetPcr()[1].LockArray);
        if ( UxDebugDisableLookaside )
        {
          v22 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0630)(
                          (unsigned int)dword_1401A0618,
                          qword_1401A0620,
                          (unsigned int)dword_1401A0628,
                          0);
        }
        else if ( UxCompactMode )
        {
          v47 = qword_1401A0610;
          v48 = KeGetCurrentNodeNumber();
          v22 = (char *)PplAllocateFromLookasideListProcessor(v47, v48);
        }
        else
        {
          v21 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(v20 + 1) << 7);
          if ( !*(_BYTE *)(v21 + 176) )
            PplpLazyInitializeLookasideList(qword_1401A0610, v21 + 64);
          v22 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v21 + 64));
        }
        v14 = v22;
        if ( !v22 )
          goto LABEL_19;
        *(_QWORD *)(v22 + 4) = 0;
        *((_DWORD *)v22 + 3) = 0;
        *((_QWORD *)v22 + 3) = 0;
        *((_QWORD *)v22 + 4) = 0;
        *((_QWORD *)v22 + 5) = 0;
        *((_QWORD *)v22 + 6) = 0;
        *((_DWORD *)v22 + 14) = 0;
        *((_QWORD *)v22 + 9) = 0;
        *(_DWORD *)v22 = v20;
        v23 = 0;
      }
      v14[4] = 1397979221;
      v14[5] = v23;
      *((_QWORD *)v14 + 8) = (char *)v14 + v18 + 80;
      v14[15] = v13;
    }
LABEL_19:
    v8 = a6;
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 15, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v14);
  if ( v14 )
  {
    v24 = *((_QWORD *)v14 + 8);
    v25 = 0;
    v26 = v14[15];
    while ( 1 )
    {
      v56 = v26;
      v61 = v24;
      if ( !v11 )
      {
        v8 = a6;
        v14[14] = v24 - v14[16];
        *v8 = v14;
        goto LABEL_26;
      }
      v28 = v7;
      if ( (unsigned int)v7 > Size )
        v28 = Size;
      v57 = v28;
      v29 = v64;
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      {
        LODWORD(v55) = a5;
        WPP_SF_qqLqqLlq((unsigned int)&v62, v16, v17, (_DWORD)a1, v24, v26, (char)v63, (char)v64, v28, v55, &v62);
      }
      v16 = a1[114];
      Size_4 = v16 + v28 + a1[115];
      if ( Size_4 > v26 )
      {
        v25 = -1073741789;
      }
      else
      {
        v30 = (char *)(v16 + v24);
        v31 = *v29;
        v7 = *v63;
        while ( 1 )
        {
          v60 = v30;
          if ( !v28 )
          {
            v24 = v61;
            v35 = a5;
            *v63 = v7;
            *v64 = v31;
            v36 = UxpSslSealMessage((_DWORD)a1, v61, Size_4, v35, (__int64)&v62);
            LODWORD(v7) = v65;
            v25 = v36;
            v28 = v57;
            v26 = v56;
            goto LABEL_45;
          }
          if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
          {
            v32 = *(char **)(v7 + 24);
          }
          else
          {
            v32 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000000u);
            v30 = v60;
          }
          if ( !v32 )
            break;
          v33 = *(_DWORD *)(v7 + 40) - v31;
          v34 = &v32[v31];
          if ( v33 <= v28 )
          {
            v7 = *(_QWORD *)v7;
            v31 = 0;
          }
          else
          {
            v31 += v28;
            v33 = v28;
          }
          memmove(v30, v34, v33);
          v30 = &v60[v33];
          v28 -= v33;
        }
        LODWORD(v7) = v65;
        v25 = -1073741670;
        v24 = v61;
        v28 = v57;
        v26 = v56;
      }
LABEL_45:
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_Dd(1041, 36, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v62, v25);
      if ( v25 < 0 )
        break;
      if ( v62 > v26 )
      {
        v25 = -1073741675;
        break;
      }
      LODWORD(v7) = v7 - v28;
      v24 += v62;
      v26 -= v62;
      v65 = v7;
      --v11;
    }
    UxSslFreeSendBufferList(v14);
    v8 = a6;
  }
  else
  {
    v25 = -1073741670;
  }
LABEL_26:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qD(1041, 34, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, *v8, v25);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14004bdc0  mov     rax, rsp
0x14004bdc3  mov     [rax+20h], r9d
0x14004bdc7  mov     [rax+18h], r8
0x14004bdcb  mov     [rax+10h], rdx
0x14004bdcf  push    rsi
0x14004bdd0  sub     rsp, 0C0h
0x14004bdd7  mov     [rax-28h], r12
0x14004bddb  xor     r12d, r12d
0x14004bdde  mov     [rax-38h], r14
0x14004bde2  mov     r14, rcx
0x14004bde5  mov     [rax-40h], r15
0x14004bde9  mov     r15d, r9d
0x14004bdec  mov     [rax+8], r12d
0x14004bdf0  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004bdf7  mov     rsi, [rsp+0C8h+arg_28]
0x14004bdff  jnz     loc_14004C4BA
0x14004be05  mov     [rsp+0C8h+var_10], rbx
0x14004be0d  mov     [rsp+0C8h+var_18], rbp
0x14004be15  mov     [rsi], r12
0x14004be18  mov     r8d, [r14+1C8h]
0x14004be1f  mov     [rsp+0C8h+var_20], rdi
0x14004be27  mov     [rsp+0C8h+var_30], r13
0x14004be2f  cmp     r8d, 10000h
0x14004be36  jnb     loc_14004C238
0x14004be3c  mov     ecx, [r14+1CCh]
0x14004be43  cmp     ecx, 10000h
0x14004be49  jnb     loc_14004C238
0x14004be4f  mov     r9d, [r14+1D0h]
0x14004be56  xor     edx, edx
0x14004be58  mov     eax, r15d
0x14004be5b  mov     dword ptr [rsp+0C8h+Size], r9d
0x14004be60  div     r9d
0x14004be63  mov     r13d, r12d
0x14004be66  test    edx, edx
0x14004be68  setnz   r13b
0x14004be6c  add     rcx, r8
0x14004be6f  add     r13d, eax
0x14004be72  mov     eax, r13d
0x14004be75  imul    rcx, rax
0x14004be79  add     rcx, r15
0x14004be7c  mov     edi, ecx
0x14004be7e  cmp     rdi, rcx
0x14004be81  jnz     loc_14004C242
0x14004be87  mov     rbx, r12
0x14004be8a  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004be91  jnz     loc_14004C3EB
0x14004be97  mov     rdx, rdi; Length
0x14004be9a  mov     ecx, 0FFFh; Base
0x14004be9f  call    cs:__imp_MmSizeOfMdl
0x14004bea6  nop     dword ptr [rax+rax+00h]
0x14004beab  lea     ecx, [rdi+50h]
0x14004beae  cmp     ecx, 50h ; 'P'
0x14004beb1  jb      loc_14004BF75
0x14004beb7  lea     esi, [rax+7]
0x14004beba  and     esi, 0FFFFFFF8h
0x14004bebd  lea     eax, [rsi+50h]
0x14004bec0  add     eax, edi
0x14004bec2  cmp     eax, esi
0x14004bec4  jb      loc_14004BF6D
0x14004beca  cmp     edi, 905h
0x14004bed0  ja      loc_14004C198
0x14004bed6  mov     ebp, gs:1A4h
0x14004bede  cmp     cs:UxDebugDisableLookaside, bl
0x14004bee4  jnz     loc_14004C24C
0x14004beea  cmp     cs:UxCompactMode, bl
0x14004bef0  jnz     loc_14004C409
0x14004bef6  mov     rcx, cs:qword_1401A0610
0x14004befd  lea     ebx, [rbp+1]
0x14004bf00  shl     rbx, 7
0x14004bf04  add     rbx, rcx
0x14004bf07  movzx   eax, byte ptr [rbx+0B0h]
0x14004bf0e  test    al, al
0x14004bf10  jz      loc_14004C42C
0x14004bf16  lea     rcx, [rbx+40h]; Lookaside
0x14004bf1a  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004bf21  nop     dword ptr [rax+rax+00h]
0x14004bf26  mov     rbx, rax
0x14004bf29  test    rax, rax
0x14004bf2c  jz      short loc_14004BF6D
0x14004bf2e  mov     [rax+4], r12
0x14004bf32  mov     [rax+0Ch], r12d
0x14004bf36  mov     [rax+18h], r12
0x14004bf3a  mov     [rax+20h], r12
0x14004bf3e  mov     [rax+28h], r12
0x14004bf42  mov     [rax+30h], r12
0x14004bf46  mov     [rax+38h], r12d
0x14004bf4a  mov     [rax+48h], r12
0x14004bf4e  mov     [rax], ebp
0x14004bf50  mov     eax, r12d
0x14004bf53  mov     ecx, esi
0x14004bf55  add     rcx, 50h ; 'P'
0x14004bf59  mov     dword ptr [rbx+10h], 53537855h
0x14004bf60  add     rcx, rbx
0x14004bf63  mov     [rbx+14h], eax
0x14004bf66  mov     [rbx+40h], rcx
0x14004bf6a  mov     [rbx+3Ch], edi
0x14004bf6d  mov     rsi, [rsp+0C8h+arg_28]
0x14004bf75  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004bf7c  jnz     loc_14004C4E7
0x14004bf82  test    rbx, rbx
0x14004bf85  jz      loc_14004C505
0x14004bf8b  mov     rbp, [rbx+40h]
0x14004bf8f  mov     edi, r12d
0x14004bf92  mov     r12d, [rbx+3Ch]
0x14004bf96  mov     [rsp+0C8h+var_68], r12d
0x14004bf9b  mov     [rsp+0C8h+var_50], rbp
0x14004bfa0  test    r13d, r13d
0x14004bfa3  jnz     short loc_14004C007
0x14004bfa5  sub     ebp, [rbx+40h]
0x14004bfa8  mov     rsi, [rsp+0C8h+arg_28]
0x14004bfb0  mov     [rbx+38h], ebp
0x14004bfb3  mov     [rsi], rbx
0x14004bfb6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004bfbd  mov     r15, [rsp+0C8h+var_40]
0x14004bfc5  mov     r14, [rsp+0C8h+var_38]
0x14004bfcd  mov     r13, [rsp+0C8h+var_30]
0x14004bfd5  mov     r12, [rsp+0C8h+var_28]
0x14004bfdd  mov     rbp, [rsp+0C8h+var_18]
0x14004bfe5  mov     rbx, [rsp+0C8h+var_10]
0x14004bfed  jnz     loc_14004C176
0x14004bff3  mov     eax, edi
0x14004bff5  mov     rdi, [rsp+0C8h+var_20]
0x14004bffd  add     rsp, 0C0h
0x14004c004  pop     rsi
0x14004c005  retn
0x14004c007  cmp     r15d, dword ptr [rsp+0C8h+Size]
0x14004c00c  mov     esi, r15d
0x14004c00f  cmova   esi, dword ptr [rsp+0C8h+Size]
0x14004c014  mov     [rsp+0C8h+var_64], esi
0x14004c018  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c01f  mov     rdi, [rsp+0C8h+arg_10]
0x14004c027  jnz     loc_14004C50F
0x14004c02d  mov     edx, [r14+1C8h]
0x14004c034  mov     eax, [r14+1CCh]
0x14004c03b  lea     ecx, [rdx+rsi]
0x14004c03e  add     eax, ecx
0x14004c040  mov     dword ptr [rsp+0C8h+Size+4], eax
0x14004c044  cmp     eax, r12d
0x14004c047  ja      loc_14004C575
0x14004c04d  mov     rax, [rsp+0C8h+arg_8]
0x14004c055  lea     r9, [rdx+rbp]
0x14004c059  mov     r12d, [rdi]
0x14004c05c  mov     r15, [rax]
0x14004c05f  mov     [rsp+0C8h+var_58], r9
0x14004c064  test    esi, esi
0x14004c066  jz      short loc_14004C0E4
0x14004c068  test    byte ptr [r15+0Ah], 5
0x14004c06d  jz      short loc_14004C0B3
0x14004c06f  mov     rax, [r15+18h]
0x14004c073  test    rax, rax
0x14004c076  jz      loc_14004C555
0x14004c07c  mov     ebp, [r15+28h]
0x14004c080  mov     edx, r12d
0x14004c083  sub     ebp, r12d
0x14004c086  add     rdx, rax; Src
0x14004c089  cmp     ebp, esi
0x14004c08b  jbe     short loc_14004C0AB
0x14004c08d  add     r12d, esi
0x14004c090  mov     ebp, esi
0x14004c092  mov     r8d, ebp; Size
0x14004c095  mov     rcx, r9; void *
0x14004c098  mov     edi, ebp
0x14004c09a  call    memmove
0x14004c09f  mov     r9, [rsp+0C8h+var_58]
0x14004c0a4  add     r9, rdi
0x14004c0a7  sub     esi, ebp
0x14004c0a9  jmp     short loc_14004C05F
0x14004c0ab  mov     r15, [r15]
0x14004c0ae  xor     r12d, r12d
0x14004c0b1  jmp     short loc_14004C092
0x14004c0b3  mov     [rsp+0C8h+Priority], 40000000h; Priority
0x14004c0bb  xor     r9d, r9d; RequestedAddress
0x14004c0be  xor     edx, edx; AccessMode
0x14004c0c0  mov     [rsp+0C8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004c0c8  mov     r8d, 1; CacheType
0x14004c0ce  mov     rcx, r15; MemoryDescriptorList
0x14004c0d1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004c0d8  nop     dword ptr [rax+rax+00h]
0x14004c0dd  mov     r9, [rsp+0C8h+var_58]
0x14004c0e2  jmp     short loc_14004C073
0x14004c0e4  mov     rax, [rsp+0C8h+arg_8]
0x14004c0ec  mov     rcx, r14
0x14004c0ef  mov     rbp, [rsp+0C8h+var_50]
0x14004c0f4  movzx   r9d, [rsp+0C8h+arg_20]
0x14004c0fd  mov     rdx, rbp
0x14004c100  mov     r8d, dword ptr [rsp+0C8h+Size+4]
0x14004c105  mov     [rax], r15
0x14004c108  mov     rax, [rsp+0C8h+arg_10]
0x14004c110  mov     [rax], r12d
0x14004c113  lea     rax, [rsp+0C8h+arg_0]
0x14004c11b  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rax
0x14004c120  call    UxpSslSealMessage
0x14004c125  mov     r15d, [rsp+0C8h+arg_18]
0x14004c12d  mov     edi, eax
0x14004c12f  mov     esi, [rsp+0C8h+var_64]
0x14004c133  mov     r12d, [rsp+0C8h+var_68]
0x14004c138  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c13f  jnz     loc_14004C57F
0x14004c145  test    edi, edi
0x14004c147  js      loc_14004C5AB
0x14004c14d  mov     ecx, [rsp+0C8h+arg_0]
0x14004c154  cmp     ecx, r12d
0x14004c157  ja      loc_14004C5A6
0x14004c15d  sub     r15d, esi
0x14004c160  add     rbp, rcx
0x14004c163  sub     r12d, ecx
0x14004c166  mov     [rsp+0C8h+arg_18], r15d
0x14004c16e  dec     r13d
0x14004c171  jmp     loc_14004BF96
0x14004c176  mov     r9, [rsi]
0x14004c179  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004c180  mov     edx, 22h ; '"'
0x14004c185  mov     [rsp+0C8h+BugCheckOnFailure], edi
0x14004c189  mov     ecx, 411h
0x14004c18e  call    WPP_SF_qD
0x14004c193  jmp     loc_14004BFF3
0x14004c198  cmp     edi, 2105h
0x14004c19e  jbe     loc_14004C274
0x14004c1a4  cmp     edi, 4105h
0x14004c1aa  ja      loc_14004C34C
0x14004c1b0  mov     ebp, gs:1A4h
0x14004c1b8  cmp     cs:UxDebugDisableLookaside, bl
0x14004c1be  jnz     loc_14004C2FC
0x14004c1c4  cmp     cs:UxCompactMode, bl
0x14004c1ca  jnz     loc_14004C46B
0x14004c1d0  mov     rcx, cs:qword_1401A0670
0x14004c1d7  lea     ebx, [rbp+1]
0x14004c1da  shl     rbx, 7
0x14004c1de  add     rbx, rcx
0x14004c1e1  movzx   eax, byte ptr [rbx+0B0h]
0x14004c1e8  test    al, al
0x14004c1ea  jz      loc_14004C48E
0x14004c1f0  lea     rcx, [rbx+40h]; Lookaside
0x14004c1f4  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004c1fb  nop     dword ptr [rax+rax+00h]
0x14004c200  mov     rbx, rax
0x14004c203  test    rax, rax
0x14004c206  jz      loc_14004BF6D
0x14004c20c  mov     [rax+4], r12
0x14004c210  mov     [rax+0Ch], r12d
0x14004c214  mov     [rax+18h], r12
0x14004c218  mov     [rax+20h], r12
0x14004c21c  mov     [rax+28h], r12
0x14004c220  mov     [rax+30h], r12
0x14004c224  mov     [rax+38h], r12d
0x14004c228  mov     [rax+48h], r12
0x14004c22c  mov     [rax], ebp
0x14004c22e  mov     eax, 2
0x14004c233  jmp     loc_14004BF53
0x14004c238  mov     edi, 0C000000Dh
0x14004c23d  jmp     loc_14004BFB6
0x14004c242  mov     edi, 0C0000095h
0x14004c247  jmp     loc_14004BFB6
0x14004c24c  mov     rax, cs:off_1401A0630
0x14004c253  xor     r9d, r9d
0x14004c256  mov     r8d, cs:dword_1401A0628
0x14004c25d  mov     rdx, cs:qword_1401A0620
0x14004c264  mov     ecx, cs:dword_1401A0618
0x14004c26a  call    _guard_dispatch_icall
0x14004c26f  jmp     loc_14004BF26
0x14004c274  mov     ebp, gs:1A4h
0x14004c27c  cmp     cs:UxDebugDisableLookaside, bl
0x14004c282  jnz     loc_14004C324
0x14004c288  cmp     cs:UxCompactMode, bl
0x14004c28e  jnz     loc_14004C43A
0x14004c294  mov     rcx, cs:qword_1401A0640
0x14004c29b  lea     ebx, [rbp+1]
0x14004c29e  shl     rbx, 7
0x14004c2a2  add     rbx, rcx
0x14004c2a5  movzx   eax, byte ptr [rbx+0B0h]
0x14004c2ac  test    al, al
0x14004c2ae  jz      loc_14004C45D
0x14004c2b4  lea     rcx, [rbx+40h]; Lookaside
0x14004c2b8  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004c2bf  nop     dword ptr [rax+rax+00h]
0x14004c2c4  mov     rbx, rax
0x14004c2c7  test    rax, rax
0x14004c2ca  jz      loc_14004BF6D
0x14004c2d0  mov     [rax+4], r12
0x14004c2d4  mov     [rax+0Ch], r12d
0x14004c2d8  mov     [rax+18h], r12
0x14004c2dc  mov     [rax+20h], r12
0x14004c2e0  mov     [rax+28h], r12
0x14004c2e4  mov     [rax+30h], r12
0x14004c2e8  mov     [rax+38h], r12d
0x14004c2ec  mov     [rax+48h], r12
0x14004c2f0  mov     [rax], ebp
0x14004c2f2  mov     eax, 1
0x14004c2f7  jmp     loc_14004BF53
0x14004c2fc  mov     rax, cs:off_1401A0690
0x14004c303  xor     r9d, r9d
0x14004c306  mov     r8d, cs:dword_1401A0688
0x14004c30d  mov     rdx, cs:qword_1401A0680
0x14004c314  mov     ecx, cs:dword_1401A0678
0x14004c31a  call    _guard_dispatch_icall
0x14004c31f  jmp     loc_14004C200
0x14004c324  mov     rax, cs:off_1401A0660
0x14004c32b  xor     r9d, r9d
0x14004c32e  mov     r8d, cs:dword_1401A0658
0x14004c335  mov     rdx, cs:qword_1401A0650
  ... truncated ...
```
