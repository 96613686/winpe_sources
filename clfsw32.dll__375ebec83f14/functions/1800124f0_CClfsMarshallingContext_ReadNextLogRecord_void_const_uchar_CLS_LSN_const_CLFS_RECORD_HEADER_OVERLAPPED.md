# CClfsMarshallingContext::ReadNextLogRecord(void * const,uchar,_CLS_LSN * const,_CLFS_RECORD_HEADER * &,_OVERLAPPED *)

- ea: `0x1800124f0`
- end: `0x180012e11`
- name: `?ReadNextLogRecord@CClfsMarshallingContext@@QEAAKQEAXEQEAT_CLS_LSN@@AEAPEAU_CLFS_RECORD_HEADER@@PEAU_OVERLAPPED@@@Z`
- size: `2337`
- prototype: `unsigned int(CClfsMarshallingContext *__hidden this, void *const, unsigned __int8, union _CLS_LSN *const, struct _CLFS_RECORD_HEADER **, struct _OVERLAPPED *)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000aec0`
- `0x18000c6f0`
- `0x18000c900`
- `0x180013cc0`

## callees

- `0x180008ca0`
- `0x18000f60c`
- `0x18001067c`
- `0x1800106f8`
- `0x1800113dc`
- `0x180011cfc`
- `0x1800124f0`

## pseudocode

```c
int __fastcall CClfsMarshallingContext::ReadNextLogRecord(
        CClfsMarshallingContext *this,
        char *a2,
        unsigned __int8 a3,
        union _CLS_LSN *const a4,
        struct _CLFS_RECORD_HEADER **a5,
        struct _OVERLAPPED *a6)
{
  union _CLS_LSN v6; // rdi
  unsigned __int8 v8; // bl
  struct _CLFS_RECORD_HEADER **v10; // r12
  unsigned int *v11; // rdx
  __int16 v12; // r10
  union _CLS_LSN v13; // rax
  __int64 v14; // r8
  char v15; // r10
  int result; // eax
  struct _CLFS_RECORD_HEADER *v17; // rcx
  unsigned __int8 *v18; // rdx
  __int16 v19; // ax
  struct _CLFS_RECORD_HEADER *FirstRecord; // rax
  __int64 v21; // rcx
  CClfsMarshallingContext *v22; // r11
  CLFS_LSN *v23; // r14
  union _CLS_LSN *v24; // rcx
  union _CLS_LSN *v25; // rdi
  unsigned __int8 *v26; // rdx
  int LsnInBlock; // eax
  struct _CLFS_RECORD_HEADER *v28; // rcx
  __int64 v29; // rax
  ULONGLONG *v30; // rcx
  unsigned __int8 *v31; // rdx
  struct _CLFS_RECORD_HEADER *v32; // rcx
  __int16 v33; // cx
  __int16 v34; // ax
  _DWORD *v35; // rdx
  int cidContainer; // ecx
  _DWORD *v37; // r8
  unsigned int v38; // ecx
  unsigned int v39; // edx
  __int16 v40; // ax
  unsigned int v41; // r8d
  __int64 v42; // rdx
  signed __int32 v43; // r9d
  signed __int32 v44; // eax
  unsigned int LogRecordInternal; // r11d
  __int16 v46; // ax
  __int16 v47; // ax
  unsigned int v48; // edx
  __int64 v49; // r10
  __int64 v50; // r9
  signed __int32 v51; // r8d
  signed __int32 v52; // eax
  unsigned int v53; // edx
  __int64 v54; // r10
  __int64 v55; // r9
  signed __int32 v56; // r8d
  signed __int32 v57; // eax
  __int16 v58; // bx
  char *v59; // r9
  __int16 v60; // r10
  struct _CLFS_RECORD_HEADER *v61; // rax
  __int16 v62; // r10
  __int16 v63; // r10
  __int16 v64; // ax
  __int16 v65; // r10
  struct _CLFS_RECORD_HEADER *v66; // rax
  __int16 v67; // r10
  int v68; // r11d
  struct _CLFS_RECORD_HEADER *v69; // r8
  CLFS_LSN v70; // rbx
  CLFS_CONTAINER_ID v71; // ecx
  CLFS_LSN v72; // rax
  int v73; // eax
  unsigned __int64 v74; // rdx
  unsigned __int64 v75; // rax
  unsigned __int64 v76; // r9
  unsigned __int64 v77; // rax
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // rtt
  __int16 v80; // r10
  struct _OVERLAPPED *v81; // [rsp+48h] [rbp-39h]
  unsigned int v82; // [rsp+58h] [rbp-29h] BYREF
  union _CLS_LSN v83; // [rsp+60h] [rbp-21h] BYREF
  struct _CLFS_RECORD_HEADER *v84; // [rsp+68h] [rbp-19h] BYREF
  CLFS_LSN v85; // [rsp+70h] [rbp-11h]
  CLFS_LSN v86; // [rsp+78h] [rbp-9h]
  union _CLS_LSN v87; // [rsp+80h] [rbp-1h] BYREF
  void *v88; // [rsp+88h] [rbp+7h]
  union _CLS_LSN v90; // [rsp+E0h] [rbp+5Fh] BYREF
  unsigned __int8 v91; // [rsp+E8h] [rbp+67h]

  v91 = a3;
  v6 = CLFS_LSN_INVALID;
  v83 = CLFS_LSN_INVALID;
  v82 = 0;
  v8 = a3;
  LOBYTE(v90.offset.idxRecord) = 0;
  if ( !a2 )
    return 6606;
  if ( a4
    && (CLFS_LSN_INVALID.ullOffset == a4->ullOffset || (a4->offset.idxRecord & 0xFFFFFE00) % *((_DWORD *)this + 34)) )
  {
    return 87;
  }
  v10 = a5;
  *a5 = 0;
  if ( *((_DWORD *)a2 + 4) != -1040322545 )
    return 6;
  if ( *((_DWORD *)a2 + 5) != 224 )
    return 6;
  v11 = (unsigned int *)*((_QWORD *)a2 + 24);
  if ( v11 != (unsigned int *)this )
    return 6;
  if ( (v12 = *((_WORD *)a2 + 14), v13 = CLFS_LSN_INVALID, (v12 & 0x80) == 0)
    || a2 != (char *)-144LL && CLFS_LSN_INVALID.ullOffset == *((_QWORD *)a2 + 18)
    || a4 )
  {
    if ( (a3 & 0x3F) == 0 )
      return 87;
  }
  if ( (v12 & 0x1000) != 0 )
    return 6606;
  v14 = *((_QWORD *)a2 + 8);
  if ( *(char *)(v11[32] + v14 - 16) < 0 )
    return 170;
  if ( (v12 & 0x80) == 0 )
  {
    if ( a4 || *((_QWORD *)a2 + 13) )
    {
LABEL_38:
      v88 = 0;
      if ( !a6 )
        v88 = (void *)*((_QWORD *)a2 + 7);
      while ( *((_DWORD *)a2 + 32) != 1 )
      {
        if ( *((_DWORD *)a2 + 32) == 2 )
        {
          if ( v13.ullOffset == v6.ullOffset )
          {
            v24 = (union _CLS_LSN *)*((_QWORD *)a2 + 13);
            if ( a4 )
            {
              if ( v24 && a4->ullOffset > v24->ullOffset )
                return 87;
              v25 = a4;
            }
            else
            {
              v25 = v24 + 2;
            }
            v6 = *v25;
            v83 = v6;
            if ( ((v8 & 2) != 0 || (a2[28] & 0x10) != 0) && v13.ullOffset == v6.ullOffset )
              return 6618;
          }
          v26 = (unsigned __int8 *)*((_QWORD *)a2 + 8);
          v87 = v13;
          v84 = 0;
          LsnInBlock = ClfsFindLsnInBlock(&v83, v26, &v84, &v87);
          if ( v6.ullOffset == v87.ullOffset )
          {
            v28 = v84;
LABEL_63:
            if ( LsnInBlock == 6609 )
              goto LABEL_19;
          }
          else
          {
            v28 = 0;
            if ( LsnInBlock < 0 )
              goto LABEL_63;
          }
          if ( v28 )
          {
            *((_QWORD *)a2 + 13) = v28;
            *v10 = v28;
            v29 = *((_QWORD *)a2 + 13);
            *((_WORD *)a2 + 14) &= ~0x100u;
            if ( (v8 & *(_BYTE *)(v29 + 36)) != 0 )
              goto LABEL_150;
            v6 = *(union _CLS_LSN *)(v29 + 16);
            goto LABEL_67;
          }
LABEL_83:
          v33 = *((_WORD *)a2 + 14);
          *((_WORD *)a2 + 14) = v33 & 0xFEFF;
          if ( (v33 & 0x100) != 0 )
            return 1168;
          goto LABEL_84;
        }
        if ( *((_DWORD *)a2 + 32) != 3 )
          return 6610;
        v19 = *((_WORD *)a2 + 14);
        if ( (v19 & 0x100) != 0 && (v19 & 0x2000) == 0 )
        {
          *((_WORD *)a2 + 14) = v19 & 0xFE7F;
          *((_QWORD *)a2 + 14) = *((_QWORD *)a2 + 8);
          FirstRecord = CLogIocb::GetFirstRecord((CLogIocb *)a2);
          *((_QWORD *)a2 + 13) = FirstRecord;
          if ( (v8 & *((_BYTE *)FirstRecord + 36)) != 0 )
          {
            *((_QWORD *)a2 + 17) = *(_QWORD *)FirstRecord;
            *v10 = FirstRecord;
            return 0;
          }
        }
        while ( !CLogIocb::NextRecord((CLogIocb *)a2) )
        {
          v21 = *((_QWORD *)a2 + 13);
          if ( (v8 & *(_BYTE *)(v21 + 36)) != 0 )
          {
            *((_QWORD *)a2 + 17) = *(_QWORD *)v21;
            *v10 = (struct _CLFS_RECORD_HEADER *)v21;
            return 0;
          }
        }
        v23 = (CLFS_LSN *)(a2 + 160);
LABEL_85:
        v34 = *((_WORD *)a2 + 14);
        if ( (v34 & 0x200) == 0 )
          goto LABEL_96;
        if ( (v34 & 0x2000) != 0 )
          goto LABEL_96;
        v35 = (_DWORD *)*((_QWORD *)a2 + 13);
        if ( !v35 )
          goto LABEL_96;
        if ( v23 )
        {
          cidContainer = v23->offset.cidContainer;
          v37 = a2 + 160;
        }
        else
        {
          cidContainer = -1;
          v37 = 0;
        }
        if ( v35[1] != cidContainer )
          goto LABEL_96;
        v38 = -1;
        v39 = *v35 & 0xFFFFFE00;
        if ( v23 )
          v38 = *v37 & 0xFFFFFE00;
        if ( v39 == v38 )
          v40 = v34 & 0xFEFF;
        else
LABEL_96:
          v40 = v34 | 0x100;
        *((_WORD *)a2 + 14) = v40;
        v41 = 0;
        v42 = *((_QWORD *)a2 + 8) + *(unsigned int *)(*((_QWORD *)a2 + 24) + 128LL);
        while ( 1 )
        {
          v43 = *(_DWORD *)(v42 - 16);
          v44 = _InterlockedCompareExchange((volatile signed __int32 *)(v42 - 16), v43 | 0x80, v43);
          if ( (v44 & 0x80) != 0 )
            return 170;
          if ( v44 == v43 )
            break;
          if ( v41 > 5 )
            return 170;
          ++v41;
        }
        *((_WORD *)a2 + 14) &= ~0x2000u;
        LogRecordInternal = CClfsMarshallingContext::ReadMarshalledLogRecord(
                              v22,
                              (struct CLogIocb *)a2,
                              &v82,
                              (unsigned __int8 *)&v90);
        if ( LogRecordInternal )
        {
          if ( LogRecordInternal != 1168 )
          {
            v53 = 0;
            v54 = *((_QWORD *)a2 + 8);
            v55 = *(unsigned int *)(*((_QWORD *)a2 + 24) + 128LL);
            while ( 1 )
            {
              v56 = *(_DWORD *)(v55 + v54 - 16);
              v57 = _InterlockedCompareExchange((volatile signed __int32 *)(v55 + v54 - 16), v56 & 0xFFFFFF7F, v56);
              if ( (v57 & 0x80u) == 0 || v57 == v56 || v53 > 5 )
                break;
              ++v53;
            }
          }
        }
        else
        {
          v46 = *((_WORD *)a2 + 14);
          if ( LOBYTE(v90.offset.idxRecord) )
            v47 = v46 & 0xFDFF;
          else
            v47 = v46 | 0x200;
          *((_WORD *)a2 + 14) = v47;
          v48 = 0;
          v49 = *((_QWORD *)a2 + 8);
          v50 = *(unsigned int *)(*((_QWORD *)a2 + 24) + 128LL);
          while ( 1 )
          {
            v51 = *(_DWORD *)(v50 + v49 - 16);
            v52 = _InterlockedCompareExchange((volatile signed __int32 *)(v50 + v49 - 16), v51 & 0xFFFFFF7F, v51);
            if ( (v52 & 0x80u) == 0 || v52 == v51 || v48 > 5 )
              break;
            ++v48;
          }
        }
        v58 = *((_WORD *)a2 + 14);
        if ( LogRecordInternal == 1168 )
        {
          v81 = a6;
          v59 = (char *)*((_QWORD *)a2 + 8);
          *((_WORD *)a2 + 14) = v58 & 0xFDFF;
          *((_QWORD *)a2 + 21) = *((_QWORD *)a2 + 20);
          LogRecordInternal = NtReadLogRecordInternal(
                                *((void **)this + 6),
                                (union _CLS_LSN *)a2 + 20,
                                (unsigned int)(*((_DWORD *)a2 + 32) == 3) + 1,
                                v59,
                                *((_DWORD *)this + 32),
                                (unsigned int *)a2 + 18,
                                (unsigned __int64)v88,
                                (*((_DWORD *)this + 39) & 0x20) == 0,
                                v81);
        }
        if ( LogRecordInternal == 997 )
        {
          *((_WORD *)a2 + 14) |= 0x80u;
          return 997;
        }
        *((CLFS_LSN *)a2 + 21) = CLFS_LSN_INVALID;
        if ( !LogRecordInternal )
        {
          v60 = *((_WORD *)a2 + 14) & 0xFF7F;
          *((_WORD *)a2 + 14) = v60;
          if ( (v60 & 0x100) == 0
            || (*((_QWORD *)a2 + 14) = *((_QWORD *)a2 + 8),
                v61 = CLogIocb::GetFirstRecord((CLogIocb *)a2),
                (*((_QWORD *)a2 + 13) = v61) != 0) )
          {
            v8 = v91;
            v13 = CLFS_LSN_INVALID;
            continue;
          }
          *((_WORD *)a2 + 14) = v62 | 0x1000;
          return 6609;
        }
        v63 = *((_WORD *)a2 + 14);
        v64 = v63 & 0xFDFF;
        v65 = v63 | 0x200;
        if ( (v58 & 0x200) == 0 )
          v65 = v64;
        *((_WORD *)a2 + 14) = v65;
        v66 = CLogIocb::GetFirstRecord((CLogIocb *)a2);
        v69 = v66;
        if ( !v66 )
          return 6609;
        if ( v68 != 38 )
        {
          if ( v68 == 6603 )
LABEL_154:
            v80 = v67 & 0xFEFF;
          else
            v80 = v67 & 0xEEFF | 0x1000;
          *((_WORD *)a2 + 14) = v80;
          return v68;
        }
        if ( this != (CClfsMarshallingContext *)-200LL && *((_QWORD *)this + 25) == *(_QWORD *)v66 )
          goto LABEL_154;
        v70 = CLFS_LSN_INVALID;
        if ( !v23 || (v71 = v23->offset.cidContainer, v71 == -1) )
        {
          v72 = CLFS_LSN_INVALID;
          v85 = CLFS_LSN_INVALID;
        }
        else
        {
          v85.ullOffset = __PAIR64__(v71, v23->offset.idxRecord & 0xFFFFFE00);
          v72 = v85;
        }
        if ( v72.ullOffset != *(_QWORD *)v69 )
          goto LABEL_154;
        v87.ullOffset = 0;
        if ( (CLogIocb::GetLastRecord((CLogIocb *)a2, (struct _CLFS_RECORD_HEADER **)&v87) & 0x80000000) != 0 )
          goto LABEL_19;
        v73 = *((_DWORD *)this + 34);
        if ( v73 )
          v74 = ~(unsigned __int64)(unsigned int)(v73 - 1)
              & (v87.ullOffset + (unsigned int)(v73 - 1) + *(unsigned int *)(v87.ullOffset + 24) - *((_QWORD *)a2 + 8));
        else
          LODWORD(v74) = 0;
        v75 = *(_QWORD *)(*((_QWORD *)a2 + 8) + 24LL);
        if ( CLFS_LSN_INVALID.ullOffset != v75 )
        {
          v76 = *((_QWORD *)this + 21);
          v79 = (unsigned int)v74 + (v75 & 0xFFFFFE00) + v76 * HIDWORD(v75);
          v77 = v79 / v76;
          v78 = v79 % v76;
          if ( !((v79 / v76) >> 32) && !HIDWORD(v78) )
          {
            if ( (_DWORD)v77 == -1 || (v78 & 0x1FF) != 0 )
            {
              v86 = CLFS_LSN_INVALID;
            }
            else
            {
              v86.ullOffset = __PAIR64__(v77, v78);
              v70.ullOffset = __PAIR64__(v77, v78);
            }
          }
        }
        *v23 = v70;
        *((_WORD *)a2 + 14) &= ~0x80u;
        *((_WORD *)a2 + 14) |= 0x2000u;
        v13 = CLFS_LSN_INVALID;
        v8 = v91;
      }
      if ( v13.ullOffset == v6.ullOffset )
      {
        v30 = (ULONGLONG *)*((_QWORD *)a2 + 13);
        if ( a4 )
        {
          if ( v30 && a4->ullOffset > *v30 )
            return 87;
          v6 = *a4;
        }
        else
        {
          v6.ullOffset = v30[1];
        }
        v83 = v6;
      }
      v31 = (unsigned __int8 *)*((_QWORD *)a2 + 8);
      v87 = v13;
      v84 = 0;
      result = ClfsFindLsnInBlock(&v83, v31, &v84, &v87);
      if ( v6.ullOffset == v87.ullOffset )
      {
        v32 = v84;
      }
      else
      {
        v32 = 0;
        if ( result >= 0 )
        {
LABEL_80:
          if ( !v32 )
            goto LABEL_83;
          *((_QWORD *)a2 + 13) = v32;
          *v10 = v32;
          v29 = *((_QWORD *)a2 + 13);
          *((_WORD *)a2 + 14) &= ~0x100u;
          if ( (v8 & *(_BYTE *)(v29 + 36)) != 0 )
          {
LABEL_150:
            *((_QWORD *)a2 + 17) = *(_QWORD *)v29;
            return 0;
          }
          v6 = *(union _CLS_LSN *)(v29 + 8);
LABEL_67:
          v83 = v6;
LABEL_84:
          v22 = this;
          v23 = (CLFS_LSN *)(a2 + 160);
          *((union _CLS_LSN *)a2 + 20) = v6;
          goto LABEL_85;
        }
      }
      if ( result == 6609 )
      {
        *((_WORD *)a2 + 14) |= 0x1000u;
        return result;
      }
      goto LABEL_80;
    }
    return 6606;
  }
  v6 = *(union _CLS_LSN *)(a2 + 168);
  v83 = v6;
  *((_WORD *)a2 + 14) = v12 & 0xFE7F;
  *((_QWORD *)a2 + 14) = v14;
  *((_QWORD *)a2 + 13) = CLogIocb::GetFirstRecord((CLogIocb *)a2);
  if ( a4 )
  {
    v13 = CLFS_LSN_INVALID;
    goto LABEL_38;
  }
  if ( (v15 & 0x10) == 0 )
  {
    *v10 = 0;
    v18 = (unsigned __int8 *)*((_QWORD *)a2 + 8);
    v90 = CLFS_LSN_INVALID;
    result = ClfsFindLsnInBlock(&v83, v18, v10, &v90);
    if ( v6.ullOffset != v90.ullOffset )
    {
      *v10 = 0;
      if ( result >= 0 )
        result = 1168;
    }
    v17 = *v10;
    if ( !*v10 || result )
      return result;
    goto LABEL_31;
  }
  if ( CLogIocb::GetLastRecord((CLogIocb *)a2, v10) != 6609 )
  {
    v17 = *v10;
    if ( !*v10 )
    {
      *((_QWORD *)a2 + 13) = CLogIocb::GetFirstRecord((CLogIocb *)a2);
      return 6611;
    }
    if ( (v8 & 2) != 0 && (*((_BYTE *)v17 + 36) & 2) == 0 )
      return 6607;
LABEL_31:
    if ( (v8 & *((_BYTE *)v17 + 36)) != 0 )
    {
      *((_QWORD *)a2 + 13) = v17;
      return 0;
    }
    return 6624;
  }
LABEL_19:
  *((_WORD *)a2 + 14) |= 0x1000u;
  return 6609;
}

```

## disassembly

```asm
0x1800124f0  mov     rax, rsp
0x1800124f3  mov     [rax+20h], rbx
0x1800124f7  mov     [rax+18h], r8b
0x1800124fb  mov     [rax+8], rcx
0x1800124ff  push    rbp
0x180012500  push    rsi
0x180012501  push    rdi
0x180012502  push    r12
0x180012504  push    r13
0x180012506  push    r14
0x180012508  push    r15
0x18001250a  lea     rbp, [rax-4Fh]
0x18001250e  sub     rsp, 90h
0x180012515  mov     rdi, qword ptr cs:CLFS_LSN_INVALID
0x18001251c  xor     r14d, r14d
0x18001251f  mov     qword ptr [rbp+47h+var_68], rdi
0x180012523  mov     r13, r9
0x180012526  mov     [rbp+47h+var_70], r14d
0x18001252a  mov     bl, r8b
0x18001252d  mov     byte ptr [rbp+47h+arg_8], r14b
0x180012531  mov     rsi, rdx
0x180012534  mov     r11, rcx
0x180012537  test    rdx, rdx
0x18001253a  jz      loc_180012DF0
0x180012540  test    r9, r9
0x180012543  jz      short loc_180012566
0x180012545  cmp     rdi, [r9]
0x180012548  jz      loc_180012DE2
0x18001254e  mov     eax, [r9]
0x180012551  xor     edx, edx
0x180012553  and     eax, 0FFFFFE00h
0x180012558  div     dword ptr [rcx+88h]
0x18001255e  test    edx, edx
0x180012560  jnz     loc_180012DE2
0x180012566  mov     r12, [rbp+47h+arg_20]
0x18001256a  mov     [r12], r14
0x18001256e  cmp     dword ptr [rsi+10h], 0C1FDF00Fh
0x180012575  jnz     loc_180012DE9
0x18001257b  cmp     dword ptr [rsi+14h], 0E0h
0x180012582  jnz     loc_180012DE9
0x180012588  mov     rdx, [rsi+0C0h]
0x18001258f  cmp     rdx, rcx
0x180012592  jnz     loc_180012DE9
0x180012598  movzx   r10d, word ptr [rsi+1Ch]
0x18001259d  mov     r8d, 80h
0x1800125a3  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1800125aa  movzx   r9d, r10w
0x1800125ae  and     r9w, r8w
0x1800125b2  jz      short loc_1800125CA
0x1800125b4  lea     rcx, [rsi+90h]
0x1800125bb  test    rcx, rcx
0x1800125be  jz      short loc_1800125C5
0x1800125c0  cmp     rax, [rcx]
0x1800125c3  jz      short loc_1800125CA
0x1800125c5  test    r13, r13
0x1800125c8  jz      short loc_1800125D3
0x1800125ca  test    bl, 3Fh
0x1800125cd  jz      loc_180012DE2
0x1800125d3  mov     r15d, 1000h
0x1800125d9  test    r15w, r10w
0x1800125dd  jnz     loc_180012DF0
0x1800125e3  mov     r8, [rsi+40h]
0x1800125e7  mov     ecx, [rdx+80h]
0x1800125ed  test    byte ptr [rcx+r8-10h], 80h
0x1800125f3  jnz     loc_180012DDB
0x1800125f9  mov     ecx, 0FE7Fh
0x1800125fe  test    r9w, r9w
0x180012602  jz      loc_1800126FF
0x180012608  mov     rdi, [rsi+0A8h]
0x18001260f  and     r10w, cx
0x180012613  mov     rcx, rsi; this
0x180012616  mov     qword ptr [rbp+47h+var_68], rdi
0x18001261a  mov     [rsi+1Ch], r10w
0x18001261f  mov     [rsi+70h], r8
0x180012623  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x180012628  mov     [rsi+68h], rax
0x18001262c  test    r13, r13
0x18001262f  jnz     loc_1800126F6
0x180012635  test    r10b, 10h
0x180012639  jz      short loc_180012690
0x18001263b  mov     rdx, r12; struct _CLFS_RECORD_HEADER **
0x18001263e  mov     rcx, rsi; this
0x180012641  call    ?GetLastRecord@CLogIocb@@QEAAKAEAPEAU_CLFS_RECORD_HEADER@@@Z; CLogIocb::GetLastRecord(_CLFS_RECORD_HEADER * &)
0x180012646  cmp     eax, 19D1h
0x18001264b  jnz     short loc_18001265C
0x18001264d  or      [rsi+1Ch], r15w
0x180012652  mov     eax, 19D1h
0x180012657  jmp     loc_180012DF5
0x18001265c  mov     rcx, [r12]
0x180012660  test    rcx, rcx
0x180012663  jnz     short loc_18001267B
0x180012665  mov     rcx, rsi; this
0x180012668  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x18001266d  mov     [rsi+68h], rax
0x180012671  mov     eax, 19D3h
0x180012676  jmp     loc_180012DF5
0x18001267b  test    bl, 2
0x18001267e  jz      short loc_1800126DC
0x180012680  test    byte ptr [rcx+24h], 2
0x180012684  jnz     short loc_1800126DC
0x180012686  mov     eax, 19CFh
0x18001268b  jmp     loc_180012DF5
0x180012690  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180012697  lea     r9, [rbp+47h+arg_8]; union _CLS_LSN *
0x18001269b  mov     [r12], r14
0x18001269f  lea     rcx, [rbp+47h+var_68]; union _CLS_LSN *
0x1800126a3  mov     rdx, [rsi+40h]; unsigned __int8 *
0x1800126a7  mov     r8, r12; struct _CLFS_RECORD_HEADER **
0x1800126aa  mov     qword ptr [rbp+47h+arg_8], rax
0x1800126ae  call    ?ClfsFindLsnInBlock@@YAKAEBT_CLS_LSN@@PEAEAEAPEAU_CLFS_RECORD_HEADER@@AEAT1@@Z; ClfsFindLsnInBlock(_CLS_LSN const &,uchar *,_CLFS_RECORD_HEADER * &,_CLS_LSN &)
0x1800126b3  cmp     rdi, qword ptr [rbp+47h+arg_8]
0x1800126b7  jz      short loc_1800126C7
0x1800126b9  test    eax, eax
0x1800126bb  mov     [r12], r14
0x1800126bf  mov     ecx, 490h
0x1800126c4  cmovns  eax, ecx
0x1800126c7  mov     rcx, [r12]
0x1800126cb  test    rcx, rcx
0x1800126ce  jz      loc_180012DF5
0x1800126d4  test    eax, eax
0x1800126d6  jnz     loc_180012DF5
0x1800126dc  test    [rcx+24h], bl
0x1800126df  jnz     short loc_1800126EB
0x1800126e1  mov     eax, 19E0h
0x1800126e6  jmp     loc_180012DF5
0x1800126eb  mov     [rsi+68h], rcx
0x1800126ef  xor     eax, eax
0x1800126f1  jmp     loc_180012DF5
0x1800126f6  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1800126fd  jmp     short loc_18001270E
0x1800126ff  test    r13, r13
0x180012702  jnz     short loc_18001270E
0x180012704  cmp     [rsi+68h], r14
0x180012708  jz      loc_180012DF0
0x18001270e  mov     [rbp+47h+var_40], r14
0x180012712  cmp     [rbp+47h+arg_28], r14
0x180012716  jnz     short loc_180012720
0x180012718  mov     rcx, [rsi+38h]
0x18001271c  mov     [rbp+47h+var_40], rcx
0x180012720  mov     r8d, 100h
0x180012726  mov     r9d, 2000h
0x18001272c  mov     edx, [rsi+80h]
0x180012732  sub     edx, 1
0x180012735  jz      loc_180012892
0x18001273b  sub     edx, 1
0x18001273e  jz      loc_1800127C9
0x180012744  cmp     edx, 1
0x180012747  jnz     loc_180012D61
0x18001274d  movzx   eax, word ptr [rsi+1Ch]
0x180012751  test    r8w, ax
0x180012755  jz      short loc_1800127A5
0x180012757  test    r9w, ax
0x18001275b  jnz     short loc_1800127A5
0x18001275d  mov     ecx, 0FE7Fh
0x180012762  and     ax, cx
0x180012765  mov     rcx, rsi; this
0x180012768  mov     [rsi+1Ch], ax
0x18001276c  mov     rax, [rsi+40h]
0x180012770  mov     [rsi+70h], rax
0x180012774  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x180012779  mov     [rsi+68h], rax
0x18001277d  mov     r10, rax
0x180012780  test    [rax+24h], bl
0x180012783  jz      short loc_1800127A5
0x180012785  mov     rax, [rax]
0x180012788  mov     [rsi+88h], rax
0x18001278f  mov     [r12], r10
0x180012793  jmp     loc_1800126EF
0x180012798  mov     rcx, [rsi+68h]
0x18001279c  test    [rcx+24h], bl
0x18001279f  jnz     loc_180012D4E
0x1800127a5  mov     rcx, rsi; this
0x1800127a8  call    ?NextRecord@CLogIocb@@QEAAKXZ; CLogIocb::NextRecord(void)
0x1800127ad  test    eax, eax
0x1800127af  jz      short loc_180012798
0x1800127b1  lea     r14, [rsi+0A0h]
0x1800127b8  mov     r9d, 0FEFFh
0x1800127be  mov     r10d, 100h
0x1800127c4  jmp     loc_180012964
0x1800127c9  cmp     rax, rdi
0x1800127cc  jnz     short loc_18001281B
0x1800127ce  mov     rcx, [rsi+68h]
0x1800127d2  test    r13, r13
0x1800127d5  jnz     short loc_1800127DD
0x1800127d7  lea     rdi, [rcx+10h]
0x1800127db  jmp     short loc_180012800
0x1800127dd  test    rcx, rcx
0x1800127e0  jz      short loc_1800127FD
0x1800127e2  mov     edx, [r13+4]
0x1800127e6  cmp     edx, [rcx+4]
0x1800127e9  jb      short loc_1800127FD
0x1800127eb  jnz     loc_180012DE2
0x1800127f1  mov     ecx, [rcx]
0x1800127f3  cmp     [r13+0], ecx
0x1800127f7  ja      loc_180012DE2
0x1800127fd  mov     rdi, r13
0x180012800  mov     rdi, [rdi]
0x180012803  mov     qword ptr [rbp+47h+var_68], rdi
0x180012807  test    bl, 2
0x18001280a  jnz     short loc_180012812
0x18001280c  test    byte ptr [rsi+1Ch], 10h
0x180012810  jz      short loc_18001281B
0x180012812  cmp     rax, rdi
0x180012815  jz      loc_180012D6B
0x18001281b  mov     rdx, [rsi+40h]; unsigned __int8 *
0x18001281f  lea     r9, [rbp+47h+var_48]; union _CLS_LSN *
0x180012823  lea     r8, [rbp+47h+var_60]; struct _CLFS_RECORD_HEADER **
0x180012827  mov     qword ptr [rbp+47h+var_48], rax
0x18001282b  lea     rcx, [rbp+47h+var_68]; union _CLS_LSN *
0x18001282f  mov     [rbp+47h+var_60], r14
0x180012833  call    ?ClfsFindLsnInBlock@@YAKAEBT_CLS_LSN@@PEAEAEAPEAU_CLFS_RECORD_HEADER@@AEAT1@@Z; ClfsFindLsnInBlock(_CLS_LSN const &,uchar *,_CLFS_RECORD_HEADER * &,_CLS_LSN &)
0x180012838  cmp     rdi, qword ptr [rbp+47h+var_48]
0x18001283c  jz      short loc_180012847
0x18001283e  mov     rcx, r14
0x180012841  test    eax, eax
0x180012843  jns     short loc_180012856
0x180012845  jmp     short loc_18001284B
0x180012847  mov     rcx, [rbp+47h+var_60]
0x18001284b  cmp     eax, 19D1h
0x180012850  jz      loc_18001264D
0x180012856  mov     r9d, 0FEFFh
0x18001285c  test    rcx, rcx
0x18001285f  jz      loc_180012937
0x180012865  mov     [rsi+68h], rcx
0x180012869  mov     [r12], rcx
0x18001286d  mov     rax, [rsi+68h]
0x180012871  and     [rsi+1Ch], r9w
0x180012876  test    [rax+24h], bl
0x180012879  jnz     loc_180012D75
0x18001287f  mov     rdi, [rax+10h]
0x180012883  mov     qword ptr [rbp+47h+var_68], rdi
0x180012887  mov     r10d, 100h
0x18001288d  jmp     loc_180012956
0x180012892  cmp     rax, rdi
0x180012895  jnz     short loc_1800128CE
0x180012897  mov     rcx, [rsi+68h]
0x18001289b  test    r13, r13
0x18001289e  jnz     short loc_1800128A6
0x1800128a0  mov     rdi, [rcx+8]
0x1800128a4  jmp     short loc_1800128CA
0x1800128a6  test    rcx, rcx
0x1800128a9  jz      short loc_1800128C6
0x1800128ab  mov     edx, [r13+4]
0x1800128af  cmp     edx, [rcx+4]
0x1800128b2  jb      short loc_1800128C6
0x1800128b4  jnz     loc_180012DE2
0x1800128ba  mov     ecx, [rcx]
0x1800128bc  cmp     [r13+0], ecx
0x1800128c0  ja      loc_180012DE2
0x1800128c6  mov     rdi, [r13+0]
0x1800128ca  mov     qword ptr [rbp+47h+var_68], rdi
0x1800128ce  mov     rdx, [rsi+40h]; unsigned __int8 *
0x1800128d2  lea     r9, [rbp+47h+var_48]; union _CLS_LSN *
0x1800128d6  lea     r8, [rbp+47h+var_60]; struct _CLFS_RECORD_HEADER **
0x1800128da  mov     qword ptr [rbp+47h+var_48], rax
0x1800128de  lea     rcx, [rbp+47h+var_68]; union _CLS_LSN *
0x1800128e2  mov     [rbp+47h+var_60], r14
0x1800128e6  call    ?ClfsFindLsnInBlock@@YAKAEBT_CLS_LSN@@PEAEAEAPEAU_CLFS_RECORD_HEADER@@AEAT1@@Z; ClfsFindLsnInBlock(_CLS_LSN const &,uchar *,_CLFS_RECORD_HEADER * &,_CLS_LSN &)
0x1800128eb  cmp     rdi, qword ptr [rbp+47h+var_48]
0x1800128ef  jz      short loc_1800128FA
0x1800128f1  mov     rcx, r14
0x1800128f4  test    eax, eax
0x1800128f6  jns     short loc_180012909
0x1800128f8  jmp     short loc_1800128FE
0x1800128fa  mov     rcx, [rbp+47h+var_60]
0x1800128fe  cmp     eax, 19D1h
0x180012903  jz      loc_180012DD4
0x180012909  mov     r9d, 0FEFFh
0x18001290f  test    rcx, rcx
0x180012912  jz      short loc_180012937
0x180012914  mov     [rsi+68h], rcx
0x180012918  mov     [r12], rcx
0x18001291c  mov     rax, [rsi+68h]
0x180012920  and     [rsi+1Ch], r9w
0x180012925  test    [rax+24h], bl
0x180012928  jnz     loc_180012D75
0x18001292e  mov     rdi, [rax+8]
0x180012932  jmp     loc_180012883
0x180012937  movzx   ecx, word ptr [rsi+1Ch]
0x18001293b  mov     r10d, 100h
0x180012941  movzx   eax, cx
0x180012944  and     ax, r9w
0x180012948  mov     [rsi+1Ch], ax
0x18001294c  test    r10w, cx
0x180012950  jnz     loc_180012DCD
0x180012956  mov     r11, [rbp+47h+arg_0]
0x18001295a  lea     r14, [rsi+0A0h]
0x180012961  mov     [r14], rdi
0x180012964  movzx   eax, word ptr [rsi+1Ch]
0x180012968  xor     ebx, ebx
0x18001296a  bt      ax, 9
0x18001296f  jnb     short loc_1800129C1
0x180012971  bt      ax, 0Dh
0x180012976  jb      short loc_1800129C1
0x180012978  mov     rdx, [rsi+68h]
0x18001297c  test    rdx, rdx
0x18001297f  jz      short loc_1800129C1
0x180012981  test    r14, r14
0x180012984  jz      short loc_180012993
0x180012986  mov     ecx, [r14+4]
  ... truncated ...
```
