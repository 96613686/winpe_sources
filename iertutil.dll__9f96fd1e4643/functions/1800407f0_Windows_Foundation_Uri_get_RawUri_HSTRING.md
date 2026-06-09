# Windows::Foundation::Uri::get_RawUri(HSTRING__ * *)

- ea: `0x1800407f0`
- end: `0x1800408e0`
- name: `?get_RawUri@Uri@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `240`
- prototype: `int(Windows::Foundation::Uri *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800407f0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004086a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004086a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004089b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004089b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800408cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800408cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800408bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800408d8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800408bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800408d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004088a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004088a`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Uri::get_RawUri(Windows::Foundation::Uri *this, HSTRING *a2)
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
  if ( !*((_QWORD *)this + 15) )
  {
    sourceString = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, PCNZWCH *, _QWORD))(*(_QWORD *)v4 + 24LL))(
           v4,
           11,
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
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 15, (signed __int64)string, 0) )
      WindowsDeleteString(string);
    if ( v5 < 0 )
LABEL_16:
      RoOriginateError((unsigned int)v5, 0);
    SysFreeString((BSTR)sourceString);
    if ( v5 < 0 )
      goto LABEL_15;
  }
  v5 = WindowsDuplicateString(*((HSTRING *)this + 15), a2);
  if ( v5 < 0 )
    goto LABEL_15;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800407f0  mov     [rsp+arg_10], rbx
0x1800407f5  push    rbp
0x1800407f6  push    rsi
0x1800407f7  push    rdi
0x1800407f8  sub     rsp, 30h
0x1800407fc  xor     ebp, ebp
0x1800407fe  mov     rdi, rcx
0x180040801  mov     [rdx], rbp
0x180040804  mov     rsi, rdx
0x180040807  mov     rcx, [rcx+58h]
0x18004080b  test    rcx, rcx
0x18004080e  jz      loc_1800408B6
0x180040814  cmp     [rdi+78h], rbp
0x180040818  jnz     short loc_180040894
0x18004081a  mov     [rsp+48h+sourceString], rbp
0x18004081f  lea     r8, [rsp+48h+sourceString]
0x180040824  mov     rax, [rcx]
0x180040827  lea     edx, [rbp+0Bh]
0x18004082a  xor     r9d, r9d
0x18004082d  mov     rax, [rax+18h]
0x180040831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040836  mov     ebx, eax
0x180040838  test    eax, eax
0x18004083a  js      loc_1800408D4
0x180040840  mov     rax, [rsp+48h+sourceString]
0x180040845  lea     rcx, word_1801758E4
0x18004084c  test    rax, rax
0x18004084f  mov     [rsp+48h+string], rbp
0x180040854  cmovnz  rcx, rax; sourceString
0x180040858  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004085c  inc     rdx; length
0x18004085f  cmp     [rcx+rdx*2], bp
0x180040863  jnz     short loc_18004085C
0x180040865  lea     r8, [rsp+48h+string]; string
0x18004086a  call    cs:__imp_WindowsCreateString
0x180040870  mov     rcx, [rsp+48h+string]
0x180040875  mov     ebx, eax
0x180040877  xor     eax, eax
0x180040879  lock cmpxchg [rdi+78h], rcx
0x18004087f  jnz     short loc_1800408C7
0x180040881  test    ebx, ebx
0x180040883  js      short loc_1800408D4
0x180040885  mov     rcx, [rsp+48h+sourceString]; bstrString
0x18004088a  call    cs:__imp_SysFreeString
0x180040890  test    ebx, ebx
0x180040892  js      short loc_1800408BB
0x180040894  mov     rcx, [rdi+78h]; string
0x180040898  mov     rdx, rsi; newString
0x18004089b  call    cs:__imp_WindowsDuplicateString
0x1800408a1  mov     ebx, eax
0x1800408a3  test    eax, eax
0x1800408a5  js      short loc_1800408BB
0x1800408a7  mov     eax, ebx
0x1800408a9  mov     rbx, [rsp+48h+arg_10]
0x1800408ae  add     rsp, 30h
0x1800408b2  pop     rdi
0x1800408b3  pop     rsi
0x1800408b4  pop     rbp
0x1800408b5  retn
0x1800408b6  mov     ebx, 8000FFFFh
0x1800408bb  xor     edx, edx
0x1800408bd  mov     ecx, ebx
0x1800408bf  call    cs:__imp_RoOriginateError
0x1800408c5  jmp     short loc_1800408A7
0x1800408c7  mov     rcx, [rsp+48h+string]; string
0x1800408cc  call    cs:__imp_WindowsDeleteString
0x1800408d2  jmp     short loc_180040881
0x1800408d4  xor     edx, edx
0x1800408d6  mov     ecx, ebx
0x1800408d8  call    cs:__imp_RoOriginateError
0x1800408de  jmp     short loc_180040885
```
