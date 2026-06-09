# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180012f9c`
- end: `0x18001312c`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `400`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180013ad8`

## callees

- `0x180010f5c`
- `0x180011024`
- `0x1800110e8`
- `0x1800119bc`
- `0x180011b10`
- `0x180012e28`
- `0x180012f9c`
- `0x180049880`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x18001301c`
- `KERNEL32!FindResourceExW` at `0x18001301c`
- `KERNEL32!LoadResource` at `0x18001303a`
- `KERNEL32!LoadResource` at `0x18001303a`
- `KERNEL32!SizeofResource` at `0x18001304e`
- `KERNEL32!SizeofResource` at `0x18001304e`
- `KERNEL32!MultiByteToWideChar` at `0x1800130b8`
- `KERNEL32!MultiByteToWideChar` at `0x1800130b8`
- `KERNEL32!LoadLibraryExW` at `0x180012ff6`
- `KERNEL32!LoadLibraryExW` at `0x180012ff6`
- `KERNEL32!FreeLibrary` at `0x1800130ee`
- `KERNEL32!FreeLibrary` at `0x1800130ee`

## pseudocode

```c
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
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[1032]; // [rsp+58h] [rbp-A8h] BYREF

  v20[1] = this;
  v19 = 0;
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
0x180012f9c  mov     [rsp-8+arg_0], rbx
0x180012fa1  push    rbp
0x180012fa2  push    rsi
0x180012fa3  push    rdi
0x180012fa4  lea     rbp, [rsp-370h]
0x180012fac  sub     rsp, 470h
0x180012fb3  mov     rax, cs:__security_cookie
0x180012fba  xor     rax, rsp
0x180012fbd  mov     [rbp+380h+var_20], rax
0x180012fc4  mov     rax, rdx
0x180012fc7  mov     [rsp+480h+var_440], rcx
0x180012fcc  xor     edx, edx; hFile
0x180012fce  mov     [rsp+480h+var_450], 0
0x180012fd7  mov     rbx, r8
0x180012fda  mov     [rsp+480h+var_448], 0
0x180012fe3  mov     rcx, rax; lpLibFileName
0x180012fe6  mov     [rsp+480h+var_430], 0
0x180012fef  mov     rsi, r9
0x180012ff2  lea     r8d, [rdx+2]; dwFlags
0x180012ff6  call    cs:__imp_LoadLibraryExW
0x180012ffc  mov     rdi, rax
0x180012fff  test    rax, rax
0x180013002  jnz     short loc_180013010
0x180013004  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013009  mov     ebx, eax
0x18001300b  jmp     loc_1800130F4
0x180013010  xor     r9d, r9d; wLanguage
0x180013013  mov     r8, rbx; lpName
0x180013016  mov     rdx, rsi; lpType
0x180013019  mov     rcx, rdi; hModule
0x18001301c  call    cs:__imp_FindResourceExW
0x180013022  mov     rbx, rax
0x180013025  test    rax, rax
0x180013028  jnz     short loc_180013034
0x18001302a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001302f  jmp     loc_1800130E9
0x180013034  mov     rdx, rbx; hResInfo
0x180013037  mov     rcx, rdi; hModule
0x18001303a  call    cs:__imp_LoadResource
0x180013040  mov     rsi, rax
0x180013043  test    rax, rax
0x180013046  jz      short loc_18001302A
0x180013048  mov     rdx, rbx; hResInfo
0x18001304b  mov     rcx, rdi; hModule
0x18001304e  call    cs:__imp_SizeofResource
0x180013054  mov     ebx, eax
0x180013056  inc     eax
0x180013058  cmp     eax, ebx
0x18001305a  jnb     short loc_180013066
0x18001305c  mov     ebx, 8007000Eh
0x180013061  jmp     loc_1800130F4
0x180013066  mov     ecx, eax
0x180013068  mov     edx, 2
0x18001306d  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180013072  cmp     rax, 400h
0x180013078  jbe     short loc_18001308E
0x18001307a  mov     rdx, rax
0x18001307d  lea     rcx, [rsp+480h+var_430]
0x180013082  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180013087  mov     rax, [rsp+480h+var_430]
0x18001308c  jmp     short loc_180013098
0x18001308e  lea     rax, [rsp+480h+var_428]
0x180013093  mov     [rsp+480h+var_430], rax
0x180013098  test    rax, rax
0x18001309b  jnz     short loc_1800130A4
0x18001309d  mov     ebx, 8007000Eh
0x1800130a2  jmp     short loc_1800130EB
0x1800130a4  xor     edx, edx; dwFlags
0x1800130a6  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x1800130aa  mov     r9d, ebx; cbMultiByte
0x1800130ad  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x1800130b2  mov     r8, rsi; lpMultiByteStr
0x1800130b5  lea     ecx, [rdx+3]; CodePage
0x1800130b8  call    cs:__imp_MultiByteToWideChar
0x1800130be  test    eax, eax
0x1800130c0  jz      loc_18001302A
0x1800130c6  mov     r8d, [rbp+380h+arg_20]; int
0x1800130cd  xor     ecx, ecx
0x1800130cf  mov     edx, eax
0x1800130d1  mov     rax, [rsp+480h+var_430]
0x1800130d6  mov     [rax+rdx*2], cx
0x1800130da  lea     rcx, [rsp+480h+var_448]; this
0x1800130df  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x1800130e4  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800130e9  mov     ebx, eax
0x1800130eb  mov     rcx, rdi; hLibModule
0x1800130ee  call    cs:__imp_FreeLibrary
0x1800130f4  lea     rcx, [rsp+480h+var_430]
0x1800130f9  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800130fe  lea     rcx, [rsp+480h+var_450]
0x180013103  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013108  mov     eax, ebx
0x18001310a  mov     rcx, [rbp+380h+var_20]
0x180013111  xor     rcx, rsp; StackCookie
0x180013114  call    __security_check_cookie
0x180013119  mov     rbx, [rsp+480h+arg_0]
0x180013121  add     rsp, 470h
0x180013128  pop     rdi
0x180013129  pop     rsi
0x18001312a  pop     rbp
0x18001312b  retn
```
