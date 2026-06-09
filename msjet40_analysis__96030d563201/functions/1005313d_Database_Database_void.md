# Database::~Database(void)

- ea: `0x1005313d`
- end: `0x1005343d`
- name: `??1Database@@MAE@XZ`
- size: `768`
- prototype: `void __usercall(Database *__hidden this@<ecx>)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops`

## callers

- `0x100530c0`
- `0x10053448`

## callees

- `0x1004e4f0`
- `0x10050d08`
- `0x10050f9a`
- `0x10051340`
- `0x10052daf`
- `0x1005313d`
- `0x10054d3f`
- `0x10055a0e`
- `0x1005625f`
- `0x100568f1`
- `0x100578a3`
- `0x10061803`
- `0x10072140`
- `0x10073b10`
- `0x10074b2c`
- `0x10075579`
- `0x10077a66`
- `0x1007a3ef`
- `0x1007b3c0`
- `0x10122f60`
- `0x10123ae2`
- `0x10123af8`
- `0x10123e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10053417`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10053417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100531c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100532ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100531c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100532ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005317c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100531b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100532dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005317c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100531b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100532dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x100531d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x100531d9`

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
  EnterCriticalSection(dword_101304C0);
  Collection::RemoveObject(dword_101304BC, this);
  LeaveCriticalSection(dword_101304C0);
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
0x1005313d  mov     edi, edi
0x1005313f  push    ebp
0x10053140  mov     ebp, esp
0x10053142  push    0FFFFFFFFh
0x10053144  push    offset ??1Database@@MAE@XZ_SEH
0x10053149  mov     eax, large fs:0
0x1005314f  push    eax
0x10053150  sub     esp, 28h
0x10053153  push    ebx
0x10053154  push    esi
0x10053155  push    edi
0x10053156  mov     eax, ___security_cookie
0x1005315b  xor     eax, ebp
0x1005315d  push    eax
0x1005315e  lea     eax, [ebp+var_C]
0x10053161  mov     large fs:0, eax
0x10053167  mov     edi, ecx
0x10053169  mov     dword ptr [edi], offset ??_7Database@@6B@; const Database::`vftable'
0x1005316f  push    dword_101304C0; lpCriticalSection
0x10053175  mov     [ebp+var_34], 1
0x1005317c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10053182  mov     ecx, dword_101304BC; this
0x10053188  push    edi; void *
0x10053189  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x1005318e  push    dword_101304C0; lpCriticalSection
0x10053194  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005319a  mov     ecx, lpCriticalSection; lpCriticalSection
0x100531a0  lea     eax, [ebp+var_34]
0x100531a3  push    eax; struct Err *
0x100531a4  push    edi; struct Database *
0x100531a5  call    ?CancelMessages@Queue@@QAEKPAVDatabase@@AAVErr@@@Z; Queue::CancelMessages(Database *,Err &)
0x100531aa  mov     ebx, [edi+40h]
0x100531ad  test    ebx, ebx
0x100531af  jz      short loc_100531CB
0x100531b1  lea     esi, [ebx+1Ch]
0x100531b4  push    esi; lpCriticalSection
0x100531b5  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100531bb  lea     ecx, [ebx+0Ch]; this
0x100531be  push    edi; void *
0x100531bf  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x100531c4  push    esi; lpCriticalSection
0x100531c5  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100531cb  xor     ebx, ebx
0x100531cd  xor     esi, esi
0x100531cf  inc     ebx
0x100531d0  cmp     [edi+0D4h], esi
0x100531d6  jz      short loc_100531F0
0x100531d8  push    ebx; dwMilliseconds
0x100531d9  call    ds:__imp__Sleep@4; Sleep(x)
0x100531df  jmp     short loc_100531D0
0x100531e1  mov     eax, [edi+34h]
0x100531e4  mov     ecx, [eax]; this
0x100531e6  test    ecx, ecx
0x100531e8  jz      short loc_100531F0
0x100531ea  push    ecx; unsigned int
0x100531eb  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x100531f0  cmp     [edi+3Ch], esi
0x100531f3  ja      short loc_100531E1
0x100531f5  mov     eax, [edi+48h]
0x100531f8  dec     eax
0x100531f9  sub     eax, 1
0x100531fc  jz      short loc_10053208
0x100531fe  sub     eax, 1
0x10053201  jz      short loc_10053208
0x10053203  sub     eax, 1
0x10053206  jnz     short loc_1005321E
0x10053208  lea     ecx, [ebp+var_34]; this
0x1005320b  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10053210  lea     eax, [ebp+var_34]
0x10053213  mov     [ebp+var_34], ebx
0x10053216  push    eax; struct Err *
0x10053217  mov     ecx, edi; this
0x10053219  call    ?RecyclePages@Database@@IAEXAAVErr@@@Z; Database::RecyclePages(Err &)
0x1005321e  lea     ecx, [ebp+var_34]; this
0x10053221  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10053226  mov     [ebp+var_34], ebx
0x10053229  lea     eax, [ebp+var_34]
0x1005322c  lea     ebx, [edi+118h]
0x10053232  push    eax; struct Err *
0x10053233  mov     ecx, ebx; this
0x10053235  call    ?Close@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Close(Err &)
0x1005323a  mov     eax, [edi+3A8h]
0x10053240  test    eax, eax
0x10053242  jz      short loc_1005324B
0x10053244  push    eax; Block
0x10053245  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005324a  pop     ecx
0x1005324b  cmp     [edi+48h], esi
0x1005324e  jz      loc_100532F7
0x10053254  cmp     [edi+44h], esi
0x10053257  jz      short loc_100532B2
0x10053259  lea     ecx, [ebp+var_34]; this
0x1005325c  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10053261  push    ecx; enum LckTyp *
0x10053262  push    esi; struct Transaction *
0x10053263  lea     eax, [ebp+var_34]
0x10053266  mov     [ebp+var_34], 1
0x1005326d  push    eax; struct Err *
0x1005326e  push    1; char
0x10053270  push    esi; unsigned int
0x10053271  lea     eax, [ebp+var_18]
0x10053274  mov     [ebp+var_18], esi
0x10053277  push    eax; struct PageRef *
0x10053278  mov     ecx, edi; this
0x1005327a  mov     [ebp+var_14], esi
0x1005327d  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@PAW4LckTyp@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *,LckTyp *)
0x10053282  test    byte ptr [ebp+var_34], 8
0x10053286  jnz     short loc_100532A7
0x10053288  lea     eax, [ebp+var_34]
0x1005328b  mov     ecx, edi; this
0x1005328d  push    eax; struct Err *
0x1005328e  lea     eax, [ebp+var_18]
0x10053291  push    eax; struct DBHeaderPage *
0x10053292  call    ?CheckForCorruption@Database@@IAEXPAVDBHeaderPage@@AAVErr@@@Z; Database::CheckForCorruption(DBHeaderPage *,Err &)
0x10053297  test    byte ptr [ebp+var_34], 8
0x1005329b  jz      short loc_100532A7
0x1005329d  mov     eax, [edi+44h]
0x100532a0  and     dword ptr [eax+14h], 0FFFFFEFFh
0x100532a7  mov     eax, [ebp+var_18]
0x100532aa  test    eax, eax
0x100532ac  jz      short loc_100532B2
0x100532ae  lock dec dword ptr [eax+4Ch]
0x100532b2  lea     ecx, [ebp+var_34]; this
0x100532b5  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100532ba  xor     eax, eax
0x100532bc  inc     eax
0x100532bd  mov     [ebp+var_34], eax
0x100532c0  cmp     [edi+48h], eax
0x100532c3  jz      short loc_100532CC
0x100532c5  cmp     [edi+48h], esi
0x100532c8  jz      short loc_100532CC
0x100532ca  mov     eax, esi
0x100532cc  push    eax
0x100532cd  lea     eax, [ebp+var_34]
0x100532d0  mov     ecx, edi
0x100532d2  push    eax
0x100532d3  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z; Database::WriteDirtyPages(Err &,DBWriteOption)
0x100532d8  lea     esi, [edi+68h]
0x100532db  push    esi; lpCriticalSection
0x100532dc  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100532e2  lea     eax, [ebp+var_34]
0x100532e5  lea     ecx, [edi+4]; this
0x100532e8  push    eax; struct Err *
0x100532e9  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x100532ee  push    esi; lpCriticalSection
0x100532ef  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100532f5  xor     esi, esi
0x100532f7  cmp     [edi+44h], esi
0x100532fa  jz      loc_100533A3
0x10053300  lea     ecx, [ebp+var_34]; this
0x10053303  mov     [ebp+var_20], 1
0x1005330a  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x1005330f  mov     [ebp+var_34], 1
0x10053316  cmp     [edi+0E8h], esi
0x1005331c  jz      short loc_10053335
0x1005331e  mov     ecx, [edi+44h]; this
0x10053321  lea     eax, [ebp+var_20]
0x10053324  push    eax; struct Err *
0x10053325  mov     eax, [edi+64h]
0x10053328  push    1; nNumberOfBytesToUnlockLow
0x1005332a  add     eax, 10000500h
0x1005332f  push    eax; dwFileOffsetLow
0x10053330  call    ?UnlockRange@File@@QAEXKKAAVErr@@@Z; File::UnlockRange(ulong,ulong,Err &)
0x10053335  test    byte ptr [edi+0ECh], 10h
0x1005333c  jz      short loc_10053355
0x1005333e  mov     ecx, [edi+44h]; this
0x10053341  lea     eax, [ebp+var_20]
0x10053344  push    eax; struct Err *
0x10053345  mov     eax, [edi+64h]
0x10053348  push    1; nNumberOfBytesToUnlockLow
0x1005334a  add     eax, 100000FFh
0x1005334f  push    eax; dwFileOffsetLow
0x10053350  call    ?UnlockRange@File@@QAEXKKAAVErr@@@Z; File::UnlockRange(ulong,ulong,Err &)
0x10053355  mov     ecx, [edi+44h]; this
0x10053358  lea     eax, [ebp+var_20]
0x1005335b  push    eax; struct Err *
0x1005335c  mov     eax, [edi+64h]
0x1005335f  push    1; nNumberOfBytesToUnlockLow
0x10053361  add     eax, 10000000h
0x10053366  push    eax; dwFileOffsetLow
0x10053367  call    ?UnlockRange@File@@QAEXKKAAVErr@@@Z; File::UnlockRange(ulong,ulong,Err &)
0x1005336c  mov     ecx, [edi+44h]; this
0x1005336f  lea     eax, [ebp+var_34]
0x10053372  push    eax; struct Err *
0x10053373  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10053378  mov     esi, [edi+44h]
0x1005337b  test    esi, esi
0x1005337d  jz      short loc_10053390
0x1005337f  mov     ecx, esi; this
0x10053381  call    ??1File@@QAE@XZ; File::~File(void)
0x10053386  push    30h ; '0'; unsigned int
0x10053388  push    esi; Block
0x10053389  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005338e  pop     ecx
0x1005338f  pop     ecx
0x10053390  test    [ebp+var_20], 0FFFFFFFEh
0x10053397  jz      short loc_100533A1
0x10053399  lea     ecx, [ebp+var_20]; this
0x1005339c  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100533a1  xor     esi, esi
0x100533a3  test    [ebp+var_34], 0FFFFFFFEh
0x100533aa  jz      short loc_100533B4
0x100533ac  lea     ecx, [ebp+var_34]; this
0x100533af  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100533b4  lea     ecx, [edi+3C0h]; this
0x100533ba  call    ??1DynaBitmap@@QAE@XZ; DynaBitmap::~DynaBitmap(void)
0x100533bf  lea     ecx, [edi+3ACh]; this
0x100533c5  call    ??1DynaBitmap@@QAE@XZ; DynaBitmap::~DynaBitmap(void)
0x100533ca  lea     ecx, [edi+184h]; this
0x100533d0  call    ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x100533d5  mov     ecx, ebx; this
0x100533d7  call    ??1AbstractSpacemap@@QAE@XZ; AbstractSpacemap::~AbstractSpacemap(void)
0x100533dc  lea     ecx, [edi+0F0h]; this
0x100533e2  call    ??1Transaction@@QAE@XZ; Transaction::~Transaction(void)
0x100533e7  lea     ecx, [edi+0C0h]; this
0x100533ed  test    dword ptr [ecx], 0FFFFFFFEh
0x100533f3  jz      short loc_100533FA
0x100533f5  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100533fa  lea     ecx, [edi+98h]; this
0x10053400  call    ?Free@HashTable@@QAEXXZ; HashTable::Free(void)
0x10053405  lea     ecx, [edi+80h]; this
0x1005340b  call    ??1PageDescBlocks@@QAE@XZ; PageDescBlocks::~PageDescBlocks(void)
0x10053410  lea     eax, [edi+68h]
0x10053413  mov     [ebp+var_4], esi
0x10053416  push    eax; lpCriticalSection
0x10053417  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1005341d  lea     ecx, [edi+34h]; this
0x10053420  call    ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x10053425  lea     ecx, [edi+4]; this
0x10053428  call    ??1File@@QAE@XZ; File::~File(void)
0x1005342d  mov     ecx, [ebp+var_C]
0x10053430  mov     large fs:0, ecx
0x10053437  pop     ecx
0x10053438  pop     edi
0x10053439  pop     esi
0x1005343a  pop     ebx
0x1005343b  leave
0x1005343c  retn
0x10123eb0  jmp     ds:__imp____std_terminate
0x101252d1  nop
0x101252d2  nop
0x101252d3  mov     edx, [esp-4+arg_4]
0x101252d7  lea     eax, [edx+0Ch]
0x101252da  mov     ecx, [edx-38h]
0x101252dd  xor     ecx, eax; StackCookie
0x101252df  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101252e4  mov     eax, offset stru_101278CC
0x101252e9  jmp     ___CxxFrameHandler3
```
