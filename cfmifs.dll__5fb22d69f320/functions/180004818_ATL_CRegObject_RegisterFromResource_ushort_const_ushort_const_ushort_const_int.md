# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004818`
- end: `0x1800049d3`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000547c`
- `0x18000579c`

## callees

- `0x180003248`
- `0x180003484`
- `0x18000397c`
- `0x180003e24`
- `0x180004688`
- `0x180004818`
- `0x180006030`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800048c1`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800048c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004988`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004988`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800048ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800048ad`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000488f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000488f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004869`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004869`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004952`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004952`

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
0x180004818  mov     [rsp-8+arg_0], rbx
0x18000481d  push    rbp
0x18000481e  push    rsi
0x18000481f  push    rdi
0x180004820  lea     rbp, [rsp-360h]
0x180004828  sub     rsp, 460h
0x18000482f  mov     rax, cs:__security_cookie
0x180004836  xor     rax, rsp
0x180004839  mov     [rbp+370h+var_20], rax
0x180004840  mov     rax, rdx
0x180004843  mov     [rsp+470h+var_438], rcx
0x180004848  xor     edx, edx; hFile
0x18000484a  mov     [rsp+470h+var_440], 0
0x180004853  mov     rbx, r8
0x180004856  mov     [rsp+470h+var_430], 0
0x18000485f  mov     rcx, rax; lpLibFileName
0x180004862  mov     rsi, r9
0x180004865  lea     r8d, [rdx+2]; dwFlags
0x180004869  call    cs:__imp_LoadLibraryExW
0x18000486f  mov     rdi, rax
0x180004872  test    rax, rax
0x180004875  jnz     short loc_180004883
0x180004877  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000487c  mov     ebx, eax
0x18000487e  jmp     loc_18000498E
0x180004883  xor     r9d, r9d; wLanguage
0x180004886  mov     r8, rbx; lpName
0x180004889  mov     rdx, rsi; lpType
0x18000488c  mov     rcx, rdi; hModule
0x18000488f  call    cs:__imp_FindResourceExW
0x180004895  mov     rbx, rax
0x180004898  test    rax, rax
0x18000489b  jnz     short loc_1800048A7
0x18000489d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800048a2  jmp     loc_180004983
0x1800048a7  mov     rdx, rbx; hResInfo
0x1800048aa  mov     rcx, rdi; hModule
0x1800048ad  call    cs:__imp_LoadResource
0x1800048b3  mov     rsi, rax
0x1800048b6  test    rax, rax
0x1800048b9  jz      short loc_18000489D
0x1800048bb  mov     rdx, rbx; hResInfo
0x1800048be  mov     rcx, rdi; hModule
0x1800048c1  call    cs:__imp_SizeofResource
0x1800048c7  mov     ebx, eax
0x1800048c9  lea     ecx, [rax+1]
0x1800048cc  cmp     ecx, eax
0x1800048ce  jnb     short loc_1800048F0
0x1800048d0  lea     rax, [rsp+470h+var_428]
0x1800048d5  cmp     [rsp+470h+var_430], rax
0x1800048da  jz      short loc_1800048E6
0x1800048dc  lea     rcx, [rsp+470h+var_430]
0x1800048e1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800048e6  mov     eax, 8007000Eh
0x1800048eb  jmp     loc_1800049A6
0x1800048f0  test    ecx, ecx
0x1800048f2  jz      short loc_180004928
0x1800048f4  xor     edx, edx
0x1800048f6  mov     r8d, ecx
0x1800048f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800048fd  div     r8
0x180004900  cmp     rax, 2
0x180004904  jb      loc_1800049C8
0x18000490a  lea     rdx, [rcx+rcx]
0x18000490e  cmp     rdx, 400h
0x180004915  jbe     short loc_180004928
0x180004917  lea     rcx, [rsp+470h+var_430]
0x18000491c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004921  mov     rax, [rsp+470h+var_430]
0x180004926  jmp     short loc_180004932
0x180004928  lea     rax, [rsp+470h+var_428]
0x18000492d  mov     [rsp+470h+var_430], rax
0x180004932  test    rax, rax
0x180004935  jnz     short loc_18000493E
0x180004937  mov     ebx, 8007000Eh
0x18000493c  jmp     short loc_180004985
0x18000493e  xor     edx, edx; dwFlags
0x180004940  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x180004944  mov     r9d, ebx; cbMultiByte
0x180004947  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x18000494c  mov     r8, rsi; lpMultiByteStr
0x18000494f  lea     ecx, [rdx+3]; CodePage
0x180004952  call    cs:__imp_MultiByteToWideChar
0x180004958  test    eax, eax
0x18000495a  jz      loc_18000489D
0x180004960  mov     r8d, [rbp+370h+arg_20]; int
0x180004967  xor     ecx, ecx
0x180004969  mov     edx, eax
0x18000496b  mov     rax, [rsp+470h+var_430]
0x180004970  mov     [rax+rdx*2], cx
0x180004974  lea     rcx, [rsp+470h+var_440]; this
0x180004979  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x18000497e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004983  mov     ebx, eax
0x180004985  mov     rcx, rdi; hLibModule
0x180004988  call    cs:__imp_FreeLibrary
0x18000498e  lea     rax, [rsp+470h+var_428]
0x180004993  cmp     [rsp+470h+var_430], rax
0x180004998  jz      short loc_1800049A4
0x18000499a  lea     rcx, [rsp+470h+var_430]
0x18000499f  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800049a4  mov     eax, ebx
0x1800049a6  mov     rcx, [rbp+370h+var_20]
0x1800049ad  xor     rcx, rsp; StackCookie
0x1800049b0  call    __security_check_cookie
0x1800049b5  mov     rbx, [rsp+470h+arg_0]
0x1800049bd  add     rsp, 460h
0x1800049c4  pop     rdi
0x1800049c5  pop     rsi
0x1800049c6  pop     rbp
0x1800049c7  retn
0x1800049c8  mov     ecx, 80070057h; int
0x1800049cd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
