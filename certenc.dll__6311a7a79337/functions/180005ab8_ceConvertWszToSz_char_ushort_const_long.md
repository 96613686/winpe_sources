# ceConvertWszToSz(char * *,ushort const *,long)

- ea: `0x180005ab8`
- end: `0x180005b65`
- name: `?ceConvertWszToSz@@YAHPEAPEADPEBGJ@Z`
- size: `173`
- prototype: `int(char **, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032e0`
- `0x18000662c`
- `0x180006760`
- `0x1800081f0`

## callees

- `0x180005ab8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005af6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b48`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180005b2e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180005b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b3a`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180005ace`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180005b07`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180005ace`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180005b07`

## pseudocode

```c
__int64 __fastcall ceConvertWszToSz(HLOCAL *a1, const unsigned __int16 *a2)
{
  unsigned int v2; // edi
  UINT ACP; // eax
  int i; // eax
  char *v7; // rax
  CHAR *lpMultiByteStr; // rsi
  UINT v9; // eax
  int cbMultiByte; // ebp

  v2 = 0;
  *a1 = 0;
  ACP = GetACP();
  for ( i = WideCharToMultiByte(ACP, 0x400u, a2, -1, 0, 0, 0, 0);
        ;
        i = WideCharToMultiByte(v9, 0x400u, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    cbMultiByte = i;
    if ( i <= 0 )
      break;
    if ( *a1 )
      return 1;
    v7 = (char *)LocalAlloc(0, i + 1);
    *a1 = v7;
    lpMultiByteStr = v7;
    if ( !v7 )
      return v2;
    v9 = GetACP();
  }
  GetLastError();
  if ( *a1 )
  {
    LocalFree(*a1);
    *a1 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180005ab8  push    rbx
0x180005aba  push    rbp
0x180005abb  push    rsi
0x180005abc  push    rdi
0x180005abd  push    r14
0x180005abf  sub     rsp, 40h
0x180005ac3  xor     edi, edi
0x180005ac5  mov     r14, rdx
0x180005ac8  mov     [rcx], rdi
0x180005acb  mov     rbx, rcx
0x180005ace  call    cs:__imp_GetACP
0x180005ad4  mov     [rsp+68h+lpUsedDefaultChar], rdi
0x180005ad9  mov     [rsp+68h+lpDefaultChar], rdi
0x180005ade  mov     [rsp+68h+cbMultiByte], edi
0x180005ae2  mov     [rsp+68h+lpMultiByteStr], rdi
0x180005ae7  jmp     short loc_180005B20
0x180005ae9  cmp     [rbx], rdi
0x180005aec  jnz     short loc_180005B5E
0x180005aee  lea     eax, [rbp+1]
0x180005af1  xor     ecx, ecx; uFlags
0x180005af3  movsxd  rdx, eax; uBytes
0x180005af6  call    cs:__imp_LocalAlloc
0x180005afc  mov     [rbx], rax
0x180005aff  mov     rsi, rax
0x180005b02  test    rax, rax
0x180005b05  jz      short loc_180005B51
0x180005b07  call    cs:__imp_GetACP
0x180005b0d  mov     [rsp+68h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180005b12  mov     [rsp+68h+lpDefaultChar], rdi; lpDefaultChar
0x180005b17  mov     [rsp+68h+cbMultiByte], ebp; cbMultiByte
0x180005b1b  mov     [rsp+68h+lpMultiByteStr], rsi; lpMultiByteStr
0x180005b20  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005b24  mov     r8, r14; lpWideCharStr
0x180005b27  mov     edx, 400h; dwFlags
0x180005b2c  mov     ecx, eax; CodePage
0x180005b2e  call    cs:__imp_WideCharToMultiByte
0x180005b34  mov     ebp, eax
0x180005b36  test    eax, eax
0x180005b38  jg      short loc_180005AE9
0x180005b3a  call    cs:__imp_GetLastError
0x180005b40  mov     rcx, [rbx]; hMem
0x180005b43  test    rcx, rcx
0x180005b46  jz      short loc_180005B51
0x180005b48  call    cs:__imp_LocalFree
0x180005b4e  mov     [rbx], rdi
0x180005b51  mov     eax, edi
0x180005b53  add     rsp, 40h
0x180005b57  pop     r14
0x180005b59  pop     rdi
0x180005b5a  pop     rsi
0x180005b5b  pop     rbp
0x180005b5c  pop     rbx
0x180005b5d  retn
0x180005b5e  mov     edi, 1
0x180005b63  jmp     short loc_180005B51
```
