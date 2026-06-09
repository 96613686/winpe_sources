# _com_util::ConvertStringToBSTR(char const *)

- ea: `0x180035950`
- end: `0x180035ad3`
- name: `?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z`
- size: `387`
- prototype: `BSTR __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cc8c`
- `0x180022164`

## callees

- `0x1800039f0`
- `0x18003593c`
- `0x180035950`
- `0x1800388e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035a70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035ab3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035a70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035ab3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180035a17`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180035a17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ab9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800359cf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180035a4f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800359cf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180035a4f`
- `OLEAUT32!__imp_SysAllocString` at `0x180035a5c`
- `OLEAUT32!__imp_SysAllocString` at `0x180035a5c`

## pseudocode

```c
BSTR __fastcall _com_util::ConvertStringToBSTR(LPCCH lpMultiByteStr)
{
  __int64 v3; // rax
  int v4; // r15d
  int v5; // eax
  int cchWideChar; // edi
  size_t v7; // rcx
  __int64 v8; // rax
  void *v9; // rsp
  void *lpWideCharStr; // rbx
  BSTR v11; // rsi
  signed int LastError; // eax
  signed int v13; // eax
  WCHAR WideCharStr[2]; // [rsp+30h] [rbp+0h] BYREF
  int v15; // [rsp+34h] [rbp+4h]
  void *v16; // [rsp+38h] [rbp+8h]

  if ( !lpMultiByteStr )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( lpMultiByteStr[v3] );
  v4 = v3 + 1;
  v15 = v3 + 1;
  v5 = MultiByteToWideChar(0, 0, lpMultiByteStr, v3 + 1, 0, 0);
  cchWideChar = v5;
  *(_DWORD *)WideCharStr = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    _com_issue_error(LastError);
  }
  v7 = 2LL * v5;
  if ( v5 >= 4096 )
  {
    lpWideCharStr = malloc(v7);
  }
  else
  {
    v8 = v7 + 15;
    if ( v7 + 15 < v7 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = WideCharStr;
  }
  v16 = lpWideCharStr;
  if ( !lpWideCharStr )
    goto LABEL_17;
  if ( !MultiByteToWideChar(0, 0, lpMultiByteStr, v4, (LPWSTR)lpWideCharStr, cchWideChar) )
  {
    if ( cchWideChar >= 4096 )
      free(lpWideCharStr);
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    _com_issue_error(v13);
  }
  v11 = SysAllocString((const OLECHAR *)lpWideCharStr);
  if ( cchWideChar >= 4096 )
    free(lpWideCharStr);
  if ( !v11 )
LABEL_17:
    _com_issue_error(-2147024882);
  return v11;
}

```

## disassembly

```asm
0x180035950  mov     [rsp-8+arg_0], rcx
0x180035955  push    rbp
0x180035956  push    rdi
0x180035957  push    r15
0x180035959  sub     rsp, 50h
0x18003595d  lea     rbp, [rsp+30h]
0x180035962  mov     [rbp+30h+arg_8], rbx
0x180035966  mov     [rbp+30h+arg_10], rsi
0x18003596a  mov     rax, cs:__security_cookie
0x180035971  xor     rax, rbp
0x180035974  mov     [rbp+30h+var_20], rax
0x180035978  mov     rsi, rcx
0x18003597b  test    rcx, rcx
0x18003597e  jnz     short loc_18003599F
0x180035980  xor     eax, eax
0x180035982  mov     rcx, [rbp+30h+var_20]
0x180035986  xor     rcx, rbp; StackCookie
0x180035989  call    __security_check_cookie
0x18003598e  mov     rbx, [rbp+30h+arg_8]
0x180035992  mov     rsi, [rbp+30h+arg_10]
0x180035996  lea     rsp, [rbp+20h]
0x18003599a  pop     r15
0x18003599c  pop     rdi
0x18003599d  pop     rbp
0x18003599e  retn
0x18003599f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800359a3  inc     rax
0x1800359a6  cmp     byte ptr [rcx+rax], 0
0x1800359aa  jnz     short loc_1800359A3
0x1800359ac  lea     r15d, [rax+1]
0x1800359b0  mov     [rbp+30h+var_2C], r15d
0x1800359b4  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x1800359bc  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x1800359c5  mov     r9d, r15d; cbMultiByte
0x1800359c8  mov     r8, rcx; lpMultiByteStr
0x1800359cb  xor     edx, edx; dwFlags
0x1800359cd  xor     ecx, ecx; CodePage
0x1800359cf  call    cs:__imp_MultiByteToWideChar
0x1800359d5  movsxd  rdi, eax
0x1800359d8  mov     dword ptr [rbp+30h+WideCharStr], edi
0x1800359db  test    eax, eax
0x1800359dd  jz      loc_180035A8E
0x1800359e3  mov     rcx, rdi
0x1800359e6  add     rcx, rcx; Size
0x1800359e9  cmp     edi, 1000h
0x1800359ef  jge     short loc_180035A17
0x1800359f1  lea     rax, [rcx+0Fh]
0x1800359f5  cmp     rax, rcx
0x1800359f8  ja      short loc_180035A04
0x1800359fa  mov     rax, 0FFFFFFFFFFFFFF0h
0x180035a04  and     rax, 0FFFFFFFFFFFFFFF0h
0x180035a08  call    _alloca_probe
0x180035a0d  sub     rsp, rax
0x180035a10  lea     rbx, [rsp+60h+WideCharStr]
0x180035a15  jmp     short loc_180035A20
0x180035a17  call    cs:__imp_malloc
0x180035a1d  mov     rbx, rax
0x180035a20  mov     [rbp+30h+var_28], rbx
0x180035a24  jmp     short loc_180035A37
0x180035a26  xor     ebx, ebx
0x180035a28  mov     [rbp+30h+var_28], rbx
0x180035a2c  mov     rsi, [rbp+30h+arg_0]
0x180035a30  mov     edi, dword ptr [rbp+30h+WideCharStr]
0x180035a33  mov     r15d, [rbp+30h+var_2C]
0x180035a37  test    rbx, rbx
0x180035a3a  jz      short loc_180035A83
0x180035a3c  mov     [rsp+60h+cchWideChar], edi; cchWideChar
0x180035a40  mov     [rsp+60h+lpWideCharStr], rbx; lpWideCharStr
0x180035a45  mov     r9d, r15d; cbMultiByte
0x180035a48  mov     r8, rsi; lpMultiByteStr
0x180035a4b  xor     edx, edx; dwFlags
0x180035a4d  xor     ecx, ecx; CodePage
0x180035a4f  call    cs:__imp_MultiByteToWideChar
0x180035a55  test    eax, eax
0x180035a57  jz      short loc_180035AA8
0x180035a59  mov     rcx, rbx; psz
0x180035a5c  call    cs:__imp_SysAllocString
0x180035a62  mov     rsi, rax
0x180035a65  cmp     edi, 1000h
0x180035a6b  jl      short loc_180035A76
0x180035a6d  mov     rcx, rbx; Block
0x180035a70  call    cs:__imp_free
0x180035a76  test    rsi, rsi
0x180035a79  jz      short loc_180035A83
0x180035a7b  mov     rax, rsi
0x180035a7e  jmp     loc_180035982
0x180035a83  mov     ecx, 8007000Eh; int
0x180035a88  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180035a8e  call    cs:__imp_GetLastError
0x180035a94  test    eax, eax
0x180035a96  jle     short loc_180035AA0
0x180035a98  movzx   eax, ax
0x180035a9b  or      eax, 80070000h
0x180035aa0  mov     ecx, eax; int
0x180035aa2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180035aa8  cmp     edi, 1000h
0x180035aae  jl      short loc_180035AB9
0x180035ab0  mov     rcx, rbx; Block
0x180035ab3  call    cs:__imp_free
0x180035ab9  call    cs:__imp_GetLastError
0x180035abf  test    eax, eax
0x180035ac1  jle     short loc_180035ACB
0x180035ac3  movzx   eax, ax
0x180035ac6  or      eax, 80070000h
0x180035acb  mov     ecx, eax; int
0x180035acd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
