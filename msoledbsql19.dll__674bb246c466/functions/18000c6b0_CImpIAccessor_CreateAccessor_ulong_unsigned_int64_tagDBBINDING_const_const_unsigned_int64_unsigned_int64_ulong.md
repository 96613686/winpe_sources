# CImpIAccessor::CreateAccessor(ulong,unsigned __int64,tagDBBINDING const * const,unsigned __int64,unsigned __int64 *,ulong * const)

- ea: `0x18000c6b0`
- end: `0x18000d6d7`
- name: `?CreateAccessor@CImpIAccessor@@UEAAJK_KQEBUtagDBBINDING@@0PEA_KQEAK@Z`
- size: `4135`
- prototype: `int(CImpIAccessor *__hidden this, unsigned int, unsigned __int64, const struct tagDBBINDING *const, unsigned __int64, unsigned __int64 *, unsigned int *const)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x180008c80`
- `0x180009340`
- `0x18000c6b0`
- `0x18000d6e0`
- `0x18000e6b0`
- `0x18005ce20`
- `0x180133ef0`
- `0x180136954`
- `0x18013f360`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000d0ca`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000d0ca`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000d0d6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000d0d6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000c7fc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000c7fc`

## string_xrefs

- `0x18000c7af`: `IAccessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CImpIAccessor::CreateAccessor(
        CRowset **this,
        unsigned int a2,
        unsigned __int64 a3,
        const struct tagDBBINDING *const a4,
        unsigned __int64 a5,
        unsigned __int64 *a6,
        unsigned int *const a7)
{
  unsigned int v9; // r15d
  CRowset *v11; // rdx
  __int64 v12; // rcx
  int inserted; // edi
  int v14; // eax
  int v15; // eax
  char *v16; // rbx
  int v17; // eax
  unsigned int v18; // r14d
  __int64 v19; // rdx
  int v20; // r11d
  char *v21; // rsi
  int v22; // r10d
  const struct tagDBBINDING *v23; // r9
  DBPART dwPart; // eax
  DBTYPE wType; // r8
  __int16 v26; // dx
  BYTE bScale; // al
  DBMEMOWNER dwMemOwner; // ecx
  DBTYPE v29; // cx
  DBPARAMIO eParamIO; // ecx
  CImpIAccessor *v31; // rdx
  int v32; // ecx
  DBPART v33; // edx
  DBLENGTH cbMaxLen; // r8
  __int64 v35; // rax
  DBBYTEOFFSET obLength; // rcx
  DBBYTEOFFSET obValue; // rdx
  DBBYTEOFFSET obStatus; // rcx
  DBBYTEOFFSET v39; // rdx
  DBPART v40; // r8d
  DBBYTEOFFSET v41; // rcx
  DBBYTEOFFSET v42; // rdx
  DBBYTEOFFSET v43; // rcx
  DBBYTEOFFSET v44; // rax
  DBPART v45; // r8d
  DBBYTEOFFSET v46; // rcx
  DBBYTEOFFSET v47; // rdx
  DBBYTEOFFSET v48; // rcx
  DBBYTEOFFSET v49; // rdx
  DBORDINAL iOrdinal; // r9
  DBPARAMIO v51; // ecx
  DBORDINAL *v52; // r10
  DBPARAMIO v53; // edx
  DBTYPE v54; // cx
  unsigned __int16 v55; // cx
  int v56; // r8d
  int v57; // eax
  unsigned __int64 v58; // rcx
  __int64 v59; // rax
  unsigned __int64 v60; // rbx
  size_t v61; // r8
  void *v62; // rcx
  unsigned __int64 v63; // rdi
  unsigned __int64 v64; // rsi
  char *v65; // r14
  __int16 v66; // ax
  __int64 v67; // rcx
  __int64 v68; // rax
  int v69; // edi
  unsigned int *v70; // r15
  int v71; // r14d
  int v72; // esi
  bool v73; // zf
  void **v74; // rsi
  __int64 v75; // rdx
  int v76; // eax
  int v77; // edx
  int v78; // eax
  unsigned __int64 v79; // rsi
  void **v80; // rdi
  __int64 v81; // rdx
  __int64 v82; // rax
  int v83; // r12d
  unsigned __int64 v84; // rdx
  CImpIAccessor *v85; // r15
  wchar_t *v86; // r8
  __int64 v87; // rdx
  int v89; // [rsp+60h] [rbp-A0h]
  int v90; // [rsp+64h] [rbp-9Ch]
  int v91; // [rsp+68h] [rbp-98h]
  int v92; // [rsp+6Ch] [rbp-94h] BYREF
  int v93; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 *v94; // [rsp+78h] [rbp-88h]
  unsigned int *v95; // [rsp+80h] [rbp-80h]
  int v96; // [rsp+88h] [rbp-78h]
  int v97; // [rsp+8Ch] [rbp-74h] BYREF
  int v98; // [rsp+90h] [rbp-70h]
  int v99; // [rsp+94h] [rbp-6Ch]
  CImpIAccessor *v100; // [rsp+98h] [rbp-68h]
  unsigned __int64 v101; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v102; // [rsp+A8h] [rbp-58h]
  unsigned int v103; // [rsp+B0h] [rbp-50h] BYREF
  int v104; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v105; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v106; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t v107[80]; // [rsp+D0h] [rbp-30h] BYREF

  v9 = a2;
  v100 = (CImpIAccessor *)this;
  v103 = a2;
  v94 = a6;
  v95 = a7;
  v106 = -1;
  if ( (bidGblFlags & 4) != 0 )
  {
    if ( off_1802662C8[0] )
      bidScopeEnterW(&v106, off_1802662C8[0], *((unsigned int *)this[1] + 13), v103);
    v9 = v103;
  }
  if ( (bidGblFlags & 0x40002) == 0x40002 && (unsigned int)ConstrBidActID(v107, 0x50u) && (bidGblFlags & 2) != 0 )
  {
    if ( off_180262DB0[0] )
      bidTraceW(off_1802601F0[0], 463872, off_180262DB0[0], *((unsigned int *)this[1] + 13));
    v9 = v103;
  }
  v105 = 0;
  v92 = 0;
  v93 = 0;
  v97 = 0;
  v101 = 0;
  if ( a6 )
    *a6 = 0;
  SetErrorInfo(0, 0);
  v11 = this[1];
  if ( *((_DWORD *)v11 + 2) == 6 )
  {
    if ( (*((_DWORD *)v11 + 86) & 0x1000) != 0
      || *((_DWORD *)v11 + 158) != *(_DWORD *)(*((_QWORD *)v11 + 8) + 940LL)
      && (unsigned int)CRowset::FMakeZombie(this[1]) )
    {
      inserted = -2147418113;
      if ( (bidGblFlags & 2) != 0 )
        v15 = bidTraceHR(off_1802601F0[0], 495625, 2147549183LL);
      else
        v15 = -2147418113;
      CError::PostError(g_pCError, v15, &IID_IAccessor, 0x9F07u, 0);
      goto LABEL_275;
    }
    v12 = *((_QWORD *)this[1] + 78);
    if ( v12 && *(_DWORD *)(v12 + 144) )
    {
      inserted = -2147217842;
      if ( (bidGblFlags & 2) != 0 )
        v14 = bidTraceHR(off_1802601F0[0], 495625, 2147749454LL);
      else
        v14 = -2147217842;
      CError::PostHResult(g_pCError, v14, &IID_IAccessor);
      goto LABEL_275;
    }
  }
  v16 = (char *)(this + 24);
  if ( this == (CRowset **)-192LL )
  {
    v102 = 0;
  }
  else
  {
    if ( *(_QWORD *)v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 32LL) + 8LL))(*(_QWORD *)v16 + 32LL);
    v102 = *(_QWORD *)v16;
    v16 = 0;
  }
  if ( !a6 )
    goto LABEL_35;
  if ( a3 )
  {
    if ( !a4 )
    {
LABEL_35:
      if ( (bidGblFlags & 2) != 0 )
        v17 = bidTraceHR(off_1802601F0[0], 508937, 2147942487LL);
      else
        v17 = -2147024809;
      goto LABEL_264;
    }
  }
  else if ( ((_BYTE)this[2] & 1) == 0 || (*((_BYTE *)this[1] + 88) & 4) == 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v17 = bidTraceHR(off_1802601F0[0], 520201, 2147749449LL);
    else
      v17 = -2147217847;
    goto LABEL_264;
  }
  if ( (v9 & 0xFFFFFFF0) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v17 = bidTraceHR(off_1802601F0[0], 527369, 2147749446LL);
    else
      v17 = -2147217850;
    goto LABEL_264;
  }
  if ( (v9 & 2) != 0 )
  {
    if ( (v9 & 1) != 0 )
      v18 = 2;
    else
      v18 = (~(_BYTE)v9 & 8 | 0x20u) >> 3;
    v91 = v18;
    v90 = !(v9 & 1) + 2;
  }
  else
  {
    v18 = 1;
    v91 = 1;
    v90 = 1;
  }
  if ( (v9 & 4) != 0 )
  {
    v89 = ((v9 & 1) == 0) + 2;
  }
  else
  {
    if ( (v9 & 2) == 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v19 = 539657;
        goto LABEL_57;
      }
      goto LABEL_58;
    }
    v89 = 1;
  }
  if ( (v9 & 8) != 0 && ((_DWORD)this[2] & 6) == 2 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v19 = 547849;
LABEL_57:
      v17 = bidTraceHR(off_1802601F0[0], v19, 2147749446LL);
LABEL_264:
      v78 = CError::PostHResult(g_pCError, v17, &IID_IAccessor);
      goto LABEL_265;
    }
    goto LABEL_58;
  }
  if ( (v9 & 4) != 0 )
  {
    if ( ((_BYTE)this[2] & 1) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v19 = 557065;
        goto LABEL_57;
      }
LABEL_58:
      v17 = -2147217850;
      goto LABEL_264;
    }
    memset_0(*((void **)this[4] + 2), 0, *(_QWORD *)this[4] >> 3);
  }
  if ( a7 )
    memset_0(a7, 0, 4 * a3);
  inserted = (int)v16;
  v99 = (int)v16;
  v98 = (int)v16;
  v20 = (int)v16;
  v96 = (int)v16;
  v21 = v16;
  if ( !a3 )
  {
    v58 = (unsigned __int64)v16;
    v91 = v18;
    goto LABEL_179;
  }
  v22 = v9 & 4;
  v104 = v22;
  while ( 2 )
  {
    v23 = &a4[(_QWORD)v21];
    dwPart = v23->dwPart;
    if ( (dwPart & 7) == 0 || (dwPart & 0xFFFFFFF8) != 0 )
    {
      LODWORD(v16) = 3;
LABEL_78:
      if ( (bidGblFlags & 2) != 0 )
      {
        inserted = bidTraceHR(off_1802601F0[0], 758793, 2147749409LL);
        v9 = v103;
      }
      else
      {
        inserted = -2147217887;
      }
      if ( v95 )
        v95[(_QWORD)v21] = (unsigned int)v16;
      goto LABEL_163;
    }
    wType = v23->wType;
    v26 = wType & 0x7000;
    if ( (wType & 0x7000) != 0 && v26 != 0x4000 && v26 != 4096 && v26 != 0x2000 )
    {
      LODWORD(v16) = 3;
      goto LABEL_78;
    }
    switch ( wType & 0x8FFF )
    {
      case 0:
      case 1:
        if ( (v23->eParamIO & 1) == 0 )
          goto LABEL_77;
        goto LABEL_88;
      case 2:
      case 3:
      case 4:
      case 5:
      case 6:
      case 7:
      case 8:
      case 0xB:
      case 0xC:
      case 0xE:
      case 0x10:
      case 0x11:
      case 0x12:
      case 0x13:
      case 0x14:
      case 0x15:
      case 0x40:
      case 0x48:
      case 0x80:
      case 0x81:
      case 0x82:
      case 0x84:
      case 0x85:
      case 0x86:
      case 0x87:
      case 0x8D:
      case 0x90:
      case 0x91:
      case 0x92:
        goto LABEL_88;
      case 0xD:
        if ( !v26 )
          goto LABEL_88;
        LODWORD(v16) = 2;
        goto LABEL_78;
      case 0x83:
        bScale = v23->bScale;
        if ( bScale && bScale > v23->bPrecision )
          goto LABEL_77;
        goto LABEL_88;
      case 0x8F:
        if ( v26 )
        {
          LODWORD(v16) = 2;
          goto LABEL_78;
        }
        if ( v23->eParamIO != 1 )
          goto LABEL_77;
LABEL_88:
        if ( a4[(_QWORD)v21].pTypeInfo || (dwMemOwner = a4[(_QWORD)v21].dwMemOwner, (dwMemOwner & 0xFFFFFFFE) != 0) )
        {
LABEL_77:
          LODWORD(v16) = 3;
          goto LABEL_78;
        }
        if ( dwMemOwner == 1 )
        {
          v29 = a4[(_QWORD)v21].wType;
          if ( (v29 & 0x7000) == 0 && v29 != 8 )
            goto LABEL_77;
          if ( v22 )
          {
            eParamIO = a4[(_QWORD)v21].eParamIO;
            if ( (eParamIO & 2) != 0 || (eParamIO & 1) != 0 && (v9 & 1) == 0 )
              goto LABEL_77;
          }
          v99 = 1;
        }
        v31 = v100;
        if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)v100 + 1) + 8LL) - 6) > 1 )
          goto LABEL_134;
        v32 = a4[(_QWORD)v21].wType;
        if ( (_WORD)v32 == 143 )
          goto LABEL_77;
        v33 = a4[(_QWORD)v21].dwPart;
        if ( (v33 & 1) != 0 )
        {
          cbMaxLen = a4[(_QWORD)v21].cbMaxLen;
          if ( (v32 & 0x6000) == 0 && ((((_WORD)v32 - 8) & 0xFFFA) != 0 || v32 == 12) )
          {
            if ( (v32 & 0x1000) != 0 )
            {
              cbMaxLen = 16;
            }
            else
            {
              v35 = a4[(_QWORD)v21].wType;
              if ( !`FIsFixedLengthOLEDBType'::`2'::fVariableLengthType[v35] )
                cbMaxLen = `GetFixedLengthOLEDBTypeSize'::`2'::fixedLenSizes[v35];
            }
          }
          else
          {
            cbMaxLen = 8;
          }
          if ( (v33 & 2) != 0
            && (obLength = a4[(_QWORD)v21].obLength, obValue = a4[(_QWORD)v21].obValue, obValue < obLength)
            && obValue + cbMaxLen > obLength
            || (a4[(_QWORD)v21].dwPart & 4) != 0
            && (obStatus = a4[(_QWORD)v21].obStatus, v39 = a4[(_QWORD)v21].obValue, v39 < obStatus)
            && v39 + cbMaxLen > obStatus )
          {
            LODWORD(v16) = 3;
          }
        }
        v40 = a4[(_QWORD)v21].dwPart;
        if ( (v40 & 2) == 0 )
          goto LABEL_124;
        if ( (v40 & 1) != 0 )
        {
          v41 = a4[(_QWORD)v21].obLength;
          v42 = a4[(_QWORD)v21].obValue;
          if ( v41 < v42 && v41 + 8 > v42 )
            goto LABEL_123;
        }
        if ( (v40 & 4) == 0 )
          goto LABEL_132;
        v43 = a4[(_QWORD)v21].obStatus;
        v44 = a4[(_QWORD)v21].obLength;
        if ( v44 >= v43 || v44 + 8 <= v43 )
          goto LABEL_125;
LABEL_123:
        LODWORD(v16) = 3;
LABEL_124:
        if ( (v40 & 4) == 0 )
          goto LABEL_132;
LABEL_125:
        v45 = a4[(_QWORD)v21].dwPart;
        if ( (v45 & 1) != 0
          && (v46 = a4[(_QWORD)v21].obStatus, v47 = a4[(_QWORD)v21].obValue, v46 < v47)
          && v46 + 4 > v47
          || (v45 & 2) != 0
          && (v48 = a4[(_QWORD)v21].obStatus, v49 = a4[(_QWORD)v21].obLength, v48 < v49)
          && v48 + 4 > v49 )
        {
          LODWORD(v16) = 3;
          goto LABEL_78;
        }
LABEL_132:
        if ( (_DWORD)v16 )
          goto LABEL_78;
        v31 = v100;
LABEL_134:
        if ( !v22 )
          goto LABEL_163;
        iOrdinal = a4[(_QWORD)v21].iOrdinal;
        if ( !iOrdinal )
        {
          LODWORD(v16) = 1;
          goto LABEL_78;
        }
        v51 = a4[(_QWORD)v21].eParamIO;
        if ( (v51 & 3) == 0 || (v51 & 0xFFFFFFFC) != 0 )
          goto LABEL_77;
        if ( (v51 & 1) == 0 )
          goto LABEL_146;
        v52 = (DBORDINAL *)*((_QWORD *)v31 + 4);
        if ( iOrdinal < *v52 )
        {
          if ( (*(_BYTE *)((iOrdinal >> 3) + v52[2]) & *((_BYTE *)v52 + (a4[(_QWORD)v21].iOrdinal & 7) + 8)) != 0 )
            goto LABEL_77;
          if ( iOrdinal < *v52 )
          {
            *(_BYTE *)(v52[2] + (iOrdinal >> 3)) |= *((_BYTE *)v52 + (a4[(_QWORD)v21].iOrdinal & 7) + 8);
            goto LABEL_146;
          }
        }
        _mm_lfence();
        if ( (int)CBitArray::SetSlots((CBitArray *)v52, a4[(_QWORD)v21].iOrdinal, a4[(_QWORD)v21].iOrdinal) >= 0 )
        {
          v9 = v103;
          v20 = v96;
LABEL_146:
          v53 = a4[(_QWORD)v21].eParamIO;
          if ( (v53 & 2) != 0 )
          {
            v54 = a4[(_QWORD)v21].wType;
            if ( (v54 & 0x4000) != 0 )
            {
              v55 = v54 & 0x8FFF;
              if ( !`FIsFixedLengthOLEDBType'::`2'::fVariableLengthType[v55] && v55 != 144 )
                goto LABEL_77;
            }
          }
          if ( (v9 & 1) != 0 )
          {
            v56 = v98;
            if ( (v53 & 1) != 0 )
              v56 = 1;
            v98 = v56;
            if ( (v53 & 2) != 0 )
              v20 = 1;
            v96 = v20;
            if ( v56 )
            {
              if ( v20 )
                goto LABEL_77;
            }
          }
LABEL_163:
          if ( (unsigned __int64)++v21 >= a3 )
            goto LABEL_167;
          v22 = v104;
          v20 = v96;
          LODWORD(v16) = 0;
          continue;
        }
        if ( (bidGblFlags & 2) == 0 )
        {
          inserted = -2147024882;
          goto LABEL_168;
        }
        inserted = bidTraceHR(off_1802601F0[0], 722953, 2147942414LL);
        v9 = v103;
LABEL_167:
        if ( inserted >= 0 )
        {
          if ( v99 )
          {
            if ( v18 - 4 <= 1 )
              v18 = 3;
            v91 = v18;
          }
          v58 = a3 - 1;
LABEL_179:
          if ( !is_mul_ok(v58, 0x58u)
            || 88 * v58 + 152 < 88 * v58
            || (v59 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 112LL))(g_pMO),
                (v60 = v59) == 0) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_213;
            v75 = 789513;
LABEL_212:
            v76 = bidTraceHR(off_1802601F0[0], v75, 2147942414LL);
LABEL_214:
            v77 = v76;
LABEL_215:
            v78 = CError::PostHResult(g_pCError, v77, &IID_IAccessor);
LABEL_265:
            inserted = v78;
            goto LABEL_266;
          }
          if ( a3 )
          {
            v61 = 88 * a3;
            v62 = (void *)(v59 + 64);
            if ( 88 * a3 )
            {
              if ( v59 != -64 )
              {
                if ( a4 )
                {
                  memcpy_0(v62, a4, v61);
                  goto LABEL_189;
                }
                memset_0(v62, 0, v61);
              }
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
          }
LABEL_189:
          *(_QWORD *)(v60 + 56) = a3;
          v63 = 0;
          if ( a3 )
          {
            _mm_lfence();
            v64 = v60 + 104;
            v65 = (char *)a4 - v60;
            while ( 1 )
            {
              v66 = *(_WORD *)&v65[v64 - 20];
              if ( (v66 == 13 || v66 == 143) && (v65[v64 - 48] & 1) != 0 )
              {
                v67 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                        g_pMO,
                        20);
                *(_QWORD *)v64 = v67;
                if ( !v67 )
                {
                  if ( v63 )
                  {
                    v74 = (void **)(v60 + 88 * v63 + 104);
                    do
                    {
                      --v63;
                      v74 -= 11;
                      if ( *v74 )
                      {
                        operator delete(*v74, 0x14u);
                        *v74 = 0;
                      }
                    }
                    while ( v63 );
                  }
                  _mm_lfence();
                  (*(void (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 128LL))(
                    g_pMO,
                    v60);
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v75 = 822281;
                    goto LABEL_212;
                  }
LABEL_213:
                  v76 = -2147024882;
                  goto LABEL_214;
                }
                v68 = *(_QWORD *)&v65[v64 - 64];
                if ( v68 )
                {
                  *(_OWORD *)v67 = *(_OWORD *)v68;
                  *(_DWORD *)(v67 + 16) = *(_DWORD *)(v68 + 16);
                }
                else
                {
                  *(_DWORD *)v67 = 0;
                  *(GUID *)(*(_QWORD *)v64 + 4LL) = IID_IUnknown;
                }
              }
              else
              {
                *(_QWORD *)v64 = 0;
              }
              ++v63;
              v64 += 88LL;
              if ( v63 >= a3 )
              {
                v9 = v103;
                v18 = v91;
                break;
              }
            }
          }
          v69 = v90;
          if ( (*((_BYTE *)v100 + 16) & 2) == 0 )
          {
            v71 = 0;
            v92 = 0;
            v72 = 0;
            v93 = 0;
            goto LABEL_238;
          }
          v70 = v95;
          CImpIAccessor::ValidateAccessor(
            v100,
            v18,
            v90,
            v89,
            a3,
            (struct tagDBBINDING *const)(v60 + 64),
            v95,
            &v101,
            &v92,
            &v93,
            &v97,
            &v103);
          v71 = v92;
          v72 = v93;
          if ( v92 )
          {
            if ( v93 )
              goto LABEL_220;
            v73 = v90 == 3;
          }
          else
          {
            if ( !v93 )
            {
LABEL_219:
              if ( v97 )
                goto LABEL_220;
              if ( v92 )
              {
                v91 = 0;
              }
              else
              {
                if ( v93 )
                  v69 = 0;
                v90 = v69;
              }
              if ( v70 )
                memset_0(v70, 0, 4 * a3);
              v9 = v103;
LABEL_238:
              if ( v69 == 3 && a3 )
              {
                v81 = 8 * a3;
                if ( !is_mul_ok(a3, 8u) )
                  v81 = -1;
                v82 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(
                        g_pMO,
                        v81);
                *(_QWORD *)(v60 + 48) = v82;
                if ( !v82 )
                {
                  v83 = 0;
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v72 = bidTraceHR(off_1802601F0[0], 908297, 2147942414LL);
                    v71 = v92;
                    v9 = v103;
                  }
                  else
                  {
                    v72 = -2147024882;
                  }
                  goto LABEL_251;
                }
                v84 = 0;
                _mm_lfence();
                do
                {
                  *(_QWORD *)(*(_QWORD *)(v60 + 48) + 8 * v84++) = a4->iOrdinal;
                  ++a4;
                }
                while ( v84 < a3 );
                v71 = v92;
                v72 = v93;
                v9 = v103;
              }
              else
              {
                *(_QWORD *)(v60 + 48) = 0;
              }
              v83 = v90;
LABEL_251:
              *(_DWORD *)(v60 + 24) = v9;
              v85 = v100;
              inserted = CExtPtrBuffer::InsertIntoExtBuffer(*((CExtPtrBuffer **)v100 + 3), v60, &v105);
              if ( inserted >= 0 )
              {
                *(_DWORD *)v60 = v91;
                *(_DWORD *)(v60 + 4) = v83;
                *(_DWORD *)(v60 + 8) = v89;
                *(_DWORD *)(v60 + 12) = v71;
                *(_DWORD *)(v60 + 16) = v72;
                *(_DWORD *)(v60 + 20) = 0;
                *(_DWORD *)(v60 + 28) = 1;
                *(_QWORD *)(v60 + 32) = v101;
                *(_QWORD *)(v60 + 40) = a5;
                *v94 = v105;
                goto LABEL_266;
              }
              _mm_lfence();
              CImpIAccessor::DeleteSqlAccessor(v85, (struct tagSQLACCESSOR *)v60);
              if ( (bidGblFlags & 2) != 0 )
                inserted = bidTraceHR(off_1802601F0[0], 933897, (unsigned int)inserted);
              v77 = inserted;
              goto LABEL_215;
            }
            v73 = (*((_BYTE *)v100 + 16) & 4) == 0;
          }
          if ( v73 )
            goto LABEL_219;
LABEL_220:
          v79 = 0;
          if ( *(_QWORD *)(v60 + 56) )
          {
            v80 = (void **)(v60 + 104);
            do
            {
              if ( *v80 )
              {
                operator delete(*v80, 0x14u);
                *v80 = 0;
              }
              ++v79;
              v80 += 11;
            }
            while ( v79 < *(_QWORD *)(v60 + 56) );
          }
          (*(void (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v60);
          if ( (bidGblFlags & 2) != 0 )
            v76 = bidTraceHR(off_1802601F0[0], 873481, 2147749409LL);
          else
            v76 = -2147217887;
          goto LABEL_214;
        }
LABEL_168:
        _mm_lfence();
        if ( (bidGblFlags & 2) != 0 )
          v57 = bidTraceHR(off_1802601F0[0], 770057, (unsigned int)inserted);
        else
          v57 = inserted;
        CError::PostHResult(g_pCError, v57, &IID_IAccessor);
LABEL_266:
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( inserted < 0 )
          {
            if ( off_180262DC0[0] )
            {
              _mm_lfence();
              v86 = off_180262DC0[0];
              v87 = 964608;
LABEL_272:
              bidTraceW(off_1802601F0[0], v87, v86, (unsigned int)inserted);
            }
          }
          else if ( off_180262DB8[0] )
          {
            _mm_lfence();
            v86 = off_180262DB8[0];
            v87 = 960512;
            goto LABEL_272;
          }
        }
        if ( v102 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(v102 + 32) + 24LL))(v102 + 32);
LABEL_275:
        _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v106);
        return (unsigned int)inserted;
      default:
        LOBYTE(v16) = wType == 0xC000u;
        LODWORD(v16) = (_DWORD)v16 + 2;
        goto LABEL_78;
    }
  }
}

```

## disassembly

```asm
0x18000c6b0  push    rbp
0x18000c6b2  push    rbx
0x18000c6b3  push    rsi
0x18000c6b4  push    rdi
0x18000c6b5  push    r12
0x18000c6b7  push    r13
0x18000c6b9  push    r14
0x18000c6bb  push    r15
0x18000c6bd  lea     rbp, [rsp-88h]
0x18000c6c5  sub     rsp, 188h
0x18000c6cc  mov     rax, cs:__security_cookie
0x18000c6d3  xor     rax, rsp
0x18000c6d6  mov     [rbp+0C0h+var_50], rax
0x18000c6da  mov     r12, r9
0x18000c6dd  mov     r13, r8
0x18000c6e0  mov     r15d, edx
0x18000c6e3  mov     rdi, rcx
0x18000c6e6  mov     [rbp+0C0h+var_128], rcx
0x18000c6ea  mov     [rbp+0C0h+var_110], edx
0x18000c6ed  mov     r14, [rbp+0C0h+arg_28]
0x18000c6f4  mov     [rsp+1C0h+var_148], r14
0x18000c6f9  mov     rsi, [rbp+0C0h+arg_30]
0x18000c700  mov     [rbp+0C0h+var_140], rsi
0x18000c704  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c70b  mov     [rbp+0C0h+var_F8], rax
0x18000c70f  test    byte ptr cs:_bidGblFlags, 4
0x18000c716  jz      short loc_18000C769
0x18000c718  mov     rax, cs:off_1802662C8; "<IAccessor::CreateAccessor|OLEDB|API> %"...
0x18000c71f  test    rax, rax
0x18000c722  jz      short loc_18000C765
0x18000c724  mov     r8, [rcx+8]
0x18000c728  mov     [rsp+1C0h+var_178], rsi
0x18000c72d  mov     [rsp+1C0h+var_180], r14
0x18000c732  mov     rax, [rbp+0C0h+arg_20]
0x18000c739  mov     [rsp+1C0h+var_188], rax
0x18000c73e  mov     [rsp+1C0h+var_190], r9
0x18000c743  mov     [rsp+1C0h+var_198], r13
0x18000c748  mov     [rsp+1C0h+var_1A0], r13
0x18000c74d  mov     r9d, [rbp+0C0h+var_110]
0x18000c751  mov     r8d, [r8+34h]
0x18000c755  mov     rdx, cs:off_1802662C8; "<IAccessor::CreateAccessor|OLEDB|API> %"...
0x18000c75c  lea     rcx, [rbp+0C0h+var_F8]
0x18000c760  call    _bidScopeEnterW
0x18000c765  mov     r15d, [rbp+0C0h+var_110]
0x18000c769  mov     eax, cs:_bidGblFlags
0x18000c76f  and     eax, 40002h
0x18000c774  cmp     eax, 40002h
0x18000c779  jnz     short loc_18000C7DB
0x18000c77b  mov     edx, 50h ; 'P'; unsigned __int64
0x18000c780  lea     rcx, [rbp+0C0h+var_F0]; wchar_t *
0x18000c784  call    ?ConstrBidActID@@YAHPEA_W_K@Z; ConstrBidActID(wchar_t *,unsigned __int64)
0x18000c789  test    eax, eax
0x18000c78b  jz      short loc_18000C7DB
0x18000c78d  test    byte ptr cs:_bidGblFlags, 2
0x18000c794  jz      short loc_18000C7DB
0x18000c796  mov     rax, cs:off_180262DB0; "<CImpIAccessor::CreateAccessor|OLEDB|DR"...
0x18000c79d  test    rax, rax
0x18000c7a0  jz      short loc_18000C7D7
0x18000c7a2  mov     r9, [rdi+8]
0x18000c7a6  lea     rax, [rbp+0C0h+var_F0]
0x18000c7aa  mov     [rsp+1C0h+var_198], rax
0x18000c7af  lea     rax, aIaccessor; "IAccessor"
0x18000c7b6  mov     [rsp+1C0h+var_1A0], rax
0x18000c7bb  mov     r9d, [r9+34h]
0x18000c7bf  mov     r8, cs:off_180262DB0; "<CImpIAccessor::CreateAccessor|OLEDB|DR"...
0x18000c7c6  mov     edx, 71400h
0x18000c7cb  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000c7d2  call    _bidTraceW
0x18000c7d7  mov     r15d, [rbp+0C0h+var_110]
0x18000c7db  xor     ebx, ebx
0x18000c7dd  mov     [rbp+0C0h+var_100], rbx
0x18000c7e1  mov     [rsp+1C0h+var_154], ebx
0x18000c7e5  mov     [rsp+1C0h+var_150], ebx
0x18000c7e9  mov     [rbp+0C0h+var_134], ebx
0x18000c7ec  mov     [rbp+0C0h+var_120], rbx
0x18000c7f0  test    r14, r14
0x18000c7f3  jz      short loc_18000C7F8
0x18000c7f5  mov     [r14], rbx
0x18000c7f8  xor     edx, edx; perrinfo
0x18000c7fa  xor     ecx, ecx; dwReserved
0x18000c7fc  call    cs:__imp_SetErrorInfo
0x18000c802  mov     rdx, [rdi+8]
0x18000c806  mov     eax, 1000h
0x18000c80b  cmp     dword ptr [rdx+8], 6
0x18000c80f  jnz     loc_18000C8E6
0x18000c815  test    [rdx+158h], eax
0x18000c81b  jnz     short loc_18000C89B
0x18000c81d  mov     rax, [rdx+40h]
0x18000c821  mov     ecx, [rax+3ACh]
0x18000c827  cmp     [rdx+278h], ecx
0x18000c82d  jz      short loc_18000C83B
0x18000c82f  mov     rcx, rdx; this
0x18000c832  call    ?FMakeZombie@CRowset@@QEAAHXZ; CRowset::FMakeZombie(void)
0x18000c837  test    eax, eax
0x18000c839  jnz     short loc_18000C89B
0x18000c83b  mov     rax, [rdi+8]
0x18000c83f  mov     rcx, [rax+270h]
0x18000c846  test    rcx, rcx
0x18000c849  jz      loc_18000C8E6
0x18000c84f  cmp     [rcx+90h], ebx
0x18000c855  jz      loc_18000C8E6
0x18000c85b  mov     edi, 80040E4Eh
0x18000c860  test    byte ptr cs:_bidGblFlags, 2
0x18000c867  jz      short loc_18000C87F
0x18000c869  mov     r8d, edi
0x18000c86c  mov     edx, 79009h
0x18000c871  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000c878  call    _bidTraceHR
0x18000c87d  jmp     short loc_18000C881
0x18000c87f  mov     eax, edi
0x18000c881  lea     r8, IID_IAccessor; struct _GUID *
0x18000c888  mov     edx, eax; int
0x18000c88a  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18000c891  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18000c896  jmp     loc_18000D600
0x18000c89b  mov     edi, 8000FFFFh
0x18000c8a0  test    byte ptr cs:_bidGblFlags, 2
0x18000c8a7  jz      short loc_18000C8BF
0x18000c8a9  mov     r8d, edi
0x18000c8ac  mov     edx, 79009h
0x18000c8b1  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000c8b8  call    _bidTraceHR
0x18000c8bd  jmp     short loc_18000C8C1
0x18000c8bf  mov     eax, edi
0x18000c8c1  mov     [rsp+1C0h+var_1A0], rbx; struct tagDISPPARAMS *
0x18000c8c6  mov     r9d, 9F07h; unsigned int
0x18000c8cc  lea     r8, IID_IAccessor; struct _GUID *
0x18000c8d3  mov     edx, eax; int
0x18000c8d5  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18000c8dc  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x18000c8e1  jmp     loc_18000D600
0x18000c8e6  lea     rbx, [rdi+0C0h]
0x18000c8ed  test    rbx, rbx
0x18000c8f0  jz      short loc_18000C916
0x18000c8f2  mov     rcx, [rbx]
0x18000c8f5  test    rcx, rcx
0x18000c8f8  jz      short loc_18000C90B
0x18000c8fa  add     rcx, 20h ; ' '
0x18000c8fe  mov     rax, [rcx]
0x18000c901  mov     rax, [rax+8]
0x18000c905  call    cs:__guard_dispatch_icall_fptr
0x18000c90b  mov     rax, [rbx]
0x18000c90e  mov     [rbp+0C0h+var_118], rax
0x18000c912  xor     ebx, ebx
0x18000c914  jmp     short loc_18000C91A
0x18000c916  mov     [rbp+0C0h+var_118], rbx
0x18000c91a  test    r14, r14
0x18000c91d  jz      short loc_18000C929
0x18000c91f  test    r13, r13
0x18000c922  jz      short loc_18000C952
0x18000c924  test    r12, r12
0x18000c927  jnz     short loc_18000C96A
0x18000c929  test    byte ptr cs:_bidGblFlags, 2
0x18000c930  jz      loc_18000D553
0x18000c936  mov     edx, 7C409h
0x18000c93b  mov     r8d, 80070057h
0x18000c941  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000c948  call    _bidTraceHR
0x18000c94d  jmp     loc_18000D558
0x18000c952  test    byte ptr [rdi+10h], 1
0x18000c956  jz      loc_18000D52A
0x18000c95c  mov     rax, [rdi+8]
0x18000c960  test    byte ptr [rax+58h], 4
0x18000c964  jz      loc_18000D52A
0x18000c96a  test    r15d, 0FFFFFFF0h
0x18000c971  jz      short loc_18000C9A2
0x18000c973  test    byte ptr cs:_bidGblFlags, 2
0x18000c97a  jz      short loc_18000C998
0x18000c97c  mov     edx, 80C09h
0x18000c981  mov     r8d, 80040E46h
0x18000c987  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000c98e  call    _bidTraceHR
0x18000c993  jmp     loc_18000D558
0x18000c998  mov     eax, 80040E46h
0x18000c99d  jmp     loc_18000D558
0x18000c9a2  mov     eax, r15d
0x18000c9a5  mov     ecx, 1
0x18000c9aa  and     eax, 2
0x18000c9ad  jz      short loc_18000C9E8
0x18000c9af  mov     ecx, r15d
0x18000c9b2  and     ecx, 1
0x18000c9b5  jz      short loc_18000C9BF
0x18000c9b7  mov     r14d, 2
0x18000c9bd  jmp     short loc_18000C9D2
0x18000c9bf  movzx   r14d, r15b
0x18000c9c3  not     r14b
0x18000c9c6  and     r14d, 8
0x18000c9ca  or      r14d, 20h
0x18000c9ce  shr     r14d, 3
0x18000c9d2  mov     [rsp+1C0h+var_158], r14d
0x18000c9d7  xor     ecx, 1
0x18000c9da  add     ecx, 2
0x18000c9dd  mov     [rsp+1C0h+var_15C], ecx
0x18000c9e1  mov     ecx, 1
0x18000c9e6  jmp     short loc_18000C9F3
0x18000c9e8  mov     r14d, ecx
0x18000c9eb  mov     [rsp+1C0h+var_158], ecx
0x18000c9ef  mov     [rsp+1C0h+var_15C], ecx
0x18000c9f3  test    r15b, 4
0x18000c9f7  jz      short loc_18000CA0A
0x18000c9f9  mov     eax, r15d
0x18000c9fc  not     eax
0x18000c9fe  and     eax, 1
0x18000ca01  add     eax, 2
0x18000ca04  mov     [rsp+1C0h+var_160], eax
0x18000ca08  jmp     short loc_18000CA16
0x18000ca0a  test    eax, eax
0x18000ca0c  jz      loc_18000D513
0x18000ca12  mov     [rsp+1C0h+var_160], ecx
0x18000ca16  test    r15b, 8
0x18000ca1a  jz      short loc_18000CA6A
0x18000ca1c  mov     eax, [rdi+10h]
0x18000ca1f  and     al, 6
0x18000ca21  cmp     al, 2
0x18000ca23  jnz     short loc_18000CA6A
0x18000ca25  test    byte ptr cs:_bidGblFlags, al
0x18000ca2b  jz      short loc_18000CA46
0x18000ca2d  mov     edx, 85C09h
0x18000ca32  mov     r8d, 80040E46h
0x18000ca38  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000ca3f  call    _bidTraceHR
0x18000ca44  jmp     short loc_18000CA4B
0x18000ca46  mov     eax, 80040E46h
0x18000ca4b  lea     r8, IID_IAccessor; struct _GUID *
0x18000ca52  mov     edx, eax; int
0x18000ca54  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18000ca5b  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18000ca60  mov     r14, [rsp+1C0h+var_148]
0x18000ca65  jmp     loc_18000D56D
0x18000ca6a  test    r15b, 4
0x18000ca6e  jz      short loc_18000CA9C
0x18000ca70  test    byte ptr [rdi+10h], 1
0x18000ca74  jz      short loc_18000CA86
0x18000ca76  test    byte ptr cs:_bidGblFlags, 2
0x18000ca7d  jz      short loc_18000CA46
0x18000ca7f  mov     edx, 88009h
0x18000ca84  jmp     short loc_18000CA32
0x18000ca86  mov     rcx, [rdi+20h]
0x18000ca8a  mov     r8, [rcx]
0x18000ca8d  shr     r8, 3; Size
0x18000ca91  xor     edx, edx; Val
0x18000ca93  mov     rcx, [rcx+10h]; void *
0x18000ca97  call    memset_0
0x18000ca9c  test    rsi, rsi
0x18000ca9f  jz      short loc_18000CAB3
0x18000caa1  lea     r8, ds:0[r13*4]; Size
0x18000caa9  xor     edx, edx; Val
0x18000caab  mov     rcx, rsi; void *
0x18000caae  call    memset_0
0x18000cab3  mov     edi, ebx
0x18000cab5  mov     [rbp+0C0h+var_12C], ebx
0x18000cab8  mov     [rbp+0C0h+var_130], ebx
0x18000cabb  mov     r11d, ebx
0x18000cabe  mov     [rbp+0C0h+var_138], ebx
0x18000cac1  mov     rsi, rbx
0x18000cac4  mov     ecx, 80040E21h
0x18000cac9  test    r13, r13
0x18000cacc  jz      loc_18000D054
0x18000cad2  mov     r10d, r15d
0x18000cad5  and     r10d, 4
0x18000cad9  mov     [rbp+0C0h+var_108], r10d
0x18000cadd  mov     edx, 3
0x18000cae2  imul    r9, rsi, 58h ; 'X'
0x18000cae6  add     r9, r12
0x18000cae9  mov     eax, [r9+38h]
0x18000caed  test    al, 7
0x18000caef  jz      loc_18000CF82
0x18000caf5  test    eax, 0FFFFFFF8h
0x18000cafa  jnz     loc_18000CF82
0x18000cb00  movzx   r8d, word ptr [r9+54h]
0x18000cb05  movzx   edx, r8w
0x18000cb09  mov     eax, 7000h
0x18000cb0e  and     dx, ax
0x18000cb11  jz      short loc_18000CB38
0x18000cb13  mov     eax, 4000h
0x18000cb18  cmp     dx, ax
0x18000cb1b  jz      short loc_18000CB38
0x18000cb1d  mov     eax, 1000h
0x18000cb22  cmp     dx, ax
0x18000cb25  jz      short loc_18000CB38
0x18000cb27  mov     eax, 2000h
0x18000cb2c  cmp     dx, ax
0x18000cb2f  jz      short loc_18000CB38
0x18000cb31  mov     ebx, 3
0x18000cb36  jmp     short loc_18000CB88
0x18000cb38  movzx   eax, r8w
0x18000cb3c  mov     ecx, 8FFFh
0x18000cb41  and     ax, cx
0x18000cb44  movzx   ecx, ax
0x18000cb47  cmp     ecx, 92h; switch 147 cases
0x18000cb4d  ja      def_18000CB75; jumptable 000000018000CB75 default case, cases 9,10,15,22-63,65-71,73-127,136-140,142
0x18000cb53  mov     eax, ecx
0x18000cb55  lea     rcx, cs:180000000h
0x18000cb5c  movzx   eax, ds:(byte_18000D644 - 180000000h)[rcx+rax]
0x18000cb64  mov     ecx, ds:(jpt_18000CB75 - 180000000h)[rcx+rax*4]
0x18000cb6b  lea     rax, cs:180000000h
0x18000cb72  add     rcx, rax
0x18000cb75  jmp     rcx; switch jump
0x18000cb77  test    byte ptr [r9+40h], 1; jumptable 000000018000CB75 cases 0,1
0x18000cb7c  jnz     short loc_18000CBE4; jumptable 000000018000CB75 cases 2-8,11,12,14,16-21,64,72,128-130,132-135,141,144-146
  ... truncated ...
```
