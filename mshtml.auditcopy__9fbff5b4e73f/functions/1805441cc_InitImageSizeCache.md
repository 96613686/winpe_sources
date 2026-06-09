# InitImageSizeCache

- ea: `0x1805441cc`
- end: `0x1805445ec`
- name: `InitImageSizeCache`
- size: `1056`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180543cd4`
- `0x180543df0`
- `0x180543f68`
- `0x1805440ac`
- `0x180a52de0`

## callees

- `0x1805441cc`
- `0x1807c1510`
- `0x1810f6516`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!OpenFileMappingW` at `0x180544316`
- `KERNEL32!OpenFileMappingW` at `0x180544316`
- `KERNEL32!MapViewOfFile` at `0x180544347`
- `KERNEL32!MapViewOfFile` at `0x1805444c4`
- `KERNEL32!MapViewOfFile` at `0x180544347`
- `KERNEL32!MapViewOfFile` at `0x1805444c4`
- `KERNEL32!SetFilePointer` at `0x180544465`
- `KERNEL32!SetFilePointer` at `0x180544465`
- `KERNEL32!CreateFileW` at `0x180544400`
- `KERNEL32!CreateFileW` at `0x180544400`
- `KERNEL32!GetFileSize` at `0x18054443d`
- `KERNEL32!GetFileSize` at `0x18054443d`
- `KERNEL32!CreateMutexW` at `0x1805442c6`
- `KERNEL32!CreateMutexW` at `0x1805442c6`
- `KERNEL32!SetEndOfFile` at `0x180544474`
- `KERNEL32!SetEndOfFile` at `0x180544474`
- `KERNEL32!CreateFileMappingW` at `0x180544495`
- `KERNEL32!CreateFileMappingW` at `0x180544495`
- `KERNEL32!FlushViewOfFile` at `0x180544533`
- `KERNEL32!FlushViewOfFile` at `0x180544533`
- `KERNEL32!UnmapViewOfFile` at `0x18054455b`
- `KERNEL32!UnmapViewOfFile` at `0x18054455b`
- `KERNEL32!ReleaseMutex` at `0x180544591`
- `KERNEL32!ReleaseMutex` at `0x180544591`
- `KERNEL32!GetLastError` at `0x18054441e`
- `KERNEL32!GetLastError` at `0x18054441e`
- `KERNEL32!CloseHandle` at `0x180544576`
- `KERNEL32!CloseHandle` at `0x1805445a0`
- `KERNEL32!CloseHandle` at `0x1805445b5`
- `KERNEL32!CloseHandle` at `0x180544576`
- `KERNEL32!CloseHandle` at `0x1805445a0`
- `KERNEL32!CloseHandle` at `0x1805445b5`
- `KERNEL32!WaitForSingleObject` at `0x1805442eb`
- `KERNEL32!WaitForSingleObject` at `0x1805442eb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18054426b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180544280`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18054426b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180544280`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1805443ca`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1805443ca`

## string_xrefs

- `0x1805442a7`: `Local\MSIMGSIZECacheMapAC`
- `0x180544293`: `Local\MSIMGSIZECacheMutexAC`
- `0x1805442bb`: `Local\MSIMGSIZECacheMap`
- `0x1805442b4`: `Local\MSIMGSIZECacheMutex`
- `0x1805442a0`: `Local\MSIMGSIZECacheMapLow`
- `0x18054428c`: `Local\MSIMGSIZECacheMutexLow`

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
  if ( dword_1815BF16C )
    goto LABEL_2;
  FileW = -1;
  v3 = 0;
  if ( (Microsoft_IEEnableBits & 8) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      (REGHANDLE *)&BERP_IE_Context,
      (const EVENT_DESCRIPTOR *)MSHTML_INITIMAGESIZECACHE_START,
      0,
      0);
  v4 = 1;
  dword_1815BF16C = 1;
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
    McTemplateU0pq_EventWriteTransfer(
      (REGHANDLE *)&BERP_IE_Context,
      (const EVENT_DESCRIPTOR *)MSHTML_INITIMAGESIZECACHE_STOP,
      0,
      0);
LABEL_2:
  LOBYTE(v0) = lpBaseAddress != 0;
  return v0;
}

```

## disassembly

```asm
0x1805441cc  push    rbx
0x1805441ce  push    rsi
0x1805441cf  push    rdi
0x1805441d0  push    r12
0x1805441d2  push    r13
0x1805441d4  push    r14
0x1805441d6  push    r15
0x1805441d8  sub     rsp, 290h
0x1805441df  mov     rax, cs:__security_cookie
0x1805441e6  xor     rax, rsp
0x1805441e9  mov     [rsp+2C8h+var_48], rax
0x1805441f1  xor     ebx, ebx
0x1805441f3  cmp     cs:dword_1815BF16C, ebx
0x1805441f9  jz      short loc_18054422B
0x1805441fb  cmp     cs:lpBaseAddress, rbx
0x180544202  setnz   bl
0x180544205  mov     eax, ebx
0x180544207  mov     rcx, [rsp+2C8h+var_48]
0x18054420f  xor     rcx, rsp; StackCookie
0x180544212  call    __security_check_cookie
0x180544217  add     rsp, 290h
0x18054421e  pop     r15
0x180544220  pop     r14
0x180544222  pop     r13
0x180544224  pop     r12
0x180544226  pop     rdi
0x180544227  pop     rsi
0x180544228  pop     rbx
0x180544229  retn
0x18054422b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18054422f  mov     [rsp+2C8h+var_280], rsi
0x180544234  mov     rdi, rbx
0x180544237  test    byte ptr cs:Microsoft_IEEnableBits, 8
0x18054423e  jz      short loc_180544259
0x180544240  xor     r9d, r9d
0x180544243  xor     r8d, r8d
0x180544246  lea     rdx, MSHTML_INITIMAGESIZECACHE_START
0x18054424d  lea     rcx, BERP_IE_Context
0x180544254  call    McTemplateU0pq_EventWriteTransfer
0x180544259  mov     r15d, 1
0x18054425f  mov     cs:dword_1815BF16C, r15d
0x180544266  mov     ecx, 20000004h
0x18054426b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180544272  nop     dword ptr [rax+rax+00h]
0x180544277  test    al, al
0x180544279  jz      short loc_1805442B4
0x18054427b  mov     ecx, 20000003h
0x180544280  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180544287  nop     dword ptr [rax+rax+00h]
0x18054428c  lea     rcx, aLocalMsimgsize; "Local\\MSIMGSIZECacheMutexLow"
0x180544293  lea     r8, aLocalMsimgsize_4; "Local\\MSIMGSIZECacheMutexAC"
0x18054429a  test    al, al
0x18054429c  cmovz   r8, rcx
0x1805442a0  lea     rcx, aLocalMsimgsize_2; "Local\\MSIMGSIZECacheMapLow"
0x1805442a7  lea     r12, aLocalMsimgsize_0; "Local\\MSIMGSIZECacheMapAC"
0x1805442ae  cmovz   r12, rcx
0x1805442b2  jmp     short loc_1805442C2
0x1805442b4  lea     r8, Name; "Local\\MSIMGSIZECacheMutex"
0x1805442bb  lea     r12, aLocalMsimgsize_3; "Local\\MSIMGSIZECacheMap"
0x1805442c2  xor     edx, edx; bInitialOwner
0x1805442c4  xor     ecx, ecx; lpMutexAttributes
0x1805442c6  call    cs:__imp_CreateMutexW
0x1805442cd  nop     dword ptr [rax+rax+00h]
0x1805442d2  mov     r14, rax
0x1805442d5  mov     [rsp+2C8h+var_270], rax
0x1805442da  test    rax, rax
0x1805442dd  jz      loc_18054454A
0x1805442e3  mov     edx, 0FA0h; dwMilliseconds
0x1805442e8  mov     rcx, rax; hHandle
0x1805442eb  call    cs:__imp_WaitForSingleObject
0x1805442f2  nop     dword ptr [rax+rax+00h]
0x1805442f7  test    eax, eax
0x1805442f9  jnz     loc_18054454A
0x1805442ff  cmp     cs:lpBaseAddress, rbx
0x180544306  jnz     loc_180544589
0x18054430c  mov     r8, r12; lpName
0x18054430f  xor     edx, edx; bInheritHandle
0x180544311  mov     ecx, 0F001Fh; dwDesiredAccess
0x180544316  call    cs:__imp_OpenFileMappingW
0x18054431d  nop     dword ptr [rax+rax+00h]
0x180544322  mov     cs:hObject, rax
0x180544329  test    rax, rax
0x18054432c  jz      short loc_1805443A0
0x18054432e  mov     r13d, 0BFE0h
0x180544334  mov     [rsp+2C8h+dwNumberOfBytesToMap], r13; dwNumberOfBytesToMap
0x180544339  xor     r9d, r9d; dwFileOffsetLow
0x18054433c  xor     r8d, r8d; dwFileOffsetHigh
0x18054433f  mov     edx, 0F001Fh; dwDesiredAccess
0x180544344  mov     rcx, rax; hFileMappingObject
0x180544347  call    cs:__imp_MapViewOfFile
0x18054434e  nop     dword ptr [rax+rax+00h]
0x180544353  mov     rdi, rax
0x180544356  mov     [rsp+2C8h+var_278], rax
0x18054435b  test    rax, rax
0x18054435e  jz      loc_18054454A
0x180544364  cmp     dword ptr [rax], 0CAC8EF17h
0x18054436a  jnz     short loc_180544375
0x18054436c  cmp     dword ptr [rax+4], 2
0x180544370  jnz     short loc_180544375
0x180544372  mov     r15d, ebx
0x180544375  mov     [rsp+2C8h+var_268], r15d
0x18054437a  jmp     short loc_180544392
0x18054437c  xor     ebx, ebx
0x18054437e  mov     r14, [rsp+2C8h+var_270]
0x180544383  mov     rsi, [rsp+2C8h+var_280]
0x180544388  mov     rdi, [rsp+2C8h+var_278]
0x18054438d  jmp     loc_18054454A
0x180544392  test    r15d, r15d
0x180544395  jz      loc_180544543
0x18054439b  jmp     loc_18054454A
0x1805443a0  mov     dword ptr [rsp+2C8h+FileName], ebx
0x1805443a4  xor     edx, edx; Val
0x1805443a6  mov     r8d, 204h; Size
0x1805443ac  lea     rcx, [rsp+2C8h+var_254]; void *
0x1805443b1  call    memset_0
0x1805443b6  mov     r9d, 104h
0x1805443bc  lea     r8, [rsp+2C8h+FileName]
0x1805443c1  xor     edx, edx
0x1805443c3  mov     rcx, cs:?BROWSERPROFILEDATA_FILEPATH_ImageSizeCache@FilePathStore@@3UBROWSERPROFILEDATA_FILEPATHID@1@B; FilePathStore::BROWSERPROFILEDATA_FILEPATHID const FilePathStore::BROWSERPROFILEDATA_FILEPATH_ImageSizeCache
0x1805443ca  call    cs:__imp_GetBrowserProfileDataFilePath
0x1805443d1  nop     dword ptr [rax+rax+00h]
0x1805443d6  test    eax, eax
0x1805443d8  jnz     loc_18054454A
0x1805443de  mov     [rsp+2C8h+hTemplateFile], rbx; hTemplateFile
0x1805443e3  mov     [rsp+2C8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1805443e7  mov     dword ptr [rsp+2C8h+dwNumberOfBytesToMap], 4; dwCreationDisposition
0x1805443ef  xor     r9d, r9d; lpSecurityAttributes
0x1805443f2  mov     edx, 0C0000000h; dwDesiredAccess
0x1805443f7  lea     r8d, [rax+3]; dwShareMode
0x1805443fb  lea     rcx, [rsp+2C8h+FileName]; lpFileName
0x180544400  call    cs:__imp_CreateFileW
0x180544407  nop     dword ptr [rax+rax+00h]
0x18054440c  mov     rsi, rax
0x18054440f  mov     [rsp+2C8h+var_280], rax
0x180544414  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180544418  jz      loc_18054454A
0x18054441e  call    cs:__imp_GetLastError
0x180544425  nop     dword ptr [rax+rax+00h]
0x18054442a  mov     ecx, ebx
0x18054442c  cmp     eax, 0B7h
0x180544431  setnz   cl
0x180544434  mov     [rsp+2C8h+var_284], ecx
0x180544438  xor     edx, edx; lpFileSizeHigh
0x18054443a  mov     rcx, rsi; hFile
0x18054443d  call    cs:__imp_GetFileSize
0x180544444  nop     dword ptr [rax+rax+00h]
0x180544449  mov     r13d, 0BFE0h
0x18054444f  cmp     eax, r13d
0x180544452  jz      short loc_180544480
0x180544454  mov     [rsp+2C8h+var_284], r15d
0x180544459  xor     r9d, r9d; dwMoveMethod
0x18054445c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18054445f  mov     edx, r13d; lDistanceToMove
0x180544462  mov     rcx, rsi; hFile
0x180544465  call    cs:__imp_SetFilePointer
0x18054446c  nop     dword ptr [rax+rax+00h]
0x180544471  mov     rcx, rsi; hFile
0x180544474  call    cs:__imp_SetEndOfFile
0x18054447b  nop     dword ptr [rax+rax+00h]
0x180544480  mov     qword ptr [rsp+2C8h+dwFlagsAndAttributes], r12; lpName
0x180544485  mov     dword ptr [rsp+2C8h+dwNumberOfBytesToMap], ebx; dwMaximumSizeLow
0x180544489  xor     r9d, r9d; dwMaximumSizeHigh
0x18054448c  xor     edx, edx; lpFileMappingAttributes
0x18054448e  lea     r8d, [r9+4]; flProtect
0x180544492  mov     rcx, rsi; hFile
0x180544495  call    cs:__imp_CreateFileMappingW
0x18054449c  nop     dword ptr [rax+rax+00h]
0x1805444a1  mov     cs:hObject, rax
0x1805444a8  test    rax, rax
0x1805444ab  jz      loc_18054454A
0x1805444b1  mov     [rsp+2C8h+dwNumberOfBytesToMap], r13; dwNumberOfBytesToMap
0x1805444b6  xor     r9d, r9d; dwFileOffsetLow
0x1805444b9  xor     r8d, r8d; dwFileOffsetHigh
0x1805444bc  mov     edx, 0F001Fh; dwDesiredAccess
0x1805444c1  mov     rcx, rax; hFileMappingObject
0x1805444c4  call    cs:__imp_MapViewOfFile
0x1805444cb  nop     dword ptr [rax+rax+00h]
0x1805444d0  mov     rdi, rax
0x1805444d3  mov     [rsp+2C8h+var_278], rax
0x1805444d8  test    rax, rax
0x1805444db  jz      short loc_18054454A
0x1805444dd  mov     al, bl
0x1805444df  cmp     [rsp+2C8h+var_284], ebx
0x1805444e3  jnz     short loc_1805444F3
0x1805444e5  cmp     dword ptr [rdi], 0CAC8EF17h
0x1805444eb  jnz     short loc_1805444F3
0x1805444ed  cmp     dword ptr [rdi+4], 2
0x1805444f1  jz      short loc_180544514
0x1805444f3  mov     r8, r13; Size
0x1805444f6  xor     edx, edx; Val
0x1805444f8  mov     rcx, rdi; void *
0x1805444fb  call    memset_0
0x180544500  mov     dword ptr [rdi], 0CAC8EF17h
0x180544506  mov     dword ptr [rdi+4], 2
0x18054450d  mov     al, r15b
0x180544510  mov     [rsp+2C8h+var_288], al
0x180544514  jmp     short loc_180544529
0x180544516  xor     ebx, ebx
0x180544518  mov     r14, [rsp+2C8h+var_270]
0x18054451d  mov     rsi, [rsp+2C8h+var_280]
0x180544522  mov     rdi, [rsp+2C8h+var_278]
0x180544527  jmp     short loc_18054454A
0x180544529  test    al, al
0x18054452b  jz      short loc_180544543
0x18054452d  mov     rdx, r13; dwNumberOfBytesToFlush
0x180544530  mov     rcx, rdi; lpBaseAddress
0x180544533  call    cs:__imp_FlushViewOfFile
0x18054453a  nop     dword ptr [rax+rax+00h]
0x18054453f  test    eax, eax
0x180544541  jz      short loc_18054454A
0x180544543  mov     cs:lpBaseAddress, rdi
0x18054454a  cmp     cs:lpBaseAddress, rbx
0x180544551  jnz     short loc_180544589
0x180544553  test    rdi, rdi
0x180544556  jz      short loc_180544567
0x180544558  mov     rcx, rdi; lpBaseAddress
0x18054455b  call    cs:__imp_UnmapViewOfFile
0x180544562  nop     dword ptr [rax+rax+00h]
0x180544567  mov     rax, cs:hObject
0x18054456e  test    rax, rax
0x180544571  jz      short loc_180544589
0x180544573  mov     rcx, rax; hObject
0x180544576  call    cs:__imp_CloseHandle
0x18054457d  nop     dword ptr [rax+rax+00h]
0x180544582  mov     cs:hObject, rbx
0x180544589  test    r14, r14
0x18054458c  jz      short loc_1805445AC
0x18054458e  mov     rcx, r14; hMutex
0x180544591  call    cs:__imp_ReleaseMutex
0x180544598  nop     dword ptr [rax+rax+00h]
0x18054459d  mov     rcx, r14; hObject
0x1805445a0  call    cs:__imp_CloseHandle
0x1805445a7  nop     dword ptr [rax+rax+00h]
0x1805445ac  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1805445b0  jz      short loc_1805445C1
0x1805445b2  mov     rcx, rsi; hObject
0x1805445b5  call    cs:__imp_CloseHandle
0x1805445bc  nop     dword ptr [rax+rax+00h]
0x1805445c1  test    byte ptr cs:Microsoft_IEEnableBits, 8
0x1805445c8  jz      loc_1805441FB
0x1805445ce  xor     r9d, r9d
0x1805445d1  xor     r8d, r8d
0x1805445d4  lea     rdx, MSHTML_INITIMAGESIZECACHE_STOP
0x1805445db  lea     rcx, BERP_IE_Context
0x1805445e2  call    McTemplateU0pq_EventWriteTransfer
0x1805445e7  jmp     loc_1805441FB
0x181101251  push    rbp
0x181101253  sub     rsp, 40h
0x181101257  mov     rbp, rdx
0x18110125a  mov     rax, [rcx]
0x18110125d  xor     ecx, ecx
0x18110125f  cmp     dword ptr [rax], 0C0000006h
0x181101265  setz    cl
0x181101268  mov     eax, ecx
0x18110126a  add     rsp, 40h
0x18110126e  pop     rbp
0x18110126f  retn
0x181101271  push    rbp
0x181101273  sub     rsp, 40h
0x181101277  mov     rbp, rdx
0x18110127a  mov     rax, [rcx]
0x18110127d  xor     ecx, ecx
0x18110127f  cmp     dword ptr [rax], 0C0000006h
0x181101285  setz    cl
0x181101288  mov     eax, ecx
0x18110128a  add     rsp, 40h
0x18110128e  pop     rbp
0x18110128f  retn
```
