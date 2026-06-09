# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180049128`
- end: `0x1800492ba`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `402`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180049fdc`
- `0x18004a254`

## callees

- `0x180047054`
- `0x180047080`
- `0x1800471f0`
- `0x180047ab4`
- `0x180047d20`
- `0x180048e9c`
- `0x180049128`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180049182`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180049182`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800491da`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800491da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004927a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004927a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800491c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800491c6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800491a8`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800491a8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180049244`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180049244`

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
  HMODULE v8; // rdi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int Error; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[1032]; // [rsp+58h] [rbp-A8h] BYREF

  v19 = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
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
    v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
    if ( v15 <= 0x400 )
    {
      lpWideCharStr = (WCHAR *)v22;
      v21 = (LPWSTR)v22;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, v15);
      lpWideCharStr = v21;
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
      v21[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x180049128  mov     [rsp-8+arg_0], rbx
0x18004912d  push    rbp
0x18004912e  push    rsi
0x18004912f  push    rdi
0x180049130  lea     rbp, [rsp-370h]
0x180049138  sub     rsp, 470h
0x18004913f  mov     rax, cs:__security_cookie
0x180049146  xor     rax, rsp
0x180049149  mov     [rbp+380h+var_20], rax
0x180049150  mov     rsi, r9
0x180049153  mov     rbx, r8
0x180049156  mov     rax, rdx
0x180049159  mov     [rsp+480h+var_450], 0
0x180049162  mov     [rsp+480h+var_440], rcx
0x180049167  mov     [rsp+480h+var_448], 0
0x180049170  mov     [rsp+480h+var_430], 0
0x180049179  xor     edx, edx; hFile
0x18004917b  lea     r8d, [rdx+2]; dwFlags
0x18004917f  mov     rcx, rax; lpLibFileName
0x180049182  call    cs:__imp_LoadLibraryExW
0x180049188  mov     rdi, rax
0x18004918b  test    rax, rax
0x18004918e  jnz     short loc_18004919C
0x180049190  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180049195  mov     ebx, eax
0x180049197  jmp     loc_180049281
0x18004919c  xor     r9d, r9d; wLanguage
0x18004919f  mov     r8, rbx; lpName
0x1800491a2  mov     rdx, rsi; lpType
0x1800491a5  mov     rcx, rdi; hModule
0x1800491a8  call    cs:__imp_FindResourceExW
0x1800491ae  mov     rbx, rax
0x1800491b1  test    rax, rax
0x1800491b4  jnz     short loc_1800491C0
0x1800491b6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800491bb  jmp     loc_180049275
0x1800491c0  mov     rdx, rbx; hResInfo
0x1800491c3  mov     rcx, rdi; hModule
0x1800491c6  call    cs:__imp_LoadResource
0x1800491cc  mov     rsi, rax
0x1800491cf  test    rax, rax
0x1800491d2  jz      short loc_1800491B6
0x1800491d4  mov     rdx, rbx; hResInfo
0x1800491d7  mov     rcx, rdi; hModule
0x1800491da  call    cs:__imp_SizeofResource
0x1800491e0  mov     ebx, eax
0x1800491e2  inc     eax
0x1800491e4  cmp     eax, ebx
0x1800491e6  jnb     short loc_1800491F2
0x1800491e8  mov     ebx, 8007000Eh
0x1800491ed  jmp     loc_180049281
0x1800491f2  mov     ecx, eax
0x1800491f4  mov     edx, 2
0x1800491f9  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800491fe  cmp     rax, 400h
0x180049204  jbe     short loc_18004921A
0x180049206  mov     rdx, rax
0x180049209  lea     rcx, [rsp+480h+var_430]
0x18004920e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180049213  mov     rax, [rsp+480h+var_430]
0x180049218  jmp     short loc_180049224
0x18004921a  lea     rax, [rsp+480h+var_428]
0x18004921f  mov     [rsp+480h+var_430], rax
0x180049224  test    rax, rax
0x180049227  jnz     short loc_180049230
0x180049229  mov     ebx, 8007000Eh
0x18004922e  jmp     short loc_180049277
0x180049230  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x180049234  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x180049239  mov     r9d, ebx; cbMultiByte
0x18004923c  mov     r8, rsi; lpMultiByteStr
0x18004923f  xor     edx, edx; dwFlags
0x180049241  lea     ecx, [rdx+3]; CodePage
0x180049244  call    cs:__imp_MultiByteToWideChar
0x18004924a  test    eax, eax
0x18004924c  jz      loc_1800491B6
0x180049252  mov     edx, eax
0x180049254  xor     ecx, ecx
0x180049256  mov     rax, [rsp+480h+var_430]
0x18004925b  mov     [rax+rdx*2], cx
0x18004925f  mov     r8d, [rbp+380h+arg_20]; int
0x180049266  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x18004926b  lea     rcx, [rsp+480h+var_448]; this
0x180049270  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180049275  mov     ebx, eax
0x180049277  mov     rcx, rdi; hLibModule
0x18004927a  call    cs:__imp_FreeLibrary
0x180049280  nop
0x180049281  lea     rcx, [rsp+480h+var_430]
0x180049286  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18004928b  nop
0x18004928c  lea     rcx, [rsp+480h+var_450]
0x180049291  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180049296  mov     eax, ebx
0x180049298  mov     rcx, [rbp+380h+var_20]
0x18004929f  xor     rcx, rsp; StackCookie
0x1800492a2  call    __security_check_cookie
0x1800492a7  mov     rbx, [rsp+480h+arg_0]
0x1800492af  add     rsp, 470h
0x1800492b6  pop     rdi
0x1800492b7  pop     rsi
0x1800492b8  pop     rbp
0x1800492b9  retn
```
