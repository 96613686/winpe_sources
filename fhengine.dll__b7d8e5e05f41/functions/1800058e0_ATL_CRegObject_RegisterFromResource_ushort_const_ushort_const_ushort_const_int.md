# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800058e0`
- end: `0x180005a88`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `__int64 __fastcall(const wchar_t *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180006664`

## callees

- `0x180002ba8`
- `0x180002f64`
- `0x18000324c`
- `0x180004074`
- `0x1800041d0`
- `0x18000576c`
- `0x1800058e0`
- `0x180031680`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x18000598c`
- `KERNEL32!SizeofResource` at `0x18000598c`
- `KERNEL32!MultiByteToWideChar` at `0x180005a11`
- `KERNEL32!MultiByteToWideChar` at `0x180005a11`
- `KERNEL32!FindResourceExW` at `0x180005955`
- `KERNEL32!FindResourceExW` at `0x180005955`
- `KERNEL32!LoadResource` at `0x180005973`
- `KERNEL32!LoadResource` at `0x180005973`
- `KERNEL32!FreeLibrary` at `0x180005a46`
- `KERNEL32!FreeLibrary` at `0x180005a46`
- `KERNEL32!LoadLibraryExW` at `0x18000592a`
- `KERNEL32!LoadLibraryExW` at `0x18000592a`

## pseudocode

```c
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
  __int64 v20; // [rsp+48h] [rbp-450h] BYREF
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
0x1800058e0  mov     [rsp+arg_0], rbx
0x1800058e5  push    rsi
0x1800058e6  push    rdi
0x1800058e7  push    r14
0x1800058e9  sub     rsp, 480h
0x1800058f0  mov     rax, cs:__security_cookie
0x1800058f7  xor     rax, rsp
0x1800058fa  mov     [rsp+498h+var_28], rax
0x180005902  mov     r14, r9
0x180005905  mov     rdi, r8
0x180005908  mov     rax, rdx
0x18000590b  xor     ebx, ebx
0x18000590d  mov     [rsp+498h+var_450], rbx
0x180005912  mov     [rsp+498h+var_440], rcx
0x180005917  mov     [rsp+498h+var_448], rbx
0x18000591c  mov     [rsp+498h+var_438], rbx
0x180005921  xor     edx, edx; hFile
0x180005923  lea     r8d, [rbx+2]; dwFlags
0x180005927  mov     rcx, rax; lpLibFileName
0x18000592a  call    cs:__imp_LoadLibraryExW
0x180005930  mov     rsi, rax
0x180005933  mov     [rsp+498h+var_460], rax
0x180005938  test    rax, rax
0x18000593b  jnz     short loc_180005949
0x18000593d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005942  mov     ebx, eax
0x180005944  jmp     loc_180005A4D
0x180005949  xor     r9d, r9d; wLanguage
0x18000594c  mov     r8, rdi; lpName
0x18000594f  mov     rdx, r14; lpType
0x180005952  mov     rcx, rsi; hModule
0x180005955  call    cs:__imp_FindResourceExW
0x18000595b  mov     rdi, rax
0x18000595e  test    rax, rax
0x180005961  jnz     short loc_18000596D
0x180005963  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005968  jmp     loc_180005A41
0x18000596d  mov     rdx, rdi; hResInfo
0x180005970  mov     rcx, rsi; hModule
0x180005973  call    cs:__imp_LoadResource
0x180005979  mov     r14, rax
0x18000597c  mov     [rsp+498h+var_458], rax
0x180005981  test    rax, rax
0x180005984  jz      short loc_180005963
0x180005986  mov     rdx, rdi; hResInfo
0x180005989  mov     rcx, rsi; hModule
0x18000598c  call    cs:__imp_SizeofResource
0x180005992  mov     edi, eax
0x180005994  mov     [rsp+498h+var_468], eax
0x180005998  inc     eax
0x18000599a  cmp     eax, edi
0x18000599c  jnb     short loc_1800059A8
0x18000599e  mov     ebx, 8007000Eh
0x1800059a3  jmp     loc_180005A4D
0x1800059a8  mov     ecx, eax
0x1800059aa  mov     edx, 2
0x1800059af  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800059b4  cmp     rax, 400h
0x1800059ba  jbe     short loc_1800059D0
0x1800059bc  mov     rdx, rax
0x1800059bf  lea     rcx, [rsp+498h+var_438]
0x1800059c4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800059c9  mov     rax, [rsp+498h+var_438]
0x1800059ce  jmp     short loc_1800059DA
0x1800059d0  lea     rax, [rsp+498h+var_430]
0x1800059d5  mov     [rsp+498h+var_438], rax
0x1800059da  jmp     short loc_1800059F1
0x1800059dc  xor     ebx, ebx
0x1800059de  mov     rsi, [rsp+498h+var_460]
0x1800059e3  mov     r14, [rsp+498h+var_458]
0x1800059e8  mov     edi, [rsp+498h+var_468]
0x1800059ec  mov     rax, [rsp+498h+var_438]
0x1800059f1  test    rax, rax
0x1800059f4  jnz     short loc_1800059FD
0x1800059f6  mov     ebx, 8007000Eh
0x1800059fb  jmp     short loc_180005A43
0x1800059fd  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180005a01  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180005a06  mov     r9d, edi; cbMultiByte
0x180005a09  mov     r8, r14; lpMultiByteStr
0x180005a0c  xor     edx, edx; dwFlags
0x180005a0e  lea     ecx, [rdx+3]; CodePage
0x180005a11  call    cs:__imp_MultiByteToWideChar
0x180005a17  test    eax, eax
0x180005a19  jz      loc_180005963
0x180005a1f  mov     ecx, eax
0x180005a21  mov     rax, [rsp+498h+var_438]
0x180005a26  mov     [rax+rcx*2], bx
0x180005a2a  mov     r8d, [rsp+498h+arg_20]; int
0x180005a32  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180005a37  lea     rcx, [rsp+498h+var_448]; this
0x180005a3c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180005a41  mov     ebx, eax
0x180005a43  mov     rcx, rsi; hLibModule
0x180005a46  call    cs:__imp_FreeLibrary
0x180005a4c  nop
0x180005a4d  lea     rcx, [rsp+498h+var_438]
0x180005a52  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180005a57  nop
0x180005a58  lea     rcx, [rsp+498h+var_450]
0x180005a5d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005a62  mov     eax, ebx
0x180005a64  mov     rcx, [rsp+498h+var_28]
0x180005a6c  xor     rcx, rsp; StackCookie
0x180005a6f  call    __security_check_cookie
0x180005a74  mov     rbx, [rsp+498h+arg_0]
0x180005a7c  add     rsp, 480h
0x180005a83  pop     r14
0x180005a85  pop     rdi
0x180005a86  pop     rsi
0x180005a87  retn
```
