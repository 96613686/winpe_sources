# RxPurgeConflictingSrvOpensEx

- ea: `0x14005b620`
- end: `0x14005be87`
- name: `RxPurgeConflictingSrvOpensEx`
- size: `2151`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `5`
- callee_count: `13`
- tags: ``

## callers

- `0x1400511d0`
- `0x14005a850`
- `0x14006c5c0`
- `0x14006f9e0`
- `0x140072a80`

## callees

- `0x140014c10`
- `0x140015230`
- `0x140016e20`
- `0x140016e70`
- `0x140017370`
- `0x140018480`
- `0x140024338`
- `0x140057a80`
- `0x14005b620`
- `0x14005c5f0`
- `0x14006aa40`
- `0x14006ba40`
- `0x140071c90`

## import_xrefs

- `ntoskrnl!FsRtlIsExtentDangling` at `0x14007d136`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x14007d136`
- `ntoskrnl!MmIsFileSectionActive` at `0x14005b81f`
- `ntoskrnl!MmIsFileSectionActive` at `0x14005b81f`
- `ntoskrnl!ObReferenceObjectSafe` at `0x14005bb8d`
- `ntoskrnl!ObReferenceObjectSafe` at `0x14005bb8d`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14005bba4`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14005bba4`
- `ntoskrnl!KeBugCheckEx` at `0x14005be7a`
- `ntoskrnl!KeBugCheckEx` at `0x14005be7a`

## pseudocode

```c
__int64 __fastcall RxPurgeConflictingSrvOpensEx(ULONG_PTR BugCheckParameter2, char a2, int *a3, _DWORD *a4)
{
  unsigned int v4; // edi
  _DWORD *v5; // r15
  char v6; // r14
  int v8; // esi
  unsigned int v9; // r15d
  int v10; // ebp
  int v12; // r13d
  char v13; // bp
  int v14; // r14d
  int v15; // esi
  int v16; // ebp
  unsigned int v17; // eax
  __int128 v18; // xmm1
  __int64 v19; // rcx
  _QWORD *v20; // rsi
  _QWORD *v21; // rax
  bool v22; // dl
  _DWORD *v23; // rbp
  _QWORD *v24; // rax
  _DWORD *v25; // r13
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // r8
  unsigned int *v28; // r14
  int v29; // r14d
  LIST_ENTRY *v30; // rcx
  LIST_ENTRY *v31; // rax
  struct _FOBX *v32; // r14
  int v33; // esi
  struct _FOBX *v34; // rdi
  LIST_ENTRY *p_ClosePendingList; // rax
  struct _FOBX *v36; // r15
  ULONG FobxSerialNumber; // eax
  PMRX_PIPE_HANDLE_INFORMATION PipeHandleInformation; // r13
  __int64 v39; // r8
  __int64 v40; // rdx
  unsigned int i; // r15d
  int v42; // eax
  __int64 v43; // rdx
  unsigned __int64 IsExtentDangling; // rax
  BOOLEAN FlushFile[8]; // [rsp+20h] [rbp-C8h]
  __int64 v46; // [rsp+28h] [rbp-C0h]
  __int64 v47; // [rsp+30h] [rbp-B8h]
  __int64 v48; // [rsp+38h] [rbp-B0h]
  unsigned int v49; // [rsp+40h] [rbp-A8h]
  char v50; // [rsp+50h] [rbp-98h]
  int v51; // [rsp+54h] [rbp-94h]
  int v52; // [rsp+58h] [rbp-90h]
  _OWORD v53[2]; // [rsp+60h] [rbp-88h] BYREF
  unsigned __int64 v54; // [rsp+80h] [rbp-68h]
  _QWORD *v55; // [rsp+88h] [rbp-60h]
  __int64 v56; // [rsp+90h] [rbp-58h]
  BOOL v57; // [rsp+F0h] [rbp+8h] BYREF
  char v58; // [rsp+F8h] [rbp+10h]
  char v59; // [rsp+100h] [rbp+18h]
  _DWORD *v60; // [rsp+108h] [rbp+20h]

  v60 = a4;
  v58 = a2;
  v4 = 0;
  v52 = 0;
  v5 = a4;
  v6 = a2;
  memset(v53, 0, 28);
  if ( !a3 || (*(_BYTE *)(BugCheckParameter2 + 156) & 1) != 0 )
  {
    v59 = 1;
    v51 = 3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        &WPP_34a45793cf6d31669b6348460c85d061_Traceguids,
        BugCheckParameter2);
    }
  }
  else
  {
    v8 = *a3;
    v9 = a3[5];
    v10 = a3[6];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        &WPP_34a45793cf6d31669b6348460c85d061_Traceguids,
        BugCheckParameter2,
        v8,
        v9,
        a3[7],
        v10);
    }
    if ( (v8 & 0xFFEFFE7F) == 0 )
      return v4;
    if ( (v10 & 0xFFFFFFFB) == 0 || (v12 = 0, v10 == 5) )
      v12 = 3;
    v52 = 0;
    v13 = v8;
    v14 = v8 & 6;
    v15 = v8 & 0x10000;
    v16 = v13 & 0x21;
    if ( v16 || v14 || v15 )
    {
      if ( (v17 = *(_DWORD *)(BugCheckParameter2 + 424), v16) && *(_DWORD *)(BugCheckParameter2 + 440) < v17
        || v14 && *(_DWORD *)(BugCheckParameter2 + 444) < v17
        || v15 && *(_DWORD *)(BugCheckParameter2 + 448) < v17
        || *(_DWORD *)(BugCheckParameter2 + 428) && (v9 & 1) == 0
        || *(_DWORD *)(BugCheckParameter2 + 432) && (v9 & 2) == 0
        || *(_DWORD *)(BugCheckParameter2 + 436) && (v9 & 4) == 0 )
      {
        v4 = -1073741757;
        v52 = -1073741757;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids, v4);
    }
    if ( (v4 & 0x80000000) != 0 )
      return v4;
    v59 = 0;
    v18 = *(_OWORD *)(BugCheckParameter2 + 436);
    v53[0] = *(_OWORD *)(BugCheckParameter2 + 424);
    *(_OWORD *)((char *)v53 + 12) = v18;
    if ( v16 || v14 || v15 )
    {
      ++LODWORD(v53[0]);
      DWORD1(v53[0]) += v16 != 0;
      DWORD2(v53[0]) += v14 != 0;
      HIDWORD(v53[0]) += v15 != 0;
      LODWORD(v53[1]) += v9 & 1;
      DWORD1(v53[1]) += (v9 >> 1) & 1;
      DWORD2(v53[1]) += (v9 >> 2) & 1;
    }
    if ( (*(_DWORD *)(BugCheckParameter2 + 164) & 0x10) == 0 || (*(_DWORD *)(BugCheckParameter2 + 164) & 0x20) != 0 )
    {
      v6 = v58;
      v5 = v60;
      v51 = v12 | 1;
    }
    else
    {
      v6 = v58;
      v5 = v60;
      v51 = 3;
    }
  }
  v19 = *(_QWORD *)(BugCheckParameter2 + 304) + 8LL;
  v50 = 0;
  v57 = 0;
  MmIsFileSectionActive(v19, 7, &v57);
  v20 = (_QWORD *)(BugCheckParameter2 + 264);
  v21 = (_QWORD *)(BugCheckParameter2 + 264);
  v22 = v57;
  *(_BYTE *)(BugCheckParameter2 + 641) |= 1u;
  LOBYTE(v57) = v22;
  do
  {
    v21 = (_QWORD *)*v21;
    if ( v21 == v20 )
    {
      v23 = 0;
      break;
    }
    v23 = v21 - 17;
  }
  while ( *((_WORD *)v21 - 68) == 0xEBAA );
  while ( v23 )
  {
    v24 = v23 + 34;
    while ( 1 )
    {
      v24 = (_QWORD *)*v24;
      if ( v24 == v20 )
        break;
      v25 = v24 - 17;
      v55 = v24 - 17;
      if ( *((_WORD *)v24 - 68) != 0xEBAA )
        goto LABEL_34;
    }
    v25 = 0;
    v55 = 0;
LABEL_34:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids, v23, v25);
      v22 = v57;
    }
    if ( v23 == v25 )
      KeBugCheckEx(0x27u, 0xC0110327, BugCheckParameter2, (ULONG_PTR)v23, 0);
    if ( v23[41] == 1 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v40 = 15;
        goto LABEL_143;
      }
      goto LABEL_43;
    }
    if ( (v23[18] & 0x200) != 0 && !v6 && !v59 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v40 = 16;
        goto LABEL_143;
      }
      goto LABEL_43;
    }
    if ( *(_WORD *)BugCheckParameter2 == 0xEC21 && (v23[18] & 0x200) != 0 && !v6 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v40 = 17;
        goto LABEL_143;
      }
      goto LABEL_43;
    }
    v27 = (unsigned int)v23[22];
    if ( (int)v27 > 0 && (int)v27 > v23[24] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids);
        goto LABEL_97;
      }
      goto LABEL_43;
    }
    if ( v5 && v23 == v5 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids, v23, v5);
        goto LABEL_97;
      }
      goto LABEL_43;
    }
    v28 = *(unsigned int **)(BugCheckParameter2 + 712);
    if ( v28 && *(_DWORD **)(BugCheckParameter2 + 720) == v23 )
    {
      for ( i = 0; i < *v28; ++i )
      {
        v43 = *(_QWORD *)&v28[4 * i + 6];
        v54 = *(_QWORD *)&v28[4 * i + 4];
        v56 = v43;
        IsExtentDangling = FsRtlIsExtentDangling(v54, v43, 0);
        if ( v54 <= IsExtentDangling )
        {
          v27 = v54 + v56;
          if ( IsExtentDangling < v54 + v56 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v49 = i;
              v48 = v54 + v56;
              HIDWORD(v47) = HIDWORD(v54);
              HIDWORD(v46) = HIDWORD(IsExtentDangling);
              *(_DWORD *)&FlushFile[4] = HIDWORD(BugCheckParameter2);
              WPP_SF_qqqqqD(WPP_GLOBAL_Control->AttachedDevice, v54, v27, v23);
            }
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              v40 = 20;
LABEL_143:
              WPP_SF_q(v26->AttachedDevice, v40, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids, v23);
            }
LABEL_97:
            v22 = v57;
            goto LABEL_43;
          }
        }
      }
      v22 = v57;
    }
    v29 = v23[18] & 8;
    LODWORD(v54) = v29;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LODWORD(v48) = v22;
      LODWORD(v47) = v23[25];
      LODWORD(v46) = v23[23];
      *(_DWORD *)FlushFile = v29 != 0;
      WPP_SF_qdddd(WPP_GLOBAL_Control->AttachedDevice, v29 != 0, v27, v23, *(_QWORD *)FlushFile, v46, v47, v48, v49);
      v22 = v57;
    }
    if ( v29 || v23[23] == v23[25] || !v22 )
    {
      if ( v51 == 1 )
      {
        v42 = RxCheckShareAccess(v53, (unsigned int)v23[30], (unsigned int)v23[31]);
        v22 = v57;
        if ( v42 >= 0 )
          goto LABEL_43;
      }
      else if ( v51 != 3 )
      {
        goto LABEL_43;
      }
      if ( !v29 && (int)v23[23] > 0 )
      {
        v23[18] |= 0x1000u;
        v50 = 1;
      }
      v30 = (LIST_ENTRY *)(v23 + 46);
      v31 = (LIST_ENTRY *)(v23 + 46);
      do
      {
        v31 = v31->Flink;
        if ( v31 == v30 )
          goto LABEL_43;
        v32 = (struct _FOBX *)&v31[-7];
      }
      while ( LOWORD(v31[-7].Flink) == 0xEBAA );
      if ( v31 != (LIST_ENTRY *)112 )
      {
        v33 = v54;
        v34 = (struct _FOBX *)v60;
        while ( 1 )
        {
          p_ClosePendingList = &v32->ClosePendingList;
          while ( 1 )
          {
            p_ClosePendingList = p_ClosePendingList->Flink;
            if ( p_ClosePendingList == v30 )
              break;
            v36 = (struct _FOBX *)&p_ClosePendingList[-7];
            if ( LOWORD(p_ClosePendingList[-7].Flink) != 0xEBAA )
              goto LABEL_87;
          }
          v36 = 0;
LABEL_87:
          if ( v34 && v32 == v34 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                22,
                &WPP_34a45793cf6d31669b6348460c85d061_Traceguids,
                v32,
                v34);
            }
          }
          else
          {
            FobxSerialNumber = v32->FobxSerialNumber;
            if ( (FobxSerialNumber & 0x40000000) == 0 )
            {
              if ( (FobxSerialNumber & 0x400000) == 0 )
                goto LABEL_91;
              PipeHandleInformation = v32->PipeHandleInformation;
              if ( !PipeHandleInformation )
                goto LABEL_91;
              if ( (unsigned __int8)ObReferenceObjectSafe(v32->PipeHandleInformation) )
              {
                ObDereferenceObjectDeferDelete(PipeHandleInformation);
LABEL_91:
                if ( v33 || !v23[23] )
                {
                  if ( !BYTE2(v32->Specific.DiskFile.PredictedReadOffset) )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v32->1 + 5) + 192LL));
                    BYTE2(v32->Specific.DiskFile.PredictedReadOffset) = 1;
                  }
                  RxCloseAssociatedSrvOpen(0, v32);
                  LOBYTE(v39) = 1;
                  RxFcbScavengeRelatedFobxs(BugCheckParameter2, v32, v39);
                }
                goto LABEL_95;
              }
            }
            RxOrphanFobx(v32);
          }
LABEL_95:
          v30 = (LIST_ENTRY *)(v23 + 46);
          v32 = v36;
          if ( !v36 )
          {
            v4 = v52;
            v20 = (_QWORD *)(BugCheckParameter2 + 264);
            v25 = v55;
            goto LABEL_97;
          }
        }
      }
    }
LABEL_43:
    v6 = v58;
    v23 = v25;
    v5 = v60;
  }
  *(_BYTE *)(BugCheckParameter2 + 641) &= ~1u;
  if ( v50 )
    return (unsigned int)RxPurgeFcbInSystemCache((PFCB)BugCheckParameter2, 0, 0, 1u, 1u);
  return v4;
}

```

## disassembly

```asm
0x14005b620  mov     [rsp+arg_18], r9
0x14005b625  mov     [rsp+arg_8], dl
0x14005b629  push    rbx
0x14005b62a  push    rbp
0x14005b62b  push    rsi
0x14005b62c  push    rdi
0x14005b62d  push    r12
0x14005b62f  push    r13
0x14005b631  push    r14
0x14005b633  push    r15
0x14005b635  sub     rsp, 0A8h
0x14005b63c  xor     edi, edi
0x14005b63e  xorps   xmm0, xmm0
0x14005b641  mov     [rsp+0E8h+var_90], edi
0x14005b645  mov     r15, r9
0x14005b648  movzx   r14d, dl
0x14005b64c  mov     rbx, rcx
0x14005b64f  movups  [rsp+0E8h+var_88], xmm0
0x14005b654  movups  [rsp+0E8h+var_88+0Ch], xmm0
0x14005b659  test    r8, r8
0x14005b65c  jz      loc_14005B7D0
0x14005b662  test    byte ptr [rcx+9Ch], 1
0x14005b669  jnz     loc_14005B7D0
0x14005b66f  mov     esi, [r8]
0x14005b672  mov     r15d, [r8+14h]
0x14005b676  mov     ebp, [r8+18h]
0x14005b67a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b681  lea     r12, WPP_GLOBAL_Control
0x14005b688  cmp     rcx, r12
0x14005b68b  jz      short loc_14005B69A
0x14005b68d  test    dword ptr [rcx+2Ch], 200h
0x14005b694  jnz     loc_14005BBB5
0x14005b69a  test    esi, 0FFEFFE7Fh
0x14005b6a0  jnz     short loc_14005B6B9
0x14005b6a2  mov     eax, edi
0x14005b6a4  add     rsp, 0A8h
0x14005b6ab  pop     r15
0x14005b6ad  pop     r14
0x14005b6af  pop     r13
0x14005b6b1  pop     r12
0x14005b6b3  pop     rdi
0x14005b6b4  pop     rsi
0x14005b6b5  pop     rbp
0x14005b6b6  pop     rbx
0x14005b6b7  retn
0x14005b6b9  test    ebp, 0FFFFFFFBh
0x14005b6bf  jnz     loc_14005B9BD
0x14005b6c5  mov     r13d, 3
0x14005b6cb  mov     r14d, esi
0x14005b6ce  mov     [rsp+0E8h+var_90], edi
0x14005b6d2  mov     ebp, esi
0x14005b6d4  and     r14d, 6
0x14005b6d8  and     esi, 10000h
0x14005b6de  and     ebp, 21h
0x14005b6e1  jz      short loc_14005B708
0x14005b6e3  mov     eax, [rbx+1A8h]
0x14005b6e9  test    ebp, ebp
0x14005b6eb  jz      loc_14005B963
0x14005b6f1  cmp     [rbx+1B8h], eax
0x14005b6f7  jnb     loc_14005B963
0x14005b6fd  mov     edi, 0C0000043h
0x14005b702  mov     [rsp+0E8h+var_90], edi
0x14005b706  jmp     short loc_14005B711
0x14005b708  test    r14d, r14d
0x14005b70b  jnz     short loc_14005B6E3
0x14005b70d  test    esi, esi
0x14005b70f  jnz     short loc_14005B6E3
0x14005b711  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b718  cmp     rcx, r12
0x14005b71b  jz      short loc_14005B728
0x14005b71d  mov     eax, [rcx+2Ch]
0x14005b720  test    al, 8
0x14005b722  jnz     loc_14005BBF1
0x14005b728  test    edi, edi
0x14005b72a  js      loc_14005B6A2
0x14005b730  mov     [rsp+0E8h+arg_10], 0
0x14005b738  movups  xmm0, xmmword ptr [rbx+1A8h]
0x14005b73f  movups  xmm1, xmmword ptr [rbx+1B4h]
0x14005b746  movups  [rsp+0E8h+var_88], xmm0
0x14005b74b  movups  [rsp+0E8h+var_88+0Ch], xmm1
0x14005b750  test    ebp, ebp
0x14005b752  jz      loc_14005B9A7
0x14005b758  inc     dword ptr [rsp+0E8h+var_88]
0x14005b75c  xor     eax, eax
0x14005b75e  test    ebp, ebp
0x14005b760  setnz   al
0x14005b763  add     dword ptr [rsp+0E8h+var_88+4], eax
0x14005b767  xor     eax, eax
0x14005b769  test    r14d, r14d
0x14005b76c  setnz   al
0x14005b76f  add     dword ptr [rsp+0E8h+var_88+8], eax
0x14005b773  xor     eax, eax
0x14005b775  test    esi, esi
0x14005b777  setnz   al
0x14005b77a  add     dword ptr [rsp+0E8h+var_88+0Ch], eax
0x14005b77e  mov     eax, r15d
0x14005b781  and     eax, 1
0x14005b784  add     [rsp+0E8h+var_78], eax
0x14005b788  mov     eax, r15d
0x14005b78b  shr     eax, 1
0x14005b78d  and     eax, 1
0x14005b790  shr     r15d, 2
0x14005b794  add     [rsp+0E8h+var_74], eax
0x14005b798  and     r15d, 1
0x14005b79c  add     [rsp+0E8h+var_70], r15d
0x14005b7a1  mov     eax, [rbx+0A4h]
0x14005b7a7  mov     ecx, eax
0x14005b7a9  and     ecx, 20h
0x14005b7ac  test    al, 10h
0x14005b7ae  jnz     loc_14005BC18
0x14005b7b4  movzx   r14d, [rsp+0E8h+arg_8]
0x14005b7bd  or      r13d, 1
0x14005b7c1  mov     r15, [rsp+0E8h+arg_18]
0x14005b7c9  mov     [rsp+0E8h+var_94], r13d
0x14005b7ce  jmp     short loc_14005B7F7
0x14005b7d0  mov     [rsp+0E8h+arg_10], 1
0x14005b7d8  mov     [rsp+0E8h+var_94], 3
0x14005b7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b7e7  lea     r12, WPP_GLOBAL_Control
0x14005b7ee  cmp     rcx, r12
0x14005b7f1  jnz     loc_14005BC3E
0x14005b7f7  mov     rcx, [rbx+130h]
0x14005b7fe  lea     r8, [rsp+0E8h+arg_0]
0x14005b806  add     rcx, 8
0x14005b80a  mov     [rsp+0E8h+var_98], 0
0x14005b80f  mov     edx, 7
0x14005b814  mov     [rsp+0E8h+arg_0], 0
0x14005b81f  call    cs:__imp_MmIsFileSectionActive
0x14005b826  nop     dword ptr [rax+rax+00h]
0x14005b82b  cmp     [rsp+0E8h+arg_0], 0
0x14005b833  lea     rsi, [rbx+108h]
0x14005b83a  mov     rax, rsi
0x14005b83d  mov     r9d, 0EBAAh
0x14005b843  setnz   dl
0x14005b846  or      byte ptr [rbx+281h], 1
0x14005b84d  mov     byte ptr [rsp+0E8h+arg_0], dl
0x14005b854  mov     rax, [rax]
0x14005b857  cmp     rax, rsi
0x14005b85a  jz      short loc_14005B86C
0x14005b85c  lea     rbp, [rax-88h]
0x14005b863  cmp     [rbp+0], r9w
0x14005b868  jz      short loc_14005B854
0x14005b86a  jmp     short loc_14005B86E
0x14005b86c  xor     ebp, ebp
0x14005b86e  mov     r8d, 0EC21h
0x14005b874  test    rbp, rbp
0x14005b877  jz      loc_14005B935
0x14005b87d  lea     rax, [rbp+88h]
0x14005b884  mov     rax, [rax]
0x14005b887  cmp     rax, rsi
0x14005b88a  jz      short loc_14005B8A4
0x14005b88c  lea     r13, [rax-88h]
0x14005b893  mov     [rsp+0E8h+var_60], r13
0x14005b89b  cmp     [r13+0], r9w
0x14005b8a0  jz      short loc_14005B884
0x14005b8a2  jmp     short loc_14005B8AF
0x14005b8a4  xor     r13d, r13d
0x14005b8a7  mov     [rsp+0E8h+var_60], r13
0x14005b8af  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b8b6  cmp     rcx, r12
0x14005b8b9  jz      short loc_14005B8C8
0x14005b8bb  test    dword ptr [rcx+2Ch], 200h
0x14005b8c2  jnz     loc_14005BC72
0x14005b8c8  cmp     rbp, r13
0x14005b8cb  jz      loc_14005BE61
0x14005b8d1  cmp     dword ptr [rbp+0A4h], 1
0x14005b8d8  jz      loc_14005BCB2
0x14005b8de  mov     eax, [rbp+48h]
0x14005b8e1  and     eax, 200h
0x14005b8e6  jz      loc_14005B9CE
0x14005b8ec  test    r14b, r14b
0x14005b8ef  jnz     loc_14005B9CE
0x14005b8f5  cmp     [rsp+0E8h+arg_10], r14b
0x14005b8fd  jnz     loc_14005B9CE
0x14005b903  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b90a  cmp     rcx, r12
0x14005b90d  jz      short loc_14005B91C
0x14005b90f  test    dword ptr [rcx+2Ch], 200h
0x14005b916  jnz     loc_14005BCE3
0x14005b91c  movzx   r14d, [rsp+0E8h+arg_8]
0x14005b925  mov     rbp, r13
0x14005b928  mov     r15, [rsp+0E8h+arg_18]
0x14005b930  jmp     loc_14005B874
0x14005b935  and     byte ptr [rbx+281h], 0FEh
0x14005b93c  cmp     [rsp+0E8h+var_98], 0
0x14005b941  jz      loc_14005B6A2
0x14005b947  mov     r9b, 1; UninitializeCacheMaps
0x14005b94a  mov     [rsp+0E8h+FlushFile], 1; FlushFile
0x14005b94f  xor     r8d, r8d; Length
0x14005b952  xor     edx, edx; FileOffset
0x14005b954  mov     rcx, rbx; Fcb
0x14005b957  call    RxPurgeFcbInSystemCache
0x14005b95c  mov     edi, eax
0x14005b95e  jmp     loc_14005B6A2
0x14005b963  test    r14d, r14d
0x14005b966  jnz     loc_14005BAB4
0x14005b96c  test    esi, esi
0x14005b96e  jnz     loc_14005BAC5
0x14005b974  cmp     [rbx+1ACh], edi
0x14005b97a  jnz     loc_14005BAA5
0x14005b980  cmp     [rbx+1B0h], edi
0x14005b986  jnz     loc_14005BAD6
0x14005b98c  cmp     [rbx+1B4h], edi
0x14005b992  jz      loc_14005B711
0x14005b998  test    r15b, 4
0x14005b99c  jz      loc_14005B6FD
0x14005b9a2  jmp     loc_14005B711
0x14005b9a7  test    r14d, r14d
0x14005b9aa  jnz     loc_14005B758
0x14005b9b0  test    esi, esi
0x14005b9b2  jz      loc_14005B7A1
0x14005b9b8  jmp     loc_14005B758
0x14005b9bd  xor     r13d, r13d
0x14005b9c0  cmp     ebp, 5
0x14005b9c3  jz      loc_14005B6C5
0x14005b9c9  jmp     loc_14005B6CB
0x14005b9ce  cmp     [rbx], r8w
0x14005b9d2  jnz     short loc_14005B9DC
0x14005b9d4  test    eax, eax
0x14005b9d6  jnz     loc_14005BCF7
0x14005b9dc  mov     r8d, [rbp+58h]
0x14005b9e0  test    r8d, r8d
0x14005b9e3  jg      loc_14007D065
0x14005b9e9  test    r15, r15
0x14005b9ec  jnz     loc_14007D0B5
0x14005b9f2  mov     r14, [rbx+2C8h]
0x14005b9f9  test    r14, r14
0x14005b9fc  jnz     loc_14005BD31
0x14005ba02  mov     r14d, [rbp+48h]
0x14005ba06  and     r14d, 8
0x14005ba0a  mov     dword ptr [rsp+0E8h+var_68], r14d
0x14005ba12  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ba19  cmp     rcx, r12
0x14005ba1c  jz      short loc_14005BA2B
0x14005ba1e  test    dword ptr [rcx+2Ch], 200h
0x14005ba25  jnz     loc_14005BD46
0x14005ba2b  test    r14d, r14d
0x14005ba2e  jz      loc_14005BD90
0x14005ba34  mov     eax, [rsp+0E8h+var_94]
0x14005ba38  cmp     eax, 1
0x14005ba3b  jz      loc_14005BDA9
0x14005ba41  cmp     eax, 3
0x14005ba44  jnz     loc_14005BB7F
0x14005ba4a  test    r14d, r14d
0x14005ba4d  jz      loc_14005BDD8
0x14005ba53  lea     rcx, [rbp+0B8h]
0x14005ba5a  mov     rax, rcx
0x14005ba5d  mov     rax, [rax]
0x14005ba60  cmp     rax, rcx
0x14005ba63  jz      loc_14005BB7F
0x14005ba69  cmp     [rax-70h], r9w
0x14005ba6e  lea     r14, [rax-70h]
0x14005ba72  jz      short loc_14005BA5D
0x14005ba74  test    r14, r14
0x14005ba77  jz      loc_14005BB7F
0x14005ba7d  mov     esi, dword ptr [rsp+0E8h+var_68]
0x14005ba84  mov     rdi, [rsp+0E8h+arg_18]
0x14005ba8c  lea     rax, [r14+70h]
0x14005ba90  mov     rax, [rax]
0x14005ba93  cmp     rax, rcx
0x14005ba96  jz      short loc_14005BAE5
0x14005ba98  cmp     [rax-70h], r9w
0x14005ba9d  lea     r15, [rax-70h]
0x14005baa1  jz      short loc_14005BA90
0x14005baa3  jmp     short loc_14005BAE8
0x14005baa5  test    r15b, 1
0x14005baa9  jnz     loc_14005B980
0x14005baaf  jmp     loc_14005B6FD
0x14005bab4  cmp     [rbx+1BCh], eax
0x14005baba  jnb     loc_14005B96C
0x14005bac0  jmp     loc_14005B6FD
0x14005bac5  cmp     [rbx+1C0h], eax
0x14005bacb  jnb     loc_14005B974
0x14005bad1  jmp     loc_14005B6FD
0x14005bad6  test    r15b, 2
0x14005bada  jnz     loc_14005B98C
0x14005bae0  jmp     loc_14005B6FD
0x14005bae5  xor     r15d, r15d
0x14005bae8  test    rdi, rdi
0x14005baeb  jnz     loc_14005BDF3
0x14005baf1  mov     eax, [r14+48h]
0x14005baf5  bt      eax, 1Eh
0x14005baf9  jb      loc_14005BE54
0x14005baff  bt      eax, 16h
0x14005bb03  jnb     short loc_14005BB0E
0x14005bb05  mov     r13, [r14+30h]
0x14005bb09  test    r13, r13
0x14005bb0c  jnz     short loc_14005BB8A
0x14005bb0e  test    esi, esi
0x14005bb10  jz      loc_14005BE45
0x14005bb16  cmp     byte ptr [r14+92h], 0
0x14005bb1e  jnz     short loc_14005BB33
0x14005bb20  mov     rax, [r14+28h]
0x14005bb24  lock dec dword ptr [rax+0C0h]
0x14005bb2b  mov     byte ptr [r14+92h], 1
0x14005bb33  mov     rdx, r14; Fobx
0x14005bb36  xor     ecx, ecx; RxContext
0x14005bb38  call    RxCloseAssociatedSrvOpen
0x14005bb3d  mov     r8b, 1
0x14005bb40  mov     rdx, r14
  ... truncated ...
```
