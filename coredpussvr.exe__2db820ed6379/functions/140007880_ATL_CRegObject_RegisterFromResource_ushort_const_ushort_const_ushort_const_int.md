# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x140007880`
- end: `0x140007a81`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `513`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140008460`
- `0x14000878c`

## callees

- `0x140001500`
- `0x1400067c8`
- `0x140006900`
- `0x140006940`
- `0x140006e04`
- `0x1400076dc`
- `0x140007880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400078ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400078ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007a2a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007a2a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1400078fb`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1400078fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14000791f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14000791f`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14000793e`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14000793e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400079ef`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400079ef`

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
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int v12; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  DWORD v15; // eax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  _QWORD v20[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v22[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20[2] = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v21 != (LPWSTR)v22 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v21);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, a3, 0);
  v11 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v13 = (const CHAR *)LoadResource(v8, Resource);
  if ( !v13 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v8, v11);
  v15 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v15 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v22;
        v21 = (LPWSTR)v22;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, 2LL * v15);
        lpWideCharStr = v21;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v8);
      goto LABEL_21;
    }
    v18 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v21[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140007880  mov     [rsp+arg_0], rbx
0x140007885  push    rsi
0x140007886  push    rdi
0x140007887  push    r14
0x140007889  sub     rsp, 480h
0x140007890  mov     rax, cs:__security_cookie
0x140007897  xor     rax, rsp
0x14000789a  mov     [rsp+498h+var_28], rax
0x1400078a2  mov     r14, r9
0x1400078a5  mov     rdi, r8
0x1400078a8  mov     rax, rdx
0x1400078ab  xor     ebx, ebx
0x1400078ad  mov     [rsp+498h+var_440], rbx
0x1400078b2  mov     [rsp+498h+var_448], rcx
0x1400078b7  mov     [rsp+498h+var_450], rbx
0x1400078bc  mov     [rsp+498h+var_438], rbx
0x1400078c1  xor     edx, edx; hFile
0x1400078c3  lea     r8d, [rbx+2]; dwFlags
0x1400078c7  mov     rcx, rax; lpLibFileName
0x1400078ca  call    cs:__imp_LoadLibraryExW
0x1400078d1  nop     dword ptr [rax+rax+00h]
0x1400078d6  mov     rsi, rax
0x1400078d9  mov     [rsp+498h+var_460], rax
0x1400078de  test    rax, rax
0x1400078e1  jnz     short loc_1400078EF
0x1400078e3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400078e8  mov     ebx, eax
0x1400078ea  jmp     loc_140007A37
0x1400078ef  xor     r9d, r9d; wLanguage
0x1400078f2  mov     r8, rdi; lpName
0x1400078f5  mov     rdx, r14; lpType
0x1400078f8  mov     rcx, rsi; hModule
0x1400078fb  call    cs:__imp_FindResourceExW
0x140007902  nop     dword ptr [rax+rax+00h]
0x140007907  mov     rdi, rax
0x14000790a  test    rax, rax
0x14000790d  jnz     short loc_140007919
0x14000790f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140007914  jmp     loc_140007A25
0x140007919  mov     rdx, rdi; hResInfo
0x14000791c  mov     rcx, rsi; hModule
0x14000791f  call    cs:__imp_LoadResource
0x140007926  nop     dword ptr [rax+rax+00h]
0x14000792b  mov     r14, rax
0x14000792e  mov     [rsp+498h+var_458], rax
0x140007933  test    rax, rax
0x140007936  jz      short loc_14000790F
0x140007938  mov     rdx, rdi; hResInfo
0x14000793b  mov     rcx, rsi; hModule
0x14000793e  call    cs:__imp_SizeofResource
0x140007945  nop     dword ptr [rax+rax+00h]
0x14000794a  mov     edi, eax
0x14000794c  mov     [rsp+498h+var_468], eax
0x140007950  inc     eax
0x140007952  cmp     eax, edi
0x140007954  jnb     short loc_140007977
0x140007956  lea     rax, [rsp+498h+var_430]
0x14000795b  cmp     [rsp+498h+var_438], rax
0x140007960  jz      short loc_14000796D
0x140007962  lea     rcx, [rsp+498h+var_438]
0x140007967  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000796c  nop
0x14000796d  mov     eax, 8007000Eh
0x140007972  jmp     loc_140007A50
0x140007977  test    eax, eax
0x140007979  jz      short loc_1400079AE
0x14000797b  mov     ecx, eax
0x14000797d  xor     edx, edx
0x14000797f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007983  div     rcx
0x140007986  cmp     rax, 2
0x14000798a  jb      loc_140007A75
0x140007990  lea     rdx, [rcx+rcx]
0x140007994  cmp     rdx, 400h
0x14000799b  jbe     short loc_1400079AE
0x14000799d  lea     rcx, [rsp+498h+var_438]
0x1400079a2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400079a7  mov     rax, [rsp+498h+var_438]
0x1400079ac  jmp     short loc_1400079B8
0x1400079ae  lea     rax, [rsp+498h+var_430]
0x1400079b3  mov     [rsp+498h+var_438], rax
0x1400079b8  jmp     short loc_1400079CF
0x1400079ba  xor     ebx, ebx
0x1400079bc  mov     rsi, [rsp+498h+var_460]
0x1400079c1  mov     r14, [rsp+498h+var_458]
0x1400079c6  mov     edi, [rsp+498h+var_468]
0x1400079ca  mov     rax, [rsp+498h+var_438]
0x1400079cf  test    rax, rax
0x1400079d2  jnz     short loc_1400079DB
0x1400079d4  mov     ebx, 8007000Eh
0x1400079d9  jmp     short loc_140007A27
0x1400079db  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1400079df  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1400079e4  mov     r9d, edi; cbMultiByte
0x1400079e7  mov     r8, r14; lpMultiByteStr
0x1400079ea  xor     edx, edx; dwFlags
0x1400079ec  lea     ecx, [rdx+3]; CodePage
0x1400079ef  call    cs:__imp_MultiByteToWideChar
0x1400079f6  nop     dword ptr [rax+rax+00h]
0x1400079fb  test    eax, eax
0x1400079fd  jz      loc_14000790F
0x140007a03  mov     ecx, eax
0x140007a05  mov     rax, [rsp+498h+var_438]
0x140007a0a  mov     [rax+rcx*2], bx
0x140007a0e  mov     r8d, [rsp+498h+arg_20]; int
0x140007a16  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x140007a1b  lea     rcx, [rsp+498h+var_450]; this
0x140007a20  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140007a25  mov     ebx, eax
0x140007a27  mov     rcx, rsi; hLibModule
0x140007a2a  call    cs:__imp_FreeLibrary
0x140007a31  nop     dword ptr [rax+rax+00h]
0x140007a36  nop
0x140007a37  lea     rax, [rsp+498h+var_430]
0x140007a3c  cmp     [rsp+498h+var_438], rax
0x140007a41  jz      short loc_140007A4E
0x140007a43  lea     rcx, [rsp+498h+var_438]
0x140007a48  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140007a4d  nop
0x140007a4e  mov     eax, ebx
0x140007a50  mov     rcx, [rsp+498h+var_28]
0x140007a58  xor     rcx, rsp; StackCookie
0x140007a5b  call    __security_check_cookie
0x140007a60  mov     rbx, [rsp+498h+arg_0]
0x140007a68  add     rsp, 480h
0x140007a6f  pop     r14
0x140007a71  pop     rdi
0x140007a72  pop     rsi
0x140007a73  retn
0x140007a75  mov     ecx, 80070057h; int
0x140007a7a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
