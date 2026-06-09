# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004d18`
- end: `0x180004ef4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180005b1c`
- `0x180005e3c`

## callees

- `0x180002ed8`
- `0x180003114`
- `0x1800039a4`
- `0x180004184`
- `0x180004b88`
- `0x180004d18`
- `0x18000dd10`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004ea4`
- `KERNEL32!FreeLibrary` at `0x180004ea4`
- `KERNEL32!LoadLibraryExW` at `0x180004d62`
- `KERNEL32!LoadLibraryExW` at `0x180004d62`
- `KERNEL32!MultiByteToWideChar` at `0x180004e6f`
- `KERNEL32!MultiByteToWideChar` at `0x180004e6f`
- `KERNEL32!SizeofResource` at `0x180004dc4`
- `KERNEL32!SizeofResource` at `0x180004dc4`
- `KERNEL32!LoadResource` at `0x180004dab`
- `KERNEL32!LoadResource` at `0x180004dab`
- `KERNEL32!FindResourceExW` at `0x180004d8d`
- `KERNEL32!FindResourceExW` at `0x180004d8d`

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
0x180004d18  mov     [rsp+arg_0], rbx
0x180004d1d  push    rsi
0x180004d1e  push    rdi
0x180004d1f  push    r14
0x180004d21  sub     rsp, 480h
0x180004d28  mov     rax, cs:__security_cookie
0x180004d2f  xor     rax, rsp
0x180004d32  mov     [rsp+498h+var_28], rax
0x180004d3a  mov     r14, r9
0x180004d3d  mov     rdi, r8
0x180004d40  mov     rax, rdx
0x180004d43  xor     ebx, ebx
0x180004d45  mov     [rsp+498h+var_440], rbx
0x180004d4a  mov     [rsp+498h+var_448], rcx
0x180004d4f  mov     [rsp+498h+var_450], rbx
0x180004d54  mov     [rsp+498h+var_438], rbx
0x180004d59  xor     edx, edx; hFile
0x180004d5b  lea     r8d, [rbx+2]; dwFlags
0x180004d5f  mov     rcx, rax; lpLibFileName
0x180004d62  call    cs:__imp_LoadLibraryExW
0x180004d68  mov     rsi, rax
0x180004d6b  mov     [rsp+498h+var_460], rax
0x180004d70  test    rax, rax
0x180004d73  jnz     short loc_180004D81
0x180004d75  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004d7a  mov     ebx, eax
0x180004d7c  jmp     loc_180004EAB
0x180004d81  xor     r9d, r9d; wLanguage
0x180004d84  mov     r8, rdi; lpName
0x180004d87  mov     rdx, r14; lpType
0x180004d8a  mov     rcx, rsi; hModule
0x180004d8d  call    cs:__imp_FindResourceExW
0x180004d93  mov     rdi, rax
0x180004d96  test    rax, rax
0x180004d99  jnz     short loc_180004DA5
0x180004d9b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004da0  jmp     loc_180004E9F
0x180004da5  mov     rdx, rdi; hResInfo
0x180004da8  mov     rcx, rsi; hModule
0x180004dab  call    cs:__imp_LoadResource
0x180004db1  mov     r14, rax
0x180004db4  mov     [rsp+498h+var_458], rax
0x180004db9  test    rax, rax
0x180004dbc  jz      short loc_180004D9B
0x180004dbe  mov     rdx, rdi; hResInfo
0x180004dc1  mov     rcx, rsi; hModule
0x180004dc4  call    cs:__imp_SizeofResource
0x180004dca  mov     edi, eax
0x180004dcc  mov     [rsp+498h+var_468], eax
0x180004dd0  inc     eax
0x180004dd2  cmp     eax, edi
0x180004dd4  jnb     short loc_180004DF7
0x180004dd6  lea     rax, [rsp+498h+var_430]
0x180004ddb  cmp     [rsp+498h+var_438], rax
0x180004de0  jz      short loc_180004DED
0x180004de2  lea     rcx, [rsp+498h+var_438]
0x180004de7  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004dec  nop
0x180004ded  mov     eax, 8007000Eh
0x180004df2  jmp     loc_180004EC4
0x180004df7  test    eax, eax
0x180004df9  jz      short loc_180004E2E
0x180004dfb  mov     ecx, eax
0x180004dfd  xor     edx, edx
0x180004dff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004e03  div     rcx
0x180004e06  cmp     rax, 2
0x180004e0a  jb      loc_180004EE8
0x180004e10  lea     rdx, [rcx+rcx]
0x180004e14  cmp     rdx, 400h
0x180004e1b  jbe     short loc_180004E2E
0x180004e1d  lea     rcx, [rsp+498h+var_438]
0x180004e22  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004e27  mov     rax, [rsp+498h+var_438]
0x180004e2c  jmp     short loc_180004E38
0x180004e2e  lea     rax, [rsp+498h+var_430]
0x180004e33  mov     [rsp+498h+var_438], rax
0x180004e38  jmp     short loc_180004E4F
0x180004e3a  xor     ebx, ebx
0x180004e3c  mov     rsi, [rsp+498h+var_460]
0x180004e41  mov     r14, [rsp+498h+var_458]
0x180004e46  mov     edi, [rsp+498h+var_468]
0x180004e4a  mov     rax, [rsp+498h+var_438]
0x180004e4f  test    rax, rax
0x180004e52  jnz     short loc_180004E5B
0x180004e54  mov     ebx, 8007000Eh
0x180004e59  jmp     short loc_180004EA1
0x180004e5b  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180004e5f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180004e64  mov     r9d, edi; cbMultiByte
0x180004e67  mov     r8, r14; lpMultiByteStr
0x180004e6a  xor     edx, edx; dwFlags
0x180004e6c  lea     ecx, [rdx+3]; CodePage
0x180004e6f  call    cs:__imp_MultiByteToWideChar
0x180004e75  test    eax, eax
0x180004e77  jz      loc_180004D9B
0x180004e7d  mov     ecx, eax
0x180004e7f  mov     rax, [rsp+498h+var_438]
0x180004e84  mov     [rax+rcx*2], bx
0x180004e88  mov     r8d, [rsp+498h+arg_20]; int
0x180004e90  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180004e95  lea     rcx, [rsp+498h+var_450]; this
0x180004e9a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004e9f  mov     ebx, eax
0x180004ea1  mov     rcx, rsi; hLibModule
0x180004ea4  call    cs:__imp_FreeLibrary
0x180004eaa  nop
0x180004eab  lea     rax, [rsp+498h+var_430]
0x180004eb0  cmp     [rsp+498h+var_438], rax
0x180004eb5  jz      short loc_180004EC2
0x180004eb7  lea     rcx, [rsp+498h+var_438]
0x180004ebc  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004ec1  nop
0x180004ec2  mov     eax, ebx
0x180004ec4  mov     rcx, [rsp+498h+var_28]
0x180004ecc  xor     rcx, rsp; StackCookie
0x180004ecf  call    __security_check_cookie
0x180004ed4  mov     rbx, [rsp+498h+arg_0]
0x180004edc  add     rsp, 480h
0x180004ee3  pop     r14
0x180004ee5  pop     rdi
0x180004ee6  pop     rsi
0x180004ee7  retn
0x180004ee8  mov     ecx, 80070057h; int
0x180004eed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
