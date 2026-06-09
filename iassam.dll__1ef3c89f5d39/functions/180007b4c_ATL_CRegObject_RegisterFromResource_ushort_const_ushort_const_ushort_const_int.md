# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180007b4c`
- end: `0x180007cf4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800090ec`
- `0x180009364`

## callees

- `0x180002340`
- `0x180002b00`
- `0x1800030dc`
- `0x1800041b8`
- `0x1800044e8`
- `0x1800079dc`
- `0x180007b4c`
- `0x18002b4a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180007cb2`
- `KERNEL32!FreeLibrary` at `0x180007cb2`
- `KERNEL32!LoadLibraryExW` at `0x180007b96`
- `KERNEL32!LoadLibraryExW` at `0x180007b96`
- `KERNEL32!MultiByteToWideChar` at `0x180007c7d`
- `KERNEL32!MultiByteToWideChar` at `0x180007c7d`
- `KERNEL32!SizeofResource` at `0x180007bf8`
- `KERNEL32!SizeofResource` at `0x180007bf8`
- `KERNEL32!LoadResource` at `0x180007bdf`
- `KERNEL32!LoadResource` at `0x180007bdf`
- `KERNEL32!FindResourceExW` at `0x180007bc1`
- `KERNEL32!FindResourceExW` at `0x180007bc1`

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
0x180007b4c  mov     [rsp+arg_0], rbx
0x180007b51  push    rsi
0x180007b52  push    rdi
0x180007b53  push    r14
0x180007b55  sub     rsp, 480h
0x180007b5c  mov     rax, cs:__security_cookie
0x180007b63  xor     rax, rsp
0x180007b66  mov     [rsp+498h+var_28], rax
0x180007b6e  mov     r14, r9
0x180007b71  mov     rdi, r8
0x180007b74  mov     rax, rdx
0x180007b77  xor     ebx, ebx
0x180007b79  mov     [rsp+498h+var_450], rbx
0x180007b7e  mov     [rsp+498h+var_440], rcx
0x180007b83  mov     [rsp+498h+var_448], rbx
0x180007b88  mov     [rsp+498h+var_438], rbx
0x180007b8d  xor     edx, edx; hFile
0x180007b8f  lea     r8d, [rbx+2]; dwFlags
0x180007b93  mov     rcx, rax; lpLibFileName
0x180007b96  call    cs:__imp_LoadLibraryExW
0x180007b9c  mov     rsi, rax
0x180007b9f  mov     [rsp+498h+var_460], rax
0x180007ba4  test    rax, rax
0x180007ba7  jnz     short loc_180007BB5
0x180007ba9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007bae  mov     ebx, eax
0x180007bb0  jmp     loc_180007CB9
0x180007bb5  xor     r9d, r9d; wLanguage
0x180007bb8  mov     r8, rdi; lpName
0x180007bbb  mov     rdx, r14; lpType
0x180007bbe  mov     rcx, rsi; hModule
0x180007bc1  call    cs:__imp_FindResourceExW
0x180007bc7  mov     rdi, rax
0x180007bca  test    rax, rax
0x180007bcd  jnz     short loc_180007BD9
0x180007bcf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007bd4  jmp     loc_180007CAD
0x180007bd9  mov     rdx, rdi; hResInfo
0x180007bdc  mov     rcx, rsi; hModule
0x180007bdf  call    cs:__imp_LoadResource
0x180007be5  mov     r14, rax
0x180007be8  mov     [rsp+498h+var_458], rax
0x180007bed  test    rax, rax
0x180007bf0  jz      short loc_180007BCF
0x180007bf2  mov     rdx, rdi; hResInfo
0x180007bf5  mov     rcx, rsi; hModule
0x180007bf8  call    cs:__imp_SizeofResource
0x180007bfe  mov     edi, eax
0x180007c00  mov     [rsp+498h+var_468], eax
0x180007c04  inc     eax
0x180007c06  cmp     eax, edi
0x180007c08  jnb     short loc_180007C14
0x180007c0a  mov     ebx, 8007000Eh
0x180007c0f  jmp     loc_180007CB9
0x180007c14  mov     ecx, eax
0x180007c16  mov     edx, 2
0x180007c1b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180007c20  cmp     rax, 400h
0x180007c26  jbe     short loc_180007C3C
0x180007c28  mov     rdx, rax
0x180007c2b  lea     rcx, [rsp+498h+var_438]
0x180007c30  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007c35  mov     rax, [rsp+498h+var_438]
0x180007c3a  jmp     short loc_180007C46
0x180007c3c  lea     rax, [rsp+498h+var_430]
0x180007c41  mov     [rsp+498h+var_438], rax
0x180007c46  jmp     short loc_180007C5D
0x180007c48  xor     ebx, ebx
0x180007c4a  mov     rsi, [rsp+498h+var_460]
0x180007c4f  mov     r14, [rsp+498h+var_458]
0x180007c54  mov     edi, [rsp+498h+var_468]
0x180007c58  mov     rax, [rsp+498h+var_438]
0x180007c5d  test    rax, rax
0x180007c60  jnz     short loc_180007C69
0x180007c62  mov     ebx, 8007000Eh
0x180007c67  jmp     short loc_180007CAF
0x180007c69  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180007c6d  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180007c72  mov     r9d, edi; cbMultiByte
0x180007c75  mov     r8, r14; lpMultiByteStr
0x180007c78  xor     edx, edx; dwFlags
0x180007c7a  lea     ecx, [rdx+3]; CodePage
0x180007c7d  call    cs:__imp_MultiByteToWideChar
0x180007c83  test    eax, eax
0x180007c85  jz      loc_180007BCF
0x180007c8b  mov     ecx, eax
0x180007c8d  mov     rax, [rsp+498h+var_438]
0x180007c92  mov     [rax+rcx*2], bx
0x180007c96  mov     r8d, [rsp+498h+arg_20]; int
0x180007c9e  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180007ca3  lea     rcx, [rsp+498h+var_448]; this
0x180007ca8  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180007cad  mov     ebx, eax
0x180007caf  mov     rcx, rsi; hLibModule
0x180007cb2  call    cs:__imp_FreeLibrary
0x180007cb8  nop
0x180007cb9  lea     rcx, [rsp+498h+var_438]
0x180007cbe  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180007cc3  nop
0x180007cc4  lea     rcx, [rsp+498h+var_450]
0x180007cc9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007cce  mov     eax, ebx
0x180007cd0  mov     rcx, [rsp+498h+var_28]
0x180007cd8  xor     rcx, rsp; StackCookie
0x180007cdb  call    __security_check_cookie
0x180007ce0  mov     rbx, [rsp+498h+arg_0]
0x180007ce8  add     rsp, 480h
0x180007cef  pop     r14
0x180007cf1  pop     rdi
0x180007cf2  pop     rsi
0x180007cf3  retn
```
