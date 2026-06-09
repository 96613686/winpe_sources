# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800118e8`
- end: `0x180011ac2`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180012e20`

## callees

- `0x1800024e0`
- `0x18000e2cc`
- `0x18000e3bc`
- `0x18000ec4c`
- `0x18000fcc0`
- `0x180011758`
- `0x1800118e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001195b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001195b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011a72`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011a72`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180011992`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180011992`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001192f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001192f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180011979`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180011979`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011a3d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011a3d`

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
  HMODULE v7; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rsi
  unsigned int v11; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  DWORD v14; // eax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  _QWORD v19[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19[2] = 0;
  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  v18 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
  v10 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v12 = (const CHAR *)LoadResource(v7, Resource);
  if ( !v12 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v7, v10);
  v14 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v14 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v21;
        v20 = (LPWSTR)v21;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2LL * v14);
        lpWideCharStr = v20;
      }
    }
    catch ( ... )
    {
      v7 = v18;
      lpWideCharStr = v20;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v7);
      goto LABEL_21;
    }
    v17 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v20[v17] = 0;
      v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800118e8  mov     [rsp+arg_0], rbx
0x1800118ed  push    rsi
0x1800118ee  push    rdi
0x1800118ef  push    r14
0x1800118f1  sub     rsp, 480h
0x1800118f8  mov     rax, cs:__security_cookie
0x1800118ff  xor     rax, rsp
0x180011902  mov     [rsp+498h+var_28], rax
0x18001190a  mov     rsi, r9
0x18001190d  mov     rax, rdx
0x180011910  xor     ebx, ebx
0x180011912  mov     [rsp+498h+var_440], rbx
0x180011917  mov     [rsp+498h+var_448], rcx
0x18001191c  mov     [rsp+498h+var_450], rbx
0x180011921  mov     [rsp+498h+var_438], rbx
0x180011926  xor     edx, edx; hFile
0x180011928  lea     r8d, [rbx+2]; dwFlags
0x18001192c  mov     rcx, rax; lpLibFileName
0x18001192f  call    cs:__imp_LoadLibraryExW
0x180011935  mov     rdi, rax
0x180011938  mov     [rsp+498h+var_460], rax
0x18001193d  test    rax, rax
0x180011940  jnz     short loc_18001194E
0x180011942  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011947  mov     ebx, eax
0x180011949  jmp     loc_180011A79
0x18001194e  xor     r9d, r9d; wLanguage
0x180011951  lea     r8d, [r9+65h]; lpName
0x180011955  mov     rdx, rsi; lpType
0x180011958  mov     rcx, rdi; hModule
0x18001195b  call    cs:__imp_FindResourceExW
0x180011961  mov     rsi, rax
0x180011964  test    rax, rax
0x180011967  jnz     short loc_180011973
0x180011969  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001196e  jmp     loc_180011A6D
0x180011973  mov     rdx, rsi; hResInfo
0x180011976  mov     rcx, rdi; hModule
0x180011979  call    cs:__imp_LoadResource
0x18001197f  mov     r14, rax
0x180011982  mov     [rsp+498h+var_458], rax
0x180011987  test    rax, rax
0x18001198a  jz      short loc_180011969
0x18001198c  mov     rdx, rsi; hResInfo
0x18001198f  mov     rcx, rdi; hModule
0x180011992  call    cs:__imp_SizeofResource
0x180011998  mov     esi, eax
0x18001199a  mov     [rsp+498h+var_468], eax
0x18001199e  inc     eax
0x1800119a0  cmp     eax, esi
0x1800119a2  jnb     short loc_1800119C5
0x1800119a4  lea     rax, [rsp+498h+var_430]
0x1800119a9  cmp     [rsp+498h+var_438], rax
0x1800119ae  jz      short loc_1800119BB
0x1800119b0  lea     rcx, [rsp+498h+var_438]
0x1800119b5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800119ba  nop
0x1800119bb  mov     eax, 8007000Eh
0x1800119c0  jmp     loc_180011A92
0x1800119c5  test    eax, eax
0x1800119c7  jz      short loc_1800119FC
0x1800119c9  mov     ecx, eax
0x1800119cb  xor     edx, edx
0x1800119cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800119d1  div     rcx
0x1800119d4  cmp     rax, 2
0x1800119d8  jb      loc_180011AB6
0x1800119de  lea     rdx, [rcx+rcx]
0x1800119e2  cmp     rdx, 400h
0x1800119e9  jbe     short loc_1800119FC
0x1800119eb  lea     rcx, [rsp+498h+var_438]
0x1800119f0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800119f5  mov     rax, [rsp+498h+var_438]
0x1800119fa  jmp     short loc_180011A06
0x1800119fc  lea     rax, [rsp+498h+var_430]
0x180011a01  mov     [rsp+498h+var_438], rax
0x180011a06  jmp     short loc_180011A1D
0x180011a08  xor     ebx, ebx
0x180011a0a  mov     rdi, [rsp+498h+var_460]
0x180011a0f  mov     r14, [rsp+498h+var_458]
0x180011a14  mov     esi, [rsp+498h+var_468]
0x180011a18  mov     rax, [rsp+498h+var_438]
0x180011a1d  test    rax, rax
0x180011a20  jnz     short loc_180011A29
0x180011a22  mov     ebx, 8007000Eh
0x180011a27  jmp     short loc_180011A6F
0x180011a29  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180011a2d  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180011a32  mov     r9d, esi; cbMultiByte
0x180011a35  mov     r8, r14; lpMultiByteStr
0x180011a38  xor     edx, edx; dwFlags
0x180011a3a  lea     ecx, [rdx+3]; CodePage
0x180011a3d  call    cs:__imp_MultiByteToWideChar
0x180011a43  test    eax, eax
0x180011a45  jz      loc_180011969
0x180011a4b  mov     ecx, eax
0x180011a4d  mov     rax, [rsp+498h+var_438]
0x180011a52  mov     [rax+rcx*2], bx
0x180011a56  mov     r8d, [rsp+498h+arg_20]; int
0x180011a5e  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180011a63  lea     rcx, [rsp+498h+var_450]; this
0x180011a68  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180011a6d  mov     ebx, eax
0x180011a6f  mov     rcx, rdi; hLibModule
0x180011a72  call    cs:__imp_FreeLibrary
0x180011a78  nop
0x180011a79  lea     rax, [rsp+498h+var_430]
0x180011a7e  cmp     [rsp+498h+var_438], rax
0x180011a83  jz      short loc_180011A90
0x180011a85  lea     rcx, [rsp+498h+var_438]
0x180011a8a  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180011a8f  nop
0x180011a90  mov     eax, ebx
0x180011a92  mov     rcx, [rsp+498h+var_28]
0x180011a9a  xor     rcx, rsp; StackCookie
0x180011a9d  call    __security_check_cookie
0x180011aa2  mov     rbx, [rsp+498h+arg_0]
0x180011aaa  add     rsp, 480h
0x180011ab1  pop     r14
0x180011ab3  pop     rdi
0x180011ab4  pop     rsi
0x180011ab5  retn
0x180011ab6  mov     ecx, 80070057h; int
0x180011abb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
