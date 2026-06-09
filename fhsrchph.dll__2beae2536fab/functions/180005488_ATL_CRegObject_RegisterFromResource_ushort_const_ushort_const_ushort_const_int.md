# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180005488`
- end: `0x180005664`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180006164`

## callees

- `0x1800022a0`
- `0x18000278c`
- `0x180003d88`
- `0x1800049e8`
- `0x1800052f8`
- `0x180005488`
- `0x18000ab60`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x1800054fd`
- `KERNEL32!FindResourceExW` at `0x1800054fd`
- `KERNEL32!LoadLibraryExW` at `0x1800054d2`
- `KERNEL32!LoadLibraryExW` at `0x1800054d2`
- `KERNEL32!FreeLibrary` at `0x180005614`
- `KERNEL32!FreeLibrary` at `0x180005614`
- `KERNEL32!MultiByteToWideChar` at `0x1800055df`
- `KERNEL32!MultiByteToWideChar` at `0x1800055df`
- `KERNEL32!SizeofResource` at `0x180005534`
- `KERNEL32!SizeofResource` at `0x180005534`
- `KERNEL32!LoadResource` at `0x18000551b`
- `KERNEL32!LoadResource` at `0x18000551b`

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
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21);
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
0x180005488  mov     [rsp+arg_0], rbx
0x18000548d  push    rsi
0x18000548e  push    rdi
0x18000548f  push    r14
0x180005491  sub     rsp, 480h
0x180005498  mov     rax, cs:__security_cookie
0x18000549f  xor     rax, rsp
0x1800054a2  mov     [rsp+498h+var_28], rax
0x1800054aa  mov     r14, r9
0x1800054ad  mov     rdi, r8
0x1800054b0  mov     rax, rdx
0x1800054b3  xor     ebx, ebx
0x1800054b5  mov     [rsp+498h+var_440], rbx
0x1800054ba  mov     [rsp+498h+var_448], rcx
0x1800054bf  mov     [rsp+498h+var_450], rbx
0x1800054c4  mov     [rsp+498h+var_438], rbx
0x1800054c9  xor     edx, edx; hFile
0x1800054cb  lea     r8d, [rbx+2]; dwFlags
0x1800054cf  mov     rcx, rax; lpLibFileName
0x1800054d2  call    cs:__imp_LoadLibraryExW
0x1800054d8  mov     rsi, rax
0x1800054db  mov     [rsp+498h+var_460], rax
0x1800054e0  test    rax, rax
0x1800054e3  jnz     short loc_1800054F1
0x1800054e5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800054ea  mov     ebx, eax
0x1800054ec  jmp     loc_18000561B
0x1800054f1  xor     r9d, r9d; wLanguage
0x1800054f4  mov     r8, rdi; lpName
0x1800054f7  mov     rdx, r14; lpType
0x1800054fa  mov     rcx, rsi; hModule
0x1800054fd  call    cs:__imp_FindResourceExW
0x180005503  mov     rdi, rax
0x180005506  test    rax, rax
0x180005509  jnz     short loc_180005515
0x18000550b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005510  jmp     loc_18000560F
0x180005515  mov     rdx, rdi; hResInfo
0x180005518  mov     rcx, rsi; hModule
0x18000551b  call    cs:__imp_LoadResource
0x180005521  mov     r14, rax
0x180005524  mov     [rsp+498h+var_458], rax
0x180005529  test    rax, rax
0x18000552c  jz      short loc_18000550B
0x18000552e  mov     rdx, rdi; hResInfo
0x180005531  mov     rcx, rsi; hModule
0x180005534  call    cs:__imp_SizeofResource
0x18000553a  mov     edi, eax
0x18000553c  mov     [rsp+498h+var_468], eax
0x180005540  inc     eax
0x180005542  cmp     eax, edi
0x180005544  jnb     short loc_180005567
0x180005546  lea     rax, [rsp+498h+var_430]
0x18000554b  cmp     [rsp+498h+var_438], rax
0x180005550  jz      short loc_18000555D
0x180005552  lea     rcx, [rsp+498h+var_438]
0x180005557  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000555c  nop
0x18000555d  mov     eax, 8007000Eh
0x180005562  jmp     loc_180005634
0x180005567  test    eax, eax
0x180005569  jz      short loc_18000559E
0x18000556b  mov     ecx, eax
0x18000556d  xor     edx, edx
0x18000556f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005573  div     rcx
0x180005576  cmp     rax, 2
0x18000557a  jb      loc_180005658
0x180005580  lea     rdx, [rcx+rcx]
0x180005584  cmp     rdx, 400h
0x18000558b  jbe     short loc_18000559E
0x18000558d  lea     rcx, [rsp+498h+var_438]
0x180005592  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005597  mov     rax, [rsp+498h+var_438]
0x18000559c  jmp     short loc_1800055A8
0x18000559e  lea     rax, [rsp+498h+var_430]
0x1800055a3  mov     [rsp+498h+var_438], rax
0x1800055a8  jmp     short loc_1800055BF
0x1800055aa  xor     ebx, ebx
0x1800055ac  mov     rsi, [rsp+498h+var_460]
0x1800055b1  mov     r14, [rsp+498h+var_458]
0x1800055b6  mov     edi, [rsp+498h+var_468]
0x1800055ba  mov     rax, [rsp+498h+var_438]
0x1800055bf  test    rax, rax
0x1800055c2  jnz     short loc_1800055CB
0x1800055c4  mov     ebx, 8007000Eh
0x1800055c9  jmp     short loc_180005611
0x1800055cb  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1800055cf  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1800055d4  mov     r9d, edi; cbMultiByte
0x1800055d7  mov     r8, r14; lpMultiByteStr
0x1800055da  xor     edx, edx; dwFlags
0x1800055dc  lea     ecx, [rdx+3]; CodePage
0x1800055df  call    cs:__imp_MultiByteToWideChar
0x1800055e5  test    eax, eax
0x1800055e7  jz      loc_18000550B
0x1800055ed  mov     ecx, eax
0x1800055ef  mov     rax, [rsp+498h+var_438]
0x1800055f4  mov     [rax+rcx*2], bx
0x1800055f8  mov     r8d, [rsp+498h+arg_20]; int
0x180005600  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180005605  lea     rcx, [rsp+498h+var_450]; this
0x18000560a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000560f  mov     ebx, eax
0x180005611  mov     rcx, rsi; hLibModule
0x180005614  call    cs:__imp_FreeLibrary
0x18000561a  nop
0x18000561b  lea     rax, [rsp+498h+var_430]
0x180005620  cmp     [rsp+498h+var_438], rax
0x180005625  jz      short loc_180005632
0x180005627  lea     rcx, [rsp+498h+var_438]
0x18000562c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180005631  nop
0x180005632  mov     eax, ebx
0x180005634  mov     rcx, [rsp+498h+var_28]
0x18000563c  xor     rcx, rsp; StackCookie
0x18000563f  call    __security_check_cookie
0x180005644  mov     rbx, [rsp+498h+arg_0]
0x18000564c  add     rsp, 480h
0x180005653  pop     r14
0x180005655  pop     rdi
0x180005656  pop     rsi
0x180005657  retn
0x180005658  mov     ecx, 80070057h; int
0x18000565d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
