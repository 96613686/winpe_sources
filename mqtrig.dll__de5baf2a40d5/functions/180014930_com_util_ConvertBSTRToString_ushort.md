# _com_util::ConvertBSTRToString(ushort *)

- ea: `0x180014930`
- end: `0x1800149c7`
- name: `?ConvertBSTRToString@_com_util@@YAPEADPEAG@Z`
- size: `151`
- prototype: `char *__fastcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f159`

## callees

- `0x180014920`
- `0x180014930`
- `0x180014ae8`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180014997`
- `KERNEL32!WideCharToMultiByte` at `0x180014997`
- `KERNEL32!GetLastError` at `0x1800149a1`
- `KERNEL32!GetLastError` at `0x1800149a1`

## pseudocode

```c
char *__fastcall _com_util::ConvertBSTRToString(LPCWCH lpWideCharStr)
{
  __int64 v3; // rax
  int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax
  struct IErrorInfo *v6; // rdx
  CHAR *v7; // rdi
  signed int LastError; // eax
  struct IErrorInfo *v9; // rdx

  if ( !lpWideCharStr )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( lpWideCharStr[v3] );
  cbMultiByte = 2 * v3 + 2;
  lpMultiByteStr = (CHAR *)MmAllocate(cbMultiByte);
  v7 = lpMultiByteStr;
  if ( !lpMultiByteStr )
    _com_issue_error(-2147024882, v6);
  *lpMultiByteStr = 0;
  if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    _com_issue_error(LastError, v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180014930  push    rbx
0x180014932  push    rbp
0x180014933  push    rsi
0x180014934  push    rdi
0x180014935  sub     rsp, 48h
0x180014939  xor     ebp, ebp
0x18001493b  mov     rbx, rcx
0x18001493e  test    rcx, rcx
0x180014941  jnz     short loc_180014947
0x180014943  xor     eax, eax
0x180014945  jmp     short loc_1800149BE
0x180014947  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001494b  inc     rax
0x18001494e  cmp     [rcx+rax*2], bp
0x180014952  jnz     short loc_18001494B
0x180014954  lea     esi, ds:2[rax*2]
0x18001495b  movsxd  rcx, esi; unsigned __int64
0x18001495e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014963  mov     rdi, rax
0x180014966  test    rax, rax
0x180014969  jnz     short loc_180014976
0x18001496b  mov     ecx, 8007000Eh; int
0x180014970  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180014976  mov     [rsp+68h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18001497b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001497f  mov     [rsp+68h+lpDefaultChar], rbp; lpDefaultChar
0x180014984  mov     r8, rbx; lpWideCharStr
0x180014987  mov     [rsp+68h+cbMultiByte], esi; cbMultiByte
0x18001498b  xor     edx, edx; dwFlags
0x18001498d  xor     ecx, ecx; CodePage
0x18001498f  mov     [rsp+68h+lpMultiByteStr], rdi; lpMultiByteStr
0x180014994  mov     [rax], bpl
0x180014997  call    cs:__imp_WideCharToMultiByte
0x18001499d  test    eax, eax
0x18001499f  jnz     short loc_1800149BB
0x1800149a1  call    cs:__imp_GetLastError
0x1800149a7  test    eax, eax
0x1800149a9  jle     short loc_1800149B3
0x1800149ab  movzx   eax, ax
0x1800149ae  or      eax, 80070000h
0x1800149b3  mov     ecx, eax; int
0x1800149b5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800149bb  mov     rax, rdi
0x1800149be  add     rsp, 48h
0x1800149c2  pop     rdi
0x1800149c3  pop     rsi
0x1800149c4  pop     rbp
0x1800149c5  pop     rbx
0x1800149c6  retn
```
