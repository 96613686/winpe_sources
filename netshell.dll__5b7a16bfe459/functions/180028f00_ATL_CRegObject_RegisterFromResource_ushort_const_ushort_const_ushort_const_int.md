# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180028f00`
- end: `0x1800290a8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002a11c`
- `0x18002a394`

## callees

- `0x18001e1e0`
- `0x18002325c`
- `0x1800238f8`
- `0x180024108`
- `0x1800254fc`
- `0x1800257e8`
- `0x180028d8c`
- `0x180028f00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180028f93`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180028f93`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180028fac`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180028fac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028f4a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028f4a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029066`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029066`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180028f75`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180028f75`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180029031`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180029031`

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
0x180028f00  mov     [rsp+arg_0], rbx
0x180028f05  push    rsi
0x180028f06  push    rdi
0x180028f07  push    r14
0x180028f09  sub     rsp, 480h
0x180028f10  mov     rax, cs:__security_cookie
0x180028f17  xor     rax, rsp
0x180028f1a  mov     [rsp+498h+var_28], rax
0x180028f22  mov     r14, r9
0x180028f25  mov     rdi, r8
0x180028f28  mov     rax, rdx
0x180028f2b  xor     ebx, ebx
0x180028f2d  mov     [rsp+498h+var_450], rbx
0x180028f32  mov     [rsp+498h+var_440], rcx
0x180028f37  mov     [rsp+498h+var_448], rbx
0x180028f3c  mov     [rsp+498h+var_438], rbx
0x180028f41  xor     edx, edx; hFile
0x180028f43  lea     r8d, [rbx+2]; dwFlags
0x180028f47  mov     rcx, rax; lpLibFileName
0x180028f4a  call    cs:__imp_LoadLibraryExW
0x180028f50  mov     rsi, rax
0x180028f53  mov     [rsp+498h+var_460], rax
0x180028f58  test    rax, rax
0x180028f5b  jnz     short loc_180028F69
0x180028f5d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028f62  mov     ebx, eax
0x180028f64  jmp     loc_18002906D
0x180028f69  xor     r9d, r9d; wLanguage
0x180028f6c  mov     r8, rdi; lpName
0x180028f6f  mov     rdx, r14; lpType
0x180028f72  mov     rcx, rsi; hModule
0x180028f75  call    cs:__imp_FindResourceExW
0x180028f7b  mov     rdi, rax
0x180028f7e  test    rax, rax
0x180028f81  jnz     short loc_180028F8D
0x180028f83  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028f88  jmp     loc_180029061
0x180028f8d  mov     rdx, rdi; hResInfo
0x180028f90  mov     rcx, rsi; hModule
0x180028f93  call    cs:__imp_LoadResource
0x180028f99  mov     r14, rax
0x180028f9c  mov     [rsp+498h+var_458], rax
0x180028fa1  test    rax, rax
0x180028fa4  jz      short loc_180028F83
0x180028fa6  mov     rdx, rdi; hResInfo
0x180028fa9  mov     rcx, rsi; hModule
0x180028fac  call    cs:__imp_SizeofResource
0x180028fb2  mov     edi, eax
0x180028fb4  mov     [rsp+498h+var_468], eax
0x180028fb8  inc     eax
0x180028fba  cmp     eax, edi
0x180028fbc  jnb     short loc_180028FC8
0x180028fbe  mov     ebx, 8007000Eh
0x180028fc3  jmp     loc_18002906D
0x180028fc8  mov     ecx, eax
0x180028fca  mov     edx, 2
0x180028fcf  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180028fd4  cmp     rax, 400h
0x180028fda  jbe     short loc_180028FF0
0x180028fdc  mov     rdx, rax
0x180028fdf  lea     rcx, [rsp+498h+var_438]
0x180028fe4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180028fe9  mov     rax, [rsp+498h+var_438]
0x180028fee  jmp     short loc_180028FFA
0x180028ff0  lea     rax, [rsp+498h+var_430]
0x180028ff5  mov     [rsp+498h+var_438], rax
0x180028ffa  jmp     short loc_180029011
0x180028ffc  xor     ebx, ebx
0x180028ffe  mov     rsi, [rsp+498h+var_460]
0x180029003  mov     r14, [rsp+498h+var_458]
0x180029008  mov     edi, [rsp+498h+var_468]
0x18002900c  mov     rax, [rsp+498h+var_438]
0x180029011  test    rax, rax
0x180029014  jnz     short loc_18002901D
0x180029016  mov     ebx, 8007000Eh
0x18002901b  jmp     short loc_180029063
0x18002901d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180029021  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180029026  mov     r9d, edi; cbMultiByte
0x180029029  mov     r8, r14; lpMultiByteStr
0x18002902c  xor     edx, edx; dwFlags
0x18002902e  lea     ecx, [rdx+3]; CodePage
0x180029031  call    cs:__imp_MultiByteToWideChar
0x180029037  test    eax, eax
0x180029039  jz      loc_180028F83
0x18002903f  mov     ecx, eax
0x180029041  mov     rax, [rsp+498h+var_438]
0x180029046  mov     [rax+rcx*2], bx
0x18002904a  mov     r8d, [rsp+498h+arg_20]; int
0x180029052  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180029057  lea     rcx, [rsp+498h+var_448]; this
0x18002905c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180029061  mov     ebx, eax
0x180029063  mov     rcx, rsi; hLibModule
0x180029066  call    cs:__imp_FreeLibrary
0x18002906c  nop
0x18002906d  lea     rcx, [rsp+498h+var_438]
0x180029072  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180029077  nop
0x180029078  lea     rcx, [rsp+498h+var_450]
0x18002907d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180029082  mov     eax, ebx
0x180029084  mov     rcx, [rsp+498h+var_28]
0x18002908c  xor     rcx, rsp; StackCookie
0x18002908f  call    __security_check_cookie
0x180029094  mov     rbx, [rsp+498h+arg_0]
0x18002909c  add     rsp, 480h
0x1800290a3  pop     r14
0x1800290a5  pop     rdi
0x1800290a6  pop     rsi
0x1800290a7  retn
```
