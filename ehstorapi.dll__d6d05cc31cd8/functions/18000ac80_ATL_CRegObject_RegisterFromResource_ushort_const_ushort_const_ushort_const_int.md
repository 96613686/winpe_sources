# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000ac80`
- end: `0x18000ae28`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000b7bc`
- `0x18000ba34`

## callees

- `0x180008bb8`
- `0x180008bf4`
- `0x180008cd0`
- `0x180009724`
- `0x180009948`
- `0x18000ab0c`
- `0x18000ac80`
- `0x18000c4f0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x18000acf5`
- `KERNEL32!FindResourceExW` at `0x18000acf5`
- `KERNEL32!LoadResource` at `0x18000ad13`
- `KERNEL32!LoadResource` at `0x18000ad13`
- `KERNEL32!SizeofResource` at `0x18000ad2c`
- `KERNEL32!SizeofResource` at `0x18000ad2c`
- `KERNEL32!MultiByteToWideChar` at `0x18000adb1`
- `KERNEL32!MultiByteToWideChar` at `0x18000adb1`
- `KERNEL32!FreeLibrary` at `0x18000ade6`
- `KERNEL32!FreeLibrary` at `0x18000ade6`
- `KERNEL32!LoadLibraryExW` at `0x18000acca`
- `KERNEL32!LoadLibraryExW` at `0x18000acca`

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
0x18000ac80  mov     [rsp+arg_0], rbx
0x18000ac85  push    rsi
0x18000ac86  push    rdi
0x18000ac87  push    r14
0x18000ac89  sub     rsp, 480h
0x18000ac90  mov     rax, cs:__security_cookie
0x18000ac97  xor     rax, rsp
0x18000ac9a  mov     [rsp+498h+var_28], rax
0x18000aca2  mov     r14, r9
0x18000aca5  mov     rdi, r8
0x18000aca8  mov     rax, rdx
0x18000acab  xor     ebx, ebx
0x18000acad  mov     [rsp+498h+var_450], rbx
0x18000acb2  mov     [rsp+498h+var_440], rcx
0x18000acb7  mov     [rsp+498h+var_448], rbx
0x18000acbc  mov     [rsp+498h+var_438], rbx
0x18000acc1  xor     edx, edx; hFile
0x18000acc3  lea     r8d, [rbx+2]; dwFlags
0x18000acc7  mov     rcx, rax; lpLibFileName
0x18000acca  call    cs:__imp_LoadLibraryExW
0x18000acd0  mov     rsi, rax
0x18000acd3  mov     [rsp+498h+var_460], rax
0x18000acd8  test    rax, rax
0x18000acdb  jnz     short loc_18000ACE9
0x18000acdd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000ace2  mov     ebx, eax
0x18000ace4  jmp     loc_18000ADED
0x18000ace9  xor     r9d, r9d; wLanguage
0x18000acec  mov     r8, rdi; lpName
0x18000acef  mov     rdx, r14; lpType
0x18000acf2  mov     rcx, rsi; hModule
0x18000acf5  call    cs:__imp_FindResourceExW
0x18000acfb  mov     rdi, rax
0x18000acfe  test    rax, rax
0x18000ad01  jnz     short loc_18000AD0D
0x18000ad03  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000ad08  jmp     loc_18000ADE1
0x18000ad0d  mov     rdx, rdi; hResInfo
0x18000ad10  mov     rcx, rsi; hModule
0x18000ad13  call    cs:__imp_LoadResource
0x18000ad19  mov     r14, rax
0x18000ad1c  mov     [rsp+498h+var_458], rax
0x18000ad21  test    rax, rax
0x18000ad24  jz      short loc_18000AD03
0x18000ad26  mov     rdx, rdi; hResInfo
0x18000ad29  mov     rcx, rsi; hModule
0x18000ad2c  call    cs:__imp_SizeofResource
0x18000ad32  mov     edi, eax
0x18000ad34  mov     [rsp+498h+var_468], eax
0x18000ad38  inc     eax
0x18000ad3a  cmp     eax, edi
0x18000ad3c  jnb     short loc_18000AD48
0x18000ad3e  mov     ebx, 8007000Eh
0x18000ad43  jmp     loc_18000ADED
0x18000ad48  mov     ecx, eax
0x18000ad4a  mov     edx, 2
0x18000ad4f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000ad54  cmp     rax, 400h
0x18000ad5a  jbe     short loc_18000AD70
0x18000ad5c  mov     rdx, rax
0x18000ad5f  lea     rcx, [rsp+498h+var_438]
0x18000ad64  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000ad69  mov     rax, [rsp+498h+var_438]
0x18000ad6e  jmp     short loc_18000AD7A
0x18000ad70  lea     rax, [rsp+498h+var_430]
0x18000ad75  mov     [rsp+498h+var_438], rax
0x18000ad7a  jmp     short loc_18000AD91
0x18000ad7c  xor     ebx, ebx
0x18000ad7e  mov     rsi, [rsp+498h+var_460]
0x18000ad83  mov     r14, [rsp+498h+var_458]
0x18000ad88  mov     edi, [rsp+498h+var_468]
0x18000ad8c  mov     rax, [rsp+498h+var_438]
0x18000ad91  test    rax, rax
0x18000ad94  jnz     short loc_18000AD9D
0x18000ad96  mov     ebx, 8007000Eh
0x18000ad9b  jmp     short loc_18000ADE3
0x18000ad9d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000ada1  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000ada6  mov     r9d, edi; cbMultiByte
0x18000ada9  mov     r8, r14; lpMultiByteStr
0x18000adac  xor     edx, edx; dwFlags
0x18000adae  lea     ecx, [rdx+3]; CodePage
0x18000adb1  call    cs:__imp_MultiByteToWideChar
0x18000adb7  test    eax, eax
0x18000adb9  jz      loc_18000AD03
0x18000adbf  mov     ecx, eax
0x18000adc1  mov     rax, [rsp+498h+var_438]
0x18000adc6  mov     [rax+rcx*2], bx
0x18000adca  mov     r8d, [rsp+498h+arg_20]; int
0x18000add2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18000add7  lea     rcx, [rsp+498h+var_448]; this
0x18000addc  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000ade1  mov     ebx, eax
0x18000ade3  mov     rcx, rsi; hLibModule
0x18000ade6  call    cs:__imp_FreeLibrary
0x18000adec  nop
0x18000aded  lea     rcx, [rsp+498h+var_438]
0x18000adf2  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000adf7  nop
0x18000adf8  lea     rcx, [rsp+498h+var_450]
0x18000adfd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ae02  mov     eax, ebx
0x18000ae04  mov     rcx, [rsp+498h+var_28]
0x18000ae0c  xor     rcx, rsp; StackCookie
0x18000ae0f  call    __security_check_cookie
0x18000ae14  mov     rbx, [rsp+498h+arg_0]
0x18000ae1c  add     rsp, 480h
0x18000ae23  pop     r14
0x18000ae25  pop     rdi
0x18000ae26  pop     rsi
0x18000ae27  retn
```
