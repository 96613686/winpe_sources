# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18001a668`
- end: `0x18001a810`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001b9dc`
- `0x18001bc54`

## callees

- `0x180001e80`
- `0x180016b3c`
- `0x180016bd0`
- `0x180016e6c`
- `0x180017c54`
- `0x180017f08`
- `0x18001a3cc`
- `0x18001a668`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001a6fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001a6fb`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001a714`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001a714`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a6b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a6b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a7ce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a7ce`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001a6dd`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001a6dd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a799`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a799`

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
0x18001a668  mov     [rsp+arg_0], rbx
0x18001a66d  push    rsi
0x18001a66e  push    rdi
0x18001a66f  push    r14
0x18001a671  sub     rsp, 480h
0x18001a678  mov     rax, cs:__security_cookie
0x18001a67f  xor     rax, rsp
0x18001a682  mov     [rsp+498h+var_28], rax
0x18001a68a  mov     r14, r9
0x18001a68d  mov     rdi, r8
0x18001a690  mov     rax, rdx
0x18001a693  xor     ebx, ebx
0x18001a695  mov     [rsp+498h+var_450], rbx
0x18001a69a  mov     [rsp+498h+var_440], rcx
0x18001a69f  mov     [rsp+498h+var_448], rbx
0x18001a6a4  mov     [rsp+498h+var_438], rbx
0x18001a6a9  xor     edx, edx; hFile
0x18001a6ab  lea     r8d, [rbx+2]; dwFlags
0x18001a6af  mov     rcx, rax; lpLibFileName
0x18001a6b2  call    cs:__imp_LoadLibraryExW
0x18001a6b8  mov     rsi, rax
0x18001a6bb  mov     [rsp+498h+var_460], rax
0x18001a6c0  test    rax, rax
0x18001a6c3  jnz     short loc_18001A6D1
0x18001a6c5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a6ca  mov     ebx, eax
0x18001a6cc  jmp     loc_18001A7D5
0x18001a6d1  xor     r9d, r9d; wLanguage
0x18001a6d4  mov     r8, rdi; lpName
0x18001a6d7  mov     rdx, r14; lpType
0x18001a6da  mov     rcx, rsi; hModule
0x18001a6dd  call    cs:__imp_FindResourceExW
0x18001a6e3  mov     rdi, rax
0x18001a6e6  test    rax, rax
0x18001a6e9  jnz     short loc_18001A6F5
0x18001a6eb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a6f0  jmp     loc_18001A7C9
0x18001a6f5  mov     rdx, rdi; hResInfo
0x18001a6f8  mov     rcx, rsi; hModule
0x18001a6fb  call    cs:__imp_LoadResource
0x18001a701  mov     r14, rax
0x18001a704  mov     [rsp+498h+var_458], rax
0x18001a709  test    rax, rax
0x18001a70c  jz      short loc_18001A6EB
0x18001a70e  mov     rdx, rdi; hResInfo
0x18001a711  mov     rcx, rsi; hModule
0x18001a714  call    cs:__imp_SizeofResource
0x18001a71a  mov     edi, eax
0x18001a71c  mov     [rsp+498h+var_468], eax
0x18001a720  inc     eax
0x18001a722  cmp     eax, edi
0x18001a724  jnb     short loc_18001A730
0x18001a726  mov     ebx, 8007000Eh
0x18001a72b  jmp     loc_18001A7D5
0x18001a730  mov     ecx, eax
0x18001a732  mov     edx, 2
0x18001a737  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001a73c  cmp     rax, 400h
0x18001a742  jbe     short loc_18001A758
0x18001a744  mov     rdx, rax
0x18001a747  lea     rcx, [rsp+498h+var_438]
0x18001a74c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001a751  mov     rax, [rsp+498h+var_438]
0x18001a756  jmp     short loc_18001A762
0x18001a758  lea     rax, [rsp+498h+var_430]
0x18001a75d  mov     [rsp+498h+var_438], rax
0x18001a762  jmp     short loc_18001A779
0x18001a764  xor     ebx, ebx
0x18001a766  mov     rsi, [rsp+498h+var_460]
0x18001a76b  mov     r14, [rsp+498h+var_458]
0x18001a770  mov     edi, [rsp+498h+var_468]
0x18001a774  mov     rax, [rsp+498h+var_438]
0x18001a779  test    rax, rax
0x18001a77c  jnz     short loc_18001A785
0x18001a77e  mov     ebx, 8007000Eh
0x18001a783  jmp     short loc_18001A7CB
0x18001a785  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18001a789  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001a78e  mov     r9d, edi; cbMultiByte
0x18001a791  mov     r8, r14; lpMultiByteStr
0x18001a794  xor     edx, edx; dwFlags
0x18001a796  lea     ecx, [rdx+3]; CodePage
0x18001a799  call    cs:__imp_MultiByteToWideChar
0x18001a79f  test    eax, eax
0x18001a7a1  jz      loc_18001A6EB
0x18001a7a7  mov     ecx, eax
0x18001a7a9  mov     rax, [rsp+498h+var_438]
0x18001a7ae  mov     [rax+rcx*2], bx
0x18001a7b2  mov     r8d, [rsp+498h+arg_20]; int
0x18001a7ba  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18001a7bf  lea     rcx, [rsp+498h+var_448]; this
0x18001a7c4  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18001a7c9  mov     ebx, eax
0x18001a7cb  mov     rcx, rsi; hLibModule
0x18001a7ce  call    cs:__imp_FreeLibrary
0x18001a7d4  nop
0x18001a7d5  lea     rcx, [rsp+498h+var_438]
0x18001a7da  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001a7df  nop
0x18001a7e0  lea     rcx, [rsp+498h+var_450]
0x18001a7e5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a7ea  mov     eax, ebx
0x18001a7ec  mov     rcx, [rsp+498h+var_28]
0x18001a7f4  xor     rcx, rsp; StackCookie
0x18001a7f7  call    __security_check_cookie
0x18001a7fc  mov     rbx, [rsp+498h+arg_0]
0x18001a804  add     rsp, 480h
0x18001a80b  pop     r14
0x18001a80d  pop     rdi
0x18001a80e  pop     rsi
0x18001a80f  retn
```
