# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800110a8`
- end: `0x180011284`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001217c`
- `0x18001249c`

## callees

- `0x18000e698`
- `0x18000e8d4`
- `0x18000f208`
- `0x18000fe34`
- `0x180010f18`
- `0x1800110a8`
- `0x1800181e0`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x180011154`
- `KERNEL32!SizeofResource` at `0x180011154`
- `KERNEL32!MultiByteToWideChar` at `0x1800111ff`
- `KERNEL32!MultiByteToWideChar` at `0x1800111ff`
- `KERNEL32!FindResourceExW` at `0x18001111d`
- `KERNEL32!FindResourceExW` at `0x18001111d`
- `KERNEL32!LoadResource` at `0x18001113b`
- `KERNEL32!LoadResource` at `0x18001113b`
- `KERNEL32!FreeLibrary` at `0x180011234`
- `KERNEL32!FreeLibrary` at `0x180011234`
- `KERNEL32!LoadLibraryExW` at `0x1800110f2`
- `KERNEL32!LoadLibraryExW` at `0x1800110f2`

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
0x1800110a8  mov     [rsp+arg_0], rbx
0x1800110ad  push    rsi
0x1800110ae  push    rdi
0x1800110af  push    r14
0x1800110b1  sub     rsp, 480h
0x1800110b8  mov     rax, cs:__security_cookie
0x1800110bf  xor     rax, rsp
0x1800110c2  mov     [rsp+498h+var_28], rax
0x1800110ca  mov     r14, r9
0x1800110cd  mov     rdi, r8
0x1800110d0  mov     rax, rdx
0x1800110d3  xor     ebx, ebx
0x1800110d5  mov     [rsp+498h+var_440], rbx
0x1800110da  mov     [rsp+498h+var_448], rcx
0x1800110df  mov     [rsp+498h+var_450], rbx
0x1800110e4  mov     [rsp+498h+var_438], rbx
0x1800110e9  xor     edx, edx; hFile
0x1800110eb  lea     r8d, [rbx+2]; dwFlags
0x1800110ef  mov     rcx, rax; lpLibFileName
0x1800110f2  call    cs:__imp_LoadLibraryExW
0x1800110f8  mov     rsi, rax
0x1800110fb  mov     [rsp+498h+var_460], rax
0x180011100  test    rax, rax
0x180011103  jnz     short loc_180011111
0x180011105  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001110a  mov     ebx, eax
0x18001110c  jmp     loc_18001123B
0x180011111  xor     r9d, r9d; wLanguage
0x180011114  mov     r8, rdi; lpName
0x180011117  mov     rdx, r14; lpType
0x18001111a  mov     rcx, rsi; hModule
0x18001111d  call    cs:__imp_FindResourceExW
0x180011123  mov     rdi, rax
0x180011126  test    rax, rax
0x180011129  jnz     short loc_180011135
0x18001112b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011130  jmp     loc_18001122F
0x180011135  mov     rdx, rdi; hResInfo
0x180011138  mov     rcx, rsi; hModule
0x18001113b  call    cs:__imp_LoadResource
0x180011141  mov     r14, rax
0x180011144  mov     [rsp+498h+var_458], rax
0x180011149  test    rax, rax
0x18001114c  jz      short loc_18001112B
0x18001114e  mov     rdx, rdi; hResInfo
0x180011151  mov     rcx, rsi; hModule
0x180011154  call    cs:__imp_SizeofResource
0x18001115a  mov     edi, eax
0x18001115c  mov     [rsp+498h+var_468], eax
0x180011160  inc     eax
0x180011162  cmp     eax, edi
0x180011164  jnb     short loc_180011187
0x180011166  lea     rax, [rsp+498h+var_430]
0x18001116b  cmp     [rsp+498h+var_438], rax
0x180011170  jz      short loc_18001117D
0x180011172  lea     rcx, [rsp+498h+var_438]
0x180011177  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18001117c  nop
0x18001117d  mov     eax, 8007000Eh
0x180011182  jmp     loc_180011254
0x180011187  test    eax, eax
0x180011189  jz      short loc_1800111BE
0x18001118b  mov     ecx, eax
0x18001118d  xor     edx, edx
0x18001118f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011193  div     rcx
0x180011196  cmp     rax, 2
0x18001119a  jb      loc_180011278
0x1800111a0  lea     rdx, [rcx+rcx]
0x1800111a4  cmp     rdx, 400h
0x1800111ab  jbe     short loc_1800111BE
0x1800111ad  lea     rcx, [rsp+498h+var_438]
0x1800111b2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800111b7  mov     rax, [rsp+498h+var_438]
0x1800111bc  jmp     short loc_1800111C8
0x1800111be  lea     rax, [rsp+498h+var_430]
0x1800111c3  mov     [rsp+498h+var_438], rax
0x1800111c8  jmp     short loc_1800111DF
0x1800111ca  xor     ebx, ebx
0x1800111cc  mov     rsi, [rsp+498h+var_460]
0x1800111d1  mov     r14, [rsp+498h+var_458]
0x1800111d6  mov     edi, [rsp+498h+var_468]
0x1800111da  mov     rax, [rsp+498h+var_438]
0x1800111df  test    rax, rax
0x1800111e2  jnz     short loc_1800111EB
0x1800111e4  mov     ebx, 8007000Eh
0x1800111e9  jmp     short loc_180011231
0x1800111eb  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1800111ef  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1800111f4  mov     r9d, edi; cbMultiByte
0x1800111f7  mov     r8, r14; lpMultiByteStr
0x1800111fa  xor     edx, edx; dwFlags
0x1800111fc  lea     ecx, [rdx+3]; CodePage
0x1800111ff  call    cs:__imp_MultiByteToWideChar
0x180011205  test    eax, eax
0x180011207  jz      loc_18001112B
0x18001120d  mov     ecx, eax
0x18001120f  mov     rax, [rsp+498h+var_438]
0x180011214  mov     [rax+rcx*2], bx
0x180011218  mov     r8d, [rsp+498h+arg_20]; int
0x180011220  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180011225  lea     rcx, [rsp+498h+var_450]; this
0x18001122a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18001122f  mov     ebx, eax
0x180011231  mov     rcx, rsi; hLibModule
0x180011234  call    cs:__imp_FreeLibrary
0x18001123a  nop
0x18001123b  lea     rax, [rsp+498h+var_430]
0x180011240  cmp     [rsp+498h+var_438], rax
0x180011245  jz      short loc_180011252
0x180011247  lea     rcx, [rsp+498h+var_438]
0x18001124c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180011251  nop
0x180011252  mov     eax, ebx
0x180011254  mov     rcx, [rsp+498h+var_28]
0x18001125c  xor     rcx, rsp; StackCookie
0x18001125f  call    __security_check_cookie
0x180011264  mov     rbx, [rsp+498h+arg_0]
0x18001126c  add     rsp, 480h
0x180011273  pop     r14
0x180011275  pop     rdi
0x180011276  pop     rsi
0x180011277  retn
0x180011278  mov     ecx, 80070057h; int
0x18001127d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
