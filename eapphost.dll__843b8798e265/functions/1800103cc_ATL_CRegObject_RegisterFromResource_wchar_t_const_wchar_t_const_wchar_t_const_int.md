# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x1800103cc`
- end: `0x180010599`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `461`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180010e14`
- `0x18002b450`

## callees

- `0x180002af0`
- `0x18000e958`
- `0x18000ea04`
- `0x18000ea3c`
- `0x18000f378`
- `0x18000f5a4`
- `0x18001024c`
- `0x1800103cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010416`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010416`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010550`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010550`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001046b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001046b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010447`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010447`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001048a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001048a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010515`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010515`

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
0x1800103cc  mov     [rsp+arg_0], rbx
0x1800103d1  push    rsi
0x1800103d2  push    rdi
0x1800103d3  push    r14
0x1800103d5  sub     rsp, 480h
0x1800103dc  mov     rax, cs:__security_cookie
0x1800103e3  xor     rax, rsp
0x1800103e6  mov     [rsp+498h+var_28], rax
0x1800103ee  mov     r14, r9
0x1800103f1  mov     rdi, r8
0x1800103f4  mov     rax, rdx
0x1800103f7  xor     ebx, ebx
0x1800103f9  mov     [rsp+498h+var_450], rbx
0x1800103fe  mov     [rsp+498h+var_440], rcx
0x180010403  mov     [rsp+498h+var_448], rbx
0x180010408  mov     [rsp+498h+var_438], rbx
0x18001040d  xor     edx, edx; hFile
0x18001040f  lea     r8d, [rbx+2]; dwFlags
0x180010413  mov     rcx, rax; lpLibFileName
0x180010416  call    cs:__imp_LoadLibraryExW
0x18001041d  nop     dword ptr [rax+rax+00h]
0x180010422  mov     rsi, rax
0x180010425  mov     [rsp+498h+var_460], rax
0x18001042a  test    rax, rax
0x18001042d  jnz     short loc_18001043B
0x18001042f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010434  mov     ebx, eax
0x180010436  jmp     loc_18001055D
0x18001043b  xor     r9d, r9d; wLanguage
0x18001043e  mov     r8, rdi; lpName
0x180010441  mov     rdx, r14; lpType
0x180010444  mov     rcx, rsi; hModule
0x180010447  call    cs:__imp_FindResourceExW
0x18001044e  nop     dword ptr [rax+rax+00h]
0x180010453  mov     rdi, rax
0x180010456  test    rax, rax
0x180010459  jnz     short loc_180010465
0x18001045b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010460  jmp     loc_18001054B
0x180010465  mov     rdx, rdi; hResInfo
0x180010468  mov     rcx, rsi; hModule
0x18001046b  call    cs:__imp_LoadResource
0x180010472  nop     dword ptr [rax+rax+00h]
0x180010477  mov     r14, rax
0x18001047a  mov     [rsp+498h+var_458], rax
0x18001047f  test    rax, rax
0x180010482  jz      short loc_18001045B
0x180010484  mov     rdx, rdi; hResInfo
0x180010487  mov     rcx, rsi; hModule
0x18001048a  call    cs:__imp_SizeofResource
0x180010491  nop     dword ptr [rax+rax+00h]
0x180010496  mov     edi, eax
0x180010498  mov     [rsp+498h+var_468], eax
0x18001049c  inc     eax
0x18001049e  cmp     eax, edi
0x1800104a0  jnb     short loc_1800104AC
0x1800104a2  mov     ebx, 8007000Eh
0x1800104a7  jmp     loc_18001055D
0x1800104ac  mov     ecx, eax
0x1800104ae  mov     edx, 2
0x1800104b3  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800104b8  cmp     rax, 400h
0x1800104be  jbe     short loc_1800104D4
0x1800104c0  mov     rdx, rax
0x1800104c3  lea     rcx, [rsp+498h+var_438]
0x1800104c8  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800104cd  mov     rax, [rsp+498h+var_438]
0x1800104d2  jmp     short loc_1800104DE
0x1800104d4  lea     rax, [rsp+498h+var_430]
0x1800104d9  mov     [rsp+498h+var_438], rax
0x1800104de  jmp     short loc_1800104F5
0x1800104e0  xor     ebx, ebx
0x1800104e2  mov     rsi, [rsp+498h+var_460]
0x1800104e7  mov     r14, [rsp+498h+var_458]
0x1800104ec  mov     edi, [rsp+498h+var_468]
0x1800104f0  mov     rax, [rsp+498h+var_438]
0x1800104f5  test    rax, rax
0x1800104f8  jnz     short loc_180010501
0x1800104fa  mov     ebx, 8007000Eh
0x1800104ff  jmp     short loc_18001054D
0x180010501  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180010505  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001050a  mov     r9d, edi; cbMultiByte
0x18001050d  mov     r8, r14; lpMultiByteStr
0x180010510  xor     edx, edx; dwFlags
0x180010512  lea     ecx, [rdx+3]; CodePage
0x180010515  call    cs:__imp_MultiByteToWideChar
0x18001051c  nop     dword ptr [rax+rax+00h]
0x180010521  test    eax, eax
0x180010523  jz      loc_18001045B
0x180010529  mov     ecx, eax
0x18001052b  mov     rax, [rsp+498h+var_438]
0x180010530  mov     [rax+rcx*2], bx
0x180010534  mov     r8d, [rsp+498h+arg_20]; int
0x18001053c  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x180010541  lea     rcx, [rsp+498h+var_448]; this
0x180010546  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18001054b  mov     ebx, eax
0x18001054d  mov     rcx, rsi; hLibModule
0x180010550  call    cs:__imp_FreeLibrary
0x180010557  nop     dword ptr [rax+rax+00h]
0x18001055c  nop
0x18001055d  lea     rcx, [rsp+498h+var_438]
0x180010562  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x180010567  nop
0x180010568  lea     rcx, [rsp+498h+var_450]
0x18001056d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010572  mov     eax, ebx
0x180010574  mov     rcx, [rsp+498h+var_28]
0x18001057c  xor     rcx, rsp; StackCookie
0x18001057f  call    __security_check_cookie
0x180010584  mov     rbx, [rsp+498h+arg_0]
0x18001058c  add     rsp, 480h
0x180010593  pop     r14
0x180010595  pop     rdi
0x180010596  pop     rsi
0x180010597  retn
```
