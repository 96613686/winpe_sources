# Database::~Database(void)

- ea: `0x100532cd`
- end: `0x100535cd`
- name: `??1Database@@MAE@XZ`
- size: `768`
- prototype: `void __usercall(Database *__hidden this@<ecx>)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops`

## callers

- `0x10053250`
- `0x100535d8`

## callees

- `0x1004e680`
- `0x10050e98`
- `0x1005112a`
- `0x100514d0`
- `0x10052f3f`
- `0x100532cd`
- `0x10054ecf`
- `0x10055b9e`
- `0x100563ef`
- `0x10056a81`
- `0x10057a33`
- `0x10061993`
- `0x100722d0`
- `0x10073ca0`
- `0x10074cbc`
- `0x10075709`
- `0x10077bf6`
- `0x1007a57f`
- `0x1007b550`
- `0x10123110`
- `0x10123c92`
- `0x10123ca8`
- `0x10124048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100535a7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100535a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053355`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1005347f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053355`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1005347f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005330c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10053345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005346c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005330c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10053345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005346c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10053369`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10053369`

## pseudocode

```c
void __thiscall Database::~Database(Database *this)
{
  int v2; // ebx
  Table **v3; // eax
  enum LckTyp *v4; // ecx
  void *v5; // esi
  _DWORD v6[5]; // [esp+10h] [ebp-34h] BYREF
  _DWORD v7[2]; // [esp+24h] [ebp-20h] BYREF
  _DWORD v8[6]; // [esp+2Ch] [ebp-18h] BYREF

  *(_DWORD *)this = &Database::`vftable';
  v6[0] = 1;
  EnterCriticalSection(dword_10130558);
  Collection::RemoveObject(dword_10130554, this);
  LeaveCriticalSection(dword_10130558);
  Queue::CancelMessages(lpCriticalSection, this, (struct Err *)v6);
  v2 = *((_DWORD *)this + 16);
  if ( v2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 28));
    Collection::RemoveObject((Collection *)(v2 + 12), this);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 28));
  }
  while ( *((_DWORD *)this + 53) )
    Sleep(1u);
  while ( *((_DWORD *)this + 15) )
  {
    v3 = (Table **)*((_DWORD *)this + 13);
    if ( *v3 )
      Table::`scalar deleting destructor'(*v3, (unsigned int)*v3);
  }
  if ( *((_DWORD *)this + 18) == 2 || *((_DWORD *)this + 18) == 3 || *((_DWORD *)this + 18) == 4 )
  {
    Err::Delete((Err *)v6);
    v6[0] = 1;
    Database::RecyclePages(this, (struct Err *)v6);
  }
  Err::Delete((Err *)v6);
  v6[0] = 1;
  AbstractSpacemap::Close((Database *)((char *)this + 280), (struct Err *)v6);
  if ( *((_DWORD *)this + 234) )
    operator delete[](*((void **)this + 234));
  if ( *((_DWORD *)this + 18) )
  {
    if ( *((_DWORD *)this + 17) )
    {
      Err::Delete((Err *)v6);
      v6[0] = 1;
      v8[0] = 0;
      v8[1] = 0;
      Database::ReadPage(this, (struct PageRef *)v8, 0, 1, (struct Err *)v6, 0, v4);
      if ( (v6[0] & 8) == 0 )
      {
        Database::CheckForCorruption(this, (struct DBHeaderPage *)v8, (struct Err *)v6);
        if ( (v6[0] & 8) != 0 )
          *(_DWORD *)(*((_DWORD *)this + 17) + 20) &= ~0x100u;
      }
      if ( v8[0] )
        _InterlockedDecrement((volatile signed __int32 *)(v8[0] + 76));
    }
    Err::Delete((Err *)v6);
    v6[0] = 1;
    Database::WriteDirtyPages(this, v6, *((_DWORD *)this + 18) < 2u);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    File::Close((Database *)((char *)this + 4), (struct Err *)v6);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  }
  if ( *((_DWORD *)this + 17) )
  {
    v7[0] = 1;
    Err::Delete((Err *)v6);
    v6[0] = 1;
    if ( *((_DWORD *)this + 58) )
      File::UnlockRange(*((File **)this + 17), *((_DWORD *)this + 25) + 268436736, 1u, (struct Err *)v7);
    if ( (*((_BYTE *)this + 236) & 0x10) != 0 )
      File::UnlockRange(*((File **)this + 17), *((_DWORD *)this + 25) + 268435711, 1u, (struct Err *)v7);
    File::UnlockRange(*((File **)this + 17), *((_DWORD *)this + 25) + 0x10000000, 1u, (struct Err *)v7);
    File::Close(*((File **)this + 17), (struct Err *)v6);
    v5 = (void *)*((_DWORD *)this + 17);
    if ( v5 )
    {
      File::~File(*((File **)this + 17));
      operator delete(v5, 0x30u);
    }
    if ( (v7[0] & 0xFFFFFFFE) != 0 )
      Err::Delete((Err *)v7);
  }
  if ( (v6[0] & 0xFFFFFFFE) != 0 )
    Err::Delete((Err *)v6);
  DynaBitmap::~DynaBitmap((Database *)((char *)this + 960));
  DynaBitmap::~DynaBitmap((Database *)((char *)this + 940));
  PresOrderList::~PresOrderList((Database *)((char *)this + 388));
  AbstractSpacemap::~AbstractSpacemap((Database *)((char *)this + 280));
  Transaction::~Transaction((Database *)((char *)this + 240));
  if ( (*((_DWORD *)this + 48) & 0xFFFFFFFE) != 0 )
    Err::Delete((Database *)((char *)this + 192));
  HashTable::Free((Database *)((char *)this + 152));
  PageDescBlocks::~PageDescBlocks((Database *)((char *)this + 128));
  v8[5] = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  PresOrderList::~PresOrderList((Database *)((char *)this + 52));
  File::~File((Database *)((char *)this + 4));
}

```

## disassembly

```asm
0x100532cd  mov     edi, edi
0x100532cf  push    ebp
0x100532d0  mov     ebp, esp
0x100532d2  push    0FFFFFFFFh
0x100532d4  push    offset ??1Database@@MAE@XZ_SEH
0x100532d9  mov     eax, large fs:0
0x100532df  push    eax
0x100532e0  sub     esp, 28h
0x100532e3  push    ebx
0x100532e4  push    esi
0x100532e5  push    edi
0x100532e6  mov     eax, ___security_cookie
0x100532eb  xor     eax, ebp
0x100532ed  push    eax
0x100532ee  lea     eax, [ebp+var_C]
0x100532f1  mov     large fs:0, eax
0x100532f7  mov     edi, ecx
0x100532f9  mov     dword ptr [edi], offset ??_7Database@@6B@; const Database::`vftable'
0x100532ff  push    dword_10130558; lpCriticalSection
0x10053305  mov     [ebp+var_34], 1
0x1005330c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10053312  mov     ecx, dword_10130554; this
0x10053318  push    edi; void *
0x10053319  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x1005331e  push    dword_10130558; lpCriticalSection
0x10053324  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005332a  mov     ecx, lpCriticalSection; lpCriticalSection
0x10053330  lea     eax, [ebp+var_34]
0x10053333  push    eax; struct Err *
0x10053334  push    edi; struct Database *
0x10053335  call    ?CancelMessages@Queue@@QAEKPAVDatabase@@AAVErr@@@Z; Queue::CancelMessages(Database *,Err &)
0x1005333a  mov     ebx, [edi+40h]
0x1005333d  test    ebx, ebx
0x1005333f  jz      short loc_1005335B
0x10053341  lea     esi, [ebx+1Ch]
0x10053344  push    esi; lpCriticalSection
0x10053345  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1005334b  lea     ecx, [ebx+0Ch]; this
0x1005334e  push    edi; void *
0x1005334f  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x10053354  push    esi; lpCriticalSection
0x10053355  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005335b  xor     ebx, ebx
0x1005335d  xor     esi, esi
0x1005335f  inc     ebx
0x10053360  cmp     [edi+0D4h], esi
0x10053366  jz      short loc_10053380
0x10053368  push    ebx; dwMilliseconds
0x10053369  call    ds:__imp__Sleep@4; Sleep(x)
0x1005336f  jmp     short loc_10053360
0x10053371  mov     eax, [edi+34h]
0x10053374  mov     ecx, [eax]; this
0x10053376  test    ecx, ecx
0x10053378  jz      short loc_10053380
0x1005337a  push    ecx; unsigned int
0x1005337b  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x10053380  cmp     [edi+3Ch], esi
0x10053383  ja      short loc_10053371
0x10053385  mov     eax, [edi+48h]
0x10053388  dec     eax
0x10053389  sub     eax, 1
0x1005338c  jz      short loc_10053398
0x1005338e  sub     eax, 1
0x10053391  jz      short loc_10053398
0x10053393  sub     eax, 1
0x10053396  jnz     short loc_100533AE
0x10053398  lea     ecx, [ebp+var_34]; this
0x1005339b  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100533a0  lea     eax, [ebp+var_34]
0x100533a3  mov     [ebp+var_34], ebx
0x100533a6  push    eax; struct Err *
0x100533a7  mov     ecx, edi; this
0x100533a9  call    ?RecyclePages@Database@@IAEXAAVErr@@@Z; Database::RecyclePages(Err &)
0x100533ae  lea     ecx, [ebp+var_34]; this
0x100533b1  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100533b6  mov     [ebp+var_34], ebx
0x100533b9  lea     eax, [ebp+var_34]
0x100533bc  lea     ebx, [edi+118h]
0x100533c2  push    eax; struct Err *
0x100533c3  mov     ecx, ebx; this
0x100533c5  call    ?Close@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Close(Err &)
0x100533ca  mov     eax, [edi+3A8h]
0x100533d0  test    eax, eax
0x100533d2  jz      short loc_100533DB
0x100533d4  push    eax; Block
0x100533d5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100533da  pop     ecx
0x100533db  cmp     [edi+48h], esi
0x100533de  jz      loc_10053487
0x100533e4  cmp     [edi+44h], esi
0x100533e7  jz      short loc_10053442
0x100533e9  lea     ecx, [ebp+var_34]; this
0x100533ec  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100533f1  push    ecx; enum LckTyp *
0x100533f2  push    esi; struct Transaction *
0x100533f3  lea     eax, [ebp+var_34]
0x100533f6  mov     [ebp+var_34], 1
0x100533fd  push    eax; struct Err *
0x100533fe  push    1; char
0x10053400  push    esi; unsigned int
0x10053401  lea     eax, [ebp+var_18]
0x10053404  mov     [ebp+var_18], esi
0x10053407  push    eax; struct PageRef *
0x10053408  mov     ecx, edi; this
0x1005340a  mov     [ebp+var_14], esi
0x1005340d  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@PAW4LckTyp@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *,LckTyp *)
0x10053412  test    byte ptr [ebp+var_34], 8
0x10053416  jnz     short loc_10053437
0x10053418  lea     eax, [ebp+var_34]
0x1005341b  mov     ecx, edi; this
0x1005341d  push    eax; struct Err *
0x1005341e  lea     eax, [ebp+var_18]
0x10053421  push    eax; struct DBHeaderPage *
0x10053422  call    ?CheckForCorruption@Database@@IAEXPAVDBHeaderPage@@AAVErr@@@Z; Database::CheckForCorruption(DBHeaderPage *,Err &)
0x10053427  test    byte ptr [ebp+var_34], 8
0x1005342b  jz      short loc_10053437
0x1005342d  mov     eax, [edi+44h]
0x10053430  and     dword ptr [eax+14h], 0FFFFFEFFh
0x10053437  mov     eax, [ebp+var_18]
0x1005343a  test    eax, eax
0x1005343c  jz      short loc_10053442
0x1005343e  lock dec dword ptr [eax+4Ch]
0x10053442  lea     ecx, [ebp+var_34]; this
0x10053445  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x1005344a  xor     eax, eax
0x1005344c  inc     eax
0x1005344d  mov     [ebp+var_34], eax
0x10053450  cmp     [edi+48h], eax
0x10053453  jz      short loc_1005345C
0x10053455  cmp     [edi+48h], esi
0x10053458  jz      short loc_1005345C
0x1005345a  mov     eax, esi
0x1005345c  push    eax
0x1005345d  lea     eax, [ebp+var_34]
0x10053460  mov     ecx, edi
0x10053462  push    eax
0x10053463  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z; Database::WriteDirtyPages(Err &,DBWriteOption)
0x10053468  lea     esi, [edi+68h]
0x1005346b  push    esi; lpCriticalSection
0x1005346c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10053472  lea     eax, [ebp+var_34]
0x10053475  lea     ecx, [edi+4]; this
0x10053478  push    eax; struct Err *
0x10053479  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x1005347e  push    esi; lpCriticalSection
0x1005347f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10053485  xor     esi, esi
0x10053487  cmp     [edi+44h], esi
0x1005348a  jz      loc_10053533
0x10053490  lea     ecx, [ebp+var_34]; this
0x10053493  mov     [ebp+var_20], 1
0x1005349a  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x1005349f  mov     [ebp+var_34], 1
0x100534a6  cmp     [edi+0E8h], esi
0x100534ac  jz      short loc_100534C5
0x100534ae  mov     ecx, [edi+44h]; this
0x100534b1  lea     eax, [ebp+var_20]
0x100534b4  push    eax; struct Err *
0x100534b5  mov     eax, [edi+64h]
0x100534b8  push    1; nNumberOfBytesToUnlockLow
0x100534ba  add     eax, 10000500h
0x100534bf  push    eax; dwFileOffsetLow
0x100534c0  call    ?UnlockRange@File@@QAEXKKAAVErr@@@Z; File::UnlockRange(ulong,ulong,Err &)
0x100534c5  test    byte ptr [edi+0ECh], 10h
0x100534cc  jz      short loc_100534E5
0x100534ce  mov     ecx, [edi+44h]; this
0x100534d1  lea     eax, [ebp+var_20]
0x100534d4  push    eax; struct Err *
0x100534d5  mov     eax, [edi+64h]
0x100534d8  push    1; nNumberOfBytesToUnlockLow
0x100534da  add     eax, 100000FFh
0x100534df  push    eax; dwFileOffsetLow
0x100534e0  call    ?UnlockRange@File@@QAEXKKAAVErr@@@Z; File::UnlockRange(ulong,ulong,Err &)
0x100534e5  mov     ecx, [edi+44h]; this
0x100534e8  lea     eax, [ebp+var_20]
0x100534eb  push    eax; struct Err *
0x100534ec  mov     eax, [edi+64h]
0x100534ef  push    1; nNumberOfBytesToUnlockLow
0x100534f1  add     eax, 10000000h
0x100534f6  push    eax; dwFileOffsetLow
0x100534f7  call    ?UnlockRange@File@@QAEXKKAAVErr@@@Z; File::UnlockRange(ulong,ulong,Err &)
0x100534fc  mov     ecx, [edi+44h]; this
0x100534ff  lea     eax, [ebp+var_34]
0x10053502  push    eax; struct Err *
0x10053503  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10053508  mov     esi, [edi+44h]
0x1005350b  test    esi, esi
0x1005350d  jz      short loc_10053520
0x1005350f  mov     ecx, esi; this
0x10053511  call    ??1File@@QAE@XZ; File::~File(void)
0x10053516  push    30h ; '0'; unsigned int
0x10053518  push    esi; Block
0x10053519  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005351e  pop     ecx
0x1005351f  pop     ecx
0x10053520  test    [ebp+var_20], 0FFFFFFFEh
0x10053527  jz      short loc_10053531
0x10053529  lea     ecx, [ebp+var_20]; this
0x1005352c  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10053531  xor     esi, esi
0x10053533  test    [ebp+var_34], 0FFFFFFFEh
0x1005353a  jz      short loc_10053544
0x1005353c  lea     ecx, [ebp+var_34]; this
0x1005353f  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10053544  lea     ecx, [edi+3C0h]; this
0x1005354a  call    ??1DynaBitmap@@QAE@XZ; DynaBitmap::~DynaBitmap(void)
0x1005354f  lea     ecx, [edi+3ACh]; this
0x10053555  call    ??1DynaBitmap@@QAE@XZ; DynaBitmap::~DynaBitmap(void)
0x1005355a  lea     ecx, [edi+184h]; this
0x10053560  call    ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x10053565  mov     ecx, ebx; this
0x10053567  call    ??1AbstractSpacemap@@QAE@XZ; AbstractSpacemap::~AbstractSpacemap(void)
0x1005356c  lea     ecx, [edi+0F0h]; this
0x10053572  call    ??1Transaction@@QAE@XZ; Transaction::~Transaction(void)
0x10053577  lea     ecx, [edi+0C0h]; this
0x1005357d  test    dword ptr [ecx], 0FFFFFFFEh
0x10053583  jz      short loc_1005358A
0x10053585  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x1005358a  lea     ecx, [edi+98h]; this
0x10053590  call    ?Free@HashTable@@QAEXXZ; HashTable::Free(void)
0x10053595  lea     ecx, [edi+80h]; this
0x1005359b  call    ??1PageDescBlocks@@QAE@XZ; PageDescBlocks::~PageDescBlocks(void)
0x100535a0  lea     eax, [edi+68h]
0x100535a3  mov     [ebp+var_4], esi
0x100535a6  push    eax; lpCriticalSection
0x100535a7  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x100535ad  lea     ecx, [edi+34h]; this
0x100535b0  call    ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x100535b5  lea     ecx, [edi+4]; this
0x100535b8  call    ??1File@@QAE@XZ; File::~File(void)
0x100535bd  mov     ecx, [ebp+var_C]
0x100535c0  mov     large fs:0, ecx
0x100535c7  pop     ecx
0x100535c8  pop     edi
0x100535c9  pop     esi
0x100535ca  pop     ebx
0x100535cb  leave
0x100535cc  retn
0x10124060  jmp     ds:__imp____std_terminate
0x10125481  nop
0x10125482  nop
0x10125483  mov     edx, [esp-4+arg_4]
0x10125487  lea     eax, [edx+0Ch]
0x1012548a  mov     ecx, [edx-38h]
0x1012548d  xor     ecx, eax; StackCookie
0x1012548f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125494  mov     eax, offset stru_10127A7C
0x10125499  jmp     ___CxxFrameHandler3
```
