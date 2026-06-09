# CImpIRowsetUpdate::DeleteRows(ulong,ulong,ulong const * const,ulong * const)

- ea: `0x10032510`
- end: `0x10032b93`
- name: `?DeleteRows@CImpIRowsetUpdate@@UAGJKKQBKQAK@Z`
- size: `1667`
- prototype: `int __stdcall(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, const unsigned int *const, unsigned int *const)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001fc50`
- `0x10027a60`
- `0x1002d9b0`
- `0x10032510`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10032b77`
- `KERNEL32!LeaveCriticalSection` at `0x10032b77`
- `KERNEL32!EnterCriticalSection` at `0x100325ab`
- `KERNEL32!EnterCriticalSection` at `0x100325ab`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1003254d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1003254d`
- `msjet40!__imp__JetDelete@8` at `0x10032873`
- `msjet40!__imp__JetDelete@8` at `0x10032873`
- `msjet40!__imp__JetGetBookmark@20` at `0x10032a6c`
- `msjet40!__imp__JetGetBookmark@20` at `0x10032a6c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10032b57`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10032b57`
- `msjet40!__imp__JetGotoBookmark@16` at `0x100327fd`
- `msjet40!__imp__JetGotoBookmark@16` at `0x100327fd`
- `msjet40!__imp__JetMove@16` at `0x100329eb`
- `msjet40!__imp__JetMove@16` at `0x10032a1c`
- `msjet40!__imp__JetMove@16` at `0x100329eb`
- `msjet40!__imp__JetMove@16` at `0x10032a1c`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::DeleteRows(
        CImpIRowsetUpdate *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int *const a5)
{
  unsigned int *v5; // edi
  struct _RTL_CRITICAL_SECTION *v6; // esi
  struct _RTL_CRITICAL_SECTION *v7; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v9; // ecx
  int isZombie; // eax
  int v11; // edi
  int v12; // ebx
  unsigned int v13; // eax
  int v14; // esi
  unsigned int v15; // ebx
  unsigned int v16; // edx
  int v17; // ecx
  int v18; // edx
  bool v19; // zf
  _DWORD *v20; // edx
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  _DWORD *v24; // ebx
  unsigned int v25; // ecx
  int v26; // eax
  int v27; // edx
  _DWORD *v28; // eax
  int v29; // ecx
  int v30; // ecx
  int v31; // eax
  JET_TABLEID v32; // esi
  JET_ERR v33; // eax
  int v34; // ebx
  int v35; // eax
  _DWORD *v36; // ecx
  JET_SESID v37; // edx
  JET_ERR v38; // eax
  JET_ERR v39; // ecx
  int v40; // eax
  JET_ERR Bookmark; // eax
  const struct _GUID *v43; // [esp+0h] [ebp-40h]
  const struct _GUID *v44; // [esp+4h] [ebp-3Ch]
  unsigned int pcbActual; // [esp+10h] [ebp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [esp+14h] [ebp-2Ch]
  struct _RTL_CRITICAL_SECTION *v47; // [esp+18h] [ebp-28h]
  _DWORD *v48; // [esp+1Ch] [ebp-24h]
  unsigned int v49; // [esp+20h] [ebp-20h]
  JET_SESID sesid; // [esp+24h] [ebp-1Ch] BYREF
  int v51; // [esp+28h] [ebp-18h]
  int v52; // [esp+2Ch] [ebp-14h]
  unsigned int v53; // [esp+30h] [ebp-10h]
  int v54; // [esp+3Ch] [ebp-4h]

  v5 = a5;
  v49 = 0;
  v51 = 0;
  v52 = 0;
  sesid = 0;
  SetErrorInfo(0, 0);
  v6 = 0;
  v47 = 0;
  v54 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)this + 2);
  LockSemaphore = v7[2].LockSemaphore;
  if ( LockSemaphore )
  {
    if ( LockSemaphore[4] == 1 && (v9 = (CTransactionState *)LockSemaphore[2]) != 0 )
      isZombie = CTransactionState::isZombie(v9);
    else
      isZombie = LockSemaphore[3];
    if ( isZombie == 1 )
    {
      v11 = -2147418113;
      goto LABEL_118;
    }
  }
  if ( ((int)v7[4].DebugInfo & 0x400) != 0 )
  {
    v11 = -2147217888;
    goto LABEL_118;
  }
  v6 = v7 + 3;
  lpCriticalSection = v7 + 3;
  v47 = v7 + 3;
  EnterCriticalSection(v7 + 3);
  v12 = *((_DWORD *)this + 2);
  if ( !*(_DWORD *)(v12 + 236) )
  {
    v11 = -2147418113;
    goto LABEL_118;
  }
  JoltProperties::GetIntValue(*(JoltProperties **)(v12 + 160), 0x75u, &sesid);
  if ( (sesid & 2) == 0 )
  {
    v11 = -2147217837;
    goto LABEL_118;
  }
  if ( !a3 )
  {
    v11 = 0;
    goto LABEL_121;
  }
  if ( !a4 )
  {
    v11 = -2147024809;
    goto LABEL_118;
  }
  if ( CRowset::GetEditCursor((CRowset *)v12) )
  {
    v11 = -2147467259;
    goto LABEL_118;
  }
  v13 = 0;
  v53 = 0;
  v14 = 0;
  while ( 1 )
  {
    v15 = v13;
    if ( v5 )
      v5[v13] = 0;
    sesid = (JET_SESID)&a4[v15];
    v16 = a4[v15];
    v48 = *(_DWORD **)(*((_DWORD *)this + 2) + 104);
    v17 = v48[6];
    if ( v16 > v17 + 8 * v48[5] - 1
      || (*(_BYTE *)(((v16 - v17) >> 3) + v48[4]) & *((_BYTE *)&Bitmap::ThisBit + ((v16 - v17) & 7))) != 0
      || (v18 = *(_DWORD *)sesid * *v48, v19 = v48[2] + v18 == 0, v20 = (_DWORD *)(v48[2] + v18), v48 = v20, v19)
      || *v20 == -1 )
    {
      v26 = 1;
      v51 = 1;
      if ( v5 )
        v5[v15] = 12;
LABEL_106:
      v25 = v53;
LABEL_107:
      v27 = v52;
      goto LABEL_108;
    }
    v21 = v20[1];
    if ( v21 == 16 || v21 == 4 )
    {
      v25 = v53;
      v26 = 1;
      v27 = v52;
      v51 = 1;
      if ( v5 )
        v5[v15] = 8;
      goto LABEL_108;
    }
    v22 = *((_DWORD *)this + 2);
    if ( (*(_BYTE *)(v22 + 96) & 0x10) != 0 )
    {
      v32 = *(_DWORD *)(v22 + 112);
      if ( v32 == -1 )
        v32 = *(_DWORD *)(v22 + 108);
      v33 = JetGotoBookmark(*(_DWORD *)(*(_DWORD *)(v22 + 56) + 16), v32, v20, 4u);
      v14 = v33;
      v49 = v33;
      if ( v33 == -1017 )
      {
        if ( v5 )
          v5[v15] = 8;
        v26 = 1;
        v51 = 1;
        goto LABEL_106;
      }
      if ( v33 )
      {
        if ( v5 )
          v5[v15] = 12;
        v26 = 1;
        v51 = 1;
        goto LABEL_106;
      }
      if ( CRowset::RowNotify((CRowset *)sesid, 6u, 0, (enum DBREASONENUM)v43, (enum DBEVENTPHASEENUM)v44) )
      {
        if ( v5 )
          v5[v15] = 4;
        v26 = 1;
        v51 = 1;
        goto LABEL_106;
      }
      v14 = JetDelete(
              *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 16),
              *(_DWORD *)(*((_DWORD *)this + 2) + 112));
      v49 = v14;
      if ( v14 < 0 )
        CRowset::RowNotify(
          (CRowset *)sesid,
          6u,
          (const unsigned int *const)3,
          (enum DBREASONENUM)v43,
          (enum DBEVENTPHASEENUM)v44);
      if ( v14 > -1102 )
      {
        if ( v14 > 1624 )
        {
          if ( v14 != 1625 && v14 != 1626 )
            goto LABEL_79;
        }
        else if ( v14 != 1624 )
        {
          if ( v14 == -1053 )
            goto LABEL_68;
          if ( v14 )
            goto LABEL_79;
          goto LABEL_83;
        }
        if ( v5 )
          v5[v15] = 2;
LABEL_83:
        v52 = 1;
        CRowset::RowNotify(
          (CRowset *)sesid,
          6u,
          (const unsigned int *const)4,
          (enum DBREASONENUM)v43,
          (enum DBEVENTPHASEENUM)v44);
        v48[1] = 16;
        v34 = *((_DWORD *)this + 2);
        v19 = *(_DWORD *)(v34 + 116) == 4;
        v35 = *(_DWORD *)(v34 + 56);
        v36 = *(_DWORD **)(v34 + 128);
        v48 = v36;
        v37 = *(_DWORD *)(v35 + 16);
        sesid = v37;
        if ( v19 )
        {
          v26 = v51;
          v27 = 1;
          v25 = v53;
          goto LABEL_108;
        }
        v38 = JetMove(v37, *(_DWORD *)(v34 + 108), 2 * (v36 == (_DWORD *)2) - 1, 0);
        v39 = v38;
        if ( !v38 )
          goto LABEL_91;
        if ( v38 == -1603 )
        {
          if ( (*(_BYTE *)(v34 + 96) & 4) == 0 )
          {
            v39 = JetMove(sesid, *(_DWORD *)(v34 + 108), (v48 != (_DWORD *)2) + 0x7FFFFFFF, 0);
            *(_DWORD *)(v34 + 128) = 0;
          }
          v40 = *(_DWORD *)(v34 + 96);
          if ( (v40 & 0x80u) == 0 )
            *(_DWORD *)(v34 + 96) = v40 | 4;
          if ( !v39 )
          {
LABEL_91:
            if ( v48 == (_DWORD *)2 )
              *(_DWORD *)(v34 + 96) &= ~0x200u;
          }
        }
        if ( !*(_DWORD *)(v34 + 132)
          || (Bookmark = JetGetBookmark(
                           *(_DWORD *)(*(_DWORD *)(v34 + 56) + 16),
                           *(_DWORD *)(v34 + 108),
                           (void *)(v34 + 124),
                           4u,
                           &pcbActual),
              Bookmark >= 0) )
        {
          v26 = v51;
          goto LABEL_106;
        }
        v25 = v53;
        v19 = Bookmark == -1603;
        v27 = v52;
        v26 = v51;
        if ( v19 )
          *(_DWORD *)(v34 + 124) = -1;
        goto LABEL_108;
      }
      if ( v14 != -1102 )
      {
        if ( v14 > -1613 )
        {
          if ( v14 != -1612 && v14 != -1605 )
            goto LABEL_79;
        }
        else if ( v14 != -1613 )
        {
          if ( v14 == -1907 || v14 == -1809 )
          {
            v25 = v53;
            v26 = 1;
            v27 = v52;
            v51 = 1;
            if ( v5 )
              v5[v15] = 16;
            goto LABEL_108;
          }
LABEL_79:
          v25 = v53;
          v26 = 1;
          v27 = v52;
          v51 = 1;
          if ( v5 )
            v5[v15] = 19;
          goto LABEL_108;
        }
LABEL_68:
        v25 = v53;
        v26 = 1;
        v27 = v52;
        v51 = 1;
        if ( v5 )
          v5[v15] = 11;
        goto LABEL_108;
      }
      v25 = v53;
      v26 = 1;
      v27 = v52;
      v51 = 1;
      if ( v5 )
        v5[v15] = 7;
    }
    else
    {
      v23 = *(_DWORD *)(v22 + 220);
      v24 = v20;
      if ( v23 == -2
        || *(_DWORD *)(v22 + 236)
        && ((v5 = a5, v14 = v49, *(_DWORD *)(v22 + 224) == *(_DWORD *)sesid) || v23 == -1 && !*(_DWORD *)(v22 + 224)) )
      {
        if ( CRowset::RowNotify((CRowset *)sesid, 6u, 0, (enum DBREASONENUM)v43, (enum DBEVENTPHASEENUM)v44) )
        {
          v25 = v53;
          if ( v5 )
            v5[v53] = 4;
          v26 = 1;
          v51 = 1;
          goto LABEL_107;
        }
        v28 = (_DWORD *)(*((_DWORD *)this + 2) + 220);
        if ( *v24 == -2 )
        {
          *v28 = -1;
          v29 = 16;
          v28[2] = 0;
          v28[1] = 0;
          v28[3] = -1;
          v28[4] = 1;
        }
        else
        {
          *v28 = *v24;
          v30 = *((_DWORD *)this + 2);
          v31 = *(_DWORD *)sesid;
          *(_DWORD *)(v30 + 228) = *(_DWORD *)sesid;
          *(_DWORD *)(v30 + 224) = v31;
          v29 = 4;
          ++v24[2];
        }
        v48[1] = v29;
        CRowset::RowNotify(
          (CRowset *)sesid,
          6u,
          (const unsigned int *const)4,
          (enum DBREASONENUM)v43,
          (enum DBEVENTPHASEENUM)v44);
        v26 = v51;
        v27 = 1;
        v25 = v53;
        v52 = 1;
      }
      else
      {
        v25 = v53;
        v26 = 1;
        v27 = v52;
        v51 = 1;
        if ( v5 )
          v5[v53] = 13;
      }
    }
LABEL_108:
    v53 = v25 + 1;
    if ( v25 + 1 >= a3 )
      break;
    v13 = v53;
  }
  if ( v27 == 1 )
  {
    v11 = 265946;
    if ( v26 != 1 )
      v11 = 0;
  }
  else
  {
    v11 = 0;
    if ( v26 == 1 )
      v11 = -2147217887;
  }
  v19 = v14 == 0;
  v6 = lpCriticalSection;
  if ( !v19 )
  {
    CExtError::SendJetErrortoOLEAuto(v49, (int)&IID_IRowsetUpdate, (int)v43, v44);
    goto LABEL_121;
  }
  if ( v11 < 0 )
  {
LABEL_118:
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 16),
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 20),
            &pcbActual,
            4,
            3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IRowsetUpdate, 0, v43, (int)v44);
  }
LABEL_121:
  if ( v6 )
    LeaveCriticalSection(v6);
  return v11;
}

```

## disassembly

```asm
0x10032510  mov     edi, edi
0x10032512  push    ebp
0x10032513  mov     ebp, esp
0x10032515  push    0FFFFFFFFh
0x10032517  push    offset ?DeleteRows@CImpIRowsetUpdate@@UAGJKKQBKQAK@Z_SEH
0x1003251c  mov     eax, large fs:0
0x10032522  push    eax
0x10032523  sub     esp, 24h
0x10032526  push    ebx
0x10032527  push    esi
0x10032528  push    edi
0x10032529  mov     eax, ___security_cookie
0x1003252e  xor     eax, ebp
0x10032530  push    eax
0x10032531  lea     eax, [ebp+var_C]
0x10032534  mov     large fs:0, eax
0x1003253a  mov     edi, [ebp+arg_10]
0x1003253d  xor     eax, eax
0x1003253f  push    eax; perrinfo
0x10032540  push    eax; dwReserved
0x10032541  mov     [ebp+var_20], eax
0x10032544  mov     [ebp+var_18], eax
0x10032547  mov     [ebp+var_14], eax
0x1003254a  mov     [ebp+sesid], eax
0x1003254d  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10032553  xor     esi, esi
0x10032555  mov     [ebp+var_28], esi
0x10032558  mov     eax, [ebp+this]
0x1003255b  mov     [ebp+var_4], esi
0x1003255e  mov     edx, [eax+8]
0x10032561  mov     eax, [edx+40h]
0x10032564  test    eax, eax
0x10032566  jz      short loc_1003258E
0x10032568  cmp     dword ptr [eax+10h], 1
0x1003256c  jnz     short loc_1003257C
0x1003256e  mov     ecx, [eax+8]; this
0x10032571  test    ecx, ecx
0x10032573  jz      short loc_1003257C
0x10032575  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1003257a  jmp     short loc_1003257F
0x1003257c  mov     eax, [eax+0Ch]
0x1003257f  cmp     eax, 1
0x10032582  jnz     short loc_1003258E
0x10032584  mov     edi, 8000FFFFh
0x10032589  jmp     loc_10032B40
0x1003258e  test    dword ptr [edx+60h], 400h
0x10032595  jz      short loc_100325A1
0x10032597  mov     edi, 80040E20h
0x1003259c  jmp     loc_10032B40
0x100325a1  lea     esi, [edx+48h]
0x100325a4  push    esi; lpCriticalSection
0x100325a5  mov     [ebp+lpCriticalSection], esi
0x100325a8  mov     [ebp+var_28], esi
0x100325ab  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100325b1  mov     ebx, [ebp+this]
0x100325b4  mov     ebx, [ebx+8]
0x100325b7  cmp     dword ptr [ebx+0ECh], 0
0x100325be  jnz     short loc_100325CA
0x100325c0  mov     edi, 8000FFFFh
0x100325c5  jmp     loc_10032B40
0x100325ca  mov     ecx, [ebx+0A0h]; this
0x100325d0  lea     eax, [ebp+sesid]
0x100325d3  push    eax; unsigned int *
0x100325d4  push    75h ; 'u'; unsigned int
0x100325d6  call    ?GetIntValue@JoltProperties@@QBEJKAAK@Z; JoltProperties::GetIntValue(ulong,ulong &)
0x100325db  test    byte ptr [ebp+sesid], 2
0x100325df  jnz     short loc_100325EB
0x100325e1  mov     edi, 80040E53h
0x100325e6  jmp     loc_10032B40
0x100325eb  cmp     [ebp+arg_8], 0
0x100325ef  jz      loc_10032B70
0x100325f5  cmp     [ebp+arg_C], 0
0x100325f9  jnz     short loc_10032605
0x100325fb  mov     edi, 80070057h
0x10032600  jmp     loc_10032B40
0x10032605  mov     ecx, ebx; this
0x10032607  call    ?GetEditCursor@CRowset@@IAEJXZ; CRowset::GetEditCursor(void)
0x1003260c  test    eax, eax
0x1003260e  jz      short loc_1003261A
0x10032610  mov     edi, 80004005h
0x10032615  jmp     loc_10032B40
0x1003261a  xor     eax, eax
0x1003261c  mov     [ebp+var_10], eax
0x1003261f  cmp     [ebp+arg_8], eax
0x10032622  jbe     loc_10032B70
0x10032628  xor     esi, esi
0x1003262a  jmp     short loc_10032633
0x10032630  mov     eax, [ebp+var_10]
0x10032633  lea     ebx, ds:0[eax*4]
0x1003263a  test    edi, edi
0x1003263c  jz      short loc_10032645
0x1003263e  mov     dword ptr [edi+ebx], 0
0x10032645  mov     eax, [ebp+this]
0x10032648  mov     ecx, [ebp+arg_C]
0x1003264b  add     ecx, ebx
0x1003264d  mov     [ebp+sesid], ecx
0x10032650  mov     eax, [eax+8]
0x10032653  mov     edx, [ecx]
0x10032655  mov     eax, [eax+68h]
0x10032658  mov     [ebp+var_24], eax
0x1003265b  mov     ecx, [eax+18h]
0x1003265e  mov     eax, [eax+14h]
0x10032661  lea     eax, ds:0FFFFFFFFh[eax*8]
0x10032668  add     eax, ecx
0x1003266a  cmp     edx, eax
0x1003266c  ja      loc_10032ABF
0x10032672  mov     eax, [ebp+var_24]
0x10032675  sub     edx, ecx
0x10032677  mov     ecx, edx
0x10032679  and     edx, 7
0x1003267c  shr     ecx, 3
0x1003267f  mov     eax, [eax+10h]
0x10032682  mov     al, [ecx+eax]
0x10032685  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1003268b  jnz     loc_10032ABF
0x10032691  mov     eax, [ebp+var_24]
0x10032694  mov     ecx, [ebp+sesid]
0x10032697  mov     edx, [eax]
0x10032699  imul    edx, [ecx]
0x1003269c  add     edx, [eax+8]
0x1003269f  mov     [ebp+var_24], edx
0x100326a2  jz      loc_10032ABF
0x100326a8  cmp     dword ptr [edx], 0FFFFFFFFh
0x100326ab  jz      loc_10032ABF
0x100326b1  mov     eax, [edx+4]
0x100326b4  cmp     eax, 10h
0x100326b7  jz      loc_10032AA4
0x100326bd  cmp     eax, 4
0x100326c0  jz      loc_10032AA4
0x100326c6  mov     eax, [ebp+this]
0x100326c9  mov     ecx, [eax+8]
0x100326cc  test    byte ptr [ecx+60h], 10h
0x100326d0  jnz     loc_100327E8
0x100326d6  mov     eax, [ecx+0DCh]
0x100326dc  mov     ebx, edx
0x100326de  cmp     eax, 0FFFFFFFEh
0x100326e1  jz      short loc_1003270D
0x100326e3  cmp     dword ptr [ecx+0ECh], 0
0x100326ea  jz      short loc_1003273D
0x100326ec  mov     edi, [ebp+sesid]
0x100326ef  mov     esi, [edi]
0x100326f1  cmp     [ecx+0E0h], esi
0x100326f7  mov     edi, [ebp+arg_10]
0x100326fa  mov     esi, [ebp+var_20]
0x100326fd  jz      short loc_1003270D
0x100326ff  cmp     eax, 0FFFFFFFFh
0x10032702  jnz     short loc_1003273D
0x10032704  cmp     dword ptr [ecx+0E0h], 0
0x1003270b  jnz     short loc_1003273D
0x1003270d  push    0; unsigned int *
0x1003270f  push    6; unsigned int
0x10032711  push    [ebp+sesid]; this
0x10032714  mov     edx, 1
0x10032719  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x1003271e  test    eax, eax
0x10032720  jz      short loc_1003275F
0x10032722  mov     ecx, [ebp+var_10]
0x10032725  test    edi, edi
0x10032727  jz      short loc_10032730
0x10032729  mov     dword ptr [edi+ecx*4], 4
0x10032730  mov     eax, 1
0x10032735  mov     [ebp+var_18], eax
0x10032738  jmp     loc_10032AE7
0x1003273d  mov     ecx, [ebp+var_10]
0x10032740  mov     eax, 1
0x10032745  mov     edx, [ebp+var_14]
0x10032748  mov     [ebp+var_18], eax
0x1003274b  test    edi, edi
0x1003274d  jz      loc_10032AEA
0x10032753  mov     dword ptr [edi+ecx*4], 0Dh
0x1003275a  jmp     loc_10032AEA
0x1003275f  mov     edx, [ebp+this]
0x10032762  mov     ecx, [ebx]
0x10032764  mov     eax, [edx+8]
0x10032767  add     eax, 0DCh
0x1003276c  cmp     ecx, 0FFFFFFFEh
0x1003276f  jnz     short loc_1003279A
0x10032771  mov     dword ptr [eax], 0FFFFFFFFh
0x10032777  mov     ecx, 10h
0x1003277c  mov     dword ptr [eax+8], 0
0x10032783  mov     dword ptr [eax+4], 0
0x1003278a  mov     dword ptr [eax+0Ch], 0FFFFFFFFh
0x10032791  mov     dword ptr [eax+10h], 1
0x10032798  jmp     short loc_100327B8
0x1003279a  mov     [eax], ecx
0x1003279c  mov     ecx, [edx+8]
0x1003279f  mov     eax, [ebp+sesid]
0x100327a2  mov     eax, [eax]
0x100327a4  mov     [ecx+0E4h], eax
0x100327aa  mov     [ecx+0E0h], eax
0x100327b0  mov     ecx, 4
0x100327b5  inc     dword ptr [ebx+8]
0x100327b8  mov     eax, [ebp+var_24]
0x100327bb  mov     edx, 1
0x100327c0  push    4; unsigned int *
0x100327c2  push    6; unsigned int
0x100327c4  mov     [eax+4], ecx
0x100327c7  mov     eax, [ebp+this]
0x100327ca  push    [ebp+sesid]; this
0x100327cd  mov     ecx, [eax+8]
0x100327d0  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x100327d5  mov     eax, [ebp+var_18]
0x100327d8  mov     edx, 1
0x100327dd  mov     ecx, [ebp+var_10]
0x100327e0  mov     [ebp+var_14], edx
0x100327e3  jmp     loc_10032AEA
0x100327e8  mov     esi, [ecx+70h]
0x100327eb  mov     eax, [ecx+38h]
0x100327ee  cmp     esi, 0FFFFFFFFh
0x100327f1  jnz     short loc_100327F6
0x100327f3  mov     esi, [ecx+6Ch]
0x100327f6  push    4; cbBookmark
0x100327f8  push    edx; pvBookmark
0x100327f9  push    esi; tableid
0x100327fa  push    dword ptr [eax+10h]; sesid
0x100327fd  call    ds:__imp__JetGotoBookmark@16; JetGotoBookmark(x,x,x,x)
0x10032803  mov     esi, eax
0x10032805  mov     [ebp+var_20], esi
0x10032808  cmp     esi, 0FFFFFC07h
0x1003280e  jz      loc_10032A8F
0x10032814  test    esi, esi
0x10032816  jz      short loc_10032830
0x10032818  test    edi, edi
0x1003281a  jz      short loc_10032823
0x1003281c  mov     dword ptr [edi+ebx], 0Ch
0x10032823  mov     eax, 1
0x10032828  mov     [ebp+var_18], eax
0x1003282b  jmp     loc_10032AE4
0x10032830  mov     eax, [ebp+this]
0x10032833  mov     edx, 1
0x10032838  push    0; unsigned int *
0x1003283a  push    6; unsigned int
0x1003283c  push    [ebp+sesid]; this
0x1003283f  mov     ecx, [eax+8]
0x10032842  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10032847  test    eax, eax
0x10032849  jz      short loc_10032863
0x1003284b  test    edi, edi
0x1003284d  jz      short loc_10032856
0x1003284f  mov     dword ptr [edi+ebx], 4
0x10032856  mov     eax, 1
0x1003285b  mov     [ebp+var_18], eax
0x1003285e  jmp     loc_10032AE4
0x10032863  mov     eax, [ebp+this]
0x10032866  mov     eax, [eax+8]
0x10032869  mov     ecx, [eax+70h]
0x1003286c  mov     eax, [eax+38h]
0x1003286f  push    ecx; tableid
0x10032870  push    dword ptr [eax+10h]; sesid
0x10032873  call    ds:__imp__JetDelete@8; JetDelete(x,x)
0x10032879  mov     esi, eax
0x1003287b  mov     [ebp+var_20], esi
0x1003287e  test    esi, esi
0x10032880  jns     short loc_10032899
0x10032882  mov     eax, [ebp+this]
0x10032885  mov     edx, 1
0x1003288a  push    3; unsigned int *
0x1003288c  push    6; unsigned int
0x1003288e  push    [ebp+sesid]; this
0x10032891  mov     ecx, [eax+8]
0x10032894  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10032899  cmp     esi, 0FFFFFBB2h
0x1003289f  jg      loc_1003293B
0x100328a5  jz      short loc_10032919
0x100328a7  cmp     esi, 0FFFFF9B3h
0x100328ad  jg      short loc_100328E7
0x100328af  jz      short loc_100328F7
0x100328b1  cmp     esi, 0FFFFF88Dh
0x100328b7  jz      short loc_100328C5
0x100328b9  cmp     esi, 0FFFFF8EFh
0x100328bf  jnz     loc_10032961
0x100328c5  mov     ecx, [ebp+var_10]
0x100328c8  mov     eax, 1
0x100328cd  mov     edx, [ebp+var_14]
0x100328d0  mov     [ebp+var_18], eax
0x100328d3  test    edi, edi
0x100328d5  jz      loc_10032AEA
0x100328db  mov     dword ptr [edi+ebx], 10h
0x100328e2  jmp     loc_10032AEA
0x100328e7  cmp     esi, 0FFFFF9B4h
0x100328ed  jz      short loc_100328F7
0x100328ef  cmp     esi, 0FFFFF9BBh
0x100328f5  jnz     short loc_10032961
0x100328f7  mov     ecx, [ebp+var_10]
0x100328fa  mov     eax, 1
0x100328ff  mov     edx, [ebp+var_14]
0x10032902  mov     [ebp+var_18], eax
0x10032905  test    edi, edi
0x10032907  jz      loc_10032AEA
0x1003290d  mov     dword ptr [edi+ebx], 0Bh
0x10032914  jmp     loc_10032AEA
0x10032919  mov     ecx, [ebp+var_10]
0x1003291c  mov     eax, 1
0x10032921  mov     edx, [ebp+var_14]
0x10032924  mov     [ebp+var_18], eax
0x10032927  test    edi, edi
0x10032929  jz      loc_10032AEA
0x1003292f  mov     dword ptr [edi+ebx], 7
0x10032936  jmp     loc_10032AEA
0x1003293b  cmp     esi, 658h
  ... truncated ...
```
