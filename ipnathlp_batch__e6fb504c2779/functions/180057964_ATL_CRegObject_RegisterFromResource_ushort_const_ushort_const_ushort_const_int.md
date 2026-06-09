# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180057964`
- end: `0x180057b31`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `461`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180058f30`
- `0x1800591b4`

## callees

- `0x180051f30`
- `0x180053aa0`
- `0x180054104`
- `0x1800541b0`
- `0x180054bd8`
- `0x180054d9c`
- `0x1800577e4`
- `0x180057964`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180057a03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180057a03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800579ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800579ae`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180057a22`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180057a22`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057ae8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180057ae8`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800579df`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800579df`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180057aad`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180057aad`

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
0x180057964  mov     [rsp+arg_0], rbx
0x180057969  push    rsi
0x18005796a  push    rdi
0x18005796b  push    r14
0x18005796d  sub     rsp, 480h
0x180057974  mov     rax, cs:__security_cookie
0x18005797b  xor     rax, rsp
0x18005797e  mov     [rsp+498h+var_28], rax
0x180057986  mov     r14, r9
0x180057989  mov     rdi, r8
0x18005798c  mov     rax, rdx
0x18005798f  xor     ebx, ebx
0x180057991  mov     [rsp+498h+var_450], rbx
0x180057996  mov     [rsp+498h+var_440], rcx
0x18005799b  mov     [rsp+498h+var_448], rbx
0x1800579a0  mov     [rsp+498h+var_438], rbx
0x1800579a5  xor     edx, edx; hFile
0x1800579a7  lea     r8d, [rbx+2]; dwFlags
0x1800579ab  mov     rcx, rax; lpLibFileName
0x1800579ae  call    cs:__imp_LoadLibraryExW
0x1800579b5  nop     dword ptr [rax+rax+00h]
0x1800579ba  mov     rsi, rax
0x1800579bd  mov     [rsp+498h+var_460], rax
0x1800579c2  test    rax, rax
0x1800579c5  jnz     short loc_1800579D3
0x1800579c7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800579cc  mov     ebx, eax
0x1800579ce  jmp     loc_180057AF5
0x1800579d3  xor     r9d, r9d; wLanguage
0x1800579d6  mov     r8, rdi; lpName
0x1800579d9  mov     rdx, r14; lpType
0x1800579dc  mov     rcx, rsi; hModule
0x1800579df  call    cs:__imp_FindResourceExW
0x1800579e6  nop     dword ptr [rax+rax+00h]
0x1800579eb  mov     rdi, rax
0x1800579ee  test    rax, rax
0x1800579f1  jnz     short loc_1800579FD
0x1800579f3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800579f8  jmp     loc_180057AE3
0x1800579fd  mov     rdx, rdi; hResInfo
0x180057a00  mov     rcx, rsi; hModule
0x180057a03  call    cs:__imp_LoadResource
0x180057a0a  nop     dword ptr [rax+rax+00h]
0x180057a0f  mov     r14, rax
0x180057a12  mov     [rsp+498h+var_458], rax
0x180057a17  test    rax, rax
0x180057a1a  jz      short loc_1800579F3
0x180057a1c  mov     rdx, rdi; hResInfo
0x180057a1f  mov     rcx, rsi; hModule
0x180057a22  call    cs:__imp_SizeofResource
0x180057a29  nop     dword ptr [rax+rax+00h]
0x180057a2e  mov     edi, eax
0x180057a30  mov     [rsp+498h+var_468], eax
0x180057a34  inc     eax
0x180057a36  cmp     eax, edi
0x180057a38  jnb     short loc_180057A44
0x180057a3a  mov     ebx, 8007000Eh
0x180057a3f  jmp     loc_180057AF5
0x180057a44  mov     ecx, eax
0x180057a46  mov     edx, 2
0x180057a4b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180057a50  cmp     rax, 400h
0x180057a56  jbe     short loc_180057A6C
0x180057a58  mov     rdx, rax
0x180057a5b  lea     rcx, [rsp+498h+var_438]
0x180057a60  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180057a65  mov     rax, [rsp+498h+var_438]
0x180057a6a  jmp     short loc_180057A76
0x180057a6c  lea     rax, [rsp+498h+var_430]
0x180057a71  mov     [rsp+498h+var_438], rax
0x180057a76  jmp     short loc_180057A8D
0x180057a78  xor     ebx, ebx
0x180057a7a  mov     rsi, [rsp+498h+var_460]
0x180057a7f  mov     r14, [rsp+498h+var_458]
0x180057a84  mov     edi, [rsp+498h+var_468]
0x180057a88  mov     rax, [rsp+498h+var_438]
0x180057a8d  test    rax, rax
0x180057a90  jnz     short loc_180057A99
0x180057a92  mov     ebx, 8007000Eh
0x180057a97  jmp     short loc_180057AE5
0x180057a99  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180057a9d  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180057aa2  mov     r9d, edi; cbMultiByte
0x180057aa5  mov     r8, r14; lpMultiByteStr
0x180057aa8  xor     edx, edx; dwFlags
0x180057aaa  lea     ecx, [rdx+3]; CodePage
0x180057aad  call    cs:__imp_MultiByteToWideChar
0x180057ab4  nop     dword ptr [rax+rax+00h]
0x180057ab9  test    eax, eax
0x180057abb  jz      loc_1800579F3
0x180057ac1  mov     ecx, eax
0x180057ac3  mov     rax, [rsp+498h+var_438]
0x180057ac8  mov     [rax+rcx*2], bx
0x180057acc  mov     r8d, [rsp+498h+arg_20]; int
0x180057ad4  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180057ad9  lea     rcx, [rsp+498h+var_448]; this
0x180057ade  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180057ae3  mov     ebx, eax
0x180057ae5  mov     rcx, rsi; hLibModule
0x180057ae8  call    cs:__imp_FreeLibrary
0x180057aef  nop     dword ptr [rax+rax+00h]
0x180057af4  nop
0x180057af5  lea     rcx, [rsp+498h+var_438]
0x180057afa  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180057aff  nop
0x180057b00  lea     rcx, [rsp+498h+var_450]
0x180057b05  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180057b0a  mov     eax, ebx
0x180057b0c  mov     rcx, [rsp+498h+var_28]
0x180057b14  xor     rcx, rsp; StackCookie
0x180057b17  call    __security_check_cookie
0x180057b1c  mov     rbx, [rsp+498h+arg_0]
0x180057b24  add     rsp, 480h
0x180057b2b  pop     r14
0x180057b2d  pop     rdi
0x180057b2e  pop     rsi
0x180057b2f  retn
```
