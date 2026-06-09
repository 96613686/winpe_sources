# Cursor::UpdateRecord(Err &)

- ea: `0x1001c3d0`
- end: `0x1001c8ab`
- name: `?UpdateRecord@Cursor@@AAEXAAVErr@@@Z`
- size: `1243`
- prototype: `void __thiscall(Cursor *__hidden this, struct Err *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, installer_update`

## callers

- `0x1001aaa0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10010580`
- `0x10018ff0`
- `0x1001c3d0`
- `0x1001c8c0`
- `0x1001d350`
- `0x1001d640`
- `0x1001d9a0`
- `0x10023730`
- `0x10023830`
- `0x10024ee0`
- `0x10025030`
- `0x100250e0`
- `0x100251a0`
- `0x10025ee0`
- `0x100481d0`
- `0x10048670`
- `0x1005d1d0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
void __thiscall Cursor::UpdateRecord(Cursor *this, struct Err *a2)
{
  unsigned int v3; // eax
  struct Err *v4; // esi
  Database *v5; // ecx
  unsigned int v6; // edi
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  unsigned int v10; // edi
  Database *v11; // ecx
  unsigned int v12; // edi
  Database *v13; // ecx
  size_t v14; // esi
  size_t v15; // eax
  int v16; // edi
  bool v17; // zf
  int v18; // edi
  unsigned int v19; // eax
  unsigned int v20; // ecx
  int v21; // edx
  int v22; // eax
  int v23; // edx
  unsigned int inserted; // eax
  IAccMeth *v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // edx
  unsigned int v29; // eax
  void *v30; // [esp-Ch] [ebp-70h]
  struct Transaction *v31; // [esp-8h] [ebp-6Ch]
  struct Transaction *v32; // [esp-8h] [ebp-6Ch]
  struct Transaction *v33; // [esp-8h] [ebp-6Ch]
  int v34; // [esp+10h] [ebp-54h] BYREF
  void *Src; // [esp+14h] [ebp-50h] BYREF
  size_t Size; // [esp+18h] [ebp-4Ch]
  void *Block; // [esp+1Ch] [ebp-48h]
  void *v38; // [esp+20h] [ebp-44h]
  int v39; // [esp+24h] [ebp-40h] BYREF
  _WORD *v40; // [esp+28h] [ebp-3Ch]
  int v41; // [esp+34h] [ebp-30h] BYREF
  _WORD *v42; // [esp+38h] [ebp-2Ch]
  unsigned __int8 v43[4]; // [esp+44h] [ebp-20h] BYREF
  unsigned int v44; // [esp+48h] [ebp-1Ch]
  unsigned int v45; // [esp+4Ch] [ebp-18h]
  unsigned int v46; // [esp+50h] [ebp-14h]
  int v47; // [esp+60h] [ebp-4h]

  v39 = 0;
  v40 = 0;
  v47 = 1;
  v44 = 0;
  v45 = 0;
  v41 = 0;
  v42 = 0;
  v3 = (*(int (__thiscall **)(_DWORD, struct Err *))(**((_DWORD **)this + 8) + 12))(*((_DWORD *)this + 8), a2);
  v4 = a2;
  v31 = (struct Transaction *)*((_DWORD *)this + 10);
  v5 = (Database *)*((_DWORD *)v31 + 2);
  v46 = v3;
  *(_DWORD *)v43 = v3 >> 8;
  Database::ReadPageForUpdate(v5, (struct PageRef *)&v39, v3 >> 8, a2, v31, 0);
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    if ( *v40 == 265 )
      Err::SetError(a2, -1017, 265);
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      v6 = v46;
      v7 = DataPage::RecordAddress(&v39, v46, &Src) - 1;
      if ( v7 )
      {
        v9 = v7 - 1;
        if ( v9 )
        {
          if ( v9 == 1 )
            Err::SetError(a2, -1017, v8);
        }
        else
        {
          Err::SetError(a2, -1045, v8);
        }
      }
      else
      {
        v10 = *(_DWORD *)Src;
        v32 = (struct Transaction *)*((_DWORD *)this + 10);
        v45 = *(_DWORD *)Src >> 8;
        v11 = (Database *)*((_DWORD *)v32 + 2);
        v44 = v10;
        Database::ReadPageForUpdate(v11, (struct PageRef *)&v41, v45, a2, v32, 0);
        if ( (*(_BYTE *)a2 & 8) == 0 )
          DataPage::RecordAddress(&v41, v10, &Src);
        v6 = v46;
      }
      if ( (*(_BYTE *)a2 & 8) == 0 )
      {
        if ( *(_DWORD *)(*((_DWORD *)this + 13) + 40) )
        {
          v30 = Block;
          *((_DWORD *)this + 86) = 0;
          Cursor::DeleteFromIndexes(this, (unsigned __int8 *)Src, Size, (unsigned int)v30, v6, a2);
          if ( *((_DWORD *)this + 86) )
          {
            if ( (*(_BYTE *)a2 & 8) == 0 )
            {
              Database::ReadPageForUpdate(
                *(Database **)(*((_DWORD *)this + 10) + 8),
                (struct PageRef *)&v39,
                *(unsigned int *)v43,
                a2,
                *((struct Transaction **)this + 10),
                0);
              if ( (*(_BYTE *)a2 & 8) == 0 )
              {
                if ( DataPage::RecordAddress(&v39, v6, &Src) == 1 )
                {
                  v12 = *(_DWORD *)Src;
                  v33 = (struct Transaction *)*((_DWORD *)this + 10);
                  v45 = *(_DWORD *)Src >> 8;
                  v13 = (Database *)*((_DWORD *)v33 + 2);
                  v44 = v12;
                  Database::ReadPageForUpdate(v13, (struct PageRef *)&v41, v45, a2, v33, 0);
                  if ( (*(_BYTE *)a2 & 8) == 0 )
                    DataPage::RecordAddress(&v41, v12, &Src);
                }
                v14 = Size;
                v15 = 2012;
                v16 = *((_DWORD *)this + 13);
                if ( Size < 0x7DC )
                  v15 = Size;
                memcpy((void *)(v16 + 76), Src, v15);
                *(_DWORD *)(v16 + 4) = v14;
                v4 = a2;
              }
            }
          }
        }
      }
    }
  }
  if ( *((_DWORD *)this + 11) == 1 )
  {
    v17 = (*(_BYTE *)v4 & 8) == 0;
    if ( (*(_BYTE *)v4 & 8) != 0 )
      goto LABEL_28;
    Cursor::VerifyChecksum(this, v4);
  }
  v17 = (*(_BYTE *)v4 & 8) == 0;
LABEL_28:
  v18 = v39;
  if ( v17 )
  {
    v19 = DataPage::Replace(
            (DataPage *)&v39,
            v46,
            **((const unsigned __int8 ***)this + 13),
            *(_DWORD *)(*((_DWORD *)this + 13) + 4));
    v20 = v44;
    *(_DWORD *)v43 = v19;
    if ( v44 )
    {
      if ( v19 )
      {
        v21 = *((_DWORD *)this + 23);
        if ( v21 )
        {
          Database::UnlockPage(*(_DWORD *)(*((_DWORD *)this + 10) + 8), v21, v4, *((_DWORD *)this + 10), 0);
          v20 = v44;
          *((_DWORD *)this + 23) = 0;
        }
        DataPage::Delete((DataPage *)&v41, v20);
      }
      else
      {
        *(_DWORD *)v43 = DataPage::Replace(
                           (DataPage *)&v41,
                           v44,
                           **((const unsigned __int8 ***)this + 13),
                           *(_DWORD *)(*((_DWORD *)this + 13) + 4));
        if ( !*(_DWORD *)v43 )
          DataPage::Delete((DataPage *)&v41, v44);
      }
      if ( (unsigned __int16)(2 * (v42[4] + 5)) + (unsigned int)(unsigned __int16)v42[1] < 0x800 )
      {
        if ( DataPage::WillFit(&v41, *(_DWORD *)(*((_DWORD *)this + 13) + 4), v4) )
        {
          v34 = 1;
          LOBYTE(v47) = 3;
          AbstractSpacemap::AddPage(v45, &v34, (char *)this + 236);
          LOBYTE(v47) = 1;
          Err::~Err((Err *)&v34);
        }
      }
      else
      {
        v34 = 1;
        LOBYTE(v47) = 2;
        *v42 = 265;
        AbstractSpacemap::RemovePage(v45, &v34, (char *)this + 236);
        v22 = v34;
        if ( (v34 & 8) == 0 )
        {
          AbstractSpacemap::RemovePage(v45, &v34, (char *)this + 140);
          v22 = v34;
          if ( (v34 & 8) == 0 )
          {
            Transaction::FreePage(*(_DWORD *)(*((_DWORD *)this + 1) + 60), v45, 1, &v34);
            v22 = v34;
          }
        }
        LOBYTE(v47) = 1;
        if ( (v22 & 0xFFFFFFFE) != 0 )
        {
          if ( Block )
            operator delete[](Block);
          if ( v38 )
            operator delete[](v38);
        }
      }
      v23 = v41;
      *(_DWORD *)(v41 + 4 * *(_DWORD *)(v41 + 24) + 28) = *(_DWORD *)(v41 + 4 * *(_DWORD *)(v41 + 24) + 28) & 0xFFFFFF0F
                                                        | 0x50;
      *(_DWORD *)(v23 + 4 * *(_DWORD *)(v23 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v23 + 64);
      v19 = *(_DWORD *)v43;
    }
    if ( v19 )
    {
      v28 = *((_DWORD *)this + 13);
      if ( *(_DWORD *)(v28 + 40) )
      {
        v29 = 2012;
        if ( *(_DWORD *)v28 != v28 + 76 )
          v29 = 0;
        Cursor::InsertIntoIndexes(this, *(unsigned __int8 **)v28, *(_DWORD *)(v28 + 4), v29, v46, v4);
      }
    }
    else
    {
      inserted = Cursor::InsertRecord(this, 1, v46, v4);
      v17 = (*(_BYTE *)v4 & 8) == 0;
      *(_DWORD *)v43 = inserted;
      if ( v17 )
      {
        if ( *((_DWORD *)this + 11) == 2 )
        {
          v25 = (IAccMeth *)*((_DWORD *)this + 10);
          v44 = inserted >> 8;
          IAccMeth::LockPage(v25, inserted >> 8, v4, 0);
          if ( (*(_BYTE *)v4 & 8) == 0 )
          {
            v26 = *((_DWORD *)this + 23);
            if ( v26 )
              Database::UnlockPage(*(_DWORD *)(*((_DWORD *)this + 10) + 8), v26, v4, *((_DWORD *)this + 10), 0);
            *((_DWORD *)this + 23) = v44;
          }
          inserted = *(_DWORD *)v43;
        }
        *(_DWORD *)v43 = inserted;
        *(_DWORD *)v43 = DataPage::Replace((DataPage *)&v39, v46, v43, 4u);
        if ( *(_DWORD *)v43 )
          v40[(unsigned __int8)v46 + 5] = v40[(unsigned __int8)v46 + 5] & 0x3FFF | 0x4000;
        if ( DataPage::WillFit(&v39, *(_DWORD *)(*((_DWORD *)this + 13) + 4), v4) )
          AbstractSpacemap::AddPage(*(_DWORD *)v43 >> 8, v4, v27);
        if ( !*(_DWORD *)v43 )
          Err::SetError(v4, -1012, v27);
      }
    }
    *(_DWORD *)(v18 + 4 * *(_DWORD *)(v18 + 24) + 28) |= 8u;
    ++*(_DWORD *)(v18 + 64);
  }
  if ( v41 )
    --*(_WORD *)(v41 + 76);
  if ( v18 )
    --*(_WORD *)(v18 + 76);
}

```

## disassembly

```asm
0x1001c3d0  mov     edi, edi
0x1001c3d2  push    ebp
0x1001c3d3  mov     ebp, esp
0x1001c3d5  push    0FFFFFFFFh
0x1001c3d7  push    offset ?UpdateRecord@Cursor@@AAEXAAVErr@@@Z_SEH
0x1001c3dc  mov     eax, large fs:0
0x1001c3e2  push    eax
0x1001c3e3  sub     esp, 48h
0x1001c3e6  push    ebx
0x1001c3e7  push    esi
0x1001c3e8  push    edi
0x1001c3e9  mov     eax, ___security_cookie
0x1001c3ee  xor     eax, ebp
0x1001c3f0  push    eax; unsigned int
0x1001c3f1  lea     eax, [ebp+var_C]
0x1001c3f4  mov     large fs:0, eax
0x1001c3fa  mov     ebx, ecx
0x1001c3fc  mov     [ebp+var_40], 0
0x1001c403  mov     [ebp+var_3C], 0
0x1001c40a  mov     [ebp+var_4], 0
0x1001c411  mov     [ebp+var_1C], 0
0x1001c418  mov     [ebp+var_18], 0
0x1001c41f  mov     [ebp+var_30], 0
0x1001c426  mov     [ebp+var_2C], 0
0x1001c42d  push    [ebp+arg_0]; void *
0x1001c430  mov     byte ptr [ebp+var_4], 1
0x1001c434  mov     edi, [ebx+20h]
0x1001c437  mov     eax, [edi]
0x1001c439  mov     esi, [eax+0Ch]
0x1001c43c  mov     ecx, esi
0x1001c43e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001c444  mov     ecx, edi
0x1001c446  call    esi
0x1001c448  mov     edx, [ebx+28h]
0x1001c44b  mov     esi, [ebp+arg_0]
0x1001c44e  push    0; char
0x1001c450  push    edx; struct Transaction *
0x1001c451  mov     ecx, [edx+8]; this
0x1001c454  mov     [ebp+var_14], eax
0x1001c457  shr     eax, 8
0x1001c45a  push    esi; struct Err *
0x1001c45b  push    eax; unsigned int
0x1001c45c  mov     dword ptr [ebp+var_20], eax
0x1001c45f  lea     eax, [ebp+var_40]
0x1001c462  push    eax; struct PageRef *
0x1001c463  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001c468  test    byte ptr [esi], 8
0x1001c46b  mov     ecx, 109h
0x1001c470  jnz     loc_1001C5DB
0x1001c476  mov     eax, [ebp+var_3C]
0x1001c479  cmp     [eax], cx
0x1001c47c  jnz     short loc_1001C48B
0x1001c47e  push    ecx
0x1001c47f  push    0FFFFFC07h
0x1001c484  mov     ecx, esi
0x1001c486  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001c48b  test    byte ptr [esi], 8
0x1001c48e  jnz     loc_1001C5DB
0x1001c494  mov     edi, [ebp+var_14]
0x1001c497  lea     eax, [ebp+Src]
0x1001c49a  push    eax
0x1001c49b  push    edi
0x1001c49c  lea     ecx, [ebp+var_40]
0x1001c49f  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x1001c4a4  sub     eax, 1
0x1001c4a7  jz      short loc_1001C4D1
0x1001c4a9  sub     eax, 1
0x1001c4ac  jz      short loc_1001C4C2
0x1001c4ae  sub     eax, 1
0x1001c4b1  jnz     short loc_1001C50A
0x1001c4b3  push    ecx
0x1001c4b4  push    0FFFFFC07h
0x1001c4b9  mov     ecx, esi
0x1001c4bb  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001c4c0  jmp     short loc_1001C50A
0x1001c4c2  push    ecx
0x1001c4c3  push    0FFFFFBEBh
0x1001c4c8  mov     ecx, esi
0x1001c4ca  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001c4cf  jmp     short loc_1001C50A
0x1001c4d1  mov     eax, [ebp+Src]
0x1001c4d4  push    0; char
0x1001c4d6  mov     edi, [eax]
0x1001c4d8  mov     ecx, edi
0x1001c4da  mov     eax, [ebx+28h]
0x1001c4dd  push    eax; struct Transaction *
0x1001c4de  shr     ecx, 8
0x1001c4e1  push    esi; struct Err *
0x1001c4e2  push    ecx; unsigned int
0x1001c4e3  mov     [ebp+var_18], ecx
0x1001c4e6  lea     ecx, [ebp+var_30]
0x1001c4e9  push    ecx; struct PageRef *
0x1001c4ea  mov     ecx, [eax+8]; this
0x1001c4ed  mov     [ebp+var_1C], edi
0x1001c4f0  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001c4f5  test    byte ptr [esi], 8
0x1001c4f8  jnz     short loc_1001C507
0x1001c4fa  lea     eax, [ebp+Src]
0x1001c4fd  push    eax
0x1001c4fe  push    edi
0x1001c4ff  lea     ecx, [ebp+var_30]
0x1001c502  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x1001c507  mov     edi, [ebp+var_14]
0x1001c50a  test    byte ptr [esi], 8
0x1001c50d  jnz     loc_1001C5DB
0x1001c513  mov     eax, [ebx+34h]
0x1001c516  cmp     dword ptr [eax+28h], 0
0x1001c51a  jz      loc_1001C5DB
0x1001c520  push    esi; struct Err *
0x1001c521  push    edi; unsigned int
0x1001c522  push    [ebp+Block]; unsigned int
0x1001c525  mov     ecx, ebx; this
0x1001c527  mov     dword ptr [ebx+158h], 0
0x1001c531  push    [ebp+Size]; unsigned int
0x1001c534  push    [ebp+Src]; unsigned __int8 *
0x1001c537  call    ?DeleteFromIndexes@Cursor@@AAEXPAEIIKAAVErr@@@Z; Cursor::DeleteFromIndexes(uchar *,uint,uint,ulong,Err &)
0x1001c53c  cmp     dword ptr [ebx+158h], 0
0x1001c543  jz      loc_1001C5DB
0x1001c549  test    byte ptr [esi], 8
0x1001c54c  jnz     loc_1001C5DB
0x1001c552  mov     eax, [ebx+28h]
0x1001c555  lea     ecx, [ebp+var_40]
0x1001c558  push    0; char
0x1001c55a  push    eax; struct Transaction *
0x1001c55b  push    esi; struct Err *
0x1001c55c  push    dword ptr [ebp+var_20]; unsigned int
0x1001c55f  push    ecx; struct PageRef *
0x1001c560  mov     ecx, [eax+8]; this
0x1001c563  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001c568  test    byte ptr [esi], 8
0x1001c56b  jnz     short loc_1001C5DB
0x1001c56d  lea     eax, [ebp+Src]
0x1001c570  push    eax
0x1001c571  push    edi
0x1001c572  lea     ecx, [ebp+var_40]
0x1001c575  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x1001c57a  sub     eax, 1
0x1001c57d  jnz     short loc_1001C5B5
0x1001c57f  mov     eax, [ebp+Src]
0x1001c582  push    0; char
0x1001c584  mov     edi, [eax]
0x1001c586  mov     ecx, edi
0x1001c588  mov     eax, [ebx+28h]
0x1001c58b  push    eax; struct Transaction *
0x1001c58c  shr     ecx, 8
0x1001c58f  push    esi; struct Err *
0x1001c590  push    ecx; unsigned int
0x1001c591  mov     [ebp+var_18], ecx
0x1001c594  lea     ecx, [ebp+var_30]
0x1001c597  push    ecx; struct PageRef *
0x1001c598  mov     ecx, [eax+8]; this
0x1001c59b  mov     [ebp+var_1C], edi
0x1001c59e  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001c5a3  test    byte ptr [esi], 8
0x1001c5a6  jnz     short loc_1001C5B5
0x1001c5a8  lea     eax, [ebp+Src]
0x1001c5ab  push    eax
0x1001c5ac  push    edi
0x1001c5ad  lea     ecx, [ebp+var_30]
0x1001c5b0  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x1001c5b5  mov     esi, [ebp+Size]
0x1001c5b8  mov     eax, 7DCh
0x1001c5bd  mov     edi, [ebx+34h]
0x1001c5c0  cmp     esi, eax
0x1001c5c2  cmovb   eax, esi
0x1001c5c5  push    eax; Size
0x1001c5c6  push    [ebp+Src]; Src
0x1001c5c9  lea     eax, [edi+4Ch]
0x1001c5cc  push    eax; void *
0x1001c5cd  call    _memcpy
0x1001c5d2  mov     [edi+4], esi
0x1001c5d5  add     esp, 0Ch
0x1001c5d8  mov     esi, [ebp+arg_0]
0x1001c5db  cmp     dword ptr [ebx+2Ch], 1
0x1001c5df  jnz     short loc_1001C5EE
0x1001c5e1  test    byte ptr [esi], 8
0x1001c5e4  jnz     short loc_1001C5F1
0x1001c5e6  push    esi; struct Err *
0x1001c5e7  mov     ecx, ebx; this
0x1001c5e9  call    ?VerifyChecksum@Cursor@@AAEXAAVErr@@@Z; Cursor::VerifyChecksum(Err &)
0x1001c5ee  test    byte ptr [esi], 8
0x1001c5f1  mov     edi, [ebp+var_40]
0x1001c5f4  jnz     loc_1001C884
0x1001c5fa  mov     eax, [ebx+34h]
0x1001c5fd  lea     ecx, [ebp+var_40]; this
0x1001c600  push    dword ptr [eax+4]; unsigned int
0x1001c603  push    dword ptr [eax]; Src
0x1001c605  push    [ebp+var_14]; unsigned int
0x1001c608  call    ?Replace@DataPage@@QAEKKPBEI@Z; DataPage::Replace(ulong,uchar const *,uint)
0x1001c60d  mov     ecx, [ebp+var_1C]
0x1001c610  mov     dword ptr [ebp+var_20], eax
0x1001c613  test    ecx, ecx
0x1001c615  jz      loc_1001C776
0x1001c61b  test    eax, eax
0x1001c61d  jnz     short loc_1001C63C
0x1001c61f  mov     eax, [ebx+34h]
0x1001c622  push    dword ptr [eax+4]; unsigned int
0x1001c625  push    dword ptr [eax]; Src
0x1001c627  push    ecx; unsigned int
0x1001c628  lea     ecx, [ebp+var_30]; this
0x1001c62b  call    ?Replace@DataPage@@QAEKKPBEI@Z; DataPage::Replace(ulong,uchar const *,uint)
0x1001c630  mov     dword ptr [ebp+var_20], eax
0x1001c633  test    eax, eax
0x1001c635  jnz     short loc_1001C666
0x1001c637  push    [ebp+var_1C]
0x1001c63a  jmp     short loc_1001C65E
0x1001c63c  mov     edx, [ebx+5Ch]
0x1001c63f  test    edx, edx
0x1001c641  jz      short loc_1001C65D
0x1001c643  mov     eax, [ebx+28h]
0x1001c646  push    0
0x1001c648  push    eax
0x1001c649  push    esi
0x1001c64a  mov     ecx, [eax+8]
0x1001c64d  push    edx
0x1001c64e  call    ?UnlockPage@Database@@QAEXKAAVErr@@PAVTransaction@@W4UnlockType@@@Z; Database::UnlockPage(ulong,Err &,Transaction *,UnlockType)
0x1001c653  mov     ecx, [ebp+var_1C]
0x1001c656  mov     dword ptr [ebx+5Ch], 0
0x1001c65d  push    ecx; unsigned int
0x1001c65e  lea     ecx, [ebp+var_30]; this
0x1001c661  call    ?Delete@DataPage@@QAEXK@Z; DataPage::Delete(ulong)
0x1001c666  mov     edx, [ebp+var_2C]
0x1001c669  mov     ax, [edx+8]
0x1001c66d  movzx   ecx, word ptr [edx+2]
0x1001c671  add     ax, 5
0x1001c675  add     ax, ax
0x1001c678  movzx   eax, ax
0x1001c67b  add     ecx, eax
0x1001c67d  cmp     ecx, 800h
0x1001c683  jb      loc_1001C714
0x1001c689  mov     [ebp+var_54], 1
0x1001c690  mov     eax, 109h
0x1001c695  mov     byte ptr [ebp+var_4], 2
0x1001c699  lea     ecx, [ebx+0ECh]
0x1001c69f  mov     [edx], ax
0x1001c6a2  push    ecx
0x1001c6a3  lea     eax, [ebp+var_54]
0x1001c6a6  push    eax
0x1001c6a7  push    [ebp+var_18]
0x1001c6aa  call    ?RemovePage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::RemovePage(ulong,Err &,SMAssertAction)
0x1001c6af  mov     eax, [ebp+var_54]
0x1001c6b2  test    al, 8
0x1001c6b4  jnz     short loc_1001C6E7
0x1001c6b6  lea     ecx, [ebx+8Ch]
0x1001c6bc  push    ecx
0x1001c6bd  lea     eax, [ebp+var_54]
0x1001c6c0  push    eax
0x1001c6c1  push    [ebp+var_18]
0x1001c6c4  call    ?RemovePage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::RemovePage(ulong,Err &,SMAssertAction)
0x1001c6c9  mov     eax, [ebp+var_54]
0x1001c6cc  test    al, 8
0x1001c6ce  jnz     short loc_1001C6E7
0x1001c6d0  mov     eax, [ebx+4]
0x1001c6d3  lea     ecx, [ebp+var_54]
0x1001c6d6  push    ecx
0x1001c6d7  push    1
0x1001c6d9  push    [ebp+var_18]
0x1001c6dc  mov     ecx, [eax+3Ch]
0x1001c6df  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x1001c6e4  mov     eax, [ebp+var_54]
0x1001c6e7  mov     byte ptr [ebp+var_4], 1
0x1001c6eb  test    eax, 0FFFFFFFEh
0x1001c6f0  jz      short loc_1001C751
0x1001c6f2  mov     eax, [ebp+Block]
0x1001c6f5  test    eax, eax
0x1001c6f7  jz      short loc_1001C702
0x1001c6f9  push    eax; Block
0x1001c6fa  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001c6ff  add     esp, 4
0x1001c702  mov     eax, [ebp+var_44]
0x1001c705  test    eax, eax
0x1001c707  jz      short loc_1001C751
0x1001c709  push    eax; Block
0x1001c70a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001c70f  add     esp, 4
0x1001c712  jmp     short loc_1001C751
0x1001c714  mov     eax, [ebx+34h]
0x1001c717  lea     ecx, [ebp+var_30]
0x1001c71a  push    esi
0x1001c71b  push    dword ptr [eax+4]
0x1001c71e  call    ?WillFit@DataPage@@QBE?AW4DPBool@@IAAVErr@@@Z; DataPage::WillFit(uint,Err &)
0x1001c723  test    eax, eax
0x1001c725  jz      short loc_1001C751
0x1001c727  mov     [ebp+var_54], 1
0x1001c72e  lea     ecx, [ebx+0ECh]
0x1001c734  mov     byte ptr [ebp+var_4], 3
0x1001c738  push    ecx
0x1001c739  lea     eax, [ebp+var_54]
0x1001c73c  push    eax
0x1001c73d  push    [ebp+var_18]
0x1001c740  call    ?AddPage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::AddPage(ulong,Err &,SMAssertAction)
0x1001c745  lea     ecx, [ebp+var_54]; this
0x1001c748  mov     byte ptr [ebp+var_4], 1
0x1001c74c  call    ??1Err@@QAE@XZ; Err::~Err(void)
0x1001c751  mov     edx, [ebp+var_30]
0x1001c754  mov     eax, [edx+18h]
0x1001c757  lea     ecx, [edx+eax*4]
0x1001c75a  mov     eax, [ecx+1Ch]
0x1001c75d  and     eax, 0FFFFFF5Fh
0x1001c762  or      eax, 50h
  ... truncated ...
```
