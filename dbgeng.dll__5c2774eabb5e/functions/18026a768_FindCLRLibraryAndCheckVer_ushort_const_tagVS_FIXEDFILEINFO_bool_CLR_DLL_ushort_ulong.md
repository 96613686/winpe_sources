# FindCLRLibraryAndCheckVer(ushort const *,tagVS_FIXEDFILEINFO *,bool,CLR_DLL,ushort *,ulong)

- ea: `0x18026a768`
- end: `0x18026a9f5`
- name: `?FindCLRLibraryAndCheckVer@@YAJPEBGPEAUtagVS_FIXEDFILEINFO@@_NW4CLR_DLL@@PEAGK@Z`
- size: `653`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18026a9fc`
- `0x18028a5e8`

## callees

- `0x1800793cc`
- `0x180085700`
- `0x1800e8b30`
- `0x18026a768`
- `0x180419c3c`
- `0x18041a5f4`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18026a919`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18026a919`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x18026a872`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x18026a872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a83f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18026a7d8`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18026a804`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18026a7d8`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18026a804`

## string_xrefs

- `0x18026a8a7`: `CLRDLL: Unable to get version info for '%s', %s\n`
- `0x18026a81c`: `CLRDLL: Unable to find '%s' on the path\n`
- `0x18026a9af`: `CLRDLL: %s:%u.%u.%u.%02u f:%x\ndoesn't match desired version %u.%u.%u.%02u f:%x\n`
- `0x18026a909`: `CLRDLL: Unable to query fixed version for '%s'\n`

## pseudocode

```c
__int64 __fastcall FindCLRLibraryAndCheckVer(
        const unsigned __int16 *a1,
        __int64 a2,
        char a3,
        int a4,
        LPWSTR Destination,
        unsigned int a6)
{
  __m128i v7; // xmm6
  const WCHAR *v10; // rdi
  const unsigned __int16 *v11; // rax
  const WCHAR *v12; // rcx
  WCHAR *v13; // rbx
  unsigned int v14; // ebx
  signed int LastError; // eax
  int AllFileVersionInfo; // eax
  unsigned __int16 *v18; // rax
  unsigned int v19; // r15d
  unsigned int v20; // r8d
  unsigned int v21; // ebx
  LPWSTR lpBuffer; // [rsp+28h] [rbp-69h]
  LPWSTR *lpFilePart; // [rsp+30h] [rbp-61h]
  void *v24; // [rsp+68h] [rbp-29h] BYREF
  __int128 v25; // [rsp+80h] [rbp-11h]
  LPWSTR FilePart; // [rsp+E8h] [rbp+57h] BYREF

  v7 = 0;
  v25 = 0;
  v10 = a1;
  v11 = PathTail(a1);
  if ( v11 == v12 )
  {
    v13 = Destination;
    FilePart = 0;
    if ( !SearchPathW(g_SymbolSearchPath, v12, 0, 0x104u, Destination, &FilePart)
      && !SearchPathW(0, v10, 0, 0x104u, v13, &FilePart) )
    {
      if ( a3 )
        ErrOut(L"CLRDLL: Unable to find '%s' on the path\n", v10);
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        return (unsigned int)-2147467259;
      }
      return v14;
    }
    v10 = v13;
  }
  else
  {
    wcscpy_s(Destination, 0x104u, v10);
  }
  FilePart = 0;
  AllFileVersionInfo = GetAllFileVersionInfo(v10, (void **)&FilePart);
  v14 = AllFileVersionInfo;
  if ( AllFileVersionInfo )
  {
    if ( a3 )
    {
      v18 = FormatStatusCode(AllFileVersionInfo);
      ErrOut(L"CLRDLL: Unable to get version info for '%s', %s\n", v10, v18);
    }
    return v14;
  }
  v24 = 0;
  a6 = 0;
  if ( (unsigned int)DbgVerQueryValueW(FilePart, L"\\", &v24, &a6) && a6 == 52 )
  {
    v14 = 0;
    v7 = *(__m128i *)v24;
    v25 = *((_OWORD *)v24 + 1);
  }
  else
  {
    v14 = -2147467259;
    if ( a3 )
      ErrOut(L"CLRDLL: Unable to query fixed version for '%s'\n", v10);
  }
  free(FilePart);
  if ( v14 )
    return v14;
  if ( a4 == 6 )
    return 0;
  v19 = *(_DWORD *)(a2 + 8);
  v20 = _mm_cvtsi128_si32(_mm_srli_si128(v7, 8));
  v21 = _mm_cvtsi128_si32(_mm_srli_si128(v7, 12));
  if ( v20 == v19 && v21 == *(_DWORD *)(a2 + 12) && ((*(_BYTE *)(a2 + 28) ^ BYTE12(v25)) & 0x21) == 0 )
    return 0;
  if ( a3 )
  {
    LODWORD(lpFilePart) = (unsigned __int16)v21;
    LODWORD(lpBuffer) = HIWORD(v21);
    ErrOut(
      L"CLRDLL: %s:%u.%u.%u.%02u f:%x\ndoesn't match desired version %u.%u.%u.%02u f:%x\n",
      v10,
      HIWORD(v20),
      (unsigned __int16)v20,
      lpBuffer,
      lpFilePart,
      HIDWORD(v25),
      HIWORD(v19),
      (unsigned __int16)v19,
      HIWORD(*(_DWORD *)(a2 + 12)),
      (unsigned __int16)*(_DWORD *)(a2 + 12),
      *(_DWORD *)(a2 + 28));
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18026a768  mov     rax, rsp
0x18026a76b  mov     [rax+10h], rbx
0x18026a76f  mov     [rax+18h], rsi
0x18026a773  push    rbp
0x18026a774  push    rdi
0x18026a775  push    r12
0x18026a777  push    r14
0x18026a779  push    r15
0x18026a77b  lea     rbp, [rax-4Fh]
0x18026a77f  sub     rsp, 0B0h
0x18026a786  movaps  xmmword ptr [rax-38h], xmm6
0x18026a78a  mov     r15d, r9d
0x18026a78d  xorps   xmm6, xmm6
0x18026a790  mov     sil, r8b
0x18026a793  movups  [rbp+47h+var_58], xmm6
0x18026a797  mov     r14, rdx
0x18026a79a  mov     rdi, rcx
0x18026a79d  call    ?PathTail@@YAPEBGPEBG@Z; PathTail(ushort const *)
0x18026a7a2  cmp     rax, rcx
0x18026a7a5  jnz     loc_18026A866
0x18026a7ab  mov     rbx, [rbp+47h+Destination]
0x18026a7af  lea     rax, [rbp+47h+FilePart]
0x18026a7b3  mov     rdx, rcx; lpFileName
0x18026a7b6  mov     [rsp+0D0h+lpFilePart], rax; lpFilePart
0x18026a7bb  mov     rcx, cs:?g_SymbolSearchPath@@3PEAGEA; lpPath
0x18026a7c2  mov     r9d, 104h; nBufferLength
0x18026a7c8  xor     r8d, r8d; lpExtension
0x18026a7cb  mov     [rsp+0D0h+lpBuffer], rbx; lpBuffer
0x18026a7d0  mov     [rbp+47h+FilePart], 0
0x18026a7d8  call    cs:__imp_SearchPathW
0x18026a7df  nop     dword ptr [rax+rax+00h]
0x18026a7e4  test    eax, eax
0x18026a7e6  jnz     short loc_18026A861
0x18026a7e8  lea     rax, [rbp+47h+FilePart]
0x18026a7ec  mov     r9d, 104h; nBufferLength
0x18026a7f2  mov     [rsp+0D0h+lpFilePart], rax; lpFilePart
0x18026a7f7  xor     r8d, r8d; lpExtension
0x18026a7fa  mov     rdx, rdi; lpFileName
0x18026a7fd  mov     [rsp+0D0h+lpBuffer], rbx; lpBuffer
0x18026a802  xor     ecx, ecx; lpPath
0x18026a804  call    cs:__imp_SearchPathW
0x18026a80b  nop     dword ptr [rax+rax+00h]
0x18026a810  test    eax, eax
0x18026a812  jnz     short loc_18026A861
0x18026a814  test    sil, sil
0x18026a817  jz      short loc_18026A828
0x18026a819  mov     rdx, rdi
0x18026a81c  lea     rcx, aClrdllUnableTo_2; "CLRDLL: Unable to find '%s' on the path"...
0x18026a823  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18026a828  call    cs:__imp_GetLastError
0x18026a82f  nop     dword ptr [rax+rax+00h]
0x18026a834  test    eax, eax
0x18026a836  jnz     short loc_18026A83F
0x18026a838  mov     ebx, 80004005h
0x18026a83d  jmp     short loc_18026A85A
0x18026a83f  call    cs:__imp_GetLastError
0x18026a846  nop     dword ptr [rax+rax+00h]
0x18026a84b  mov     ebx, eax
0x18026a84d  test    eax, eax
0x18026a84f  jle     short loc_18026A85A
0x18026a851  movzx   ebx, ax
0x18026a854  or      ebx, 80070000h
0x18026a85a  mov     eax, ebx
0x18026a85c  jmp     loc_18026A9D3
0x18026a861  mov     rdi, rbx
0x18026a864  jmp     short loc_18026A87E
0x18026a866  mov     rcx, [rbp+47h+Destination]; Destination
0x18026a86a  mov     r8, rdi; Source
0x18026a86d  mov     edx, 104h; SizeInWords
0x18026a872  call    cs:__imp_wcscpy_s
0x18026a879  nop     dword ptr [rax+rax+00h]
0x18026a87e  lea     rdx, [rbp+47h+FilePart]; void **
0x18026a882  mov     [rbp+47h+FilePart], 0
0x18026a88a  mov     rcx, rdi; unsigned __int16 *
0x18026a88d  call    ?GetAllFileVersionInfo@@YAJPEBGPEAPEAX@Z; GetAllFileVersionInfo(ushort const *,void * *)
0x18026a892  mov     ebx, eax
0x18026a894  test    eax, eax
0x18026a896  jz      short loc_18026A8B8
0x18026a898  test    sil, sil
0x18026a89b  jz      short loc_18026A85A
0x18026a89d  mov     ecx, eax; int
0x18026a89f  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x18026a8a4  mov     r8, rax
0x18026a8a7  lea     rcx, aClrdllUnableTo_1; "CLRDLL: Unable to get version info for "...
0x18026a8ae  mov     rdx, rdi
0x18026a8b1  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18026a8b6  jmp     short loc_18026A85A
0x18026a8b8  mov     rcx, [rbp+47h+FilePart]; void *
0x18026a8bc  lea     r9, [rbp+47h+arg_28]; unsigned int *
0x18026a8c0  lea     r8, [rbp+47h+var_70]; void **
0x18026a8c4  mov     [rbp+47h+var_70], 0
0x18026a8cc  lea     rdx, asc_1805DF320; "\\"
0x18026a8d3  mov     [rbp+47h+arg_28], 0
0x18026a8da  call    ?DbgVerQueryValueW@@YAHPEBXPEBGPEAPEAXPEAI@Z; DbgVerQueryValueW(void const *,ushort const *,void * *,uint *)
0x18026a8df  test    eax, eax
0x18026a8e1  jz      short loc_18026A8FC
0x18026a8e3  cmp     [rbp+47h+arg_28], 34h ; '4'
0x18026a8e7  jnz     short loc_18026A8FC
0x18026a8e9  mov     rax, [rbp+47h+var_70]
0x18026a8ed  xor     ebx, ebx
0x18026a8ef  movups  xmm0, xmmword ptr [rax+10h]
0x18026a8f3  movups  xmm6, xmmword ptr [rax]
0x18026a8f6  movups  [rbp+47h+var_58], xmm0
0x18026a8fa  jmp     short loc_18026A915
0x18026a8fc  mov     ebx, 80004005h
0x18026a901  test    sil, sil
0x18026a904  jz      short loc_18026A915
0x18026a906  mov     rdx, rdi
0x18026a909  lea     rcx, aClrdllUnableTo_0; "CLRDLL: Unable to query fixed version f"...
0x18026a910  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18026a915  mov     rcx, [rbp+47h+FilePart]; Block
0x18026a919  call    cs:__imp_free
0x18026a920  nop     dword ptr [rax+rax+00h]
0x18026a925  test    ebx, ebx
0x18026a927  jnz     loc_18026A85A
0x18026a92d  cmp     r15d, 6
0x18026a931  jz      loc_18026A9D1
0x18026a937  mov     r15d, [r14+8]
0x18026a93b  movdqa  xmm0, xmm6
0x18026a93f  mov     r12d, dword ptr [rbp+47h+var_58+0Ch]
0x18026a943  psrldq  xmm6, 8
0x18026a948  movd    r8d, xmm6
0x18026a94d  psrldq  xmm0, 0Ch
0x18026a952  movd    ebx, xmm0
0x18026a956  cmp     r8d, r15d
0x18026a959  jnz     short loc_18026A96C
0x18026a95b  cmp     ebx, [r14+0Ch]
0x18026a95f  jnz     short loc_18026A96C
0x18026a961  mov     eax, r12d
0x18026a964  xor     eax, [r14+1Ch]
0x18026a968  test    al, 21h
0x18026a96a  jz      short loc_18026A9D1
0x18026a96c  test    sil, sil
0x18026a96f  jz      short loc_18026A9CA
0x18026a971  mov     r11d, [r14+0Ch]
0x18026a975  mov     eax, [r14+1Ch]
0x18026a979  mov     [rsp+0D0h+var_78], eax
0x18026a97d  movzx   r10d, r11w
0x18026a981  mov     [rsp+0D0h+var_80], r10d
0x18026a986  movzx   edx, r15w
0x18026a98a  movzx   ecx, bx
0x18026a98d  shr     r11d, 10h
0x18026a991  mov     [rsp+0D0h+var_88], r11d
0x18026a996  mov     [rsp+0D0h+var_90], edx
0x18026a99a  mov     rdx, rdi
0x18026a99d  shr     r15d, 10h
0x18026a9a1  mov     [rsp+0D0h+var_98], r15d
0x18026a9a6  mov     [rsp+0D0h+var_A0], r12d
0x18026a9ab  mov     dword ptr [rsp+0D0h+lpFilePart], ecx
0x18026a9af  lea     rcx, aClrdllSUUU02uF; "CLRDLL: %s:%u.%u.%u.%02u f:%x\ndoesn't "...
0x18026a9b6  shr     ebx, 10h
0x18026a9b9  movzx   r9d, r8w
0x18026a9bd  shr     r8d, 10h
0x18026a9c1  mov     dword ptr [rsp+0D0h+lpBuffer], ebx
0x18026a9c5  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18026a9ca  mov     eax, 80070057h
0x18026a9cf  jmp     short loc_18026A9D3
0x18026a9d1  xor     eax, eax
0x18026a9d3  lea     r11, [rsp+0D0h+var_20]
0x18026a9db  mov     rbx, [r11+38h]
0x18026a9df  mov     rsi, [r11+40h]
0x18026a9e3  movaps  xmm6, xmmword ptr [r11-10h]
0x18026a9e8  mov     rsp, r11
0x18026a9eb  pop     r15
0x18026a9ed  pop     r14
0x18026a9ef  pop     r12
0x18026a9f1  pop     rdi
0x18026a9f2  pop     rbp
0x18026a9f3  retn
```
