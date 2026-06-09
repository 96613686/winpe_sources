# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180053810`
- end: `0x1800539b8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180054d2c`
- `0x180054fa4`

## callees

- `0x18004e0c0`
- `0x18004fbcc`
- `0x18005021c`
- `0x1800502bc`
- `0x180050ca8`
- `0x180050e5c`
- `0x1800536a0`
- `0x180053810`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800538a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800538a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005385a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005385a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800538bc`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800538bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180053976`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180053976`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180053885`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180053885`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180053941`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180053941`

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
0x180053810  mov     [rsp+arg_0], rbx
0x180053815  push    rsi
0x180053816  push    rdi
0x180053817  push    r14
0x180053819  sub     rsp, 480h
0x180053820  mov     rax, cs:__security_cookie
0x180053827  xor     rax, rsp
0x18005382a  mov     [rsp+498h+var_28], rax
0x180053832  mov     r14, r9
0x180053835  mov     rdi, r8
0x180053838  mov     rax, rdx
0x18005383b  xor     ebx, ebx
0x18005383d  mov     [rsp+498h+var_450], rbx
0x180053842  mov     [rsp+498h+var_440], rcx
0x180053847  mov     [rsp+498h+var_448], rbx
0x18005384c  mov     [rsp+498h+var_438], rbx
0x180053851  xor     edx, edx; hFile
0x180053853  lea     r8d, [rbx+2]; dwFlags
0x180053857  mov     rcx, rax; lpLibFileName
0x18005385a  call    cs:__imp_LoadLibraryExW
0x180053860  mov     rsi, rax
0x180053863  mov     [rsp+498h+var_460], rax
0x180053868  test    rax, rax
0x18005386b  jnz     short loc_180053879
0x18005386d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180053872  mov     ebx, eax
0x180053874  jmp     loc_18005397D
0x180053879  xor     r9d, r9d; wLanguage
0x18005387c  mov     r8, rdi; lpName
0x18005387f  mov     rdx, r14; lpType
0x180053882  mov     rcx, rsi; hModule
0x180053885  call    cs:__imp_FindResourceExW
0x18005388b  mov     rdi, rax
0x18005388e  test    rax, rax
0x180053891  jnz     short loc_18005389D
0x180053893  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180053898  jmp     loc_180053971
0x18005389d  mov     rdx, rdi; hResInfo
0x1800538a0  mov     rcx, rsi; hModule
0x1800538a3  call    cs:__imp_LoadResource
0x1800538a9  mov     r14, rax
0x1800538ac  mov     [rsp+498h+var_458], rax
0x1800538b1  test    rax, rax
0x1800538b4  jz      short loc_180053893
0x1800538b6  mov     rdx, rdi; hResInfo
0x1800538b9  mov     rcx, rsi; hModule
0x1800538bc  call    cs:__imp_SizeofResource
0x1800538c2  mov     edi, eax
0x1800538c4  mov     [rsp+498h+var_468], eax
0x1800538c8  inc     eax
0x1800538ca  cmp     eax, edi
0x1800538cc  jnb     short loc_1800538D8
0x1800538ce  mov     ebx, 8007000Eh
0x1800538d3  jmp     loc_18005397D
0x1800538d8  mov     ecx, eax
0x1800538da  mov     edx, 2
0x1800538df  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800538e4  cmp     rax, 400h
0x1800538ea  jbe     short loc_180053900
0x1800538ec  mov     rdx, rax
0x1800538ef  lea     rcx, [rsp+498h+var_438]
0x1800538f4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800538f9  mov     rax, [rsp+498h+var_438]
0x1800538fe  jmp     short loc_18005390A
0x180053900  lea     rax, [rsp+498h+var_430]
0x180053905  mov     [rsp+498h+var_438], rax
0x18005390a  jmp     short loc_180053921
0x18005390c  xor     ebx, ebx
0x18005390e  mov     rsi, [rsp+498h+var_460]
0x180053913  mov     r14, [rsp+498h+var_458]
0x180053918  mov     edi, [rsp+498h+var_468]
0x18005391c  mov     rax, [rsp+498h+var_438]
0x180053921  test    rax, rax
0x180053924  jnz     short loc_18005392D
0x180053926  mov     ebx, 8007000Eh
0x18005392b  jmp     short loc_180053973
0x18005392d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180053931  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180053936  mov     r9d, edi; cbMultiByte
0x180053939  mov     r8, r14; lpMultiByteStr
0x18005393c  xor     edx, edx; dwFlags
0x18005393e  lea     ecx, [rdx+3]; CodePage
0x180053941  call    cs:__imp_MultiByteToWideChar
0x180053947  test    eax, eax
0x180053949  jz      loc_180053893
0x18005394f  mov     ecx, eax
0x180053951  mov     rax, [rsp+498h+var_438]
0x180053956  mov     [rax+rcx*2], bx
0x18005395a  mov     r8d, [rsp+498h+arg_20]; int
0x180053962  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180053967  lea     rcx, [rsp+498h+var_448]; this
0x18005396c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180053971  mov     ebx, eax
0x180053973  mov     rcx, rsi; hLibModule
0x180053976  call    cs:__imp_FreeLibrary
0x18005397c  nop
0x18005397d  lea     rcx, [rsp+498h+var_438]
0x180053982  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180053987  nop
0x180053988  lea     rcx, [rsp+498h+var_450]
0x18005398d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180053992  mov     eax, ebx
0x180053994  mov     rcx, [rsp+498h+var_28]
0x18005399c  xor     rcx, rsp; StackCookie
0x18005399f  call    __security_check_cookie
0x1800539a4  mov     rbx, [rsp+498h+arg_0]
0x1800539ac  add     rsp, 480h
0x1800539b3  pop     r14
0x1800539b5  pop     rdi
0x1800539b6  pop     rsi
0x1800539b7  retn
```
