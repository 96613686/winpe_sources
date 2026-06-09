# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800042a8`
- end: `0x180004484`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180004d04`

## callees

- `0x180003118`
- `0x180003248`
- `0x18000374c`
- `0x180003a3c`
- `0x180004118`
- `0x1800042a8`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x180004354`
- `KERNEL32!SizeofResource` at `0x180004354`
- `KERNEL32!MultiByteToWideChar` at `0x1800043ff`
- `KERNEL32!MultiByteToWideChar` at `0x1800043ff`
- `KERNEL32!FindResourceExW` at `0x18000431d`
- `KERNEL32!FindResourceExW` at `0x18000431d`
- `KERNEL32!LoadResource` at `0x18000433b`
- `KERNEL32!LoadResource` at `0x18000433b`
- `KERNEL32!FreeLibrary` at `0x180004434`
- `KERNEL32!FreeLibrary` at `0x180004434`
- `KERNEL32!LoadLibraryExW` at `0x1800042f2`
- `KERNEL32!LoadLibraryExW` at `0x1800042f2`

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
0x1800042a8  mov     [rsp+arg_0], rbx
0x1800042ad  push    rsi
0x1800042ae  push    rdi
0x1800042af  push    r14
0x1800042b1  sub     rsp, 480h
0x1800042b8  mov     rax, cs:__security_cookie
0x1800042bf  xor     rax, rsp
0x1800042c2  mov     [rsp+498h+var_28], rax
0x1800042ca  mov     r14, r9
0x1800042cd  mov     rdi, r8
0x1800042d0  mov     rax, rdx
0x1800042d3  xor     ebx, ebx
0x1800042d5  mov     [rsp+498h+var_440], rbx
0x1800042da  mov     [rsp+498h+var_448], rcx
0x1800042df  mov     [rsp+498h+var_450], rbx
0x1800042e4  mov     [rsp+498h+var_438], rbx
0x1800042e9  xor     edx, edx; hFile
0x1800042eb  lea     r8d, [rbx+2]; dwFlags
0x1800042ef  mov     rcx, rax; lpLibFileName
0x1800042f2  call    cs:__imp_LoadLibraryExW
0x1800042f8  mov     rsi, rax
0x1800042fb  mov     [rsp+498h+var_460], rax
0x180004300  test    rax, rax
0x180004303  jnz     short loc_180004311
0x180004305  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000430a  mov     ebx, eax
0x18000430c  jmp     loc_18000443B
0x180004311  xor     r9d, r9d; wLanguage
0x180004314  mov     r8, rdi; lpName
0x180004317  mov     rdx, r14; lpType
0x18000431a  mov     rcx, rsi; hModule
0x18000431d  call    cs:__imp_FindResourceExW
0x180004323  mov     rdi, rax
0x180004326  test    rax, rax
0x180004329  jnz     short loc_180004335
0x18000432b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004330  jmp     loc_18000442F
0x180004335  mov     rdx, rdi; hResInfo
0x180004338  mov     rcx, rsi; hModule
0x18000433b  call    cs:__imp_LoadResource
0x180004341  mov     r14, rax
0x180004344  mov     [rsp+498h+var_458], rax
0x180004349  test    rax, rax
0x18000434c  jz      short loc_18000432B
0x18000434e  mov     rdx, rdi; hResInfo
0x180004351  mov     rcx, rsi; hModule
0x180004354  call    cs:__imp_SizeofResource
0x18000435a  mov     edi, eax
0x18000435c  mov     [rsp+498h+var_468], eax
0x180004360  inc     eax
0x180004362  cmp     eax, edi
0x180004364  jnb     short loc_180004387
0x180004366  lea     rax, [rsp+498h+var_430]
0x18000436b  cmp     [rsp+498h+var_438], rax
0x180004370  jz      short loc_18000437D
0x180004372  lea     rcx, [rsp+498h+var_438]
0x180004377  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000437c  nop
0x18000437d  mov     eax, 8007000Eh
0x180004382  jmp     loc_180004454
0x180004387  test    eax, eax
0x180004389  jz      short loc_1800043BE
0x18000438b  mov     ecx, eax
0x18000438d  xor     edx, edx
0x18000438f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004393  div     rcx
0x180004396  cmp     rax, 2
0x18000439a  jb      loc_180004478
0x1800043a0  lea     rdx, [rcx+rcx]
0x1800043a4  cmp     rdx, 400h
0x1800043ab  jbe     short loc_1800043BE
0x1800043ad  lea     rcx, [rsp+498h+var_438]
0x1800043b2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800043b7  mov     rax, [rsp+498h+var_438]
0x1800043bc  jmp     short loc_1800043C8
0x1800043be  lea     rax, [rsp+498h+var_430]
0x1800043c3  mov     [rsp+498h+var_438], rax
0x1800043c8  jmp     short loc_1800043DF
0x1800043ca  xor     ebx, ebx
0x1800043cc  mov     rsi, [rsp+498h+var_460]
0x1800043d1  mov     r14, [rsp+498h+var_458]
0x1800043d6  mov     edi, [rsp+498h+var_468]
0x1800043da  mov     rax, [rsp+498h+var_438]
0x1800043df  test    rax, rax
0x1800043e2  jnz     short loc_1800043EB
0x1800043e4  mov     ebx, 8007000Eh
0x1800043e9  jmp     short loc_180004431
0x1800043eb  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1800043ef  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1800043f4  mov     r9d, edi; cbMultiByte
0x1800043f7  mov     r8, r14; lpMultiByteStr
0x1800043fa  xor     edx, edx; dwFlags
0x1800043fc  lea     ecx, [rdx+3]; CodePage
0x1800043ff  call    cs:__imp_MultiByteToWideChar
0x180004405  test    eax, eax
0x180004407  jz      loc_18000432B
0x18000440d  mov     ecx, eax
0x18000440f  mov     rax, [rsp+498h+var_438]
0x180004414  mov     [rax+rcx*2], bx
0x180004418  mov     r8d, [rsp+498h+arg_20]; int
0x180004420  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180004425  lea     rcx, [rsp+498h+var_450]; this
0x18000442a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000442f  mov     ebx, eax
0x180004431  mov     rcx, rsi; hLibModule
0x180004434  call    cs:__imp_FreeLibrary
0x18000443a  nop
0x18000443b  lea     rax, [rsp+498h+var_430]
0x180004440  cmp     [rsp+498h+var_438], rax
0x180004445  jz      short loc_180004452
0x180004447  lea     rcx, [rsp+498h+var_438]
0x18000444c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004451  nop
0x180004452  mov     eax, ebx
0x180004454  mov     rcx, [rsp+498h+var_28]
0x18000445c  xor     rcx, rsp; StackCookie
0x18000445f  call    __security_check_cookie
0x180004464  mov     rbx, [rsp+498h+arg_0]
0x18000446c  add     rsp, 480h
0x180004473  pop     r14
0x180004475  pop     rdi
0x180004476  pop     rsi
0x180004477  retn
0x180004478  mov     ecx, 80070057h; int
0x18000447d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
