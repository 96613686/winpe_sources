# _com_util::ConvertStringToBSTR(char const *)

- ea: `0x18001e79c`
- end: `0x18001e91f`
- name: `?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z`
- size: `387`
- prototype: `BSTR __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012ed4`
- `0x180019e58`

## callees

- `0x1800022e0`
- `0x1800117c8`
- `0x18001e79c`
- `0x18001ea10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e8bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e8ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e8bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e8ff`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e863`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e905`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e81b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e89b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e81b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e89b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e8a8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e8a8`

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
0x18001e79c  mov     [rsp-8+arg_0], rcx
0x18001e7a1  push    rbp
0x18001e7a2  push    rdi
0x18001e7a3  push    r15
0x18001e7a5  sub     rsp, 50h
0x18001e7a9  lea     rbp, [rsp+30h]
0x18001e7ae  mov     [rbp+30h+arg_8], rbx
0x18001e7b2  mov     [rbp+30h+arg_10], rsi
0x18001e7b6  mov     rax, cs:__security_cookie
0x18001e7bd  xor     rax, rbp
0x18001e7c0  mov     [rbp+30h+var_20], rax
0x18001e7c4  mov     rsi, rcx
0x18001e7c7  test    rcx, rcx
0x18001e7ca  jnz     short loc_18001E7EB
0x18001e7cc  xor     eax, eax
0x18001e7ce  mov     rcx, [rbp+30h+var_20]
0x18001e7d2  xor     rcx, rbp; StackCookie
0x18001e7d5  call    __security_check_cookie
0x18001e7da  mov     rbx, [rbp+30h+arg_8]
0x18001e7de  mov     rsi, [rbp+30h+arg_10]
0x18001e7e2  lea     rsp, [rbp+20h]
0x18001e7e6  pop     r15
0x18001e7e8  pop     rdi
0x18001e7e9  pop     rbp
0x18001e7ea  retn
0x18001e7eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e7ef  inc     rax
0x18001e7f2  cmp     byte ptr [rcx+rax], 0
0x18001e7f6  jnz     short loc_18001E7EF
0x18001e7f8  lea     r15d, [rax+1]
0x18001e7fc  mov     [rbp+30h+var_2C], r15d
0x18001e800  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18001e808  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18001e811  mov     r9d, r15d; cbMultiByte
0x18001e814  mov     r8, rcx; lpMultiByteStr
0x18001e817  xor     edx, edx; dwFlags
0x18001e819  xor     ecx, ecx; CodePage
0x18001e81b  call    cs:__imp_MultiByteToWideChar
0x18001e821  movsxd  rdi, eax
0x18001e824  mov     dword ptr [rbp+30h+WideCharStr], edi
0x18001e827  test    eax, eax
0x18001e829  jz      loc_18001E8DA
0x18001e82f  mov     rcx, rdi
0x18001e832  add     rcx, rcx; Size
0x18001e835  cmp     edi, 1000h
0x18001e83b  jge     short loc_18001E863
0x18001e83d  lea     rax, [rcx+0Fh]
0x18001e841  cmp     rax, rcx
0x18001e844  ja      short loc_18001E850
0x18001e846  mov     rax, 0FFFFFFFFFFFFFF0h
0x18001e850  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001e854  call    _alloca_probe
0x18001e859  sub     rsp, rax
0x18001e85c  lea     rbx, [rsp+60h+WideCharStr]
0x18001e861  jmp     short loc_18001E86C
0x18001e863  call    cs:__imp_malloc
0x18001e869  mov     rbx, rax
0x18001e86c  mov     [rbp+30h+var_28], rbx
0x18001e870  jmp     short loc_18001E883
0x18001e872  xor     ebx, ebx
0x18001e874  mov     [rbp+30h+var_28], rbx
0x18001e878  mov     rsi, [rbp+30h+arg_0]
0x18001e87c  mov     edi, dword ptr [rbp+30h+WideCharStr]
0x18001e87f  mov     r15d, [rbp+30h+var_2C]
0x18001e883  test    rbx, rbx
0x18001e886  jz      short loc_18001E8CF
0x18001e888  mov     [rsp+60h+cchWideChar], edi; cchWideChar
0x18001e88c  mov     [rsp+60h+lpWideCharStr], rbx; lpWideCharStr
0x18001e891  mov     r9d, r15d; cbMultiByte
0x18001e894  mov     r8, rsi; lpMultiByteStr
0x18001e897  xor     edx, edx; dwFlags
0x18001e899  xor     ecx, ecx; CodePage
0x18001e89b  call    cs:__imp_MultiByteToWideChar
0x18001e8a1  test    eax, eax
0x18001e8a3  jz      short loc_18001E8F4
0x18001e8a5  mov     rcx, rbx; psz
0x18001e8a8  call    cs:__imp_SysAllocString
0x18001e8ae  mov     rsi, rax
0x18001e8b1  cmp     edi, 1000h
0x18001e8b7  jl      short loc_18001E8C2
0x18001e8b9  mov     rcx, rbx; Block
0x18001e8bc  call    cs:__imp_free
0x18001e8c2  test    rsi, rsi
0x18001e8c5  jz      short loc_18001E8CF
0x18001e8c7  mov     rax, rsi
0x18001e8ca  jmp     loc_18001E7CE
0x18001e8cf  mov     ecx, 8007000Eh; int
0x18001e8d4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001e8da  call    cs:__imp_GetLastError
0x18001e8e0  test    eax, eax
0x18001e8e2  jle     short loc_18001E8EC
0x18001e8e4  movzx   eax, ax
0x18001e8e7  or      eax, 80070000h
0x18001e8ec  mov     ecx, eax; int
0x18001e8ee  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001e8f4  cmp     edi, 1000h
0x18001e8fa  jl      short loc_18001E905
0x18001e8fc  mov     rcx, rbx; Block
0x18001e8ff  call    cs:__imp_free
0x18001e905  call    cs:__imp_GetLastError
0x18001e90b  test    eax, eax
0x18001e90d  jle     short loc_18001E917
0x18001e90f  movzx   eax, ax
0x18001e912  or      eax, 80070000h
0x18001e917  mov     ecx, eax; int
0x18001e919  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
