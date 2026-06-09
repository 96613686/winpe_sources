# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180032040`
- end: `0x1800321e8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800334dc`
- `0x180033754`

## callees

- `0x18002b530`
- `0x18002d39c`
- `0x18002e130`
- `0x18002e280`
- `0x18002f344`
- `0x18002f62c`
- `0x180031ecc`
- `0x180032040`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003208a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003208a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800321a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800321a6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800320b5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800320b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800320d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800320d3`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800320ec`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800320ec`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032171`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180032171`

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
0x180032040  mov     [rsp+arg_0], rbx
0x180032045  push    rsi
0x180032046  push    rdi
0x180032047  push    r14
0x180032049  sub     rsp, 480h
0x180032050  mov     rax, cs:__security_cookie
0x180032057  xor     rax, rsp
0x18003205a  mov     [rsp+498h+var_28], rax
0x180032062  mov     r14, r9
0x180032065  mov     rdi, r8
0x180032068  mov     rax, rdx
0x18003206b  xor     ebx, ebx
0x18003206d  mov     [rsp+498h+var_450], rbx
0x180032072  mov     [rsp+498h+var_440], rcx
0x180032077  mov     [rsp+498h+var_448], rbx
0x18003207c  mov     [rsp+498h+var_438], rbx
0x180032081  xor     edx, edx; hFile
0x180032083  lea     r8d, [rbx+2]; dwFlags
0x180032087  mov     rcx, rax; lpLibFileName
0x18003208a  call    cs:__imp_LoadLibraryExW
0x180032090  mov     rsi, rax
0x180032093  mov     [rsp+498h+var_460], rax
0x180032098  test    rax, rax
0x18003209b  jnz     short loc_1800320A9
0x18003209d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800320a2  mov     ebx, eax
0x1800320a4  jmp     loc_1800321AD
0x1800320a9  xor     r9d, r9d; wLanguage
0x1800320ac  mov     r8, rdi; lpName
0x1800320af  mov     rdx, r14; lpType
0x1800320b2  mov     rcx, rsi; hModule
0x1800320b5  call    cs:__imp_FindResourceExW
0x1800320bb  mov     rdi, rax
0x1800320be  test    rax, rax
0x1800320c1  jnz     short loc_1800320CD
0x1800320c3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800320c8  jmp     loc_1800321A1
0x1800320cd  mov     rdx, rdi; hResInfo
0x1800320d0  mov     rcx, rsi; hModule
0x1800320d3  call    cs:__imp_LoadResource
0x1800320d9  mov     r14, rax
0x1800320dc  mov     [rsp+498h+var_458], rax
0x1800320e1  test    rax, rax
0x1800320e4  jz      short loc_1800320C3
0x1800320e6  mov     rdx, rdi; hResInfo
0x1800320e9  mov     rcx, rsi; hModule
0x1800320ec  call    cs:__imp_SizeofResource
0x1800320f2  mov     edi, eax
0x1800320f4  mov     [rsp+498h+var_468], eax
0x1800320f8  inc     eax
0x1800320fa  cmp     eax, edi
0x1800320fc  jnb     short loc_180032108
0x1800320fe  mov     ebx, 8007000Eh
0x180032103  jmp     loc_1800321AD
0x180032108  mov     ecx, eax
0x18003210a  mov     edx, 2
0x18003210f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180032114  cmp     rax, 400h
0x18003211a  jbe     short loc_180032130
0x18003211c  mov     rdx, rax
0x18003211f  lea     rcx, [rsp+498h+var_438]
0x180032124  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180032129  mov     rax, [rsp+498h+var_438]
0x18003212e  jmp     short loc_18003213A
0x180032130  lea     rax, [rsp+498h+var_430]
0x180032135  mov     [rsp+498h+var_438], rax
0x18003213a  jmp     short loc_180032151
0x18003213c  xor     ebx, ebx
0x18003213e  mov     rsi, [rsp+498h+var_460]
0x180032143  mov     r14, [rsp+498h+var_458]
0x180032148  mov     edi, [rsp+498h+var_468]
0x18003214c  mov     rax, [rsp+498h+var_438]
0x180032151  test    rax, rax
0x180032154  jnz     short loc_18003215D
0x180032156  mov     ebx, 8007000Eh
0x18003215b  jmp     short loc_1800321A3
0x18003215d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180032161  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180032166  mov     r9d, edi; cbMultiByte
0x180032169  mov     r8, r14; lpMultiByteStr
0x18003216c  xor     edx, edx; dwFlags
0x18003216e  lea     ecx, [rdx+3]; CodePage
0x180032171  call    cs:__imp_MultiByteToWideChar
0x180032177  test    eax, eax
0x180032179  jz      loc_1800320C3
0x18003217f  mov     ecx, eax
0x180032181  mov     rax, [rsp+498h+var_438]
0x180032186  mov     [rax+rcx*2], bx
0x18003218a  mov     r8d, [rsp+498h+arg_20]; int
0x180032192  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180032197  lea     rcx, [rsp+498h+var_448]; this
0x18003219c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800321a1  mov     ebx, eax
0x1800321a3  mov     rcx, rsi; hLibModule
0x1800321a6  call    cs:__imp_FreeLibrary
0x1800321ac  nop
0x1800321ad  lea     rcx, [rsp+498h+var_438]
0x1800321b2  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800321b7  nop
0x1800321b8  lea     rcx, [rsp+498h+var_450]
0x1800321bd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800321c2  mov     eax, ebx
0x1800321c4  mov     rcx, [rsp+498h+var_28]
0x1800321cc  xor     rcx, rsp; StackCookie
0x1800321cf  call    __security_check_cookie
0x1800321d4  mov     rbx, [rsp+498h+arg_0]
0x1800321dc  add     rsp, 480h
0x1800321e3  pop     r14
0x1800321e5  pop     rdi
0x1800321e6  pop     rsi
0x1800321e7  retn
```
