# UxpSslPrepareSendBuffer

- ea: `0x14004bde0`
- end: `0x14004c5e0`
- name: `UxpSslPrepareSendBuffer`
- size: `2048`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14013b034`
- `0x14013b0ec`

## callees

- `0x140049d28`
- `0x14004ba90`
- `0x14004bde0`
- `0x14004d150`
- `0x140051410`
- `0x1401677e0`
- `0x140167840`
- `0x1401c3f78`
- `0x1401d5a48`
- `0x1401d5b20`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c0f1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c0f1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004bf3a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c214`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c2d8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004bf3a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c214`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c2d8`
- `ntoskrnl!MmSizeOfMdl` at `0x14004bebf`
- `ntoskrnl!MmSizeOfMdl` at `0x14004bebf`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c430`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c461`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c492`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c4c3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c430`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c461`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c492`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004c4c3`
- `ntoskrnl!ExAllocatePool3` at `0x140176444`
- `ntoskrnl!ExAllocatePool3` at `0x140176444`

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
0x14004bde0  mov     rax, rsp
0x14004bde3  mov     [rax+20h], r9d
0x14004bde7  mov     [rax+18h], r8
0x14004bdeb  mov     [rax+10h], rdx
0x14004bdef  push    rsi
0x14004bdf0  sub     rsp, 0C0h
0x14004bdf7  mov     [rax-28h], r12
0x14004bdfb  xor     r12d, r12d
0x14004bdfe  mov     [rax-38h], r14
0x14004be02  mov     r14, rcx
0x14004be05  mov     [rax-40h], r15
0x14004be09  mov     r15d, r9d
0x14004be0c  mov     [rax+8], r12d
0x14004be10  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004be17  mov     rsi, [rsp+0C8h+arg_28]
0x14004be1f  jnz     loc_14004C4DA
0x14004be25  mov     [rsp+0C8h+var_10], rbx
0x14004be2d  mov     [rsp+0C8h+var_18], rbp
0x14004be35  mov     [rsi], r12
0x14004be38  mov     r8d, [r14+1C8h]
0x14004be3f  mov     [rsp+0C8h+var_20], rdi
0x14004be47  mov     [rsp+0C8h+var_30], r13
0x14004be4f  cmp     r8d, 10000h
0x14004be56  jnb     loc_14004C258
0x14004be5c  mov     ecx, [r14+1CCh]
0x14004be63  cmp     ecx, 10000h
0x14004be69  jnb     loc_14004C258
0x14004be6f  mov     r9d, [r14+1D0h]
0x14004be76  xor     edx, edx
0x14004be78  mov     eax, r15d
0x14004be7b  mov     dword ptr [rsp+0C8h+Size], r9d
0x14004be80  div     r9d
0x14004be83  mov     r13d, r12d
0x14004be86  test    edx, edx
0x14004be88  setnz   r13b
0x14004be8c  add     rcx, r8
0x14004be8f  add     r13d, eax
0x14004be92  mov     eax, r13d
0x14004be95  imul    rcx, rax
0x14004be99  add     rcx, r15
0x14004be9c  mov     edi, ecx
0x14004be9e  cmp     rdi, rcx
0x14004bea1  jnz     loc_14004C262
0x14004bea7  mov     rbx, r12
0x14004beaa  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004beb1  jnz     loc_14004C40B
0x14004beb7  mov     rdx, rdi; Length
0x14004beba  mov     ecx, 0FFFh; Base
0x14004bebf  call    cs:__imp_MmSizeOfMdl
0x14004bec6  nop     dword ptr [rax+rax+00h]
0x14004becb  lea     ecx, [rdi+50h]
0x14004bece  cmp     ecx, 50h ; 'P'
0x14004bed1  jb      loc_14004BF95
0x14004bed7  lea     esi, [rax+7]
0x14004beda  and     esi, 0FFFFFFF8h
0x14004bedd  lea     eax, [rsi+50h]
0x14004bee0  add     eax, edi
0x14004bee2  cmp     eax, esi
0x14004bee4  jb      loc_14004BF8D
0x14004beea  cmp     edi, 905h
0x14004bef0  ja      loc_14004C1B8
0x14004bef6  mov     ebp, gs:1A4h
0x14004befe  cmp     cs:UxDebugDisableLookaside, bl
0x14004bf04  jnz     loc_14004C26C
0x14004bf0a  cmp     cs:UxCompactMode, bl
0x14004bf10  jnz     loc_14004C429
0x14004bf16  mov     rcx, cs:qword_1401A0610
0x14004bf1d  lea     ebx, [rbp+1]
0x14004bf20  shl     rbx, 7
0x14004bf24  add     rbx, rcx
0x14004bf27  movzx   eax, byte ptr [rbx+0B0h]
0x14004bf2e  test    al, al
0x14004bf30  jz      loc_14004C44C
0x14004bf36  lea     rcx, [rbx+40h]; Lookaside
0x14004bf3a  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004bf41  nop     dword ptr [rax+rax+00h]
0x14004bf46  mov     rbx, rax
0x14004bf49  test    rax, rax
0x14004bf4c  jz      short loc_14004BF8D
0x14004bf4e  mov     [rax+4], r12
0x14004bf52  mov     [rax+0Ch], r12d
0x14004bf56  mov     [rax+18h], r12
0x14004bf5a  mov     [rax+20h], r12
0x14004bf5e  mov     [rax+28h], r12
0x14004bf62  mov     [rax+30h], r12
0x14004bf66  mov     [rax+38h], r12d
0x14004bf6a  mov     [rax+48h], r12
0x14004bf6e  mov     [rax], ebp
0x14004bf70  mov     eax, r12d
0x14004bf73  mov     ecx, esi
0x14004bf75  add     rcx, 50h ; 'P'
0x14004bf79  mov     dword ptr [rbx+10h], 53537855h
0x14004bf80  add     rcx, rbx
0x14004bf83  mov     [rbx+14h], eax
0x14004bf86  mov     [rbx+40h], rcx
0x14004bf8a  mov     [rbx+3Ch], edi
0x14004bf8d  mov     rsi, [rsp+0C8h+arg_28]
0x14004bf95  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004bf9c  jnz     loc_14004C507
0x14004bfa2  test    rbx, rbx
0x14004bfa5  jz      loc_14004C525
0x14004bfab  mov     rbp, [rbx+40h]
0x14004bfaf  mov     edi, r12d
0x14004bfb2  mov     r12d, [rbx+3Ch]
0x14004bfb6  mov     [rsp+0C8h+var_68], r12d
0x14004bfbb  mov     [rsp+0C8h+var_50], rbp
0x14004bfc0  test    r13d, r13d
0x14004bfc3  jnz     short loc_14004C027
0x14004bfc5  sub     ebp, [rbx+40h]
0x14004bfc8  mov     rsi, [rsp+0C8h+arg_28]
0x14004bfd0  mov     [rbx+38h], ebp
0x14004bfd3  mov     [rsi], rbx
0x14004bfd6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004bfdd  mov     r15, [rsp+0C8h+var_40]
0x14004bfe5  mov     r14, [rsp+0C8h+var_38]
0x14004bfed  mov     r13, [rsp+0C8h+var_30]
0x14004bff5  mov     r12, [rsp+0C8h+var_28]
0x14004bffd  mov     rbp, [rsp+0C8h+var_18]
0x14004c005  mov     rbx, [rsp+0C8h+var_10]
0x14004c00d  jnz     loc_14004C196
0x14004c013  mov     eax, edi
0x14004c015  mov     rdi, [rsp+0C8h+var_20]
0x14004c01d  add     rsp, 0C0h
0x14004c024  pop     rsi
0x14004c025  retn
0x14004c027  cmp     r15d, dword ptr [rsp+0C8h+Size]
0x14004c02c  mov     esi, r15d
0x14004c02f  cmova   esi, dword ptr [rsp+0C8h+Size]
0x14004c034  mov     [rsp+0C8h+var_64], esi
0x14004c038  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c03f  mov     rdi, [rsp+0C8h+arg_10]
0x14004c047  jnz     loc_14004C52F
0x14004c04d  mov     edx, [r14+1C8h]
0x14004c054  mov     eax, [r14+1CCh]
0x14004c05b  lea     ecx, [rdx+rsi]
0x14004c05e  add     eax, ecx
0x14004c060  mov     dword ptr [rsp+0C8h+Size+4], eax
0x14004c064  cmp     eax, r12d
0x14004c067  ja      loc_14004C595
0x14004c06d  mov     rax, [rsp+0C8h+arg_8]
0x14004c075  lea     r9, [rdx+rbp]
0x14004c079  mov     r12d, [rdi]
0x14004c07c  mov     r15, [rax]
0x14004c07f  mov     [rsp+0C8h+var_58], r9
0x14004c084  test    esi, esi
0x14004c086  jz      short loc_14004C104
0x14004c088  test    byte ptr [r15+0Ah], 5
0x14004c08d  jz      short loc_14004C0D3
0x14004c08f  mov     rax, [r15+18h]
0x14004c093  test    rax, rax
0x14004c096  jz      loc_14004C575
0x14004c09c  mov     ebp, [r15+28h]
0x14004c0a0  mov     edx, r12d
0x14004c0a3  sub     ebp, r12d
0x14004c0a6  add     rdx, rax; Src
0x14004c0a9  cmp     ebp, esi
0x14004c0ab  jbe     short loc_14004C0CB
0x14004c0ad  add     r12d, esi
0x14004c0b0  mov     ebp, esi
0x14004c0b2  mov     r8d, ebp; Size
0x14004c0b5  mov     rcx, r9; void *
0x14004c0b8  mov     edi, ebp
0x14004c0ba  call    memmove
0x14004c0bf  mov     r9, [rsp+0C8h+var_58]
0x14004c0c4  add     r9, rdi
0x14004c0c7  sub     esi, ebp
0x14004c0c9  jmp     short loc_14004C07F
0x14004c0cb  mov     r15, [r15]
0x14004c0ce  xor     r12d, r12d
0x14004c0d1  jmp     short loc_14004C0B2
0x14004c0d3  mov     [rsp+0C8h+Priority], 40000000h; Priority
0x14004c0db  xor     r9d, r9d; RequestedAddress
0x14004c0de  xor     edx, edx; AccessMode
0x14004c0e0  mov     [rsp+0C8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004c0e8  mov     r8d, 1; CacheType
0x14004c0ee  mov     rcx, r15; MemoryDescriptorList
0x14004c0f1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004c0f8  nop     dword ptr [rax+rax+00h]
0x14004c0fd  mov     r9, [rsp+0C8h+var_58]
0x14004c102  jmp     short loc_14004C093
0x14004c104  mov     rax, [rsp+0C8h+arg_8]
0x14004c10c  mov     rcx, r14
0x14004c10f  mov     rbp, [rsp+0C8h+var_50]
0x14004c114  movzx   r9d, [rsp+0C8h+arg_20]
0x14004c11d  mov     rdx, rbp
0x14004c120  mov     r8d, dword ptr [rsp+0C8h+Size+4]
0x14004c125  mov     [rax], r15
0x14004c128  mov     rax, [rsp+0C8h+arg_10]
0x14004c130  mov     [rax], r12d
0x14004c133  lea     rax, [rsp+0C8h+arg_0]
0x14004c13b  mov     qword ptr [rsp+0C8h+BugCheckOnFailure], rax
0x14004c140  call    UxpSslSealMessage
0x14004c145  mov     r15d, [rsp+0C8h+arg_18]
0x14004c14d  mov     edi, eax
0x14004c14f  mov     esi, [rsp+0C8h+var_64]
0x14004c153  mov     r12d, [rsp+0C8h+var_68]
0x14004c158  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c15f  jnz     loc_14004C59F
0x14004c165  test    edi, edi
0x14004c167  js      loc_14004C5CB
0x14004c16d  mov     ecx, [rsp+0C8h+arg_0]
0x14004c174  cmp     ecx, r12d
0x14004c177  ja      loc_14004C5C6
0x14004c17d  sub     r15d, esi
0x14004c180  add     rbp, rcx
0x14004c183  sub     r12d, ecx
0x14004c186  mov     [rsp+0C8h+arg_18], r15d
0x14004c18e  dec     r13d
0x14004c191  jmp     loc_14004BFB6
0x14004c196  mov     r9, [rsi]
0x14004c199  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004c1a0  mov     edx, 22h ; '"'
0x14004c1a5  mov     [rsp+0C8h+BugCheckOnFailure], edi
0x14004c1a9  mov     ecx, 411h
0x14004c1ae  call    WPP_SF_qD
0x14004c1b3  jmp     loc_14004C013
0x14004c1b8  cmp     edi, 2105h
0x14004c1be  jbe     loc_14004C294
0x14004c1c4  cmp     edi, 4105h
0x14004c1ca  ja      loc_14004C36C
0x14004c1d0  mov     ebp, gs:1A4h
0x14004c1d8  cmp     cs:UxDebugDisableLookaside, bl
0x14004c1de  jnz     loc_14004C31C
0x14004c1e4  cmp     cs:UxCompactMode, bl
0x14004c1ea  jnz     loc_14004C48B
0x14004c1f0  mov     rcx, cs:qword_1401A0670
0x14004c1f7  lea     ebx, [rbp+1]
0x14004c1fa  shl     rbx, 7
0x14004c1fe  add     rbx, rcx
0x14004c201  movzx   eax, byte ptr [rbx+0B0h]
0x14004c208  test    al, al
0x14004c20a  jz      loc_14004C4AE
0x14004c210  lea     rcx, [rbx+40h]; Lookaside
0x14004c214  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004c21b  nop     dword ptr [rax+rax+00h]
0x14004c220  mov     rbx, rax
0x14004c223  test    rax, rax
0x14004c226  jz      loc_14004BF8D
0x14004c22c  mov     [rax+4], r12
0x14004c230  mov     [rax+0Ch], r12d
0x14004c234  mov     [rax+18h], r12
0x14004c238  mov     [rax+20h], r12
0x14004c23c  mov     [rax+28h], r12
0x14004c240  mov     [rax+30h], r12
0x14004c244  mov     [rax+38h], r12d
0x14004c248  mov     [rax+48h], r12
0x14004c24c  mov     [rax], ebp
0x14004c24e  mov     eax, 2
0x14004c253  jmp     loc_14004BF73
0x14004c258  mov     edi, 0C000000Dh
0x14004c25d  jmp     loc_14004BFD6
0x14004c262  mov     edi, 0C0000095h
0x14004c267  jmp     loc_14004BFD6
0x14004c26c  mov     rax, cs:off_1401A0630
0x14004c273  xor     r9d, r9d
0x14004c276  mov     r8d, cs:dword_1401A0628
0x14004c27d  mov     rdx, cs:qword_1401A0620
0x14004c284  mov     ecx, cs:dword_1401A0618
0x14004c28a  call    _guard_dispatch_icall
0x14004c28f  jmp     loc_14004BF46
0x14004c294  mov     ebp, gs:1A4h
0x14004c29c  cmp     cs:UxDebugDisableLookaside, bl
0x14004c2a2  jnz     loc_14004C344
0x14004c2a8  cmp     cs:UxCompactMode, bl
0x14004c2ae  jnz     loc_14004C45A
0x14004c2b4  mov     rcx, cs:qword_1401A0640
0x14004c2bb  lea     ebx, [rbp+1]
0x14004c2be  shl     rbx, 7
0x14004c2c2  add     rbx, rcx
0x14004c2c5  movzx   eax, byte ptr [rbx+0B0h]
0x14004c2cc  test    al, al
0x14004c2ce  jz      loc_14004C47D
0x14004c2d4  lea     rcx, [rbx+40h]; Lookaside
0x14004c2d8  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004c2df  nop     dword ptr [rax+rax+00h]
0x14004c2e4  mov     rbx, rax
0x14004c2e7  test    rax, rax
0x14004c2ea  jz      loc_14004BF8D
0x14004c2f0  mov     [rax+4], r12
0x14004c2f4  mov     [rax+0Ch], r12d
0x14004c2f8  mov     [rax+18h], r12
0x14004c2fc  mov     [rax+20h], r12
0x14004c300  mov     [rax+28h], r12
0x14004c304  mov     [rax+30h], r12
0x14004c308  mov     [rax+38h], r12d
0x14004c30c  mov     [rax+48h], r12
0x14004c310  mov     [rax], ebp
0x14004c312  mov     eax, 1
0x14004c317  jmp     loc_14004BF73
0x14004c31c  mov     rax, cs:off_1401A0690
0x14004c323  xor     r9d, r9d
0x14004c326  mov     r8d, cs:dword_1401A0688
0x14004c32d  mov     rdx, cs:qword_1401A0680
0x14004c334  mov     ecx, cs:dword_1401A0678
0x14004c33a  call    _guard_dispatch_icall
0x14004c33f  jmp     loc_14004C220
0x14004c344  mov     rax, cs:off_1401A0660
0x14004c34b  xor     r9d, r9d
0x14004c34e  mov     r8d, cs:dword_1401A0658
0x14004c355  mov     rdx, cs:qword_1401A0650
  ... truncated ...
```
