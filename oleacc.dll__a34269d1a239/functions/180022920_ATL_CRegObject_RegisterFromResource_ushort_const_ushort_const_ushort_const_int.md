# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180022920`
- end: `0x180022ac8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800232fc`
- `0x180023544`

## callees

- `0x18001e4c0`
- `0x180020670`
- `0x1800206d0`
- `0x18002078c`
- `0x1800211b8`
- `0x180021378`
- `0x1800227ac`
- `0x180022920`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002296a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002296a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800229cc`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800229cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800229b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800229b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022a86`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022a86`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180022995`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180022995`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180022a51`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180022a51`

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
0x180022920  mov     [rsp+arg_0], rbx
0x180022925  push    rsi
0x180022926  push    rdi
0x180022927  push    r14
0x180022929  sub     rsp, 480h
0x180022930  mov     rax, cs:__security_cookie
0x180022937  xor     rax, rsp
0x18002293a  mov     [rsp+498h+var_28], rax
0x180022942  mov     r14, r9
0x180022945  mov     rdi, r8
0x180022948  mov     rax, rdx
0x18002294b  xor     ebx, ebx
0x18002294d  mov     [rsp+498h+var_450], rbx
0x180022952  mov     [rsp+498h+var_440], rcx
0x180022957  mov     [rsp+498h+var_448], rbx
0x18002295c  mov     [rsp+498h+var_438], rbx
0x180022961  xor     edx, edx; hFile
0x180022963  lea     r8d, [rbx+2]; dwFlags
0x180022967  mov     rcx, rax; lpLibFileName
0x18002296a  call    cs:__imp_LoadLibraryExW
0x180022970  mov     rsi, rax
0x180022973  mov     [rsp+498h+var_460], rax
0x180022978  test    rax, rax
0x18002297b  jnz     short loc_180022989
0x18002297d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180022982  mov     ebx, eax
0x180022984  jmp     loc_180022A8D
0x180022989  xor     r9d, r9d; wLanguage
0x18002298c  mov     r8, rdi; lpName
0x18002298f  mov     rdx, r14; lpType
0x180022992  mov     rcx, rsi; hModule
0x180022995  call    cs:__imp_FindResourceExW
0x18002299b  mov     rdi, rax
0x18002299e  test    rax, rax
0x1800229a1  jnz     short loc_1800229AD
0x1800229a3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800229a8  jmp     loc_180022A81
0x1800229ad  mov     rdx, rdi; hResInfo
0x1800229b0  mov     rcx, rsi; hModule
0x1800229b3  call    cs:__imp_LoadResource
0x1800229b9  mov     r14, rax
0x1800229bc  mov     [rsp+498h+var_458], rax
0x1800229c1  test    rax, rax
0x1800229c4  jz      short loc_1800229A3
0x1800229c6  mov     rdx, rdi; hResInfo
0x1800229c9  mov     rcx, rsi; hModule
0x1800229cc  call    cs:__imp_SizeofResource
0x1800229d2  mov     edi, eax
0x1800229d4  mov     [rsp+498h+var_468], eax
0x1800229d8  inc     eax
0x1800229da  cmp     eax, edi
0x1800229dc  jnb     short loc_1800229E8
0x1800229de  mov     ebx, 8007000Eh
0x1800229e3  jmp     loc_180022A8D
0x1800229e8  mov     ecx, eax
0x1800229ea  mov     edx, 2
0x1800229ef  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800229f4  cmp     rax, 400h
0x1800229fa  jbe     short loc_180022A10
0x1800229fc  mov     rdx, rax
0x1800229ff  lea     rcx, [rsp+498h+var_438]
0x180022a04  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180022a09  mov     rax, [rsp+498h+var_438]
0x180022a0e  jmp     short loc_180022A1A
0x180022a10  lea     rax, [rsp+498h+var_430]
0x180022a15  mov     [rsp+498h+var_438], rax
0x180022a1a  jmp     short loc_180022A31
0x180022a1c  xor     ebx, ebx
0x180022a1e  mov     rsi, [rsp+498h+var_460]
0x180022a23  mov     r14, [rsp+498h+var_458]
0x180022a28  mov     edi, [rsp+498h+var_468]
0x180022a2c  mov     rax, [rsp+498h+var_438]
0x180022a31  test    rax, rax
0x180022a34  jnz     short loc_180022A3D
0x180022a36  mov     ebx, 8007000Eh
0x180022a3b  jmp     short loc_180022A83
0x180022a3d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180022a41  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180022a46  mov     r9d, edi; cbMultiByte
0x180022a49  mov     r8, r14; lpMultiByteStr
0x180022a4c  xor     edx, edx; dwFlags
0x180022a4e  lea     ecx, [rdx+3]; CodePage
0x180022a51  call    cs:__imp_MultiByteToWideChar
0x180022a57  test    eax, eax
0x180022a59  jz      loc_1800229A3
0x180022a5f  mov     ecx, eax
0x180022a61  mov     rax, [rsp+498h+var_438]
0x180022a66  mov     [rax+rcx*2], bx
0x180022a6a  mov     r8d, [rsp+498h+arg_20]; int
0x180022a72  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180022a77  lea     rcx, [rsp+498h+var_448]; this
0x180022a7c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180022a81  mov     ebx, eax
0x180022a83  mov     rcx, rsi; hLibModule
0x180022a86  call    cs:__imp_FreeLibrary
0x180022a8c  nop
0x180022a8d  lea     rcx, [rsp+498h+var_438]
0x180022a92  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180022a97  nop
0x180022a98  lea     rcx, [rsp+498h+var_450]
0x180022a9d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180022aa2  mov     eax, ebx
0x180022aa4  mov     rcx, [rsp+498h+var_28]
0x180022aac  xor     rcx, rsp; StackCookie
0x180022aaf  call    __security_check_cookie
0x180022ab4  mov     rbx, [rsp+498h+arg_0]
0x180022abc  add     rsp, 480h
0x180022ac3  pop     r14
0x180022ac5  pop     rdi
0x180022ac6  pop     rsi
0x180022ac7  retn
```
