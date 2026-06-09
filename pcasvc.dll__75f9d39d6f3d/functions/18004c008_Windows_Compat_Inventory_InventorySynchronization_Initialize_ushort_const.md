# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x18004c008`
- end: `0x18004c229`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800a1638`

## callees

- `0x18000dc08`
- `0x18004c008`
- `0x18004c574`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004c07c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004c07c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c0df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c0df`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004c1f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004c1f1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004c0f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004c0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c0fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c0fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c042`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c0a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c042`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c0a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c122`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004c157`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18004c157`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004c1c8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004c1c8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004c185`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004c185`

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
0x18004c008  mov     [rsp+arg_10], rbx
0x18004c00d  push    rsi
0x18004c00e  push    rdi
0x18004c00f  push    r14
0x18004c011  sub     rsp, 250h
0x18004c018  mov     rax, cs:__security_cookie
0x18004c01f  xor     rax, rsp
0x18004c022  mov     [rsp+268h+var_28], rax
0x18004c02a  mov     rsi, rdx
0x18004c02d  mov     rdi, rcx
0x18004c030  xor     edx, edx; Val
0x18004c032  lea     rcx, [rsp+268h+Name]; void *
0x18004c037  mov     r8d, 208h; Size
0x18004c03d  call    memset_0
0x18004c042  call    cs:__imp_GetCurrentProcessId
0x18004c048  mov     r14d, 104h
0x18004c04e  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x18004c055  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18004c05a  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18004c05e  mov     edx, r14d; unsigned __int64
0x18004c061  mov     r9, rsi
0x18004c064  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c069  mov     ebx, eax
0x18004c06b  test    eax, eax
0x18004c06d  js      loc_18004C1FB
0x18004c073  lea     r8, [rsp+268h+Name]; lpName
0x18004c078  xor     edx, edx; bInitialOwner
0x18004c07a  xor     ecx, ecx; lpMutexAttributes
0x18004c07c  call    cs:__imp_CreateMutexW
0x18004c082  mov     [rdi], rax
0x18004c085  test    rax, rax
0x18004c088  jnz     short loc_18004C0A8
0x18004c08a  call    cs:__imp_GetLastError
0x18004c090  mov     ebx, eax
0x18004c092  test    eax, eax
0x18004c094  jle     loc_18004C1F7
0x18004c09a  movzx   ebx, ax
0x18004c09d  or      ebx, 80070000h
0x18004c0a3  jmp     loc_18004C1F7
0x18004c0a8  call    cs:__imp_GetCurrentProcessId
0x18004c0ae  mov     r9, rsi
0x18004c0b1  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x18004c0b8  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18004c0bd  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18004c0c1  mov     rdx, r14; unsigned __int64
0x18004c0c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c0c9  mov     ebx, eax
0x18004c0cb  test    eax, eax
0x18004c0cd  js      loc_18004C1FB
0x18004c0d3  lea     r9, [rsp+268h+Name]; lpName
0x18004c0d8  xor     r8d, r8d; bInitialState
0x18004c0db  xor     edx, edx; bManualReset
0x18004c0dd  xor     ecx, ecx; lpEventAttributes
0x18004c0df  call    cs:__imp_CreateEventW
0x18004c0e5  mov     [rdi+10h], rax
0x18004c0e9  test    rax, rax
0x18004c0ec  jz      short loc_18004C08A
0x18004c0ee  mov     rcx, [rdi]; hHandle
0x18004c0f1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004c0f4  call    cs:__imp_WaitForSingleObject
0x18004c0fa  test    eax, eax
0x18004c0fc  jz      short loc_18004C122
0x18004c0fe  call    cs:__imp_GetLastError
0x18004c104  mov     ebx, eax
0x18004c106  test    eax, eax
0x18004c108  jle     short loc_18004C113
0x18004c10a  movzx   ebx, ax
0x18004c10d  or      ebx, 80070000h
0x18004c113  test    ebx, ebx
0x18004c115  mov     eax, 80004005h
0x18004c11a  cmovns  ebx, eax
0x18004c11d  jmp     loc_18004C1FB
0x18004c122  call    cs:__imp_GetCurrentProcessId
0x18004c128  mov     r9, rsi
0x18004c12b  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x18004c132  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18004c137  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18004c13b  mov     rdx, r14; unsigned __int64
0x18004c13e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c143  mov     ebx, eax
0x18004c145  test    eax, eax
0x18004c147  js      loc_18004C1EE
0x18004c14d  xor     edx, edx; bInheritHandle
0x18004c14f  lea     r8, [rsp+268h+Name]; lpName
0x18004c154  lea     ecx, [rdx+2]; dwDesiredAccess
0x18004c157  call    cs:__imp_OpenFileMappingW
0x18004c15d  mov     [rdi+8], rax
0x18004c161  test    rax, rax
0x18004c164  jnz     short loc_18004C1AF
0x18004c166  xor     r9d, r9d; dwMaximumSizeHigh
0x18004c169  lea     rax, [rsp+268h+Name]
0x18004c16e  mov     [rsp+268h+lpName], rax; lpName
0x18004c173  xor     edx, edx; lpFileMappingAttributes
0x18004c175  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004c179  mov     [rsp+268h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x18004c181  lea     r8d, [r9+4]; flProtect
0x18004c185  call    cs:__imp_CreateFileMappingW
0x18004c18b  mov     [rdi+8], rax
0x18004c18f  test    rax, rax
0x18004c192  jnz     short loc_18004C1AB
0x18004c194  call    cs:__imp_GetLastError
0x18004c19a  mov     ebx, eax
0x18004c19c  test    eax, eax
0x18004c19e  jle     short loc_18004C1EE
0x18004c1a0  movzx   ebx, ax
0x18004c1a3  or      ebx, 80070000h
0x18004c1a9  jmp     short loc_18004C1EE
0x18004c1ab  xor     bl, bl
0x18004c1ad  jmp     short loc_18004C1B1
0x18004c1af  mov     bl, 1
0x18004c1b1  xor     r9d, r9d; dwFileOffsetLow
0x18004c1b4  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18004c1bd  xor     r8d, r8d; dwFileOffsetHigh
0x18004c1c0  mov     edx, 0F001Fh; dwDesiredAccess
0x18004c1c5  mov     rcx, rax; hFileMappingObject
0x18004c1c8  call    cs:__imp_MapViewOfFile
0x18004c1ce  mov     [rdi+18h], rax
0x18004c1d2  test    rax, rax
0x18004c1d5  jz      short loc_18004C194
0x18004c1d7  test    bl, bl
0x18004c1d9  jnz     short loc_18004C1EC
0x18004c1db  mov     dword ptr [rax], 0
0x18004c1e1  mov     rax, [rdi+18h]
0x18004c1e5  mov     dword ptr [rax+4], 0
0x18004c1ec  xor     ebx, ebx
0x18004c1ee  mov     rcx, [rdi]; hMutex
0x18004c1f1  call    cs:__imp_ReleaseMutex
0x18004c1f7  test    ebx, ebx
0x18004c1f9  jns     short loc_18004C203
0x18004c1fb  mov     rcx, rdi; this
0x18004c1fe  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x18004c203  mov     eax, ebx
0x18004c205  mov     rcx, [rsp+268h+var_28]
0x18004c20d  xor     rcx, rsp; StackCookie
0x18004c210  call    __security_check_cookie
0x18004c215  mov     rbx, [rsp+268h+arg_10]
0x18004c21d  add     rsp, 250h
0x18004c224  pop     r14
0x18004c226  pop     rdi
0x18004c227  pop     rsi
0x18004c228  retn
```
