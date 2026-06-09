# InitImageSizeCache

- ea: `0x180486824`
- end: `0x180486bcb`
- name: `InitImageSizeCache`
- size: `935`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18048633c`
- `0x180486450`
- `0x1804865c8`
- `0x18048670c`
- `0x180a3f8d0`

## callees

- `0x180486824`
- `0x1807b5a24`
- `0x1810c2cb6`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!OpenFileMappingW` at `0x180486955`
- `KERNEL32!OpenFileMappingW` at `0x180486955`
- `KERNEL32!MapViewOfFile` at `0x180486980`
- `KERNEL32!MapViewOfFile` at `0x180486acd`
- `KERNEL32!MapViewOfFile` at `0x180486980`
- `KERNEL32!MapViewOfFile` at `0x180486acd`
- `KERNEL32!SetFilePointer` at `0x180486a80`
- `KERNEL32!SetFilePointer` at `0x180486a80`
- `KERNEL32!CreateFileW` at `0x180486a2d`
- `KERNEL32!CreateFileW` at `0x180486a2d`
- `KERNEL32!GetFileSize` at `0x180486a5e`
- `KERNEL32!GetFileSize` at `0x180486a5e`
- `KERNEL32!CreateMutexW` at `0x180486911`
- `KERNEL32!CreateMutexW` at `0x180486911`
- `KERNEL32!SetEndOfFile` at `0x180486a89`
- `KERNEL32!SetEndOfFile` at `0x180486a89`
- `KERNEL32!CreateFileMappingW` at `0x180486aa4`
- `KERNEL32!CreateFileMappingW` at `0x180486aa4`
- `KERNEL32!FlushViewOfFile` at `0x180486b36`
- `KERNEL32!FlushViewOfFile` at `0x180486b36`
- `KERNEL32!UnmapViewOfFile` at `0x180486b58`
- `KERNEL32!UnmapViewOfFile` at `0x180486b58`
- `KERNEL32!ReleaseMutex` at `0x180486b82`
- `KERNEL32!ReleaseMutex` at `0x180486b82`
- `KERNEL32!GetLastError` at `0x180486a45`
- `KERNEL32!GetLastError` at `0x180486a45`
- `KERNEL32!CloseHandle` at `0x180486b6d`
- `KERNEL32!CloseHandle` at `0x180486b8b`
- `KERNEL32!CloseHandle` at `0x180486b9a`
- `KERNEL32!CloseHandle` at `0x180486b6d`
- `KERNEL32!CloseHandle` at `0x180486b8b`
- `KERNEL32!CloseHandle` at `0x180486b9a`
- `KERNEL32!WaitForSingleObject` at `0x180486930`
- `KERNEL32!WaitForSingleObject` at `0x180486930`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804868c2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804868d1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804868c2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804868d1`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1804869fd`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1804869fd`

## string_xrefs

- `0x1804868eb`: `Local\MSIMGSIZECacheMapLow`
- `0x1804868d7`: `Local\MSIMGSIZECacheMutexLow`
- `0x1804868f2`: `Local\MSIMGSIZECacheMapAC`
- `0x1804868de`: `Local\MSIMGSIZECacheMutexAC`
- `0x180486906`: `Local\MSIMGSIZECacheMap`
- `0x1804868ff`: `Local\MSIMGSIZECacheMutex`

## pseudocode

```c
__int64 InitImageSizeCache()
{
  unsigned int v0; // ebx
  __int64 FileW; // rsi
  _DWORD *v3; // rdi
  int v4; // r15d
  char Bool; // al
  const WCHAR *v6; // r8
  const WCHAR *v7; // r12
  HANDLE MutexW; // rax
  void *v9; // r14
  HANDLE v10; // rax
  _DWORD *v11; // rax
  HANDLE FileMappingW; // rax
  char v13; // al
  BOOL v14; // [rsp+44h] [rbp-284h]
  WCHAR FileName[2]; // [rsp+70h] [rbp-258h] BYREF
  _BYTE v16[524]; // [rsp+74h] [rbp-254h] BYREF

  v0 = 0;
  if ( dword_18158C06C )
    goto LABEL_2;
  FileW = -1;
  v3 = 0;
  if ( (Microsoft_IEEnableBits & 8) != 0 )
    McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, MSHTML_INITIMAGESIZECACHE_START, 0, 0);
  v4 = 1;
  dword_18158C06C = 1;
  if ( (unsigned __int8)IEConfiguration_GetBool(536870916) )
  {
    Bool = IEConfiguration_GetBool(536870915);
    v6 = L"Local\\MSIMGSIZECacheMutexAC";
    if ( !Bool )
      v6 = L"Local\\MSIMGSIZECacheMutexLow";
    v7 = L"Local\\MSIMGSIZECacheMapAC";
    if ( !Bool )
      v7 = L"Local\\MSIMGSIZECacheMapLow";
  }
  else
  {
    v6 = L"Local\\MSIMGSIZECacheMutex";
    v7 = L"Local\\MSIMGSIZECacheMap";
  }
  MutexW = CreateMutexW(0, 0, v6);
  v9 = MutexW;
  if ( !MutexW || WaitForSingleObject(MutexW, 0xFA0u) )
    goto LABEL_35;
  if ( !lpBaseAddress )
  {
    v10 = OpenFileMappingW(0xF001Fu, 0, v7);
    hObject = v10;
    if ( v10 )
    {
      v11 = MapViewOfFile(v10, 0xF001Fu, 0, 0, 0xBFE0u);
      v3 = v11;
      if ( !v11 )
        goto LABEL_35;
      if ( *v11 == -892801257 && v11[1] == 2 )
        v4 = 0;
      if ( v4 )
        goto LABEL_35;
    }
    else
    {
      *(_DWORD *)FileName = 0;
      memset_0(v16, 0, 0x204u);
      if ( (unsigned int)GetBrowserProfileDataFilePath(
                           FilePathStore::BROWSERPROFILEDATA_FILEPATH_ImageSizeCache,
                           0,
                           FileName,
                           260) )
        goto LABEL_35;
      FileW = (__int64)CreateFileW(FileName, 0xC0000000, 3u, 0, 4u, 0, 0);
      if ( FileW == -1 )
        goto LABEL_35;
      v14 = GetLastError() != 183;
      if ( GetFileSize((HANDLE)FileW, 0) != 49120 )
      {
        v14 = 1;
        SetFilePointer((HANDLE)FileW, 49120, 0, 0);
        SetEndOfFile((HANDLE)FileW);
      }
      FileMappingW = CreateFileMappingW((HANDLE)FileW, 0, 4u, 0, 0, v7);
      hObject = FileMappingW;
      if ( !FileMappingW )
        goto LABEL_35;
      v3 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0xBFE0u);
      if ( !v3 )
        goto LABEL_35;
      v13 = 0;
      if ( v14 || *v3 != -892801257 || v3[1] != 2 )
      {
        memset_0(v3, 0, 0xBFE0u);
        *v3 = -892801257;
        v3[1] = 2;
        v13 = 1;
      }
      if ( v13 && !FlushViewOfFile(v3, 0xBFE0u) )
        goto LABEL_35;
    }
    lpBaseAddress = v3;
LABEL_35:
    if ( !lpBaseAddress )
    {
      if ( v3 )
        UnmapViewOfFile(v3);
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
    }
  }
  if ( v9 )
  {
    ReleaseMutex(v9);
    CloseHandle(v9);
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( (Microsoft_IEEnableBits & 8) != 0 )
    McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, MSHTML_INITIMAGESIZECACHE_STOP, 0, 0);
LABEL_2:
  LOBYTE(v0) = lpBaseAddress != 0;
  return v0;
}

```

## disassembly

```asm
0x180486824  push    rbx
0x180486826  push    rsi
0x180486827  push    rdi
0x180486828  push    r12
0x18048682a  push    r13
0x18048682c  push    r14
0x18048682e  push    r15
0x180486830  sub     rsp, 290h
0x180486837  mov     rax, cs:__security_cookie
0x18048683e  xor     rax, rsp
0x180486841  mov     [rsp+2C8h+var_48], rax
0x180486849  xor     ebx, ebx
0x18048684b  cmp     cs:dword_18158C06C, ebx
0x180486851  jz      short loc_180486882
0x180486853  cmp     cs:lpBaseAddress, rbx
0x18048685a  setnz   bl
0x18048685d  mov     eax, ebx
0x18048685f  mov     rcx, [rsp+2C8h+var_48]
0x180486867  xor     rcx, rsp; StackCookie
0x18048686a  call    __security_check_cookie
0x18048686f  add     rsp, 290h
0x180486876  pop     r15
0x180486878  pop     r14
0x18048687a  pop     r13
0x18048687c  pop     r12
0x18048687e  pop     rdi
0x18048687f  pop     rsi
0x180486880  pop     rbx
0x180486881  retn
0x180486882  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180486886  mov     [rsp+2C8h+var_280], rsi
0x18048688b  mov     rdi, rbx
0x18048688e  test    byte ptr cs:Microsoft_IEEnableBits, 8
0x180486895  jz      short loc_1804868B0
0x180486897  xor     r9d, r9d
0x18048689a  xor     r8d, r8d
0x18048689d  lea     rdx, MSHTML_INITIMAGESIZECACHE_START
0x1804868a4  lea     rcx, BERP_IE_Context
0x1804868ab  call    McTemplateU0pq_EventWriteTransfer
0x1804868b0  mov     r15d, 1
0x1804868b6  mov     cs:dword_18158C06C, r15d
0x1804868bd  mov     ecx, 20000004h
0x1804868c2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1804868c8  test    al, al
0x1804868ca  jz      short loc_1804868FF
0x1804868cc  mov     ecx, 20000003h
0x1804868d1  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1804868d7  lea     rcx, aLocalMsimgsize; "Local\\MSIMGSIZECacheMutexLow"
0x1804868de  lea     r8, aLocalMsimgsize_4; "Local\\MSIMGSIZECacheMutexAC"
0x1804868e5  test    al, al
0x1804868e7  cmovz   r8, rcx
0x1804868eb  lea     rcx, aLocalMsimgsize_2; "Local\\MSIMGSIZECacheMapLow"
0x1804868f2  lea     r12, aLocalMsimgsize_0; "Local\\MSIMGSIZECacheMapAC"
0x1804868f9  cmovz   r12, rcx
0x1804868fd  jmp     short loc_18048690D
0x1804868ff  lea     r8, Name; "Local\\MSIMGSIZECacheMutex"
0x180486906  lea     r12, aLocalMsimgsize_3; "Local\\MSIMGSIZECacheMap"
0x18048690d  xor     edx, edx; bInitialOwner
0x18048690f  xor     ecx, ecx; lpMutexAttributes
0x180486911  call    cs:__imp_CreateMutexW
0x180486917  mov     r14, rax
0x18048691a  mov     [rsp+2C8h+var_270], rax
0x18048691f  test    rax, rax
0x180486922  jz      loc_180486B47
0x180486928  mov     edx, 0FA0h; dwMilliseconds
0x18048692d  mov     rcx, rax; hHandle
0x180486930  call    cs:__imp_WaitForSingleObject
0x180486936  test    eax, eax
0x180486938  jnz     loc_180486B47
0x18048693e  cmp     cs:lpBaseAddress, rbx
0x180486945  jnz     loc_180486B7A
0x18048694b  mov     r8, r12; lpName
0x18048694e  xor     edx, edx; bInheritHandle
0x180486950  mov     ecx, 0F001Fh; dwDesiredAccess
0x180486955  call    cs:__imp_OpenFileMappingW
0x18048695b  mov     cs:hObject, rax
0x180486962  test    rax, rax
0x180486965  jz      short loc_1804869D3
0x180486967  mov     r13d, 0BFE0h
0x18048696d  mov     [rsp+2C8h+dwNumberOfBytesToMap], r13; dwNumberOfBytesToMap
0x180486972  xor     r9d, r9d; dwFileOffsetLow
0x180486975  xor     r8d, r8d; dwFileOffsetHigh
0x180486978  mov     edx, 0F001Fh; dwDesiredAccess
0x18048697d  mov     rcx, rax; hFileMappingObject
0x180486980  call    cs:__imp_MapViewOfFile
0x180486986  mov     rdi, rax
0x180486989  mov     [rsp+2C8h+var_278], rax
0x18048698e  test    rax, rax
0x180486991  jz      loc_180486B47
0x180486997  cmp     dword ptr [rax], 0CAC8EF17h
0x18048699d  jnz     short loc_1804869A8
0x18048699f  cmp     dword ptr [rax+4], 2
0x1804869a3  jnz     short loc_1804869A8
0x1804869a5  mov     r15d, ebx
0x1804869a8  mov     [rsp+2C8h+var_268], r15d
0x1804869ad  jmp     short loc_1804869C5
0x1804869af  xor     ebx, ebx
0x1804869b1  mov     r14, [rsp+2C8h+var_270]
0x1804869b6  mov     rsi, [rsp+2C8h+var_280]
0x1804869bb  mov     rdi, [rsp+2C8h+var_278]
0x1804869c0  jmp     loc_180486B47
0x1804869c5  test    r15d, r15d
0x1804869c8  jz      loc_180486B40
0x1804869ce  jmp     loc_180486B47
0x1804869d3  mov     dword ptr [rsp+2C8h+FileName], ebx
0x1804869d7  xor     edx, edx; Val
0x1804869d9  mov     r8d, 204h; Size
0x1804869df  lea     rcx, [rsp+2C8h+var_254]; void *
0x1804869e4  call    memset_0
0x1804869e9  mov     r9d, 104h
0x1804869ef  lea     r8, [rsp+2C8h+FileName]
0x1804869f4  xor     edx, edx
0x1804869f6  mov     rcx, cs:?BROWSERPROFILEDATA_FILEPATH_ImageSizeCache@FilePathStore@@3UBROWSERPROFILEDATA_FILEPATHID@1@B; FilePathStore::BROWSERPROFILEDATA_FILEPATHID const FilePathStore::BROWSERPROFILEDATA_FILEPATH_ImageSizeCache
0x1804869fd  call    cs:__imp_GetBrowserProfileDataFilePath
0x180486a03  test    eax, eax
0x180486a05  jnz     loc_180486B47
0x180486a0b  mov     [rsp+2C8h+hTemplateFile], rbx; hTemplateFile
0x180486a10  mov     [rsp+2C8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180486a14  mov     dword ptr [rsp+2C8h+dwNumberOfBytesToMap], 4; dwCreationDisposition
0x180486a1c  xor     r9d, r9d; lpSecurityAttributes
0x180486a1f  mov     edx, 0C0000000h; dwDesiredAccess
0x180486a24  lea     r8d, [rax+3]; dwShareMode
0x180486a28  lea     rcx, [rsp+2C8h+FileName]; lpFileName
0x180486a2d  call    cs:__imp_CreateFileW
0x180486a33  mov     rsi, rax
0x180486a36  mov     [rsp+2C8h+var_280], rax
0x180486a3b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180486a3f  jz      loc_180486B47
0x180486a45  call    cs:__imp_GetLastError
0x180486a4b  mov     ecx, ebx
0x180486a4d  cmp     eax, 0B7h
0x180486a52  setnz   cl
0x180486a55  mov     [rsp+2C8h+var_284], ecx
0x180486a59  xor     edx, edx; lpFileSizeHigh
0x180486a5b  mov     rcx, rsi; hFile
0x180486a5e  call    cs:__imp_GetFileSize
0x180486a64  mov     r13d, 0BFE0h
0x180486a6a  cmp     eax, r13d
0x180486a6d  jz      short loc_180486A8F
0x180486a6f  mov     [rsp+2C8h+var_284], r15d
0x180486a74  xor     r9d, r9d; dwMoveMethod
0x180486a77  xor     r8d, r8d; lpDistanceToMoveHigh
0x180486a7a  mov     edx, r13d; lDistanceToMove
0x180486a7d  mov     rcx, rsi; hFile
0x180486a80  call    cs:__imp_SetFilePointer
0x180486a86  mov     rcx, rsi; hFile
0x180486a89  call    cs:__imp_SetEndOfFile
0x180486a8f  mov     qword ptr [rsp+2C8h+dwFlagsAndAttributes], r12; lpName
0x180486a94  mov     dword ptr [rsp+2C8h+dwNumberOfBytesToMap], ebx; dwMaximumSizeLow
0x180486a98  xor     r9d, r9d; dwMaximumSizeHigh
0x180486a9b  xor     edx, edx; lpFileMappingAttributes
0x180486a9d  lea     r8d, [r9+4]; flProtect
0x180486aa1  mov     rcx, rsi; hFile
0x180486aa4  call    cs:__imp_CreateFileMappingW
0x180486aaa  mov     cs:hObject, rax
0x180486ab1  test    rax, rax
0x180486ab4  jz      loc_180486B47
0x180486aba  mov     [rsp+2C8h+dwNumberOfBytesToMap], r13; dwNumberOfBytesToMap
0x180486abf  xor     r9d, r9d; dwFileOffsetLow
0x180486ac2  xor     r8d, r8d; dwFileOffsetHigh
0x180486ac5  mov     edx, 0F001Fh; dwDesiredAccess
0x180486aca  mov     rcx, rax; hFileMappingObject
0x180486acd  call    cs:__imp_MapViewOfFile
0x180486ad3  mov     rdi, rax
0x180486ad6  mov     [rsp+2C8h+var_278], rax
0x180486adb  test    rax, rax
0x180486ade  jz      short loc_180486B47
0x180486ae0  mov     al, bl
0x180486ae2  cmp     [rsp+2C8h+var_284], ebx
0x180486ae6  jnz     short loc_180486AF6
0x180486ae8  cmp     dword ptr [rdi], 0CAC8EF17h
0x180486aee  jnz     short loc_180486AF6
0x180486af0  cmp     dword ptr [rdi+4], 2
0x180486af4  jz      short loc_180486B17
0x180486af6  mov     r8, r13; Size
0x180486af9  xor     edx, edx; Val
0x180486afb  mov     rcx, rdi; void *
0x180486afe  call    memset_0
0x180486b03  mov     dword ptr [rdi], 0CAC8EF17h
0x180486b09  mov     dword ptr [rdi+4], 2
0x180486b10  mov     al, r15b
0x180486b13  mov     [rsp+2C8h+var_288], al
0x180486b17  jmp     short loc_180486B2C
0x180486b19  xor     ebx, ebx
0x180486b1b  mov     r14, [rsp+2C8h+var_270]
0x180486b20  mov     rsi, [rsp+2C8h+var_280]
0x180486b25  mov     rdi, [rsp+2C8h+var_278]
0x180486b2a  jmp     short loc_180486B47
0x180486b2c  test    al, al
0x180486b2e  jz      short loc_180486B40
0x180486b30  mov     rdx, r13; dwNumberOfBytesToFlush
0x180486b33  mov     rcx, rdi; lpBaseAddress
0x180486b36  call    cs:__imp_FlushViewOfFile
0x180486b3c  test    eax, eax
0x180486b3e  jz      short loc_180486B47
0x180486b40  mov     cs:lpBaseAddress, rdi
0x180486b47  cmp     cs:lpBaseAddress, rbx
0x180486b4e  jnz     short loc_180486B7A
0x180486b50  test    rdi, rdi
0x180486b53  jz      short loc_180486B5E
0x180486b55  mov     rcx, rdi; lpBaseAddress
0x180486b58  call    cs:__imp_UnmapViewOfFile
0x180486b5e  mov     rax, cs:hObject
0x180486b65  test    rax, rax
0x180486b68  jz      short loc_180486B7A
0x180486b6a  mov     rcx, rax; hObject
0x180486b6d  call    cs:__imp_CloseHandle
0x180486b73  mov     cs:hObject, rbx
0x180486b7a  test    r14, r14
0x180486b7d  jz      short loc_180486B91
0x180486b7f  mov     rcx, r14; hMutex
0x180486b82  call    cs:__imp_ReleaseMutex
0x180486b88  mov     rcx, r14; hObject
0x180486b8b  call    cs:__imp_CloseHandle
0x180486b91  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180486b95  jz      short loc_180486BA0
0x180486b97  mov     rcx, rsi; hObject
0x180486b9a  call    cs:__imp_CloseHandle
0x180486ba0  test    byte ptr cs:Microsoft_IEEnableBits, 8
0x180486ba7  jz      loc_180486853
0x180486bad  xor     r9d, r9d
0x180486bb0  xor     r8d, r8d
0x180486bb3  lea     rdx, MSHTML_INITIMAGESIZECACHE_STOP
0x180486bba  lea     rcx, BERP_IE_Context
0x180486bc1  call    McTemplateU0pq_EventWriteTransfer
0x180486bc6  jmp     loc_180486853
0x1810cdcdf  push    rbp
0x1810cdce1  sub     rsp, 40h
0x1810cdce5  mov     rbp, rdx
0x1810cdce8  mov     rax, [rcx]
0x1810cdceb  xor     ecx, ecx
0x1810cdced  cmp     dword ptr [rax], 0C0000006h
0x1810cdcf3  setz    cl
0x1810cdcf6  mov     eax, ecx
0x1810cdcf8  add     rsp, 40h
0x1810cdcfc  pop     rbp
0x1810cdcfd  retn
0x1810cdcff  push    rbp
0x1810cdd01  sub     rsp, 40h
0x1810cdd05  mov     rbp, rdx
0x1810cdd08  mov     rax, [rcx]
0x1810cdd0b  xor     ecx, ecx
0x1810cdd0d  cmp     dword ptr [rax], 0C0000006h
0x1810cdd13  setz    cl
0x1810cdd16  mov     eax, ecx
0x1810cdd18  add     rsp, 40h
0x1810cdd1c  pop     rbp
0x1810cdd1d  retn
```
