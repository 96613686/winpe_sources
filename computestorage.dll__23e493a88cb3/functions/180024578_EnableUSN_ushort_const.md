# EnableUSN(ushort const *)

- ea: `0x180024578`
- end: `0x1800247db`
- name: `?EnableUSN@@YAXPEBG@Z`
- size: `611`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180027668`

## callees

- `0x180002690`
- `0x180002da0`
- `0x180012818`
- `0x1800136f8`
- `0x180024578`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024649`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024649`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800245b2`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800245b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024740`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800246c2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002471c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800246c2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002471c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800245dd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800245dd`

## string_xrefs

- `0x180024771`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180024783`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180024795`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x1800247a7`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x1800247c9`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c
void __fastcall EnableUSN(const unsigned __int16 *a1)
{
  const char *v1; // r9
  const char *v2; // r9
  __int64 v3; // rax
  unsigned __int64 v4; // rcx
  char *FileW; // rbx
  const char *v6; // r9
  DWORD LastError; // eax
  const char *v8; // r9
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  __int128 InBuffer; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD OutBuffer[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+90h] [rbp-70h]
  WCHAR szVolumeName[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  if ( !GetVolumePathNameW(a1, szVolumePathName, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      v1);
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      v2);
  if ( szVolumeName[0] )
  {
    v3 = -1;
    do
      ++v3;
    while ( szVolumeName[v3] );
    v4 = 2 * v3 - 2;
    if ( v4 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v4) = 0;
  }
  FileW = (char *)CreateFileW(szVolumeName, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      v6);
  BytesReturned = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  v13 = 0;
  if ( !DeviceIoControl(FileW, 0x900F4u, 0, 0, OutBuffer, 0x38u, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 1179 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x133,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        (const char *)LastError,
        dwCreationDisposition);
    InBuffer = 0;
    if ( !DeviceIoControl(FileW, 0x900E7u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x140,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        v8);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
}

```

## disassembly

```asm
0x180024578  mov     [rsp-8+arg_8], rbx
0x18002457d  mov     [rsp-8+arg_10], rdi
0x180024582  push    rbp
0x180024583  lea     rbp, [rsp-3D0h]
0x18002458b  sub     rsp, 4D0h
0x180024592  mov     rax, cs:__security_cookie
0x180024599  xor     rax, rsp
0x18002459c  mov     [rbp+3D0h+var_10], rax
0x1800245a3  mov     ebx, 104h
0x1800245a8  mov     r8d, ebx; cchBufferLength
0x1800245ab  lea     rdx, [rbp+3D0h+szVolumePathName]; lpszVolumePathName
0x1800245b2  call    cs:__imp_GetVolumePathNameW
0x1800245b9  nop     dword ptr [rax+rax+00h]
0x1800245be  mov     rcx, [rbp+3D8h]; this
0x1800245c5  xor     edi, edi
0x1800245c7  test    eax, eax
0x1800245c9  jz      loc_180024783
0x1800245cf  mov     r8d, ebx; cchBufferLength
0x1800245d2  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumeName
0x1800245d6  lea     rcx, [rbp+3D0h+szVolumePathName]; lpszVolumeMountPoint
0x1800245dd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800245e4  nop     dword ptr [rax+rax+00h]
0x1800245e9  mov     rcx, [rbp+3D8h]; this
0x1800245f0  test    eax, eax
0x1800245f2  jz      loc_180024795
0x1800245f8  cmp     [rbp+3D0h+szVolumeName], di
0x1800245fc  jz      short loc_180024629
0x1800245fe  lea     rcx, [rbp+3D0h+szVolumeName]
0x180024602  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024606  inc     rax
0x180024609  cmp     [rcx+rax*2], di
0x18002460d  jnz     short loc_180024606
0x18002460f  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180024617  cmp     rcx, 208h
0x18002461e  jnb     loc_1800247B9
0x180024624  mov     [rbp+rcx+3D0h+szVolumeName], di
0x180024629  mov     [rsp+4D0h+hTemplateFile], rdi; hTemplateFile
0x18002462e  mov     [rsp+4D0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180024632  mov     r8d, 3; dwShareMode
0x180024638  mov     [rsp+4D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002463d  xor     r9d, r9d; lpSecurityAttributes
0x180024640  mov     edx, 0C0000000h; dwDesiredAccess
0x180024645  lea     rcx, [rbp+3D0h+szVolumeName]; lpFileName
0x180024649  call    cs:__imp_CreateFileW
0x180024650  nop     dword ptr [rax+rax+00h]
0x180024655  mov     rbx, rax
0x180024658  mov     [rsp+4D0h+var_490], rax
0x18002465d  inc     rax
0x180024660  test    rax, 0FFFFFFFFFFFFFFFEh
0x180024666  setz    al
0x180024669  mov     rcx, [rbp+3D8h]; this
0x180024670  test    al, al
0x180024672  jnz     loc_1800247A7
0x180024678  mov     [rsp+4D0h+BytesReturned], edi
0x18002467c  xorps   xmm0, xmm0
0x18002467f  xor     eax, eax
0x180024681  movups  [rsp+4D0h+OutBuffer], xmm0
0x180024686  movups  [rsp+4D0h+var_460], xmm0
0x18002468b  movups  [rbp+3D0h+var_450], xmm0
0x18002468f  mov     [rbp+3D0h+var_440], rax
0x180024693  mov     [rsp+4D0h+lpOverlapped], rdi; lpOverlapped
0x180024698  lea     rax, [rsp+4D0h+BytesReturned]
0x18002469d  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x1800246a2  mov     [rsp+4D0h+dwFlagsAndAttributes], 38h ; '8'; nOutBufferSize
0x1800246aa  lea     rax, [rsp+4D0h+OutBuffer]
0x1800246af  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rax; unsigned int
0x1800246b4  xor     r9d, r9d; nInBufferSize
0x1800246b7  xor     r8d, r8d; lpInBuffer
0x1800246ba  mov     edx, 900F4h; dwIoControlCode
0x1800246bf  mov     rcx, rbx; hDevice
0x1800246c2  call    cs:__imp_DeviceIoControl
0x1800246c9  nop     dword ptr [rax+rax+00h]
0x1800246ce  test    eax, eax
0x1800246d0  jnz     short loc_180024733
0x1800246d2  call    cs:__imp_GetLastError
0x1800246d9  nop     dword ptr [rax+rax+00h]
0x1800246de  cmp     eax, 49Bh
0x1800246e3  jnz     loc_1800247BF
0x1800246e9  xorps   xmm0, xmm0
0x1800246ec  movups  [rsp+4D0h+InBuffer], xmm0
0x1800246f1  mov     [rsp+4D0h+lpOverlapped], rdi; lpOverlapped
0x1800246f6  lea     rax, [rsp+4D0h+BytesReturned]
0x1800246fb  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x180024700  mov     [rsp+4D0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180024704  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rdi; lpOutBuffer
0x180024709  mov     r9d, 10h; nInBufferSize
0x18002470f  lea     r8, [rsp+4D0h+InBuffer]; lpInBuffer
0x180024714  mov     edx, 900E7h; dwIoControlCode
0x180024719  mov     rcx, rbx; hDevice
0x18002471c  call    cs:__imp_DeviceIoControl
0x180024723  nop     dword ptr [rax+rax+00h]
0x180024728  mov     rcx, [rbp+3D8h]; this
0x18002472f  test    eax, eax
0x180024731  jz      short loc_180024771
0x180024733  lea     rax, [rbx-1]
0x180024737  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002473b  ja      short loc_18002474C
0x18002473d  mov     rcx, rbx; hObject
0x180024740  call    cs:__imp_CloseHandle
0x180024747  nop     dword ptr [rax+rax+00h]
0x18002474c  mov     rcx, [rbp+3D0h+var_10]
0x180024753  xor     rcx, rsp; StackCookie
0x180024756  call    __security_check_cookie
0x18002475b  lea     r11, [rsp+4D0h+var_s0]
0x180024763  mov     rbx, [r11+18h]
0x180024767  mov     rdi, [r11+20h]
0x18002476b  mov     rsp, r11
0x18002476e  pop     rbp
0x18002476f  retn
0x180024771  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180024778  mov     edx, 140h; void *
0x18002477d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024783  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18002478a  mov     edx, 109h; void *
0x18002478f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024795  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18002479c  mov     edx, 10Ch; void *
0x1800247a1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800247a7  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x1800247ae  mov     edx, 11Dh; void *
0x1800247b3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800247b9  call    __report_rangecheckfailure
0x1800247bf  mov     rcx, [rbp+3D8h]; this
0x1800247c6  mov     r9d, eax; char *
0x1800247c9  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x1800247d0  mov     edx, 133h; void *
0x1800247d5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
