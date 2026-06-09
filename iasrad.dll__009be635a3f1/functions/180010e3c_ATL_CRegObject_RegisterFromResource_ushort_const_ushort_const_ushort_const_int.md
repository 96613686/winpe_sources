# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180010e3c`
- end: `0x180010fe4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180011e4c`
- `0x1800120c4`

## callees

- `0x18000adb0`
- `0x18000e150`
- `0x18000e3bc`
- `0x18000ee48`
- `0x18000f178`
- `0x180010ccc`
- `0x180010e3c`
- `0x18002e230`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180010f6d`
- `KERNEL32!MultiByteToWideChar` at `0x180010f6d`
- `KERNEL32!FreeLibrary` at `0x180010fa2`
- `KERNEL32!FreeLibrary` at `0x180010fa2`
- `KERNEL32!LoadLibraryExW` at `0x180010e86`
- `KERNEL32!LoadLibraryExW` at `0x180010e86`
- `KERNEL32!SizeofResource` at `0x180010ee8`
- `KERNEL32!SizeofResource` at `0x180010ee8`
- `KERNEL32!LoadResource` at `0x180010ecf`
- `KERNEL32!LoadResource` at `0x180010ecf`
- `KERNEL32!FindResourceExW` at `0x180010eb1`
- `KERNEL32!FindResourceExW` at `0x180010eb1`

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
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  __int64 v20; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-448h] BYREF
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
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
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
0x180010e3c  mov     [rsp+arg_0], rbx
0x180010e41  push    rsi
0x180010e42  push    rdi
0x180010e43  push    r14
0x180010e45  sub     rsp, 480h
0x180010e4c  mov     rax, cs:__security_cookie
0x180010e53  xor     rax, rsp
0x180010e56  mov     [rsp+498h+var_28], rax
0x180010e5e  mov     r14, r9
0x180010e61  mov     rdi, r8
0x180010e64  mov     rax, rdx
0x180010e67  xor     ebx, ebx
0x180010e69  mov     [rsp+498h+var_450], rbx
0x180010e6e  mov     [rsp+498h+var_440], rcx
0x180010e73  mov     [rsp+498h+var_448], rbx
0x180010e78  mov     [rsp+498h+var_438], rbx
0x180010e7d  xor     edx, edx; hFile
0x180010e7f  lea     r8d, [rbx+2]; dwFlags
0x180010e83  mov     rcx, rax; lpLibFileName
0x180010e86  call    cs:__imp_LoadLibraryExW
0x180010e8c  mov     rsi, rax
0x180010e8f  mov     [rsp+498h+var_460], rax
0x180010e94  test    rax, rax
0x180010e97  jnz     short loc_180010EA5
0x180010e99  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010e9e  mov     ebx, eax
0x180010ea0  jmp     loc_180010FA9
0x180010ea5  xor     r9d, r9d; wLanguage
0x180010ea8  mov     r8, rdi; lpName
0x180010eab  mov     rdx, r14; lpType
0x180010eae  mov     rcx, rsi; hModule
0x180010eb1  call    cs:__imp_FindResourceExW
0x180010eb7  mov     rdi, rax
0x180010eba  test    rax, rax
0x180010ebd  jnz     short loc_180010EC9
0x180010ebf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010ec4  jmp     loc_180010F9D
0x180010ec9  mov     rdx, rdi; hResInfo
0x180010ecc  mov     rcx, rsi; hModule
0x180010ecf  call    cs:__imp_LoadResource
0x180010ed5  mov     r14, rax
0x180010ed8  mov     [rsp+498h+var_458], rax
0x180010edd  test    rax, rax
0x180010ee0  jz      short loc_180010EBF
0x180010ee2  mov     rdx, rdi; hResInfo
0x180010ee5  mov     rcx, rsi; hModule
0x180010ee8  call    cs:__imp_SizeofResource
0x180010eee  mov     edi, eax
0x180010ef0  mov     [rsp+498h+var_468], eax
0x180010ef4  inc     eax
0x180010ef6  cmp     eax, edi
0x180010ef8  jnb     short loc_180010F04
0x180010efa  mov     ebx, 8007000Eh
0x180010eff  jmp     loc_180010FA9
0x180010f04  mov     ecx, eax
0x180010f06  mov     edx, 2
0x180010f0b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180010f10  cmp     rax, 400h
0x180010f16  jbe     short loc_180010F2C
0x180010f18  mov     rdx, rax
0x180010f1b  lea     rcx, [rsp+498h+var_438]
0x180010f20  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180010f25  mov     rax, [rsp+498h+var_438]
0x180010f2a  jmp     short loc_180010F36
0x180010f2c  lea     rax, [rsp+498h+var_430]
0x180010f31  mov     [rsp+498h+var_438], rax
0x180010f36  jmp     short loc_180010F4D
0x180010f38  xor     ebx, ebx
0x180010f3a  mov     rsi, [rsp+498h+var_460]
0x180010f3f  mov     r14, [rsp+498h+var_458]
0x180010f44  mov     edi, [rsp+498h+var_468]
0x180010f48  mov     rax, [rsp+498h+var_438]
0x180010f4d  test    rax, rax
0x180010f50  jnz     short loc_180010F59
0x180010f52  mov     ebx, 8007000Eh
0x180010f57  jmp     short loc_180010F9F
0x180010f59  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180010f5d  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180010f62  mov     r9d, edi; cbMultiByte
0x180010f65  mov     r8, r14; lpMultiByteStr
0x180010f68  xor     edx, edx; dwFlags
0x180010f6a  lea     ecx, [rdx+3]; CodePage
0x180010f6d  call    cs:__imp_MultiByteToWideChar
0x180010f73  test    eax, eax
0x180010f75  jz      loc_180010EBF
0x180010f7b  mov     ecx, eax
0x180010f7d  mov     rax, [rsp+498h+var_438]
0x180010f82  mov     [rax+rcx*2], bx
0x180010f86  mov     r8d, [rsp+498h+arg_20]; int
0x180010f8e  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180010f93  lea     rcx, [rsp+498h+var_448]; this
0x180010f98  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180010f9d  mov     ebx, eax
0x180010f9f  mov     rcx, rsi; hLibModule
0x180010fa2  call    cs:__imp_FreeLibrary
0x180010fa8  nop
0x180010fa9  lea     rcx, [rsp+498h+var_438]
0x180010fae  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180010fb3  nop
0x180010fb4  lea     rcx, [rsp+498h+var_450]
0x180010fb9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010fbe  mov     eax, ebx
0x180010fc0  mov     rcx, [rsp+498h+var_28]
0x180010fc8  xor     rcx, rsp; StackCookie
0x180010fcb  call    __security_check_cookie
0x180010fd0  mov     rbx, [rsp+498h+arg_0]
0x180010fd8  add     rsp, 480h
0x180010fdf  pop     r14
0x180010fe1  pop     rdi
0x180010fe2  pop     rsi
0x180010fe3  retn
```
