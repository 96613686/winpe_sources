# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004a88`
- end: `0x180004c62`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `474`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180005620`

## callees

- `0x180003688`
- `0x1800037b8`
- `0x180004048`
- `0x180004220`
- `0x1800048f8`
- `0x180004a88`
- `0x180011340`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004acf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004acf`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004b32`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180004b32`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004c12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004c12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004b19`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180004b19`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180004afb`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180004afb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004bdd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004bdd`

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
  _QWORD v19[3]; // [rsp+48h] [rbp-450h] BYREF
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
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
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
      v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004a88  mov     [rsp+arg_0], rbx
0x180004a8d  push    rsi
0x180004a8e  push    rdi
0x180004a8f  push    r14
0x180004a91  sub     rsp, 480h
0x180004a98  mov     rax, cs:__security_cookie
0x180004a9f  xor     rax, rsp
0x180004aa2  mov     [rsp+498h+var_28], rax
0x180004aaa  mov     rsi, r9
0x180004aad  mov     rax, rdx
0x180004ab0  xor     ebx, ebx
0x180004ab2  mov     [rsp+498h+var_440], rbx
0x180004ab7  mov     [rsp+498h+var_448], rcx
0x180004abc  mov     [rsp+498h+var_450], rbx
0x180004ac1  mov     [rsp+498h+var_438], rbx
0x180004ac6  xor     edx, edx; hFile
0x180004ac8  lea     r8d, [rbx+2]; dwFlags
0x180004acc  mov     rcx, rax; lpLibFileName
0x180004acf  call    cs:__imp_LoadLibraryExW
0x180004ad5  mov     rdi, rax
0x180004ad8  mov     [rsp+498h+var_460], rax
0x180004add  test    rax, rax
0x180004ae0  jnz     short loc_180004AEE
0x180004ae2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004ae7  mov     ebx, eax
0x180004ae9  jmp     loc_180004C19
0x180004aee  xor     r9d, r9d; wLanguage
0x180004af1  lea     r8d, [r9+65h]; lpName
0x180004af5  mov     rdx, rsi; lpType
0x180004af8  mov     rcx, rdi; hModule
0x180004afb  call    cs:__imp_FindResourceExW
0x180004b01  mov     rsi, rax
0x180004b04  test    rax, rax
0x180004b07  jnz     short loc_180004B13
0x180004b09  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004b0e  jmp     loc_180004C0D
0x180004b13  mov     rdx, rsi; hResInfo
0x180004b16  mov     rcx, rdi; hModule
0x180004b19  call    cs:__imp_LoadResource
0x180004b1f  mov     r14, rax
0x180004b22  mov     [rsp+498h+var_458], rax
0x180004b27  test    rax, rax
0x180004b2a  jz      short loc_180004B09
0x180004b2c  mov     rdx, rsi; hResInfo
0x180004b2f  mov     rcx, rdi; hModule
0x180004b32  call    cs:__imp_SizeofResource
0x180004b38  mov     esi, eax
0x180004b3a  mov     [rsp+498h+var_468], eax
0x180004b3e  inc     eax
0x180004b40  cmp     eax, esi
0x180004b42  jnb     short loc_180004B65
0x180004b44  lea     rax, [rsp+498h+var_430]
0x180004b49  cmp     [rsp+498h+var_438], rax
0x180004b4e  jz      short loc_180004B5B
0x180004b50  lea     rcx, [rsp+498h+var_438]
0x180004b55  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004b5a  nop
0x180004b5b  mov     eax, 8007000Eh
0x180004b60  jmp     loc_180004C32
0x180004b65  test    eax, eax
0x180004b67  jz      short loc_180004B9C
0x180004b69  mov     ecx, eax
0x180004b6b  xor     edx, edx
0x180004b6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004b71  div     rcx
0x180004b74  cmp     rax, 2
0x180004b78  jb      loc_180004C56
0x180004b7e  lea     rdx, [rcx+rcx]
0x180004b82  cmp     rdx, 400h
0x180004b89  jbe     short loc_180004B9C
0x180004b8b  lea     rcx, [rsp+498h+var_438]
0x180004b90  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004b95  mov     rax, [rsp+498h+var_438]
0x180004b9a  jmp     short loc_180004BA6
0x180004b9c  lea     rax, [rsp+498h+var_430]
0x180004ba1  mov     [rsp+498h+var_438], rax
0x180004ba6  jmp     short loc_180004BBD
0x180004ba8  xor     ebx, ebx
0x180004baa  mov     rdi, [rsp+498h+var_460]
0x180004baf  mov     r14, [rsp+498h+var_458]
0x180004bb4  mov     esi, [rsp+498h+var_468]
0x180004bb8  mov     rax, [rsp+498h+var_438]
0x180004bbd  test    rax, rax
0x180004bc0  jnz     short loc_180004BC9
0x180004bc2  mov     ebx, 8007000Eh
0x180004bc7  jmp     short loc_180004C0F
0x180004bc9  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x180004bcd  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180004bd2  mov     r9d, esi; cbMultiByte
0x180004bd5  mov     r8, r14; lpMultiByteStr
0x180004bd8  xor     edx, edx; dwFlags
0x180004bda  lea     ecx, [rdx+3]; CodePage
0x180004bdd  call    cs:__imp_MultiByteToWideChar
0x180004be3  test    eax, eax
0x180004be5  jz      loc_180004B09
0x180004beb  mov     ecx, eax
0x180004bed  mov     rax, [rsp+498h+var_438]
0x180004bf2  mov     [rax+rcx*2], bx
0x180004bf6  mov     r8d, [rsp+498h+arg_20]; int
0x180004bfe  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180004c03  lea     rcx, [rsp+498h+var_450]; this
0x180004c08  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004c0d  mov     ebx, eax
0x180004c0f  mov     rcx, rdi; hLibModule
0x180004c12  call    cs:__imp_FreeLibrary
0x180004c18  nop
0x180004c19  lea     rax, [rsp+498h+var_430]
0x180004c1e  cmp     [rsp+498h+var_438], rax
0x180004c23  jz      short loc_180004C30
0x180004c25  lea     rcx, [rsp+498h+var_438]
0x180004c2a  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004c2f  nop
0x180004c30  mov     eax, ebx
0x180004c32  mov     rcx, [rsp+498h+var_28]
0x180004c3a  xor     rcx, rsp; StackCookie
0x180004c3d  call    __security_check_cookie
0x180004c42  mov     rbx, [rsp+498h+arg_0]
0x180004c4a  add     rsp, 480h
0x180004c51  pop     r14
0x180004c53  pop     rdi
0x180004c54  pop     rsi
0x180004c55  retn
0x180004c56  mov     ecx, 80070057h; int
0x180004c5b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
