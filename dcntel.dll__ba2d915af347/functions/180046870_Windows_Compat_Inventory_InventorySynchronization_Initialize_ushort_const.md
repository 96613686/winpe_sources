# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x180046870`
- end: `0x180046a91`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800472dc`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18001286c`
- `0x180046870`
- `0x18004c2b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004695c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004695c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046a59`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180046a59`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800468e4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800468e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046947`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800468aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004698a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800468aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004698a`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800469bf`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800469bf`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800469ed`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800469ed`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046a30`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180046870  mov     [rsp+arg_10], rbx
0x180046875  push    rsi
0x180046876  push    rdi
0x180046877  push    r14
0x180046879  sub     rsp, 250h
0x180046880  mov     rax, cs:__security_cookie
0x180046887  xor     rax, rsp
0x18004688a  mov     [rsp+268h+var_28], rax
0x180046892  mov     rsi, rdx
0x180046895  mov     rdi, rcx
0x180046898  xor     edx, edx; Val
0x18004689a  lea     rcx, [rsp+268h+Name]; void *
0x18004689f  mov     r8d, 208h; Size
0x1800468a5  call    memset_0
0x1800468aa  call    cs:__imp_GetCurrentProcessId
0x1800468b0  mov     r14d, 104h
0x1800468b6  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x1800468bd  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x1800468c2  mov     [rsp+268h+dwMaximumSizeLow], eax
0x1800468c6  mov     edx, r14d; unsigned __int64
0x1800468c9  mov     r9, rsi
0x1800468cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800468d1  mov     ebx, eax
0x1800468d3  test    eax, eax
0x1800468d5  js      loc_180046A63
0x1800468db  lea     r8, [rsp+268h+Name]; lpName
0x1800468e0  xor     edx, edx; bInitialOwner
0x1800468e2  xor     ecx, ecx; lpMutexAttributes
0x1800468e4  call    cs:__imp_CreateMutexW
0x1800468ea  mov     [rdi], rax
0x1800468ed  test    rax, rax
0x1800468f0  jnz     short loc_180046910
0x1800468f2  call    cs:__imp_GetLastError
0x1800468f8  mov     ebx, eax
0x1800468fa  test    eax, eax
0x1800468fc  jle     loc_180046A5F
0x180046902  movzx   ebx, ax
0x180046905  or      ebx, 80070000h
0x18004690b  jmp     loc_180046A5F
0x180046910  call    cs:__imp_GetCurrentProcessId
0x180046916  mov     r9, rsi
0x180046919  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x180046920  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180046925  mov     [rsp+268h+dwMaximumSizeLow], eax
0x180046929  mov     rdx, r14; unsigned __int64
0x18004692c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046931  mov     ebx, eax
0x180046933  test    eax, eax
0x180046935  js      loc_180046A63
0x18004693b  lea     r9, [rsp+268h+Name]; lpName
0x180046940  xor     r8d, r8d; bInitialState
0x180046943  xor     edx, edx; bManualReset
0x180046945  xor     ecx, ecx; lpEventAttributes
0x180046947  call    cs:__imp_CreateEventW
0x18004694d  mov     [rdi+10h], rax
0x180046951  test    rax, rax
0x180046954  jz      short loc_1800468F2
0x180046956  mov     rcx, [rdi]; hHandle
0x180046959  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004695c  call    cs:__imp_WaitForSingleObject
0x180046962  test    eax, eax
0x180046964  jz      short loc_18004698A
0x180046966  call    cs:__imp_GetLastError
0x18004696c  mov     ebx, eax
0x18004696e  test    eax, eax
0x180046970  jle     short loc_18004697B
0x180046972  movzx   ebx, ax
0x180046975  or      ebx, 80070000h
0x18004697b  test    ebx, ebx
0x18004697d  mov     eax, 80004005h
0x180046982  cmovns  ebx, eax
0x180046985  jmp     loc_180046A63
0x18004698a  call    cs:__imp_GetCurrentProcessId
0x180046990  mov     r9, rsi
0x180046993  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x18004699a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18004699f  mov     [rsp+268h+dwMaximumSizeLow], eax
0x1800469a3  mov     rdx, r14; unsigned __int64
0x1800469a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800469ab  mov     ebx, eax
0x1800469ad  test    eax, eax
0x1800469af  js      loc_180046A56
0x1800469b5  xor     edx, edx; bInheritHandle
0x1800469b7  lea     r8, [rsp+268h+Name]; lpName
0x1800469bc  lea     ecx, [rdx+2]; dwDesiredAccess
0x1800469bf  call    cs:__imp_OpenFileMappingW
0x1800469c5  mov     [rdi+8], rax
0x1800469c9  test    rax, rax
0x1800469cc  jnz     short loc_180046A17
0x1800469ce  xor     r9d, r9d; dwMaximumSizeHigh
0x1800469d1  lea     rax, [rsp+268h+Name]
0x1800469d6  mov     [rsp+268h+lpName], rax; lpName
0x1800469db  xor     edx, edx; lpFileMappingAttributes
0x1800469dd  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800469e1  mov     [rsp+268h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x1800469e9  lea     r8d, [r9+4]; flProtect
0x1800469ed  call    cs:__imp_CreateFileMappingW
0x1800469f3  mov     [rdi+8], rax
0x1800469f7  test    rax, rax
0x1800469fa  jnz     short loc_180046A13
0x1800469fc  call    cs:__imp_GetLastError
0x180046a02  mov     ebx, eax
0x180046a04  test    eax, eax
0x180046a06  jle     short loc_180046A56
0x180046a08  movzx   ebx, ax
0x180046a0b  or      ebx, 80070000h
0x180046a11  jmp     short loc_180046A56
0x180046a13  xor     bl, bl
0x180046a15  jmp     short loc_180046A19
0x180046a17  mov     bl, 1
0x180046a19  xor     r9d, r9d; dwFileOffsetLow
0x180046a1c  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180046a25  xor     r8d, r8d; dwFileOffsetHigh
0x180046a28  mov     edx, 0F001Fh; dwDesiredAccess
0x180046a2d  mov     rcx, rax; hFileMappingObject
0x180046a30  call    cs:__imp_MapViewOfFile
0x180046a36  mov     [rdi+18h], rax
0x180046a3a  test    rax, rax
0x180046a3d  jz      short loc_1800469FC
0x180046a3f  test    bl, bl
0x180046a41  jnz     short loc_180046A54
0x180046a43  mov     dword ptr [rax], 0
0x180046a49  mov     rax, [rdi+18h]
0x180046a4d  mov     dword ptr [rax+4], 0
0x180046a54  xor     ebx, ebx
0x180046a56  mov     rcx, [rdi]; hMutex
0x180046a59  call    cs:__imp_ReleaseMutex
0x180046a5f  test    ebx, ebx
0x180046a61  jns     short loc_180046A6B
0x180046a63  mov     rcx, rdi; this
0x180046a66  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x180046a6b  mov     eax, ebx
0x180046a6d  mov     rcx, [rsp+268h+var_28]
0x180046a75  xor     rcx, rsp; StackCookie
0x180046a78  call    __security_check_cookie
0x180046a7d  mov     rbx, [rsp+268h+arg_10]
0x180046a85  add     rsp, 250h
0x180046a8c  pop     r14
0x180046a8e  pop     rdi
0x180046a8f  pop     rsi
0x180046a90  retn
```
