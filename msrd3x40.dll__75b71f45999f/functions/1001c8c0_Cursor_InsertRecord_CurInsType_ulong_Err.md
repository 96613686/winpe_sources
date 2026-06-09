# Cursor::InsertRecord(CurInsType,ulong,Err &)

- ea: `0x1001c8c0`
- end: `0x1001ccb1`
- name: `?InsertRecord@Cursor@@AAEKW4CurInsType@@KAAVErr@@@Z`
- size: `1009`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1001aaa0`
- `0x1001b010`
- `0x1001c3d0`
- `0x1004d040`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x1000f890`
- `0x10010580`
- `0x1001c8c0`
- `0x1001d350`
- `0x10023730`
- `0x10024b00`
- `0x10024f60`
- `0x100251a0`
- `0x10025ee0`
- `0x10042d20`
- `0x100471e0`
- `0x100473e0`
- `0x10047a60`
- `0x100481d0`
- `0x10048980`
- `0x10048e90`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001cb0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001cb0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cb31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cb31`

## pseudocode

```c
unsigned int __thiscall Cursor::InsertRecord(int this, int a2, unsigned int a3, struct Err *a4)
{
  AbstractSpacemap *v4; // esi
  unsigned int Page; // edi
  int v6; // eax
  unsigned int v7; // eax
  void *v8; // eax
  int v9; // esi
  PageDesc *v10; // eax
  Cursor *v11; // esi
  int v12; // ecx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  _WORD *v16; // ecx
  int v17; // ecx
  __int16 v18; // ax
  unsigned int v19; // eax
  int v20; // edx
  int v21; // esi
  unsigned int v22; // ecx
  unsigned __int8 *v23; // edx
  unsigned __int8 *v24; // eax
  Cursor *v25; // esi
  int v26; // ecx
  unsigned int v28; // [esp-10h] [ebp-64h]
  const unsigned __int8 *v29; // [esp-8h] [ebp-5Ch]
  int v31; // [esp-4h] [ebp-58h]
  unsigned int v32; // [esp-4h] [ebp-58h]
  int v33[3]; // [esp+10h] [ebp-44h] BYREF
  void *Block; // [esp+1Ch] [ebp-38h]
  void *v35; // [esp+20h] [ebp-34h]
  int v36; // [esp+24h] [ebp-30h] BYREF
  int v37; // [esp+28h] [ebp-2Ch]
  int v38; // [esp+30h] [ebp-24h]
  struct Transaction *v39; // [esp+34h] [ebp-20h]
  int v40; // [esp+38h] [ebp-1Ch]
  AbstractSpacemap *v41; // [esp+3Ch] [ebp-18h]
  unsigned int v42; // [esp+40h] [ebp-14h]
  Cursor *v43; // [esp+44h] [ebp-10h]
  int v44; // [esp+50h] [ebp-4h]

  v43 = (Cursor *)this;
  v42 = 0;
  v36 = 0;
  v37 = 0;
  v4 = (AbstractSpacemap *)(this + 236);
  v44 = 0;
  v40 = 1;
  v41 = (AbstractSpacemap *)(this + 236);
  Page = AbstractSpacemap::FirstPage((AbstractSpacemap *)(this + 236), a4);
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_44;
  while ( 1 )
  {
    if ( !Page )
      goto LABEL_37;
    v33[0] = 1;
    LOBYTE(v44) = 1;
    Database::ReadPageForUpdate(
      *(Database **)(*((_DWORD *)v43 + 10) + 8),
      (struct PageRef *)&v36,
      Page,
      (struct Err *)v33,
      *((struct Transaction **)v43 + 10),
      32);
    if ( (v33[0] & 8) == 0 )
    {
      if ( *(_WORD *)v37 == 257 && DataPage::WillFit(&v36, *(_DWORD *)(*((_DWORD *)v43 + 13) + 4), a4) )
      {
        LOBYTE(v44) = 0;
        if ( (v33[0] & 0xFFFFFFFE) == 0 )
          goto LABEL_37;
        if ( Block )
          operator delete[](Block);
        v8 = v35;
        goto LABEL_35;
      }
      AbstractSpacemap::Setup(v4, 1, a4);
      if ( (*(_BYTE *)a4 & 8) == 0 && AbstractSpacemap::GetBitmap(v4, Page, 2, a4) == 1 )
      {
        if ( (*(_BYTE *)(((Page - *((_DWORD *)v4 + 6)) >> 3) + *((_DWORD *)v4 + 4))
            & *((_BYTE *)&Bitmap::ThisBit + ((Page - *((_DWORD *)v4 + 6)) & 7))) != 0 )
        {
          Bitmap::Clear((AbstractSpacemap *)((char *)v4 + 16), Page, a4);
          v4 = v41;
          AbstractSpacemap::UpdateBitmap(v41);
        }
        else
        {
          v4 = v41;
        }
      }
      v6 = *(_DWORD *)a4;
      if ( (*(_DWORD *)a4 & 8) != 0 )
        break;
    }
LABEL_20:
    v7 = AbstractSpacemap::NextPage(v4, Page, a4);
    LOBYTE(v44) = 0;
    Page = v7;
    if ( (v33[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v35 )
        operator delete[](v35);
    }
    if ( (*(_BYTE *)a4 & 8) != 0 )
      goto LABEL_37;
  }
  if ( (v6 & 1) == 0 && *((_DWORD *)a4 + 1) == -1102 )
  {
    if ( (v6 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)a4 + 3) )
        operator delete[](*((void **)a4 + 3));
      if ( *((_DWORD *)a4 + 4) )
        operator delete[](*((void **)a4 + 4));
    }
    *(_DWORD *)a4 = 1;
    goto LABEL_20;
  }
  LOBYTE(v44) = 0;
  if ( (v33[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    v8 = v35;
    if ( v35 )
    {
LABEL_35:
      if ( v8 )
        operator delete[](v8);
    }
  }
LABEL_37:
  if ( (*(_BYTE *)a4 & 8) == 0 && !Page )
  {
    Page = (*(int (__thiscall **)(_DWORD, char *, struct Err *))(**(_DWORD **)(*((_DWORD *)v43 + 1) + 16) + 4))(
             *(_DWORD *)(*((_DWORD *)v43 + 1) + 16),
             (char *)v43 + 140,
             a4);
    if ( (*(_BYTE *)a4 & 8) == 0 )
    {
      v39 = (struct Transaction *)*((_DWORD *)v43 + 10);
      v9 = *((_DWORD *)v39 + 2);
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 112));
      v10 = Database::FindOrCreate((Database *)v9, Page, a4);
      if ( (*(_BYTE *)a4 & 8) == 0 )
        PageDesc::DontReadPage(v10, (struct PageRef *)&v36, v39, a4);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 112));
      if ( (*(_BYTE *)a4 & 8) == 0 )
      {
        v11 = v43;
        v12 = v37;
        v31 = v37;
        v13 = *((_DWORD *)v43 + 3);
        v40 = 0;
        *(_DWORD *)(v37 + 4) = *(_DWORD *)(v13 + 40);
        *(_DWORD *)v12 = 133562625;
        *(_WORD *)(v12 + 8) = 0;
        v38 = 0;
        AbstractSpacemap::AddPage(Page, a4, v31);
        goto LABEL_45;
      }
    }
  }
LABEL_44:
  v11 = v43;
LABEL_45:
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_62;
  v14 = *((_DWORD *)v11 + 13);
  v32 = *(_DWORD *)(v14 + 4);
  v29 = *(const unsigned __int8 **)v14;
  if ( a2 == 1 )
  {
    v15 = DataPage::Insert((DataPage *)&v36, v29, v32);
    v42 = v15;
    if ( v15 )
    {
      v17 = v37 + 2 * (unsigned __int8)v15;
      v18 = *(_WORD *)(v17 + 10);
      v16 = (_WORD *)(v17 + 10);
      *v16 = v18 & 0x3FFF | 0x8000;
      v19 = v42;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  v19 = DataPage::Insert((DataPage *)&v36, v29, v32);
  v42 = v19;
LABEL_50:
  if ( v19 )
  {
    v20 = v36;
    *(_DWORD *)(v36 + 4 * *(_DWORD *)(v36 + 24) + 28) = *(_DWORD *)(v36 + 4 * *(_DWORD *)(v36 + 24) + 28) & 0xFFFFFF0F
                                                      | 0x20;
    *(_DWORD *)(v20 + 4 * *(_DWORD *)(v20 + 24) + 28) |= 8u;
    ++*(_DWORD *)(v20 + 64);
  }
  else
  {
LABEL_51:
    Err::SetError(a4, -1012, v16);
  }
  if ( (*(_BYTE *)a4 & 8) != 0 || a2 == 2 )
  {
LABEL_62:
    v25 = v43;
  }
  else
  {
    v21 = *((_DWORD *)v11 + 13);
    v22 = 2012;
    v23 = *(unsigned __int8 **)v21;
    v24 = (unsigned __int8 *)(v21 + 76);
    if ( a2 == 1 )
    {
      v39 = 0;
      if ( v23 != v24 )
        v22 = (unsigned int)v39;
    }
    else
    {
      a3 = v42;
      v39 = 0;
      if ( v23 != v24 )
        v22 = (unsigned int)v39;
    }
    v28 = *(_DWORD *)(v21 + 4);
    v25 = v43;
    Cursor::InsertIntoIndexes(v43, v23, v28, v22, a3, a4);
  }
  if ( (*(_BYTE *)a4 & 8) == 0 && !v40 && DataPage::WillFit(&v36, *(_DWORD *)(*((_DWORD *)v25 + 13) + 4), a4) )
    AbstractSpacemap::AddPage(Page, a4, v26);
  if ( v36 )
    --*(_WORD *)(v36 + 76);
  return v42;
}

```

## disassembly

```asm
0x1001c8c0  mov     edi, edi
0x1001c8c2  push    ebp
0x1001c8c3  mov     ebp, esp
0x1001c8c5  push    0FFFFFFFFh
0x1001c8c7  push    offset ?InsertRecord@Cursor@@AAEKW4CurInsType@@KAAVErr@@@Z_SEH
0x1001c8cc  mov     eax, large fs:0
0x1001c8d2  push    eax
0x1001c8d3  sub     esp, 38h
0x1001c8d6  push    ebx
0x1001c8d7  push    esi
0x1001c8d8  push    edi
0x1001c8d9  mov     eax, ___security_cookie
0x1001c8de  xor     eax, ebp
0x1001c8e0  push    eax
0x1001c8e1  lea     eax, [ebp+var_C]
0x1001c8e4  mov     large fs:0, eax
0x1001c8ea  mov     eax, ecx
0x1001c8ec  mov     [ebp+var_10], eax
0x1001c8ef  mov     [ebp+var_14], 0
0x1001c8f6  mov     [ebp+var_30], 0
0x1001c8fd  mov     [ebp+var_2C], 0
0x1001c904  mov     ebx, [ebp+arg_8]
0x1001c907  lea     esi, [eax+0ECh]
0x1001c90d  push    ebx; struct Err *
0x1001c90e  mov     ecx, esi; this
0x1001c910  mov     [ebp+var_4], 0
0x1001c917  mov     [ebp+var_1C], 1
0x1001c91e  mov     [ebp+var_18], esi
0x1001c921  call    ?FirstPage@AbstractSpacemap@@QAEKAAVErr@@@Z; AbstractSpacemap::FirstPage(Err &)
0x1001c926  test    byte ptr [ebx], 8
0x1001c929  mov     edi, eax
0x1001c92b  jnz     loc_1001CB71
0x1001c931  test    edi, edi
0x1001c933  jz      loc_1001CAC0
0x1001c939  mov     [ebp+var_44], 1
0x1001c940  mov     eax, [ebp+var_10]
0x1001c943  lea     ecx, [ebp+var_44]
0x1001c946  push    20h ; ' '; char
0x1001c948  mov     byte ptr [ebp+var_4], 1
0x1001c94c  mov     eax, [eax+28h]
0x1001c94f  push    eax; struct Transaction *
0x1001c950  push    ecx; struct Err *
0x1001c951  push    edi; unsigned int
0x1001c952  lea     ecx, [ebp+var_30]
0x1001c955  push    ecx; struct PageRef *
0x1001c956  mov     ecx, [eax+8]; this
0x1001c959  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001c95e  test    byte ptr [ebp+var_44], 8
0x1001c962  jnz     loc_1001CA2A
0x1001c968  mov     eax, [ebp+var_2C]
0x1001c96b  mov     ecx, 101h
0x1001c970  cmp     [eax], cx
0x1001c973  jnz     short loc_1001C98F
0x1001c975  mov     eax, [ebp+var_10]
0x1001c978  lea     ecx, [ebp+var_30]
0x1001c97b  push    ebx
0x1001c97c  mov     eax, [eax+34h]
0x1001c97f  push    dword ptr [eax+4]
0x1001c982  call    ?WillFit@DataPage@@QBE?AW4DPBool@@IAAVErr@@@Z; DataPage::WillFit(uint,Err &)
0x1001c987  test    eax, eax
0x1001c989  jnz     loc_1001CA6D
0x1001c98f  push    ebx
0x1001c990  push    1
0x1001c992  mov     ecx, esi
0x1001c994  call    ?Setup@AbstractSpacemap@@IAEXW4SetupType@1@AAVErr@@@Z; AbstractSpacemap::Setup(AbstractSpacemap::SetupType,Err &)
0x1001c999  test    byte ptr [ebx], 8
0x1001c99c  jnz     short loc_1001C9E2
0x1001c99e  push    ebx
0x1001c99f  push    2
0x1001c9a1  push    edi
0x1001c9a2  mov     ecx, esi
0x1001c9a4  call    ?GetBitmap@AbstractSpacemap@@IAE?AW4GBResult@1@KW4GBDirection@1@AAVErr@@@Z; AbstractSpacemap::GetBitmap(ulong,AbstractSpacemap::GBDirection,Err &)
0x1001c9a9  cmp     eax, 1
0x1001c9ac  jnz     short loc_1001C9E2
0x1001c9ae  mov     eax, [esi+10h]
0x1001c9b1  lea     ecx, [esi+10h]; this
0x1001c9b4  mov     esi, edi
0x1001c9b6  sub     esi, [ecx+8]
0x1001c9b9  mov     edx, esi
0x1001c9bb  and     esi, 7
0x1001c9be  shr     edx, 3
0x1001c9c1  mov     al, [edx+eax]
0x1001c9c4  test    ds:?ThisBit@Bitmap@@1QBEB[esi], al; uchar const * const Bitmap::ThisBit
0x1001c9ca  jz      short loc_1001C9DF
0x1001c9cc  push    ebx; struct Err *
0x1001c9cd  push    edi; unsigned int
0x1001c9ce  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x1001c9d3  mov     esi, [ebp+var_18]
0x1001c9d6  mov     ecx, esi; this
0x1001c9d8  call    ?UpdateBitmap@AbstractSpacemap@@IAEXXZ; AbstractSpacemap::UpdateBitmap(void)
0x1001c9dd  jmp     short loc_1001C9E2
0x1001c9df  mov     esi, [ebp+var_18]
0x1001c9e2  mov     eax, [ebx]
0x1001c9e4  test    al, 8
0x1001c9e6  jz      short loc_1001CA2A
0x1001c9e8  test    al, 1
0x1001c9ea  jnz     loc_1001CA8F
0x1001c9f0  cmp     dword ptr [ebx+4], 0FFFFFBB2h
0x1001c9f7  jnz     loc_1001CA8F
0x1001c9fd  test    eax, 0FFFFFFFEh
0x1001ca02  jz      short loc_1001CA24
0x1001ca04  mov     eax, [ebx+0Ch]
0x1001ca07  test    eax, eax
0x1001ca09  jz      short loc_1001CA14
0x1001ca0b  push    eax; Block
0x1001ca0c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ca11  add     esp, 4
0x1001ca14  mov     eax, [ebx+10h]
0x1001ca17  test    eax, eax
0x1001ca19  jz      short loc_1001CA24
0x1001ca1b  push    eax; Block
0x1001ca1c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ca21  add     esp, 4
0x1001ca24  mov     dword ptr [ebx], 1
0x1001ca2a  push    ebx; struct Err *
0x1001ca2b  push    edi; unsigned int
0x1001ca2c  mov     ecx, esi; this
0x1001ca2e  call    ?NextPage@AbstractSpacemap@@QAEKKAAVErr@@@Z; AbstractSpacemap::NextPage(ulong,Err &)
0x1001ca33  mov     byte ptr [ebp+var_4], 0
0x1001ca37  mov     edi, eax
0x1001ca39  test    [ebp+var_44], 0FFFFFFFEh
0x1001ca40  jz      short loc_1001CA62
0x1001ca42  mov     eax, [ebp+Block]
0x1001ca45  test    eax, eax
0x1001ca47  jz      short loc_1001CA52
0x1001ca49  push    eax; Block
0x1001ca4a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ca4f  add     esp, 4
0x1001ca52  mov     eax, [ebp+var_34]
0x1001ca55  test    eax, eax
0x1001ca57  jz      short loc_1001CA62
0x1001ca59  push    eax; Block
0x1001ca5a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ca5f  add     esp, 4
0x1001ca62  test    byte ptr [ebx], 8
0x1001ca65  jz      loc_1001C931
0x1001ca6b  jmp     short loc_1001CAC0
0x1001ca6d  mov     byte ptr [ebp+var_4], 0
0x1001ca71  test    [ebp+var_44], 0FFFFFFFEh
0x1001ca78  jz      short loc_1001CAC0
0x1001ca7a  mov     eax, [ebp+Block]
0x1001ca7d  test    eax, eax
0x1001ca7f  jz      short loc_1001CA8A
0x1001ca81  push    eax; Block
0x1001ca82  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ca87  add     esp, 4
0x1001ca8a  mov     eax, [ebp+var_34]
0x1001ca8d  jmp     short loc_1001CAB3
0x1001ca8f  mov     byte ptr [ebp+var_4], 0
0x1001ca93  test    [ebp+var_44], 0FFFFFFFEh
0x1001ca9a  jz      short loc_1001CAC0
0x1001ca9c  mov     eax, [ebp+Block]
0x1001ca9f  test    eax, eax
0x1001caa1  jz      short loc_1001CAAC
0x1001caa3  push    eax; Block
0x1001caa4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001caa9  add     esp, 4
0x1001caac  mov     eax, [ebp+var_34]
0x1001caaf  test    eax, eax
0x1001cab1  jz      short loc_1001CAC0
0x1001cab3  test    eax, eax
0x1001cab5  jz      short loc_1001CAC0
0x1001cab7  push    eax; Block
0x1001cab8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001cabd  add     esp, 4
0x1001cac0  test    byte ptr [ebx], 8
0x1001cac3  jnz     loc_1001CB71
0x1001cac9  test    edi, edi
0x1001cacb  jnz     loc_1001CB71
0x1001cad1  mov     ecx, [ebp+var_10]
0x1001cad4  push    ebx; unsigned int
0x1001cad5  mov     eax, [ecx+4]
0x1001cad8  mov     edi, [eax+10h]
0x1001cadb  mov     eax, [edi]
0x1001cadd  mov     esi, [eax+4]
0x1001cae0  lea     eax, [ecx+8Ch]
0x1001cae6  push    eax; void *
0x1001cae7  mov     ecx, esi
0x1001cae9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001caef  mov     ecx, edi
0x1001caf1  call    esi
0x1001caf3  test    byte ptr [ebx], 8
0x1001caf6  mov     edi, eax
0x1001caf8  jnz     short loc_1001CB71
0x1001cafa  mov     eax, [ebp+var_10]
0x1001cafd  mov     eax, [eax+28h]
0x1001cb00  mov     [ebp+var_20], eax
0x1001cb03  mov     esi, [eax+8]
0x1001cb06  lea     eax, [esi+70h]
0x1001cb09  push    eax; lpCriticalSection
0x1001cb0a  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001cb10  push    ebx; struct Err *
0x1001cb11  push    edi; unsigned int
0x1001cb12  mov     ecx, esi; this
0x1001cb14  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x1001cb19  test    byte ptr [ebx], 8
0x1001cb1c  jnz     short loc_1001CB2D
0x1001cb1e  push    ebx; struct Err *
0x1001cb1f  push    [ebp+var_20]; struct Transaction *
0x1001cb22  lea     ecx, [ebp+var_30]
0x1001cb25  push    ecx; struct PageRef *
0x1001cb26  mov     ecx, eax; this
0x1001cb28  call    ?DontReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@@Z; PageDesc::DontReadPage(PageRef &,Transaction *,Err &)
0x1001cb2d  lea     eax, [esi+70h]
0x1001cb30  push    eax; lpCriticalSection
0x1001cb31  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cb37  test    byte ptr [ebx], 8
0x1001cb3a  jnz     short loc_1001CB71
0x1001cb3c  mov     esi, [ebp+var_10]
0x1001cb3f  mov     ecx, [ebp+var_2C]
0x1001cb42  push    ecx
0x1001cb43  push    ebx
0x1001cb44  mov     eax, [esi+0Ch]
0x1001cb47  push    edi
0x1001cb48  mov     [ebp+var_1C], 0
0x1001cb4f  mov     eax, [eax+28h]
0x1001cb52  mov     [ecx+4], eax
0x1001cb55  xor     eax, eax
0x1001cb57  mov     dword ptr [ecx], 7F60101h
0x1001cb5d  mov     [ecx+8], ax
0x1001cb61  lea     ecx, [esi+8Ch]
0x1001cb67  mov     [ebp+var_24], eax
0x1001cb6a  call    ?AddPage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::AddPage(ulong,Err &,SMAssertAction)
0x1001cb6f  jmp     short loc_1001CB74
0x1001cb71  mov     esi, [ebp+var_10]
0x1001cb74  test    byte ptr [ebx], 8
0x1001cb77  mov     ecx, [ebp+arg_0]
0x1001cb7a  jnz     loc_1001CC63
0x1001cb80  mov     eax, [esi+34h]
0x1001cb83  cmp     ecx, 1
0x1001cb86  lea     ecx, [ebp+var_30]; this
0x1001cb89  push    dword ptr [eax+4]; unsigned int
0x1001cb8c  push    dword ptr [eax]; Src
0x1001cb8e  jnz     short loc_1001CBC4
0x1001cb90  call    ?Insert@DataPage@@QAEKPBEI@Z; DataPage::Insert(uchar const *,uint)
0x1001cb95  mov     [ebp+var_14], eax
0x1001cb98  test    eax, eax
0x1001cb9a  jz      short loc_1001CBD0
0x1001cb9c  mov     ecx, [ebp+var_2C]
0x1001cb9f  mov     edx, 3FFFh
0x1001cba4  movzx   eax, al
0x1001cba7  lea     ecx, [ecx+eax*2]
0x1001cbaa  mov     ax, [ecx+0Ah]
0x1001cbae  add     ecx, 0Ah
0x1001cbb1  and     ax, dx
0x1001cbb4  mov     edx, 8000h
0x1001cbb9  or      ax, dx
0x1001cbbc  mov     [ecx], ax
0x1001cbbf  mov     eax, [ebp+var_14]
0x1001cbc2  jmp     short loc_1001CBCC
0x1001cbc4  call    ?Insert@DataPage@@QAEKPBEI@Z; DataPage::Insert(uchar const *,uint)
0x1001cbc9  mov     [ebp+var_14], eax
0x1001cbcc  test    eax, eax
0x1001cbce  jnz     short loc_1001CBDF
0x1001cbd0  push    ecx
0x1001cbd1  push    0FFFFFC0Ch
0x1001cbd6  mov     ecx, ebx
0x1001cbd8  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001cbdd  jmp     short loc_1001CC01
0x1001cbdf  mov     edx, [ebp+var_30]
0x1001cbe2  mov     eax, [edx+18h]
0x1001cbe5  lea     ecx, [edx+eax*4]
0x1001cbe8  mov     eax, [ecx+1Ch]
0x1001cbeb  and     eax, 0FFFFFF2Fh
0x1001cbf0  or      eax, 20h
0x1001cbf3  mov     [ecx+1Ch], eax
0x1001cbf6  mov     eax, [edx+18h]
0x1001cbf9  or      dword ptr [edx+eax*4+1Ch], 8
0x1001cbfe  inc     dword ptr [edx+40h]
0x1001cc01  test    byte ptr [ebx], 8
0x1001cc04  mov     ecx, [ebp+arg_0]
0x1001cc07  jnz     short loc_1001CC63
0x1001cc09  cmp     ecx, 2
0x1001cc0c  jz      short loc_1001CC63
0x1001cc0e  mov     esi, [esi+34h]
0x1001cc11  cmp     ecx, 1
0x1001cc14  push    ebx; struct Err *
0x1001cc15  mov     ecx, 7DCh
0x1001cc1a  mov     edx, [esi]
0x1001cc1c  lea     eax, [esi+4Ch]
0x1001cc1f  jnz     short loc_1001CC42
0x1001cc21  push    [ebp+arg_4]; unsigned int
0x1001cc24  cmp     edx, eax
0x1001cc26  mov     [ebp+var_20], 0
0x1001cc2d  cmovnz  ecx, [ebp+var_20]
0x1001cc31  push    ecx; unsigned int
0x1001cc32  push    dword ptr [esi+4]; unsigned int
0x1001cc35  mov     esi, [ebp+var_10]
0x1001cc38  mov     ecx, esi; this
0x1001cc3a  push    edx; unsigned __int8 *
0x1001cc3b  call    ?InsertIntoIndexes@Cursor@@AAEXPAEIIKAAVErr@@@Z; Cursor::InsertIntoIndexes(uchar *,uint,uint,ulong,Err &)
0x1001cc40  jmp     short loc_1001CC66
0x1001cc42  push    [ebp+var_14]; unsigned int
0x1001cc45  cmp     edx, eax
0x1001cc47  mov     [ebp+var_20], 0
0x1001cc4e  cmovnz  ecx, [ebp+var_20]
0x1001cc52  push    ecx; unsigned int
0x1001cc53  push    dword ptr [esi+4]; unsigned int
0x1001cc56  mov     esi, [ebp+var_10]
0x1001cc59  mov     ecx, esi; this
  ... truncated ...
```
