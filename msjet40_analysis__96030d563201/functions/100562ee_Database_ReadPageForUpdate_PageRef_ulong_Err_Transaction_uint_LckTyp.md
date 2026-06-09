# Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint,LckTyp *)

- ea: `0x100562ee`
- end: `0x10056366`
- name: `?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@IPAW4LckTyp@@@Z`
- size: `120`
- prototype: `void __thiscall(Database *__hidden this, struct PageRef *, unsigned int, struct Err *, struct Transaction *, char, enum LckTyp *)`
- caller_count: `33`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1004f8e5`
- `0x10060337`
- `0x1006e465`
- `0x1006ed2c`
- `0x1006f09f`
- `0x1006f25e`
- `0x10071360`
- `0x10071ea0`
- `0x10072200`
- `0x10072900`
- `0x10072bb0`
- `0x10072e30`
- `0x10072fe0`
- `0x100732a0`
- `0x10073460`
- `0x10073780`
- `0x10073d70`
- `0x10077d07`
- `0x10077eb7`
- `0x100784b8`
- `0x10078568`
- `0x1007861f`
- `0x100786ab`
- `0x100787a8`
- `0x100794fa`
- `0x1007b618`
- `0x1007db60`
- `0x1007e635`
- `0x1007e894`
- `0x1007e91c`
- `0x100829a2`
- `0x10083cc7`
- `0x100841e6`

## callees

- `0x100562ee`
- `0x100575a6`
- `0x10074bb1`
- `0x10076c16`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100562ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100562ff`

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
0x100562ee  mov     edi, edi
0x100562f0  push    ebp
0x100562f1  mov     ebp, esp
0x100562f3  push    ecx
0x100562f4  push    ebx
0x100562f5  mov     ebx, ecx
0x100562f7  push    esi
0x100562f8  push    edi
0x100562f9  xor     edi, edi
0x100562fb  lea     eax, [ebx+68h]
0x100562fe  push    eax; lpCriticalSection
0x100562ff  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10056305  cmp     [ebx+60h], edi
0x10056308  jz      short loc_10056322
0x1005630a  cmp     dword ptr [ebx+60h], 3
0x1005630e  jz      short loc_10056322
0x10056310  mov     esi, [ebp+arg_8]
0x10056313  mov     ecx, ebx; this
0x10056315  push    esi; struct Err *
0x10056316  push    [ebp+arg_4]; unsigned int
0x10056319  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x1005631e  mov     edi, eax
0x10056320  jmp     short loc_10056332
0x10056322  mov     esi, [ebp+arg_8]
0x10056325  push    ecx
0x10056326  push    0FFFFF8EFh
0x1005632b  mov     ecx, esi
0x1005632d  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10056332  test    byte ptr [esi], 8
0x10056335  jnz     short loc_10056354
0x10056337  test    edi, edi
0x10056339  jz      short loc_10056354
0x1005633b  xor     eax, eax
0x1005633d  mov     ecx, edi; this
0x1005633f  push    eax; unsigned int
0x10056340  push    eax; unsigned int
0x10056341  push    eax; unsigned int
0x10056342  push    [ebp+arg_14]; enum LckTyp *
0x10056345  push    dword ptr [ebp+arg_10]; char
0x10056348  push    esi; struct Err *
0x10056349  push    [ebp+arg_C]; struct Transaction *
0x1005634c  push    [ebp+arg_0]; struct PageRef *
0x1005634f  call    ?ReadPageForUpdate@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@IPAW4LckTyp@@III@Z; PageDesc::ReadPageForUpdate(PageRef &,Transaction *,Err &,uint,LckTyp *,uint,uint,uint)
0x10056354  lea     eax, [ebx+68h]
0x10056357  push    eax; lpCriticalSection
0x10056358  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005635e  pop     edi
0x1005635f  pop     esi
0x10056360  pop     ebx
0x10056361  pop     ecx
0x10056362  pop     ebp
0x10056363  retn    18h
```
