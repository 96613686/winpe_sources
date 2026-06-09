# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x1800103dc`
- end: `0x180010584`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001212c`
- `0x1800123a4`

## callees

- `0x18000557c`
- `0x180006270`
- `0x180009198`
- `0x180009eb8`
- `0x18000a364`
- `0x18000bb90`
- `0x180010268`
- `0x1800103dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010426`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010426`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001046f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001046f`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180010488`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180010488`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010451`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010451`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010542`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010542`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001050d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001050d`

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
0x1800103dc  mov     [rsp+arg_0], rbx
0x1800103e1  push    rsi
0x1800103e2  push    rdi
0x1800103e3  push    r14
0x1800103e5  sub     rsp, 480h
0x1800103ec  mov     rax, cs:__security_cookie
0x1800103f3  xor     rax, rsp
0x1800103f6  mov     [rsp+498h+var_28], rax
0x1800103fe  mov     r14, r9
0x180010401  mov     rdi, r8
0x180010404  mov     rax, rdx
0x180010407  xor     ebx, ebx
0x180010409  mov     [rsp+498h+var_450], rbx
0x18001040e  mov     [rsp+498h+var_440], rcx
0x180010413  mov     [rsp+498h+var_448], rbx
0x180010418  mov     [rsp+498h+var_438], rbx
0x18001041d  xor     edx, edx; hFile
0x18001041f  lea     r8d, [rbx+2]; dwFlags
0x180010423  mov     rcx, rax; lpLibFileName
0x180010426  call    cs:__imp_LoadLibraryExW
0x18001042c  mov     rsi, rax
0x18001042f  mov     [rsp+498h+var_460], rax
0x180010434  test    rax, rax
0x180010437  jnz     short loc_180010445
0x180010439  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001043e  mov     ebx, eax
0x180010440  jmp     loc_180010549
0x180010445  xor     r9d, r9d; wLanguage
0x180010448  mov     r8, rdi; lpName
0x18001044b  mov     rdx, r14; lpType
0x18001044e  mov     rcx, rsi; hModule
0x180010451  call    cs:__imp_FindResourceExW
0x180010457  mov     rdi, rax
0x18001045a  test    rax, rax
0x18001045d  jnz     short loc_180010469
0x18001045f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180010464  jmp     loc_18001053D
0x180010469  mov     rdx, rdi; hResInfo
0x18001046c  mov     rcx, rsi; hModule
0x18001046f  call    cs:__imp_LoadResource
0x180010475  mov     r14, rax
0x180010478  mov     [rsp+498h+var_458], rax
0x18001047d  test    rax, rax
0x180010480  jz      short loc_18001045F
0x180010482  mov     rdx, rdi; hResInfo
0x180010485  mov     rcx, rsi; hModule
0x180010488  call    cs:__imp_SizeofResource
0x18001048e  mov     edi, eax
0x180010490  mov     [rsp+498h+var_468], eax
0x180010494  inc     eax
0x180010496  cmp     eax, edi
0x180010498  jnb     short loc_1800104A4
0x18001049a  mov     ebx, 8007000Eh
0x18001049f  jmp     loc_180010549
0x1800104a4  mov     ecx, eax
0x1800104a6  mov     edx, 2
0x1800104ab  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800104b0  cmp     rax, 400h
0x1800104b6  jbe     short loc_1800104CC
0x1800104b8  mov     rdx, rax
0x1800104bb  lea     rcx, [rsp+498h+var_438]
0x1800104c0  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800104c5  mov     rax, [rsp+498h+var_438]
0x1800104ca  jmp     short loc_1800104D6
0x1800104cc  lea     rax, [rsp+498h+var_430]
0x1800104d1  mov     [rsp+498h+var_438], rax
0x1800104d6  jmp     short loc_1800104ED
0x1800104d8  xor     ebx, ebx
0x1800104da  mov     rsi, [rsp+498h+var_460]
0x1800104df  mov     r14, [rsp+498h+var_458]
0x1800104e4  mov     edi, [rsp+498h+var_468]
0x1800104e8  mov     rax, [rsp+498h+var_438]
0x1800104ed  test    rax, rax
0x1800104f0  jnz     short loc_1800104F9
0x1800104f2  mov     ebx, 8007000Eh
0x1800104f7  jmp     short loc_18001053F
0x1800104f9  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1800104fd  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180010502  mov     r9d, edi; cbMultiByte
0x180010505  mov     r8, r14; lpMultiByteStr
0x180010508  xor     edx, edx; dwFlags
0x18001050a  lea     ecx, [rdx+3]; CodePage
0x18001050d  call    cs:__imp_MultiByteToWideChar
0x180010513  test    eax, eax
0x180010515  jz      loc_18001045F
0x18001051b  mov     ecx, eax
0x18001051d  mov     rax, [rsp+498h+var_438]
0x180010522  mov     [rax+rcx*2], bx
0x180010526  mov     r8d, [rsp+498h+arg_20]; int
0x18001052e  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x180010533  lea     rcx, [rsp+498h+var_448]; this
0x180010538  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18001053d  mov     ebx, eax
0x18001053f  mov     rcx, rsi; hLibModule
0x180010542  call    cs:__imp_FreeLibrary
0x180010548  nop
0x180010549  lea     rcx, [rsp+498h+var_438]
0x18001054e  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x180010553  nop
0x180010554  lea     rcx, [rsp+498h+var_450]
0x180010559  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001055e  mov     eax, ebx
0x180010560  mov     rcx, [rsp+498h+var_28]
0x180010568  xor     rcx, rsp; StackCookie
0x18001056b  call    __security_check_cookie
0x180010570  mov     rbx, [rsp+498h+arg_0]
0x180010578  add     rsp, 480h
0x18001057f  pop     r14
0x180010581  pop     rdi
0x180010582  pop     rsi
0x180010583  retn
```
