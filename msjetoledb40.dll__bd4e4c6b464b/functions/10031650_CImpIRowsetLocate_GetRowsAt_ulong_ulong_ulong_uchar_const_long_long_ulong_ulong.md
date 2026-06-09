# CImpIRowsetLocate::GetRowsAt(ulong,ulong,ulong,uchar const *,long,long,ulong *,ulong * *)

- ea: `0x10031650`
- end: `0x10031ae3`
- name: `?GetRowsAt@CImpIRowsetLocate@@UAGJKKKPBEJJPAKPAPAK@Z`
- size: `1171`
- prototype: `int(CImpIRowsetLocate *__hidden this, unsigned int, unsigned int, unsigned int, const unsigned __int8 *, int, int, unsigned int *, unsigned int **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation`

## callees

- `0x1000ba50`
- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c5c0`
- `0x1001c6d0`
- `0x1001fb90`
- `0x10027a60`
- `0x1002c7d0`
- `0x1002da40`
- `0x10031650`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10031abd`
- `KERNEL32!LeaveCriticalSection` at `0x10031abd`
- `KERNEL32!EnterCriticalSection` at `0x10031726`
- `KERNEL32!EnterCriticalSection` at `0x10031726`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100316bb`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100316bb`
- `msjet40!__imp__JetGetBookmark@20` at `0x1003195c`
- `msjet40!__imp__JetGetBookmark@20` at `0x1003195c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10031a66`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10031a66`
- `msjet40!__imp__JetGotoBookmark@16` at `0x10031843`
- `msjet40!__imp__JetGotoBookmark@16` at `0x10031843`
- `msjet40!__imp__JetMove@16` at `0x100317c3`
- `msjet40!__imp__JetMove@16` at `0x100319c2`
- `msjet40!__imp__JetMove@16` at `0x100317c3`
- `msjet40!__imp__JetMove@16` at `0x100319c2`

## pseudocode

```c
int __stdcall CImpIRowsetLocate::GetRowsAt(
        CImpIRowsetLocate *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        int cRow,
        int a7,
        unsigned int *a8,
        unsigned int **a9)
{
  int inserted; // ebx
  JET_ERR Bookmark; // edi
  struct _RTL_CRITICAL_SECTION *v11; // esi
  int v12; // eax
  JET_SESID v13; // eax
  int v14; // ecx
  struct _RTL_CRITICAL_SECTION *v15; // edx
  _DWORD *LockSemaphore; // eax
  int isZombie; // eax
  int v18; // eax
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  CRowset **v26; // edi
  CRowset *v28; // [esp-Ch] [ebp-6Ch]
  int v29; // [esp-8h] [ebp-68h]
  struct _GUID *v30; // [esp+0h] [ebp-60h]
  struct _GUID *v31; // [esp+4h] [ebp-5Ch]
  unsigned int pcbActual; // [esp+10h] [ebp-50h] BYREF
  int v33; // [esp+14h] [ebp-4Ch]
  int v34; // [esp+18h] [ebp-48h]
  struct _RTL_CRITICAL_SECTION *v35; // [esp+1Ch] [ebp-44h]
  int v36; // [esp+20h] [ebp-40h]
  void *pvBookmark; // [esp+24h] [ebp-3Ch] BYREF
  BOOL v38; // [esp+28h] [ebp-38h]
  JET_SESID sesid; // [esp+2Ch] [ebp-34h]
  unsigned int *v40; // [esp+30h] [ebp-30h]
  CRowset **v41; // [esp+34h] [ebp-2Ch]
  _DWORD *v42; // [esp+38h] [ebp-28h]
  CImpIRowsetLocate *v43; // [esp+3Ch] [ebp-24h]
  JET_ERR v44; // [esp+40h] [ebp-20h]
  _DWORD v45[2]; // [esp+44h] [ebp-1Ch] BYREF
  int v46; // [esp+4Ch] [ebp-14h]
  int v47; // [esp+5Ch] [ebp-4h]

  inserted = 0;
  Bookmark = 0;
  v11 = 0;
  v43 = this;
  v42 = (_DWORD *)*((_DWORD *)this + 2);
  pvBookmark = a5;
  v12 = v42[14];
  v40 = a8;
  v41 = (CRowset **)a9;
  v38 = 0;
  v13 = *(_DWORD *)(v12 + 16);
  v44 = 0;
  v36 = 0;
  sesid = v13;
  v35 = 0;
  v47 = 0;
  SetErrorInfo(0, 0);
  if ( a8 )
    *v40 = 0;
  v15 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)v43 + 2);
  LockSemaphore = v15[2].LockSemaphore;
  if ( !LockSemaphore
    || (LockSemaphore[4] != 1 || (v14 = LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie((CTransactionState *)v14)),
        isZombie != 1) )
  {
    if ( v15[4].SpinCount || v15[9].SpinCount )
    {
      if ( ((int)v15[4].DebugInfo & 0x400) != 0 )
      {
        inserted = -2147217888;
        goto LABEL_69;
      }
      v11 = v15 + 3;
      v35 = v15 + 3;
      EnterCriticalSection(v15 + 3);
      if ( !a4 || (v14 = (int)pvBookmark) == 0 || !v40 || !v41 )
      {
        inserted = -2147024809;
        goto LABEL_69;
      }
      if ( a4 == 1 )
      {
        if ( *(_BYTE *)pvBookmark == 1 )
        {
          v18 = CRowset::Move(0x80000000, v42, v28, v29, 0, (int)v30, (int)v31);
          inserted = v18;
          if ( v18 < 0 )
            goto LABEL_69;
          v14 = v18 == 265926;
          v38 = v14;
          goto LABEL_22;
        }
        if ( *(_BYTE *)pvBookmark == 2 )
        {
          inserted = CRowset::Move(0x7FFFFFFF, v42, v28, v29, 0, (int)v30, (int)v31);
          if ( inserted < 0 )
            goto LABEL_69;
          v38 = inserted == 265926;
          goto LABEL_22;
        }
      }
      else if ( a4 == 4 )
      {
        v20 = JetGotoBookmark(sesid, *(_DWORD *)(*((_DWORD *)v43 + 2) + 108), pvBookmark, 4u);
        Bookmark = v20;
        v44 = v20;
        if ( v20 < 0 )
        {
          if ( v20 == -1045 || v20 == -1017 )
            inserted = -2147217906;
          else
            inserted = -2147467259;
          goto LABEL_65;
        }
LABEL_22:
        if ( cRow )
        {
          if ( cRow == 0x80000000 || cRow == 0x7FFFFFFF )
          {
            inserted = -2147217890;
            goto LABEL_64;
          }
          v19 = JetMove(sesid, *(_DWORD *)(*((_DWORD *)v43 + 2) + 108), cRow, 0);
          Bookmark = v19;
          v44 = v19;
          if ( v19 == -1603 )
          {
            inserted = -2147217890;
            goto LABEL_65;
          }
          if ( v19 < 0 )
          {
            inserted = -2147467259;
            goto LABEL_65;
          }
        }
        if ( !JoltProperties::IsbPropertySet((JoltProperties *)v42[41], 0xEEu)
          || (inserted = CRowset::SetAndFillFatCursor((CRowset *)v30), inserted >= 0) )
        {
          if ( !a7 )
          {
            inserted = 0;
            goto LABEL_64;
          }
          v14 = (int)v41;
          if ( !*v41 )
          {
            v21 = abs32(a7);
            if ( (v21 & 0xC0000000) != 0
              || (v22 = (*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          4 * v21),
                  v14 = (int)v41,
                  Bookmark = v44,
                  (*v41 = (CRowset *)v22) == 0) )
            {
              inserted = -2147024882;
              goto LABEL_64;
            }
            v36 = 1;
          }
          v14 = 0;
          v34 = 2 * (a7 > 0) - 1;
          while ( 1 )
          {
            v44 = v14;
            if ( inserted == 265946 )
              break;
            v45[1] = 0;
            v23 = *((_DWORD *)v43 + 2);
            v45[0] = -1;
            v46 = 0;
            Bookmark = JetGetBookmark(sesid, *(_DWORD *)(v23 + 108), v45, 4u, &pcbActual);
            if ( Bookmark == -1603 )
              goto LABEL_57;
            ++v46;
            inserted = CExtBuffer::InsertIntoExtBuffer((CExtBuffer *)&pvBookmark, v30, &v31->Data1);
            if ( inserted < 0 )
              goto LABEL_64;
            *((_DWORD *)*v41 + abs32(v44)) = pvBookmark;
            v24 = v34;
            ++*v40;
            v33 = v24 + v44;
            if ( v24 + v44 == a7 )
            {
              v14 = v24 + v44;
              break;
            }
            Bookmark = JetMove(sesid, *(_DWORD *)(*((_DWORD *)v43 + 2) + 108), v24, 0);
            if ( Bookmark == -1603 )
            {
LABEL_57:
              v14 = v44;
              inserted = 265926;
              break;
            }
            v14 = v33;
          }
          if ( *v40 == abs32(a7) )
          {
            v25 = 0;
            if ( inserted != 265926 )
              v25 = inserted;
            inserted = v25;
          }
          if ( v14 > 0 )
            CRowset::RowNotify(
              *v41,
              4u,
              (const unsigned int *const)4,
              (enum DBREASONENUM)v30,
              (enum DBEVENTPHASEENUM)v31);
        }
LABEL_64:
        if ( !Bookmark )
        {
          if ( inserted >= 0 )
            goto LABEL_72;
          goto LABEL_69;
        }
LABEL_65:
        CExtError::SendJetErrortoOLEAuto(inserted, *(char **)(v42[14] + 16), Bookmark, (int)&IID_IRowset, (int)v30, v31);
        goto LABEL_72;
      }
      inserted = -2147217906;
      goto LABEL_69;
    }
  }
  inserted = -2147418113;
LABEL_69:
  if ( inserted != -2147024882
    && !JetGetDatabaseInfo(*(_DWORD *)(v42[14] + 16), *(_DWORD *)(v42[14] + 20), &pcbActual, 4, 3) )
  {
    CExtError::SendHRtoOLEAuto((int)&IID_IRowsetLocate, 0, v30, (int)v31);
  }
LABEL_72:
  if ( v40 )
  {
    if ( !*v40 && v36 == 1 )
    {
      v26 = v41;
      if ( v41 )
      {
        if ( *v41 )
        {
          System::Free((void *)v14);
          *v26 = 0;
        }
      }
    }
  }
  if ( !inserted && v38 )
    inserted = 265926;
  if ( v11 )
    LeaveCriticalSection(v11);
  return inserted;
}

```

## disassembly

```asm
0x10031650  mov     edi, edi
0x10031652  push    ebp
0x10031653  mov     ebp, esp
0x10031655  push    0FFFFFFFFh
0x10031657  push    offset ?GetRowsAt@CImpIRowsetLocate@@UAGJKKKPBEJJPAKPAPAK@Z_SEH
0x1003165c  mov     eax, large fs:0
0x10031662  push    eax
0x10031663  sub     esp, 44h
0x10031666  mov     eax, ___security_cookie
0x1003166b  xor     eax, ebp
0x1003166d  mov     [ebp+var_10], eax
0x10031670  push    ebx
0x10031671  push    esi
0x10031672  push    edi; int
0x10031673  push    eax; struct _GUID *
0x10031674  lea     eax, [ebp+var_C]
0x10031677  mov     large fs:0, eax
0x1003167d  mov     eax, [ebp+this]
0x10031680  xor     ebx, ebx
0x10031682  mov     ecx, [ebp+arg_10]
0x10031685  xor     edi, edi
0x10031687  mov     edx, [ebp+arg_1C]
0x1003168a  xor     esi, esi
0x1003168c  mov     [ebp+var_24], eax
0x1003168f  mov     eax, [eax+8]
0x10031692  mov     [ebp+var_28], eax
0x10031695  mov     [ebp+pvBookmark], ecx
0x10031698  mov     ecx, [ebp+arg_20]
0x1003169b  mov     eax, [eax+38h]
0x1003169e  mov     [ebp+var_30], edx
0x100316a1  mov     [ebp+var_2C], ecx
0x100316a4  mov     [ebp+var_38], ebx
0x100316a7  mov     eax, [eax+10h]
0x100316aa  mov     [ebp+var_20], edi
0x100316ad  mov     [ebp+var_40], ebx
0x100316b0  mov     [ebp+sesid], eax
0x100316b3  mov     [ebp+var_44], esi
0x100316b6  push    esi; perrinfo
0x100316b7  push    esi; int
0x100316b8  mov     [ebp+var_4], esi
0x100316bb  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100316c1  mov     eax, [ebp+var_30]
0x100316c4  test    eax, eax
0x100316c6  jz      short loc_100316CA
0x100316c8  mov     [eax], esi
0x100316ca  mov     eax, [ebp+var_24]
0x100316cd  mov     edx, [eax+8]
0x100316d0  mov     eax, [edx+40h]
0x100316d3  test    eax, eax
0x100316d5  jz      short loc_100316F3
0x100316d7  cmp     dword ptr [eax+10h], 1
0x100316db  jnz     short loc_100316EB
0x100316dd  mov     ecx, [eax+8]; this
0x100316e0  test    ecx, ecx
0x100316e2  jz      short loc_100316EB
0x100316e4  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x100316e9  jmp     short loc_100316EE
0x100316eb  mov     eax, [eax+0Ch]
0x100316ee  cmp     eax, 1
0x100316f1  jz      short loc_10031702
0x100316f3  cmp     dword ptr [edx+74h], 0
0x100316f7  jnz     short loc_1003170C
0x100316f9  cmp     dword ptr [edx+0ECh], 0
0x10031700  jnz     short loc_1003170C
0x10031702  mov     ebx, 8000FFFFh
0x10031707  jmp     loc_10031A4A
0x1003170c  test    dword ptr [edx+60h], 400h
0x10031713  jz      short loc_1003171F
0x10031715  mov     ebx, 80040E20h
0x1003171a  jmp     loc_10031A4A
0x1003171f  lea     esi, [edx+48h]
0x10031722  push    esi; lpCriticalSection
0x10031723  mov     [ebp+var_44], esi
0x10031726  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003172c  mov     eax, [ebp+arg_C]
0x1003172f  test    eax, eax
0x10031731  jz      loc_10031A45
0x10031737  mov     ecx, [ebp+pvBookmark]
0x1003173a  test    ecx, ecx
0x1003173c  jz      loc_10031A45
0x10031742  cmp     [ebp+var_30], 0
0x10031746  jz      loc_10031A45
0x1003174c  cmp     [ebp+var_2C], 0
0x10031750  jz      loc_10031A45
0x10031756  cmp     eax, 1
0x10031759  jnz     loc_10031825
0x1003175f  mov     al, [ecx]
0x10031761  cmp     al, 1
0x10031763  jnz     loc_100317F2
0x10031769  mov     ecx, [ebp+var_28]
0x1003176c  mov     edx, 80000000h
0x10031771  push    0; unsigned int
0x10031773  sub     esp, 8
0x10031776  call    ?Move@CRowset@@IAGJJKHH@Z; CRowset::Move(long,ulong,int,int)
0x1003177b  mov     ebx, eax
0x1003177d  test    ebx, ebx
0x1003177f  js      loc_10031A4A
0x10031785  xor     ecx, ecx
0x10031787  cmp     ebx, 40EC6h
0x1003178d  setz    cl
0x10031790  mov     [ebp+var_38], ecx
0x10031793  mov     eax, [ebp+cRow]
0x10031796  test    eax, eax
0x10031798  jz      loc_1003188E
0x1003179e  cmp     eax, 80000000h
0x100317a3  jz      loc_10031884
0x100317a9  cmp     eax, 7FFFFFFFh
0x100317ae  jz      loc_10031884
0x100317b4  push    0; grbit
0x100317b6  push    eax; cRow
0x100317b7  mov     eax, [ebp+var_24]
0x100317ba  mov     eax, [eax+8]
0x100317bd  push    dword ptr [eax+6Ch]; tableid
0x100317c0  push    [ebp+sesid]; sesid
0x100317c3  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x100317c9  mov     edi, eax
0x100317cb  mov     [ebp+var_20], edi
0x100317ce  cmp     edi, 0FFFFF9BDh
0x100317d4  jz      loc_1003187A
0x100317da  test    edi, edi
0x100317dc  jz      loc_1003188E
0x100317e2  jns     loc_1003188E
0x100317e8  mov     ebx, 80004005h
0x100317ed  jmp     loc_10031A27
0x100317f2  cmp     al, 2
0x100317f4  jnz     short loc_1003182A
0x100317f6  mov     ecx, [ebp+var_28]
0x100317f9  mov     edx, 7FFFFFFFh
0x100317fe  push    0; unsigned int
0x10031800  sub     esp, 8
0x10031803  call    ?Move@CRowset@@IAGJJKHH@Z; CRowset::Move(long,ulong,int,int)
0x10031808  mov     ebx, eax
0x1003180a  test    ebx, ebx
0x1003180c  js      loc_10031A4A
0x10031812  xor     eax, eax
0x10031814  cmp     ebx, 40EC6h
0x1003181a  setz    al
0x1003181d  mov     [ebp+var_38], eax
0x10031820  jmp     loc_10031793
0x10031825  cmp     eax, 4
0x10031828  jz      short loc_10031834
0x1003182a  mov     ebx, 80040E0Eh
0x1003182f  jmp     loc_10031A4A
0x10031834  mov     eax, [ebp+var_24]
0x10031837  push    4; cbBookmark
0x10031839  push    ecx; pvBookmark
0x1003183a  mov     eax, [eax+8]
0x1003183d  push    dword ptr [eax+6Ch]; tableid
0x10031840  push    [ebp+sesid]; sesid
0x10031843  call    ds:__imp__JetGotoBookmark@16; JetGotoBookmark(x,x,x,x)
0x10031849  mov     edi, eax
0x1003184b  mov     [ebp+var_20], edi
0x1003184e  test    edi, edi
0x10031850  jns     loc_10031793
0x10031856  cmp     edi, 0FFFFFBEBh
0x1003185c  jz      short loc_10031870
0x1003185e  cmp     edi, 0FFFFFC07h
0x10031864  jz      short loc_10031870
0x10031866  mov     ebx, 80004005h
0x1003186b  jmp     loc_10031A27
0x10031870  mov     ebx, 80040E0Eh
0x10031875  jmp     loc_10031A27
0x1003187a  mov     ebx, 80040E1Eh
0x1003187f  jmp     loc_10031A27
0x10031884  mov     ebx, 80040E1Eh
0x10031889  jmp     loc_10031A23
0x1003188e  mov     eax, [ebp+var_28]
0x10031891  push    0EEh; unsigned int
0x10031896  mov     ecx, [eax+0A4h]; this
0x1003189c  call    ?IsbPropertySet@JoltProperties@@QBEHK@Z; JoltProperties::IsbPropertySet(ulong)
0x100318a1  test    eax, eax
0x100318a3  jz      short loc_100318B7
0x100318a5  mov     ecx, [ebp+var_28]
0x100318a8  call    ?SetAndFillFatCursor@CRowset@@IAGJXZ; CRowset::SetAndFillFatCursor(void)
0x100318ad  mov     ebx, eax
0x100318af  test    ebx, ebx
0x100318b1  js      loc_10031A23
0x100318b7  mov     eax, [ebp+arg_18]
0x100318ba  test    eax, eax
0x100318bc  jnz     short loc_100318C5
0x100318be  xor     ebx, ebx
0x100318c0  jmp     loc_10031A23
0x100318c5  mov     ecx, [ebp+var_2C]
0x100318c8  cmp     dword ptr [ecx], 0
0x100318cb  jnz     short loc_1003190E
0x100318cd  cdq
0x100318ce  xor     eax, edx
0x100318d0  sub     eax, edx
0x100318d2  test    eax, 0C0000000h
0x100318d7  jnz     loc_100319DA
0x100318dd  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x100318e3  shl     eax, 2
0x100318e6  push    eax
0x100318e7  push    ecx
0x100318e8  mov     edx, [ecx]
0x100318ea  mov     edi, [edx+0Ch]
0x100318ed  mov     ecx, edi
0x100318ef  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100318f5  call    edi
0x100318f7  mov     ecx, [ebp+var_2C]
0x100318fa  mov     edi, [ebp+var_20]
0x100318fd  mov     [ecx], eax
0x100318ff  test    eax, eax
0x10031901  jz      loc_100319DA
0x10031907  mov     [ebp+var_40], 1
0x1003190e  xor     eax, eax
0x10031910  cmp     [ebp+arg_18], eax
0x10031913  setnle  al
0x10031916  xor     ecx, ecx
0x10031918  lea     eax, ds:0FFFFFFFFh[eax*2]
0x1003191f  mov     [ebp+var_48], eax
0x10031922  mov     [ebp+var_20], ecx
0x10031925  cmp     ebx, 40EDAh
0x1003192b  jz      loc_100319ED
0x10031931  mov     ebx, [ebp+var_24]
0x10031934  lea     eax, [ebp+pcbActual]
0x10031937  push    eax; pcbActual
0x10031938  push    4; cbMax
0x1003193a  lea     eax, [ebp+var_1C]
0x1003193d  mov     [ebp+var_18], 0
0x10031944  push    eax; pvBookmark
0x10031945  mov     eax, [ebx+8]
0x10031948  mov     [ebp+var_1C], 0FFFFFFFFh
0x1003194f  mov     [ebp+var_14], 0
0x10031956  push    dword ptr [eax+6Ch]; tableid
0x10031959  push    [ebp+sesid]; sesid
0x1003195c  call    ds:__imp__JetGetBookmark@20; JetGetBookmark(x,x,x,x,x)
0x10031962  mov     edi, eax
0x10031964  cmp     edi, 0FFFFF9BDh
0x1003196a  jz      short loc_100319E5
0x1003196c  mov     eax, [ebx+8]
0x1003196f  lea     ecx, [ebp+pvBookmark]
0x10031972  inc     [ebp+var_14]
0x10031975  lea     edx, [ebp+var_1C]
0x10031978  push    ecx; this
0x10031979  mov     ecx, [eax+68h]
0x1003197c  call    ?InsertIntoExtBuffer@CExtBuffer@@QAGJPAXAAK@Z; CExtBuffer::InsertIntoExtBuffer(void *,ulong &)
0x10031981  mov     ebx, eax
0x10031983  test    ebx, ebx
0x10031985  js      loc_10031A23
0x1003198b  mov     eax, [ebp+var_20]
0x1003198e  mov     ecx, [ebp+var_2C]
0x10031991  cdq
0x10031992  xor     eax, edx
0x10031994  sub     eax, edx
0x10031996  mov     edx, [ecx]
0x10031998  mov     ecx, [ebp+pvBookmark]
0x1003199b  mov     [edx+eax*4], ecx
0x1003199e  mov     eax, [ebp+var_30]
0x100319a1  mov     ecx, [ebp+var_48]
0x100319a4  inc     dword ptr [eax]
0x100319a6  mov     eax, [ebp+var_20]
0x100319a9  add     eax, ecx
0x100319ab  mov     [ebp+var_4C], eax
0x100319ae  cmp     eax, [ebp+arg_18]
0x100319b1  jz      short loc_100319E1
0x100319b3  mov     eax, [ebp+var_24]
0x100319b6  push    0; grbit
0x100319b8  push    ecx; cRow
0x100319b9  mov     eax, [eax+8]
0x100319bc  push    dword ptr [eax+6Ch]; tableid
0x100319bf  push    [ebp+sesid]; sesid
0x100319c2  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x100319c8  mov     edi, eax
0x100319ca  cmp     edi, 0FFFFF9BDh
0x100319d0  jz      short loc_100319E5
0x100319d2  mov     ecx, [ebp+var_4C]
0x100319d5  jmp     loc_10031922
0x100319da  mov     ebx, 8007000Eh
0x100319df  jmp     short loc_10031A23
0x100319e1  mov     ecx, eax
0x100319e3  jmp     short loc_100319ED
0x100319e5  mov     ecx, [ebp+var_20]
0x100319e8  mov     ebx, 40EC6h
0x100319ed  mov     eax, [ebp+arg_18]
0x100319f0  cdq
0x100319f1  xor     eax, edx
0x100319f3  sub     eax, edx
0x100319f5  mov     edx, [ebp+var_30]
0x100319f8  cmp     [edx], eax
0x100319fa  jnz     short loc_10031A09
0x100319fc  xor     eax, eax
0x100319fe  cmp     ebx, 40EC6h
0x10031a04  cmovnz  eax, ebx
0x10031a07  mov     ebx, eax
0x10031a09  test    ecx, ecx
0x10031a0b  jle     short loc_10031A23
0x10031a0d  mov     eax, [ebp+var_2C]
0x10031a10  mov     edx, ecx
0x10031a12  push    4; unsigned int *
0x10031a14  push    4; unsigned int
0x10031a16  push    dword ptr [eax]; this
0x10031a18  mov     eax, [ebp+var_24]
0x10031a1b  mov     ecx, [eax+8]
0x10031a1e  call    ?RowNotify@CRowset@@QAGJKQBKW4DBREASONENUM@@W4DBEVENTPHASEENUM@@@Z; CRowset::RowNotify(ulong,ulong const * const,DBREASONENUM,DBEVENTPHASEENUM)
0x10031a23  test    edi, edi
0x10031a25  jz      short loc_10031A3F
0x10031a27  mov     eax, [ebp+var_28]
0x10031a2a  mov     edx, ebx
0x10031a2c  push    offset _IID_IRowset; int
  ... truncated ...
```
