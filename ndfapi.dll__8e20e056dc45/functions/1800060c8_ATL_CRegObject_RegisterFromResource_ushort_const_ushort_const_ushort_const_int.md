# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800060c8`
- end: `0x1800062a4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180006c60`

## callees

- `0x180004cc8`
- `0x180004df8`
- `0x180005688`
- `0x180005860`
- `0x180005f38`
- `0x1800060c8`
- `0x18001f690`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180006254`
- `KERNEL32!FreeLibrary` at `0x180006254`
- `KERNEL32!LoadLibraryExW` at `0x180006112`
- `KERNEL32!LoadLibraryExW` at `0x180006112`
- `KERNEL32!MultiByteToWideChar` at `0x18000621f`
- `KERNEL32!MultiByteToWideChar` at `0x18000621f`
- `KERNEL32!SizeofResource` at `0x180006174`
- `KERNEL32!SizeofResource` at `0x180006174`
- `KERNEL32!LoadResource` at `0x18000615b`
- `KERNEL32!LoadResource` at `0x18000615b`
- `KERNEL32!FindResourceExW` at `0x18000613d`
- `KERNEL32!FindResourceExW` at `0x18000613d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800060c8  mov     [rsp+arg_0], rbx
0x1800060cd  push    rsi
0x1800060ce  push    rdi
0x1800060cf  push    r14
0x1800060d1  sub     rsp, 480h
0x1800060d8  mov     rax, cs:__security_cookie
0x1800060df  xor     rax, rsp
0x1800060e2  mov     [rsp+498h+var_28], rax
0x1800060ea  mov     r14, r9
0x1800060ed  mov     rdi, r8
0x1800060f0  mov     rax, rdx
0x1800060f3  xor     ebx, ebx
0x1800060f5  mov     [rsp+498h+var_440], rbx
0x1800060fa  mov     [rsp+498h+var_448], rcx
0x1800060ff  mov     [rsp+498h+var_450], rbx
0x180006104  mov     [rsp+498h+var_438], rbx
0x180006109  xor     edx, edx; hFile
0x18000610b  lea     r8d, [rbx+2]; dwFlags
0x18000610f  mov     rcx, rax; lpLibFileName
0x180006112  call    cs:__imp_LoadLibraryExW
0x180006118  mov     rsi, rax
0x18000611b  mov     [rsp+498h+var_460], rax
0x180006120  test    rax, rax
0x180006123  jnz     short loc_180006131
0x180006125  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000612a  mov     ebx, eax
0x18000612c  jmp     loc_18000625B
0x180006131  xor     r9d, r9d; wLanguage
0x180006134  mov     r8, rdi; lpName
0x180006137  mov     rdx, r14; lpType
0x18000613a  mov     rcx, rsi; hModule
0x18000613d  call    cs:__imp_FindResourceExW
0x180006143  mov     rdi, rax
0x180006146  test    rax, rax
0x180006149  jnz     short loc_180006155
0x18000614b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006150  jmp     loc_18000624F
0x180006155  mov     rdx, rdi; hResInfo
0x180006158  mov     rcx, rsi; hModule
0x18000615b  call    cs:__imp_LoadResource
0x180006161  mov     r14, rax
0x180006164  mov     [rsp+498h+var_458], rax
0x180006169  test    rax, rax
0x18000616c  jz      short loc_18000614B
0x18000616e  mov     rdx, rdi; hResInfo
0x180006171  mov     rcx, rsi; hModule
0x180006174  call    cs:__imp_SizeofResource
0x18000617a  mov     edi, eax
0x18000617c  mov     [rsp+498h+var_468], eax
0x180006180  inc     eax
0x180006182  cmp     eax, edi
0x180006184  jnb     short loc_1800061A7
0x180006186  lea     rax, [rsp+498h+var_430]
0x18000618b  cmp     [rsp+498h+var_438], rax
0x180006190  jz      short loc_18000619D
0x180006192  lea     rcx, [rsp+498h+var_438]
0x180006197  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000619c  nop
0x18000619d  mov     eax, 8007000Eh
0x1800061a2  jmp     loc_180006274
0x1800061a7  test    eax, eax
0x1800061a9  jz      short loc_1800061DE
0x1800061ab  mov     ecx, eax
0x1800061ad  xor     edx, edx
0x1800061af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800061b3  div     rcx
0x1800061b6  cmp     rax, 2
0x1800061ba  jb      loc_180006298
0x1800061c0  lea     rdx, [rcx+rcx]
0x1800061c4  cmp     rdx, 400h
0x1800061cb  jbe     short loc_1800061DE
0x1800061cd  lea     rcx, [rsp+498h+var_438]
0x1800061d2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800061d7  mov     rax, [rsp+498h+var_438]
0x1800061dc  jmp     short loc_1800061E8
0x1800061de  lea     rax, [rsp+498h+var_430]
0x1800061e3  mov     [rsp+498h+var_438], rax
0x1800061e8  jmp     short loc_1800061FF
0x1800061ea  xor     ebx, ebx
0x1800061ec  mov     rsi, [rsp+498h+var_460]
0x1800061f1  mov     r14, [rsp+498h+var_458]
0x1800061f6  mov     edi, [rsp+498h+var_468]
0x1800061fa  mov     rax, [rsp+498h+var_438]
0x1800061ff  test    rax, rax
0x180006202  jnz     short loc_18000620B
0x180006204  mov     ebx, 8007000Eh
0x180006209  jmp     short loc_180006251
0x18000620b  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000620f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180006214  mov     r9d, edi; cbMultiByte
0x180006217  mov     r8, r14; lpMultiByteStr
0x18000621a  xor     edx, edx; dwFlags
0x18000621c  lea     ecx, [rdx+3]; CodePage
0x18000621f  call    cs:__imp_MultiByteToWideChar
0x180006225  test    eax, eax
0x180006227  jz      loc_18000614B
0x18000622d  mov     ecx, eax
0x18000622f  mov     rax, [rsp+498h+var_438]
0x180006234  mov     [rax+rcx*2], bx
0x180006238  mov     r8d, [rsp+498h+arg_20]; int
0x180006240  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180006245  lea     rcx, [rsp+498h+var_450]; this
0x18000624a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000624f  mov     ebx, eax
0x180006251  mov     rcx, rsi; hLibModule
0x180006254  call    cs:__imp_FreeLibrary
0x18000625a  nop
0x18000625b  lea     rax, [rsp+498h+var_430]
0x180006260  cmp     [rsp+498h+var_438], rax
0x180006265  jz      short loc_180006272
0x180006267  lea     rcx, [rsp+498h+var_438]
0x18000626c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006271  nop
0x180006272  mov     eax, ebx
0x180006274  mov     rcx, [rsp+498h+var_28]
0x18000627c  xor     rcx, rsp; StackCookie
0x18000627f  call    __security_check_cookie
0x180006284  mov     rbx, [rsp+498h+arg_0]
0x18000628c  add     rsp, 480h
0x180006293  pop     r14
0x180006295  pop     rdi
0x180006296  pop     rsi
0x180006297  retn
0x180006298  mov     ecx, 80070057h; int
0x18000629d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
