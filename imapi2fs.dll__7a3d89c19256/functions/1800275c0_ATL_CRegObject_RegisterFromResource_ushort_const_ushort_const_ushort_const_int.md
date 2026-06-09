# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800275c0`
- end: `0x180027752`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `402`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180028050`

## callees

- `0x180019034`
- `0x1800258f8`
- `0x180025934`
- `0x1800259b0`
- `0x1800261f4`
- `0x18002744c`
- `0x1800275c0`
- `0x180081750`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002761a`
- `KERNEL32!LoadLibraryExW` at `0x18002761a`
- `KERNEL32!FreeLibrary` at `0x180027712`
- `KERNEL32!FreeLibrary` at `0x180027712`
- `KERNEL32!LoadResource` at `0x18002765e`
- `KERNEL32!LoadResource` at `0x18002765e`
- `KERNEL32!FindResourceExW` at `0x180027640`
- `KERNEL32!FindResourceExW` at `0x180027640`
- `KERNEL32!MultiByteToWideChar` at `0x1800276dc`
- `KERNEL32!MultiByteToWideChar` at `0x1800276dc`
- `KERNEL32!SizeofResource` at `0x180027672`
- `KERNEL32!SizeofResource` at `0x180027672`

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
  HMODULE v8; // rdi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int Error; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[1032]; // [rsp+58h] [rbp-A8h] BYREF

  v19 = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v11 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v13 = (const CHAR *)LoadResource(v8, Resource);
    if ( !v13 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v11);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v9 = -2147024882;
      goto LABEL_17;
    }
    v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
    if ( v15 <= 0x400 )
    {
      lpWideCharStr = (WCHAR *)v22;
      v21 = (LPWSTR)v22;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, v15);
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v21[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned short,10,ATL::CCRTAllocator>::~CTempBuffer<unsigned short,10,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x1800275c0  mov     [rsp-8+arg_0], rbx
0x1800275c5  push    rbp
0x1800275c6  push    rsi
0x1800275c7  push    rdi
0x1800275c8  lea     rbp, [rsp-370h]
0x1800275d0  sub     rsp, 470h
0x1800275d7  mov     rax, cs:__security_cookie
0x1800275de  xor     rax, rsp
0x1800275e1  mov     [rbp+380h+var_20], rax
0x1800275e8  mov     rsi, r9
0x1800275eb  mov     rbx, r8
0x1800275ee  mov     rax, rdx
0x1800275f1  mov     [rsp+480h+var_450], 0
0x1800275fa  mov     [rsp+480h+var_440], rcx
0x1800275ff  mov     [rsp+480h+var_448], 0
0x180027608  mov     [rsp+480h+var_430], 0
0x180027611  xor     edx, edx; hFile
0x180027613  lea     r8d, [rdx+2]; dwFlags
0x180027617  mov     rcx, rax; lpLibFileName
0x18002761a  call    cs:__imp_LoadLibraryExW
0x180027620  mov     rdi, rax
0x180027623  test    rax, rax
0x180027626  jnz     short loc_180027634
0x180027628  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002762d  mov     ebx, eax
0x18002762f  jmp     loc_180027719
0x180027634  xor     r9d, r9d; wLanguage
0x180027637  mov     r8, rbx; lpName
0x18002763a  mov     rdx, rsi; lpType
0x18002763d  mov     rcx, rdi; hModule
0x180027640  call    cs:__imp_FindResourceExW
0x180027646  mov     rbx, rax
0x180027649  test    rax, rax
0x18002764c  jnz     short loc_180027658
0x18002764e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027653  jmp     loc_18002770D
0x180027658  mov     rdx, rbx; hResInfo
0x18002765b  mov     rcx, rdi; hModule
0x18002765e  call    cs:__imp_LoadResource
0x180027664  mov     rsi, rax
0x180027667  test    rax, rax
0x18002766a  jz      short loc_18002764E
0x18002766c  mov     rdx, rbx; hResInfo
0x18002766f  mov     rcx, rdi; hModule
0x180027672  call    cs:__imp_SizeofResource
0x180027678  mov     ebx, eax
0x18002767a  inc     eax
0x18002767c  cmp     eax, ebx
0x18002767e  jnb     short loc_18002768A
0x180027680  mov     ebx, 8007000Eh
0x180027685  jmp     loc_180027719
0x18002768a  mov     ecx, eax
0x18002768c  mov     edx, 2
0x180027691  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180027696  cmp     rax, 400h
0x18002769c  jbe     short loc_1800276B2
0x18002769e  mov     rdx, rax
0x1800276a1  lea     rcx, [rsp+480h+var_430]
0x1800276a6  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800276ab  mov     rax, [rsp+480h+var_430]
0x1800276b0  jmp     short loc_1800276BC
0x1800276b2  lea     rax, [rsp+480h+var_428]
0x1800276b7  mov     [rsp+480h+var_430], rax
0x1800276bc  test    rax, rax
0x1800276bf  jnz     short loc_1800276C8
0x1800276c1  mov     ebx, 8007000Eh
0x1800276c6  jmp     short loc_18002770F
0x1800276c8  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x1800276cc  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x1800276d1  mov     r9d, ebx; cbMultiByte
0x1800276d4  mov     r8, rsi; lpMultiByteStr
0x1800276d7  xor     edx, edx; dwFlags
0x1800276d9  lea     ecx, [rdx+3]; CodePage
0x1800276dc  call    cs:__imp_MultiByteToWideChar
0x1800276e2  test    eax, eax
0x1800276e4  jz      loc_18002764E
0x1800276ea  mov     edx, eax
0x1800276ec  xor     ecx, ecx
0x1800276ee  mov     rax, [rsp+480h+var_430]
0x1800276f3  mov     [rax+rdx*2], cx
0x1800276f7  mov     r8d, [rbp+380h+arg_20]; int
0x1800276fe  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x180027703  lea     rcx, [rsp+480h+var_448]; this
0x180027708  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18002770d  mov     ebx, eax
0x18002770f  mov     rcx, rdi; hLibModule
0x180027712  call    cs:__imp_FreeLibrary
0x180027718  nop
0x180027719  lea     rcx, [rsp+480h+var_430]
0x18002771e  call    ??1?$CTempBuffer@G$09VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,10,ATL::CCRTAllocator>::~CTempBuffer<ushort,10,ATL::CCRTAllocator>(void)
0x180027723  nop
0x180027724  lea     rcx, [rsp+480h+var_450]
0x180027729  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002772e  mov     eax, ebx
0x180027730  mov     rcx, [rbp+380h+var_20]
0x180027737  xor     rcx, rsp; StackCookie
0x18002773a  call    __security_check_cookie
0x18002773f  mov     rbx, [rsp+480h+arg_0]
0x180027747  add     rsp, 470h
0x18002774e  pop     rdi
0x18002774f  pop     rsi
0x180027750  pop     rbp
0x180027751  retn
```
