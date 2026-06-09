# Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *,LckTyp *)

- ea: `0x100563ef`
- end: `0x10056478`
- name: `?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@PAW4LckTyp@@@Z`
- size: `137`
- prototype: `void __thiscall(Database *__hidden this, struct PageRef *, unsigned int, char, struct Err *, struct Transaction *, enum LckTyp *)`
- caller_count: `45`
- callee_count: `4`
- tags: ``

## callers

- `0x1004fa75`
- `0x100532cd`
- `0x10054c41`
- `0x10054ecf`
- `0x10055a58`
- `0x10055ac3`
- `0x10059968`
- `0x1006e14a`
- `0x100714f0`
- `0x10072030`
- `0x10072a90`
- `0x10072d40`
- `0x10072fc0`
- `0x10073170`
- `0x10073430`
- `0x100735f0`
- `0x10073910`
- `0x10073f00`
- `0x10077de8`
- `0x10077e97`
- `0x1007859f`
- `0x100788ca`
- `0x10078a00`
- `0x1007d58e`
- `0x1007d6a9`
- `0x1007d749`
- `0x1007d7fd`
- `0x1007d945`
- `0x1007d9f2`
- `0x1007e761`
- `0x1007e7c5`
- `0x1007ebf7`
- `0x1007f07c`
- `0x1007f108`
- `0x100813c0`
- `0x10082b32`
- `0x10084150`
- `0x10087070`
- `0x10087270`
- `0x100873c0`
- `0x100875b0`
- `0x10087961`
- `0x10087a34`
- `0x10087b07`
- `0x10087c3d`

## callees

- `0x100563ef`
- `0x10057736`
- `0x10061284`
- `0x10076ca6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1005642f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1005642f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1005646b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1005646b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056401`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056441`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056401`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056441`

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
0x100563ef  mov     edi, edi
0x100563f1  push    ebp
0x100563f2  mov     ebp, esp
0x100563f4  push    ecx
0x100563f5  push    ebx
0x100563f6  mov     ebx, ecx
0x100563f8  push    esi
0x100563f9  push    edi
0x100563fa  mov     [ebp+var_4], ebx
0x100563fd  lea     edi, [ebx+68h]
0x10056400  push    edi; lpCriticalSection
0x10056401  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10056407  mov     esi, [ebp+arg_C]
0x1005640a  mov     ecx, ebx; this
0x1005640c  push    esi; struct Err *
0x1005640d  push    [ebp+arg_4]; unsigned int
0x10056410  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x10056415  test    byte ptr [esi], 8
0x10056418  jnz     short loc_1005646A
0x1005641a  mov     ebx, [eax+44h]
0x1005641d  test    ebx, ebx
0x1005641f  jz      short loc_10056458
0x10056421  push    edi; lpCriticalSection
0x10056422  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10056428  push    1388h; dwMilliseconds
0x1005642d  push    dword ptr [ebx]; hHandle
0x1005642f  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x10056435  cmp     eax, 0FFFFFFFFh
0x10056438  jnz     short loc_10056440
0x1005643a  push    esi
0x1005643b  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10056440  push    edi; lpCriticalSection
0x10056441  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10056447  mov     ecx, [ebp+var_4]; this
0x1005644a  push    esi; struct Err *
0x1005644b  push    [ebp+arg_4]; unsigned int
0x1005644e  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x10056453  test    byte ptr [esi], 8
0x10056456  jnz     short loc_1005646A
0x10056458  push    ecx; enum LckTyp *
0x10056459  push    esi; struct Err *
0x1005645a  push    dword ptr [ebp+arg_8]; char
0x1005645d  mov     ecx, eax; this
0x1005645f  push    [ebp+arg_10]; struct Transaction *
0x10056462  push    [ebp+arg_0]; struct PageRef *
0x10056465  call    ?ReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@IAAVErr@@PAW4LckTyp@@@Z; PageDesc::ReadPage(PageRef &,Transaction *,uint,Err &,LckTyp *)
0x1005646a  push    edi; lpCriticalSection
0x1005646b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10056471  pop     edi
0x10056472  pop     esi
0x10056473  pop     ebx
0x10056474  leave
0x10056475  retn    18h
```
