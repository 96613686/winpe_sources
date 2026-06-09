# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004cf0`
- end: `0x180004eef`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `511`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000596c`

## callees

- `0x1800036f8`
- `0x18000383c`
- `0x18000418c`
- `0x1800043bc`
- `0x180004b4c`
- `0x180004cf0`
- `0x18000df10`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004e98`
- `KERNEL32!FreeLibrary` at `0x180004e98`
- `KERNEL32!LoadLibraryExW` at `0x180004d37`
- `KERNEL32!LoadLibraryExW` at `0x180004d37`
- `KERNEL32!MultiByteToWideChar` at `0x180004e5d`
- `KERNEL32!MultiByteToWideChar` at `0x180004e5d`
- `KERNEL32!SizeofResource` at `0x180004dac`
- `KERNEL32!SizeofResource` at `0x180004dac`
- `KERNEL32!LoadResource` at `0x180004d8d`
- `KERNEL32!LoadResource` at `0x180004d8d`
- `KERNEL32!FindResourceExW` at `0x180004d69`
- `KERNEL32!FindResourceExW` at `0x180004d69`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
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
  LPCWSTR v19[3]; // [rsp+48h] [rbp-450h] BYREF
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
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
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
      v11 = ATL::CRegParser::RegisterBuffer(v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004cf0  mov     [rsp+arg_0], rbx
0x180004cf5  push    rsi
0x180004cf6  push    rdi
0x180004cf7  push    r14
0x180004cf9  sub     rsp, 480h
0x180004d00  mov     rax, cs:__security_cookie
0x180004d07  xor     rax, rsp
0x180004d0a  mov     [rsp+498h+var_28], rax
0x180004d12  mov     rsi, r9
0x180004d15  mov     rax, rdx
0x180004d18  xor     ebx, ebx
0x180004d1a  mov     [rsp+498h+var_440], rbx
0x180004d1f  mov     [rsp+498h+var_448], rcx
0x180004d24  mov     [rsp+498h+var_450], rbx
0x180004d29  mov     [rsp+498h+var_438], rbx
0x180004d2e  xor     edx, edx; hFile
0x180004d30  lea     r8d, [rbx+2]; dwFlags
0x180004d34  mov     rcx, rax; lpLibFileName
0x180004d37  call    cs:__imp_LoadLibraryExW
0x180004d3e  nop     dword ptr [rax+rax+00h]
0x180004d43  mov     rdi, rax
0x180004d46  mov     [rsp+498h+var_460], rax
0x180004d4b  test    rax, rax
0x180004d4e  jnz     short loc_180004D5C
0x180004d50  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004d55  mov     ebx, eax
0x180004d57  jmp     loc_180004EA5
0x180004d5c  xor     r9d, r9d; wLanguage
0x180004d5f  lea     r8d, [r9+65h]; lpName
0x180004d63  mov     rdx, rsi; lpType
0x180004d66  mov     rcx, rdi; hModule
0x180004d69  call    cs:__imp_FindResourceExW
0x180004d70  nop     dword ptr [rax+rax+00h]
0x180004d75  mov     rsi, rax
0x180004d78  test    rax, rax
0x180004d7b  jnz     short loc_180004D87
0x180004d7d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004d82  jmp     loc_180004E93
0x180004d87  mov     rdx, rsi; hResInfo
0x180004d8a  mov     rcx, rdi; hModule
0x180004d8d  call    cs:__imp_LoadResource
0x180004d94  nop     dword ptr [rax+rax+00h]
0x180004d99  mov     r14, rax
0x180004d9c  mov     [rsp+498h+var_458], rax
0x180004da1  test    rax, rax
0x180004da4  jz      short loc_180004D7D
0x180004da6  mov     rdx, rsi; hResInfo
0x180004da9  mov     rcx, rdi; hModule
0x180004dac  call    cs:__imp_SizeofResource
0x180004db3  nop     dword ptr [rax+rax+00h]
0x180004db8  mov     esi, eax
0x180004dba  mov     [rsp+498h+var_468], eax
0x180004dbe  inc     eax
0x180004dc0  cmp     eax, esi
0x180004dc2  jnb     short loc_180004DE5
0x180004dc4  lea     rax, [rsp+498h+var_430]
0x180004dc9  cmp     [rsp+498h+var_438], rax
0x180004dce  jz      short loc_180004DDB
0x180004dd0  lea     rcx, [rsp+498h+var_438]
0x180004dd5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004dda  nop
0x180004ddb  mov     eax, 8007000Eh
0x180004de0  jmp     loc_180004EBE
0x180004de5  test    eax, eax
0x180004de7  jz      short loc_180004E1C
0x180004de9  mov     ecx, eax
0x180004deb  xor     edx, edx
0x180004ded  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004df1  div     rcx
0x180004df4  cmp     rax, 2
0x180004df8  jb      loc_180004EE3
0x180004dfe  lea     rdx, [rcx+rcx]
0x180004e02  cmp     rdx, 400h
0x180004e09  jbe     short loc_180004E1C
0x180004e0b  lea     rcx, [rsp+498h+var_438]
0x180004e10  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004e15  mov     rax, [rsp+498h+var_438]
0x180004e1a  jmp     short loc_180004E26
0x180004e1c  lea     rax, [rsp+498h+var_430]
0x180004e21  mov     [rsp+498h+var_438], rax
0x180004e26  jmp     short loc_180004E3D
0x180004e28  xor     ebx, ebx
0x180004e2a  mov     rdi, [rsp+498h+var_460]
0x180004e2f  mov     r14, [rsp+498h+var_458]
0x180004e34  mov     esi, [rsp+498h+var_468]
0x180004e38  mov     rax, [rsp+498h+var_438]
0x180004e3d  test    rax, rax
0x180004e40  jnz     short loc_180004E49
0x180004e42  mov     ebx, 8007000Eh
0x180004e47  jmp     short loc_180004E95
0x180004e49  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180004e4d  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180004e52  mov     r9d, esi; cbMultiByte
0x180004e55  mov     r8, r14; lpMultiByteStr
0x180004e58  xor     edx, edx; dwFlags
0x180004e5a  lea     ecx, [rdx+3]; CodePage
0x180004e5d  call    cs:__imp_MultiByteToWideChar
0x180004e64  nop     dword ptr [rax+rax+00h]
0x180004e69  test    eax, eax
0x180004e6b  jz      loc_180004D7D
0x180004e71  mov     ecx, eax
0x180004e73  mov     rax, [rsp+498h+var_438]
0x180004e78  mov     [rax+rcx*2], bx
0x180004e7c  mov     r8d, [rsp+498h+arg_20]; int
0x180004e84  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180004e89  lea     rcx, [rsp+498h+var_450]; this
0x180004e8e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004e93  mov     ebx, eax
0x180004e95  mov     rcx, rdi; hLibModule
0x180004e98  call    cs:__imp_FreeLibrary
0x180004e9f  nop     dword ptr [rax+rax+00h]
0x180004ea4  nop
0x180004ea5  lea     rax, [rsp+498h+var_430]
0x180004eaa  cmp     [rsp+498h+var_438], rax
0x180004eaf  jz      short loc_180004EBC
0x180004eb1  lea     rcx, [rsp+498h+var_438]
0x180004eb6  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004ebb  nop
0x180004ebc  mov     eax, ebx
0x180004ebe  mov     rcx, [rsp+498h+var_28]
0x180004ec6  xor     rcx, rsp; StackCookie
0x180004ec9  call    __security_check_cookie
0x180004ece  mov     rbx, [rsp+498h+arg_0]
0x180004ed6  add     rsp, 480h
0x180004edd  pop     r14
0x180004edf  pop     rdi
0x180004ee0  pop     rsi
0x180004ee1  retn
0x180004ee3  mov     ecx, 80070057h; int
0x180004ee8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
