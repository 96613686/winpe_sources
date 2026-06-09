# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180008c20`
- end: `0x180008dc8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800099bc`
- `0x180009c34`

## callees

- `0x180006580`
- `0x180006688`
- `0x18000680c`
- `0x180007384`
- `0x1800075e0`
- `0x180008aac`
- `0x180008c20`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008d86`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008d86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008cb3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008cb3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008c6a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008c6a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180008c95`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180008c95`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180008ccc`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180008ccc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008d51`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008d51`

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
0x180008c20  mov     [rsp+arg_0], rbx
0x180008c25  push    rsi
0x180008c26  push    rdi
0x180008c27  push    r14
0x180008c29  sub     rsp, 480h
0x180008c30  mov     rax, cs:__security_cookie
0x180008c37  xor     rax, rsp
0x180008c3a  mov     [rsp+498h+var_28], rax
0x180008c42  mov     r14, r9
0x180008c45  mov     rdi, r8
0x180008c48  mov     rax, rdx
0x180008c4b  xor     ebx, ebx
0x180008c4d  mov     [rsp+498h+var_450], rbx
0x180008c52  mov     [rsp+498h+var_440], rcx
0x180008c57  mov     [rsp+498h+var_448], rbx
0x180008c5c  mov     [rsp+498h+var_438], rbx
0x180008c61  xor     edx, edx; hFile
0x180008c63  lea     r8d, [rbx+2]; dwFlags
0x180008c67  mov     rcx, rax; lpLibFileName
0x180008c6a  call    cs:__imp_LoadLibraryExW
0x180008c70  mov     rsi, rax
0x180008c73  mov     [rsp+498h+var_460], rax
0x180008c78  test    rax, rax
0x180008c7b  jnz     short loc_180008C89
0x180008c7d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008c82  mov     ebx, eax
0x180008c84  jmp     loc_180008D8D
0x180008c89  xor     r9d, r9d; wLanguage
0x180008c8c  mov     r8, rdi; lpName
0x180008c8f  mov     rdx, r14; lpType
0x180008c92  mov     rcx, rsi; hModule
0x180008c95  call    cs:__imp_FindResourceExW
0x180008c9b  mov     rdi, rax
0x180008c9e  test    rax, rax
0x180008ca1  jnz     short loc_180008CAD
0x180008ca3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008ca8  jmp     loc_180008D81
0x180008cad  mov     rdx, rdi; hResInfo
0x180008cb0  mov     rcx, rsi; hModule
0x180008cb3  call    cs:__imp_LoadResource
0x180008cb9  mov     r14, rax
0x180008cbc  mov     [rsp+498h+var_458], rax
0x180008cc1  test    rax, rax
0x180008cc4  jz      short loc_180008CA3
0x180008cc6  mov     rdx, rdi; hResInfo
0x180008cc9  mov     rcx, rsi; hModule
0x180008ccc  call    cs:__imp_SizeofResource
0x180008cd2  mov     edi, eax
0x180008cd4  mov     [rsp+498h+var_468], eax
0x180008cd8  inc     eax
0x180008cda  cmp     eax, edi
0x180008cdc  jnb     short loc_180008CE8
0x180008cde  mov     ebx, 8007000Eh
0x180008ce3  jmp     loc_180008D8D
0x180008ce8  mov     ecx, eax
0x180008cea  mov     edx, 2
0x180008cef  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180008cf4  cmp     rax, 400h
0x180008cfa  jbe     short loc_180008D10
0x180008cfc  mov     rdx, rax
0x180008cff  lea     rcx, [rsp+498h+var_438]
0x180008d04  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180008d09  mov     rax, [rsp+498h+var_438]
0x180008d0e  jmp     short loc_180008D1A
0x180008d10  lea     rax, [rsp+498h+var_430]
0x180008d15  mov     [rsp+498h+var_438], rax
0x180008d1a  jmp     short loc_180008D31
0x180008d1c  xor     ebx, ebx
0x180008d1e  mov     rsi, [rsp+498h+var_460]
0x180008d23  mov     r14, [rsp+498h+var_458]
0x180008d28  mov     edi, [rsp+498h+var_468]
0x180008d2c  mov     rax, [rsp+498h+var_438]
0x180008d31  test    rax, rax
0x180008d34  jnz     short loc_180008D3D
0x180008d36  mov     ebx, 8007000Eh
0x180008d3b  jmp     short loc_180008D83
0x180008d3d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180008d41  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180008d46  mov     r9d, edi; cbMultiByte
0x180008d49  mov     r8, r14; lpMultiByteStr
0x180008d4c  xor     edx, edx; dwFlags
0x180008d4e  lea     ecx, [rdx+3]; CodePage
0x180008d51  call    cs:__imp_MultiByteToWideChar
0x180008d57  test    eax, eax
0x180008d59  jz      loc_180008CA3
0x180008d5f  mov     ecx, eax
0x180008d61  mov     rax, [rsp+498h+var_438]
0x180008d66  mov     [rax+rcx*2], bx
0x180008d6a  mov     r8d, [rsp+498h+arg_20]; int
0x180008d72  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180008d77  lea     rcx, [rsp+498h+var_448]; this
0x180008d7c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180008d81  mov     ebx, eax
0x180008d83  mov     rcx, rsi; hLibModule
0x180008d86  call    cs:__imp_FreeLibrary
0x180008d8c  nop
0x180008d8d  lea     rcx, [rsp+498h+var_438]
0x180008d92  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180008d97  nop
0x180008d98  lea     rcx, [rsp+498h+var_450]
0x180008d9d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008da2  mov     eax, ebx
0x180008da4  mov     rcx, [rsp+498h+var_28]
0x180008dac  xor     rcx, rsp; StackCookie
0x180008daf  call    __security_check_cookie
0x180008db4  mov     rbx, [rsp+498h+arg_0]
0x180008dbc  add     rsp, 480h
0x180008dc3  pop     r14
0x180008dc5  pop     rdi
0x180008dc6  pop     rsi
0x180008dc7  retn
```
