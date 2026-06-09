# Database::ReadPages(Semaphore *,ulong,ulong,Err &)

- ea: `0x10023420`
- end: `0x10023688`
- name: `?ReadPages@Database@@QAEXPAVSemaphore@@KKAAVErr@@@Z`
- size: `616`
- prototype: `void __thiscall(Database *__hidden this, struct Semaphore *, unsigned int, struct Err *, struct Err *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10021d70`
- `0x1004f3b0`

## callees

- `0x1000f750`
- `0x10023420`
- `0x10024b00`
- `0x1002e5c0`
- `0x10041c70`
- `0x1004e980`
- `0x1004ebd0`
- `0x1004eda0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1002345b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1002345b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002347e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100234e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100235bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002347e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100234e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100235bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x100234d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x100234d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100234b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002367d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100234b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002367d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10023638`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10023638`

## pseudocode

```c
void __thiscall Database::ReadPages(Database *this, HANDLE *a2, unsigned int a3, struct Err *a4, void **a5)
{
  Database *v5; // eax
  struct Err *v6; // ecx
  struct Err *v7; // ebx
  unsigned int v8; // esi
  struct PageDesc *v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // esi
  struct Err *v11; // ecx
  unsigned int v12; // esi
  struct PageDesc *v13; // eax
  struct Page *Pages; // eax
  bool v15; // zf
  Database *v16; // esi
  unsigned int v17; // eax
  struct PageDesc *v18; // eax
  struct PageDesc *v19; // esi
  unsigned int v20; // edx
  __int16 v21; // cx
  PageVersion *v22; // ecx
  int v23; // eax
  DWORD TickCount; // eax
  unsigned int v25; // [esp+10h] [ebp-34h] BYREF
  void *Block; // [esp+1Ch] [ebp-28h]
  void *v27; // [esp+20h] [ebp-24h]
  unsigned int v28; // [esp+24h] [ebp-20h]
  unsigned int v29; // [esp+28h] [ebp-1Ch]
  unsigned int v30; // [esp+2Ch] [ebp-18h]
  LPCRITICAL_SECTION lpCriticalSection; // [esp+30h] [ebp-14h]
  Database *v32; // [esp+34h] [ebp-10h]
  int v33; // [esp+40h] [ebp-4h]

  v5 = this;
  v32 = this;
  if ( a2 )
  {
    if ( !ResetEvent(*a2) )
      System::ErrGetLastError(v6);
    v5 = v32;
  }
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)v5 + 112);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 112));
    v7 = a4;
    v8 = 0;
    if ( a4 )
    {
      do
      {
        v9 = Database::FindOrCreate(v32, v8 + a3, a5);
        if ( (*(_BYTE *)a5 & 8) != 0 )
          break;
        ++*((_WORD *)v9 + 38);
        ++v8;
        *((_DWORD *)v9 + 17) = a2;
      }
      while ( v8 < (unsigned int)a4 );
    }
    LeaveCriticalSection(lpCriticalSection);
    if ( (*(_BYTE *)a5 & 8) != 0 )
    {
      v7 = (struct Err *)v8;
    }
    else
    {
      Pages = System::AllocatePages((struct QMsg *)&Sys, a4);
      v15 = (*(_BYTE *)a5 & 8) == 0;
      v29 = (unsigned int)Pages;
      if ( v15 )
      {
        v16 = v32;
        File::Read((Database *)((char *)v32 + 4), a3 << 11, Pages, (_DWORD)a4 << 11, (struct Err *)a5);
        if ( (*(_BYTE *)a5 & 8) == 0 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v32 + 112));
          v17 = 0;
          v30 = 0;
          if ( a4 )
          {
            do
            {
              v18 = Database::FindOrCreate(v16, a3 + v17, a5);
              v19 = v18;
              v20 = v29 + (v30 << 11);
              v15 = (*(_BYTE *)a5 & 8) == 0;
              v28 = v20;
              if ( v15 )
              {
                v21 = *((_WORD *)v18 + 38) - 1;
                v15 = *((_BYTE *)v18 + 80) == 0;
                *((_WORD *)v18 + 38) = v21;
                if ( v15
                  && !v21
                  && ((v22 = (struct PageDesc *)((char *)v18 + 28), v23 = *((_DWORD *)v18 + 7) & 7, v23 == 2) || v23 == 3) )
                {
                  PageVersion::Discard(v22, *((struct Database **)v19 + 5));
                  *((_DWORD *)v19 + 7) = v28 & 0xFFFFFF00 ^ (*((_DWORD *)v19 + 7) & 0xF8 | 1);
                  TickCount = GetTickCount();
                  ++*((_WORD *)v19 + 38);
                  *((_DWORD *)v19 + 18) = TickCount;
                }
                else
                {
                  System::FreePages((struct Page *)&Sys, v20);
                  ++*((_WORD *)v19 + 38);
                }
              }
              else
              {
                System::FreePages((struct Page *)&Sys, v29 + (v30 << 11));
              }
              v16 = v32;
              v17 = v30 + 1;
              v30 = v17;
            }
            while ( v17 < (unsigned int)a4 );
          }
          v10 = lpCriticalSection;
          LeaveCriticalSection(lpCriticalSection);
          goto LABEL_12;
        }
        System::FreePages((struct Page *)&Sys, v29);
      }
    }
    v10 = lpCriticalSection;
LABEL_12:
    if ( a2 && !SetEvent(*a2) )
      System::ErrGetLastError(v11);
    EnterCriticalSection(v10);
    v12 = 0;
    if ( v7 )
    {
      do
      {
        v25 = 1;
        v33 = 0;
        v13 = Database::FindOrCreate(v32, v12 + a3, (void **)&v25);
        --*((_WORD *)v13 + 38);
        *((_DWORD *)v13 + 17) = 0;
        v33 = -1;
        if ( (v25 & 0xFFFFFFFE) != 0 )
        {
          if ( Block )
            operator delete[](Block);
          if ( v27 )
            operator delete[](v27);
        }
        ++v12;
      }
      while ( v12 < (unsigned int)v7 );
    }
    LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x10023420  mov     edi, edi
0x10023422  push    ebp
0x10023423  mov     ebp, esp
0x10023425  push    0FFFFFFFFh
0x10023427  push    offset ?ReclaimPDSpace@Database@@QAEXXZ_SEH
0x1002342c  mov     eax, large fs:0
0x10023432  push    eax
0x10023433  sub     esp, 28h
0x10023436  push    ebx
0x10023437  push    esi
0x10023438  push    edi
0x10023439  mov     eax, ___security_cookie
0x1002343e  xor     eax, ebp
0x10023440  push    eax
0x10023441  lea     eax, [ebp+var_C]
0x10023444  mov     large fs:0, eax
0x1002344a  mov     eax, ecx
0x1002344c  mov     [ebp+var_10], eax
0x1002344f  mov     ecx, [ebp+arg_0]
0x10023452  mov     edi, [ebp+arg_C]
0x10023455  test    ecx, ecx
0x10023457  jz      short loc_1002346E
0x10023459  push    dword ptr [ecx]; hEvent
0x1002345b  call    ds:__imp__ResetEvent@4; ResetEvent(x)
0x10023461  test    eax, eax
0x10023463  jnz     short loc_1002346B
0x10023465  push    edi
0x10023466  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002346b  mov     eax, [ebp+var_10]
0x1002346e  test    byte ptr [edi], 8
0x10023471  jnz     loc_10023559
0x10023477  add     eax, 70h ; 'p'
0x1002347a  push    eax; lpCriticalSection
0x1002347b  mov     [ebp+lpCriticalSection], eax
0x1002347e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10023484  mov     ebx, [ebp+arg_8]
0x10023487  xor     esi, esi
0x10023489  test    ebx, ebx
0x1002348b  jz      short loc_100234B3
0x1002348d  nop     dword ptr [eax]
0x10023490  mov     eax, [ebp+arg_4]
0x10023493  mov     ecx, [ebp+var_10]; this
0x10023496  add     eax, esi
0x10023498  push    edi; struct Err *
0x10023499  push    eax; unsigned int
0x1002349a  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x1002349f  test    byte ptr [edi], 8
0x100234a2  jnz     short loc_100234B3
0x100234a4  inc     word ptr [eax+4Ch]
0x100234a8  inc     esi
0x100234a9  mov     ecx, [ebp+arg_0]
0x100234ac  mov     [eax+44h], ecx
0x100234af  cmp     esi, ebx
0x100234b1  jb      short loc_10023490
0x100234b3  push    [ebp+lpCriticalSection]; lpCriticalSection
0x100234b6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100234bc  test    byte ptr [edi], 8
0x100234bf  jz      loc_1002356D
0x100234c5  mov     ebx, esi
0x100234c7  mov     esi, [ebp+lpCriticalSection]
0x100234ca  mov     eax, [ebp+arg_0]
0x100234cd  test    eax, eax
0x100234cf  jz      short loc_100234E3
0x100234d1  push    dword ptr [eax]; hEvent
0x100234d3  call    ds:__imp__SetEvent@4; SetEvent(x)
0x100234d9  test    eax, eax
0x100234db  jnz     short loc_100234E3
0x100234dd  push    edi
0x100234de  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100234e3  push    esi; lpCriticalSection
0x100234e4  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100234ea  xor     esi, esi
0x100234ec  test    ebx, ebx
0x100234ee  jz      short loc_10023550
0x100234f0  mov     [ebp+var_34], 1
0x100234f7  mov     ecx, [ebp+var_10]; this
0x100234fa  lea     eax, [ebp+var_34]
0x100234fd  push    eax; struct Err *
0x100234fe  mov     eax, [ebp+arg_4]
0x10023501  add     eax, esi
0x10023503  mov     [ebp+var_4], 0
0x1002350a  push    eax; unsigned int
0x1002350b  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x10023510  dec     word ptr [eax+4Ch]
0x10023514  mov     dword ptr [eax+44h], 0
0x1002351b  mov     [ebp+var_4], 0FFFFFFFFh
0x10023522  test    [ebp+var_34], 0FFFFFFFEh
0x10023529  jz      short loc_1002354B
0x1002352b  mov     eax, [ebp+Block]
0x1002352e  test    eax, eax
0x10023530  jz      short loc_1002353B
0x10023532  push    eax; Block
0x10023533  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10023538  add     esp, 4
0x1002353b  mov     eax, [ebp+var_24]
0x1002353e  test    eax, eax
0x10023540  jz      short loc_1002354B
0x10023542  push    eax; Block
0x10023543  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10023548  add     esp, 4
0x1002354b  inc     esi
0x1002354c  cmp     esi, ebx
0x1002354e  jb      short loc_100234F0
0x10023550  push    [ebp+lpCriticalSection]; lpCriticalSection
0x10023553  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10023559  mov     ecx, [ebp+var_C]
0x1002355c  mov     large fs:0, ecx
0x10023563  pop     ecx
0x10023564  pop     edi
0x10023565  pop     esi
0x10023566  pop     ebx
0x10023567  mov     esp, ebp
0x10023569  pop     ebp
0x1002356a  retn    10h
0x1002356d  push    edi
0x1002356e  push    ebx; struct Err *
0x1002356f  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x10023574  call    ?AllocatePages@System@@QAEPAVPage@@KAAVErr@@@Z; System::AllocatePages(ulong,Err &)
0x10023579  test    byte ptr [edi], 8
0x1002357c  mov     [ebp+var_1C], eax
0x1002357f  jnz     loc_100234C7
0x10023585  mov     esi, [ebp+var_10]
0x10023588  mov     edx, ebx
0x1002358a  push    edi; struct Err *
0x1002358b  shl     edx, 0Bh
0x1002358e  push    edx; nNumberOfBytesToRead
0x1002358f  push    eax; lpBuffer
0x10023590  mov     eax, [ebp+arg_4]
0x10023593  lea     ecx, [esi+4]; this
0x10023596  shl     eax, 0Bh
0x10023599  push    eax; lDistanceToMove
0x1002359a  call    ?Read@File@@QAEXKPAXKAAVErr@@@Z; File::Read(ulong,void *,ulong,Err &)
0x1002359f  test    byte ptr [edi], 8
0x100235a2  jz      short loc_100235B7
0x100235a4  push    ebx
0x100235a5  push    [ebp+var_1C]; unsigned int
0x100235a8  mov     ecx, offset ?Sys@@3VSystem@@A; struct Page *
0x100235ad  call    ?FreePages@System@@QAEXPAVPage@@K@Z; System::FreePages(Page *,ulong)
0x100235b2  jmp     loc_100234C7
0x100235b7  lea     eax, [esi+70h]
0x100235ba  push    eax; lpCriticalSection
0x100235bb  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100235c1  xor     eax, eax
0x100235c3  mov     [ebp+var_18], eax
0x100235c6  test    ebx, ebx
0x100235c8  jz      loc_10023679
0x100235ce  mov     edi, edi
0x100235d0  add     eax, [ebp+arg_4]
0x100235d3  mov     ecx, esi; this
0x100235d5  push    edi; struct Err *
0x100235d6  push    eax; unsigned int
0x100235d7  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x100235dc  mov     edx, [ebp+var_18]
0x100235df  mov     esi, eax
0x100235e1  shl     edx, 0Bh
0x100235e4  add     edx, [ebp+var_1C]
0x100235e7  test    byte ptr [edi], 8
0x100235ea  mov     [ebp+var_20], edx
0x100235ed  jnz     short loc_1002365A
0x100235ef  mov     cx, [esi+4Ch]
0x100235f3  dec     cx
0x100235f5  cmp     byte ptr [esi+50h], 0
0x100235f9  mov     [esi+4Ch], cx
0x100235fd  jnz     short loc_10023647
0x100235ff  test    cx, cx
0x10023602  jnz     short loc_10023647
0x10023604  mov     eax, [esi+1Ch]
0x10023607  lea     ecx, [esi+1Ch]; this
0x1002360a  and     eax, 7
0x1002360d  cmp     eax, 2
0x10023610  jz      short loc_10023617
0x10023612  cmp     eax, 3
0x10023615  jnz     short loc_10023647
0x10023617  push    dword ptr [esi+14h]; struct Database *
0x1002361a  call    ?Discard@PageVersion@@QAEXAAVDatabase@@@Z; PageVersion::Discard(Database &)
0x1002361f  mov     eax, [esi+1Ch]
0x10023622  mov     ecx, [ebp+var_20]
0x10023625  and     eax, 0F8h
0x1002362a  or      eax, 1
0x1002362d  and     ecx, 0FFFFFF00h
0x10023633  xor     eax, ecx
0x10023635  mov     [esi+1Ch], eax
0x10023638  call    ds:__imp__GetTickCount@0; GetTickCount()
0x1002363e  inc     word ptr [esi+4Ch]
0x10023642  mov     [esi+48h], eax
0x10023645  jmp     short loc_10023667
0x10023647  push    1
0x10023649  push    edx; unsigned int
0x1002364a  mov     ecx, offset ?Sys@@3VSystem@@A; struct Page *
0x1002364f  call    ?FreePages@System@@QAEXPAVPage@@K@Z; System::FreePages(Page *,ulong)
0x10023654  inc     word ptr [esi+4Ch]
0x10023658  jmp     short loc_10023667
0x1002365a  push    1
0x1002365c  push    edx; unsigned int
0x1002365d  mov     ecx, offset ?Sys@@3VSystem@@A; struct Page *
0x10023662  call    ?FreePages@System@@QAEXPAVPage@@K@Z; System::FreePages(Page *,ulong)
0x10023667  mov     eax, [ebp+var_18]
0x1002366a  mov     esi, [ebp+var_10]
0x1002366d  inc     eax
0x1002366e  mov     [ebp+var_18], eax
0x10023671  cmp     eax, ebx
0x10023673  jb      loc_100235D0
0x10023679  mov     esi, [ebp+lpCriticalSection]
0x1002367c  push    esi; lpCriticalSection
0x1002367d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10023683  jmp     loc_100234CA
0x100605c0  lea     ecx, [ebp+var_34]; this
0x100605c3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100605cd  nop
0x100605ce  nop
0x100605cf  mov     edx, [esp-4+arg_4]
0x100605d3  lea     eax, [edx+0Ch]
0x100605d6  mov     ecx, [edx-38h]
0x100605d9  xor     ecx, eax; StackCookie
0x100605db  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100605e0  mov     eax, offset stru_10063474
0x100605e5  jmp     ___CxxFrameHandler3
```
