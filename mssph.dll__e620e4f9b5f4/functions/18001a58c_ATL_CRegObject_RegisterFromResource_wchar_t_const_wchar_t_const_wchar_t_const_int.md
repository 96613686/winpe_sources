# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x18001a58c`
- end: `0x18001a734`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `424`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001bbbc`
- `0x18001be34`

## callees

- `0x180005eb0`
- `0x18000fcd0`
- `0x180016554`
- `0x180016634`
- `0x180016734`
- `0x180017384`
- `0x18001a418`
- `0x18001a58c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001a61f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001a61f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001a601`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001a601`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001a638`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001a638`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a5d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a5d6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a6f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a6f2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a6bd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a6bd`

## pseudocode

```c
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
  unsigned __int64 v15; // rax
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
      Error = ResultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ResultFromLastError();
LABEL_17:
  ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x18001a58c  mov     [rsp+arg_0], rbx
0x18001a591  push    rsi
0x18001a592  push    rdi
0x18001a593  push    r14
0x18001a595  sub     rsp, 480h
0x18001a59c  mov     rax, cs:__security_cookie
0x18001a5a3  xor     rax, rsp
0x18001a5a6  mov     [rsp+498h+var_28], rax
0x18001a5ae  mov     r14, r9
0x18001a5b1  mov     rdi, r8
0x18001a5b4  mov     rax, rdx
0x18001a5b7  xor     ebx, ebx
0x18001a5b9  mov     [rsp+498h+var_450], rbx
0x18001a5be  mov     [rsp+498h+var_440], rcx
0x18001a5c3  mov     [rsp+498h+var_448], rbx
0x18001a5c8  mov     [rsp+498h+var_438], rbx
0x18001a5cd  xor     edx, edx; hFile
0x18001a5cf  lea     r8d, [rbx+2]; dwFlags
0x18001a5d3  mov     rcx, rax; lpLibFileName
0x18001a5d6  call    cs:__imp_LoadLibraryExW
0x18001a5dc  mov     rsi, rax
0x18001a5df  mov     [rsp+498h+var_460], rax
0x18001a5e4  test    rax, rax
0x18001a5e7  jnz     short loc_18001A5F5
0x18001a5e9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001a5ee  mov     ebx, eax
0x18001a5f0  jmp     loc_18001A6F9
0x18001a5f5  xor     r9d, r9d; wLanguage
0x18001a5f8  mov     r8, rdi; lpName
0x18001a5fb  mov     rdx, r14; lpType
0x18001a5fe  mov     rcx, rsi; hModule
0x18001a601  call    cs:__imp_FindResourceExW
0x18001a607  mov     rdi, rax
0x18001a60a  test    rax, rax
0x18001a60d  jnz     short loc_18001A619
0x18001a60f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001a614  jmp     loc_18001A6ED
0x18001a619  mov     rdx, rdi; hResInfo
0x18001a61c  mov     rcx, rsi; hModule
0x18001a61f  call    cs:__imp_LoadResource
0x18001a625  mov     r14, rax
0x18001a628  mov     [rsp+498h+var_458], rax
0x18001a62d  test    rax, rax
0x18001a630  jz      short loc_18001A60F
0x18001a632  mov     rdx, rdi; hResInfo
0x18001a635  mov     rcx, rsi; hModule
0x18001a638  call    cs:__imp_SizeofResource
0x18001a63e  mov     edi, eax
0x18001a640  mov     [rsp+498h+var_468], eax
0x18001a644  inc     eax
0x18001a646  cmp     eax, edi
0x18001a648  jnb     short loc_18001A654
0x18001a64a  mov     ebx, 8007000Eh
0x18001a64f  jmp     loc_18001A6F9
0x18001a654  mov     ecx, eax
0x18001a656  mov     edx, 2
0x18001a65b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001a660  cmp     rax, 400h
0x18001a666  jbe     short loc_18001A67C
0x18001a668  mov     rdx, rax
0x18001a66b  lea     rcx, [rsp+498h+var_438]
0x18001a670  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001a675  mov     rax, [rsp+498h+var_438]
0x18001a67a  jmp     short loc_18001A686
0x18001a67c  lea     rax, [rsp+498h+var_430]
0x18001a681  mov     [rsp+498h+var_438], rax
0x18001a686  jmp     short loc_18001A69D
0x18001a688  xor     ebx, ebx
0x18001a68a  mov     rsi, [rsp+498h+var_460]
0x18001a68f  mov     r14, [rsp+498h+var_458]
0x18001a694  mov     edi, [rsp+498h+var_468]
0x18001a698  mov     rax, [rsp+498h+var_438]
0x18001a69d  test    rax, rax
0x18001a6a0  jnz     short loc_18001A6A9
0x18001a6a2  mov     ebx, 8007000Eh
0x18001a6a7  jmp     short loc_18001A6EF
0x18001a6a9  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18001a6ad  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001a6b2  mov     r9d, edi; cbMultiByte
0x18001a6b5  mov     r8, r14; lpMultiByteStr
0x18001a6b8  xor     edx, edx; dwFlags
0x18001a6ba  lea     ecx, [rdx+3]; CodePage
0x18001a6bd  call    cs:__imp_MultiByteToWideChar
0x18001a6c3  test    eax, eax
0x18001a6c5  jz      loc_18001A60F
0x18001a6cb  mov     ecx, eax
0x18001a6cd  mov     rax, [rsp+498h+var_438]
0x18001a6d2  mov     [rax+rcx*2], bx
0x18001a6d6  mov     r8d, [rsp+498h+arg_20]; int
0x18001a6de  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x18001a6e3  lea     rcx, [rsp+498h+var_448]; this
0x18001a6e8  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18001a6ed  mov     ebx, eax
0x18001a6ef  mov     rcx, rsi; hLibModule
0x18001a6f2  call    cs:__imp_FreeLibrary
0x18001a6f8  nop
0x18001a6f9  lea     rcx, [rsp+498h+var_438]
0x18001a6fe  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18001a703  nop
0x18001a704  lea     rcx, [rsp+498h+var_450]
0x18001a709  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a70e  mov     eax, ebx
0x18001a710  mov     rcx, [rsp+498h+var_28]
0x18001a718  xor     rcx, rsp; StackCookie
0x18001a71b  call    __security_check_cookie
0x18001a720  mov     rbx, [rsp+498h+arg_0]
0x18001a728  add     rsp, 480h
0x18001a72f  pop     r14
0x18001a731  pop     rdi
0x18001a732  pop     rsi
0x18001a733  retn
```
