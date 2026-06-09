# Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint,LckTyp *)

- ea: `0x1005647e`
- end: `0x100564f6`
- name: `?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@IPAW4LckTyp@@@Z`
- size: `120`
- prototype: `void __thiscall(Database *__hidden this, struct PageRef *, unsigned int, struct Err *, struct Transaction *, char, enum LckTyp *)`
- caller_count: `33`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1004fa75`
- `0x100604c7`
- `0x1006e5f5`
- `0x1006eebc`
- `0x1006f22f`
- `0x1006f3ee`
- `0x100714f0`
- `0x10072030`
- `0x10072390`
- `0x10072a90`
- `0x10072d40`
- `0x10072fc0`
- `0x10073170`
- `0x10073430`
- `0x100735f0`
- `0x10073910`
- `0x10073f00`
- `0x10077e97`
- `0x10078047`
- `0x10078648`
- `0x100786f8`
- `0x100787af`
- `0x1007883b`
- `0x10078938`
- `0x1007968a`
- `0x1007b7a8`
- `0x1007dcf0`
- `0x1007e7c5`
- `0x1007ea24`
- `0x1007eaac`
- `0x10082b32`
- `0x10083e57`
- `0x10084376`

## callees

- `0x1005647e`
- `0x10057736`
- `0x10074d41`
- `0x10076da6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100564e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100564e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005648f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005648f`

## pseudocode

```c
void __thiscall Database::ReadPageForUpdate(
        Database *this,
        struct PageRef *a2,
        unsigned int a3,
        struct Err *a4,
        struct Transaction *a5,
        char a6,
        enum LckTyp *a7)
{
  PageDesc *v8; // edi
  int v9; // ecx
  struct Err *v10; // esi

  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( !*((_DWORD *)this + 24) || *((_DWORD *)this + 24) == 3 )
  {
    v10 = a4;
    Err::SetError(a4, -1809, v9);
  }
  else
  {
    v10 = a4;
    v8 = Database::FindOrCreate(this, a3, a4);
  }
  if ( (*(_BYTE *)v10 & 8) == 0 && v8 )
    PageDesc::ReadPageForUpdate(v8, a2, a5, v10, a6, a7, 0, 0, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
}

```

## disassembly

```asm
0x1005647e  mov     edi, edi
0x10056480  push    ebp
0x10056481  mov     ebp, esp
0x10056483  push    ecx
0x10056484  push    ebx
0x10056485  mov     ebx, ecx
0x10056487  push    esi
0x10056488  push    edi
0x10056489  xor     edi, edi
0x1005648b  lea     eax, [ebx+68h]
0x1005648e  push    eax; lpCriticalSection
0x1005648f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10056495  cmp     [ebx+60h], edi
0x10056498  jz      short loc_100564B2
0x1005649a  cmp     dword ptr [ebx+60h], 3
0x1005649e  jz      short loc_100564B2
0x100564a0  mov     esi, [ebp+arg_8]
0x100564a3  mov     ecx, ebx; this
0x100564a5  push    esi; struct Err *
0x100564a6  push    [ebp+arg_4]; unsigned int
0x100564a9  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x100564ae  mov     edi, eax
0x100564b0  jmp     short loc_100564C2
0x100564b2  mov     esi, [ebp+arg_8]
0x100564b5  push    ecx
0x100564b6  push    0FFFFF8EFh
0x100564bb  mov     ecx, esi
0x100564bd  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100564c2  test    byte ptr [esi], 8
0x100564c5  jnz     short loc_100564E4
0x100564c7  test    edi, edi
0x100564c9  jz      short loc_100564E4
0x100564cb  xor     eax, eax
0x100564cd  mov     ecx, edi; this
0x100564cf  push    eax; unsigned int
0x100564d0  push    eax; unsigned int
0x100564d1  push    eax; unsigned int
0x100564d2  push    [ebp+arg_14]; enum LckTyp *
0x100564d5  push    dword ptr [ebp+arg_10]; char
0x100564d8  push    esi; struct Err *
0x100564d9  push    [ebp+arg_C]; struct Transaction *
0x100564dc  push    [ebp+arg_0]; struct PageRef *
0x100564df  call    ?ReadPageForUpdate@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@IPAW4LckTyp@@III@Z; PageDesc::ReadPageForUpdate(PageRef &,Transaction *,Err &,uint,LckTyp *,uint,uint,uint)
0x100564e4  lea     eax, [ebx+68h]
0x100564e7  push    eax; lpCriticalSection
0x100564e8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100564ee  pop     edi
0x100564ef  pop     esi
0x100564f0  pop     ebx
0x100564f1  pop     ecx
0x100564f2  pop     ebp
0x100564f3  retn    18h
```
