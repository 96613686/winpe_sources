# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x18000fcf0`
- end: `0x18000fe98`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800106d4`
- `0x18002a62c`

## callees

- `0x180002a90`
- `0x18000e390`
- `0x18000e43c`
- `0x18000e46c`
- `0x18000ee24`
- `0x18000f040`
- `0x18000fb7c`
- `0x18000fcf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fd3a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fd3a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fe56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000fe56`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000fd83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000fd83`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000fd65`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000fd65`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000fd9c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000fd9c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fe21`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fe21`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rsi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  __int64 v20; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v22; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20 = 0;
  v21[1] = this;
  v21[0] = 0;
  v22 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v11 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v13 = (const CHAR *)LoadResource(v8, Resource);
    if ( !v13 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v11);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v9 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v15 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v23;
        v22 = (LPWSTR)v23;
      }
      else
      {
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
        lpWideCharStr = v22;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v22;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v22[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x18000fcf0  mov     [rsp+arg_0], rbx
0x18000fcf5  push    rsi
0x18000fcf6  push    rdi
0x18000fcf7  push    r14
0x18000fcf9  sub     rsp, 480h
0x18000fd00  mov     rax, cs:__security_cookie
0x18000fd07  xor     rax, rsp
0x18000fd0a  mov     [rsp+498h+var_28], rax
0x18000fd12  mov     r14, r9
0x18000fd15  mov     rdi, r8
0x18000fd18  mov     rax, rdx
0x18000fd1b  xor     ebx, ebx
0x18000fd1d  mov     [rsp+498h+var_450], rbx
0x18000fd22  mov     [rsp+498h+var_440], rcx
0x18000fd27  mov     [rsp+498h+var_448], rbx
0x18000fd2c  mov     [rsp+498h+var_438], rbx
0x18000fd31  xor     edx, edx; hFile
0x18000fd33  lea     r8d, [rbx+2]; dwFlags
0x18000fd37  mov     rcx, rax; lpLibFileName
0x18000fd3a  call    cs:__imp_LoadLibraryExW
0x18000fd40  mov     rsi, rax
0x18000fd43  mov     [rsp+498h+var_460], rax
0x18000fd48  test    rax, rax
0x18000fd4b  jnz     short loc_18000FD59
0x18000fd4d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fd52  mov     ebx, eax
0x18000fd54  jmp     loc_18000FE5D
0x18000fd59  xor     r9d, r9d; wLanguage
0x18000fd5c  mov     r8, rdi; lpName
0x18000fd5f  mov     rdx, r14; lpType
0x18000fd62  mov     rcx, rsi; hModule
0x18000fd65  call    cs:__imp_FindResourceExW
0x18000fd6b  mov     rdi, rax
0x18000fd6e  test    rax, rax
0x18000fd71  jnz     short loc_18000FD7D
0x18000fd73  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fd78  jmp     loc_18000FE51
0x18000fd7d  mov     rdx, rdi; hResInfo
0x18000fd80  mov     rcx, rsi; hModule
0x18000fd83  call    cs:__imp_LoadResource
0x18000fd89  mov     r14, rax
0x18000fd8c  mov     [rsp+498h+var_458], rax
0x18000fd91  test    rax, rax
0x18000fd94  jz      short loc_18000FD73
0x18000fd96  mov     rdx, rdi; hResInfo
0x18000fd99  mov     rcx, rsi; hModule
0x18000fd9c  call    cs:__imp_SizeofResource
0x18000fda2  mov     edi, eax
0x18000fda4  mov     [rsp+498h+var_468], eax
0x18000fda8  inc     eax
0x18000fdaa  cmp     eax, edi
0x18000fdac  jnb     short loc_18000FDB8
0x18000fdae  mov     ebx, 8007000Eh
0x18000fdb3  jmp     loc_18000FE5D
0x18000fdb8  mov     ecx, eax
0x18000fdba  mov     edx, 2
0x18000fdbf  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000fdc4  cmp     rax, 400h
0x18000fdca  jbe     short loc_18000FDE0
0x18000fdcc  mov     rdx, rax
0x18000fdcf  lea     rcx, [rsp+498h+var_438]
0x18000fdd4  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000fdd9  mov     rax, [rsp+498h+var_438]
0x18000fdde  jmp     short loc_18000FDEA
0x18000fde0  lea     rax, [rsp+498h+var_430]
0x18000fde5  mov     [rsp+498h+var_438], rax
0x18000fdea  jmp     short loc_18000FE01
0x18000fdec  xor     ebx, ebx
0x18000fdee  mov     rsi, [rsp+498h+var_460]
0x18000fdf3  mov     r14, [rsp+498h+var_458]
0x18000fdf8  mov     edi, [rsp+498h+var_468]
0x18000fdfc  mov     rax, [rsp+498h+var_438]
0x18000fe01  test    rax, rax
0x18000fe04  jnz     short loc_18000FE0D
0x18000fe06  mov     ebx, 8007000Eh
0x18000fe0b  jmp     short loc_18000FE53
0x18000fe0d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000fe11  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000fe16  mov     r9d, edi; cbMultiByte
0x18000fe19  mov     r8, r14; lpMultiByteStr
0x18000fe1c  xor     edx, edx; dwFlags
0x18000fe1e  lea     ecx, [rdx+3]; CodePage
0x18000fe21  call    cs:__imp_MultiByteToWideChar
0x18000fe27  test    eax, eax
0x18000fe29  jz      loc_18000FD73
0x18000fe2f  mov     ecx, eax
0x18000fe31  mov     rax, [rsp+498h+var_438]
0x18000fe36  mov     [rax+rcx*2], bx
0x18000fe3a  mov     r8d, [rsp+498h+arg_20]; int
0x18000fe42  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x18000fe47  lea     rcx, [rsp+498h+var_448]; this
0x18000fe4c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18000fe51  mov     ebx, eax
0x18000fe53  mov     rcx, rsi; hLibModule
0x18000fe56  call    cs:__imp_FreeLibrary
0x18000fe5c  nop
0x18000fe5d  lea     rcx, [rsp+498h+var_438]
0x18000fe62  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000fe67  nop
0x18000fe68  lea     rcx, [rsp+498h+var_450]
0x18000fe6d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fe72  mov     eax, ebx
0x18000fe74  mov     rcx, [rsp+498h+var_28]
0x18000fe7c  xor     rcx, rsp; StackCookie
0x18000fe7f  call    __security_check_cookie
0x18000fe84  mov     rbx, [rsp+498h+arg_0]
0x18000fe8c  add     rsp, 480h
0x18000fe93  pop     r14
0x18000fe95  pop     rdi
0x18000fe96  pop     rsi
0x18000fe97  retn
```
