# Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)

- ea: `0x10023690`
- end: `0x1002371f`
- name: `?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z`
- size: `143`
- prototype: `void __thiscall(Database *__hidden this, struct PageRef *, unsigned int, char, struct Err *, struct Transaction *)`
- caller_count: `50`
- callee_count: `4`
- tags: ``

## callers

- `0x10010810`
- `0x100109e0`
- `0x10010bb0`
- `0x10010c60`
- `0x10010d60`
- `0x10010f50`
- `0x10011160`
- `0x100125e0`
- `0x10012b50`
- `0x10018b80`
- `0x1001c100`
- `0x1001f910`
- `0x10021d70`
- `0x10022030`
- `0x10028030`
- `0x1002a480`
- `0x1002d480`
- `0x10037550`
- `0x1003ab80`
- `0x1003b1d0`
- `0x1003b400`
- `0x1003c070`
- `0x1003d0e0`
- `0x1003d300`
- `0x10046f40`
- `0x10047000`
- `0x100471e0`
- `0x10047a60`
- `0x100486e0`
- `0x10048980`
- `0x10048c00`
- `0x10048e90`
- `0x10049140`
- `0x100493a0`
- `0x10049660`
- `0x10049810`
- `0x10049dd0`
- `0x10054200`
- `0x100543a0`
- `0x10057680`
- `0x100597a0`
- `0x10059970`
- `0x10059af0`
- `0x10059d00`
- `0x1005a260`
- `0x1005a340`
- `0x1005a420`
- `0x1005a590`
- `0x1005a7c0`
- `0x1005b3b0`

## callees

- `0x10023690`
- `0x10024b00`
- `0x100429a0`
- `0x1004eda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100236a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100236e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100236a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100236e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100236d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100236d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100236c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100236c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023710`

## pseudocode

```c
void __thiscall Database::ReadPage(
        Database *this,
        struct PageRef *a2,
        unsigned int a3,
        char a4,
        void **a5,
        struct Transaction *a6)
{
  struct _RTL_CRITICAL_SECTION *v7; // edi
  struct PageDesc *v8; // eax
  HANDLE *v9; // ebx
  struct Err *v10; // ecx

  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v8 = Database::FindOrCreate(this, a3, a5);
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    v9 = (HANDLE *)*((_DWORD *)v8 + 17);
    if ( !v9 )
      goto LABEL_6;
    LeaveCriticalSection(v7);
    if ( WaitForSingleObject(*v9, 0x1388u) == -1 )
      System::ErrGetLastError(v10);
    EnterCriticalSection(v7);
    v8 = Database::FindOrCreate(this, a3, a5);
    if ( (*(_BYTE *)a5 & 8) == 0 )
LABEL_6:
      PageDesc::ReadPage(v8, a2, a6, a4, (struct Err *)a5);
  }
  LeaveCriticalSection(v7);
}

```

## disassembly

```asm
0x10023690  mov     edi, edi
0x10023692  push    ebp
0x10023693  mov     ebp, esp
0x10023695  and     esp, 0FFFFFFF8h
0x10023698  push    ecx
0x10023699  push    ebx
0x1002369a  mov     ebx, ecx
0x1002369c  push    esi
0x1002369d  push    edi
0x1002369e  mov     [esp+10h+var_4], ebx
0x100236a2  lea     edi, [ebx+70h]
0x100236a5  push    edi; lpCriticalSection
0x100236a6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100236ac  mov     esi, [ebp+arg_C]
0x100236af  mov     ecx, ebx; this
0x100236b1  push    esi; struct Err *
0x100236b2  push    [ebp+arg_4]; unsigned int
0x100236b5  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x100236ba  test    byte ptr [esi], 8
0x100236bd  jnz     short loc_1002370F
0x100236bf  mov     ebx, [eax+44h]
0x100236c2  test    ebx, ebx
0x100236c4  jz      short loc_100236FE
0x100236c6  push    edi; lpCriticalSection
0x100236c7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100236cd  push    1388h; dwMilliseconds
0x100236d2  push    dword ptr [ebx]; hHandle
0x100236d4  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100236da  cmp     eax, 0FFFFFFFFh
0x100236dd  jnz     short loc_100236E5
0x100236df  push    esi
0x100236e0  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100236e5  push    edi; lpCriticalSection
0x100236e6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100236ec  mov     ecx, [esp+10h+var_4]; this
0x100236f0  push    esi; struct Err *
0x100236f1  push    [ebp+arg_4]; unsigned int
0x100236f4  call    ?FindOrCreate@Database@@IAEPAVPageDesc@@KAAVErr@@@Z; Database::FindOrCreate(ulong,Err &)
0x100236f9  test    byte ptr [esi], 8
0x100236fc  jnz     short loc_1002370F
0x100236fe  push    esi; struct Err *
0x100236ff  push    dword ptr [ebp+arg_8]; char
0x10023702  mov     ecx, eax; this
0x10023704  push    [ebp+arg_10]; struct Transaction *
0x10023707  push    [ebp+arg_0]; struct PageRef *
0x1002370a  call    ?ReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@IAAVErr@@@Z; PageDesc::ReadPage(PageRef &,Transaction *,uint,Err &)
0x1002370f  push    edi; lpCriticalSection
0x10023710  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10023716  pop     edi
0x10023717  pop     esi
0x10023718  pop     ebx
0x10023719  mov     esp, ebp
0x1002371b  pop     ebp
0x1002371c  retn    14h
```
