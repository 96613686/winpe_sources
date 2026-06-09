# Windows::Internal::SpatialInteractions::SpatialRimDevice::WriteOutputReport(uchar *,ulong)

- ea: `0x180122100`
- end: `0x18012223b`
- name: `?WriteOutputReport@SpatialRimDevice@SpatialInteractions@Internal@Windows@@UEAAJPEAEK@Z`
- size: `315`
- prototype: `int(Windows::Internal::SpatialInteractions::SpatialRimDevice *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18008daac`
- `0x18008ead4`
- `0x180121bb0`
- `0x180122100`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122154`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180122181`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180122181`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801221d3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801221d3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SpatialInteractions::SpatialRimDevice::WriteOutputReport(
        Windows::Internal::SpatialInteractions::SpatialRimDevice *this,
        unsigned __int8 *a2,
        DWORD a3)
{
  unsigned int LastError; // ebx
  HSTRING v6; // rcx
  const WCHAR *StringRawBuffer; // rax
  HANDLE FileW; // rax
  const char *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-58h]
  void **v16; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+18h] BYREF

  if ( a3 )
  {
    v6 = (HSTRING)*((_QWORD *)this + 8);
    v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    v17 = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(v6, 0);
    FileW = CreateFileW(StringRawBuffer, 0xC0000000, 3u, 0, 3u, 0, 0);
    v10 = -1;
    v11 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(&v16);
      v10 = v11;
      v17 = v11;
    }
    if ( v10 == -1 )
    {
      v12 = 121;
    }
    else
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile((HANDLE)v10, a2, a3, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten == a3 )
        {
          LastError = 0;
        }
        else
        {
          LastError = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\spatialrimdevice.cpp",
            (const char *)0x8000FFFFLL,
            dwCreationDispositiona);
        }
        goto LABEL_13;
      }
      v12 = 123;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\spatialrimdevice.cpp",
                  v9);
LABEL_13:
    v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(&v16);
    return LastError;
  }
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x76,
    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\spatialrimdevice.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return LastError;
}

```

## disassembly

```asm
0x180122100  push    rbx
0x180122102  push    rsi
0x180122103  push    rdi
0x180122104  push    r14
0x180122106  sub     rsp, 58h
0x18012210a  mov     ebx, r8d
0x18012210d  mov     rdi, rdx
0x180122110  cmp     r8d, 1
0x180122114  jnb     short loc_180122139
0x180122116  mov     rcx, [rsp+78h]; this
0x18012211b  lea     r8, aOnecoreuapWind_87; "onecoreuap\\windows\\moderncore\\inputv"...
0x180122122  mov     ebx, 80070057h
0x180122127  mov     edx, 76h ; 'v'; void *
0x18012212c  mov     r9d, ebx; char *
0x18012212f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122134  jmp     loc_18012222F
0x180122139  mov     rcx, [rcx+40h]; string
0x18012213d  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180122144  xor     edx, edx; length
0x180122146  mov     [rsp+78h+var_38], r14
0x18012214b  mov     [rsp+78h+var_30], 0FFFFFFFFFFFFFFFFh
0x180122154  call    cs:__imp_WindowsGetStringRawBuffer
0x18012215a  mov     r8d, 3; dwShareMode
0x180122160  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180122169  mov     rcx, rax; lpFileName
0x18012216c  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180122174  xor     r9d, r9d; lpSecurityAttributes
0x180122177  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18012217c  mov     edx, 0C0000000h; dwDesiredAccess
0x180122181  call    cs:__imp_CreateFileW
0x180122187  mov     rcx, [rsp+78h+var_30]
0x18012218c  mov     rsi, rax
0x18012218f  cmp     rax, rcx
0x180122192  jz      short loc_1801221A6
0x180122194  lea     rcx, [rsp+78h+var_38]
0x180122199  call    ?Close@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(void)
0x18012219e  mov     rcx, rsi; hFile
0x1801221a1  mov     [rsp+78h+var_30], rcx
0x1801221a6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801221aa  jnz     short loc_1801221B1
0x1801221ac  lea     edx, [rcx+7Ah]
0x1801221af  jmp     short loc_1801221E0
0x1801221b1  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801221b9  mov     [rsp+78h+NumberOfBytesWritten], 0
0x1801221c4  mov     r8d, ebx; nNumberOfBytesToWrite
0x1801221c7  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; int
0x1801221d0  mov     rdx, rdi; lpBuffer
0x1801221d3  call    cs:__imp_WriteFile
0x1801221d9  test    eax, eax
0x1801221db  jnz     short loc_1801221F5
0x1801221dd  lea     edx, [rax+7Bh]; void *
0x1801221e0  mov     rcx, [rsp+78h]; this
0x1801221e5  lea     r8, aOnecoreuapWind_87; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801221ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801221f1  mov     ebx, eax
0x1801221f3  jmp     short loc_180122220
0x1801221f5  cmp     [rsp+78h+NumberOfBytesWritten], ebx
0x1801221fc  jz      short loc_18012221E
0x1801221fe  mov     rcx, [rsp+78h]; this
0x180122203  lea     r8, aOnecoreuapWind_87; "onecoreuap\\windows\\moderncore\\inputv"...
0x18012220a  mov     ebx, 8000FFFFh
0x18012220f  mov     edx, 7Ch ; '|'; void *
0x180122214  mov     r9d, ebx; char *
0x180122217  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012221c  jmp     short loc_180122220
0x18012221e  xor     ebx, ebx
0x180122220  lea     rcx, [rsp+78h+var_38]
0x180122225  mov     [rsp+78h+var_38], r14
0x18012222a  call    ?Close@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(void)
0x18012222f  mov     eax, ebx
0x180122231  add     rsp, 58h
0x180122235  pop     r14
0x180122237  pop     rdi
0x180122238  pop     rsi
0x180122239  pop     rbx
0x18012223a  retn
```
