# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180008c0c`
- end: `0x180008dc7`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000a7ac`
- `0x18000aacc`

## callees

- `0x180004818`
- `0x180004a54`
- `0x180004a90`
- `0x1800059c8`
- `0x180008a7c`
- `0x180008c0c`
- `0x180018500`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180008d46`
- `KERNEL32!MultiByteToWideChar` at `0x180008d46`
- `KERNEL32!FindResourceExW` at `0x180008c83`
- `KERNEL32!FindResourceExW` at `0x180008c83`
- `KERNEL32!LoadResource` at `0x180008ca1`
- `KERNEL32!LoadResource` at `0x180008ca1`
- `KERNEL32!FreeLibrary` at `0x180008d7c`
- `KERNEL32!FreeLibrary` at `0x180008d7c`
- `KERNEL32!LoadLibraryExW` at `0x180008c5d`
- `KERNEL32!LoadLibraryExW` at `0x180008c5d`
- `KERNEL32!SizeofResource` at `0x180008cb5`
- `KERNEL32!SizeofResource` at `0x180008cb5`

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
  HMODULE v8; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  __int64 v15; // rcx
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  LPCWSTR v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[1032]; // [rsp+48h] [rbp-B8h] BYREF

  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
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
  if ( (unsigned int)v15 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_14;
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v15 < 2 )
      ATL::AtlThrowImpl(-2147024809);
    if ( (unsigned __int64)(2 * v15) <= 0x400 )
    {
LABEL_14:
      lpWideCharStr = (WCHAR *)v21;
      v20 = (LPWSTR)v21;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2 * v15);
      lpWideCharStr = v20;
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
      v20[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer(v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180008c0c  mov     [rsp-8+arg_0], rbx
0x180008c11  push    rbp
0x180008c12  push    rsi
0x180008c13  push    rdi
0x180008c14  lea     rbp, [rsp-360h]
0x180008c1c  sub     rsp, 460h
0x180008c23  mov     rax, cs:__security_cookie
0x180008c2a  xor     rax, rsp
0x180008c2d  mov     [rbp+370h+var_20], rax
0x180008c34  mov     rax, rdx
0x180008c37  mov     [rsp+470h+var_438], rcx
0x180008c3c  xor     edx, edx; hFile
0x180008c3e  mov     [rsp+470h+var_440], 0
0x180008c47  mov     rbx, r8
0x180008c4a  mov     [rsp+470h+var_430], 0
0x180008c53  mov     rcx, rax; lpLibFileName
0x180008c56  mov     rsi, r9
0x180008c59  lea     r8d, [rdx+2]; dwFlags
0x180008c5d  call    cs:__imp_LoadLibraryExW
0x180008c63  mov     rdi, rax
0x180008c66  test    rax, rax
0x180008c69  jnz     short loc_180008C77
0x180008c6b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008c70  mov     ebx, eax
0x180008c72  jmp     loc_180008D82
0x180008c77  xor     r9d, r9d; wLanguage
0x180008c7a  mov     r8, rbx; lpName
0x180008c7d  mov     rdx, rsi; lpType
0x180008c80  mov     rcx, rdi; hModule
0x180008c83  call    cs:__imp_FindResourceExW
0x180008c89  mov     rbx, rax
0x180008c8c  test    rax, rax
0x180008c8f  jnz     short loc_180008C9B
0x180008c91  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008c96  jmp     loc_180008D77
0x180008c9b  mov     rdx, rbx; hResInfo
0x180008c9e  mov     rcx, rdi; hModule
0x180008ca1  call    cs:__imp_LoadResource
0x180008ca7  mov     rsi, rax
0x180008caa  test    rax, rax
0x180008cad  jz      short loc_180008C91
0x180008caf  mov     rdx, rbx; hResInfo
0x180008cb2  mov     rcx, rdi; hModule
0x180008cb5  call    cs:__imp_SizeofResource
0x180008cbb  mov     ebx, eax
0x180008cbd  lea     ecx, [rax+1]
0x180008cc0  cmp     ecx, eax
0x180008cc2  jnb     short loc_180008CE4
0x180008cc4  lea     rax, [rsp+470h+var_428]
0x180008cc9  cmp     [rsp+470h+var_430], rax
0x180008cce  jz      short loc_180008CDA
0x180008cd0  lea     rcx, [rsp+470h+var_430]
0x180008cd5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180008cda  mov     eax, 8007000Eh
0x180008cdf  jmp     loc_180008D9A
0x180008ce4  test    ecx, ecx
0x180008ce6  jz      short loc_180008D1C
0x180008ce8  xor     edx, edx
0x180008cea  mov     r8d, ecx
0x180008ced  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008cf1  div     r8
0x180008cf4  cmp     rax, 2
0x180008cf8  jb      loc_180008DBC
0x180008cfe  lea     rdx, [rcx+rcx]
0x180008d02  cmp     rdx, 400h
0x180008d09  jbe     short loc_180008D1C
0x180008d0b  lea     rcx, [rsp+470h+var_430]
0x180008d10  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180008d15  mov     rax, [rsp+470h+var_430]
0x180008d1a  jmp     short loc_180008D26
0x180008d1c  lea     rax, [rsp+470h+var_428]
0x180008d21  mov     [rsp+470h+var_430], rax
0x180008d26  test    rax, rax
0x180008d29  jnz     short loc_180008D32
0x180008d2b  mov     ebx, 8007000Eh
0x180008d30  jmp     short loc_180008D79
0x180008d32  xor     edx, edx; dwFlags
0x180008d34  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x180008d38  mov     r9d, ebx; cbMultiByte
0x180008d3b  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x180008d40  mov     r8, rsi; lpMultiByteStr
0x180008d43  lea     ecx, [rdx+3]; CodePage
0x180008d46  call    cs:__imp_MultiByteToWideChar
0x180008d4c  test    eax, eax
0x180008d4e  jz      loc_180008C91
0x180008d54  mov     r8d, [rbp+370h+arg_20]; int
0x180008d5b  xor     ecx, ecx
0x180008d5d  mov     edx, eax
0x180008d5f  mov     rax, [rsp+470h+var_430]
0x180008d64  mov     [rax+rdx*2], cx
0x180008d68  lea     rcx, [rsp+470h+var_440]; this
0x180008d6d  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x180008d72  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180008d77  mov     ebx, eax
0x180008d79  mov     rcx, rdi; hLibModule
0x180008d7c  call    cs:__imp_FreeLibrary
0x180008d82  lea     rax, [rsp+470h+var_428]
0x180008d87  cmp     [rsp+470h+var_430], rax
0x180008d8c  jz      short loc_180008D98
0x180008d8e  lea     rcx, [rsp+470h+var_430]
0x180008d93  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180008d98  mov     eax, ebx
0x180008d9a  mov     rcx, [rbp+370h+var_20]
0x180008da1  xor     rcx, rsp; StackCookie
0x180008da4  call    __security_check_cookie
0x180008da9  mov     rbx, [rsp+470h+arg_0]
0x180008db1  add     rsp, 460h
0x180008db8  pop     rdi
0x180008db9  pop     rsi
0x180008dba  pop     rbp
0x180008dbb  retn
0x180008dbc  mov     ecx, 80070057h; int
0x180008dc1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
