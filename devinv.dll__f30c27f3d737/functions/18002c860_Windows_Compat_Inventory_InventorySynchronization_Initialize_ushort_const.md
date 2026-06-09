# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x18002c860`
- end: `0x18002ca81`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002d2d0`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000dcec`
- `0x18002c860`
- `0x180030fe4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002c8d4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002c8d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ca49`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ca49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c937`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c937`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c94c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c94c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c89a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c97a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c89a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c97a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002ca20`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002ca20`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002c9dd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002c9dd`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002c9af`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002c9af`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::InventorySynchronization::Initialize(
        Windows::Compat::Inventory::InventorySynchronization *this,
        const unsigned __int16 *a2)
{
  signed int v4; // ebx
  HANDLE MutexW; // rax
  signed int v6; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE FileMappingW; // rax
  signed int v10; // eax
  char v11; // bl
  _DWORD *v12; // rax
  DWORD dwMaximumSizeLowb; // [rsp+20h] [rbp-248h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-248h]
  DWORD dwMaximumSizeLowa[2]; // [rsp+20h] [rbp-248h]
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF

  memset_0(Name, 0, 0x208u);
  dwMaximumSizeLowb = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsMutex%d", a2, dwMaximumSizeLowb);
  if ( v4 < 0 )
    goto LABEL_26;
  MutexW = CreateMutexW(0, 0, Name);
  *(_QWORD *)this = MutexW;
  if ( MutexW )
  {
    dwMaximumSizeLow[0] = GetCurrentProcessId();
    v4 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsEvent%d", a2, *(_QWORD *)dwMaximumSizeLow);
    if ( v4 < 0 )
    {
LABEL_26:
      Windows::Compat::Inventory::InventorySynchronization::Uninitialize(this);
      return (unsigned int)v4;
    }
    EventW = CreateEventW(0, 0, 0, Name);
    *((_QWORD *)this + 2) = EventW;
    if ( EventW )
    {
      if ( WaitForSingleObject(*(HANDLE *)this, 0xFFFFFFFF) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 >= 0 )
          v4 = -2147467259;
        goto LABEL_26;
      }
      dwMaximumSizeLowa[0] = GetCurrentProcessId();
      v4 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsMemory%d", a2, *(_QWORD *)dwMaximumSizeLowa);
      if ( v4 < 0 )
        goto LABEL_24;
      FileMappingW = OpenFileMappingW(2u, 0, Name);
      *((_QWORD *)this + 1) = FileMappingW;
      if ( FileMappingW )
      {
        v11 = 1;
      }
      else
      {
        FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 8u, Name);
        *((_QWORD *)this + 1) = FileMappingW;
        if ( !FileMappingW )
          goto LABEL_16;
        v11 = 0;
      }
      v12 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      *((_QWORD *)this + 3) = v12;
      if ( v12 )
      {
        if ( !v11 )
        {
          *v12 = 0;
          *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) = 0;
        }
        v4 = 0;
        goto LABEL_24;
      }
LABEL_16:
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
LABEL_24:
      ReleaseMutex(*(HANDLE *)this);
      goto LABEL_25;
    }
  }
  v6 = GetLastError();
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
LABEL_25:
  if ( v4 < 0 )
    goto LABEL_26;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c860  mov     [rsp+arg_10], rbx
0x18002c865  push    rsi
0x18002c866  push    rdi
0x18002c867  push    r14
0x18002c869  sub     rsp, 250h
0x18002c870  mov     rax, cs:__security_cookie
0x18002c877  xor     rax, rsp
0x18002c87a  mov     [rsp+268h+var_28], rax
0x18002c882  mov     rsi, rdx
0x18002c885  mov     rdi, rcx
0x18002c888  xor     edx, edx; Val
0x18002c88a  lea     rcx, [rsp+268h+Name]; void *
0x18002c88f  mov     r8d, 208h; Size
0x18002c895  call    memset_0
0x18002c89a  call    cs:__imp_GetCurrentProcessId
0x18002c8a0  mov     r14d, 104h
0x18002c8a6  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x18002c8ad  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18002c8b2  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18002c8b6  mov     edx, r14d; unsigned __int64
0x18002c8b9  mov     r9, rsi
0x18002c8bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c8c1  mov     ebx, eax
0x18002c8c3  test    eax, eax
0x18002c8c5  js      loc_18002CA53
0x18002c8cb  lea     r8, [rsp+268h+Name]; lpName
0x18002c8d0  xor     edx, edx; bInitialOwner
0x18002c8d2  xor     ecx, ecx; lpMutexAttributes
0x18002c8d4  call    cs:__imp_CreateMutexW
0x18002c8da  mov     [rdi], rax
0x18002c8dd  test    rax, rax
0x18002c8e0  jnz     short loc_18002C900
0x18002c8e2  call    cs:__imp_GetLastError
0x18002c8e8  mov     ebx, eax
0x18002c8ea  test    eax, eax
0x18002c8ec  jle     loc_18002CA4F
0x18002c8f2  movzx   ebx, ax
0x18002c8f5  or      ebx, 80070000h
0x18002c8fb  jmp     loc_18002CA4F
0x18002c900  call    cs:__imp_GetCurrentProcessId
0x18002c906  mov     r9, rsi
0x18002c909  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x18002c910  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18002c915  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18002c919  mov     rdx, r14; unsigned __int64
0x18002c91c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c921  mov     ebx, eax
0x18002c923  test    eax, eax
0x18002c925  js      loc_18002CA53
0x18002c92b  lea     r9, [rsp+268h+Name]; lpName
0x18002c930  xor     r8d, r8d; bInitialState
0x18002c933  xor     edx, edx; bManualReset
0x18002c935  xor     ecx, ecx; lpEventAttributes
0x18002c937  call    cs:__imp_CreateEventW
0x18002c93d  mov     [rdi+10h], rax
0x18002c941  test    rax, rax
0x18002c944  jz      short loc_18002C8E2
0x18002c946  mov     rcx, [rdi]; hHandle
0x18002c949  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c94c  call    cs:__imp_WaitForSingleObject
0x18002c952  test    eax, eax
0x18002c954  jz      short loc_18002C97A
0x18002c956  call    cs:__imp_GetLastError
0x18002c95c  mov     ebx, eax
0x18002c95e  test    eax, eax
0x18002c960  jle     short loc_18002C96B
0x18002c962  movzx   ebx, ax
0x18002c965  or      ebx, 80070000h
0x18002c96b  test    ebx, ebx
0x18002c96d  mov     eax, 80004005h
0x18002c972  cmovns  ebx, eax
0x18002c975  jmp     loc_18002CA53
0x18002c97a  call    cs:__imp_GetCurrentProcessId
0x18002c980  mov     r9, rsi
0x18002c983  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x18002c98a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18002c98f  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18002c993  mov     rdx, r14; unsigned __int64
0x18002c996  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c99b  mov     ebx, eax
0x18002c99d  test    eax, eax
0x18002c99f  js      loc_18002CA46
0x18002c9a5  xor     edx, edx; bInheritHandle
0x18002c9a7  lea     r8, [rsp+268h+Name]; lpName
0x18002c9ac  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002c9af  call    cs:__imp_OpenFileMappingW
0x18002c9b5  mov     [rdi+8], rax
0x18002c9b9  test    rax, rax
0x18002c9bc  jnz     short loc_18002CA07
0x18002c9be  xor     r9d, r9d; dwMaximumSizeHigh
0x18002c9c1  lea     rax, [rsp+268h+Name]
0x18002c9c6  mov     [rsp+268h+lpName], rax; lpName
0x18002c9cb  xor     edx, edx; lpFileMappingAttributes
0x18002c9cd  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18002c9d1  mov     [rsp+268h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x18002c9d9  lea     r8d, [r9+4]; flProtect
0x18002c9dd  call    cs:__imp_CreateFileMappingW
0x18002c9e3  mov     [rdi+8], rax
0x18002c9e7  test    rax, rax
0x18002c9ea  jnz     short loc_18002CA03
0x18002c9ec  call    cs:__imp_GetLastError
0x18002c9f2  mov     ebx, eax
0x18002c9f4  test    eax, eax
0x18002c9f6  jle     short loc_18002CA46
0x18002c9f8  movzx   ebx, ax
0x18002c9fb  or      ebx, 80070000h
0x18002ca01  jmp     short loc_18002CA46
0x18002ca03  xor     bl, bl
0x18002ca05  jmp     short loc_18002CA09
0x18002ca07  mov     bl, 1
0x18002ca09  xor     r9d, r9d; dwFileOffsetLow
0x18002ca0c  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18002ca15  xor     r8d, r8d; dwFileOffsetHigh
0x18002ca18  mov     edx, 0F001Fh; dwDesiredAccess
0x18002ca1d  mov     rcx, rax; hFileMappingObject
0x18002ca20  call    cs:__imp_MapViewOfFile
0x18002ca26  mov     [rdi+18h], rax
0x18002ca2a  test    rax, rax
0x18002ca2d  jz      short loc_18002C9EC
0x18002ca2f  test    bl, bl
0x18002ca31  jnz     short loc_18002CA44
0x18002ca33  mov     dword ptr [rax], 0
0x18002ca39  mov     rax, [rdi+18h]
0x18002ca3d  mov     dword ptr [rax+4], 0
0x18002ca44  xor     ebx, ebx
0x18002ca46  mov     rcx, [rdi]; hMutex
0x18002ca49  call    cs:__imp_ReleaseMutex
0x18002ca4f  test    ebx, ebx
0x18002ca51  jns     short loc_18002CA5B
0x18002ca53  mov     rcx, rdi; this
0x18002ca56  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x18002ca5b  mov     eax, ebx
0x18002ca5d  mov     rcx, [rsp+268h+var_28]
0x18002ca65  xor     rcx, rsp; StackCookie
0x18002ca68  call    __security_check_cookie
0x18002ca6d  mov     rbx, [rsp+268h+arg_10]
0x18002ca75  add     rsp, 250h
0x18002ca7c  pop     r14
0x18002ca7e  pop     rdi
0x18002ca7f  pop     rsi
0x18002ca80  retn
```
