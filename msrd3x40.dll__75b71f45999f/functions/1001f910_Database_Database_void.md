# Database::~Database(void)

- ea: `0x1001f910`
- end: `0x1001fd99`
- name: `??1Database@@MAE@XZ`
- size: `1161`
- prototype: `void __thiscall(Database *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x10018700`
- `0x1001f780`
- `0x1001f7e0`

## callees

- `0x1001f910`
- `0x1001fdb0`
- `0x10022030`
- `0x10022f00`
- `0x10023690`
- `0x10023bb0`
- `0x100248b0`
- `0x1002e4e0`
- `0x1002ee30`
- `0x10049b80`
- `0x10051e80`
- `0x1005ce60`
- `0x1005d130`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001f94d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001f9b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001fb9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001f94d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001f9b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001fb9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001fd1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001fd82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001fd1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001fd82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001f991`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001f9eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001fbb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001f991`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001f9eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001fbb0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001fa02`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001fa02`

## pseudocode

```c
void __thiscall Database::~Database(Database *this)
{
  unsigned int v2; // ecx
  int v3; // esi
  int v4; // ecx
  unsigned int v5; // ecx
  Database **v6; // edx
  unsigned int v7; // eax
  unsigned int v8; // eax
  Table **v9; // eax
  Table *v10; // esi
  File **v11; // esi
  File **v12; // ecx
  File *v13; // ecx
  int v14; // eax
  int v15; // eax
  Database *v16; // ecx
  _DWORD v17[3]; // [esp+Ch] [ebp-30h] BYREF
  void *Block; // [esp+18h] [ebp-24h]
  void *v19; // [esp+1Ch] [ebp-20h]
  _DWORD v20[3]; // [esp+20h] [ebp-1Ch] BYREF
  File **v21; // [esp+2Ch] [ebp-10h]
  int v22; // [esp+38h] [ebp-4h]

  *(_DWORD *)this = &Database::`vftable';
  v17[0] = 1;
  EnterCriticalSection(&stru_10066950);
  if ( dword_1006694C )
  {
    *(_DWORD *)(dword_10066944 + 4 * dword_1006694C) = this;
    v2 = 0;
    if ( (Database *)*dword_10066944 != this )
    {
      do
        ++v2;
      while ( *(Database **)(dword_10066944 + 4 * v2) != this );
    }
    if ( v2 < dword_1006694C )
    {
      --dword_1006694C;
      *(_DWORD *)(dword_10066944 + 4 * v2) = *(_DWORD *)(dword_10066944 + 4 * dword_1006694C);
    }
  }
  LeaveCriticalSection(&stru_10066950);
  Queue::CancelMessages(&stru_100668BC, this, (struct Err *)v17);
  v3 = *((_DWORD *)this + 15);
  if ( v3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 28));
    v4 = *(_DWORD *)(v3 + 20);
    if ( v4 )
    {
      *(_DWORD *)(*(_DWORD *)(v3 + 12) + 4 * v4) = this;
      v5 = 0;
      v6 = *(Database ***)(v3 + 12);
      if ( *v6 != this )
      {
        do
          ++v5;
        while ( v6[v5] != this );
      }
      v7 = *(_DWORD *)(v3 + 20);
      if ( v5 < v7 )
      {
        v8 = v7 - 1;
        *(_DWORD *)(v3 + 20) = v8;
        v6[v5] = v6[v8];
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 28));
  }
  while ( *((_DWORD *)this + 54) )
    Sleep(1u);
  while ( *((_DWORD *)this + 14) )
  {
    v9 = (Table **)*((_DWORD *)this + 12);
    v10 = *v9;
    if ( *v9 )
    {
      Table::~Table(*v9);
      operator delete(v10, 0x778u);
    }
  }
  if ( *((_DWORD *)this + 17) == 2 || (unsigned int)(*((_DWORD *)this + 17) - 3) <= 1 )
  {
    if ( (v17[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v19 )
        operator delete[](v19);
    }
    v17[0] = 1;
    Database::RecyclePages(this, (struct Err *)v17);
  }
  if ( (v17[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v19 )
      operator delete[](v19);
  }
  v17[0] = 1;
  AbstractSpacemap::Close((Database *)((char *)this + 276), (struct Err *)v17);
  if ( *((_DWORD *)this + 17) )
  {
    if ( *((_DWORD *)this + 16) )
    {
      if ( (v17[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v19 )
          operator delete[](v19);
      }
      v17[0] = 1;
      v20[0] = 0;
      v20[1] = 0;
      Database::ReadPage(this, (struct PageRef *)v20, 0, 1, (struct Err *)v17, 0);
      if ( (v17[0] & 8) == 0 )
      {
        Database::CheckForCorruption(this, (struct DBHeaderPage *)v20, (struct Err *)v17);
        if ( (v17[0] & 8) != 0 )
          *(_DWORD *)(*((_DWORD *)this + 16) + 16) &= ~0x100u;
      }
      if ( v20[0] )
        --*(_WORD *)(v20[0] + 76);
    }
    if ( (v17[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v19 )
        operator delete[](v19);
    }
    v17[0] = 1;
    Database::WriteDirtyPages(this, (struct Err *)v17);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    File::Close((Database *)((char *)this + 4), (struct Err *)v17);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  }
  v11 = (File **)((char *)this + 64);
  if ( *((_DWORD *)this + 16) )
  {
    v12 = (File **)((char *)this + 64);
    if ( (v17[0] & 0xFFFFFFFE) != 0 )
    {
      v21 = (File **)((char *)this + 64);
      if ( Block )
      {
        v21 = (File **)((char *)this + 64);
        operator delete[](Block);
        v21 = (File **)((char *)this + 64);
      }
      v12 = (File **)((char *)this + 64);
      if ( v19 )
      {
        operator delete[](v19);
        v12 = v21;
      }
    }
    v13 = *v12;
    v17[0] = 1;
    File::Close(v13, (struct Err *)v17);
    if ( *v11 )
      File::`scalar deleting destructor'(*v11, (unsigned int)*v11);
  }
  if ( (v17[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v19 )
      operator delete[](v19);
  }
  if ( *((Database **)this + 236) != (Database *)((char *)this + 960) )
    operator delete[](*((void **)this + 236));
  if ( *((Database **)this + 231) != (Database *)((char *)this + 940) )
    operator delete[](*((void **)this + 231));
  if ( *((_DWORD *)this + 94) )
    operator delete[](*((void **)this + 94));
  v14 = *((_DWORD *)this + 80);
  if ( v14 )
    --*(_WORD *)(v14 + 76);
  v15 = *((_DWORD *)this + 76);
  if ( v15 )
    --*(_WORD *)(v15 + 76);
  Transaction::~Transaction((Database *)((char *)this + 236));
  if ( (*((_DWORD *)this + 49) & 0xFFFFFFFE) != 0 )
  {
    if ( *((_DWORD *)this + 52) )
      operator delete[](*((void **)this + 52));
    if ( *((_DWORD *)this + 53) )
      operator delete[](*((void **)this + 53));
  }
  HashTable::~HashTable((Database *)((char *)this + 160));
  v22 = 0;
  v16 = (Database *)*((_DWORD *)this + 39);
  if ( v16 )
    Database::ReclaimPDSpace(v16);
  if ( *((_DWORD *)this + 37) )
    operator delete[](*((void **)this + 37));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 12) )
    operator delete[](*((void **)this + 12));
  v17[0] = 1;
  File::Close((Database *)((char *)this + 4), (struct Err *)v17);
  if ( *((_DWORD *)this + 2) )
    operator delete[](*((void **)this + 2));
  if ( (v17[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v19 )
      operator delete[](v19);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x1001f910  mov     edi, edi
0x1001f912  push    ebp
0x1001f913  mov     ebp, esp
0x1001f915  push    0FFFFFFFFh
0x1001f917  push    offset ??1Database@@MAE@XZ_SEH
0x1001f91c  mov     eax, large fs:0
0x1001f922  push    eax
0x1001f923  sub     esp, 24h
0x1001f926  push    esi
0x1001f927  push    edi
0x1001f928  mov     eax, ___security_cookie
0x1001f92d  xor     eax, ebp
0x1001f92f  push    eax
0x1001f930  lea     eax, [ebp+var_C]
0x1001f933  mov     large fs:0, eax
0x1001f939  mov     edi, ecx
0x1001f93b  push    offset stru_10066950; lpCriticalSection
0x1001f940  mov     dword ptr [edi], offset ??_7Database@@6B@; const Database::`vftable'
0x1001f946  mov     [ebp+var_30], 1
0x1001f94d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001f953  mov     ecx, dword_1006694C
0x1001f959  test    ecx, ecx
0x1001f95b  jz      short loc_1001F98C
0x1001f95d  mov     eax, dword_10066944
0x1001f962  mov     [eax+ecx*4], edi
0x1001f965  xor     ecx, ecx
0x1001f967  mov     edx, dword_10066944
0x1001f96d  cmp     [edx], edi
0x1001f96f  jz      short loc_1001F977
0x1001f971  inc     ecx
0x1001f972  cmp     [edx+ecx*4], edi
0x1001f975  jnz     short loc_1001F971
0x1001f977  mov     eax, dword_1006694C
0x1001f97c  cmp     ecx, eax
0x1001f97e  jnb     short loc_1001F98C
0x1001f980  dec     eax
0x1001f981  mov     dword_1006694C, eax
0x1001f986  mov     eax, [edx+eax*4]
0x1001f989  mov     [edx+ecx*4], eax
0x1001f98c  push    offset stru_10066950; lpCriticalSection
0x1001f991  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001f997  lea     eax, [ebp+var_30]
0x1001f99a  mov     ecx, offset stru_100668BC; lpCriticalSection
0x1001f99f  push    eax; struct Err *
0x1001f9a0  push    edi; struct Database *
0x1001f9a1  call    ?CancelMessages@Queue@@QAEKPAVDatabase@@AAVErr@@@Z; Queue::CancelMessages(Database *,Err &)
0x1001f9a6  mov     esi, [edi+3Ch]
0x1001f9a9  test    esi, esi
0x1001f9ab  jz      short loc_1001F9F1
0x1001f9ad  lea     eax, [esi+1Ch]
0x1001f9b0  push    eax; lpCriticalSection
0x1001f9b1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001f9b7  mov     ecx, [esi+14h]
0x1001f9ba  test    ecx, ecx
0x1001f9bc  jz      short loc_1001F9E7
0x1001f9be  mov     eax, [esi+0Ch]
0x1001f9c1  mov     [eax+ecx*4], edi
0x1001f9c4  xor     ecx, ecx
0x1001f9c6  mov     edx, [esi+0Ch]
0x1001f9c9  cmp     [edx], edi
0x1001f9cb  jz      short loc_1001F9D6
0x1001f9cd  nop     dword ptr [eax]
0x1001f9d0  inc     ecx
0x1001f9d1  cmp     [edx+ecx*4], edi
0x1001f9d4  jnz     short loc_1001F9D0
0x1001f9d6  mov     eax, [esi+14h]
0x1001f9d9  cmp     ecx, eax
0x1001f9db  jnb     short loc_1001F9E7
0x1001f9dd  dec     eax
0x1001f9de  mov     [esi+14h], eax
0x1001f9e1  mov     eax, [edx+eax*4]
0x1001f9e4  mov     [edx+ecx*4], eax
0x1001f9e7  lea     eax, [esi+1Ch]
0x1001f9ea  push    eax; lpCriticalSection
0x1001f9eb  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001f9f1  cmp     dword ptr [edi+0D8h], 0
0x1001f9f8  jz      short loc_1001FA11
0x1001f9fa  nop     word ptr [eax+eax+00h]
0x1001fa00  push    1; dwMilliseconds
0x1001fa02  call    ds:__imp__Sleep@4; Sleep(x)
0x1001fa08  cmp     dword ptr [edi+0D8h], 0
0x1001fa0f  jnz     short loc_1001FA00
0x1001fa11  cmp     dword ptr [edi+38h], 0
0x1001fa15  jbe     short loc_1001FA3B
0x1001fa17  mov     eax, [edi+30h]
0x1001fa1a  mov     esi, [eax]
0x1001fa1c  test    esi, esi
0x1001fa1e  jz      short loc_1001FA35
0x1001fa20  mov     ecx, esi; this
0x1001fa22  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x1001fa27  push    778h; unsigned int
0x1001fa2c  push    esi; Block
0x1001fa2d  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001fa32  add     esp, 8
0x1001fa35  cmp     dword ptr [edi+38h], 0
0x1001fa39  ja      short loc_1001FA17
0x1001fa3b  mov     eax, [edi+44h]
0x1001fa3e  sub     eax, 2
0x1001fa41  jz      short loc_1001FA4D
0x1001fa43  sub     eax, 1
0x1001fa46  jz      short loc_1001FA4D
0x1001fa48  sub     eax, 1
0x1001fa4b  jnz     short loc_1001FA88
0x1001fa4d  test    [ebp+var_30], 0FFFFFFFEh
0x1001fa54  jz      short loc_1001FA76
0x1001fa56  mov     eax, [ebp+Block]
0x1001fa59  test    eax, eax
0x1001fa5b  jz      short loc_1001FA66
0x1001fa5d  push    eax; Block
0x1001fa5e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fa63  add     esp, 4
0x1001fa66  mov     eax, [ebp+var_20]
0x1001fa69  test    eax, eax
0x1001fa6b  jz      short loc_1001FA76
0x1001fa6d  push    eax; Block
0x1001fa6e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fa73  add     esp, 4
0x1001fa76  lea     eax, [ebp+var_30]
0x1001fa79  mov     [ebp+var_30], 1
0x1001fa80  push    eax; struct Err *
0x1001fa81  mov     ecx, edi; this
0x1001fa83  call    ?RecyclePages@Database@@IAEXAAVErr@@@Z; Database::RecyclePages(Err &)
0x1001fa88  test    [ebp+var_30], 0FFFFFFFEh
0x1001fa8f  jz      short loc_1001FAB1
0x1001fa91  mov     eax, [ebp+Block]
0x1001fa94  test    eax, eax
0x1001fa96  jz      short loc_1001FAA1
0x1001fa98  push    eax; Block
0x1001fa99  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fa9e  add     esp, 4
0x1001faa1  mov     eax, [ebp+var_20]
0x1001faa4  test    eax, eax
0x1001faa6  jz      short loc_1001FAB1
0x1001faa8  push    eax; Block
0x1001faa9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001faae  add     esp, 4
0x1001fab1  lea     eax, [ebp+var_30]
0x1001fab4  mov     [ebp+var_30], 1
0x1001fabb  lea     ecx, [edi+114h]; this
0x1001fac1  push    eax; struct Err *
0x1001fac2  call    ?Close@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Close(Err &)
0x1001fac7  cmp     dword ptr [edi+44h], 0
0x1001facb  jz      loc_1001FBB6
0x1001fad1  cmp     dword ptr [edi+40h], 0
0x1001fad5  jz      loc_1001FB5E
0x1001fadb  test    [ebp+var_30], 0FFFFFFFEh
0x1001fae2  jz      short loc_1001FB04
0x1001fae4  mov     eax, [ebp+Block]
0x1001fae7  test    eax, eax
0x1001fae9  jz      short loc_1001FAF4
0x1001faeb  push    eax; Block
0x1001faec  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001faf1  add     esp, 4
0x1001faf4  mov     eax, [ebp+var_20]
0x1001faf7  test    eax, eax
0x1001faf9  jz      short loc_1001FB04
0x1001fafb  push    eax; Block
0x1001fafc  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fb01  add     esp, 4
0x1001fb04  push    0; struct Transaction *
0x1001fb06  lea     eax, [ebp+var_30]
0x1001fb09  mov     [ebp+var_30], 1
0x1001fb10  push    eax; struct Err *
0x1001fb11  push    1; char
0x1001fb13  push    0; unsigned int
0x1001fb15  lea     eax, [ebp+var_1C]
0x1001fb18  mov     [ebp+var_1C], 0
0x1001fb1f  push    eax; struct PageRef *
0x1001fb20  mov     ecx, edi; this
0x1001fb22  mov     [ebp+var_18], 0
0x1001fb29  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x1001fb2e  test    byte ptr [ebp+var_30], 8
0x1001fb32  jnz     short loc_1001FB53
0x1001fb34  lea     eax, [ebp+var_30]
0x1001fb37  mov     ecx, edi; this
0x1001fb39  push    eax; struct Err *
0x1001fb3a  lea     eax, [ebp+var_1C]
0x1001fb3d  push    eax; struct DBHeaderPage *
0x1001fb3e  call    ?CheckForCorruption@Database@@IAEXPAVDBHeaderPage@@AAVErr@@@Z; Database::CheckForCorruption(DBHeaderPage *,Err &)
0x1001fb43  test    byte ptr [ebp+var_30], 8
0x1001fb47  jz      short loc_1001FB53
0x1001fb49  mov     eax, [edi+40h]
0x1001fb4c  and     dword ptr [eax+10h], 0FFFFFEFFh
0x1001fb53  mov     eax, [ebp+var_1C]
0x1001fb56  test    eax, eax
0x1001fb58  jz      short loc_1001FB5E
0x1001fb5a  dec     word ptr [eax+4Ch]
0x1001fb5e  test    [ebp+var_30], 0FFFFFFFEh
0x1001fb65  jz      short loc_1001FB87
0x1001fb67  mov     eax, [ebp+Block]
0x1001fb6a  test    eax, eax
0x1001fb6c  jz      short loc_1001FB77
0x1001fb6e  push    eax; Block
0x1001fb6f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fb74  add     esp, 4
0x1001fb77  mov     eax, [ebp+var_20]
0x1001fb7a  test    eax, eax
0x1001fb7c  jz      short loc_1001FB87
0x1001fb7e  push    eax; Block
0x1001fb7f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fb84  add     esp, 4
0x1001fb87  lea     eax, [ebp+var_30]
0x1001fb8a  mov     [ebp+var_30], 1
0x1001fb91  push    eax; struct Err *
0x1001fb92  mov     ecx, edi; this
0x1001fb94  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@@Z; Database::WriteDirtyPages(Err &)
0x1001fb99  lea     esi, [edi+70h]
0x1001fb9c  push    esi; lpCriticalSection
0x1001fb9d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001fba3  lea     eax, [ebp+var_30]
0x1001fba6  lea     ecx, [edi+4]; this
0x1001fba9  push    eax; struct Err *
0x1001fbaa  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x1001fbaf  push    esi; lpCriticalSection
0x1001fbb0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001fbb6  cmp     dword ptr [edi+40h], 0
0x1001fbba  lea     esi, [edi+40h]
0x1001fbbd  jz      short loc_1001FC1D
0x1001fbbf  test    [ebp+var_30], 0FFFFFFFEh
0x1001fbc6  mov     ecx, esi
0x1001fbc8  jz      short loc_1001FBFF
0x1001fbca  mov     ecx, [ebp+Block]
0x1001fbcd  mov     eax, esi
0x1001fbcf  mov     [ebp+var_10], eax
0x1001fbd2  test    ecx, ecx
0x1001fbd4  jz      short loc_1001FBE8
0x1001fbd6  push    ecx; Block
0x1001fbd7  mov     [ebp+var_10], eax
0x1001fbda  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fbdf  lea     eax, [edi+40h]
0x1001fbe2  add     esp, 4
0x1001fbe5  mov     [ebp+var_10], eax
0x1001fbe8  mov     edx, [ebp+var_20]
0x1001fbeb  mov     ecx, esi
0x1001fbed  test    edx, edx
0x1001fbef  jz      short loc_1001FBFF
0x1001fbf1  mov     ecx, eax
0x1001fbf3  push    edx; Block
0x1001fbf4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fbf9  mov     ecx, [ebp+var_10]
0x1001fbfc  add     esp, 4
0x1001fbff  mov     ecx, [ecx]; this
0x1001fc01  lea     eax, [ebp+var_30]
0x1001fc04  push    eax; struct Err *
0x1001fc05  mov     [ebp+var_30], 1
0x1001fc0c  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x1001fc11  mov     ecx, [esi]; this
0x1001fc13  test    ecx, ecx
0x1001fc15  jz      short loc_1001FC1D
0x1001fc17  push    ecx; unsigned int
0x1001fc18  call    ??_GFile@@QAEPAXI@Z; File::`scalar deleting destructor'(uint)
0x1001fc1d  test    [ebp+var_30], 0FFFFFFFEh
0x1001fc24  jz      short loc_1001FC46
0x1001fc26  mov     eax, [ebp+Block]
0x1001fc29  test    eax, eax
0x1001fc2b  jz      short loc_1001FC36
0x1001fc2d  push    eax; Block
0x1001fc2e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fc33  add     esp, 4
0x1001fc36  mov     eax, [ebp+var_20]
0x1001fc39  test    eax, eax
0x1001fc3b  jz      short loc_1001FC46
0x1001fc3d  push    eax; Block
0x1001fc3e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fc43  add     esp, 4
0x1001fc46  mov     ecx, [edi+3B0h]
0x1001fc4c  lea     eax, [edi+3C0h]
0x1001fc52  cmp     ecx, eax
0x1001fc54  jz      short loc_1001FC5F
0x1001fc56  push    ecx; Block
0x1001fc57  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fc5c  add     esp, 4
0x1001fc5f  mov     ecx, [edi+39Ch]
0x1001fc65  lea     eax, [edi+3ACh]
0x1001fc6b  cmp     ecx, eax
0x1001fc6d  jz      short loc_1001FC78
0x1001fc6f  push    ecx; Block
0x1001fc70  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fc75  add     esp, 4
0x1001fc78  mov     eax, [edi+178h]
0x1001fc7e  test    eax, eax
0x1001fc80  jz      short loc_1001FC8B
0x1001fc82  push    eax; Block
0x1001fc83  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fc88  add     esp, 4
0x1001fc8b  mov     eax, [edi+140h]
0x1001fc91  test    eax, eax
0x1001fc93  jz      short loc_1001FC99
0x1001fc95  dec     word ptr [eax+4Ch]
0x1001fc99  mov     eax, [edi+130h]
0x1001fc9f  test    eax, eax
0x1001fca1  jz      short loc_1001FCA7
0x1001fca3  dec     word ptr [eax+4Ch]
0x1001fca7  lea     ecx, [edi+0ECh]; this
0x1001fcad  call    ??1Transaction@@QAE@XZ; Transaction::~Transaction(void)
0x1001fcb2  test    dword ptr [edi+0C4h], 0FFFFFFFEh
0x1001fcbc  jz      short loc_1001FCE4
0x1001fcbe  mov     eax, [edi+0D0h]
0x1001fcc4  test    eax, eax
0x1001fcc6  jz      short loc_1001FCD1
  ... truncated ...
```
