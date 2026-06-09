# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004428`
- end: `0x180004604`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180005074`

## callees

- `0x180002f48`
- `0x180003078`
- `0x1800030b4`
- `0x1800039a4`
- `0x180004298`
- `0x180004428`
- `0x180009a00`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x1800044d4`
- `KERNEL32!SizeofResource` at `0x1800044d4`
- `KERNEL32!MultiByteToWideChar` at `0x18000457f`
- `KERNEL32!MultiByteToWideChar` at `0x18000457f`
- `KERNEL32!FindResourceExW` at `0x18000449d`
- `KERNEL32!FindResourceExW` at `0x18000449d`
- `KERNEL32!LoadResource` at `0x1800044bb`
- `KERNEL32!LoadResource` at `0x1800044bb`
- `KERNEL32!FreeLibrary` at `0x1800045b4`
- `KERNEL32!FreeLibrary` at `0x1800045b4`
- `KERNEL32!LoadLibraryExW` at `0x180004472`
- `KERNEL32!LoadLibraryExW` at `0x180004472`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
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
  LPCWSTR v20[3]; // [rsp+48h] [rbp-450h] BYREF
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
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
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
      v12 = ATL::CRegParser::RegisterBuffer(v20, v21, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004428  mov     [rsp+arg_0], rbx
0x18000442d  push    rsi
0x18000442e  push    rdi
0x18000442f  push    r14
0x180004431  sub     rsp, 480h
0x180004438  mov     rax, cs:__security_cookie
0x18000443f  xor     rax, rsp
0x180004442  mov     [rsp+498h+var_28], rax
0x18000444a  mov     r14, r9
0x18000444d  mov     rdi, r8
0x180004450  mov     rax, rdx
0x180004453  xor     ebx, ebx
0x180004455  mov     [rsp+498h+var_440], rbx
0x18000445a  mov     [rsp+498h+var_448], rcx
0x18000445f  mov     [rsp+498h+var_450], rbx
0x180004464  mov     [rsp+498h+var_438], rbx
0x180004469  xor     edx, edx; hFile
0x18000446b  lea     r8d, [rbx+2]; dwFlags
0x18000446f  mov     rcx, rax; lpLibFileName
0x180004472  call    cs:__imp_LoadLibraryExW
0x180004478  mov     rsi, rax
0x18000447b  mov     [rsp+498h+var_460], rax
0x180004480  test    rax, rax
0x180004483  jnz     short loc_180004491
0x180004485  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000448a  mov     ebx, eax
0x18000448c  jmp     loc_1800045BB
0x180004491  xor     r9d, r9d; wLanguage
0x180004494  mov     r8, rdi; lpName
0x180004497  mov     rdx, r14; lpType
0x18000449a  mov     rcx, rsi; hModule
0x18000449d  call    cs:__imp_FindResourceExW
0x1800044a3  mov     rdi, rax
0x1800044a6  test    rax, rax
0x1800044a9  jnz     short loc_1800044B5
0x1800044ab  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800044b0  jmp     loc_1800045AF
0x1800044b5  mov     rdx, rdi; hResInfo
0x1800044b8  mov     rcx, rsi; hModule
0x1800044bb  call    cs:__imp_LoadResource
0x1800044c1  mov     r14, rax
0x1800044c4  mov     [rsp+498h+var_458], rax
0x1800044c9  test    rax, rax
0x1800044cc  jz      short loc_1800044AB
0x1800044ce  mov     rdx, rdi; hResInfo
0x1800044d1  mov     rcx, rsi; hModule
0x1800044d4  call    cs:__imp_SizeofResource
0x1800044da  mov     edi, eax
0x1800044dc  mov     [rsp+498h+var_468], eax
0x1800044e0  inc     eax
0x1800044e2  cmp     eax, edi
0x1800044e4  jnb     short loc_180004507
0x1800044e6  lea     rax, [rsp+498h+var_430]
0x1800044eb  cmp     [rsp+498h+var_438], rax
0x1800044f0  jz      short loc_1800044FD
0x1800044f2  lea     rcx, [rsp+498h+var_438]
0x1800044f7  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800044fc  nop
0x1800044fd  mov     eax, 8007000Eh
0x180004502  jmp     loc_1800045D4
0x180004507  test    eax, eax
0x180004509  jz      short loc_18000453E
0x18000450b  mov     ecx, eax
0x18000450d  xor     edx, edx
0x18000450f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004513  div     rcx
0x180004516  cmp     rax, 2
0x18000451a  jb      loc_1800045F8
0x180004520  lea     rdx, [rcx+rcx]
0x180004524  cmp     rdx, 400h
0x18000452b  jbe     short loc_18000453E
0x18000452d  lea     rcx, [rsp+498h+var_438]
0x180004532  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004537  mov     rax, [rsp+498h+var_438]
0x18000453c  jmp     short loc_180004548
0x18000453e  lea     rax, [rsp+498h+var_430]
0x180004543  mov     [rsp+498h+var_438], rax
0x180004548  jmp     short loc_18000455F
0x18000454a  xor     ebx, ebx
0x18000454c  mov     rsi, [rsp+498h+var_460]
0x180004551  mov     r14, [rsp+498h+var_458]
0x180004556  mov     edi, [rsp+498h+var_468]
0x18000455a  mov     rax, [rsp+498h+var_438]
0x18000455f  test    rax, rax
0x180004562  jnz     short loc_18000456B
0x180004564  mov     ebx, 8007000Eh
0x180004569  jmp     short loc_1800045B1
0x18000456b  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000456f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180004574  mov     r9d, edi; cbMultiByte
0x180004577  mov     r8, r14; lpMultiByteStr
0x18000457a  xor     edx, edx; dwFlags
0x18000457c  lea     ecx, [rdx+3]; CodePage
0x18000457f  call    cs:__imp_MultiByteToWideChar
0x180004585  test    eax, eax
0x180004587  jz      loc_1800044AB
0x18000458d  mov     ecx, eax
0x18000458f  mov     rax, [rsp+498h+var_438]
0x180004594  mov     [rax+rcx*2], bx
0x180004598  mov     r8d, [rsp+498h+arg_20]; int
0x1800045a0  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800045a5  lea     rcx, [rsp+498h+var_450]; this
0x1800045aa  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800045af  mov     ebx, eax
0x1800045b1  mov     rcx, rsi; hLibModule
0x1800045b4  call    cs:__imp_FreeLibrary
0x1800045ba  nop
0x1800045bb  lea     rax, [rsp+498h+var_430]
0x1800045c0  cmp     [rsp+498h+var_438], rax
0x1800045c5  jz      short loc_1800045D2
0x1800045c7  lea     rcx, [rsp+498h+var_438]
0x1800045cc  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800045d1  nop
0x1800045d2  mov     eax, ebx
0x1800045d4  mov     rcx, [rsp+498h+var_28]
0x1800045dc  xor     rcx, rsp; StackCookie
0x1800045df  call    __security_check_cookie
0x1800045e4  mov     rbx, [rsp+498h+arg_0]
0x1800045ec  add     rsp, 480h
0x1800045f3  pop     r14
0x1800045f5  pop     rdi
0x1800045f6  pop     rsi
0x1800045f7  retn
0x1800045f8  mov     ecx, 80070057h; int
0x1800045fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
