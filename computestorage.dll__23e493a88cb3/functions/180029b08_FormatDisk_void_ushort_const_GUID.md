# FormatDisk(void *,ushort const *,_GUID)

- ea: `0x180029b08`
- end: `0x180029fc2`
- name: `?FormatDisk@@YA?AUPartitionInfo@@PEAXPEBGU_GUID@@@Z`
- size: `1210`
- prototype: `_OWORD *__fastcall(_OWORD *, void *, __int64, UUID *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014c20`
- `0x180015670`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180003ba9`
- `0x1800084b4`
- `0x180008fac`
- `0x180009a38`
- `0x1800127bc`
- `0x1800136f8`
- `0x180029b08`
- `0x18002a118`
- `0x18002a8b0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029b57`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029b57`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029f01`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029f01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b85`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029b85`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029e8f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029e8f`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180029de7`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180029de7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180029dd7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180029dd7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029beb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029c44`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029d7d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029beb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029c44`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029d7d`
- `RPCRT4!UuidCreate` at `0x180029ca0`
- `RPCRT4!UuidCreate` at `0x180029ca0`

## string_xrefs

- `0x180029f3b`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029f62`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029f74`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029f86`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029f98`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029fad`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029b50`: `fmifs.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_OWORD *__fastcall FormatDisk(_OWORD *a1, void *a2, __int64 a3, UUID *a4)
{
  HMODULE Library; // rax
  const char *v8; // r9
  HMODULE v9; // rbx
  const char *v10; // r9
  FARPROC ProcAddress; // r12
  const char *v12; // r9
  const char *v13; // r9
  UUID v14; // xmm1
  const char *v15; // r9
  __int64 DiskVolumePath; // rax
  int v17; // esi
  __int64 v18; // r15
  __int128 *v19; // rcx
  int Data1; // r14d
  unsigned int v22; // eax
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h]
  __int128 v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  DWORD BytesReturned[4]; // [rsp+90h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+B0h] [rbp-50h]
  RTL_CONDITION_VARIABLE ConditionVariable; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-40h]
  __int128 v32; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  __int128 v34; // [rsp+F0h] [rbp-10h]
  UUID v35; // [rsp+100h] [rbp+0h]
  __int128 InBuffer; // [rsp+110h] [rbp+10h] BYREF
  __int64 v37; // [rsp+120h] [rbp+20h]
  _BYTE OutBuffer[4]; // [rsp+130h] [rbp+30h] BYREF
  int v39; // [rsp+134h] [rbp+34h]
  __int128 v40; // [rsp+138h] [rbp+38h]
  __int64 v41; // [rsp+148h] [rbp+48h]
  __int64 v42; // [rsp+150h] [rbp+50h]
  int v43; // [rsp+160h] [rbp+60h]
  __int64 v44; // [rsp+168h] [rbp+68h]
  __int64 v45; // [rsp+170h] [rbp+70h]
  int v46; // [rsp+178h] [rbp+78h]
  char v47; // [rsp+17Ch] [rbp+7Ch]
  GUID v48; // [rsp+180h] [rbp+80h]
  int v49; // [rsp+1F0h] [rbp+F0h]
  __int64 v50; // [rsp+1F8h] [rbp+F8h]
  __int64 v51; // [rsp+200h] [rbp+100h]
  int v52; // [rsp+208h] [rbp+108h]
  char v53; // [rsp+20Ch] [rbp+10Ch]
  GUID v54; // [rsp+210h] [rbp+110h]
  UUID v55; // [rsp+220h] [rbp+120h]
  unsigned __int64 v56; // [rsp+230h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *(_QWORD *)BytesReturned = a1;
  Library = LoadLibraryExW(L"fmifs.dll", 0, 0x800u);
  v9 = Library;
  if ( !Library )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v8);
  ProcAddress = GetProcAddress(Library, "FormatEx2");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v10);
  InBuffer = 0;
  v37 = 0;
  LODWORD(InBuffer) = 1;
  BytesReturned[0] = 0;
  if ( !DeviceIoControl(a2, 0x7C058u, &InBuffer, 0x18u, 0, 0, BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v12);
  memset_0(OutBuffer, 0, 0x150u);
  if ( !DeviceIoControl(a2, 0x70050u, 0, 0, OutBuffer, 0x150u, BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v13);
  v32 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32) = 0;
  v35 = 0;
  v34 = v40;
  if ( !memcmp_0(&GUID_00000000_0000_0000_0000_000000000000, a4, 0x10u) )
  {
    Uuid = 0;
    UuidCreate(&Uuid);
    v14 = Uuid;
  }
  else
  {
    v14 = *a4;
  }
  v35 = v14;
  v39 = 2;
  v43 = 1;
  v44 = 0x100000;
  v45 = 0x8000000;
  v46 = 0;
  v47 = 1;
  v48 = PARTITION_MSFT_RESERVED_GUID;
  v49 = 1;
  v50 = 135266304;
  v51 = v42 - 135266304 + v41;
  v52 = 1;
  v53 = 1;
  v54 = PARTITION_BASIC_DATA_GUID;
  v55 = v14;
  v56 = 0x8000000000000000uLL;
  if ( !DeviceIoControl(a2, 0x7C054u, OutBuffer, 0x150u, 0, 0, BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x228,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v15);
  DiskVolumePath = GetDiskVolumePath(&Uuid, a2);
  std::wstring::operator=(&v32, DiskVolumePath);
  std::wstring::~wstring((char **)&Uuid);
  v17 = 0;
  v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  while ( 1 )
  {
    Uuid.Data1 = -2147418113;
    v29 = 0;
    InitializeSRWLock((PSRWLOCK)Uuid.Data4);
    InitializeConditionVariable(&ConditionVariable);
    v31 = 1;
    *(_QWORD *)(v18 + 2888) = &Uuid;
    v23[0] = 0x204500000002LL;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v23[1] = &qword_18004C4D0;
    v19 = &v32;
    if ( si128.m128i_i64[1] > 7uLL )
      v19 = (__int128 *)v32;
    ((void (__fastcall *)(__int128 *, __int64, const wchar_t *, _QWORD *))ProcAddress)(v19, 12, L"NTFS", v23);
    Vml::VmSlimEvent::Wait((PSRWLOCK)Uuid.Data4, 0xFFFFFFFF);
    Data1 = Uuid.Data1;
    *(_QWORD *)(v18 + 2888) = 0;
    if ( Data1 >= 0 )
      break;
    Sleep(0x3E8u);
    if ( ++v17 >= 3 )
    {
      v22 = wil::verify_hresult<long>(Data1);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x283,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        (const char *)v22,
        (int)lambda_84911dc0c7d45ac9e8b2066b124b16a3_::_lambda_invoker_cdecl_);
    }
  }
  *a1 = 0;
  *a1 = v32;
  a1[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32) = 0;
  a1[2] = v34;
  a1[3] = v35;
  std::wstring::~wstring((char **)&v32);
  FreeLibrary(v9);
  return a1;
}

```

## disassembly

```asm
0x180029b08  mov     [rsp-8+arg_10], rbx
0x180029b0d  push    rbp
0x180029b0e  push    rsi
0x180029b0f  push    rdi
0x180029b10  push    r12
0x180029b12  push    r13
0x180029b14  push    r14
0x180029b16  push    r15
0x180029b18  lea     rbp, [rsp-190h]
0x180029b20  sub     rsp, 290h
0x180029b27  mov     rax, cs:__security_cookie
0x180029b2e  xor     rax, rsp
0x180029b31  mov     [rbp+1C0h+var_40], rax
0x180029b38  mov     r14, r9
0x180029b3b  mov     rsi, rdx
0x180029b3e  mov     rdi, rcx
0x180029b41  mov     qword ptr [rbp+1C0h+BytesReturned], rcx
0x180029b45  xor     r13d, r13d
0x180029b48  xor     edx, edx; hFile
0x180029b4a  mov     r8d, 800h; dwFlags
0x180029b50  lea     rcx, LibFileName; "fmifs.dll"
0x180029b57  call    cs:__imp_LoadLibraryExW
0x180029b5e  nop     dword ptr [rax+rax+00h]
0x180029b63  mov     rbx, rax
0x180029b66  mov     [rsp+2C0h+var_278], rax
0x180029b6b  mov     rcx, [rbp+1C8h]; this
0x180029b72  test    rax, rax
0x180029b75  jz      loc_180029F74
0x180029b7b  lea     rdx, aFormatex2; "FormatEx2"
0x180029b82  mov     rcx, rax; hModule
0x180029b85  call    cs:__imp_GetProcAddress
0x180029b8c  nop     dword ptr [rax+rax+00h]
0x180029b91  mov     r12, rax
0x180029b94  mov     rcx, [rbp+1C8h]; this
0x180029b9b  test    rax, rax
0x180029b9e  jz      loc_180029F86
0x180029ba4  xorps   xmm0, xmm0
0x180029ba7  xor     eax, eax
0x180029ba9  movups  [rbp+1C0h+InBuffer], xmm0
0x180029bad  mov     [rbp+1C0h+var_1A0], rax
0x180029bb1  mov     dword ptr [rbp+1C0h+InBuffer], 1
0x180029bb8  mov     [rbp+1C0h+BytesReturned], r13d
0x180029bbc  mov     r15, [rbp+1C8h]
0x180029bc3  mov     [rsp+2C0h+lpOverlapped], r13; lpOverlapped
0x180029bc8  lea     rax, [rbp+1C0h+BytesReturned]
0x180029bcc  mov     [rsp+2C0h+lpBytesReturned], rax; lpBytesReturned
0x180029bd1  mov     [rsp+2C0h+nOutBufferSize], r13d; nOutBufferSize
0x180029bd6  mov     [rsp+2C0h+lpOutBuffer], r13; lpOutBuffer
0x180029bdb  lea     r9d, [r13+18h]; nInBufferSize
0x180029bdf  lea     r8, [rbp+1C0h+InBuffer]; lpInBuffer
0x180029be3  mov     edx, 7C058h; dwIoControlCode
0x180029be8  mov     rcx, rsi; hDevice
0x180029beb  call    cs:__imp_DeviceIoControl
0x180029bf2  nop     dword ptr [rax+rax+00h]
0x180029bf7  test    eax, eax
0x180029bf9  jz      loc_180029F98
0x180029bff  xor     edx, edx; Val
0x180029c01  mov     r8d, 150h; Size
0x180029c07  lea     rcx, [rbp+1C0h+OutBuffer]; void *
0x180029c0b  call    memset_0
0x180029c10  mov     r15, [rbp+1C8h]
0x180029c17  mov     [rsp+2C0h+lpOverlapped], r13; lpOverlapped
0x180029c1c  lea     rax, [rbp+1C0h+BytesReturned]
0x180029c20  mov     [rsp+2C0h+lpBytesReturned], rax; lpBytesReturned
0x180029c25  mov     [rsp+2C0h+nOutBufferSize], 150h; nOutBufferSize
0x180029c2d  lea     rax, [rbp+1C0h+OutBuffer]
0x180029c31  mov     [rsp+2C0h+lpOutBuffer], rax; lpOutBuffer
0x180029c36  xor     r9d, r9d; nInBufferSize
0x180029c39  xor     r8d, r8d; lpInBuffer
0x180029c3c  mov     edx, 70050h; dwIoControlCode
0x180029c41  mov     rcx, rsi; hDevice
0x180029c44  call    cs:__imp_DeviceIoControl
0x180029c4b  nop     dword ptr [rax+rax+00h]
0x180029c50  test    eax, eax
0x180029c52  jz      loc_180029FAD
0x180029c58  xorps   xmm0, xmm0
0x180029c5b  movups  [rbp+1C0h+var_1F0], xmm0
0x180029c5f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180029c67  movdqa  [rbp+1C0h+var_1E0], xmm1
0x180029c6c  mov     word ptr [rbp+1C0h+var_1F0], r13w
0x180029c71  movups  [rbp+1C0h+var_1C0], xmm0
0x180029c75  movups  xmm0, [rbp+1C0h+var_188]
0x180029c79  movdqu  [rbp+1C0h+var_1D0], xmm0
0x180029c7e  lea     r8d, [r13+10h]; Size
0x180029c82  mov     rdx, r14; Buf2
0x180029c85  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000; Buf1
0x180029c8c  call    memcmp_0
0x180029c91  test    eax, eax
0x180029c93  jnz     short loc_180029CB2
0x180029c95  xorps   xmm0, xmm0
0x180029c98  movups  xmmword ptr [rbp+1C0h+Uuid.Data1], xmm0
0x180029c9c  lea     rcx, [rbp+1C0h+Uuid]; Uuid
0x180029ca0  call    cs:__imp_UuidCreate
0x180029ca7  nop     dword ptr [rax+rax+00h]
0x180029cac  movups  xmm1, xmmword ptr [rbp+1C0h+Uuid.Data1]
0x180029cb0  jmp     short loc_180029CB6
0x180029cb2  movups  xmm1, xmmword ptr [r14]
0x180029cb6  movaps  [rbp+1C0h+var_1C0], xmm1
0x180029cba  mov     [rbp+1C0h+var_18C], 2
0x180029cc1  mov     edx, 1
0x180029cc6  mov     [rbp+1C0h+var_160], edx
0x180029cc9  mov     [rbp+1C0h+var_158], 100000h
0x180029cd1  mov     [rbp+1C0h+var_150], 8000000h
0x180029cd9  mov     [rbp+1C0h+var_148], r13d
0x180029cdd  mov     [rbp+1C0h+var_144], dl
0x180029ce0  movups  xmm0, xmmword ptr cs:PARTITION_MSFT_RESERVED_GUID.Data1
0x180029ce7  movdqu  [rbp+1C0h+var_140], xmm0
0x180029cef  mov     [rbp+1C0h+var_D0], edx
0x180029cf5  mov     [rbp+1C0h+var_C8], 8100000h
0x180029d00  mov     rcx, [rbp+1C0h+var_178]
0x180029d04  mov     rax, [rbp+1C0h+var_170]
0x180029d08  add     rax, 0FFFFFFFFF7F00000h
0x180029d0e  add     rcx, rax
0x180029d11  mov     [rbp+1C0h+var_C0], rcx
0x180029d18  mov     [rbp+1C0h+var_B8], edx
0x180029d1e  mov     [rbp+1C0h+var_B4], dl
0x180029d24  movups  xmm0, xmmword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x180029d2b  movdqu  [rbp+1C0h+var_B0], xmm0
0x180029d33  movdqu  [rbp+1C0h+var_A0], xmm1
0x180029d3b  mov     rax, 8000000000000000h
0x180029d45  mov     [rbp+1C0h+var_90], rax
0x180029d4c  mov     r14, [rbp+1C8h]
0x180029d53  mov     [rsp+2C0h+lpOverlapped], r13; lpOverlapped
0x180029d58  lea     rax, [rbp+1C0h+BytesReturned]
0x180029d5c  mov     [rsp+2C0h+lpBytesReturned], rax; lpBytesReturned
0x180029d61  mov     [rsp+2C0h+nOutBufferSize], r13d; nOutBufferSize
0x180029d66  mov     [rsp+2C0h+lpOutBuffer], r13; lpOutBuffer
0x180029d6b  mov     r9d, 150h; nInBufferSize
0x180029d71  lea     r8, [rbp+1C0h+OutBuffer]; lpInBuffer
0x180029d75  mov     edx, 7C054h; dwIoControlCode
0x180029d7a  mov     rcx, rsi; hDevice
0x180029d7d  call    cs:__imp_DeviceIoControl
0x180029d84  nop     dword ptr [rax+rax+00h]
0x180029d89  test    eax, eax
0x180029d8b  jz      loc_180029F3B
0x180029d91  mov     rdx, rsi
0x180029d94  lea     rcx, [rbp+1C0h+Uuid]
0x180029d98  call    ?GetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetDiskVolumePath(void *)
0x180029d9d  mov     rdx, rax
0x180029da0  lea     rcx, [rbp+1C0h+var_1F0]
0x180029da4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029da9  lea     rcx, [rbp+1C0h+Uuid]
0x180029dad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029db2  mov     esi, r13d
0x180029db5  mov     ecx, cs:_tls_index
0x180029dbb  mov     rax, gs:58h
0x180029dc4  mov     r15, [rax+rcx*8]
0x180029dc8  mov     [rbp+1C0h+Uuid.Data1], 8000FFFFh
0x180029dcf  mov     [rbp+1C0h+var_210], r13d
0x180029dd3  lea     rcx, [rbp+1C0h+Uuid.Data4]; SRWLock
0x180029dd7  call    cs:__imp_InitializeSRWLock
0x180029dde  nop     dword ptr [rax+rax+00h]
0x180029de3  lea     rcx, [rbp+1C0h+ConditionVariable]; ConditionVariable
0x180029de7  call    cs:__imp_InitializeConditionVariable
0x180029dee  nop     dword ptr [rax+rax+00h]
0x180029df3  mov     [rbp+1C0h+var_200], 1
0x180029dfb  lea     rax, [rbp+1C0h+Uuid]
0x180029dff  mov     ecx, 0B48h
0x180029e04  mov     [r15+rcx], rax
0x180029e08  xorps   xmm0, xmm0
0x180029e0b  xor     eax, eax
0x180029e0d  movups  [rsp+2C0h+var_270], xmm0
0x180029e12  movups  [rsp+2C0h+var_260], xmm0
0x180029e17  movups  [rsp+2C0h+var_250], xmm0
0x180029e1c  mov     [rbp+1C0h+var_240], rax
0x180029e20  mov     byte ptr [rsp+2C0h+var_270], 2
0x180029e25  lea     rax, qword_18004C4D0
0x180029e2c  mov     qword ptr [rsp+2C0h+var_270+8], rax
0x180029e31  mov     dword ptr [rsp+2C0h+var_270+4], 2045h
0x180029e39  lea     rcx, [rbp+1C0h+var_1F0]
0x180029e3d  cmp     qword ptr [rbp+1C0h+var_1E0+8], 7
0x180029e42  cmova   rcx, qword ptr [rbp+1C0h+var_1F0]
0x180029e47  lea     rax, _lambda_84911dc0c7d45ac9e8b2066b124b16a3____lambda_invoker_cdecl_
0x180029e4e  mov     [rsp+2C0h+lpOutBuffer], rax; int
0x180029e53  lea     r9, [rsp+2C0h+var_270]
0x180029e58  lea     r8, aNtfs; "NTFS"
0x180029e5f  mov     edx, 0Ch
0x180029e64  mov     rax, r12
0x180029e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e6c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029e6f  lea     rcx, [rbp+1C0h+Uuid.Data4]; SRWLock
0x180029e73  call    ?Wait@VmSlimEvent@Vml@@QEAAHK@Z; Vml::VmSlimEvent::Wait(ulong)
0x180029e78  mov     r14d, [rbp+1C0h+Uuid.Data1]
0x180029e7c  mov     eax, 0B48h
0x180029e81  mov     [r15+rax], r13
0x180029e85  test    r14d, r14d
0x180029e88  jns     short loc_180029EAB
0x180029e8a  mov     ecx, 3E8h; dwMilliseconds
0x180029e8f  call    cs:__imp_Sleep
0x180029e96  nop     dword ptr [rax+rax+00h]
0x180029e9b  inc     esi
0x180029e9d  cmp     esi, 3
0x180029ea0  jge     loc_180029F50
0x180029ea6  jmp     loc_180029DC8
0x180029eab  xorps   xmm0, xmm0
0x180029eae  movups  xmmword ptr [rdi], xmm0
0x180029eb1  mov     rax, qword ptr [rbp+1C0h+var_1F0]
0x180029eb5  mov     [rdi], rax
0x180029eb8  mov     rax, qword ptr [rbp+1C0h+var_1F0+8]
0x180029ebc  mov     [rdi+8], rax
0x180029ec0  mov     rax, qword ptr [rbp+1C0h+var_1E0]
0x180029ec4  mov     [rdi+10h], rax
0x180029ec8  mov     rax, qword ptr [rbp+1C0h+var_1E0+8]
0x180029ecc  mov     [rdi+18h], rax
0x180029ed0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180029ed8  movdqa  [rbp+1C0h+var_1E0], xmm0
0x180029edd  mov     word ptr [rbp+1C0h+var_1F0], r13w
0x180029ee2  movaps  xmm0, [rbp+1C0h+var_1D0]
0x180029ee6  movdqu  xmmword ptr [rdi+20h], xmm0
0x180029eeb  movaps  xmm1, [rbp+1C0h+var_1C0]
0x180029eef  movdqu  xmmword ptr [rdi+30h], xmm1
0x180029ef4  lea     rcx, [rbp+1C0h+var_1F0]
0x180029ef8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029efd  nop
0x180029efe  mov     rcx, rbx; hLibModule
0x180029f01  call    cs:__imp_FreeLibrary
0x180029f08  nop     dword ptr [rax+rax+00h]
0x180029f0d  mov     rax, rdi
0x180029f10  mov     rcx, [rbp+1C0h+var_40]
0x180029f17  xor     rcx, rsp; StackCookie
0x180029f1a  call    __security_check_cookie
0x180029f1f  mov     rbx, [rsp+2C0h+arg_10]
0x180029f27  add     rsp, 290h
0x180029f2e  pop     r15
0x180029f30  pop     r14
0x180029f32  pop     r13
0x180029f34  pop     r12
0x180029f36  pop     rdi
0x180029f37  pop     rsi
0x180029f38  pop     rbp
0x180029f39  retn
0x180029f3b  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029f42  mov     edx, 228h; void *
0x180029f47  mov     rcx, r14; this
0x180029f4a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180029f50  mov     ecx, r14d
0x180029f53  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180029f58  mov     r9d, eax; char *
0x180029f5b  mov     rcx, [rbp+1C8h]; this
0x180029f62  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029f69  mov     edx, 283h; void *
0x180029f6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029f74  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029f7b  mov     edx, 1DEh; void *
0x180029f80  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180029f86  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029f8d  mov     edx, 1E1h; void *
0x180029f92  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180029f98  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029f9f  mov     edx, 1EFh; void *
0x180029fa4  mov     rcx, r15; this
0x180029fa7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180029fad  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029fb4  mov     edx, 1FEh; void *
0x180029fb9  mov     rcx, r15; this
0x180029fbc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
