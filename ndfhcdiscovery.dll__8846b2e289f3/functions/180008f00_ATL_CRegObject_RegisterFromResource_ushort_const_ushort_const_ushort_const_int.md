# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180008f00`
- end: `0x1800090ff`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `511`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009c78`

## callees

- `0x180006768`
- `0x1800068ac`
- `0x1800068ec`
- `0x1800070b4`
- `0x180008d5c`
- `0x180008f00`
- `0x1800136b0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800090a8`
- `KERNEL32!FreeLibrary` at `0x1800090a8`
- `KERNEL32!LoadLibraryExW` at `0x180008f47`
- `KERNEL32!LoadLibraryExW` at `0x180008f47`
- `KERNEL32!MultiByteToWideChar` at `0x18000906d`
- `KERNEL32!MultiByteToWideChar` at `0x18000906d`
- `KERNEL32!SizeofResource` at `0x180008fbc`
- `KERNEL32!SizeofResource` at `0x180008fbc`
- `KERNEL32!LoadResource` at `0x180008f9d`
- `KERNEL32!LoadResource` at `0x180008f9d`
- `KERNEL32!FindResourceExW` at `0x180008f79`
- `KERNEL32!FindResourceExW` at `0x180008f79`

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
0x180008f00  mov     [rsp+arg_0], rbx
0x180008f05  push    rsi
0x180008f06  push    rdi
0x180008f07  push    r14
0x180008f09  sub     rsp, 480h
0x180008f10  mov     rax, cs:__security_cookie
0x180008f17  xor     rax, rsp
0x180008f1a  mov     [rsp+498h+var_28], rax
0x180008f22  mov     rsi, r9
0x180008f25  mov     rax, rdx
0x180008f28  xor     ebx, ebx
0x180008f2a  mov     [rsp+498h+var_440], rbx
0x180008f2f  mov     [rsp+498h+var_448], rcx
0x180008f34  mov     [rsp+498h+var_450], rbx
0x180008f39  mov     [rsp+498h+var_438], rbx
0x180008f3e  xor     edx, edx; hFile
0x180008f40  lea     r8d, [rbx+2]; dwFlags
0x180008f44  mov     rcx, rax; lpLibFileName
0x180008f47  call    cs:__imp_LoadLibraryExW
0x180008f4e  nop     dword ptr [rax+rax+00h]
0x180008f53  mov     rdi, rax
0x180008f56  mov     [rsp+498h+var_460], rax
0x180008f5b  test    rax, rax
0x180008f5e  jnz     short loc_180008F6C
0x180008f60  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008f65  mov     ebx, eax
0x180008f67  jmp     loc_1800090B5
0x180008f6c  xor     r9d, r9d; wLanguage
0x180008f6f  lea     r8d, [r9+65h]; lpName
0x180008f73  mov     rdx, rsi; lpType
0x180008f76  mov     rcx, rdi; hModule
0x180008f79  call    cs:__imp_FindResourceExW
0x180008f80  nop     dword ptr [rax+rax+00h]
0x180008f85  mov     rsi, rax
0x180008f88  test    rax, rax
0x180008f8b  jnz     short loc_180008F97
0x180008f8d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008f92  jmp     loc_1800090A3
0x180008f97  mov     rdx, rsi; hResInfo
0x180008f9a  mov     rcx, rdi; hModule
0x180008f9d  call    cs:__imp_LoadResource
0x180008fa4  nop     dword ptr [rax+rax+00h]
0x180008fa9  mov     r14, rax
0x180008fac  mov     [rsp+498h+var_458], rax
0x180008fb1  test    rax, rax
0x180008fb4  jz      short loc_180008F8D
0x180008fb6  mov     rdx, rsi; hResInfo
0x180008fb9  mov     rcx, rdi; hModule
0x180008fbc  call    cs:__imp_SizeofResource
0x180008fc3  nop     dword ptr [rax+rax+00h]
0x180008fc8  mov     esi, eax
0x180008fca  mov     [rsp+498h+var_468], eax
0x180008fce  inc     eax
0x180008fd0  cmp     eax, esi
0x180008fd2  jnb     short loc_180008FF5
0x180008fd4  lea     rax, [rsp+498h+var_430]
0x180008fd9  cmp     [rsp+498h+var_438], rax
0x180008fde  jz      short loc_180008FEB
0x180008fe0  lea     rcx, [rsp+498h+var_438]
0x180008fe5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180008fea  nop
0x180008feb  mov     eax, 8007000Eh
0x180008ff0  jmp     loc_1800090CE
0x180008ff5  test    eax, eax
0x180008ff7  jz      short loc_18000902C
0x180008ff9  mov     ecx, eax
0x180008ffb  xor     edx, edx
0x180008ffd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009001  div     rcx
0x180009004  cmp     rax, 2
0x180009008  jb      loc_1800090F3
0x18000900e  lea     rdx, [rcx+rcx]
0x180009012  cmp     rdx, 400h
0x180009019  jbe     short loc_18000902C
0x18000901b  lea     rcx, [rsp+498h+var_438]
0x180009020  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180009025  mov     rax, [rsp+498h+var_438]
0x18000902a  jmp     short loc_180009036
0x18000902c  lea     rax, [rsp+498h+var_430]
0x180009031  mov     [rsp+498h+var_438], rax
0x180009036  jmp     short loc_18000904D
0x180009038  xor     ebx, ebx
0x18000903a  mov     rdi, [rsp+498h+var_460]
0x18000903f  mov     r14, [rsp+498h+var_458]
0x180009044  mov     esi, [rsp+498h+var_468]
0x180009048  mov     rax, [rsp+498h+var_438]
0x18000904d  test    rax, rax
0x180009050  jnz     short loc_180009059
0x180009052  mov     ebx, 8007000Eh
0x180009057  jmp     short loc_1800090A5
0x180009059  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x18000905d  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180009062  mov     r9d, esi; cbMultiByte
0x180009065  mov     r8, r14; lpMultiByteStr
0x180009068  xor     edx, edx; dwFlags
0x18000906a  lea     ecx, [rdx+3]; CodePage
0x18000906d  call    cs:__imp_MultiByteToWideChar
0x180009074  nop     dword ptr [rax+rax+00h]
0x180009079  test    eax, eax
0x18000907b  jz      loc_180008F8D
0x180009081  mov     ecx, eax
0x180009083  mov     rax, [rsp+498h+var_438]
0x180009088  mov     [rax+rcx*2], bx
0x18000908c  mov     r8d, [rsp+498h+arg_20]; int
0x180009094  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180009099  lea     rcx, [rsp+498h+var_450]; this
0x18000909e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800090a3  mov     ebx, eax
0x1800090a5  mov     rcx, rdi; hLibModule
0x1800090a8  call    cs:__imp_FreeLibrary
0x1800090af  nop     dword ptr [rax+rax+00h]
0x1800090b4  nop
0x1800090b5  lea     rax, [rsp+498h+var_430]
0x1800090ba  cmp     [rsp+498h+var_438], rax
0x1800090bf  jz      short loc_1800090CC
0x1800090c1  lea     rcx, [rsp+498h+var_438]
0x1800090c6  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800090cb  nop
0x1800090cc  mov     eax, ebx
0x1800090ce  mov     rcx, [rsp+498h+var_28]
0x1800090d6  xor     rcx, rsp; StackCookie
0x1800090d9  call    __security_check_cookie
0x1800090de  mov     rbx, [rsp+498h+arg_0]
0x1800090e6  add     rsp, 480h
0x1800090ed  pop     r14
0x1800090ef  pop     rdi
0x1800090f0  pop     rsi
0x1800090f1  retn
0x1800090f3  mov     ecx, 80070057h; int
0x1800090f8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
