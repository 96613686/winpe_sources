# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x14000d708`
- end: `0x14000d8c3`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000e20c`
- `0x14000e534`

## callees

- `0x140001fa0`
- `0x1400045e4`
- `0x14000cb58`
- `0x14000cc48`
- `0x14000ce40`
- `0x14000d578`
- `0x14000d708`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000d878`
- `KERNEL32!FreeLibrary` at `0x14000d878`
- `KERNEL32!LoadLibraryExW` at `0x14000d759`
- `KERNEL32!LoadLibraryExW` at `0x14000d759`
- `KERNEL32!MultiByteToWideChar` at `0x14000d842`
- `KERNEL32!MultiByteToWideChar` at `0x14000d842`
- `KERNEL32!SizeofResource` at `0x14000d7b1`
- `KERNEL32!SizeofResource` at `0x14000d7b1`
- `KERNEL32!LoadResource` at `0x14000d79d`
- `KERNEL32!LoadResource` at `0x14000d79d`
- `KERNEL32!FindResourceExW` at `0x14000d77f`
- `KERNEL32!FindResourceExW` at `0x14000d77f`

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
0x14000d708  mov     [rsp-8+arg_0], rbx
0x14000d70d  push    rbp
0x14000d70e  push    rsi
0x14000d70f  push    rdi
0x14000d710  lea     rbp, [rsp-360h]
0x14000d718  sub     rsp, 460h
0x14000d71f  mov     rax, cs:__security_cookie
0x14000d726  xor     rax, rsp
0x14000d729  mov     [rbp+370h+var_20], rax
0x14000d730  mov     rax, rdx
0x14000d733  mov     [rsp+470h+var_438], rcx
0x14000d738  xor     edx, edx; hFile
0x14000d73a  mov     [rsp+470h+var_440], 0
0x14000d743  mov     rbx, r8
0x14000d746  mov     [rsp+470h+var_430], 0
0x14000d74f  mov     rcx, rax; lpLibFileName
0x14000d752  mov     rsi, r9
0x14000d755  lea     r8d, [rdx+2]; dwFlags
0x14000d759  call    cs:__imp_LoadLibraryExW
0x14000d75f  mov     rdi, rax
0x14000d762  test    rax, rax
0x14000d765  jnz     short loc_14000D773
0x14000d767  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000d76c  mov     ebx, eax
0x14000d76e  jmp     loc_14000D87E
0x14000d773  xor     r9d, r9d; wLanguage
0x14000d776  mov     r8, rbx; lpName
0x14000d779  mov     rdx, rsi; lpType
0x14000d77c  mov     rcx, rdi; hModule
0x14000d77f  call    cs:__imp_FindResourceExW
0x14000d785  mov     rbx, rax
0x14000d788  test    rax, rax
0x14000d78b  jnz     short loc_14000D797
0x14000d78d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000d792  jmp     loc_14000D873
0x14000d797  mov     rdx, rbx; hResInfo
0x14000d79a  mov     rcx, rdi; hModule
0x14000d79d  call    cs:__imp_LoadResource
0x14000d7a3  mov     rsi, rax
0x14000d7a6  test    rax, rax
0x14000d7a9  jz      short loc_14000D78D
0x14000d7ab  mov     rdx, rbx; hResInfo
0x14000d7ae  mov     rcx, rdi; hModule
0x14000d7b1  call    cs:__imp_SizeofResource
0x14000d7b7  mov     ebx, eax
0x14000d7b9  lea     ecx, [rax+1]
0x14000d7bc  cmp     ecx, eax
0x14000d7be  jnb     short loc_14000D7E0
0x14000d7c0  lea     rax, [rsp+470h+var_428]
0x14000d7c5  cmp     [rsp+470h+var_430], rax
0x14000d7ca  jz      short loc_14000D7D6
0x14000d7cc  lea     rcx, [rsp+470h+var_430]
0x14000d7d1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000d7d6  mov     eax, 8007000Eh
0x14000d7db  jmp     loc_14000D896
0x14000d7e0  test    ecx, ecx
0x14000d7e2  jz      short loc_14000D818
0x14000d7e4  xor     edx, edx
0x14000d7e6  mov     r8d, ecx
0x14000d7e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d7ed  div     r8
0x14000d7f0  cmp     rax, 2
0x14000d7f4  jb      loc_14000D8B8
0x14000d7fa  lea     rdx, [rcx+rcx]
0x14000d7fe  cmp     rdx, 400h
0x14000d805  jbe     short loc_14000D818
0x14000d807  lea     rcx, [rsp+470h+var_430]
0x14000d80c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000d811  mov     rax, [rsp+470h+var_430]
0x14000d816  jmp     short loc_14000D822
0x14000d818  lea     rax, [rsp+470h+var_428]
0x14000d81d  mov     [rsp+470h+var_430], rax
0x14000d822  test    rax, rax
0x14000d825  jnz     short loc_14000D82E
0x14000d827  mov     ebx, 8007000Eh
0x14000d82c  jmp     short loc_14000D875
0x14000d82e  xor     edx, edx; dwFlags
0x14000d830  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x14000d834  mov     r9d, ebx; cbMultiByte
0x14000d837  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x14000d83c  mov     r8, rsi; lpMultiByteStr
0x14000d83f  lea     ecx, [rdx+3]; CodePage
0x14000d842  call    cs:__imp_MultiByteToWideChar
0x14000d848  test    eax, eax
0x14000d84a  jz      loc_14000D78D
0x14000d850  mov     r8d, [rbp+370h+arg_20]; int
0x14000d857  xor     ecx, ecx
0x14000d859  mov     edx, eax
0x14000d85b  mov     rax, [rsp+470h+var_430]
0x14000d860  mov     [rax+rdx*2], cx
0x14000d864  lea     rcx, [rsp+470h+var_440]; this
0x14000d869  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x14000d86e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x14000d873  mov     ebx, eax
0x14000d875  mov     rcx, rdi; hLibModule
0x14000d878  call    cs:__imp_FreeLibrary
0x14000d87e  lea     rax, [rsp+470h+var_428]
0x14000d883  cmp     [rsp+470h+var_430], rax
0x14000d888  jz      short loc_14000D894
0x14000d88a  lea     rcx, [rsp+470h+var_430]
0x14000d88f  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000d894  mov     eax, ebx
0x14000d896  mov     rcx, [rbp+370h+var_20]
0x14000d89d  xor     rcx, rsp; StackCookie
0x14000d8a0  call    __security_check_cookie
0x14000d8a5  mov     rbx, [rsp+470h+arg_0]
0x14000d8ad  add     rsp, 460h
0x14000d8b4  pop     rdi
0x14000d8b5  pop     rsi
0x14000d8b6  pop     rbp
0x14000d8b7  retn
0x14000d8b8  mov     ecx, 80070057h; int
0x14000d8bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
