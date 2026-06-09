# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800162bc`
- end: `0x180016464`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001730c`
- `0x180017584`

## callees

- `0x180013124`
- `0x180013378`
- `0x180013450`
- `0x180013d98`
- `0x18001405c`
- `0x18001614c`
- `0x1800162bc`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180016368`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180016368`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180016331`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180016331`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016306`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016306`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016422`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016422`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001634f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001634f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800163ed`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800163ed`

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
0x1800162bc  mov     [rsp+arg_0], rbx
0x1800162c1  push    rsi
0x1800162c2  push    rdi
0x1800162c3  push    r14
0x1800162c5  sub     rsp, 480h
0x1800162cc  mov     rax, cs:__security_cookie
0x1800162d3  xor     rax, rsp
0x1800162d6  mov     [rsp+498h+var_28], rax
0x1800162de  mov     r14, r9
0x1800162e1  mov     rdi, r8
0x1800162e4  mov     rax, rdx
0x1800162e7  xor     ebx, ebx
0x1800162e9  mov     [rsp+498h+var_450], rbx
0x1800162ee  mov     [rsp+498h+var_440], rcx
0x1800162f3  mov     [rsp+498h+var_448], rbx
0x1800162f8  mov     [rsp+498h+var_438], rbx
0x1800162fd  xor     edx, edx; hFile
0x1800162ff  lea     r8d, [rbx+2]; dwFlags
0x180016303  mov     rcx, rax; lpLibFileName
0x180016306  call    cs:__imp_LoadLibraryExW
0x18001630c  mov     rsi, rax
0x18001630f  mov     [rsp+498h+var_460], rax
0x180016314  test    rax, rax
0x180016317  jnz     short loc_180016325
0x180016319  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001631e  mov     ebx, eax
0x180016320  jmp     loc_180016429
0x180016325  xor     r9d, r9d; wLanguage
0x180016328  mov     r8, rdi; lpName
0x18001632b  mov     rdx, r14; lpType
0x18001632e  mov     rcx, rsi; hModule
0x180016331  call    cs:__imp_FindResourceExW
0x180016337  mov     rdi, rax
0x18001633a  test    rax, rax
0x18001633d  jnz     short loc_180016349
0x18001633f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180016344  jmp     loc_18001641D
0x180016349  mov     rdx, rdi; hResInfo
0x18001634c  mov     rcx, rsi; hModule
0x18001634f  call    cs:__imp_LoadResource
0x180016355  mov     r14, rax
0x180016358  mov     [rsp+498h+var_458], rax
0x18001635d  test    rax, rax
0x180016360  jz      short loc_18001633F
0x180016362  mov     rdx, rdi; hResInfo
0x180016365  mov     rcx, rsi; hModule
0x180016368  call    cs:__imp_SizeofResource
0x18001636e  mov     edi, eax
0x180016370  mov     [rsp+498h+var_468], eax
0x180016374  inc     eax
0x180016376  cmp     eax, edi
0x180016378  jnb     short loc_180016384
0x18001637a  mov     ebx, 8007000Eh
0x18001637f  jmp     loc_180016429
0x180016384  mov     ecx, eax
0x180016386  mov     edx, 2
0x18001638b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180016390  cmp     rax, 400h
0x180016396  jbe     short loc_1800163AC
0x180016398  mov     rdx, rax
0x18001639b  lea     rcx, [rsp+498h+var_438]
0x1800163a0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800163a5  mov     rax, [rsp+498h+var_438]
0x1800163aa  jmp     short loc_1800163B6
0x1800163ac  lea     rax, [rsp+498h+var_430]
0x1800163b1  mov     [rsp+498h+var_438], rax
0x1800163b6  jmp     short loc_1800163CD
0x1800163b8  xor     ebx, ebx
0x1800163ba  mov     rsi, [rsp+498h+var_460]
0x1800163bf  mov     r14, [rsp+498h+var_458]
0x1800163c4  mov     edi, [rsp+498h+var_468]
0x1800163c8  mov     rax, [rsp+498h+var_438]
0x1800163cd  test    rax, rax
0x1800163d0  jnz     short loc_1800163D9
0x1800163d2  mov     ebx, 8007000Eh
0x1800163d7  jmp     short loc_18001641F
0x1800163d9  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1800163dd  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1800163e2  mov     r9d, edi; cbMultiByte
0x1800163e5  mov     r8, r14; lpMultiByteStr
0x1800163e8  xor     edx, edx; dwFlags
0x1800163ea  lea     ecx, [rdx+3]; CodePage
0x1800163ed  call    cs:__imp_MultiByteToWideChar
0x1800163f3  test    eax, eax
0x1800163f5  jz      loc_18001633F
0x1800163fb  mov     ecx, eax
0x1800163fd  mov     rax, [rsp+498h+var_438]
0x180016402  mov     [rax+rcx*2], bx
0x180016406  mov     r8d, [rsp+498h+arg_20]; int
0x18001640e  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180016413  lea     rcx, [rsp+498h+var_448]; this
0x180016418  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18001641d  mov     ebx, eax
0x18001641f  mov     rcx, rsi; hLibModule
0x180016422  call    cs:__imp_FreeLibrary
0x180016428  nop
0x180016429  lea     rcx, [rsp+498h+var_438]
0x18001642e  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180016433  nop
0x180016434  lea     rcx, [rsp+498h+var_450]
0x180016439  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001643e  mov     eax, ebx
0x180016440  mov     rcx, [rsp+498h+var_28]
0x180016448  xor     rcx, rsp; StackCookie
0x18001644b  call    __security_check_cookie
0x180016450  mov     rbx, [rsp+498h+arg_0]
0x180016458  add     rsp, 480h
0x18001645f  pop     r14
0x180016461  pop     rdi
0x180016462  pop     rsi
0x180016463  retn
```
