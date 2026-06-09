# Table::CreatePhysicalIndex(Instance *,PhysicalIndex *,Err &)

- ea: `0x10058210`
- end: `0x10058ba7`
- name: `?CreatePhysicalIndex@Table@@AAEXPAVInstance@@PAVPhysicalIndex@@AAVErr@@@Z`
- size: `2455`
- prototype: `void __thiscall(Table *__hidden this, struct Instance *, struct PhysicalIndex *, struct Err *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10055260`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10010600`
- `0x100106b0`
- `0x10011f50`
- `0x10012d60`
- `0x10019240`
- `0x10019960`
- `0x10025e60`
- `0x10025ee0`
- `0x10038630`
- `0x10038650`
- `0x10039890`
- `0x100399c0`
- `0x10045310`
- `0x10045450`
- `0x10045580`
- `0x10045880`
- `0x10045920`
- `0x100461b0`
- `0x10046360`
- `0x10046400`
- `0x1004bd40`
- `0x10051800`
- `0x10058210`
- `0x1005d130`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005e804`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10058b3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10058b3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10058b44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10058b44`

## pseudocode

```c
void __userpurge Table::CreatePhysicalIndex(
        Table *this@<ecx>,
        int a2@<ebp>,
        struct Instance *a3,
        struct PhysicalIndex *a4,
        struct Err *a5)
{
  struct Err *v5; // edi
  struct PhysicalIndex *v6; // esi
  int v7; // eax
  unsigned int v8; // eax
  int v9; // edx
  int v10; // eax
  struct SortItem **SortItem; // eax
  Checksum *v12; // ecx
  struct Instance *v13; // esi
  int v14; // edi
  int v15; // eax
  int v16; // edi
  char v17; // al
  _WORD *v18; // esi
  struct SortItem **v19; // eax
  struct SortItem **v20; // esi
  unsigned __int8 *ByteAlloc; // eax
  struct SortItem **v22; // edx
  struct SortItem **DataSpace; // eax
  char v24; // al
  unsigned __int16 *v25; // edi
  int v26; // eax
  struct SortItem **v27; // esi
  int v28; // ecx
  char *v29; // ecx
  int *v30; // edx
  unsigned int v31; // esi
  bool v32; // cf
  unsigned __int8 v33; // al
  unsigned __int8 v34; // al
  unsigned __int8 v35; // al
  int v36; // eax
  struct PhysicalIndex *v37; // ecx
  struct PhysicalIndex *v38; // ecx
  int v39; // ecx
  int v40; // eax
  int v41; // eax
  int v42; // ecx
  struct SortItem **v43; // eax
  bool v44; // zf
  HANDLE ProcessHeap; // eax
  void *v46; // [esp-928h] [ebp-934h]
  int v47; // [esp-914h] [ebp-920h]
  int v48; // [esp-910h] [ebp-91Ch]
  int v49; // [esp-90Ch] [ebp-918h] BYREF
  int v50; // [esp-908h] [ebp-914h]
  Table *v51; // [esp-904h] [ebp-910h]
  int v52; // [esp-900h] [ebp-90Ch] BYREF
  struct Instance *v53; // [esp-8FCh] [ebp-908h]
  int v54; // [esp-8F8h] [ebp-904h]
  int v55; // [esp-8F4h] [ebp-900h]
  int v56; // [esp-8F0h] [ebp-8FCh]
  int v57; // [esp-8ECh] [ebp-8F8h]
  int v58; // [esp-8E8h] [ebp-8F4h] BYREF
  char *v59; // [esp-8E4h] [ebp-8F0h]
  struct SortItem *v60; // [esp-8E0h] [ebp-8ECh]
  struct SortItem *v61; // [esp-8DCh] [ebp-8E8h]
  int v62; // [esp-8D8h] [ebp-8E4h]
  struct Instance *v63; // [esp-8D4h] [ebp-8E0h]
  struct SortItem **v64; // [esp-8D0h] [ebp-8DCh]
  __int128 v65; // [esp-8CCh] [ebp-8D8h] BYREF
  void *v66; // [esp-8BCh] [ebp-8C8h]
  struct Instance *v67; // [esp-8B8h] [ebp-8C4h] BYREF
  struct PhysicalIndex *v68; // [esp-8B4h] [ebp-8C0h]
  struct Err *v69; // [esp-8B0h] [ebp-8BCh]
  char v70; // [esp-8AAh] [ebp-8B6h]
  char v71; // [esp-8A9h] [ebp-8B5h]
  _BYTE v72[208]; // [esp-8A8h] [ebp-8B4h] BYREF
  _BYTE v73[8]; // [esp-7D8h] [ebp-7E4h] BYREF
  void *v74; // [esp-7D0h] [ebp-7DCh]
  int v75; // [esp-7CCh] [ebp-7D8h]
  unsigned __int16 *v76; // [esp-7C8h] [ebp-7D4h]
  unsigned __int16 **v77; // [esp-7C4h] [ebp-7D0h]
  struct SortItem **v78; // [esp-7C0h] [ebp-7CCh]
  int v79; // [esp-67Ch] [ebp-688h] BYREF
  int v80; // [esp-654h] [ebp-660h] BYREF
  _BYTE v81[36]; // [esp-1F0h] [ebp-1FCh] BYREF
  int v82; // [esp-1CCh] [ebp-1D8h]
  unsigned int v83; // [esp-80h] [ebp-8Ch] BYREF
  int *v84; // [esp-7Ch] [ebp-88h]
  int v85; // [esp-78h] [ebp-84h]
  int v86; // [esp-74h] [ebp-80h]
  int v87; // [esp-70h] [ebp-7Ch] BYREF
  _DWORD v88[3]; // [esp-50h] [ebp-5Ch] BYREF
  unsigned int v89; // [esp-44h] [ebp-50h] BYREF
  unsigned __int8 *v90; // [esp-40h] [ebp-4Ch]
  int v91; // [esp-3Ch] [ebp-48h]
  unsigned int v92; // [esp-38h] [ebp-44h]
  _DWORD v93[12]; // [esp-34h] [ebp-40h] BYREF
  int v94; // [esp-4h] [ebp-10h]
  int v95; // [esp+0h] [ebp-Ch]
  void *v96; // [esp+4h] [ebp-8h]
  int v97; // [esp+8h] [ebp-4h] BYREF
  void *retaddr; // [esp+Ch] [ebp+0h]

  v95 = a2;
  v96 = retaddr;
  v94 = -1;
  v93[11] = &loc_100622A1;
  v93[10] = NtCurrentTeb()->NtTib.ExceptionList;
  v93[9] = &v97;
  v51 = this;
  v5 = a5;
  v6 = a4;
  v63 = a3;
  v68 = a4;
  v69 = a5;
  Cursor::Cursor(v81, a3, this, 0, 0, a5, 0);
  v94 = 0;
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    (*(void (__thiscall **)(int, int, _DWORD, struct Err *))(*(_DWORD *)v82 + 8))(v82, 1, 0, v69);
    v5 = v69;
    v6 = v68;
  }
  v7 = *(_DWORD *)v5;
  if ( (*(_DWORD *)v5 & 1) == 0 && *((_DWORD *)v5 + 1) == -1603 )
  {
    if ( (v7 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)v5 + 3) )
        operator delete[](*((void **)v5 + 3));
      if ( *((_DWORD *)v5 + 4) )
        operator delete[](*((void **)v5 + 4));
    }
    *(_DWORD *)v5 = 1;
    goto LABEL_125;
  }
  if ( (v7 & 8) != 0 )
    goto LABEL_125;
  LODWORD(v65) = 1;
  LOBYTE(v94) = 1;
  Sort::Sort((Sort *)v73);
  v50 = *((_DWORD *)v6 + 8);
  v8 = (unsigned int)(dword_10066930 << 11) >> 1;
  if ( v8 < 0x4000 )
    v8 = 0x4000;
  Sort::Open(v73, *((_DWORD *)v63 + 3), 0, v8, v5);
  if ( (*(_BYTE *)v5 & 8) != 0 )
    goto LABEL_118;
  v62 = 0;
  v90 = (unsigned __int8 *)v93;
  v89 = 0;
  v91 = 0;
  v92 = 32;
  LOBYTE(v94) = 3;
  v48 = *((_DWORD *)v63 + 3);
  v52 = v48;
  v67 = 0;
  (*(void (__thiscall **)(_DWORD, int, struct Instance **))(pJetInfoBlock + 12))(
    *(_DWORD *)(pJetInfoBlock + 12),
    v48,
    &v67);
  v63 = v67;
  v53 = v67;
  v54 = 0;
  v47 = 0;
  v56 = 0;
  v57 = 0;
  if ( !v67 || *(_DWORD *)(*((_DWORD *)v51 + 9) + 68) == 1 )
  {
    v70 = 0;
  }
  else
  {
    v70 = 1;
    v55 = 0;
    Callback::Report((Callback *)&v52, v5);
    v63 = v53;
    v47 = 1;
    v48 = v52;
  }
  v9 = v65;
  v64 = 0;
  if ( (v65 & 8) == 0 )
  {
    while ( 1 )
    {
      v71 = 0;
      v10 = (*(int (__thiscall **)(int, __int128 *))(*(_DWORD *)v82 + 48))(v82, &v65);
      v9 = v65;
      v59 = (char *)v10;
      if ( (v65 & 8) != 0
        || (SortItem = Sort::AllocateSortItem((Sort *)v73, 0x103u, (struct Err *)&v65),
            v9 = v65,
            v60 = (struct SortItem *)SortItem,
            (v65 & 8) != 0) )
      {
LABEL_56:
        v5 = v69;
        goto LABEL_57;
      }
      if ( SortItem == v78 )
      {
        Err::SetError(&v65, -1011, v12);
        v9 = v65;
        goto LABEL_56;
      }
      v13 = 0;
      v14 = 0;
      v61 = *SortItem;
      v89 = 0;
      v67 = 0;
      if ( v50 > 0 )
      {
        do
        {
          if ( (v9 & 8) != 0 )
            break;
          v67 = (struct Instance *)((char *)v67 + 1);
          v15 = *((_DWORD *)v68 + 7);
          v16 = *((_DWORD *)v51 + *(_DWORD *)(v15 + 8 * (_DWORD)v13) + 94);
          v17 = (*(int (__thiscall **)(int, unsigned int *, bool, char *, __int128 *))(*(_DWORD *)v16 + 36))(
                  v16,
                  &v89,
                  (unsigned __int8)*(_DWORD *)(v15 + 8 * (_DWORD)v13 + 4) == 0,
                  v59,
                  &v65);
          v13 = v67;
          v9 = v65;
          v71 |= 2 - (v17 != 0);
        }
        while ( (int)v67 < v50 );
        v14 = v89;
        if ( v89 > 0xFF )
        {
          v18 = v90 + 253;
          *v18 = Checksum::ComputeCrc(v12, v90 + 253, v89 - 253);
          v14 = 255;
          v9 = v65;
          v89 = 255;
        }
      }
      if ( (v9 & 8) != 0 )
      {
        v20 = v64;
      }
      else
      {
        v19 = (struct SortItem **)(*(int (__thiscall **)(int, __int128 *))(*(_DWORD *)v82 + 12))(v82, &v65);
        v9 = v65;
        v20 = v19;
        v14 = v89;
        v64 = v19;
      }
      if ( (v9 & 8) != 0 )
        goto LABEL_56;
      if ( v14 + 4 > v92 )
      {
        ByteAlloc = Key::NextByteAlloc((Key *)&v89, 4u, (struct Err *)&v65);
        LOBYTE(v9) = v65;
      }
      else
      {
        ByteAlloc = &v90[v14];
      }
      if ( (v9 & 8) == 0 )
      {
        *(_DWORD *)ByteAlloc = _byteswap_ulong((unsigned int)v20);
        v89 += 4;
      }
      QuickKey::Copy((QuickKey *)&v89, (unsigned __int8 *)v61 + 4, 0x103u, (struct Err *)&v65);
      v22 = (struct SortItem **)v60;
      *(_WORD *)(*(_DWORD *)v60 + 2) = v89;
      DataSpace = Sort::AllocateDataSpace((Sort *)v73, v22, 1u, (struct Err *)&v65);
      v9 = v65;
      if ( (v65 & 8) == 0 )
      {
        *((_BYTE *)*DataSpace + *((unsigned __int16 *)*DataSpace + 1) + 4) = v71;
        v9 = v65;
      }
      v24 = *((_BYTE *)v68 + 64);
      if ( (v24 & 8) != 0 && (v71 & 1) != 0 )
        break;
      if ( (v24 & 2) != 0 && (v71 & 2) == 0 )
        goto LABEL_50;
LABEL_52:
      if ( (v9 & 8) == 0 )
      {
        ++v62;
        (*(void (__thiscall **)(int, int, int, __int128 *))(*(_DWORD *)v82 + 8))(v82, 1, 2, &v65);
        v9 = v65;
        if ( (v65 & 8) == 0 )
          continue;
      }
      goto LABEL_56;
    }
    if ( v9 < 8 )
    {
      if ( (v9 & 0xFFFFFFFE) != 0 )
      {
        if ( HIDWORD(v65) )
          operator delete[]((void *)HIDWORD(v65));
        if ( v66 )
          operator delete[](v66);
      }
      v66 = 0;
      v65 = _xmm;
      v9 = _xmm;
    }
LABEL_50:
    v25 = *v77;
    if ( (unsigned __int16 *)((char *)*v77 + (*v77)[1] + **v77 + 4) == v76 )
    {
      --v75;
      v76 = v25;
      ++v77;
    }
    goto LABEL_52;
  }
LABEL_57:
  if ( ((v9 & 1) != 0 || DWORD1(v65) != -1603) && v9 > *(_DWORD *)v5 )
    Err::operator=(&v65);
  if ( (*(_BYTE *)v5 & 8) != 0 )
    goto LABEL_110;
  Sort::EndInsert(v73, v5);
  if ( (*(_BYTE *)v5 & 8) != 0 )
    goto LABEL_110;
  v26 = v57;
  if ( v70 )
    v26 = v62;
  v57 = v26;
  v27 = Sort::First((Sort *)v73, v5);
  v64 = v27;
  if ( v27 == v78 || (*(_BYTE *)v5 & 8) != 0 )
    goto LABEL_102;
  v61 = (struct SortItem *)*((unsigned __int8 *)v68 + 64);
  Btree::Btree((Btree *)v72, (struct Cursor *)v81, v68);
  v83 = 0;
  v84 = &v87;
  v85 = 0;
  v86 = 32;
  LOBYTE(v94) = 5;
  if ( (*(_BYTE *)v5 & 8) != 0 )
    goto LABEL_101;
  while ( v27 != v78 )
  {
    v60 = *v27;
    v28 = *((unsigned __int16 *)v60 + 1);
    v59 = (char *)v60 + 4;
    v58 = v28;
    Btree::AddLastKey((Btree *)v72, (const struct QuickKey *)&v58, v5);
    v29 = v59;
    v50 = (int)v59;
    v49 = v58 - 4;
    if ( v58 - 4 != v83 )
      goto LABEL_92;
    v30 = v84;
    v31 = v83 - 4;
    if ( v83 < 4 )
    {
LABEL_73:
      if ( v31 == -4 )
        goto LABEL_82;
    }
    else
    {
      while ( *(_DWORD *)v29 == *v30 )
      {
        v29 += 4;
        ++v30;
        v32 = v31 < 4;
        v31 -= 4;
        if ( v32 )
          goto LABEL_73;
      }
    }
    v32 = (unsigned __int8)*v29 < *(_BYTE *)v30;
    if ( *v29 != *(_BYTE *)v30
      || v31 != -3
      && ((v33 = v29[1], v32 = v33 < *((_BYTE *)v30 + 1), v33 != *((_BYTE *)v30 + 1))
       || v31 != -2
       && ((v34 = v29[2], v32 = v34 < *((_BYTE *)v30 + 2), v34 != *((_BYTE *)v30 + 2))
        || v31 != -1 && (v35 = v29[3], v32 = v35 < *((_BYTE *)v30 + 3), v35 != *((_BYTE *)v30 + 3)))) )
    {
      v36 = v32 ? -1 : 1;
      goto LABEL_83;
    }
LABEL_82:
    v36 = 0;
LABEL_83:
    if ( !v36 )
    {
      if ( ((unsigned __int8)v61 & 1) != 0 && (*((_BYTE *)v60 + *((unsigned __int16 *)v60 + 1) + 4) & 1) == 0 )
      {
        if ( (*(_DWORD *)v5 & 0xFFFFFFFE) != 0 )
        {
          if ( *((_DWORD *)v5 + 3) )
            operator delete[](*((void **)v5 + 3));
          if ( *((_DWORD *)v5 + 4) )
            operator delete[](*((void **)v5 + 4));
        }
        *(_DWORD *)v5 = 8;
        *((_DWORD *)v5 + 1) = -1605;
        *((_DWORD *)v5 + 2) = 0;
        *((_DWORD *)v5 + 3) = 0;
        *((_DWORD *)v5 + 4) = 0;
      }
      goto LABEL_93;
    }
LABEL_92:
    v37 = v68;
    *(_BYTE *)(*((_DWORD *)v68 + 5) + 88) |= 1u;
    ++*((_DWORD *)v37 + 13);
    Key::Assign((Key *)&v83, (const struct QuickKey *)&v49, v5);
LABEL_93:
    v38 = v68;
    *(_BYTE *)(*((_DWORD *)v68 + 5) + 88) |= 1u;
    ++*((_DWORD *)v38 + 11);
    if ( v70 )
    {
      v39 = v56 + 1;
      v56 = v39;
      if ( (v39 & 0x7F) == 0 )
      {
        v40 = *(_DWORD *)(v48 + 212);
        v88[1] = v39;
        v88[2] = v57;
        v88[0] = 12;
        v41 = ((int (__thiscall *)(struct Instance *, int, _DWORD, int, _DWORD *))v63)(
                v63,
                v40,
                *(&dword_10003DB8 + v54),
                dword_10003DA4[v47],
                v88);
        if ( v41 < 0 )
          Err::SetError(v5, v41, v42);
      }
    }
    v43 = Sort::Next((Sort *)v73, v64, v5);
    v44 = (*(_BYTE *)v5 & 8) == 0;
    v27 = v43;
    v64 = v43;
    if ( !v44 )
      break;
  }
  if ( v85 == 1 && v84 )
    operator delete[](v84);
LABEL_101:
  LOBYTE(v94) = 3;
  Btree::~Btree((Btree *)v72);
LABEL_102:
  if ( (*(_DWORD *)v5 & 1) == 0 && *((_DWORD *)v5 + 1) == -1603 )
  {
    if ( (*(_DWORD *)v5 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)v5 + 3) )
        operator delete[](*((void **)v5 + 3));
      if ( *((_DWORD *)v5 + 4) )
        operator delete[](*((void **)v5 + 4));
    }
    *(_DWORD *)v5 = 1;
  }
LABEL_110:
  Sort::Close((Sort *)v73);
  if ( v70 )
  {
    if ( (*(_BYTE *)v5 & 8) != 0 )
    {
      v55 = 4;
    }
    else
    {
      v55 = 3;
      v57 = v56;
    }
    Callback::Report((Callback *)&v52, v5);
  }
  if ( v91 == 1 && v90 )
    operator delete[](v90);
LABEL_118:
  LOBYTE(v94) = 6;
  Sort::Close((Sort *)v73);
  `eh vector destructor iterator'(&v80, 0xA0u, 7u, (void (__thiscall *)(void *))SortWorkFile::~SortWorkFile);
  Transaction::~Transaction((Transaction *)&v79);
  if ( v74 )
  {
    v46 = v74;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v46);
  }
  if ( (v65 & 0xFFFFFFFE) != 0 )
  {
    if ( HIDWORD(v65) )
      operator delete[]((void *)HIDWORD(v65));
    if ( v66 )
      operator delete[](v66);
  }
LABEL_125:
  Cursor::~Cursor((Cursor *)v81);
}

```

## disassembly

```asm
0x10058210  mov     edi, edi
0x10058212  push    ebx
0x10058213  mov     ebx, esp
0x10058215  sub     esp, 8
0x10058218  and     esp, 0FFFFFFF8h
0x1005821b  add     esp, 4
0x1005821e  push    ebp
0x1005821f  mov     ebp, [ebx+4]
0x10058222  mov     [esp+0Ch+var_8], ebp
0x10058226  mov     ebp, esp
0x10058228  push    0FFFFFFFFh
0x1005822a  push    offset loc_100622A1
0x1005822f  mov     eax, large fs:0
0x10058235  push    eax
0x10058236  push    ebx
0x10058237  sub     esp, 908h
0x1005823d  mov     eax, ___security_cookie
0x10058242  xor     eax, ebp
0x10058244  mov     [ebp-14h], eax
0x10058247  push    esi
0x10058248  push    edi
0x10058249  push    eax; unsigned int
0x1005824a  lea     eax, [ebp-0Ch]
0x1005824d  mov     large fs:0, eax
0x10058253  mov     [ebp-904h], ecx
0x10058259  mov     edi, [ebx+10h]
0x1005825c  mov     eax, [ebx+8]
0x1005825f  mov     esi, [ebx+0Ch]
0x10058262  push    0
0x10058264  push    edi
0x10058265  push    0
0x10058267  push    0
0x10058269  push    ecx
0x1005826a  push    eax
0x1005826b  lea     ecx, [ebp-1F0h]
0x10058271  mov     [ebp-8D4h], eax
0x10058277  mov     [ebp-8B4h], esi
0x1005827d  mov     [ebp-8B0h], edi
0x10058283  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)
0x10058288  mov     dword ptr [ebp-4], 0
0x1005828f  test    byte ptr [edi], 8
0x10058292  jnz     short loc_100582C1
0x10058294  mov     edi, [ebp-1CCh]
0x1005829a  push    dword ptr [ebp-8B0h]
0x100582a0  push    0; unsigned int
0x100582a2  mov     eax, [edi]
0x100582a4  push    1; void *
0x100582a6  mov     esi, [eax+8]
0x100582a9  mov     ecx, esi
0x100582ab  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100582b1  mov     ecx, edi
0x100582b3  call    esi
0x100582b5  mov     edi, [ebp-8B0h]
0x100582bb  mov     esi, [ebp-8B4h]
0x100582c1  mov     eax, [edi]
0x100582c3  test    al, 1
0x100582c5  jnz     short loc_10058302
0x100582c7  cmp     dword ptr [edi+4], 0FFFFF9BDh
0x100582ce  jnz     short loc_10058302
0x100582d0  test    eax, 0FFFFFFFEh
0x100582d5  jz      short loc_100582F7
0x100582d7  mov     eax, [edi+0Ch]
0x100582da  test    eax, eax
0x100582dc  jz      short loc_100582E7
0x100582de  push    eax; Block
0x100582df  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100582e4  add     esp, 4
0x100582e7  mov     eax, [edi+10h]
0x100582ea  test    eax, eax
0x100582ec  jz      short loc_100582F7
0x100582ee  push    eax; Block
0x100582ef  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100582f4  add     esp, 4
0x100582f7  mov     dword ptr [edi], 1
0x100582fd  jmp     loc_10058B7C
0x10058302  test    al, 8
0x10058304  jnz     loc_10058B7C
0x1005830a  mov     dword ptr [ebp-8CCh], 1
0x10058314  lea     ecx, [ebp-7D8h]; this
0x1005831a  mov     byte ptr [ebp-4], 1
0x1005831e  call    ??0Sort@@QAE@XZ; Sort::Sort(void)
0x10058323  mov     eax, [esi+20h]
0x10058326  mov     ecx, 4000h
0x1005832b  mov     esi, [ebp-8D4h]
0x10058331  mov     [ebp-908h], eax
0x10058337  mov     eax, dword_10066930
0x1005833c  shl     eax, 0Bh
0x1005833f  shr     eax, 1
0x10058341  cmp     eax, ecx
0x10058343  push    edi
0x10058344  cmovb   eax, ecx
0x10058347  lea     ecx, [ebp-7D8h]
0x1005834d  push    eax
0x1005834e  push    0
0x10058350  push    dword ptr [esi+0Ch]
0x10058353  call    ?Open@Sort@@QAEXPAVSession@@W4SortMode@@KAAVErr@@@Z; Sort::Open(Session *,SortMode,ulong,Err &)
0x10058358  test    byte ptr [edi], 8
0x1005835b  jnz     loc_10058AFE
0x10058361  lea     eax, [ebp-34h]
0x10058364  mov     dword ptr [ebp-8D8h], 0
0x1005836e  mov     [ebp-40h], eax
0x10058371  mov     dword ptr [ebp-44h], 0
0x10058378  mov     dword ptr [ebp-3Ch], 0
0x1005837f  mov     dword ptr [ebp-38h], 20h ; ' '
0x10058386  mov     byte ptr [ebp-4], 3
0x1005838a  mov     ecx, [esi+0Ch]
0x1005838d  mov     eax, _pJetInfoBlock
0x10058392  mov     [ebp-910h], ecx
0x10058398  mov     [ebp-900h], ecx
0x1005839e  mov     dword ptr [ebp-8B8h], 0
0x100583a8  mov     esi, [eax+0Ch]
0x100583ab  lea     eax, [ebp-8B8h]
0x100583b1  push    eax; unsigned int
0x100583b2  push    ecx; void *
0x100583b3  mov     ecx, esi
0x100583b5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100583bb  call    esi
0x100583bd  mov     eax, [ebp-8B8h]
0x100583c3  mov     [ebp-8D4h], eax
0x100583c9  mov     [ebp-8FCh], eax
0x100583cf  mov     dword ptr [ebp-8F8h], 0
0x100583d9  mov     dword ptr [ebp-914h], 0
0x100583e3  mov     dword ptr [ebp-8F0h], 0
0x100583ed  mov     dword ptr [ebp-8ECh], 0
0x100583f7  test    eax, eax
0x100583f9  jz      short loc_1005844B
0x100583fb  mov     eax, [ebp-904h]
0x10058401  mov     eax, [eax+24h]
0x10058404  cmp     dword ptr [eax+44h], 1
0x10058408  jz      short loc_1005844B
0x1005840a  push    edi; struct Err *
0x1005840b  lea     ecx, [ebp-900h]; this
0x10058411  mov     byte ptr [ebp-8AAh], 1
0x10058418  mov     dword ptr [ebp-8F4h], 0
0x10058422  call    ?Report@Callback@@QAEXAAVErr@@@Z; Callback::Report(Err &)
0x10058427  mov     eax, [ebp-8FCh]
0x1005842d  mov     [ebp-8D4h], eax
0x10058433  mov     eax, [ebp-900h]
0x10058439  mov     dword ptr [ebp-914h], 1
0x10058443  mov     [ebp-910h], eax
0x10058449  jmp     short loc_10058452
0x1005844b  mov     byte ptr [ebp-8AAh], 0
0x10058452  mov     edx, [ebp-8CCh]
0x10058458  mov     dword ptr [ebp-8D0h], 0
0x10058462  test    dl, 8
0x10058465  jnz     loc_10058785
0x1005846b  nop     dword ptr [eax+eax+00h]
0x10058470  mov     edi, [ebp-1CCh]
0x10058476  mov     byte ptr [ebp-8A9h], 0
0x1005847d  mov     eax, [edi]
0x1005847f  mov     esi, [eax+30h]
0x10058482  lea     eax, [ebp-8CCh]
0x10058488  push    eax; void *
0x10058489  mov     ecx, esi
0x1005848b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10058491  mov     ecx, edi
0x10058493  call    esi
0x10058495  mov     edx, [ebp-8CCh]
0x1005849b  mov     [ebp-8E4h], eax
0x100584a1  test    dl, 8
0x100584a4  jnz     loc_1005877F
0x100584aa  lea     eax, [ebp-8CCh]
0x100584b0  push    eax; struct Err *
0x100584b1  push    103h; unsigned __int16
0x100584b6  lea     ecx, [ebp-7D8h]; this
0x100584bc  call    ?AllocateSortItem@Sort@@QAEPAPAVSortItem@@GAAVErr@@@Z; Sort::AllocateSortItem(ushort,Err &)
0x100584c1  mov     edx, [ebp-8CCh]
0x100584c7  mov     [ebp-8E0h], eax
0x100584cd  test    dl, 8
0x100584d0  jnz     loc_1005877F
0x100584d6  cmp     eax, [ebp-7C0h]
0x100584dc  jz      loc_10058768
0x100584e2  mov     eax, [eax]
0x100584e4  xor     esi, esi
0x100584e6  xor     edi, edi
0x100584e8  mov     [ebp-8DCh], eax
0x100584ee  mov     [ebp-44h], edi
0x100584f1  mov     [ebp-8B8h], esi
0x100584f7  cmp     [ebp-908h], esi
0x100584fd  jle     loc_100585A5
0x10058503  test    dl, 8
0x10058506  jnz     short loc_10058575
0x10058508  mov     eax, [ebp-8B4h]
0x1005850e  inc     dword ptr [ebp-8B8h]
0x10058514  mov     eax, [eax+1Ch]
0x10058517  mov     ecx, [eax+esi*8]
0x1005851a  mov     edx, [eax+esi*8+4]
0x1005851e  mov     eax, [ebp-904h]
0x10058524  mov     edi, [eax+ecx*4+178h]
0x1005852b  mov     eax, [edi]
0x1005852d  mov     esi, [eax+24h]
0x10058530  lea     eax, [ebp-8CCh]
0x10058536  push    eax
0x10058537  push    dword ptr [ebp-8E4h]
0x1005853d  xor     eax, eax
0x1005853f  mov     ecx, esi
0x10058541  test    dl, dl
0x10058543  setz    al
0x10058546  push    eax; unsigned int
0x10058547  lea     eax, [ebp-44h]
0x1005854a  push    eax; void *
0x1005854b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10058551  mov     ecx, edi
0x10058553  call    esi
0x10058555  mov     esi, [ebp-8B8h]
0x1005855b  neg     al
0x1005855d  mov     edx, [ebp-8CCh]
0x10058563  sbb     al, al
0x10058565  add     al, 2
0x10058567  or      [ebp-8A9h], al
0x1005856d  cmp     esi, [ebp-908h]
0x10058573  jl      short loc_10058503
0x10058575  mov     edi, [ebp-44h]
0x10058578  cmp     edi, 0FFh
0x1005857e  jbe     short loc_100585A5
0x10058580  mov     eax, [ebp-40h]
0x10058583  lea     esi, [eax+0FDh]
0x10058589  sub     eax, esi
0x1005858b  add     eax, edi
0x1005858d  push    eax; unsigned int
0x1005858e  push    esi; unsigned __int8 *
0x1005858f  call    ?ComputeCrc@Checksum@@QAEGPAEI@Z; Checksum::ComputeCrc(uchar *,uint)
0x10058594  mov     [esi], ax
0x10058597  mov     edi, 0FFh
0x1005859c  mov     edx, [ebp-8CCh]
0x100585a2  mov     [ebp-44h], edi
0x100585a5  test    dl, 8
0x100585a8  jnz     short loc_100585DB
0x100585aa  mov     edi, [ebp-1CCh]
0x100585b0  mov     eax, [edi]
0x100585b2  mov     esi, [eax+0Ch]
0x100585b5  lea     eax, [ebp-8CCh]
0x100585bb  push    eax; void *
0x100585bc  mov     ecx, esi
0x100585be  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100585c4  mov     ecx, edi
0x100585c6  call    esi
0x100585c8  mov     edx, [ebp-8CCh]
0x100585ce  mov     esi, eax
0x100585d0  mov     edi, [ebp-44h]
0x100585d3  mov     [ebp-8D0h], esi
0x100585d9  jmp     short loc_100585E1
0x100585db  mov     esi, [ebp-8D0h]
0x100585e1  test    dl, 8
0x100585e4  jnz     loc_1005877F
0x100585ea  lea     ecx, [edi+4]
0x100585ed  cmp     ecx, [ebp-38h]
0x100585f0  ja      short loc_100585F9
0x100585f2  mov     eax, [ebp-40h]
0x100585f5  add     eax, edi
0x100585f7  jmp     short loc_10058610
0x100585f9  lea     eax, [ebp-8CCh]
0x100585ff  push    eax; struct Err *
0x10058600  push    4; unsigned int
0x10058602  lea     ecx, [ebp-44h]; this
0x10058605  call    ?NextByteAlloc@Key@@AAEPAEIAAVErr@@@Z; Key::NextByteAlloc(uint,Err &)
0x1005860a  mov     edx, [ebp-8CCh]
0x10058610  test    dl, 8
0x10058613  jnz     short loc_1005861F
0x10058615  mov     ecx, esi
0x10058617  bswap   ecx
0x10058619  mov     [eax], ecx
0x1005861b  add     dword ptr [ebp-44h], 4
0x1005861f  lea     eax, [ebp-8CCh]
0x10058625  push    eax; struct Err *
0x10058626  mov     eax, [ebp-8DCh]
0x1005862c  lea     ecx, [ebp-44h]; this
0x1005862f  push    103h; unsigned int
0x10058634  add     eax, 4
0x10058637  push    eax; unsigned __int8 *
0x10058638  call    ?Copy@QuickKey@@QBEIPAEIAAVErr@@@Z; QuickKey::Copy(uchar *,uint,Err &)
0x1005863d  mov     edx, [ebp-8E0h]
0x10058643  mov     ax, [ebp-44h]
0x10058647  mov     ecx, [edx]
0x10058649  mov     [ecx+2], ax
0x1005864d  lea     eax, [ebp-8CCh]
0x10058653  push    eax; struct Err *
0x10058654  push    1; unsigned __int16
0x10058656  push    edx; struct SortItem **
0x10058657  lea     ecx, [ebp-7D8h]; this
0x1005865d  call    ?AllocateDataSpace@Sort@@QAEPAPAVSortItem@@PAPAV2@GAAVErr@@@Z; Sort::AllocateDataSpace(SortItem * *,ushort,Err &)
0x10058662  mov     edx, [ebp-8CCh]
0x10058668  test    dl, 8
0x1005866b  jnz     short loc_10058683
0x1005866d  mov     ecx, [eax]
0x1005866f  mov     dl, [ebp-8A9h]
0x10058675  movzx   eax, word ptr [ecx+2]
0x10058679  mov     [eax+ecx+4], dl
0x1005867d  mov     edx, [ebp-8CCh]
0x10058683  mov     eax, [ebp-8B4h]
0x10058689  mov     cl, [ebp-8A9h]
0x1005868f  mov     al, [eax+40h]
0x10058692  test    al, 8
0x10058694  jz      short loc_100586EE
0x10058696  test    cl, 1
0x10058699  jz      short loc_100586EE
0x1005869b  cmp     edx, 8
0x1005869e  jge     short loc_100586F7
0x100586a0  test    edx, 0FFFFFFFEh
0x100586a6  jz      short loc_100586CE
  ... truncated ...
```
