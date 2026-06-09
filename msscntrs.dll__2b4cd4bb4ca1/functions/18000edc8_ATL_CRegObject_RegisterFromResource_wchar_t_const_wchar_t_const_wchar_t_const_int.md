# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x18000edc8`
- end: `0x18000efa4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(const WCHAR *this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000ffec`
- `0x180010314`

## callees

- `0x1800024a0`
- `0x18000c308`
- `0x18000c3f8`
- `0x18000c434`
- `0x18000c974`
- `0x18000ec38`
- `0x18000edc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000ee3d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000ee3d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ef54`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ef54`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000ee74`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000ee74`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ee12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ee12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000ee5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000ee5b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ef1f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ef1f`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
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
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
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
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, 2LL * v15);
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
    ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000edc8  mov     [rsp+arg_0], rbx
0x18000edcd  push    rsi
0x18000edce  push    rdi
0x18000edcf  push    r14
0x18000edd1  sub     rsp, 480h
0x18000edd8  mov     rax, cs:__security_cookie
0x18000eddf  xor     rax, rsp
0x18000ede2  mov     [rsp+498h+var_28], rax
0x18000edea  mov     r14, r9
0x18000eded  mov     rdi, r8
0x18000edf0  mov     rax, rdx
0x18000edf3  xor     ebx, ebx
0x18000edf5  mov     [rsp+498h+var_440], rbx
0x18000edfa  mov     [rsp+498h+var_448], rcx
0x18000edff  mov     [rsp+498h+var_450], rbx
0x18000ee04  mov     [rsp+498h+var_438], rbx
0x18000ee09  xor     edx, edx; hFile
0x18000ee0b  lea     r8d, [rbx+2]; dwFlags
0x18000ee0f  mov     rcx, rax; lpLibFileName
0x18000ee12  call    cs:__imp_LoadLibraryExW
0x18000ee18  mov     rsi, rax
0x18000ee1b  mov     [rsp+498h+var_460], rax
0x18000ee20  test    rax, rax
0x18000ee23  jnz     short loc_18000EE31
0x18000ee25  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000ee2a  mov     ebx, eax
0x18000ee2c  jmp     loc_18000EF5B
0x18000ee31  xor     r9d, r9d; wLanguage
0x18000ee34  mov     r8, rdi; lpName
0x18000ee37  mov     rdx, r14; lpType
0x18000ee3a  mov     rcx, rsi; hModule
0x18000ee3d  call    cs:__imp_FindResourceExW
0x18000ee43  mov     rdi, rax
0x18000ee46  test    rax, rax
0x18000ee49  jnz     short loc_18000EE55
0x18000ee4b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000ee50  jmp     loc_18000EF4F
0x18000ee55  mov     rdx, rdi; hResInfo
0x18000ee58  mov     rcx, rsi; hModule
0x18000ee5b  call    cs:__imp_LoadResource
0x18000ee61  mov     r14, rax
0x18000ee64  mov     [rsp+498h+var_458], rax
0x18000ee69  test    rax, rax
0x18000ee6c  jz      short loc_18000EE4B
0x18000ee6e  mov     rdx, rdi; hResInfo
0x18000ee71  mov     rcx, rsi; hModule
0x18000ee74  call    cs:__imp_SizeofResource
0x18000ee7a  mov     edi, eax
0x18000ee7c  mov     [rsp+498h+var_468], eax
0x18000ee80  inc     eax
0x18000ee82  cmp     eax, edi
0x18000ee84  jnb     short loc_18000EEA7
0x18000ee86  lea     rax, [rsp+498h+var_430]
0x18000ee8b  cmp     [rsp+498h+var_438], rax
0x18000ee90  jz      short loc_18000EE9D
0x18000ee92  lea     rcx, [rsp+498h+var_438]
0x18000ee97  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18000ee9c  nop
0x18000ee9d  mov     eax, 8007000Eh
0x18000eea2  jmp     loc_18000EF74
0x18000eea7  test    eax, eax
0x18000eea9  jz      short loc_18000EEDE
0x18000eeab  mov     ecx, eax
0x18000eead  xor     edx, edx
0x18000eeaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000eeb3  div     rcx
0x18000eeb6  cmp     rax, 2
0x18000eeba  jb      loc_18000EF98
0x18000eec0  lea     rdx, [rcx+rcx]
0x18000eec4  cmp     rdx, 400h
0x18000eecb  jbe     short loc_18000EEDE
0x18000eecd  lea     rcx, [rsp+498h+var_438]
0x18000eed2  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000eed7  mov     rax, [rsp+498h+var_438]
0x18000eedc  jmp     short loc_18000EEE8
0x18000eede  lea     rax, [rsp+498h+var_430]
0x18000eee3  mov     [rsp+498h+var_438], rax
0x18000eee8  jmp     short loc_18000EEFF
0x18000eeea  xor     ebx, ebx
0x18000eeec  mov     rsi, [rsp+498h+var_460]
0x18000eef1  mov     r14, [rsp+498h+var_458]
0x18000eef6  mov     edi, [rsp+498h+var_468]
0x18000eefa  mov     rax, [rsp+498h+var_438]
0x18000eeff  test    rax, rax
0x18000ef02  jnz     short loc_18000EF0B
0x18000ef04  mov     ebx, 8007000Eh
0x18000ef09  jmp     short loc_18000EF51
0x18000ef0b  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000ef0f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000ef14  mov     r9d, edi; cbMultiByte
0x18000ef17  mov     r8, r14; lpMultiByteStr
0x18000ef1a  xor     edx, edx; dwFlags
0x18000ef1c  lea     ecx, [rdx+3]; CodePage
0x18000ef1f  call    cs:__imp_MultiByteToWideChar
0x18000ef25  test    eax, eax
0x18000ef27  jz      loc_18000EE4B
0x18000ef2d  mov     ecx, eax
0x18000ef2f  mov     rax, [rsp+498h+var_438]
0x18000ef34  mov     [rax+rcx*2], bx
0x18000ef38  mov     r8d, [rsp+498h+arg_20]; int
0x18000ef40  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x18000ef45  lea     rcx, [rsp+498h+var_450]; this
0x18000ef4a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18000ef4f  mov     ebx, eax
0x18000ef51  mov     rcx, rsi; hLibModule
0x18000ef54  call    cs:__imp_FreeLibrary
0x18000ef5a  nop
0x18000ef5b  lea     rax, [rsp+498h+var_430]
0x18000ef60  cmp     [rsp+498h+var_438], rax
0x18000ef65  jz      short loc_18000EF72
0x18000ef67  lea     rcx, [rsp+498h+var_438]
0x18000ef6c  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18000ef71  nop
0x18000ef72  mov     eax, ebx
0x18000ef74  mov     rcx, [rsp+498h+var_28]
0x18000ef7c  xor     rcx, rsp; StackCookie
0x18000ef7f  call    __security_check_cookie
0x18000ef84  mov     rbx, [rsp+498h+arg_0]
0x18000ef8c  add     rsp, 480h
0x18000ef93  pop     r14
0x18000ef95  pop     rdi
0x18000ef96  pop     rsi
0x18000ef97  retn
0x18000ef98  mov     ecx, 80070057h; int
0x18000ef9d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
