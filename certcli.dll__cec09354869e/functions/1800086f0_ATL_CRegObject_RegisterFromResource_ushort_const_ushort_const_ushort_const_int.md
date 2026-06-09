# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800086f0`
- end: `0x180008893`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `419`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800098cc`
- `0x180009b70`

## callees

- `0x180004a8c`
- `0x180004e8c`
- `0x180005160`
- `0x180005dac`
- `0x180006008`
- `0x1800082ac`
- `0x1800086f0`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000879c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000879c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008783`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008783`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000873a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000873a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180008765`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180008765`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008851`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008851`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000881c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000881c`

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
  int v16; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  _QWORD *v19; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR lpWideCharStr; // [rsp+60h] [rbp-438h] BYREF
  char v22; // [rsp+68h] [rbp-430h] BYREF

  v19 = 0;
  v20[1] = this;
  v20[0] = 0;
  lpWideCharStr = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v18 = Library;
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
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
      if ( v15 <= 0x400 )
        lpWideCharStr = (LPWSTR)&v22;
      else
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpWideCharStr, v15);
    }
    catch ( ... )
    {
      v8 = v18;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v16 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v16 )
    {
      lpWideCharStr[v16] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, lpWideCharStr, a5);
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpWideCharStr);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x1800086f0  mov     [rsp+arg_0], rbx
0x1800086f5  push    rsi
0x1800086f6  push    rdi
0x1800086f7  push    r14
0x1800086f9  sub     rsp, 480h
0x180008700  mov     rax, cs:__security_cookie
0x180008707  xor     rax, rsp
0x18000870a  mov     [rsp+498h+var_28], rax
0x180008712  mov     r14, r9
0x180008715  mov     rdi, r8
0x180008718  mov     rax, rdx
0x18000871b  xor     ebx, ebx
0x18000871d  mov     [rsp+498h+var_450], rbx
0x180008722  mov     [rsp+498h+var_440], rcx
0x180008727  mov     [rsp+498h+var_448], rbx
0x18000872c  mov     [rsp+498h+var_438], rbx
0x180008731  xor     edx, edx; hFile
0x180008733  lea     r8d, [rbx+2]; dwFlags
0x180008737  mov     rcx, rax; lpLibFileName
0x18000873a  call    cs:__imp_LoadLibraryExW
0x180008740  mov     rsi, rax
0x180008743  mov     [rsp+498h+var_460], rax
0x180008748  test    rax, rax
0x18000874b  jnz     short loc_180008759
0x18000874d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008752  mov     ebx, eax
0x180008754  jmp     loc_180008858
0x180008759  xor     r9d, r9d; wLanguage
0x18000875c  mov     r8, rdi; lpName
0x18000875f  mov     rdx, r14; lpType
0x180008762  mov     rcx, rsi; hModule
0x180008765  call    cs:__imp_FindResourceExW
0x18000876b  mov     rdi, rax
0x18000876e  test    rax, rax
0x180008771  jnz     short loc_18000877D
0x180008773  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008778  jmp     loc_18000884C
0x18000877d  mov     rdx, rdi; hResInfo
0x180008780  mov     rcx, rsi; hModule
0x180008783  call    cs:__imp_LoadResource
0x180008789  mov     r14, rax
0x18000878c  mov     [rsp+498h+var_458], rax
0x180008791  test    rax, rax
0x180008794  jz      short loc_180008773
0x180008796  mov     rdx, rdi; hResInfo
0x180008799  mov     rcx, rsi; hModule
0x18000879c  call    cs:__imp_SizeofResource
0x1800087a2  mov     edi, eax
0x1800087a4  mov     [rsp+498h+var_468], eax
0x1800087a8  inc     eax
0x1800087aa  cmp     eax, edi
0x1800087ac  jnb     short loc_1800087B8
0x1800087ae  mov     ebx, 8007000Eh
0x1800087b3  jmp     loc_180008858
0x1800087b8  mov     ecx, eax
0x1800087ba  mov     edx, 2
0x1800087bf  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800087c4  cmp     rax, 400h
0x1800087ca  jbe     short loc_1800087DB
0x1800087cc  mov     rdx, rax
0x1800087cf  lea     rcx, [rsp+498h+var_438]
0x1800087d4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800087d9  jmp     short loc_1800087E5
0x1800087db  lea     rax, [rsp+498h+var_430]
0x1800087e0  mov     [rsp+498h+var_438], rax
0x1800087e5  jmp     short loc_1800087F7
0x1800087e7  xor     ebx, ebx
0x1800087e9  mov     rsi, [rsp+498h+var_460]
0x1800087ee  mov     r14, [rsp+498h+var_458]
0x1800087f3  mov     edi, [rsp+498h+var_468]
0x1800087f7  mov     rax, [rsp+498h+var_438]
0x1800087fc  test    rax, rax
0x1800087ff  jnz     short loc_180008808
0x180008801  mov     ebx, 8007000Eh
0x180008806  jmp     short loc_18000884E
0x180008808  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000880c  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180008811  mov     r9d, edi; cbMultiByte
0x180008814  mov     r8, r14; lpMultiByteStr
0x180008817  xor     edx, edx; dwFlags
0x180008819  lea     ecx, [rdx+3]; CodePage
0x18000881c  call    cs:__imp_MultiByteToWideChar
0x180008822  test    eax, eax
0x180008824  jz      loc_180008773
0x18000882a  mov     ecx, eax
0x18000882c  mov     rax, [rsp+498h+var_438]
0x180008831  mov     [rax+rcx*2], bx
0x180008835  mov     r8d, [rsp+498h+arg_20]; int
0x18000883d  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180008842  lea     rcx, [rsp+498h+var_448]; this
0x180008847  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000884c  mov     ebx, eax
0x18000884e  mov     rcx, rsi; hLibModule
0x180008851  call    cs:__imp_FreeLibrary
0x180008857  nop
0x180008858  lea     rcx, [rsp+498h+var_438]
0x18000885d  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180008862  nop
0x180008863  lea     rcx, [rsp+498h+var_450]
0x180008868  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000886d  mov     eax, ebx
0x18000886f  mov     rcx, [rsp+498h+var_28]
0x180008877  xor     rcx, rsp; StackCookie
0x18000887a  call    __security_check_cookie
0x18000887f  mov     rbx, [rsp+498h+arg_0]
0x180008887  add     rsp, 480h
0x18000888e  pop     r14
0x180008890  pop     rdi
0x180008891  pop     rsi
0x180008892  retn
```
