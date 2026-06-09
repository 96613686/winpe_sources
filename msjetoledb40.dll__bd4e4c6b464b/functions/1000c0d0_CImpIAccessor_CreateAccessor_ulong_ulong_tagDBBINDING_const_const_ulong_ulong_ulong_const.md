# CImpIAccessor::CreateAccessor(ulong,ulong,tagDBBINDING const * const,ulong,ulong *,ulong * const)

- ea: `0x1000c0d0`
- end: `0x1000c747`
- name: `?CreateAccessor@CImpIAccessor@@UAGJKKQBUtagDBBINDING@@KPAKQAK@Z`
- size: `1655`
- prototype: `int(CImpIAccessor *__hidden this, unsigned int, unsigned int, const struct tagDBBINDING *const, unsigned int, unsigned int *, unsigned int *const)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x1000ba90`
- `0x1000c0d0`
- `0x1000c750`
- `0x1000e9d0`
- `0x1000e9f0`
- `0x1001c380`
- `0x1001c5c0`
- `0x1001c6d0`
- `0x100495b0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`
- `0x1004dc81`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000c719`
- `KERNEL32!LeaveCriticalSection` at `0x1000c719`
- `KERNEL32!EnterCriticalSection` at `0x1000c12e`
- `KERNEL32!EnterCriticalSection` at `0x1000c12e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000c11e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000c11e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000c6fd`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000c6fd`

## pseudocode

```c
int __stdcall CImpIAccessor::CreateAccessor(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        unsigned int a3,
        const struct tagDBBINDING *const Src,
        unsigned int a5,
        unsigned int *a6,
        struct tagDBBINDING *a7)
{
  int inserted; // edi
  struct _RTL_CRITICAL_SECTION *v8; // esi
  struct _RTL_CRITICAL_SECTION *v9; // eax
  bool v10; // zf
  _DWORD *v11; // eax
  CTransactionState *v12; // ecx
  int isZombie; // eax
  int v14; // eax
  BOOL v15; // ecx
  size_t v16; // edx
  size_t v17; // ecx
  CImpIAccessor *v18; // ecx
  unsigned int v19; // eax
  struct tagDBBINDING *v20; // ecx
  unsigned int i; // esi
  int v22; // eax
  struct tagDBBINDING *v23; // ecx
  unsigned int v24; // edx
  int v25; // ecx
  int v26; // eax
  unsigned int v27; // eax
  int wType; // edx
  unsigned int v29; // edx
  int v30; // eax
  size_t v31; // eax
  _DWORD *v32; // edi
  unsigned int v33; // ecx
  void *v34; // eax
  unsigned int v35; // edx
  int v36; // ecx
  unsigned int v37; // eax
  const struct tagDBBINDING *v38; // edx
  int v39; // ecx
  _DWORD *v40; // eax
  size_t v41; // ecx
  int v42; // ecx
  int v43; // eax
  struct _GUID *v45; // [esp+0h] [ebp-54h]
  unsigned int *v46; // [esp+4h] [ebp-50h]
  void *v47; // [esp+Ch] [ebp-48h] BYREF
  int v48; // [esp+10h] [ebp-44h]
  int v49; // [esp+14h] [ebp-40h]
  int v50; // [esp+18h] [ebp-3Ch]
  char v51; // [esp+1Ch] [ebp-38h] BYREF
  int v52; // [esp+20h] [ebp-34h]
  size_t Size; // [esp+24h] [ebp-30h] BYREF
  unsigned int RecursionCount; // [esp+28h] [ebp-2Ch] BYREF
  size_t v55; // [esp+2Ch] [ebp-28h]
  LPCRITICAL_SECTION lpCriticalSection; // [esp+30h] [ebp-24h]
  int v57; // [esp+34h] [ebp-20h]
  CImpIAccessor *v58; // [esp+38h] [ebp-1Ch]
  void *Block; // [esp+3Ch] [ebp-18h]
  unsigned int v60; // [esp+40h] [ebp-14h]
  unsigned int v61; // [esp+44h] [ebp-10h]
  int v62; // [esp+50h] [ebp-4h]

  inserted = 0;
  v48 = 1;
  v49 = 0;
  v47 = &v51;
  v52 = 0;
  v50 = 1;
  v51 = 0;
  v62 = 0;
  SetErrorInfo(0, 0);
  v8 = this + 1;
  lpCriticalSection = this + 1;
  EnterCriticalSection(this + 1);
  v9 = this;
  LOBYTE(v62) = 1;
  if ( ((int)this->LockSemaphore & 1) != 0 )
  {
    RecursionCount = this->RecursionCount;
    v10 = (*(int (__thiscall **)(unsigned int))(*(_DWORD *)RecursionCount + 20))(RecursionCount) == 0;
    v9 = this;
    if ( !v10 )
    {
      RecursionCount = this->RecursionCount;
      v11 = (_DWORD *)(*(int (__thiscall **)(unsigned int))(*(_DWORD *)RecursionCount + 20))(RecursionCount);
      if ( v11[4] == 1 && (v12 = (CTransactionState *)v11[2]) != 0 )
        isZombie = CTransactionState::isZombie(v12);
      else
        isZombie = v11[3];
      if ( isZombie == 1 )
      {
        inserted = -2147418113;
        goto LABEL_131;
      }
      v9 = this;
    }
    inserted = 0;
  }
  if ( !a6 )
  {
    inserted = -2147024809;
    goto LABEL_131;
  }
  *a6 = 0;
  if ( a3 && !Src )
  {
    inserted = -2147024809;
    goto LABEL_131;
  }
  v14 = (int)v9->LockSemaphore & 1;
  RecursionCount = v14;
  if ( !v14 && !a3 )
  {
    inserted = -2147217847;
    goto LABEL_131;
  }
  if ( !a2 || (a2 & 0xFFFFFFF0) != 0 || (a2 & 0xFFFFFFF9) != 0 && (a2 & 6) == 0 )
    goto LABEL_130;
  if ( (a2 & 2) != 0 )
  {
    if ( (a2 & 1) != 0 )
    {
      v15 = !(a2 & 1);
      v58 = (CImpIAccessor *)2;
      v57 = v15 + 2;
    }
    else
    {
      v15 = 1;
      v58 = (CImpIAccessor *)(4 - ((a2 & 8) != 0));
      v14 = RecursionCount;
      v57 = 3;
    }
  }
  else
  {
    v58 = (CImpIAccessor *)1;
    v15 = !(a2 & 1);
    v57 = 1;
  }
  Block = (void *)(a2 & 4);
  if ( (a2 & 4) != 0 )
  {
    v16 = v15 + 2;
    v55 = v15 + 2;
  }
  else
  {
    v17 = Size;
    if ( (a2 & 2) != 0 )
      v17 = 1;
    v55 = v17;
    v16 = v17;
  }
  v18 = v58;
  v8 = lpCriticalSection;
  if ( v58 == (CImpIAccessor *)2 || v16 == 2 )
  {
    inserted = -2147217848;
    goto LABEL_131;
  }
  if ( v14 && Block )
  {
LABEL_130:
    inserted = -2147217850;
    goto LABEL_131;
  }
  v19 = a3;
  if ( !a3 )
    goto LABEL_99;
  v20 = a7;
  for ( i = 0; i < a3; ++i )
  {
    v61 = 4 * i;
    if ( v20 )
      *(&v20->iOrdinal + i) = 0;
    else
      v61 = 4 * i;
    v22 = 52 * i;
    v60 = 52 * i;
    v23 = a7;
    if ( Src[i].iOrdinal )
    {
      if ( !Block )
        goto LABEL_61;
    }
    else
    {
      if ( !Block )
        goto LABEL_61;
      if ( a7 )
        *(&a7->iOrdinal + i) = 1;
      inserted = -2147217887;
    }
    v23 = a7;
    if ( (*((_BYTE *)&Src->eParamIO + v22) & 1) != 0 )
    {
      v24 = *(DBORDINAL *)((char *)&Src->iOrdinal + v22);
      v25 = v49;
      Size = 8 * v48;
      RecursionCount = v24;
      if ( v24 < v49 + 8 * v48 - 1 )
      {
        if ( (*((_BYTE *)v47 + ((v24 - v49) >> 3)) & *((_BYTE *)&Bitmap::ThisBit + ((v24 - v49) & 7))) != 0 )
        {
          v23 = a7;
          if ( a7 )
            *(DBORDINAL *)((char *)&a7->iOrdinal + v61) = 3;
          inserted = -2147217887;
          goto LABEL_60;
        }
        v24 = RecursionCount;
        v25 = v49;
      }
      if ( v24 - v25 >= Size )
      {
        if ( DynaBitmap::Grow((DynaBitmap *)&v47, v24) < 0 )
        {
LABEL_59:
          v23 = a7;
LABEL_60:
          v22 = v60;
          goto LABEL_61;
        }
        v24 = RecursionCount;
        v25 = v49;
      }
      *((_BYTE *)v47 + ((v24 - v25) >> 3)) |= *((_BYTE *)&Bitmap::ThisBit + ((v24 - v25) & 7));
      goto LABEL_59;
    }
LABEL_61:
    v26 = *(DBPART *)((char *)&Src->dwPart + v22);
    if ( (v26 & 7) == 0 || (v26 & 0xFFFFFFF8) != 0 )
    {
      if ( v23 )
      {
        v27 = v60;
        *(DBORDINAL *)((char *)&v23->iOrdinal + v61) = 3;
        v26 = *(DBPART *)((char *)&Src->dwPart + v27);
      }
      inserted = -2147217887;
    }
    if ( (v26 & 1) != 0 && !Src[v60 / 0x34].wType )
    {
      if ( v23 )
        *(DBORDINAL *)((char *)&v23->iOrdinal + v61) = 3;
      inserted = -2147217887;
    }
    if ( (Src[i].dwPart & 1) != 0 )
    {
      wType = Src[v60 / 0x34].wType;
      if ( (_WORD)wType == 0x4000
        || (_WORD)wType == 16385
        || wType == 1
        || (_WORD)wType == 0xC000
        || (wType & 0x6000) == 0x6000
        || (wType & 0x3000) == 0x3000
        || (wType & 0x5000) == 0x5000 )
      {
        if ( v23 )
          *(DBORDINAL *)((char *)&v23->iOrdinal + v61) = 3;
        inserted = -2147217887;
      }
    }
    v29 = v60;
    if ( Block && Src[v60 / 0x34].eParamIO != 1 )
    {
      if ( v23 )
        *(DBORDINAL *)((char *)&v23->iOrdinal + v61) = 3;
      inserted = -2147217887;
    }
    if ( *(DBMEMOWNER *)((char *)&Src->dwMemOwner + v29) )
    {
      if ( v23 )
        *(DBORDINAL *)((char *)&v23->iOrdinal + v61) = 3;
      inserted = -2147217887;
    }
    v20 = a7;
    if ( *(DBTYPE *)((char *)&Src->wType + v29) == 13 )
    {
      v20 = a7;
      if ( !*(DBOBJECT **)((char *)&Src->pObject + v29) )
      {
        if ( a7 )
          *(DBORDINAL *)((char *)&a7->iOrdinal + v61) = 3;
        inserted = -2147217887;
      }
    }
    v19 = a3;
  }
  v8 = lpCriticalSection;
  if ( inserted == -2147217887 )
    goto LABEL_131;
  v18 = v58;
LABEL_99:
  if ( ((int)this->LockSemaphore & 2) == 0 )
  {
LABEL_104:
    Size = 52 * a3;
    v31 = 52 * a3 + 40;
    if ( !a3 )
      v31 = 92;
    Block = operator new(v31);
    if ( !Block )
    {
LABEL_107:
      inserted = -2147024882;
      goto LABEL_131;
    }
    inserted = CExtBuffer::InsertIntoExtBuffer((CExtBuffer *)&RecursionCount, v45, v46);
    if ( inserted < 0 )
    {
      operator delete(Block);
      goto LABEL_131;
    }
    v32 = Block;
    v33 = a3;
    *(_DWORD *)Block = v58;
    v32[2] = v57;
    v32[3] = v55;
    v32[4] = a2;
    v32[1] = 0;
    v32[5] = 1;
    v32[9] = a3;
    v32[6] = 0;
    v32[7] = a5;
    if ( a3 )
    {
      memcpy(v32 + 10, Src, Size);
      v33 = a3;
    }
    if ( v57 == 3 && v33 )
    {
      v34 = operator new(saturated_mul(4u, v33));
      v32[8] = v34;
      if ( !v34 )
      {
        inserted = -2147024882;
        goto LABEL_131;
      }
      v33 = a3;
      v35 = 0;
      if ( a3 )
      {
        do
        {
          v36 = v32[8];
          v32 = Block;
          *(_DWORD *)(v36 + 4 * v35) = Src[v35].iOrdinal;
          ++v35;
        }
        while ( v35 < a3 );
        v37 = 0;
        v55 = 0;
        goto LABEL_121;
      }
    }
    else
    {
      v32[8] = 0;
    }
    v37 = 0;
    v55 = 0;
    if ( !v33 )
    {
LABEL_128:
      inserted = 0;
      *a6 = RecursionCount;
      goto LABEL_134;
    }
LABEL_121:
    v38 = Src;
    do
    {
      v39 = 52 * v37;
      Size = 52 * v37;
      v8 = lpCriticalSection;
      if ( v38[v37].wType == 13 && v38[v39 / 0x34u].pObject )
      {
        v40 = operator new(0x14u);
        v41 = Size;
        *(_DWORD *)((char *)v32 + Size + 60) = v40;
        if ( !v40 )
          goto LABEL_107;
        v38 = Src;
        v42 = *(int *)((char *)&Src->pObject + v41);
        *(_OWORD *)v40 = *(_OWORD *)v42;
        v40[4] = *(_DWORD *)(v42 + 16);
        v37 = v55;
      }
      else
      {
        v32[v39 / 4u + 15] = 0;
      }
      v55 = ++v37;
    }
    while ( v37 < a3 );
    goto LABEL_128;
  }
  inserted = CImpIAccessor::ValidateAccessor(
               v18,
               v19,
               (unsigned int)Src,
               (unsigned int)v18,
               a7,
               (int *)&Size,
               (unsigned int *const)v18,
               (int *)v45,
               (unsigned int)v46);
  if ( inserted >= 0 )
  {
    v30 = v57;
    if ( Size )
      v30 = 2;
    v57 = v30;
    goto LABEL_104;
  }
LABEL_131:
  if ( inserted != -2147024882 )
  {
    v43 = *(_DWORD *)(this->RecursionCount + 4 * ((int)this->LockSemaphore & 1) + 52);
    if ( !JetGetDatabaseInfo(*(_DWORD *)(v43 + 16), *(_DWORD *)(v43 + 20), &Size, 4, 3) )
      CExtError::SendHRtoOLEAuto(inserted, (__int128 *)&IID_IAccessor, 0, v45, (int)v46);
  }
LABEL_134:
  if ( v8 )
    LeaveCriticalSection(v8);
  if ( v47 != &v51 )
    operator delete(v47);
  return inserted;
}

```

## disassembly

```asm
0x1000c0d0  mov     edi, edi
0x1000c0d2  push    ebp
0x1000c0d3  mov     ebp, esp
0x1000c0d5  push    0FFFFFFFFh
0x1000c0d7  push    offset ?CreateAccessor@CImpIAccessor@@UAGJKKQBUtagDBBINDING@@KPAKQAK@Z_SEH
0x1000c0dc  mov     eax, large fs:0
0x1000c0e2  push    eax
0x1000c0e3  sub     esp, 3Ch
0x1000c0e6  push    esi
0x1000c0e7  push    edi; int
0x1000c0e8  mov     eax, ___security_cookie
0x1000c0ed  xor     eax, ebp
0x1000c0ef  push    eax; struct _GUID *
0x1000c0f0  lea     eax, [ebp+var_C]
0x1000c0f3  mov     large fs:0, eax
0x1000c0f9  xor     edi, edi
0x1000c0fb  mov     [ebp+var_44], 1
0x1000c102  lea     eax, [ebp+var_38]
0x1000c105  mov     [ebp+var_40], edi
0x1000c108  mov     [ebp+var_48], eax
0x1000c10b  mov     [ebp+var_34], edi
0x1000c10e  mov     [ebp+var_3C], 1
0x1000c115  mov     [ebp+var_38], 0
0x1000c119  push    edi; perrinfo
0x1000c11a  push    edi; dwReserved
0x1000c11b  mov     [ebp+var_4], edi
0x1000c11e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000c124  mov     esi, [ebp+this]
0x1000c127  add     esi, 18h
0x1000c12a  push    esi; lpCriticalSection
0x1000c12b  mov     [ebp+lpCriticalSection], esi
0x1000c12e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000c134  mov     eax, [ebp+this]
0x1000c137  mov     byte ptr [ebp+var_4], 1
0x1000c13b  test    byte ptr [eax+10h], 1
0x1000c13f  jz      short loc_1000C1A3
0x1000c141  mov     eax, [eax+8]
0x1000c144  mov     [ebp+var_2C], eax
0x1000c147  mov     eax, [eax]
0x1000c149  mov     edi, [eax+14h]
0x1000c14c  mov     ecx, edi
0x1000c14e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000c154  mov     ecx, [ebp+var_2C]
0x1000c157  call    edi
0x1000c159  test    eax, eax
0x1000c15b  mov     eax, [ebp+this]
0x1000c15e  jz      short loc_1000C1A1
0x1000c160  mov     eax, [eax+8]
0x1000c163  mov     [ebp+var_2C], eax
0x1000c166  mov     eax, [eax]
0x1000c168  mov     edi, [eax+14h]
0x1000c16b  mov     ecx, edi
0x1000c16d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000c173  mov     ecx, [ebp+var_2C]
0x1000c176  call    edi
0x1000c178  cmp     dword ptr [eax+10h], 1
0x1000c17c  jnz     short loc_1000C18C
0x1000c17e  mov     ecx, [eax+8]; this
0x1000c181  test    ecx, ecx
0x1000c183  jz      short loc_1000C18C
0x1000c185  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1000c18a  jmp     short loc_1000C18F
0x1000c18c  mov     eax, [eax+0Ch]
0x1000c18f  cmp     eax, 1
0x1000c192  jnz     short loc_1000C19E
0x1000c194  mov     edi, 8000FFFFh
0x1000c199  jmp     loc_1000C6D7
0x1000c19e  mov     eax, [ebp+this]
0x1000c1a1  xor     edi, edi
0x1000c1a3  mov     ecx, [ebp+arg_14]
0x1000c1a6  test    ecx, ecx
0x1000c1a8  jnz     short loc_1000C1B4
0x1000c1aa  mov     edi, 80070057h
0x1000c1af  jmp     loc_1000C6D7
0x1000c1b4  mov     dword ptr [ecx], 0
0x1000c1ba  mov     ecx, [ebp+arg_8]
0x1000c1bd  test    ecx, ecx
0x1000c1bf  jz      short loc_1000C1D1
0x1000c1c1  cmp     [ebp+Src], 0
0x1000c1c5  jnz     short loc_1000C1D1
0x1000c1c7  mov     edi, 80070057h
0x1000c1cc  jmp     loc_1000C6D7
0x1000c1d1  mov     eax, [eax+10h]
0x1000c1d4  and     eax, 1
0x1000c1d7  mov     [ebp+var_2C], eax
0x1000c1da  jnz     short loc_1000C1EA
0x1000c1dc  test    ecx, ecx
0x1000c1de  jnz     short loc_1000C1EA
0x1000c1e0  mov     edi, 80040E49h
0x1000c1e5  jmp     loc_1000C6D7
0x1000c1ea  mov     ecx, [ebp+arg_4]
0x1000c1ed  test    ecx, ecx
0x1000c1ef  jz      loc_1000C6D2
0x1000c1f5  test    ecx, 0FFFFFFF0h
0x1000c1fb  jnz     loc_1000C6D2
0x1000c201  test    ecx, 0FFFFFFF9h
0x1000c207  jz      short loc_1000C212
0x1000c209  test    cl, 6
0x1000c20c  jz      loc_1000C6D2
0x1000c212  mov     edx, ecx
0x1000c214  and     ecx, 1
0x1000c217  and     edx, 2
0x1000c21a  jz      short loc_1000C252
0x1000c21c  test    ecx, ecx
0x1000c21e  jz      short loc_1000C232
0x1000c220  xor     ecx, 1
0x1000c223  mov     [ebp+var_1C], 2
0x1000c22a  lea     esi, [ecx+2]
0x1000c22d  mov     [ebp+var_20], esi
0x1000c230  jmp     short loc_1000C263
0x1000c232  mov     al, byte ptr [ebp+arg_4]
0x1000c235  and     al, 8
0x1000c237  movzx   eax, al
0x1000c23a  neg     eax
0x1000c23c  sbb     eax, eax
0x1000c23e  add     eax, 4
0x1000c241  xor     ecx, 1
0x1000c244  mov     [ebp+var_1C], eax
0x1000c247  mov     eax, [ebp+var_2C]
0x1000c24a  lea     esi, [ecx+2]
0x1000c24d  mov     [ebp+var_20], esi
0x1000c250  jmp     short loc_1000C263
0x1000c252  mov     [ebp+var_1C], 1
0x1000c259  xor     ecx, 1
0x1000c25c  mov     [ebp+var_20], 1
0x1000c263  mov     esi, [ebp+arg_4]
0x1000c266  mov     [ebp+Block], esi
0x1000c269  and     [ebp+Block], 4
0x1000c26d  jz      short loc_1000C277
0x1000c26f  lea     edx, [ecx+2]
0x1000c272  mov     [ebp+var_28], edx
0x1000c275  jmp     short loc_1000C289
0x1000c277  mov     ecx, [ebp+Size]
0x1000c27a  test    edx, edx
0x1000c27c  mov     esi, 1
0x1000c281  cmovnz  ecx, esi
0x1000c284  mov     [ebp+var_28], ecx
0x1000c287  mov     edx, ecx
0x1000c289  mov     ecx, [ebp+var_1C]
0x1000c28c  mov     esi, [ebp+lpCriticalSection]
0x1000c28f  cmp     ecx, 2
0x1000c292  jz      loc_1000C6CB
0x1000c298  cmp     edx, 2
0x1000c29b  jz      loc_1000C6CB
0x1000c2a1  test    eax, eax
0x1000c2a3  jz      short loc_1000C2AF
0x1000c2a5  cmp     [ebp+Block], 0
0x1000c2a9  jnz     loc_1000C6D2
0x1000c2af  mov     eax, [ebp+arg_8]
0x1000c2b2  test    eax, eax
0x1000c2b4  jz      loc_1000C508
0x1000c2ba  mov     ecx, [ebp+arg_18]
0x1000c2bd  xor     esi, esi
0x1000c2bf  nop
0x1000c2c0  lea     edx, ds:0[esi*4]
0x1000c2c7  mov     [ebp+var_10], edx
0x1000c2ca  test    ecx, ecx
0x1000c2cc  jz      short loc_1000C2D7
0x1000c2ce  mov     dword ptr [ecx+edx], 0
0x1000c2d5  jmp     short loc_1000C2DA
0x1000c2d7  mov     [ebp+var_10], edx
0x1000c2da  mov     ecx, [ebp+Src]
0x1000c2dd  imul    eax, esi, 34h ; '4'
0x1000c2e0  mov     [ebp+var_14], eax
0x1000c2e3  cmp     dword ptr [ecx+eax], 0
0x1000c2e7  mov     ecx, [ebp+arg_18]
0x1000c2ea  jnz     short loc_1000C308
0x1000c2ec  cmp     [ebp+Block], 0
0x1000c2f0  jz      loc_1000C3AC
0x1000c2f6  test    ecx, ecx
0x1000c2f8  jz      short loc_1000C301
0x1000c2fa  mov     dword ptr [ecx+edx], 1
0x1000c301  mov     edi, 80040E21h
0x1000c306  jmp     short loc_1000C312
0x1000c308  cmp     [ebp+Block], 0
0x1000c30c  jz      loc_1000C3AC
0x1000c312  mov     ecx, [ebp+Src]
0x1000c315  test    byte ptr [ecx+eax+24h], 1
0x1000c31a  mov     ecx, [ebp+arg_18]
0x1000c31d  jz      loc_1000C3AC
0x1000c323  mov     ecx, [ebp+Src]
0x1000c326  mov     edx, [eax+ecx]
0x1000c329  mov     eax, [ebp+var_44]
0x1000c32c  mov     ecx, [ebp+var_40]
0x1000c32f  shl     eax, 3
0x1000c332  mov     [ebp+Size], eax
0x1000c335  dec     eax
0x1000c336  add     eax, ecx
0x1000c338  mov     [ebp+var_2C], edx
0x1000c33b  cmp     edx, eax
0x1000c33d  jnb     short loc_1000C375
0x1000c33f  mov     eax, [ebp+var_48]
0x1000c342  sub     edx, ecx
0x1000c344  mov     ecx, edx
0x1000c346  and     edx, 7
0x1000c349  shr     ecx, 3
0x1000c34c  mov     al, [ecx+eax]
0x1000c34f  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1000c355  jz      short loc_1000C36F
0x1000c357  mov     ecx, [ebp+arg_18]
0x1000c35a  test    ecx, ecx
0x1000c35c  jz      short loc_1000C368
0x1000c35e  mov     edx, [ebp+var_10]
0x1000c361  mov     dword ptr [ecx+edx], 3
0x1000c368  mov     edi, 80040E21h
0x1000c36d  jmp     short loc_1000C3A9
0x1000c36f  mov     edx, [ebp+var_2C]
0x1000c372  mov     ecx, [ebp+var_40]
0x1000c375  mov     eax, edx
0x1000c377  sub     eax, ecx
0x1000c379  cmp     eax, [ebp+Size]
0x1000c37c  jb      short loc_1000C391
0x1000c37e  push    edx; unsigned int
0x1000c37f  lea     ecx, [ebp+var_48]; this
0x1000c382  call    ?Grow@DynaBitmap@@AAEJK@Z; DynaBitmap::Grow(ulong)
0x1000c387  test    eax, eax
0x1000c389  js      short loc_1000C3A6
0x1000c38b  mov     edx, [ebp+var_2C]
0x1000c38e  mov     ecx, [ebp+var_40]
0x1000c391  sub     edx, ecx
0x1000c393  mov     ecx, edx
0x1000c395  and     edx, 7
0x1000c398  shr     ecx, 3
0x1000c39b  add     ecx, [ebp+var_48]
0x1000c39e  mov     al, ds:?ThisBit@Bitmap@@1QBEB[edx]; uchar const * const Bitmap::ThisBit
0x1000c3a4  or      [ecx], al
0x1000c3a6  mov     ecx, [ebp+arg_18]
0x1000c3a9  mov     eax, [ebp+var_14]
0x1000c3ac  mov     edx, [ebp+Src]
0x1000c3af  mov     eax, [edx+eax+1Ch]
0x1000c3b3  mov     edx, [ebp+var_10]
0x1000c3b6  test    al, 7
0x1000c3b8  jz      short loc_1000C3C1
0x1000c3ba  test    eax, 0FFFFFFF8h
0x1000c3bf  jz      short loc_1000C3DB
0x1000c3c1  test    ecx, ecx
0x1000c3c3  jz      short loc_1000C3D6
0x1000c3c5  mov     eax, [ebp+var_14]
0x1000c3c8  mov     edi, [ebp+Src]
0x1000c3cb  mov     dword ptr [ecx+edx], 3
0x1000c3d2  mov     eax, [edi+eax+1Ch]
0x1000c3d6  mov     edi, 80040E21h
0x1000c3db  test    al, 1
0x1000c3dd  jz      short loc_1000C400
0x1000c3df  mov     edx, [ebp+Src]
0x1000c3e2  mov     eax, [ebp+var_14]
0x1000c3e5  cmp     word ptr [edx+eax+30h], 0
0x1000c3eb  mov     edx, [ebp+var_10]
0x1000c3ee  jnz     short loc_1000C400
0x1000c3f0  test    ecx, ecx
0x1000c3f2  jz      short loc_1000C3FB
0x1000c3f4  mov     dword ptr [ecx+edx], 3
0x1000c3fb  mov     edi, 80040E21h
0x1000c400  mov     edx, [ebp+Src]
0x1000c403  imul    eax, esi, 34h ; '4'
0x1000c406  test    byte ptr [eax+edx+1Ch], 1
0x1000c40b  jz      short loc_1000C475
0x1000c40d  mov     eax, [ebp+var_14]
0x1000c410  movzx   edx, word ptr [edx+eax+30h]
0x1000c415  mov     eax, 4000h
0x1000c41a  cmp     dx, ax
0x1000c41d  jz      short loc_1000C462
0x1000c41f  mov     eax, 4001h
0x1000c424  cmp     dx, ax
0x1000c427  jz      short loc_1000C462
0x1000c429  cmp     edx, 1
0x1000c42c  jz      short loc_1000C462
0x1000c42e  mov     eax, 0C000h
0x1000c433  cmp     dx, ax
0x1000c436  jz      short loc_1000C462
0x1000c438  mov     eax, edx
0x1000c43a  and     eax, 6000h
0x1000c43f  cmp     eax, 6000h
0x1000c444  jz      short loc_1000C462
0x1000c446  mov     eax, edx
0x1000c448  and     eax, 3000h
0x1000c44d  cmp     eax, 3000h
0x1000c452  jz      short loc_1000C462
0x1000c454  and     edx, 5000h
0x1000c45a  cmp     edx, 5000h
0x1000c460  jnz     short loc_1000C475
0x1000c462  test    ecx, ecx
0x1000c464  jz      short loc_1000C470
0x1000c466  mov     eax, [ebp+var_10]
0x1000c469  mov     dword ptr [ecx+eax], 3
0x1000c470  mov     edi, 80040E21h
0x1000c475  cmp     [ebp+Block], 0
0x1000c479  mov     edx, [ebp+var_14]
0x1000c47c  jz      short loc_1000C49B
0x1000c47e  mov     eax, [ebp+Src]
0x1000c481  cmp     dword ptr [eax+edx+24h], 1
0x1000c486  mov     eax, [ebp+var_10]
0x1000c489  jz      short loc_1000C49B
0x1000c48b  test    ecx, ecx
0x1000c48d  jz      short loc_1000C496
0x1000c48f  mov     dword ptr [ecx+eax], 3
0x1000c496  mov     edi, 80040E21h
0x1000c49b  mov     eax, [ebp+Src]
0x1000c49e  cmp     dword ptr [eax+edx+20h], 0
0x1000c4a3  mov     eax, [ebp+var_10]
  ... truncated ...
```
