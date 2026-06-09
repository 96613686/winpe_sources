# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180005038`
- end: `0x180005214`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180005d2c`
- `0x180006054`

## callees

- `0x180001f90`
- `0x180003c48`
- `0x180003e74`
- `0x180003eb0`
- `0x180004494`
- `0x180004ea8`
- `0x180005038`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000518f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000518f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800050cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800050cb`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800050e4`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800050e4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800051c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800051c4`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800050ad`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800050ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005082`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005082`

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
0x180005038  mov     [rsp+arg_0], rbx
0x18000503d  push    rsi
0x18000503e  push    rdi
0x18000503f  push    r14
0x180005041  sub     rsp, 480h
0x180005048  mov     rax, cs:__security_cookie
0x18000504f  xor     rax, rsp
0x180005052  mov     [rsp+498h+var_28], rax
0x18000505a  mov     r14, r9
0x18000505d  mov     rdi, r8
0x180005060  mov     rax, rdx
0x180005063  xor     ebx, ebx
0x180005065  mov     [rsp+498h+var_440], rbx
0x18000506a  mov     [rsp+498h+var_448], rcx
0x18000506f  mov     [rsp+498h+var_450], rbx
0x180005074  mov     [rsp+498h+var_438], rbx
0x180005079  xor     edx, edx; hFile
0x18000507b  lea     r8d, [rbx+2]; dwFlags
0x18000507f  mov     rcx, rax; lpLibFileName
0x180005082  call    cs:__imp_LoadLibraryExW
0x180005088  mov     rsi, rax
0x18000508b  mov     [rsp+498h+var_460], rax
0x180005090  test    rax, rax
0x180005093  jnz     short loc_1800050A1
0x180005095  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000509a  mov     ebx, eax
0x18000509c  jmp     loc_1800051CB
0x1800050a1  xor     r9d, r9d; wLanguage
0x1800050a4  mov     r8, rdi; lpName
0x1800050a7  mov     rdx, r14; lpType
0x1800050aa  mov     rcx, rsi; hModule
0x1800050ad  call    cs:__imp_FindResourceExW
0x1800050b3  mov     rdi, rax
0x1800050b6  test    rax, rax
0x1800050b9  jnz     short loc_1800050C5
0x1800050bb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800050c0  jmp     loc_1800051BF
0x1800050c5  mov     rdx, rdi; hResInfo
0x1800050c8  mov     rcx, rsi; hModule
0x1800050cb  call    cs:__imp_LoadResource
0x1800050d1  mov     r14, rax
0x1800050d4  mov     [rsp+498h+var_458], rax
0x1800050d9  test    rax, rax
0x1800050dc  jz      short loc_1800050BB
0x1800050de  mov     rdx, rdi; hResInfo
0x1800050e1  mov     rcx, rsi; hModule
0x1800050e4  call    cs:__imp_SizeofResource
0x1800050ea  mov     edi, eax
0x1800050ec  mov     [rsp+498h+var_468], eax
0x1800050f0  inc     eax
0x1800050f2  cmp     eax, edi
0x1800050f4  jnb     short loc_180005117
0x1800050f6  lea     rax, [rsp+498h+var_430]
0x1800050fb  cmp     [rsp+498h+var_438], rax
0x180005100  jz      short loc_18000510D
0x180005102  lea     rcx, [rsp+498h+var_438]
0x180005107  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000510c  nop
0x18000510d  mov     eax, 8007000Eh
0x180005112  jmp     loc_1800051E4
0x180005117  test    eax, eax
0x180005119  jz      short loc_18000514E
0x18000511b  mov     ecx, eax
0x18000511d  xor     edx, edx
0x18000511f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005123  div     rcx
0x180005126  cmp     rax, 2
0x18000512a  jb      loc_180005208
0x180005130  lea     rdx, [rcx+rcx]
0x180005134  cmp     rdx, 400h
0x18000513b  jbe     short loc_18000514E
0x18000513d  lea     rcx, [rsp+498h+var_438]
0x180005142  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005147  mov     rax, [rsp+498h+var_438]
0x18000514c  jmp     short loc_180005158
0x18000514e  lea     rax, [rsp+498h+var_430]
0x180005153  mov     [rsp+498h+var_438], rax
0x180005158  jmp     short loc_18000516F
0x18000515a  xor     ebx, ebx
0x18000515c  mov     rsi, [rsp+498h+var_460]
0x180005161  mov     r14, [rsp+498h+var_458]
0x180005166  mov     edi, [rsp+498h+var_468]
0x18000516a  mov     rax, [rsp+498h+var_438]
0x18000516f  test    rax, rax
0x180005172  jnz     short loc_18000517B
0x180005174  mov     ebx, 8007000Eh
0x180005179  jmp     short loc_1800051C1
0x18000517b  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000517f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180005184  mov     r9d, edi; cbMultiByte
0x180005187  mov     r8, r14; lpMultiByteStr
0x18000518a  xor     edx, edx; dwFlags
0x18000518c  lea     ecx, [rdx+3]; CodePage
0x18000518f  call    cs:__imp_MultiByteToWideChar
0x180005195  test    eax, eax
0x180005197  jz      loc_1800050BB
0x18000519d  mov     ecx, eax
0x18000519f  mov     rax, [rsp+498h+var_438]
0x1800051a4  mov     [rax+rcx*2], bx
0x1800051a8  mov     r8d, [rsp+498h+arg_20]; int
0x1800051b0  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800051b5  lea     rcx, [rsp+498h+var_450]; this
0x1800051ba  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800051bf  mov     ebx, eax
0x1800051c1  mov     rcx, rsi; hLibModule
0x1800051c4  call    cs:__imp_FreeLibrary
0x1800051ca  nop
0x1800051cb  lea     rax, [rsp+498h+var_430]
0x1800051d0  cmp     [rsp+498h+var_438], rax
0x1800051d5  jz      short loc_1800051E2
0x1800051d7  lea     rcx, [rsp+498h+var_438]
0x1800051dc  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800051e1  nop
0x1800051e2  mov     eax, ebx
0x1800051e4  mov     rcx, [rsp+498h+var_28]
0x1800051ec  xor     rcx, rsp; StackCookie
0x1800051ef  call    __security_check_cookie
0x1800051f4  mov     rbx, [rsp+498h+arg_0]
0x1800051fc  add     rsp, 480h
0x180005203  pop     r14
0x180005205  pop     rdi
0x180005206  pop     rsi
0x180005207  retn
0x180005208  mov     ecx, 80070057h; int
0x18000520d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
