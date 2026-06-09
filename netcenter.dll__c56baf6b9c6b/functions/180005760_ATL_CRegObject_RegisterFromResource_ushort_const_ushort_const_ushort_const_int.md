# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180005760`
- end: `0x180005908`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000617c`
- `0x1800063fc`

## callees

- `0x180002270`
- `0x180003eb0`
- `0x180003ee8`
- `0x180003f3c`
- `0x1800049a4`
- `0x180004aec`
- `0x1800055ec`
- `0x180005760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000580c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000580c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800057d5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800057d5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800057f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800057f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800058c6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800058c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800057aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800057aa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005891`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005891`

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
0x180005760  mov     [rsp+arg_0], rbx
0x180005765  push    rsi
0x180005766  push    rdi
0x180005767  push    r14
0x180005769  sub     rsp, 480h
0x180005770  mov     rax, cs:__security_cookie
0x180005777  xor     rax, rsp
0x18000577a  mov     [rsp+498h+var_28], rax
0x180005782  mov     r14, r9
0x180005785  mov     rdi, r8
0x180005788  mov     rax, rdx
0x18000578b  xor     ebx, ebx
0x18000578d  mov     [rsp+498h+var_450], rbx
0x180005792  mov     [rsp+498h+var_440], rcx
0x180005797  mov     [rsp+498h+var_448], rbx
0x18000579c  mov     [rsp+498h+var_438], rbx
0x1800057a1  xor     edx, edx; hFile
0x1800057a3  lea     r8d, [rbx+2]; dwFlags
0x1800057a7  mov     rcx, rax; lpLibFileName
0x1800057aa  call    cs:__imp_LoadLibraryExW
0x1800057b0  mov     rsi, rax
0x1800057b3  mov     [rsp+498h+var_460], rax
0x1800057b8  test    rax, rax
0x1800057bb  jnz     short loc_1800057C9
0x1800057bd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800057c2  mov     ebx, eax
0x1800057c4  jmp     loc_1800058CD
0x1800057c9  xor     r9d, r9d; wLanguage
0x1800057cc  mov     r8, rdi; lpName
0x1800057cf  mov     rdx, r14; lpType
0x1800057d2  mov     rcx, rsi; hModule
0x1800057d5  call    cs:__imp_FindResourceExW
0x1800057db  mov     rdi, rax
0x1800057de  test    rax, rax
0x1800057e1  jnz     short loc_1800057ED
0x1800057e3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800057e8  jmp     loc_1800058C1
0x1800057ed  mov     rdx, rdi; hResInfo
0x1800057f0  mov     rcx, rsi; hModule
0x1800057f3  call    cs:__imp_LoadResource
0x1800057f9  mov     r14, rax
0x1800057fc  mov     [rsp+498h+var_458], rax
0x180005801  test    rax, rax
0x180005804  jz      short loc_1800057E3
0x180005806  mov     rdx, rdi; hResInfo
0x180005809  mov     rcx, rsi; hModule
0x18000580c  call    cs:__imp_SizeofResource
0x180005812  mov     edi, eax
0x180005814  mov     [rsp+498h+var_468], eax
0x180005818  inc     eax
0x18000581a  cmp     eax, edi
0x18000581c  jnb     short loc_180005828
0x18000581e  mov     ebx, 8007000Eh
0x180005823  jmp     loc_1800058CD
0x180005828  mov     ecx, eax
0x18000582a  mov     edx, 2
0x18000582f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180005834  cmp     rax, 400h
0x18000583a  jbe     short loc_180005850
0x18000583c  mov     rdx, rax
0x18000583f  lea     rcx, [rsp+498h+var_438]
0x180005844  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005849  mov     rax, [rsp+498h+var_438]
0x18000584e  jmp     short loc_18000585A
0x180005850  lea     rax, [rsp+498h+var_430]
0x180005855  mov     [rsp+498h+var_438], rax
0x18000585a  jmp     short loc_180005871
0x18000585c  xor     ebx, ebx
0x18000585e  mov     rsi, [rsp+498h+var_460]
0x180005863  mov     r14, [rsp+498h+var_458]
0x180005868  mov     edi, [rsp+498h+var_468]
0x18000586c  mov     rax, [rsp+498h+var_438]
0x180005871  test    rax, rax
0x180005874  jnz     short loc_18000587D
0x180005876  mov     ebx, 8007000Eh
0x18000587b  jmp     short loc_1800058C3
0x18000587d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180005881  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180005886  mov     r9d, edi; cbMultiByte
0x180005889  mov     r8, r14; lpMultiByteStr
0x18000588c  xor     edx, edx; dwFlags
0x18000588e  lea     ecx, [rdx+3]; CodePage
0x180005891  call    cs:__imp_MultiByteToWideChar
0x180005897  test    eax, eax
0x180005899  jz      loc_1800057E3
0x18000589f  mov     ecx, eax
0x1800058a1  mov     rax, [rsp+498h+var_438]
0x1800058a6  mov     [rax+rcx*2], bx
0x1800058aa  mov     r8d, [rsp+498h+arg_20]; int
0x1800058b2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800058b7  lea     rcx, [rsp+498h+var_448]; this
0x1800058bc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800058c1  mov     ebx, eax
0x1800058c3  mov     rcx, rsi; hLibModule
0x1800058c6  call    cs:__imp_FreeLibrary
0x1800058cc  nop
0x1800058cd  lea     rcx, [rsp+498h+var_438]
0x1800058d2  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800058d7  nop
0x1800058d8  lea     rcx, [rsp+498h+var_450]
0x1800058dd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800058e2  mov     eax, ebx
0x1800058e4  mov     rcx, [rsp+498h+var_28]
0x1800058ec  xor     rcx, rsp; StackCookie
0x1800058ef  call    __security_check_cookie
0x1800058f4  mov     rbx, [rsp+498h+arg_0]
0x1800058fc  add     rsp, 480h
0x180005903  pop     r14
0x180005905  pop     rdi
0x180005906  pop     rsi
0x180005907  retn
```
