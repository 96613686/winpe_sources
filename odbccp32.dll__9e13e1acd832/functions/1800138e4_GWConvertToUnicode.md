# GWConvertToUnicode

- ea: `0x1800138e4`
- end: `0x180013990`
- name: `GWConvertToUnicode`
- size: `172`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, WCHAR **, unsigned int)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ec20`
- `0x18000ecc0`
- `0x18000ee10`
- `0x18000ef70`
- `0x18000f100`
- `0x18000f2b0`
- `0x18000f3e0`
- `0x18000f600`
- `0x18000f8c0`
- `0x18000f930`
- `0x18000fab0`
- `0x18000fb00`
- `0x18000fb70`
- `0x18000fbd0`
- `0x18000fc40`
- `0x18000fcd0`
- `0x18000fdd0`

## callees

- `0x180002940`
- `0x1800138e4`

## import_xrefs

- `msvcrt!calloc` at `0x180013949`
- `msvcrt!calloc` at `0x180013949`
- `KERNEL32!MultiByteToWideChar` at `0x18001396a`
- `KERNEL32!MultiByteToWideChar` at `0x18001396a`
- `KERNEL32!GetLastError` at `0x180013983`
- `KERNEL32!GetLastError` at `0x180013983`

## pseudocode

```c
__int64 __fastcall GWConvertToUnicode(LPCCH lpMultiByteStr, WCHAR **a2, unsigned int a3)
{
  unsigned int cchWideChar; // ebx
  __int64 v7; // rbx
  WCHAR *lpWideCharStr; // rax

  cchWideChar = a3;
  if ( !lpMultiByteStr )
  {
    *a2 = 0;
    return 1;
  }
  if ( a3 == -3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( lpMultiByteStr[v7] );
    cchWideChar = v7 + 1;
  }
  if ( !cchWideChar )
    return 1;
  if ( cchWideChar <= 0x3FFFFFFE )
  {
    lpWideCharStr = (WCHAR *)calloc(2LL * (int)(cchWideChar + 1), 1u);
    *a2 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0, 0, lpMultiByteStr, cchWideChar, lpWideCharStr, cchWideChar) )
        return 1;
      OFree(*a2);
      *a2 = 0;
      GetLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800138e4  mov     [rsp+arg_8], rbx
0x1800138e9  mov     [rsp+arg_10], rsi
0x1800138ee  push    rdi
0x1800138ef  sub     rsp, 30h
0x1800138f3  mov     ebx, r8d
0x1800138f6  mov     rdi, rdx
0x1800138f9  mov     rsi, rcx
0x1800138fc  test    rcx, rcx
0x1800138ff  jnz     short loc_180013919
0x180013901  mov     [rdx], rcx
0x180013904  mov     eax, 1
0x180013909  mov     rbx, [rsp+38h+arg_8]
0x18001390e  mov     rsi, [rsp+38h+arg_10]
0x180013913  add     rsp, 30h
0x180013917  pop     rdi
0x180013918  retn
0x180013919  cmp     ebx, 0FFFFFFFDh
0x18001391c  jnz     short loc_18001392D
0x18001391e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013922  inc     rbx
0x180013925  cmp     byte ptr [rcx+rbx], 0
0x180013929  jnz     short loc_180013922
0x18001392b  inc     ebx
0x18001392d  test    ebx, ebx
0x18001392f  jz      short loc_180013904
0x180013931  js      short loc_180013989
0x180013933  cmp     ebx, 3FFFFFFEh
0x180013939  ja      short loc_180013989
0x18001393b  lea     eax, [rbx+1]
0x18001393e  mov     edx, 1; Size
0x180013943  movsxd  rcx, eax
0x180013946  add     rcx, rcx; Count
0x180013949  call    cs:__imp_calloc
0x18001394f  mov     [rdi], rax
0x180013952  test    rax, rax
0x180013955  jz      short loc_180013989
0x180013957  mov     [rsp+38h+cchWideChar], ebx; cchWideChar
0x18001395b  mov     r9d, ebx; cbMultiByte
0x18001395e  mov     r8, rsi; lpMultiByteStr
0x180013961  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x180013966  xor     edx, edx; dwFlags
0x180013968  xor     ecx, ecx; CodePage
0x18001396a  call    cs:__imp_MultiByteToWideChar
0x180013970  test    eax, eax
0x180013972  jnz     short loc_180013904
0x180013974  mov     rcx, [rdi]
0x180013977  call    OFree
0x18001397c  mov     qword ptr [rdi], 0
0x180013983  call    cs:__imp_GetLastError
0x180013989  xor     eax, eax
0x18001398b  jmp     loc_180013909
```
