# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x140004128`
- end: `0x1400042e3`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140004f48`

## callees

- `0x140002aa8`
- `0x140002bd8`
- `0x140002c14`
- `0x1400030d4`
- `0x140003f98`
- `0x140004128`
- `0x1400065f0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140004298`
- `KERNEL32!FreeLibrary` at `0x140004298`
- `KERNEL32!LoadLibraryExW` at `0x140004179`
- `KERNEL32!LoadLibraryExW` at `0x140004179`
- `KERNEL32!MultiByteToWideChar` at `0x140004262`
- `KERNEL32!MultiByteToWideChar` at `0x140004262`
- `KERNEL32!SizeofResource` at `0x1400041d1`
- `KERNEL32!SizeofResource` at `0x1400041d1`
- `KERNEL32!LoadResource` at `0x1400041bd`
- `KERNEL32!LoadResource` at `0x1400041bd`
- `KERNEL32!FindResourceExW` at `0x14000419f`
- `KERNEL32!FindResourceExW` at `0x14000419f`

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
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  __int64 v15; // rcx
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  _QWORD v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[1032]; // [rsp+48h] [rbp-B8h] BYREF

  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
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
  if ( (unsigned int)v15 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_14;
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v15 < 2 )
      ATL::AtlThrowImpl(-2147024809);
    if ( (unsigned __int64)(2 * v15) <= 0x400 )
    {
LABEL_14:
      lpWideCharStr = (WCHAR *)v21;
      v20 = (LPWSTR)v21;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2 * v15);
      lpWideCharStr = v20;
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
      v20[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140004128  mov     [rsp-8+arg_0], rbx
0x14000412d  push    rbp
0x14000412e  push    rsi
0x14000412f  push    rdi
0x140004130  lea     rbp, [rsp-360h]
0x140004138  sub     rsp, 460h
0x14000413f  mov     rax, cs:__security_cookie
0x140004146  xor     rax, rsp
0x140004149  mov     [rbp+370h+var_20], rax
0x140004150  mov     rax, rdx
0x140004153  mov     [rsp+470h+var_438], rcx
0x140004158  xor     edx, edx; hFile
0x14000415a  mov     [rsp+470h+var_440], 0
0x140004163  mov     rbx, r8
0x140004166  mov     [rsp+470h+var_430], 0
0x14000416f  mov     rcx, rax; lpLibFileName
0x140004172  mov     rsi, r9
0x140004175  lea     r8d, [rdx+2]; dwFlags
0x140004179  call    cs:__imp_LoadLibraryExW
0x14000417f  mov     rdi, rax
0x140004182  test    rax, rax
0x140004185  jnz     short loc_140004193
0x140004187  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000418c  mov     ebx, eax
0x14000418e  jmp     loc_14000429E
0x140004193  xor     r9d, r9d; wLanguage
0x140004196  mov     r8, rbx; lpName
0x140004199  mov     rdx, rsi; lpType
0x14000419c  mov     rcx, rdi; hModule
0x14000419f  call    cs:__imp_FindResourceExW
0x1400041a5  mov     rbx, rax
0x1400041a8  test    rax, rax
0x1400041ab  jnz     short loc_1400041B7
0x1400041ad  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400041b2  jmp     loc_140004293
0x1400041b7  mov     rdx, rbx; hResInfo
0x1400041ba  mov     rcx, rdi; hModule
0x1400041bd  call    cs:__imp_LoadResource
0x1400041c3  mov     rsi, rax
0x1400041c6  test    rax, rax
0x1400041c9  jz      short loc_1400041AD
0x1400041cb  mov     rdx, rbx; hResInfo
0x1400041ce  mov     rcx, rdi; hModule
0x1400041d1  call    cs:__imp_SizeofResource
0x1400041d7  mov     ebx, eax
0x1400041d9  lea     ecx, [rax+1]
0x1400041dc  cmp     ecx, eax
0x1400041de  jnb     short loc_140004200
0x1400041e0  lea     rax, [rsp+470h+var_428]
0x1400041e5  cmp     [rsp+470h+var_430], rax
0x1400041ea  jz      short loc_1400041F6
0x1400041ec  lea     rcx, [rsp+470h+var_430]
0x1400041f1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400041f6  mov     eax, 8007000Eh
0x1400041fb  jmp     loc_1400042B6
0x140004200  test    ecx, ecx
0x140004202  jz      short loc_140004238
0x140004204  xor     edx, edx
0x140004206  mov     r8d, ecx
0x140004209  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000420d  div     r8
0x140004210  cmp     rax, 2
0x140004214  jb      loc_1400042D8
0x14000421a  lea     rdx, [rcx+rcx]
0x14000421e  cmp     rdx, 400h
0x140004225  jbe     short loc_140004238
0x140004227  lea     rcx, [rsp+470h+var_430]
0x14000422c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140004231  mov     rax, [rsp+470h+var_430]
0x140004236  jmp     short loc_140004242
0x140004238  lea     rax, [rsp+470h+var_428]
0x14000423d  mov     [rsp+470h+var_430], rax
0x140004242  test    rax, rax
0x140004245  jnz     short loc_14000424E
0x140004247  mov     ebx, 8007000Eh
0x14000424c  jmp     short loc_140004295
0x14000424e  xor     edx, edx; dwFlags
0x140004250  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x140004254  mov     r9d, ebx; cbMultiByte
0x140004257  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x14000425c  mov     r8, rsi; lpMultiByteStr
0x14000425f  lea     ecx, [rdx+3]; CodePage
0x140004262  call    cs:__imp_MultiByteToWideChar
0x140004268  test    eax, eax
0x14000426a  jz      loc_1400041AD
0x140004270  mov     r8d, [rbp+370h+arg_20]; int
0x140004277  xor     ecx, ecx
0x140004279  mov     edx, eax
0x14000427b  mov     rax, [rsp+470h+var_430]
0x140004280  mov     [rax+rdx*2], cx
0x140004284  lea     rcx, [rsp+470h+var_440]; this
0x140004289  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x14000428e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140004293  mov     ebx, eax
0x140004295  mov     rcx, rdi; hLibModule
0x140004298  call    cs:__imp_FreeLibrary
0x14000429e  lea     rax, [rsp+470h+var_428]
0x1400042a3  cmp     [rsp+470h+var_430], rax
0x1400042a8  jz      short loc_1400042B4
0x1400042aa  lea     rcx, [rsp+470h+var_430]
0x1400042af  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400042b4  mov     eax, ebx
0x1400042b6  mov     rcx, [rbp+370h+var_20]
0x1400042bd  xor     rcx, rsp; StackCookie
0x1400042c0  call    __security_check_cookie
0x1400042c5  mov     rbx, [rsp+470h+arg_0]
0x1400042cd  add     rsp, 460h
0x1400042d4  pop     rdi
0x1400042d5  pop     rsi
0x1400042d6  pop     rbp
0x1400042d7  retn
0x1400042d8  mov     ecx, 80070057h; int
0x1400042dd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
