# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000b1f4`
- end: `0x18000b39c`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `__int64 __fastcall(const wchar_t *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000bfac`
- `0x18000c224`

## callees

- `0x18000873c`
- `0x18000882c`
- `0x180008948`
- `0x180009484`
- `0x1800096f4`
- `0x18000b05c`
- `0x18000b1f4`
- `0x18001a5e0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x18000b269`
- `KERNEL32!FindResourceExW` at `0x18000b269`
- `KERNEL32!LoadResource` at `0x18000b287`
- `KERNEL32!LoadResource` at `0x18000b287`
- `KERNEL32!SizeofResource` at `0x18000b2a0`
- `KERNEL32!SizeofResource` at `0x18000b2a0`
- `KERNEL32!LoadLibraryExW` at `0x18000b23e`
- `KERNEL32!LoadLibraryExW` at `0x18000b23e`
- `KERNEL32!FreeLibrary` at `0x18000b35a`
- `KERNEL32!FreeLibrary` at `0x18000b35a`
- `KERNEL32!MultiByteToWideChar` at `0x18000b325`
- `KERNEL32!MultiByteToWideChar` at `0x18000b325`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const wchar_t *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rsi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  _QWORD *v20; // [rsp+48h] [rbp-450h] BYREF
  const wchar_t *v21[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v22; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20 = 0;
  v21[1] = this;
  v21[0] = 0;
  v22 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
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
    try
    {
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v15 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v23;
        v22 = (LPWSTR)v23;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
        lpWideCharStr = v22;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v22;
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
      v22[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer(v21, v22, a5);
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x18000b1f4  mov     [rsp+arg_0], rbx
0x18000b1f9  push    rsi
0x18000b1fa  push    rdi
0x18000b1fb  push    r14
0x18000b1fd  sub     rsp, 480h
0x18000b204  mov     rax, cs:__security_cookie
0x18000b20b  xor     rax, rsp
0x18000b20e  mov     [rsp+498h+var_28], rax
0x18000b216  mov     r14, r9
0x18000b219  mov     rdi, r8
0x18000b21c  mov     rax, rdx
0x18000b21f  xor     ebx, ebx
0x18000b221  mov     [rsp+498h+var_450], rbx
0x18000b226  mov     [rsp+498h+var_440], rcx
0x18000b22b  mov     [rsp+498h+var_448], rbx
0x18000b230  mov     [rsp+498h+var_438], rbx
0x18000b235  xor     edx, edx; hFile
0x18000b237  lea     r8d, [rbx+2]; dwFlags
0x18000b23b  mov     rcx, rax; lpLibFileName
0x18000b23e  call    cs:__imp_LoadLibraryExW
0x18000b244  mov     rsi, rax
0x18000b247  mov     [rsp+498h+var_460], rax
0x18000b24c  test    rax, rax
0x18000b24f  jnz     short loc_18000B25D
0x18000b251  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b256  mov     ebx, eax
0x18000b258  jmp     loc_18000B361
0x18000b25d  xor     r9d, r9d; wLanguage
0x18000b260  mov     r8, rdi; lpName
0x18000b263  mov     rdx, r14; lpType
0x18000b266  mov     rcx, rsi; hModule
0x18000b269  call    cs:__imp_FindResourceExW
0x18000b26f  mov     rdi, rax
0x18000b272  test    rax, rax
0x18000b275  jnz     short loc_18000B281
0x18000b277  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b27c  jmp     loc_18000B355
0x18000b281  mov     rdx, rdi; hResInfo
0x18000b284  mov     rcx, rsi; hModule
0x18000b287  call    cs:__imp_LoadResource
0x18000b28d  mov     r14, rax
0x18000b290  mov     [rsp+498h+var_458], rax
0x18000b295  test    rax, rax
0x18000b298  jz      short loc_18000B277
0x18000b29a  mov     rdx, rdi; hResInfo
0x18000b29d  mov     rcx, rsi; hModule
0x18000b2a0  call    cs:__imp_SizeofResource
0x18000b2a6  mov     edi, eax
0x18000b2a8  mov     [rsp+498h+var_468], eax
0x18000b2ac  inc     eax
0x18000b2ae  cmp     eax, edi
0x18000b2b0  jnb     short loc_18000B2BC
0x18000b2b2  mov     ebx, 8007000Eh
0x18000b2b7  jmp     loc_18000B361
0x18000b2bc  mov     ecx, eax
0x18000b2be  mov     edx, 2
0x18000b2c3  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000b2c8  cmp     rax, 400h
0x18000b2ce  jbe     short loc_18000B2E4
0x18000b2d0  mov     rdx, rax
0x18000b2d3  lea     rcx, [rsp+498h+var_438]
0x18000b2d8  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000b2dd  mov     rax, [rsp+498h+var_438]
0x18000b2e2  jmp     short loc_18000B2EE
0x18000b2e4  lea     rax, [rsp+498h+var_430]
0x18000b2e9  mov     [rsp+498h+var_438], rax
0x18000b2ee  jmp     short loc_18000B305
0x18000b2f0  xor     ebx, ebx
0x18000b2f2  mov     rsi, [rsp+498h+var_460]
0x18000b2f7  mov     r14, [rsp+498h+var_458]
0x18000b2fc  mov     edi, [rsp+498h+var_468]
0x18000b300  mov     rax, [rsp+498h+var_438]
0x18000b305  test    rax, rax
0x18000b308  jnz     short loc_18000B311
0x18000b30a  mov     ebx, 8007000Eh
0x18000b30f  jmp     short loc_18000B357
0x18000b311  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000b315  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000b31a  mov     r9d, edi; cbMultiByte
0x18000b31d  mov     r8, r14; lpMultiByteStr
0x18000b320  xor     edx, edx; dwFlags
0x18000b322  lea     ecx, [rdx+3]; CodePage
0x18000b325  call    cs:__imp_MultiByteToWideChar
0x18000b32b  test    eax, eax
0x18000b32d  jz      loc_18000B277
0x18000b333  mov     ecx, eax
0x18000b335  mov     rax, [rsp+498h+var_438]
0x18000b33a  mov     [rax+rcx*2], bx
0x18000b33e  mov     r8d, [rsp+498h+arg_20]; int
0x18000b346  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18000b34b  lea     rcx, [rsp+498h+var_448]; this
0x18000b350  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000b355  mov     ebx, eax
0x18000b357  mov     rcx, rsi; hLibModule
0x18000b35a  call    cs:__imp_FreeLibrary
0x18000b360  nop
0x18000b361  lea     rcx, [rsp+498h+var_438]
0x18000b366  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000b36b  nop
0x18000b36c  lea     rcx, [rsp+498h+var_450]
0x18000b371  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b376  mov     eax, ebx
0x18000b378  mov     rcx, [rsp+498h+var_28]
0x18000b380  xor     rcx, rsp; StackCookie
0x18000b383  call    __security_check_cookie
0x18000b388  mov     rbx, [rsp+498h+arg_0]
0x18000b390  add     rsp, 480h
0x18000b397  pop     r14
0x18000b399  pop     rdi
0x18000b39a  pop     rsi
0x18000b39b  retn
```
