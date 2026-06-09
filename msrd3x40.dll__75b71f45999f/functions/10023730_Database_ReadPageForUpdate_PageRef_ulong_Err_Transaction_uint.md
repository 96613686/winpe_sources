# Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)

- ea: `0x10023730`
- end: `0x100237d6`
- name: `?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z`
- size: `166`
- prototype: `void __thiscall(Database *__hidden this, struct PageRef *, unsigned int, struct Err *, struct Transaction *, char)`
- caller_count: `36`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x10011540`
- `0x10011f50`
- `0x10012190`
- `0x100125e0`
- `0x1001c3d0`
- `0x1001c8c0`
- `0x1001ccc0`
- `0x1001cf90`
- `0x10031660`
- `0x10037550`
- `0x1003c070`
- `0x1003d0e0`
- `0x1003d300`
- `0x1003f180`
- `0x1003f550`
- `0x100471e0`
- `0x10047a60`
- `0x10047eb0`
- `0x100481d0`
- `0x10048340`
- `0x100486e0`
- `0x10048980`
- `0x10048c00`
- `0x10048e90`
- `0x10049140`
- `0x100493a0`
- `0x10049660`
- `0x10049810`
- `0x10049dd0`
- `0x10050bc0`
- `0x10052cc0`
- `0x1005a7c0`
- `0x1005a9c0`
- `0x1005b1a0`
- `0x1005b290`
- `0x1005c7e0`

## callees

- `0x10023730`
- `0x10024b00`
- `0x10042ae0`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10023740`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10023740`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100237c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100237c9`

## pseudocode

```c
void __thiscall Database::ReadPageForUpdate(
        Database *this,
        struct PageRef *a2,
        unsigned int a3,
        void **a4,
        struct Transaction *a5,
        char a6)
{
  PageDesc *v7; // ebx
  int v8; // eax
  struct Err *v9; // esi

  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v8 = *((_DWORD *)this + 26);
  if ( !v8 || v8 == 3 )
  {
    v9 = (struct Err *)a4;
    if ( (int)*a4 < 8 )
    {
      if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
      {
        if ( a4[3] )
          operator delete[](a4[3]);
        if ( a4[4] )
          operator delete[](a4[4]);
      }
      *a4 = (void *)8;
      a4[1] = (void *)-1809;
      a4[2] = 0;
      a4[3] = 0;
      a4[4] = 0;
    }
  }
  else
  {
    v9 = (struct Err *)a4;
    v7 = Database::FindOrCreate(this, a3, a4);
  }
  if ( (*(_BYTE *)v9 & 8) == 0 && v7 )
    PageDesc::ReadPageForUpdate(v7, a2, a5, v9, a6);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
}

```

## disassembly

```asm
0x10023730  mov     edi, edi
0x10023732  push    ebp
0x10023733  mov     ebp, esp
0x10023735  push    ebx
0x10023736  push    esi
0x10023737  push    edi
0x10023738  mov     edi, ecx
0x1002373a  xor     ebx, ebx
0x1002373c  lea     eax, [edi+70h]
0x1002373f  push    eax; lpCriticalSection
0x10023740  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10023746  mov     eax, [edi+68h]
0x10023749  test    eax, eax
0x1002374b  jz      short loc_10023764
0x1002374d  cmp     eax, 3
0x10023750  jz      short loc_10023764
0x10023752  mov     esi, [ebp+arg_8]
0x10023755  mov     ecx, edi; this
0x10023757  push    esi; struct Err *
0x10023758  push    [ebp+arg_4]; unsigned int
0x1002375b  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x10023760  mov     ebx, eax
0x10023762  jmp     short loc_100237AB
0x10023764  mov     esi, [ebp+arg_8]
0x10023767  mov     eax, [esi]
0x10023769  cmp     eax, 8
0x1002376c  jge     short loc_100237AB
0x1002376e  test    eax, 0FFFFFFFEh
0x10023773  jz      short loc_10023795
0x10023775  mov     eax, [esi+0Ch]
0x10023778  test    eax, eax
0x1002377a  jz      short loc_10023785
0x1002377c  push    eax; Block
0x1002377d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10023782  add     esp, 4
0x10023785  mov     eax, [esi+10h]
0x10023788  test    eax, eax
0x1002378a  jz      short loc_10023795
0x1002378c  push    eax; Block
0x1002378d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10023792  add     esp, 4
0x10023795  mov     dword ptr [esi], 8
0x1002379b  mov     dword ptr [esi+4], 0FFFFF8EFh
0x100237a2  mov     [esi+8], ebx
0x100237a5  mov     [esi+0Ch], ebx
0x100237a8  mov     [esi+10h], ebx
0x100237ab  test    byte ptr [esi], 8
0x100237ae  jnz     short loc_100237C5
0x100237b0  test    ebx, ebx
0x100237b2  jz      short loc_100237C5
0x100237b4  push    dword ptr [ebp+arg_10]; char
0x100237b7  mov     ecx, ebx; this
0x100237b9  push    esi; struct Err *
0x100237ba  push    [ebp+arg_C]; struct Transaction *
0x100237bd  push    [ebp+arg_0]; struct PageRef *
0x100237c0  call    ?ReadPageForUpdate@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@I@Z; PageDesc::ReadPageForUpdate(PageRef &,Transaction *,Err &,uint)
0x100237c5  lea     eax, [edi+70h]
0x100237c8  push    eax; lpCriticalSection
0x100237c9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100237cf  pop     edi
0x100237d0  pop     esi
0x100237d1  pop     ebx
0x100237d2  pop     ebp
0x100237d3  retn    14h
```
