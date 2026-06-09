# CFileReader::Initialize(void *)

- ea: `0x180073720`
- end: `0x18007397e`
- name: `?Initialize@CFileReader@@QEAA_NPEAX@Z`
- size: `606`
- prototype: `bool(CFileReader *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18009ff54`

## callees

- `0x180022bd4`
- `0x180073720`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073965`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800738d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800738d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007376c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007376c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800737ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800737ad`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800737d5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800737d5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800738c4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800738c4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180073859`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180073859`

## string_xrefs

- `0x180073888`: `CFileReader::Initialize: CreateFileMapping failed %d.`
- `0x1800738a6`: `CFileReader::Initialize: CreateFileMapping failed %d.`
- `0x1800737ff`: `CFileReader::Initialize: GetFileSizeEx failed %d.`
- `0x180073827`: `CFileReader::Initialize: GetFileSizeEx failed %d.`
- `0x1800738f4`: `ParseRegistryFile: MapViewOfFile failed %d.`
- `0x18007391f`: `ParseRegistryFile: MapViewOfFile failed %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CFileReader::Initialize(union _LARGE_INTEGER *this, void *a2)
{
  DWORD LastError; // ebx
  char v5; // di
  void (*v6)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v7; // rdx
  HANDLE FileMappingW; // rax
  LPVOID v9; // rax
  DWORD v10; // eax
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  int Data; // [rsp+78h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+58h] BYREF

  LastError = GetLastError();
  this[1].QuadPart = (LONGLONG)a2;
  hKey = 0;
  v5 = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableMapping", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
      this->LowPart = 1;
  }
  if ( this->LowPart )
    goto LABEL_32;
  if ( !GetFileSizeEx(a2, this + 4) )
  {
    LastError = GetLastError();
    Type = LastError;
    if ( !*(_DWORD *)&g_dwDebugLevel )
    {
LABEL_15:
      v5 = 0;
LABEL_32:
      XKey::Free((XKey *)&hKey);
      SetLastError(LastError);
      return v5;
    }
    v6 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CFileReader::Initialize: GetFileSizeEx failed %d.", LastError);
      }
      goto LABEL_15;
    }
    v7 = L"CFileReader::Initialize: GetFileSizeEx failed %d.";
LABEL_11:
    v6(2u, v7, LastError);
    goto LABEL_15;
  }
  FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
  this[2].QuadPart = (LONGLONG)FileMappingW;
  if ( !FileMappingW )
  {
    LastError = GetLastError();
    Type = LastError;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_15;
    v6 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"CFileReader::Initialize: CreateFileMapping failed %d.", LastError);
      goto LABEL_15;
    }
    v7 = L"CFileReader::Initialize: CreateFileMapping failed %d.";
    goto LABEL_11;
  }
  v9 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  this[3].QuadPart = (LONGLONG)v9;
  if ( v9 )
  {
    this[5].QuadPart = (LONGLONG)v9;
    this[6].QuadPart = (LONGLONG)v9 + this[4].QuadPart;
    goto LABEL_32;
  }
  v10 = GetLastError();
  Type = v10;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"ParseRegistryFile: MapViewOfFile failed %d.", v10);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"ParseRegistryFile: MapViewOfFile failed %d.", v10);
    }
  }
  XKey::Free((XKey *)&hKey);
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x180073720  push    rbp
0x180073722  push    rbx
0x180073723  push    rdi
0x180073724  push    r12
0x180073726  push    r13
0x180073728  push    r14
0x18007372a  push    r15
0x18007372c  mov     rbp, rsp
0x18007372f  sub     rsp, 30h
0x180073733  mov     r12, rdx
0x180073736  mov     r14, rcx
0x180073739  call    cs:__imp_GetLastError
0x18007373f  mov     ebx, eax
0x180073741  mov     [r14+8], r12
0x180073745  xor     r13d, r13d
0x180073748  mov     [rbp+hKey], r13
0x18007374c  lea     rax, [rbp+hKey]
0x180073750  mov     [rsp+30h+phkResult], rax; phkResult
0x180073755  mov     r9d, 20019h; samDesired
0x18007375b  xor     r8d, r8d; ulOptions
0x18007375e  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180073765  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007376c  call    cs:__imp_RegOpenKeyExW
0x180073772  lea     edi, [r13+1]
0x180073776  test    eax, eax
0x180073778  jnz     short loc_1800737C5
0x18007377a  mov     [rbp+Type], r13d
0x18007377e  mov     [rbp+Data], r13d
0x180073782  mov     [rbp+cbData], 4
0x180073789  lea     rax, [rbp+cbData]
0x18007378d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180073792  lea     rax, [rbp+Data]
0x180073796  mov     [rsp+30h+phkResult], rax; lpData
0x18007379b  lea     r9, [rbp+Type]; lpType
0x18007379f  xor     r8d, r8d; lpReserved
0x1800737a2  lea     rdx, aDisablemapping; "DisableMapping"
0x1800737a9  mov     rcx, [rbp+hKey]; hKey
0x1800737ad  call    cs:__imp_RegQueryValueExW
0x1800737b3  test    eax, eax
0x1800737b5  jnz     short loc_1800737C5
0x1800737b7  cmp     [rbp+Type], 4
0x1800737bb  jnz     short loc_1800737C5
0x1800737bd  cmp     [rbp+Data], edi
0x1800737c0  jnz     short loc_1800737C5
0x1800737c2  mov     [r14], edi
0x1800737c5  cmp     [r14], r13d
0x1800737c8  jnz     loc_180073959
0x1800737ce  lea     rdx, [r14+20h]; lpFileSize
0x1800737d2  mov     rcx, r12; hFile
0x1800737d5  call    cs:__imp_GetFileSizeEx
0x1800737db  test    eax, eax
0x1800737dd  jnz     short loc_180073843
0x1800737df  call    cs:__imp_GetLastError
0x1800737e5  mov     ebx, eax
0x1800737e7  mov     [rbp+Type], eax
0x1800737ea  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800737f1  jz      short loc_18007383B
0x1800737f3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800737fa  test    rax, rax
0x1800737fd  jz      short loc_180073815
0x1800737ff  lea     rdx, aCfilereaderIni_0; "CFileReader::Initialize: GetFileSizeEx "...
0x180073806  mov     r8d, ebx
0x180073809  mov     ecx, 2
0x18007380e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073813  jmp     short loc_18007383B
0x180073815  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18007381c  jz      short loc_18007383B
0x18007381e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073825  jz      short loc_18007383B
0x180073827  lea     rdx, aCfilereaderIni_0; "CFileReader::Initialize: GetFileSizeEx "...
0x18007382e  mov     r8d, ebx
0x180073831  mov     ecx, 2; unsigned int
0x180073836  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18007383b  mov     dil, r13b
0x18007383e  jmp     loc_180073959
0x180073843  mov     [rsp+30h+lpcbData], r13; lpName
0x180073848  mov     dword ptr [rsp+30h+phkResult], r13d; dwMaximumSizeLow
0x18007384d  xor     r9d, r9d; dwMaximumSizeHigh
0x180073850  xor     edx, edx; lpFileMappingAttributes
0x180073852  lea     r8d, [r9+2]; flProtect
0x180073856  mov     rcx, r12; hFile
0x180073859  call    cs:__imp_CreateFileMappingW
0x18007385f  mov     [r14+10h], rax
0x180073863  test    rax, rax
0x180073866  jnz     short loc_1800738B2
0x180073868  call    cs:__imp_GetLastError
0x18007386e  mov     ebx, eax
0x180073870  mov     [rbp+Type], eax
0x180073873  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18007387a  jz      short loc_18007383B
0x18007387c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073883  test    rax, rax
0x180073886  jz      short loc_180073894
0x180073888  lea     rdx, aCfilereaderIni; "CFileReader::Initialize: CreateFileMapp"...
0x18007388f  jmp     loc_180073806
0x180073894  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18007389b  jz      short loc_18007383B
0x18007389d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800738a4  jz      short loc_18007383B
0x1800738a6  lea     rdx, aCfilereaderIni; "CFileReader::Initialize: CreateFileMapp"...
0x1800738ad  jmp     loc_18007382E
0x1800738b2  mov     [rsp+30h+phkResult], r13; dwNumberOfBytesToMap
0x1800738b7  xor     r9d, r9d; dwFileOffsetLow
0x1800738ba  xor     r8d, r8d; dwFileOffsetHigh
0x1800738bd  lea     edx, [r9+4]; dwDesiredAccess
0x1800738c1  mov     rcx, rax; hFileMappingObject
0x1800738c4  call    cs:__imp_MapViewOfFile
0x1800738ca  mov     [r14+18h], rax
0x1800738ce  test    rax, rax
0x1800738d1  jnz     short loc_18007394A
0x1800738d3  call    cs:__imp_GetLastError
0x1800738d9  mov     [rbp+Type], eax
0x1800738dc  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800738e3  jz      short loc_180073931
0x1800738e5  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800738ec  test    r9, r9
0x1800738ef  jz      short loc_18007390A
0x1800738f1  mov     r8d, eax
0x1800738f4  lea     rdx, aParseregistryf_32; "ParseRegistryFile: MapViewOfFile failed"...
0x1800738fb  mov     ecx, 2
0x180073900  mov     rax, r9
0x180073903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073908  jmp     short loc_180073931
0x18007390a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180073911  jz      short loc_180073931
0x180073913  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18007391a  jz      short loc_180073931
0x18007391c  mov     r8d, eax
0x18007391f  lea     rdx, aParseregistryf_32; "ParseRegistryFile: MapViewOfFile failed"...
0x180073926  mov     ecx, 2; unsigned int
0x18007392b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073930  nop
0x180073931  lea     rcx, [rbp+hKey]; this
0x180073935  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x18007393a  nop
0x18007393b  mov     ecx, 0Dh; dwErrCode
0x180073940  call    cs:__imp_SetLastError
0x180073946  xor     al, al
0x180073948  jmp     short loc_18007396E
0x18007394a  mov     [r14+28h], rax
0x18007394e  mov     rdx, [r14+20h]
0x180073952  add     rdx, rax
0x180073955  mov     [r14+30h], rdx
0x180073959  lea     rcx, [rbp+hKey]; this
0x18007395d  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180073962  nop
0x180073963  mov     ecx, ebx; dwErrCode
0x180073965  call    cs:__imp_SetLastError
0x18007396b  mov     al, dil
0x18007396e  add     rsp, 30h
0x180073972  pop     r15
0x180073974  pop     r14
0x180073976  pop     r13
0x180073978  pop     r12
0x18007397a  pop     rdi
0x18007397b  pop     rbx
0x18007397c  pop     rbp
0x18007397d  retn
```
