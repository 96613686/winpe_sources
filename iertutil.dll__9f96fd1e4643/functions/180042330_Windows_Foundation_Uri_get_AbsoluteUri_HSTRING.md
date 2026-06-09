# Windows::Foundation::Uri::get_AbsoluteUri(HSTRING__ * *)

- ea: `0x180042330`
- end: `0x180042429`
- name: `?get_AbsoluteUri@Uri@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `249`
- prototype: `int(Windows::Foundation::Uri *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180042330`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800423ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800423ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800423e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800423e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042415`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042408`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042421`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042408`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180042421`
- `OLEAUT32!__imp_SysFreeString` at `0x1800423d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800423d0`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Uri::get_AbsoluteUri(Windows::Foundation::Uri *this, HSTRING *a2)
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
  if ( !*((_QWORD *)this + 16) )
  {
    sourceString = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCNZWCH *, __int64))(*(_QWORD *)v4 + 24LL))(
           v4,
           0,
           &sourceString,
           8);
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
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 16, (signed __int64)string, 0) )
      WindowsDeleteString(string);
    if ( v5 < 0 )
LABEL_16:
      RoOriginateError((unsigned int)v5, 0);
    SysFreeString((BSTR)sourceString);
    if ( v5 < 0 )
      goto LABEL_15;
  }
  v5 = WindowsDuplicateString(*((HSTRING *)this + 16), a2);
  if ( v5 < 0 )
    goto LABEL_15;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180042330  mov     [rsp+arg_10], rbx
0x180042335  push    rbp
0x180042336  push    rsi
0x180042337  push    rdi
0x180042338  sub     rsp, 30h
0x18004233c  xor     ebp, ebp
0x18004233e  mov     rdi, rcx
0x180042341  mov     [rdx], rbp
0x180042344  mov     rsi, rdx
0x180042347  mov     rcx, [rcx+58h]
0x18004234b  test    rcx, rcx
0x18004234e  jz      loc_1800423FF
0x180042354  cmp     [rdi+80h], rbp
0x18004235b  jnz     short loc_1800423DA
0x18004235d  mov     [rsp+48h+sourceString], rbp
0x180042362  lea     r9d, [rbp+8]
0x180042366  mov     rax, [rcx]
0x180042369  lea     r8, [rsp+48h+sourceString]
0x18004236e  xor     edx, edx
0x180042370  mov     rax, [rax+18h]
0x180042374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042379  mov     ebx, eax
0x18004237b  test    eax, eax
0x18004237d  js      loc_18004241D
0x180042383  mov     rax, [rsp+48h+sourceString]
0x180042388  lea     rcx, word_1801758E4
0x18004238f  test    rax, rax
0x180042392  mov     [rsp+48h+string], rbp
0x180042397  cmovnz  rcx, rax; sourceString
0x18004239b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004239f  inc     rdx; length
0x1800423a2  cmp     [rcx+rdx*2], bp
0x1800423a6  jnz     short loc_18004239F
0x1800423a8  lea     r8, [rsp+48h+string]; string
0x1800423ad  call    cs:__imp_WindowsCreateString
0x1800423b3  mov     rcx, [rsp+48h+string]
0x1800423b8  mov     ebx, eax
0x1800423ba  xor     eax, eax
0x1800423bc  lock cmpxchg [rdi+80h], rcx
0x1800423c5  jnz     short loc_180042410
0x1800423c7  test    ebx, ebx
0x1800423c9  js      short loc_18004241D
0x1800423cb  mov     rcx, [rsp+48h+sourceString]; bstrString
0x1800423d0  call    cs:__imp_SysFreeString
0x1800423d6  test    ebx, ebx
0x1800423d8  js      short loc_180042404
0x1800423da  mov     rcx, [rdi+80h]; string
0x1800423e1  mov     rdx, rsi; newString
0x1800423e4  call    cs:__imp_WindowsDuplicateString
0x1800423ea  mov     ebx, eax
0x1800423ec  test    eax, eax
0x1800423ee  js      short loc_180042404
0x1800423f0  mov     eax, ebx
0x1800423f2  mov     rbx, [rsp+48h+arg_10]
0x1800423f7  add     rsp, 30h
0x1800423fb  pop     rdi
0x1800423fc  pop     rsi
0x1800423fd  pop     rbp
0x1800423fe  retn
0x1800423ff  mov     ebx, 8000FFFFh
0x180042404  xor     edx, edx
0x180042406  mov     ecx, ebx
0x180042408  call    cs:__imp_RoOriginateError
0x18004240e  jmp     short loc_1800423F0
0x180042410  mov     rcx, [rsp+48h+string]; string
0x180042415  call    cs:__imp_WindowsDeleteString
0x18004241b  jmp     short loc_1800423C7
0x18004241d  xor     edx, edx
0x18004241f  mov     ecx, ebx
0x180042421  call    cs:__imp_RoOriginateError
0x180042427  jmp     short loc_1800423CB
```
