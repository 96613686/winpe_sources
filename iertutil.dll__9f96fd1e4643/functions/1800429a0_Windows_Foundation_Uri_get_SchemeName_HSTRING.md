# Windows::Foundation::Uri::get_SchemeName(HSTRING__ * *)

- ea: `0x1800429a0`
- end: `0x180042a99`
- name: `?get_SchemeName@Uri@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `249`
- prototype: `int(Windows::Foundation::Uri *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800429a0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042a1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042a1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180042a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180042a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042a85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042a85`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042a78`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042a91`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042a78`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042a91`
- `OLEAUT32!__imp_SysFreeString` at `0x180042a40`
- `OLEAUT32!__imp_SysFreeString` at `0x180042a40`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Uri::get_SchemeName(Windows::Foundation::Uri *this, HSTRING *a2)
{
  __int64 v4; // rcx
  HRESULT v5; // ebx
  const WCHAR *v6; // rcx
  __int64 v7; // rdx
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF
  PCNZWCH sourceString; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v4 = *((_QWORD *)this + 11);
  if ( !v4 )
  {
    v5 = -2147418113;
LABEL_15:
    RoOriginateError((unsigned int)v5, 0);
    return (unsigned int)v5;
  }
  if ( !*((_QWORD *)this + 26) )
  {
    sourceString = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, PCNZWCH *, _QWORD))(*(_QWORD *)v4 + 24LL))(
           v4,
           12,
           &sourceString,
           0);
    if ( v5 < 0 )
      goto LABEL_16;
    v6 = &word_1801758E4;
    string = 0;
    if ( sourceString )
      v6 = sourceString;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v5 = WindowsCreateString(v6, v7, &string);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 26, (signed __int64)string, 0) )
      WindowsDeleteString(string);
    if ( v5 < 0 )
LABEL_16:
      RoOriginateError((unsigned int)v5, 0);
    SysFreeString((BSTR)sourceString);
    if ( v5 < 0 )
      goto LABEL_15;
  }
  v5 = WindowsDuplicateString(*((HSTRING *)this + 26), a2);
  if ( v5 < 0 )
    goto LABEL_15;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800429a0  mov     [rsp+arg_10], rbx
0x1800429a5  push    rbp
0x1800429a6  push    rsi
0x1800429a7  push    rdi
0x1800429a8  sub     rsp, 30h
0x1800429ac  xor     ebp, ebp
0x1800429ae  mov     rdi, rcx
0x1800429b1  mov     [rdx], rbp
0x1800429b4  mov     rsi, rdx
0x1800429b7  mov     rcx, [rcx+58h]
0x1800429bb  test    rcx, rcx
0x1800429be  jz      loc_180042A6F
0x1800429c4  cmp     [rdi+0D0h], rbp
0x1800429cb  jnz     short loc_180042A4A
0x1800429cd  mov     [rsp+48h+sourceString], rbp
0x1800429d2  lea     r8, [rsp+48h+sourceString]
0x1800429d7  mov     rax, [rcx]
0x1800429da  lea     edx, [rbp+0Ch]
0x1800429dd  xor     r9d, r9d
0x1800429e0  mov     rax, [rax+18h]
0x1800429e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429e9  mov     ebx, eax
0x1800429eb  test    eax, eax
0x1800429ed  js      loc_180042A8D
0x1800429f3  mov     rax, [rsp+48h+sourceString]
0x1800429f8  lea     rcx, word_1801758E4
0x1800429ff  test    rax, rax
0x180042a02  mov     [rsp+48h+string], rbp
0x180042a07  cmovnz  rcx, rax; sourceString
0x180042a0b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180042a0f  inc     rdx; length
0x180042a12  cmp     [rcx+rdx*2], bp
0x180042a16  jnz     short loc_180042A0F
0x180042a18  lea     r8, [rsp+48h+string]; string
0x180042a1d  call    cs:__imp_WindowsCreateString
0x180042a23  mov     rcx, [rsp+48h+string]
0x180042a28  mov     ebx, eax
0x180042a2a  xor     eax, eax
0x180042a2c  lock cmpxchg [rdi+0D0h], rcx
0x180042a35  jnz     short loc_180042A80
0x180042a37  test    ebx, ebx
0x180042a39  js      short loc_180042A8D
0x180042a3b  mov     rcx, [rsp+48h+sourceString]; bstrString
0x180042a40  call    cs:__imp_SysFreeString
0x180042a46  test    ebx, ebx
0x180042a48  js      short loc_180042A74
0x180042a4a  mov     rcx, [rdi+0D0h]; string
0x180042a51  mov     rdx, rsi; newString
0x180042a54  call    cs:__imp_WindowsDuplicateString
0x180042a5a  mov     ebx, eax
0x180042a5c  test    eax, eax
0x180042a5e  js      short loc_180042A74
0x180042a60  mov     eax, ebx
0x180042a62  mov     rbx, [rsp+48h+arg_10]
0x180042a67  add     rsp, 30h
0x180042a6b  pop     rdi
0x180042a6c  pop     rsi
0x180042a6d  pop     rbp
0x180042a6e  retn
0x180042a6f  mov     ebx, 8000FFFFh
0x180042a74  xor     edx, edx
0x180042a76  mov     ecx, ebx
0x180042a78  call    cs:__imp_RoOriginateError
0x180042a7e  jmp     short loc_180042A60
0x180042a80  mov     rcx, [rsp+48h+string]; string
0x180042a85  call    cs:__imp_WindowsDeleteString
0x180042a8b  jmp     short loc_180042A37
0x180042a8d  xor     edx, edx
0x180042a8f  mov     ecx, ebx
0x180042a91  call    cs:__imp_RoOriginateError
0x180042a97  jmp     short loc_180042A3B
```
