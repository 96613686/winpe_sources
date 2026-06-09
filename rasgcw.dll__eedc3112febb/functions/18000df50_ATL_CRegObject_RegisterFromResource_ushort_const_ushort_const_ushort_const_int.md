# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000df50`
- end: `0x18000e0f8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000f6fc`
- `0x18000f974`

## callees

- `0x180003c80`
- `0x180004078`
- `0x180005060`
- `0x180006d04`
- `0x180006f60`
- `0x18000dddc`
- `0x18000df50`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000dfc5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000dfc5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000dfe3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000dfe3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000df9a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000df9a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000dffc`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000dffc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e0b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e0b6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e081`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e081`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
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
  _QWORD *v20; // [rsp+48h] [rbp-450h] BYREF
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
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x18000df50  mov     [rsp+arg_0], rbx
0x18000df55  push    rsi
0x18000df56  push    rdi
0x18000df57  push    r14
0x18000df59  sub     rsp, 480h
0x18000df60  mov     rax, cs:__security_cookie
0x18000df67  xor     rax, rsp
0x18000df6a  mov     [rsp+498h+var_28], rax
0x18000df72  mov     r14, r9
0x18000df75  mov     rdi, r8
0x18000df78  mov     rax, rdx
0x18000df7b  xor     ebx, ebx
0x18000df7d  mov     [rsp+498h+var_450], rbx
0x18000df82  mov     [rsp+498h+var_440], rcx
0x18000df87  mov     [rsp+498h+var_448], rbx
0x18000df8c  mov     [rsp+498h+var_438], rbx
0x18000df91  xor     edx, edx; hFile
0x18000df93  lea     r8d, [rbx+2]; dwFlags
0x18000df97  mov     rcx, rax; lpLibFileName
0x18000df9a  call    cs:__imp_LoadLibraryExW
0x18000dfa0  mov     rsi, rax
0x18000dfa3  mov     [rsp+498h+var_460], rax
0x18000dfa8  test    rax, rax
0x18000dfab  jnz     short loc_18000DFB9
0x18000dfad  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000dfb2  mov     ebx, eax
0x18000dfb4  jmp     loc_18000E0BD
0x18000dfb9  xor     r9d, r9d; wLanguage
0x18000dfbc  mov     r8, rdi; lpName
0x18000dfbf  mov     rdx, r14; lpType
0x18000dfc2  mov     rcx, rsi; hModule
0x18000dfc5  call    cs:__imp_FindResourceExW
0x18000dfcb  mov     rdi, rax
0x18000dfce  test    rax, rax
0x18000dfd1  jnz     short loc_18000DFDD
0x18000dfd3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000dfd8  jmp     loc_18000E0B1
0x18000dfdd  mov     rdx, rdi; hResInfo
0x18000dfe0  mov     rcx, rsi; hModule
0x18000dfe3  call    cs:__imp_LoadResource
0x18000dfe9  mov     r14, rax
0x18000dfec  mov     [rsp+498h+var_458], rax
0x18000dff1  test    rax, rax
0x18000dff4  jz      short loc_18000DFD3
0x18000dff6  mov     rdx, rdi; hResInfo
0x18000dff9  mov     rcx, rsi; hModule
0x18000dffc  call    cs:__imp_SizeofResource
0x18000e002  mov     edi, eax
0x18000e004  mov     [rsp+498h+var_468], eax
0x18000e008  inc     eax
0x18000e00a  cmp     eax, edi
0x18000e00c  jnb     short loc_18000E018
0x18000e00e  mov     ebx, 8007000Eh
0x18000e013  jmp     loc_18000E0BD
0x18000e018  mov     ecx, eax
0x18000e01a  mov     edx, 2
0x18000e01f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000e024  cmp     rax, 400h
0x18000e02a  jbe     short loc_18000E040
0x18000e02c  mov     rdx, rax
0x18000e02f  lea     rcx, [rsp+498h+var_438]
0x18000e034  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000e039  mov     rax, [rsp+498h+var_438]
0x18000e03e  jmp     short loc_18000E04A
0x18000e040  lea     rax, [rsp+498h+var_430]
0x18000e045  mov     [rsp+498h+var_438], rax
0x18000e04a  jmp     short loc_18000E061
0x18000e04c  xor     ebx, ebx
0x18000e04e  mov     rsi, [rsp+498h+var_460]
0x18000e053  mov     r14, [rsp+498h+var_458]
0x18000e058  mov     edi, [rsp+498h+var_468]
0x18000e05c  mov     rax, [rsp+498h+var_438]
0x18000e061  test    rax, rax
0x18000e064  jnz     short loc_18000E06D
0x18000e066  mov     ebx, 8007000Eh
0x18000e06b  jmp     short loc_18000E0B3
0x18000e06d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000e071  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000e076  mov     r9d, edi; cbMultiByte
0x18000e079  mov     r8, r14; lpMultiByteStr
0x18000e07c  xor     edx, edx; dwFlags
0x18000e07e  lea     ecx, [rdx+3]; CodePage
0x18000e081  call    cs:__imp_MultiByteToWideChar
0x18000e087  test    eax, eax
0x18000e089  jz      loc_18000DFD3
0x18000e08f  mov     ecx, eax
0x18000e091  mov     rax, [rsp+498h+var_438]
0x18000e096  mov     [rax+rcx*2], bx
0x18000e09a  mov     r8d, [rsp+498h+arg_20]; int
0x18000e0a2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18000e0a7  lea     rcx, [rsp+498h+var_448]; this
0x18000e0ac  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000e0b1  mov     ebx, eax
0x18000e0b3  mov     rcx, rsi; hLibModule
0x18000e0b6  call    cs:__imp_FreeLibrary
0x18000e0bc  nop
0x18000e0bd  lea     rcx, [rsp+498h+var_438]
0x18000e0c2  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000e0c7  nop
0x18000e0c8  lea     rcx, [rsp+498h+var_450]
0x18000e0cd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e0d2  mov     eax, ebx
0x18000e0d4  mov     rcx, [rsp+498h+var_28]
0x18000e0dc  xor     rcx, rsp; StackCookie
0x18000e0df  call    __security_check_cookie
0x18000e0e4  mov     rbx, [rsp+498h+arg_0]
0x18000e0ec  add     rsp, 480h
0x18000e0f3  pop     r14
0x18000e0f5  pop     rdi
0x18000e0f6  pop     rsi
0x18000e0f7  retn
```
