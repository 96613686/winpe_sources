# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180003878`
- end: `0x180003a33`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800043dc`
- `0x1800093cc`

## callees

- `0x180002958`
- `0x180002a88`
- `0x180002ac4`
- `0x180002f34`
- `0x1800036e8`
- `0x180003878`
- `0x180018500`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x180003921`
- `KERNEL32!SizeofResource` at `0x180003921`
- `KERNEL32!LoadLibraryExW` at `0x1800038c9`
- `KERNEL32!LoadLibraryExW` at `0x1800038c9`
- `KERNEL32!FreeLibrary` at `0x1800039e8`
- `KERNEL32!FreeLibrary` at `0x1800039e8`
- `KERNEL32!LoadResource` at `0x18000390d`
- `KERNEL32!LoadResource` at `0x18000390d`
- `KERNEL32!FindResourceExW` at `0x1800038ef`
- `KERNEL32!FindResourceExW` at `0x1800038ef`
- `KERNEL32!MultiByteToWideChar` at `0x1800039b2`
- `KERNEL32!MultiByteToWideChar` at `0x1800039b2`

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
0x180003878  mov     [rsp-8+arg_0], rbx
0x18000387d  push    rbp
0x18000387e  push    rsi
0x18000387f  push    rdi
0x180003880  lea     rbp, [rsp-360h]
0x180003888  sub     rsp, 460h
0x18000388f  mov     rax, cs:__security_cookie
0x180003896  xor     rax, rsp
0x180003899  mov     [rbp+370h+var_20], rax
0x1800038a0  mov     rax, rdx
0x1800038a3  mov     [rsp+470h+var_438], rcx
0x1800038a8  xor     edx, edx; hFile
0x1800038aa  mov     [rsp+470h+var_440], 0
0x1800038b3  mov     rbx, r8
0x1800038b6  mov     [rsp+470h+var_430], 0
0x1800038bf  mov     rcx, rax; lpLibFileName
0x1800038c2  mov     rsi, r9
0x1800038c5  lea     r8d, [rdx+2]; dwFlags
0x1800038c9  call    cs:__imp_LoadLibraryExW
0x1800038cf  mov     rdi, rax
0x1800038d2  test    rax, rax
0x1800038d5  jnz     short loc_1800038E3
0x1800038d7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800038dc  mov     ebx, eax
0x1800038de  jmp     loc_1800039EE
0x1800038e3  xor     r9d, r9d; wLanguage
0x1800038e6  mov     r8, rbx; lpName
0x1800038e9  mov     rdx, rsi; lpType
0x1800038ec  mov     rcx, rdi; hModule
0x1800038ef  call    cs:__imp_FindResourceExW
0x1800038f5  mov     rbx, rax
0x1800038f8  test    rax, rax
0x1800038fb  jnz     short loc_180003907
0x1800038fd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180003902  jmp     loc_1800039E3
0x180003907  mov     rdx, rbx; hResInfo
0x18000390a  mov     rcx, rdi; hModule
0x18000390d  call    cs:__imp_LoadResource
0x180003913  mov     rsi, rax
0x180003916  test    rax, rax
0x180003919  jz      short loc_1800038FD
0x18000391b  mov     rdx, rbx; hResInfo
0x18000391e  mov     rcx, rdi; hModule
0x180003921  call    cs:__imp_SizeofResource
0x180003927  mov     ebx, eax
0x180003929  lea     ecx, [rax+1]
0x18000392c  cmp     ecx, eax
0x18000392e  jnb     short loc_180003950
0x180003930  lea     rax, [rsp+470h+var_428]
0x180003935  cmp     [rsp+470h+var_430], rax
0x18000393a  jz      short loc_180003946
0x18000393c  lea     rcx, [rsp+470h+var_430]
0x180003941  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003946  mov     eax, 8007000Eh
0x18000394b  jmp     loc_180003A06
0x180003950  test    ecx, ecx
0x180003952  jz      short loc_180003988
0x180003954  xor     edx, edx
0x180003956  mov     r8d, ecx
0x180003959  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000395d  div     r8
0x180003960  cmp     rax, 2
0x180003964  jb      loc_180003A28
0x18000396a  lea     rdx, [rcx+rcx]
0x18000396e  cmp     rdx, 400h
0x180003975  jbe     short loc_180003988
0x180003977  lea     rcx, [rsp+470h+var_430]
0x18000397c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003981  mov     rax, [rsp+470h+var_430]
0x180003986  jmp     short loc_180003992
0x180003988  lea     rax, [rsp+470h+var_428]
0x18000398d  mov     [rsp+470h+var_430], rax
0x180003992  test    rax, rax
0x180003995  jnz     short loc_18000399E
0x180003997  mov     ebx, 8007000Eh
0x18000399c  jmp     short loc_1800039E5
0x18000399e  xor     edx, edx; dwFlags
0x1800039a0  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x1800039a4  mov     r9d, ebx; cbMultiByte
0x1800039a7  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x1800039ac  mov     r8, rsi; lpMultiByteStr
0x1800039af  lea     ecx, [rdx+3]; CodePage
0x1800039b2  call    cs:__imp_MultiByteToWideChar
0x1800039b8  test    eax, eax
0x1800039ba  jz      loc_1800038FD
0x1800039c0  mov     r8d, [rbp+370h+arg_20]; int
0x1800039c7  xor     ecx, ecx
0x1800039c9  mov     edx, eax
0x1800039cb  mov     rax, [rsp+470h+var_430]
0x1800039d0  mov     [rax+rdx*2], cx
0x1800039d4  lea     rcx, [rsp+470h+var_440]; this
0x1800039d9  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x1800039de  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800039e3  mov     ebx, eax
0x1800039e5  mov     rcx, rdi; hLibModule
0x1800039e8  call    cs:__imp_FreeLibrary
0x1800039ee  lea     rax, [rsp+470h+var_428]
0x1800039f3  cmp     [rsp+470h+var_430], rax
0x1800039f8  jz      short loc_180003A04
0x1800039fa  lea     rcx, [rsp+470h+var_430]
0x1800039ff  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003a04  mov     eax, ebx
0x180003a06  mov     rcx, [rbp+370h+var_20]
0x180003a0d  xor     rcx, rsp; StackCookie
0x180003a10  call    __security_check_cookie
0x180003a15  mov     rbx, [rsp+470h+arg_0]
0x180003a1d  add     rsp, 460h
0x180003a24  pop     rdi
0x180003a25  pop     rsi
0x180003a26  pop     rbp
0x180003a27  retn
0x180003a28  mov     ecx, 80070057h; int
0x180003a2d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
