# DWriteCore::Binding::Windows::MapFontFile(DWriteCore::CharSpanZ_t<char>,unsigned __int64)

- ea: `0x18029172c`
- end: `0x180291bcb`
- name: `?MapFontFile@Windows@Binding@DWriteCore@@YA?AU?$pair@V?$span@$$CBE$0?0@std@@V?$ScopedHandle@PEAXUFileViewHandle_Policy@Windows@Binding@DWriteCore@@@DWriteCore@@@std@@V?$CharSpanZ_t@D@3@_K@Z`
- size: `1183`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180292970`

## callees

- `0x1801c99c0`
- `0x1801cc990`
- `0x180212490`
- `0x18021e1c2`
- `0x18028dd88`
- `0x18029068c`
- `0x180290968`
- `0x180290fac`
- `0x180291140`
- `0x1802911d4`
- `0x180291298`
- `0x180291380`
- `0x1802913e8`
- `0x18029172c`
- `0x180291bd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180291906`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180291906`
- `kernel32!GetLastError` at `0x1802919c2`
- `kernel32!GetLastError` at `0x180291a16`
- `kernel32!GetLastError` at `0x1802919c2`
- `kernel32!GetLastError` at `0x180291a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802918f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802918fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802918f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802918fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18029180b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18029180b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18029183e`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18029183e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18029189e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18029189e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1802918d4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1802918d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall DWriteCore::Binding::Windows::MapFontFile(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  LPCWSTR v6; // rbx
  __int64 v7; // rsi
  WCHAR *FileW; // rdi
  __int64 nFileSizeLow; // rsi
  HANDLE FileMappingW; // rax
  void *v11; // rbx
  LPVOID v12; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 DepersonalizedFilePath; // rax
  __int64 v19; // rdi
  DWORD LastError; // eax
  DWriteCore::Binding::Windows *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdi
  DWORD v25; // eax
  DWriteCore::Binding::Windows *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  _QWORD pExceptionObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h]
  _BYTE v42[32]; // [rsp+68h] [rbp-98h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpFileName; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+C8h] [rbp-38h]
  void *Block; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+D8h] [rbp-28h]
  int v48; // [rsp+E0h] [rbp-20h]
  char v49; // [rsp+E8h] [rbp-18h] BYREF

  pExceptionObject[0] = a1;
  v5 = *(unsigned int *)(a2 + 8);
  v40 = *(LPCWSTR *)a2;
  v6 = v40;
  v41 = v5;
  v7 = DWriteCore::Unicode::MeasureFromUtf8(&v40);
  lpFileName = (LPCWSTR)&v49;
  v45 = 0;
  Block = 0;
  v47 = 0;
  v48 = 128;
  DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::resize(&lpFileName, v7 + 1);
  v40 = lpFileName;
  v41 = v45;
  pExceptionObject[0] = v6;
  pExceptionObject[1] = v5;
  DWriteCore::Unicode::ConvertFromUtf8(pExceptionObject, &v40);
  lpFileName[v7] = 0;
  FileW = (WCHAR *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v40 = FileW;
  if ( FileW == (WCHAR *)-1LL )
  {
    v17 = DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(&lpFileName);
    DepersonalizedFilePath = DWriteCore::Binding::Windows::GetDepersonalizedFilePath(v42, v17);
    v19 = std::wstring::c_str(DepersonalizedFilePath);
    LastError = GetLastError();
    DWriteCore::LogError<wchar_t const *>(LastError, 0x70616D656C6966LL, 131, v19);
    std::wstring::~wstring(v42);
    DWriteCore::Binding::Windows::ThrowLastError(v21);
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    v22 = DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(&lpFileName);
    v23 = DWriteCore::Binding::Windows::GetDepersonalizedFilePath(v42, v22);
    v24 = std::wstring::c_str(v23);
    v25 = GetLastError();
    DWriteCore::LogError<wchar_t const *>(v25, 0x70616D656C6966LL, 141, v24);
    std::wstring::~wstring(v42);
    DWriteCore::Binding::Windows::ThrowLastError(v26);
  }
  if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
  {
    v27 = DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(&lpFileName);
    v28 = DWriteCore::Binding::Windows::GetDepersonalizedFilePath(v42, v27);
    v29 = std::wstring::c_str(v28);
    DWriteCore::LogError<wchar_t const *>(2291683331LL, 0x70616D656C6966LL, 147, v29);
    std::wstring::~wstring(v42);
    DWriteCore::IOException::IOException((DWriteCore::IOException *)pExceptionObject, -2003283965);
    throw (DWriteCore::IOException *)pExceptionObject;
  }
  if ( FileInformation.ftLastWriteTime.dwLowDateTime
     + ((unsigned __int64)FileInformation.ftLastWriteTime.dwHighDateTime << 32) != a3 )
  {
    v30 = DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(&lpFileName);
    v31 = DWriteCore::Binding::Windows::GetDepersonalizedFilePath(v42, v30);
    v32 = std::wstring::c_str(v31);
    DWriteCore::LogError<wchar_t const *>(2291683331LL, 0x70616D656C6966LL, 153, v32);
    std::wstring::~wstring(v42);
    DWriteCore::IOException::IOException((DWriteCore::IOException *)pExceptionObject, -2003283965);
    throw (DWriteCore::IOException *)pExceptionObject;
  }
  if ( FileInformation.nFileSizeHigh || (nFileSizeLow = FileInformation.nFileSizeLow) == 0 )
  {
    v14 = DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(&lpFileName);
    v15 = DWriteCore::Binding::Windows::GetDepersonalizedFilePath(v42, v14);
    v16 = std::wstring::c_str(v15);
    DWriteCore::LogError<wchar_t const *>(2291683328LL, 0x70616D656C6966LL, 159, v16);
    std::wstring::~wstring(v42);
    LODWORD(pExceptionObject[0]) = 0;
    DWriteCore::GenericException<-2003283968>::GenericException<-2003283968>(pExceptionObject);
    throw (DWriteCore::FileFormatException *)pExceptionObject;
  }
  FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  v11 = FileMappingW;
  pExceptionObject[0] = FileMappingW;
  if ( !FileMappingW )
  {
    v36 = DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(&lpFileName);
    v37 = DWriteCore::Binding::Windows::GetDepersonalizedFilePath(v42, v36);
    v38 = std::wstring::c_str(v37);
    DWriteCore::LogError<wchar_t const *>(2147942414LL, 0x70616D656C6966LL, 175, v38);
    std::wstring::~wstring(v42);
    std::bad_alloc::bad_alloc((std::bad_alloc *)v42);
    throw (std::bad_alloc *)v42;
  }
  v12 = MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
  if ( !v12 )
  {
    v33 = DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(&lpFileName);
    v34 = DWriteCore::Binding::Windows::GetDepersonalizedFilePath(v42, v33);
    v35 = std::wstring::c_str(v34);
    DWriteCore::LogError<wchar_t const *>(2147942414LL, 0x70616D656C6966LL, 183, v35);
    std::wstring::~wstring(v42);
    std::bad_alloc::bad_alloc((std::bad_alloc *)v42);
    throw (std::bad_alloc *)v42;
  }
  *a1 = v12;
  a1[1] = nFileSizeLow;
  a1[2] = v12;
  CloseHandle(v11);
  CloseHandle(FileW);
  free(Block);
  return a1;
}

```

## disassembly

```asm
0x18029172c  push    rbp
0x18029172e  push    rbx
0x18029172f  push    rsi
0x180291730  push    rdi
0x180291731  push    r14
0x180291733  push    r15
0x180291735  lea     rbp, [rsp-108h]
0x18029173d  sub     rsp, 208h
0x180291744  mov     rax, cs:__security_cookie
0x18029174b  xor     rax, rsp
0x18029174e  mov     [rbp+130h+var_40], rax
0x180291755  mov     r15, r8
0x180291758  mov     r14, rcx
0x18029175b  mov     [rsp+230h+pExceptionObject], rcx
0x180291760  mov     edi, [rdx+8]
0x180291763  mov     rbx, [rdx]
0x180291766  mov     [rsp+230h+var_1E0], rbx
0x18029176b  mov     [rsp+230h+var_1D8], rdi
0x180291770  lea     rcx, [rsp+230h+var_1E0]
0x180291775  call    ?MeasureFromUtf8@Unicode@DWriteCore@@YA_KV?$span@$$CBD$0?0@std@@@Z; DWriteCore::Unicode::MeasureFromUtf8(std::span<char const,-1>)
0x18029177a  mov     rsi, rax
0x18029177d  lea     rax, [rbp+130h+var_148]
0x180291781  mov     [rbp+130h+lpFileName], rax
0x180291785  mov     [rbp+130h+var_168], 0
0x18029178d  mov     [rbp+130h+Block], 0
0x180291795  mov     [rbp+130h+var_158], 0
0x18029179c  mov     [rbp+130h+var_150], 80h
0x1802917a3  lea     rdx, [rsi+1]
0x1802917a7  lea     rcx, [rbp+130h+lpFileName]
0x1802917ab  call    ?resize@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAX_K@Z; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::resize(unsigned __int64)
0x1802917b0  nop
0x1802917b1  mov     rax, [rbp+130h+lpFileName]
0x1802917b5  mov     rcx, [rbp+130h+var_168]
0x1802917b9  mov     [rsp+230h+var_1E0], rax
0x1802917be  mov     [rsp+230h+var_1D8], rcx
0x1802917c3  mov     [rsp+230h+pExceptionObject], rbx
0x1802917c8  mov     [rsp+230h+var_1E8], rdi
0x1802917cd  lea     rdx, [rsp+230h+var_1E0]
0x1802917d2  lea     rcx, [rsp+230h+pExceptionObject]
0x1802917d7  call    ?ConvertFromUtf8@Unicode@DWriteCore@@YA_KV?$span@$$CBD$0?0@std@@V?$span@_W$0?0@4@@Z; DWriteCore::Unicode::ConvertFromUtf8(std::span<char const,-1>,std::span<wchar_t,-1>)
0x1802917dc  xor     ecx, ecx
0x1802917de  mov     rax, [rbp+130h+lpFileName]
0x1802917e2  mov     [rax+rsi*2], cx
0x1802917e6  mov     [rsp+230h+hTemplateFile], rcx; hTemplateFile
0x1802917eb  mov     [rsp+230h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1802917f3  mov     [rsp+230h+dwCreationDisposition], 3; dwCreationDisposition
0x1802917fb  xor     r9d, r9d; lpSecurityAttributes
0x1802917fe  mov     edx, 80000000h; dwDesiredAccess
0x180291803  lea     r8d, [rcx+7]; dwShareMode
0x180291807  mov     rcx, [rbp+130h+lpFileName]; lpFileName
0x18029180b  call    cs:__imp_CreateFileW
0x180291811  mov     rdi, rax
0x180291814  mov     [rsp+230h+var_1E0], rax
0x180291819  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18029181d  jz      loc_180291997
0x180291823  xorps   xmm0, xmm0
0x180291826  xor     eax, eax
0x180291828  movups  xmmword ptr [rbp+130h+FileInformation.dwFileAttributes], xmm0
0x18029182c  movups  xmmword ptr [rbp+130h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180291830  movups  xmmword ptr [rbp+130h+FileInformation.nFileSizeHigh], xmm0
0x180291834  mov     [rbp+130h+FileInformation.nFileIndexLow], eax
0x180291837  lea     rdx, [rbp+130h+FileInformation]; lpFileInformation
0x18029183b  mov     rcx, rdi; hFile
0x18029183e  call    cs:__imp_GetFileInformationByHandle
0x180291844  test    eax, eax
0x180291846  jz      loc_1802919EB
0x18029184c  test    byte ptr [rbp+130h+FileInformation.dwFileAttributes], 10h
0x180291850  jnz     loc_180291A3F
0x180291856  mov     ecx, [rbp+130h+FileInformation.ftLastWriteTime.dwHighDateTime]
0x180291859  shl     rcx, 20h
0x18029185d  mov     eax, [rbp+130h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x180291860  add     rcx, rax
0x180291863  cmp     rcx, r15
0x180291866  jnz     loc_180291AA4
0x18029186c  cmp     [rbp+130h+FileInformation.nFileSizeHigh], 0
0x180291870  jnz     loc_18029192E
0x180291876  mov     esi, [rbp+130h+FileInformation.nFileSizeLow]
0x180291879  test    esi, esi
0x18029187b  jz      loc_18029192E
0x180291881  mov     qword ptr [rsp+230h+dwFlagsAndAttributes], 0; lpName
0x18029188a  mov     [rsp+230h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180291892  xor     r9d, r9d; dwMaximumSizeHigh
0x180291895  xor     edx, edx; lpFileMappingAttributes
0x180291897  lea     r8d, [r9+2]; flProtect
0x18029189b  mov     rcx, rdi; hFile
0x18029189e  call    cs:__imp_CreateFileMappingW
0x1802918a4  mov     rbx, rax
0x1802918a7  mov     [rsp+230h+pExceptionObject], rax
0x1802918ac  test    rax, rax
0x1802918af  jz      loc_180291B6A
0x1802918b5  mov     qword ptr [rsp+230h+dwFlagsAndAttributes], 0; lpBaseAddress
0x1802918be  mov     qword ptr [rsp+230h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1802918c7  xor     r9d, r9d; dwFileOffsetLow
0x1802918ca  xor     r8d, r8d; dwFileOffsetHigh
0x1802918cd  lea     edx, [r9+4]; dwDesiredAccess
0x1802918d1  mov     rcx, rax; hFileMappingObject
0x1802918d4  call    cs:__imp_MapViewOfFileEx
0x1802918da  test    rax, rax
0x1802918dd  jz      loc_180291B09
0x1802918e3  mov     [r14], rax
0x1802918e6  mov     [r14+8], rsi
0x1802918ea  mov     [r14+10h], rax
0x1802918ee  mov     rcx, rbx; hObject
0x1802918f1  call    cs:__imp_CloseHandle
0x1802918f7  nop
0x1802918f8  mov     rcx, rdi; hObject
0x1802918fb  call    cs:__imp_CloseHandle
0x180291901  nop
0x180291902  mov     rcx, [rbp+130h+Block]; Block
0x180291906  call    cs:__imp_free
0x18029190c  mov     rax, r14
0x18029190f  mov     rcx, [rbp+130h+var_40]
0x180291916  xor     rcx, rsp; StackCookie
0x180291919  call    __security_check_cookie
0x18029191e  add     rsp, 208h
0x180291925  pop     r15
0x180291927  pop     r14
0x180291929  pop     rdi
0x18029192a  pop     rsi
0x18029192b  pop     rbx
0x18029192c  pop     rbp
0x18029192d  retn
0x18029192e  lea     rcx, [rbp+130h+lpFileName]
0x180291932  call    ?data@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAPEA_WXZ; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(void)
0x180291937  mov     rdx, rax
0x18029193a  lea     rcx, [rsp+230h+var_1C8]
0x18029193f  call    ?GetDepersonalizedFilePath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; DWriteCore::Binding::Windows::GetDepersonalizedFilePath(wchar_t const *)
0x180291944  mov     rcx, rax
0x180291947  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18029194c  mov     rdx, 70616D656C6966h
0x180291956  mov     r9, rax
0x180291959  mov     ecx, 88985000h
0x18029195e  mov     r8d, 9Fh
0x180291964  call    ??$LogError@PEB_W@DWriteCore@@YAJJVEventTag@0@IPEB_W@Z; DWriteCore::LogError<wchar_t const *>(long,DWriteCore::EventTag,uint,wchar_t const *)
0x180291969  lea     rcx, [rsp+230h+var_1C8]; void *
0x18029196e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180291973  mov     dword ptr [rsp+230h+pExceptionObject], 0
0x18029197b  lea     rcx, [rsp+230h+pExceptionObject]
0x180291980  call    ??0?$GenericException@$0?HHGHLAAA@@DWriteCore@@QEAA@XZ; DWriteCore::GenericException<-2003283968>::GenericException<-2003283968>(void)
0x180291985  lea     rdx, _TI3?AVFileFormatException@DWriteCore@@; pThrowInfo
0x18029198c  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180291991  call    _CxxThrowException_0
0x180291997  lea     rcx, [rbp+130h+lpFileName]
0x18029199b  call    ?data@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAPEA_WXZ; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(void)
0x1802919a0  mov     rdx, rax
0x1802919a3  lea     rcx, [rsp+230h+var_1C8]
0x1802919a8  call    ?GetDepersonalizedFilePath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; DWriteCore::Binding::Windows::GetDepersonalizedFilePath(wchar_t const *)
0x1802919ad  mov     rcx, rax
0x1802919b0  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x1802919b5  mov     rdi, rax
0x1802919b8  mov     rbx, 70616D656C6966h
0x1802919c2  call    cs:__imp_GetLastError
0x1802919c8  mov     r9, rdi
0x1802919cb  mov     r8d, 83h
0x1802919d1  mov     rdx, rbx
0x1802919d4  mov     ecx, eax
0x1802919d6  call    ??$LogError@PEB_W@DWriteCore@@YAJJVEventTag@0@IPEB_W@Z; DWriteCore::LogError<wchar_t const *>(long,DWriteCore::EventTag,uint,wchar_t const *)
0x1802919db  lea     rcx, [rsp+230h+var_1C8]; void *
0x1802919e0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802919e5  call    ?ThrowLastError@Windows@Binding@DWriteCore@@YAXXZ; DWriteCore::Binding::Windows::ThrowLastError(void)
0x1802919eb  lea     rcx, [rbp+130h+lpFileName]
0x1802919ef  call    ?data@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAPEA_WXZ; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(void)
0x1802919f4  mov     rdx, rax
0x1802919f7  lea     rcx, [rsp+230h+var_1C8]
0x1802919fc  call    ?GetDepersonalizedFilePath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; DWriteCore::Binding::Windows::GetDepersonalizedFilePath(wchar_t const *)
0x180291a01  mov     rcx, rax
0x180291a04  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x180291a09  mov     rdi, rax
0x180291a0c  mov     rbx, 70616D656C6966h
0x180291a16  call    cs:__imp_GetLastError
0x180291a1c  mov     r9, rdi
0x180291a1f  mov     r8d, 8Dh
0x180291a25  mov     rdx, rbx
0x180291a28  mov     ecx, eax
0x180291a2a  call    ??$LogError@PEB_W@DWriteCore@@YAJJVEventTag@0@IPEB_W@Z; DWriteCore::LogError<wchar_t const *>(long,DWriteCore::EventTag,uint,wchar_t const *)
0x180291a2f  lea     rcx, [rsp+230h+var_1C8]; void *
0x180291a34  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180291a39  call    ?ThrowLastError@Windows@Binding@DWriteCore@@YAXXZ; DWriteCore::Binding::Windows::ThrowLastError(void)
0x180291a3f  lea     rcx, [rbp+130h+lpFileName]
0x180291a43  call    ?data@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAPEA_WXZ; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(void)
0x180291a48  mov     rdx, rax
0x180291a4b  lea     rcx, [rsp+230h+var_1C8]
0x180291a50  call    ?GetDepersonalizedFilePath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; DWriteCore::Binding::Windows::GetDepersonalizedFilePath(wchar_t const *)
0x180291a55  mov     rcx, rax
0x180291a58  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x180291a5d  mov     rdx, 70616D656C6966h
0x180291a67  mov     r9, rax
0x180291a6a  mov     ebx, 88985003h
0x180291a6f  mov     r8d, 93h
0x180291a75  mov     ecx, ebx
0x180291a77  call    ??$LogError@PEB_W@DWriteCore@@YAJJVEventTag@0@IPEB_W@Z; DWriteCore::LogError<wchar_t const *>(long,DWriteCore::EventTag,uint,wchar_t const *)
0x180291a7c  lea     rcx, [rsp+230h+var_1C8]; void *
0x180291a81  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180291a86  mov     edx, ebx; int
0x180291a88  lea     rcx, [rsp+230h+pExceptionObject]; this
0x180291a8d  call    ??0IOException@DWriteCore@@QEAA@J@Z; DWriteCore::IOException::IOException(long)
0x180291a92  lea     rdx, _TI2?AVIOException@DWriteCore@@; pThrowInfo
0x180291a99  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180291a9e  call    _CxxThrowException_0
0x180291aa4  lea     rcx, [rbp+130h+lpFileName]
0x180291aa8  call    ?data@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAPEA_WXZ; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(void)
0x180291aad  mov     rdx, rax
0x180291ab0  lea     rcx, [rsp+230h+var_1C8]
0x180291ab5  call    ?GetDepersonalizedFilePath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; DWriteCore::Binding::Windows::GetDepersonalizedFilePath(wchar_t const *)
0x180291aba  mov     rcx, rax
0x180291abd  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x180291ac2  mov     rdx, 70616D656C6966h
0x180291acc  mov     r9, rax
0x180291acf  mov     ebx, 88985003h
0x180291ad4  mov     r8d, 99h
0x180291ada  mov     ecx, ebx
0x180291adc  call    ??$LogError@PEB_W@DWriteCore@@YAJJVEventTag@0@IPEB_W@Z; DWriteCore::LogError<wchar_t const *>(long,DWriteCore::EventTag,uint,wchar_t const *)
0x180291ae1  lea     rcx, [rsp+230h+var_1C8]; void *
0x180291ae6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180291aeb  mov     edx, ebx; int
0x180291aed  lea     rcx, [rsp+230h+pExceptionObject]; this
0x180291af2  call    ??0IOException@DWriteCore@@QEAA@J@Z; DWriteCore::IOException::IOException(long)
0x180291af7  lea     rdx, _TI2?AVIOException@DWriteCore@@; pThrowInfo
0x180291afe  lea     rcx, [rsp+230h+pExceptionObject]; pExceptionObject
0x180291b03  call    _CxxThrowException_0
0x180291b09  lea     rcx, [rbp+130h+lpFileName]
0x180291b0d  call    ?data@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAPEA_WXZ; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(void)
0x180291b12  mov     rdx, rax
0x180291b15  lea     rcx, [rsp+230h+var_1C8]
0x180291b1a  call    ?GetDepersonalizedFilePath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; DWriteCore::Binding::Windows::GetDepersonalizedFilePath(wchar_t const *)
0x180291b1f  mov     rcx, rax
0x180291b22  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x180291b27  mov     rdx, 70616D656C6966h
0x180291b31  mov     r9, rax
0x180291b34  mov     ecx, 8007000Eh
0x180291b39  mov     r8d, 0B7h
0x180291b3f  call    ??$LogError@PEB_W@DWriteCore@@YAJJVEventTag@0@IPEB_W@Z; DWriteCore::LogError<wchar_t const *>(long,DWriteCore::EventTag,uint,wchar_t const *)
0x180291b44  lea     rcx, [rsp+230h+var_1C8]; void *
0x180291b49  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180291b4e  lea     rcx, [rsp+230h+var_1C8]; this
0x180291b53  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180291b58  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180291b5f  lea     rcx, [rsp+230h+var_1C8]; pExceptionObject
0x180291b64  call    _CxxThrowException_0
0x180291b6a  lea     rcx, [rbp+130h+lpFileName]
0x180291b6e  call    ?data@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAPEA_WXZ; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::data(void)
0x180291b73  mov     rdx, rax
0x180291b76  lea     rcx, [rsp+230h+var_1C8]
0x180291b7b  call    ?GetDepersonalizedFilePath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; DWriteCore::Binding::Windows::GetDepersonalizedFilePath(wchar_t const *)
0x180291b80  mov     rcx, rax
0x180291b83  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x180291b88  mov     rdx, 70616D656C6966h
0x180291b92  mov     r9, rax
0x180291b95  mov     ecx, 8007000Eh
0x180291b9a  mov     r8d, 0AFh
0x180291ba0  call    ??$LogError@PEB_W@DWriteCore@@YAJJVEventTag@0@IPEB_W@Z; DWriteCore::LogError<wchar_t const *>(long,DWriteCore::EventTag,uint,wchar_t const *)
0x180291ba5  lea     rcx, [rsp+230h+var_1C8]; void *
0x180291baa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180291baf  lea     rcx, [rsp+230h+var_1C8]; this
0x180291bb4  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180291bb9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180291bc0  lea     rcx, [rsp+230h+var_1C8]; pExceptionObject
0x180291bc5  call    _CxxThrowException_0
```
