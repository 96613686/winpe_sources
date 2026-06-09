# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180015464`
- end: `0x1800155f4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `400`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180016ce8`

## callees

- `0x18000f970`
- `0x18001086c`
- `0x180010f88`
- `0x180010fd8`
- `0x180011e7c`
- `0x180011fc4`
- `0x1800152f0`
- `0x180015464`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180015580`
- `KERNEL32!MultiByteToWideChar` at `0x180015580`
- `KERNEL32!LoadResource` at `0x180015502`
- `KERNEL32!LoadResource` at `0x180015502`
- `KERNEL32!SizeofResource` at `0x180015516`
- `KERNEL32!SizeofResource` at `0x180015516`
- `KERNEL32!FindResourceExW` at `0x1800154e4`
- `KERNEL32!FindResourceExW` at `0x1800154e4`
- `KERNEL32!LoadLibraryExW` at `0x1800154be`
- `KERNEL32!LoadLibraryExW` at `0x1800154be`
- `KERNEL32!FreeLibrary` at `0x1800155b6`
- `KERNEL32!FreeLibrary` at `0x1800155b6`

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

  v20[1] = this;
  v19 = 0;
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x180015464  mov     [rsp-8+arg_0], rbx
0x180015469  push    rbp
0x18001546a  push    rsi
0x18001546b  push    rdi
0x18001546c  lea     rbp, [rsp-370h]
0x180015474  sub     rsp, 470h
0x18001547b  mov     rax, cs:__security_cookie
0x180015482  xor     rax, rsp
0x180015485  mov     [rbp+380h+var_20], rax
0x18001548c  mov     rax, rdx
0x18001548f  mov     [rsp+480h+var_440], rcx
0x180015494  xor     edx, edx; hFile
0x180015496  mov     [rsp+480h+var_450], 0
0x18001549f  mov     rbx, r8
0x1800154a2  mov     [rsp+480h+var_448], 0
0x1800154ab  mov     rcx, rax; lpLibFileName
0x1800154ae  mov     [rsp+480h+var_430], 0
0x1800154b7  mov     rsi, r9
0x1800154ba  lea     r8d, [rdx+2]; dwFlags
0x1800154be  call    cs:__imp_LoadLibraryExW
0x1800154c4  mov     rdi, rax
0x1800154c7  test    rax, rax
0x1800154ca  jnz     short loc_1800154D8
0x1800154cc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800154d1  mov     ebx, eax
0x1800154d3  jmp     loc_1800155BC
0x1800154d8  xor     r9d, r9d; wLanguage
0x1800154db  mov     r8, rbx; lpName
0x1800154de  mov     rdx, rsi; lpType
0x1800154e1  mov     rcx, rdi; hModule
0x1800154e4  call    cs:__imp_FindResourceExW
0x1800154ea  mov     rbx, rax
0x1800154ed  test    rax, rax
0x1800154f0  jnz     short loc_1800154FC
0x1800154f2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800154f7  jmp     loc_1800155B1
0x1800154fc  mov     rdx, rbx; hResInfo
0x1800154ff  mov     rcx, rdi; hModule
0x180015502  call    cs:__imp_LoadResource
0x180015508  mov     rsi, rax
0x18001550b  test    rax, rax
0x18001550e  jz      short loc_1800154F2
0x180015510  mov     rdx, rbx; hResInfo
0x180015513  mov     rcx, rdi; hModule
0x180015516  call    cs:__imp_SizeofResource
0x18001551c  mov     ebx, eax
0x18001551e  inc     eax
0x180015520  cmp     eax, ebx
0x180015522  jnb     short loc_18001552E
0x180015524  mov     ebx, 8007000Eh
0x180015529  jmp     loc_1800155BC
0x18001552e  mov     ecx, eax
0x180015530  mov     edx, 2
0x180015535  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001553a  cmp     rax, 400h
0x180015540  jbe     short loc_180015556
0x180015542  mov     rdx, rax
0x180015545  lea     rcx, [rsp+480h+var_430]
0x18001554a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001554f  mov     rax, [rsp+480h+var_430]
0x180015554  jmp     short loc_180015560
0x180015556  lea     rax, [rsp+480h+var_428]
0x18001555b  mov     [rsp+480h+var_430], rax
0x180015560  test    rax, rax
0x180015563  jnz     short loc_18001556C
0x180015565  mov     ebx, 8007000Eh
0x18001556a  jmp     short loc_1800155B3
0x18001556c  xor     edx, edx; dwFlags
0x18001556e  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x180015572  mov     r9d, ebx; cbMultiByte
0x180015575  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x18001557a  mov     r8, rsi; lpMultiByteStr
0x18001557d  lea     ecx, [rdx+3]; CodePage
0x180015580  call    cs:__imp_MultiByteToWideChar
0x180015586  test    eax, eax
0x180015588  jz      loc_1800154F2
0x18001558e  mov     r8d, [rbp+380h+arg_20]; int
0x180015595  xor     ecx, ecx
0x180015597  mov     edx, eax
0x180015599  mov     rax, [rsp+480h+var_430]
0x18001559e  mov     [rax+rdx*2], cx
0x1800155a2  lea     rcx, [rsp+480h+var_448]; this
0x1800155a7  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x1800155ac  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800155b1  mov     ebx, eax
0x1800155b3  mov     rcx, rdi; hLibModule
0x1800155b6  call    cs:__imp_FreeLibrary
0x1800155bc  lea     rcx, [rsp+480h+var_430]
0x1800155c1  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800155c6  lea     rcx, [rsp+480h+var_450]
0x1800155cb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800155d0  mov     eax, ebx
0x1800155d2  mov     rcx, [rbp+380h+var_20]
0x1800155d9  xor     rcx, rsp; StackCookie
0x1800155dc  call    __security_check_cookie
0x1800155e1  mov     rbx, [rsp+480h+arg_0]
0x1800155e9  add     rsp, 470h
0x1800155f0  pop     rdi
0x1800155f1  pop     rsi
0x1800155f2  pop     rbp
0x1800155f3  retn
```
