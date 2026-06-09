# GetFileVersion

- ea: `0x1800052b8`
- end: `0x18000551f`
- name: `GetFileVersion`
- size: `615`
- prototype: `__int64 __fastcall(LPCWSTR lptstrFilename, wchar_t *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a3b0`
- `0x18000a66c`

## callees

- `0x180002940`
- `0x180002e14`
- `0x180002e4c`
- `0x1800052b8`
- `0x1800074c4`
- `0x180014aae`

## import_xrefs

- `msvcrt!calloc` at `0x18000531f`
- `msvcrt!calloc` at `0x18000531f`
- `KERNEL32!VerLanguageNameW` at `0x180005431`
- `KERNEL32!VerLanguageNameW` at `0x180005431`
- `VERSION!GetFileVersionInfoSizeW` at `0x180005307`
- `VERSION!GetFileVersionInfoSizeW` at `0x180005307`
- `VERSION!GetFileVersionInfoW` at `0x18000535b`
- `VERSION!GetFileVersionInfoW` at `0x18000535b`
- `VERSION!VerQueryValueW` at `0x18000537e`
- `VERSION!VerQueryValueW` at `0x1800053d5`
- `VERSION!VerQueryValueW` at `0x180005466`
- `VERSION!VerQueryValueW` at `0x1800054d1`
- `VERSION!VerQueryValueW` at `0x18000537e`
- `VERSION!VerQueryValueW` at `0x1800053d5`
- `VERSION!VerQueryValueW` at `0x180005466`
- `VERSION!VerQueryValueW` at `0x1800054d1`

## string_xrefs

- `0x180005437`: `CompanyName`

## pseudocode

```c
__int64 __fastcall GetFileVersion(LPCWSTR lptstrFilename, wchar_t *a2, int a3)
{
  DWORD FileVersionInfoSizeW; // eax
  __int64 v7; // r14
  char *v8; // rax
  char *v9; // rbx
  unsigned __int16 *v11; // rcx
  wchar_t *v12; // rsi
  wchar_t *v13; // r14
  _WORD *i; // r8
  _WORD *j; // r8
  LPVOID v16; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-8h] BYREF
  unsigned int puLen; // [rsp+80h] [rbp+40h] BYREF
  DWORD dwHandle; // [rsp+98h] [rbp+58h] BYREF

  lpBuffer = 0;
  v16 = 0;
  puLen = 0;
  dwHandle = 0;
  if ( !lptstrFilename )
    return 0;
  memset_0(a2, 0, 0x610u);
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, &dwHandle);
  v7 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
    return 0;
  v8 = (char *)calloc(FileVersionInfoSizeW + 512LL, 1u);
  v9 = v8;
  if ( !v8 )
  {
    MemError();
    return 0;
  }
  dwHandle = 0;
  if ( !GetFileVersionInfoW(lptstrFilename, 0, v7, v8) )
  {
    OFree(v9);
    return 0;
  }
  if ( VerQueryValueW(v9, L"\\", &lpBuffer, &puLen) && puLen )
  {
    v11 = (unsigned __int16 *)lpBuffer;
    *((_DWORD *)a2 + 384) = *((unsigned __int16 *)lpBuffer + 5);
    *((_DWORD *)a2 + 385) = v11[4];
    *((_DWORD *)a2 + 386) = v11[7];
    *((_DWORD *)a2 + 387) = v11[6];
  }
  if ( a3 && VerQueryValueW(v9, L"\\VarFileInfo\\Translation", &v16, &puLen) && puLen )
  {
    v12 = (wchar_t *)&v9[v7];
    v13 = (wchar_t *)&v9[v7 + 256];
    StringCchPrintfW(
      v13,
      0x80u,
      L"\\StringFileInfo\\%04X%04X\\",
      *(unsigned __int16 *)v16,
      *((unsigned __int16 *)v16 + 1));
    VerLanguageNameW(*(unsigned __int16 *)v16, a2 + 384, 0x80u);
    StringCchPrintfW(v12, 0x80u, L"%s%s", v13, L"CompanyName");
    if ( VerQueryValueW(v9, v12, &v16, &puLen) && puLen )
    {
      for ( i = v16; *i == 32; v16 = i )
        ++i;
      StringCchCopyW(a2 + 256, 0x80u, i);
    }
    StringCchPrintfW(v12, 0x80u, L"%s%s", v13, L"FileDescription");
    if ( VerQueryValueW(v9, v12, &v16, &puLen) && puLen )
    {
      for ( j = v16; *j == 32; v16 = j )
        ++j;
      StringCchCopyW(a2 + 128, 0x80u, j);
    }
  }
  OFree(v9);
  return 1;
}

```

## disassembly

```asm
0x1800052b8  mov     [rsp-38h+arg_8], rbx
0x1800052bd  push    rbp
0x1800052be  push    rsi
0x1800052bf  push    rdi
0x1800052c0  push    r12
0x1800052c2  push    r13
0x1800052c4  push    r14
0x1800052c6  push    r15
0x1800052c8  mov     rbp, rsp
0x1800052cb  sub     rsp, 40h
0x1800052cf  xor     r13d, r13d
0x1800052d2  mov     r15d, r8d
0x1800052d5  mov     [rbp+lpBuffer], r13
0x1800052d9  mov     rdi, rdx
0x1800052dc  mov     [rbp+var_10], r13
0x1800052e0  mov     rsi, rcx
0x1800052e3  mov     [rbp+puLen], r13d
0x1800052e7  mov     [rbp+dwHandle], r13d
0x1800052eb  test    rcx, rcx
0x1800052ee  jz      short loc_180005332
0x1800052f0  xor     edx, edx; Val
0x1800052f2  mov     r8d, 610h; Size
0x1800052f8  mov     rcx, rdi; void *
0x1800052fb  call    memset_0
0x180005300  lea     rdx, [rbp+dwHandle]; lpdwHandle
0x180005304  mov     rcx, rsi; lptstrFilename
0x180005307  call    cs:__imp_GetFileVersionInfoSizeW
0x18000530d  mov     r14d, eax
0x180005310  test    eax, eax
0x180005312  jz      short loc_180005332
0x180005314  lea     rcx, [r14+200h]; Count
0x18000531b  lea     edx, [r13+1]; Size
0x18000531f  call    cs:__imp_calloc
0x180005325  mov     rbx, rax
0x180005328  test    rax, rax
0x18000532b  jnz     short loc_18000534C
0x18000532d  call    MemError
0x180005332  xor     eax, eax
0x180005334  mov     rbx, [rsp+40h+arg_8]
0x18000533c  add     rsp, 40h
0x180005340  pop     r15
0x180005342  pop     r14
0x180005344  pop     r13
0x180005346  pop     r12
0x180005348  pop     rdi
0x180005349  pop     rsi
0x18000534a  pop     rbp
0x18000534b  retn
0x18000534c  mov     r9, rbx; lpData
0x18000534f  mov     [rbp+dwHandle], r13d
0x180005353  mov     r8d, r14d; dwLen
0x180005356  xor     edx, edx; dwHandle
0x180005358  mov     rcx, rsi; lptstrFilename
0x18000535b  call    cs:__imp_GetFileVersionInfoW
0x180005361  mov     rcx, rbx; pBlock
0x180005364  test    eax, eax
0x180005366  jnz     short loc_18000536F
0x180005368  call    OFree
0x18000536d  jmp     short loc_180005332
0x18000536f  lea     r9, [rbp+puLen]; puLen
0x180005373  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180005377  lea     rdx, SubBlock; "\\"
0x18000537e  call    cs:__imp_VerQueryValueW
0x180005384  test    eax, eax
0x180005386  jz      short loc_1800053BA
0x180005388  cmp     [rbp+puLen], r13d
0x18000538c  jz      short loc_1800053BA
0x18000538e  mov     rcx, [rbp+lpBuffer]
0x180005392  movzx   eax, word ptr [rcx+0Ah]
0x180005396  mov     [rdi+600h], eax
0x18000539c  movzx   eax, word ptr [rcx+8]
0x1800053a0  mov     [rdi+604h], eax
0x1800053a6  movzx   eax, word ptr [rcx+0Eh]
0x1800053aa  mov     [rdi+608h], eax
0x1800053b0  movzx   eax, word ptr [rcx+0Ch]
0x1800053b4  mov     [rdi+60Ch], eax
0x1800053ba  test    r15d, r15d
0x1800053bd  jz      loc_18000550D
0x1800053c3  lea     r9, [rbp+puLen]; puLen
0x1800053c7  mov     rcx, rbx; pBlock
0x1800053ca  lea     r8, [rbp+var_10]; lplpBuffer
0x1800053ce  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x1800053d5  call    cs:__imp_VerQueryValueW
0x1800053db  test    eax, eax
0x1800053dd  jz      loc_18000550D
0x1800053e3  cmp     [rbp+puLen], r13d
0x1800053e7  jz      loc_18000550D
0x1800053ed  mov     rax, [rbp+var_10]
0x1800053f1  lea     rsi, [r14+rbx]
0x1800053f5  lea     r14, [rsi+100h]
0x1800053fc  mov     r15d, 80h
0x180005402  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\"
0x180005409  mov     edx, r15d; cchDest
0x18000540c  movzx   ecx, word ptr [rax+2]
0x180005410  movzx   r9d, word ptr [rax]
0x180005414  mov     dword ptr [rsp+40h+var_20], ecx
0x180005418  mov     rcx, r14; pszDest
0x18000541b  call    StringCchPrintfW
0x180005420  mov     rax, [rbp+var_10]
0x180005424  lea     rdx, [rdi+300h]; szLang
0x18000542b  mov     r8d, r15d; cchLang
0x18000542e  movzx   ecx, word ptr [rax]; wLang
0x180005431  call    cs:__imp_VerLanguageNameW
0x180005437  lea     rax, aCompanyname; "CompanyName"
0x18000543e  mov     r9, r14
0x180005441  lea     r8, aSS_1; "%s%s"
0x180005448  mov     [rsp+40h+var_20], rax
0x18000544d  mov     edx, r15d; cchDest
0x180005450  mov     rcx, rsi; pszDest
0x180005453  call    StringCchPrintfW
0x180005458  lea     r9, [rbp+puLen]; puLen
0x18000545c  mov     rdx, rsi; lpSubBlock
0x18000545f  lea     r8, [rbp+var_10]; lplpBuffer
0x180005463  mov     rcx, rbx; pBlock
0x180005466  call    cs:__imp_VerQueryValueW
0x18000546c  test    eax, eax
0x18000546e  jz      short loc_1800054A2
0x180005470  cmp     [rbp+puLen], r13d
0x180005474  jz      short loc_1800054A2
0x180005476  mov     r8, [rbp+var_10]
0x18000547a  jmp     short loc_18000548A
0x18000547c  cmp     ax, 20h ; ' '
0x180005480  jnz     short loc_180005493
0x180005482  add     r8, 2; pszSrc
0x180005486  mov     [rbp+var_10], r8
0x18000548a  movzx   eax, word ptr [r8]
0x18000548e  test    ax, ax
0x180005491  jnz     short loc_18000547C
0x180005493  lea     rcx, [rdi+200h]; pszDest
0x18000549a  mov     rdx, r15; cchDest
0x18000549d  call    StringCchCopyW
0x1800054a2  lea     rax, aFiledescriptio; "FileDescription"
0x1800054a9  mov     r9, r14
0x1800054ac  lea     r8, aSS_1; "%s%s"
0x1800054b3  mov     [rsp+40h+var_20], rax
0x1800054b8  mov     rdx, r15; cchDest
0x1800054bb  mov     rcx, rsi; pszDest
0x1800054be  call    StringCchPrintfW
0x1800054c3  lea     r9, [rbp+puLen]; puLen
0x1800054c7  mov     rdx, rsi; lpSubBlock
0x1800054ca  lea     r8, [rbp+var_10]; lplpBuffer
0x1800054ce  mov     rcx, rbx; pBlock
0x1800054d1  call    cs:__imp_VerQueryValueW
0x1800054d7  test    eax, eax
0x1800054d9  jz      short loc_18000550D
0x1800054db  cmp     [rbp+puLen], r13d
0x1800054df  jz      short loc_18000550D
0x1800054e1  mov     r8, [rbp+var_10]
0x1800054e5  jmp     short loc_1800054F5
0x1800054e7  cmp     ax, 20h ; ' '
0x1800054eb  jnz     short loc_1800054FE
0x1800054ed  add     r8, 2; pszSrc
0x1800054f1  mov     [rbp+var_10], r8
0x1800054f5  movzx   eax, word ptr [r8]
0x1800054f9  test    ax, ax
0x1800054fc  jnz     short loc_1800054E7
0x1800054fe  lea     rcx, [rdi+100h]; pszDest
0x180005505  mov     rdx, r15; cchDest
0x180005508  call    StringCchCopyW
0x18000550d  mov     rcx, rbx
0x180005510  call    OFree
0x180005515  mov     eax, 1
0x18000551a  jmp     loc_180005334
```
