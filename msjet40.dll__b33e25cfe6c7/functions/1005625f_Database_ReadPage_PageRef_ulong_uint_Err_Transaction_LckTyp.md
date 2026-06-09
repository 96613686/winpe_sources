# Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *,LckTyp *)

- ea: `0x1005625f`
- end: `0x100562e8`
- name: `?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@PAW4LckTyp@@@Z`
- size: `137`
- prototype: `void __thiscall(Database *__hidden this, struct PageRef *, unsigned int, char, struct Err *, struct Transaction *, enum LckTyp *)`
- caller_count: `45`
- callee_count: `4`
- tags: ``

## callers

- `0x1004f8e5`
- `0x1005313d`
- `0x10054ab1`
- `0x10054d3f`
- `0x100558c8`
- `0x10055933`
- `0x100597d8`
- `0x1006dfba`
- `0x10071360`
- `0x10071ea0`
- `0x10072900`
- `0x10072bb0`
- `0x10072e30`
- `0x10072fe0`
- `0x100732a0`
- `0x10073460`
- `0x10073780`
- `0x10073d70`
- `0x10077c58`
- `0x10077d07`
- `0x1007840f`
- `0x1007873a`
- `0x10078870`
- `0x1007d3fe`
- `0x1007d519`
- `0x1007d5b9`
- `0x1007d66d`
- `0x1007d7b5`
- `0x1007d862`
- `0x1007e5d1`
- `0x1007e635`
- `0x1007ea67`
- `0x1007eeec`
- `0x1007ef78`
- `0x10081230`
- `0x100829a2`
- `0x10083fc0`
- `0x10086ee0`
- `0x100870e0`
- `0x10087230`
- `0x10087420`
- `0x100877d1`
- `0x100878a4`
- `0x10087977`
- `0x10087aad`

## callees

- `0x1005625f`
- `0x100575a6`
- `0x100610f0`
- `0x10076b16`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1005629f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1005629f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100562db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100562db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100562b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100562b1`

## pseudocode

```c
void __thiscall Database::ReadPage(
        Database *this,
        struct PageRef *a2,
        unsigned int a3,
        char a4,
        struct Err *a5,
        struct Transaction *a6,
        enum LckTyp *a7)
{
  struct _RTL_CRITICAL_SECTION *v8; // edi
  struct PageDesc *v9; // eax
  enum LckTyp *v10; // ecx
  HANDLE *v11; // ebx
  struct Err *v12; // ecx

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v9 = Database::FindOrCreate(this, a3, a5);
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    v11 = (HANDLE *)*((_DWORD *)v9 + 17);
    if ( !v11 )
      goto LABEL_6;
    LeaveCriticalSection(v8);
    if ( WaitForSingleObject(*v11, 0x1388u) == -1 )
      System::ErrGetLastError(v12);
    EnterCriticalSection(v8);
    v9 = Database::FindOrCreate(this, a3, a5);
    if ( (*(_BYTE *)a5 & 8) == 0 )
LABEL_6:
      PageDesc::ReadPage(v9, a2, a6, a4, a5, v10);
  }
  LeaveCriticalSection(v8);
}

```

## disassembly

```asm
0x1005625f  mov     edi, edi
0x10056261  push    ebp
0x10056262  mov     ebp, esp
0x10056264  push    ecx
0x10056265  push    ebx
0x10056266  mov     ebx, ecx
0x10056268  push    esi
0x10056269  push    edi
0x1005626a  mov     [ebp+var_4], ebx
0x1005626d  lea     edi, [ebx+68h]
0x10056270  push    edi; lpCriticalSection
0x10056271  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10056277  mov     esi, [ebp+arg_C]
0x1005627a  mov     ecx, ebx; this
0x1005627c  push    esi; struct Err *
0x1005627d  push    [ebp+arg_4]; unsigned int
0x10056280  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x10056285  test    byte ptr [esi], 8
0x10056288  jnz     short loc_100562DA
0x1005628a  mov     ebx, [eax+44h]
0x1005628d  test    ebx, ebx
0x1005628f  jz      short loc_100562C8
0x10056291  push    edi; lpCriticalSection
0x10056292  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10056298  push    1388h; dwMilliseconds
0x1005629d  push    dword ptr [ebx]; hHandle
0x1005629f  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100562a5  cmp     eax, 0FFFFFFFFh
0x100562a8  jnz     short loc_100562B0
0x100562aa  push    esi
0x100562ab  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100562b0  push    edi; lpCriticalSection
0x100562b1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100562b7  mov     ecx, [ebp+var_4]; this
0x100562ba  push    esi; struct Err *
0x100562bb  push    [ebp+arg_4]; unsigned int
0x100562be  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x100562c3  test    byte ptr [esi], 8
0x100562c6  jnz     short loc_100562DA
0x100562c8  push    ecx; enum LckTyp *
0x100562c9  push    esi; struct Err *
0x100562ca  push    dword ptr [ebp+arg_8]; char
0x100562cd  mov     ecx, eax; this
0x100562cf  push    [ebp+arg_10]; struct Transaction *
0x100562d2  push    [ebp+arg_0]; struct PageRef *
0x100562d5  call    ?ReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@IAAVErr@@PAW4LckTyp@@@Z; PageDesc::ReadPage(PageRef &,Transaction *,uint,Err &,LckTyp *)
0x100562da  push    edi; lpCriticalSection
0x100562db  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100562e1  pop     edi
0x100562e2  pop     esi
0x100562e3  pop     ebx
0x100562e4  leave
0x100562e5  retn    18h
```
