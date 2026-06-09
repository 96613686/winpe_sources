# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180014b7c`
- end: `0x180014d30`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `436`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180017f7c`
- `0x180018204`

## callees

- `0x180001710`
- `0x180002320`
- `0x1800057dc`
- `0x1800071a0`
- `0x1800081b0`
- `0x18000a7cc`
- `0x18000a984`
- `0x1800148d4`
- `0x180014b7c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180014cf3`
- `KERNEL32!FreeLibrary` at `0x180014cf3`
- `KERNEL32!LoadLibraryExW` at `0x180014bd7`
- `KERNEL32!LoadLibraryExW` at `0x180014bd7`
- `KERNEL32!FindResourceExW` at `0x180014c02`
- `KERNEL32!FindResourceExW` at `0x180014c02`
- `KERNEL32!SizeofResource` at `0x180014c39`
- `KERNEL32!SizeofResource` at `0x180014c39`
- `KERNEL32!LoadResource` at `0x180014c20`
- `KERNEL32!LoadResource` at `0x180014c20`
- `KERNEL32!MultiByteToWideChar` at `0x180014cbe`
- `KERNEL32!MultiByteToWideChar` at `0x180014cbe`

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
  HMODULE v9; // rsi
  unsigned int v10; // ebx
  HRSRC Resource; // rax
  HRSRC v12; // rbx
  unsigned int Error; // eax
  const CHAR *v14; // r14
  DWORD cchWideChar; // ebx
  unsigned __int64 v16; // rax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v20; // [rsp+38h] [rbp-470h]
  _QWORD *v21; // [rsp+48h] [rbp-460h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-458h] BYREF
  LPWSTR v23; // [rsp+60h] [rbp-448h] BYREF
  _BYTE v24[1032]; // [rsp+68h] [rbp-440h] BYREF

  v21 = 0;
  v22[1] = this;
  v22[0] = 0;
  memset_0(&v23, 0, 0x408u);
  v23 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v9 = Library;
  v20 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v12 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v14 = (const CHAR *)LoadResource(v9, Resource);
    if ( !v14 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v9, v12);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v10 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v16 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v16 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v24;
        v23 = (LPWSTR)v24;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v23, v16);
        lpWideCharStr = v23;
      }
    }
    catch ( ... )
    {
      v9 = v20;
      lpWideCharStr = v23;
    }
    if ( !lpWideCharStr )
    {
      v10 = -2147024882;
LABEL_16:
      FreeLibrary(v9);
      goto LABEL_17;
    }
    v18 = MultiByteToWideChar(3u, 0, v14, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v23[v18] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v22, v23, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v10 = Error;
    goto LABEL_16;
  }
  v10 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v23);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
  return v10;
}

```

## disassembly

```asm
0x180014b7c  push    rbx
0x180014b7e  push    rsi
0x180014b7f  push    rdi
0x180014b80  push    r14
0x180014b82  push    r15
0x180014b84  sub     rsp, 480h
0x180014b8b  mov     rax, cs:__security_cookie
0x180014b92  xor     rax, rsp
0x180014b95  mov     [rsp+4A8h+var_38], rax
0x180014b9d  mov     r15, r9
0x180014ba0  mov     r14, r8
0x180014ba3  mov     rbx, rdx
0x180014ba6  xor     edi, edi
0x180014ba8  mov     [rsp+4A8h+var_460], rdi
0x180014bad  mov     [rsp+4A8h+var_450], rcx
0x180014bb2  mov     [rsp+4A8h+var_458], rdi
0x180014bb7  xor     edx, edx; Val
0x180014bb9  mov     r8d, 408h; Size
0x180014bbf  lea     rcx, [rsp+4A8h+var_448]; void *
0x180014bc4  call    memset_0
0x180014bc9  mov     [rsp+4A8h+var_448], rdi
0x180014bce  xor     edx, edx; hFile
0x180014bd0  lea     r8d, [rdi+2]; dwFlags
0x180014bd4  mov     rcx, rbx; lpLibFileName
0x180014bd7  call    cs:__imp_LoadLibraryExW
0x180014bdd  mov     rsi, rax
0x180014be0  mov     [rsp+4A8h+var_470], rax
0x180014be5  test    rax, rax
0x180014be8  jnz     short loc_180014BF6
0x180014bea  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180014bef  mov     ebx, eax
0x180014bf1  jmp     loc_180014CFA
0x180014bf6  xor     r9d, r9d; wLanguage
0x180014bf9  mov     r8, r14; lpName
0x180014bfc  mov     rdx, r15; lpType
0x180014bff  mov     rcx, rsi; hModule
0x180014c02  call    cs:__imp_FindResourceExW
0x180014c08  mov     rbx, rax
0x180014c0b  test    rax, rax
0x180014c0e  jnz     short loc_180014C1A
0x180014c10  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180014c15  jmp     loc_180014CEE
0x180014c1a  mov     rdx, rbx; hResInfo
0x180014c1d  mov     rcx, rsi; hModule
0x180014c20  call    cs:__imp_LoadResource
0x180014c26  mov     r14, rax
0x180014c29  mov     [rsp+4A8h+var_468], rax
0x180014c2e  test    rax, rax
0x180014c31  jz      short loc_180014C10
0x180014c33  mov     rdx, rbx; hResInfo
0x180014c36  mov     rcx, rsi; hModule
0x180014c39  call    cs:__imp_SizeofResource
0x180014c3f  mov     ebx, eax
0x180014c41  mov     [rsp+4A8h+var_478], eax
0x180014c45  inc     eax
0x180014c47  cmp     eax, ebx
0x180014c49  jnb     short loc_180014C55
0x180014c4b  mov     ebx, 8007000Eh
0x180014c50  jmp     loc_180014CFA
0x180014c55  mov     ecx, eax
0x180014c57  mov     edx, 2
0x180014c5c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180014c61  cmp     rax, 400h
0x180014c67  jbe     short loc_180014C7D
0x180014c69  mov     rdx, rax
0x180014c6c  lea     rcx, [rsp+4A8h+var_448]
0x180014c71  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180014c76  mov     rax, [rsp+4A8h+var_448]
0x180014c7b  jmp     short loc_180014C87
0x180014c7d  lea     rax, [rsp+4A8h+var_440]
0x180014c82  mov     [rsp+4A8h+var_448], rax
0x180014c87  jmp     short loc_180014C9E
0x180014c89  xor     edi, edi
0x180014c8b  mov     rsi, [rsp+4A8h+var_470]
0x180014c90  mov     r14, [rsp+4A8h+var_468]
0x180014c95  mov     ebx, [rsp+4A8h+var_478]
0x180014c99  mov     rax, [rsp+4A8h+var_448]
0x180014c9e  test    rax, rax
0x180014ca1  jnz     short loc_180014CAA
0x180014ca3  mov     ebx, 8007000Eh
0x180014ca8  jmp     short loc_180014CF0
0x180014caa  mov     [rsp+4A8h+cchWideChar], ebx; cchWideChar
0x180014cae  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x180014cb3  mov     r9d, ebx; cbMultiByte
0x180014cb6  mov     r8, r14; lpMultiByteStr
0x180014cb9  xor     edx, edx; dwFlags
0x180014cbb  lea     ecx, [rdx+3]; CodePage
0x180014cbe  call    cs:__imp_MultiByteToWideChar
0x180014cc4  test    eax, eax
0x180014cc6  jz      loc_180014C10
0x180014ccc  mov     ecx, eax
0x180014cce  mov     rax, [rsp+4A8h+var_448]
0x180014cd3  mov     [rax+rcx*2], di
0x180014cd7  mov     r8d, [rsp+4A8h+arg_20]; int
0x180014cdf  mov     rdx, [rsp+4A8h+var_448]; unsigned __int16 *
0x180014ce4  lea     rcx, [rsp+4A8h+var_458]; this
0x180014ce9  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180014cee  mov     ebx, eax
0x180014cf0  mov     rcx, rsi; hLibModule
0x180014cf3  call    cs:__imp_FreeLibrary
0x180014cf9  nop
0x180014cfa  lea     rcx, [rsp+4A8h+var_448]
0x180014cff  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180014d04  nop
0x180014d05  lea     rcx, [rsp+4A8h+var_460]
0x180014d0a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180014d0f  mov     eax, ebx
0x180014d11  mov     rcx, [rsp+4A8h+var_38]
0x180014d19  xor     rcx, rsp; StackCookie
0x180014d1c  call    __security_check_cookie
0x180014d21  add     rsp, 480h
0x180014d28  pop     r15
0x180014d2a  pop     r14
0x180014d2c  pop     rdi
0x180014d2d  pop     rsi
0x180014d2e  pop     rbx
0x180014d2f  retn
```
