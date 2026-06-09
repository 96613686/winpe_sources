# Windows::Foundation::Uri::InitializeUriProperty(__MIDL_IUri_0001,ulong,HSTRING__ * *)

- ea: `0x18003e910`
- end: `0x18003e9cf`
- name: `?InitializeUriProperty@Uri@Foundation@Windows@@AEAAJW4__MIDL_IUri_0001@@KPEAPEAUHSTRING__@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(Windows::Foundation::Uri *__hidden this, enum __MIDL_IUri_0001, unsigned int, HSTRING *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003e420`
- `0x18003e4a0`
- `0x18003e520`
- `0x18003e5a0`
- `0x18003e620`
- `0x18003e6a0`
- `0x18003e790`
- `0x18003e810`
- `0x18003e890`
- `0x18005bb50`

## callees

- `0x18003e910`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9bb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003e9c7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003e9c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e99e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e99e`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Uri::InitializeUriProperty(
        Windows::Foundation::Uri *this,
        __int64 a2,
        unsigned int a3,
        HSTRING *a4)
{
  __int64 result; // rax
  __int64 v6; // rcx
  HRESULT v7; // ebx
  const WCHAR *v8; // rcx
  __int64 v9; // rdx
  PCNZWCH sourceString[3]; // [rsp+30h] [rbp-18h] BYREF
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  result = 0;
  if ( !*a4 )
  {
    v6 = *((_QWORD *)this + 11);
    sourceString[0] = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, PCNZWCH *, _QWORD))(*(_QWORD *)v6 + 24LL))(
           v6,
           a2,
           sourceString,
           a3);
    if ( v7 < 0 )
      goto LABEL_11;
    v8 = &word_1801758E4;
    string = 0;
    v9 = -1;
    if ( sourceString[0] )
      v8 = sourceString[0];
    do
      ++v9;
    while ( v8[v9] );
    v7 = WindowsCreateString(v8, v9, &string);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)a4, (signed __int64)string, 0) )
      WindowsDeleteString(string);
    if ( v7 < 0 )
LABEL_11:
      RoOriginateError((unsigned int)v7, 0);
    SysFreeString((BSTR)sourceString[0]);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x18003e910  mov     [rsp+arg_8], rsi
0x18003e915  push    rdi
0x18003e916  sub     rsp, 40h
0x18003e91a  xor     esi, esi
0x18003e91c  mov     rdi, r9
0x18003e91f  mov     eax, esi
0x18003e921  cmp     [r9], rax
0x18003e924  jnz     loc_18003E9AB
0x18003e92a  mov     rcx, [rcx+58h]
0x18003e92e  mov     r9d, r8d
0x18003e931  mov     [rsp+48h+sourceString], rsi
0x18003e936  lea     r8, [rsp+48h+sourceString]
0x18003e93b  mov     [rsp+48h+arg_0], rbx
0x18003e940  mov     rax, [rcx]
0x18003e943  mov     rax, [rax+18h]
0x18003e947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e94c  mov     ebx, eax
0x18003e94e  test    eax, eax
0x18003e950  js      short loc_18003E9C3
0x18003e952  mov     rax, [rsp+48h+sourceString]
0x18003e957  lea     rcx, word_1801758E4
0x18003e95e  test    rax, rax
0x18003e961  mov     [rsp+48h+string], rsi
0x18003e966  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18003e96d  cmovnz  rcx, rax; sourceString
0x18003e971  inc     rdx; length
0x18003e974  cmp     [rcx+rdx*2], si
0x18003e978  jnz     short loc_18003E971
0x18003e97a  lea     r8, [rsp+48h+string]; string
0x18003e97f  call    cs:__imp_WindowsCreateString
0x18003e985  mov     rcx, [rsp+48h+string]
0x18003e98a  mov     ebx, eax
0x18003e98c  xor     eax, eax
0x18003e98e  lock cmpxchg [rdi], rcx
0x18003e993  jnz     short loc_18003E9B6
0x18003e995  test    ebx, ebx
0x18003e997  js      short loc_18003E9C3
0x18003e999  mov     rcx, [rsp+48h+sourceString]; bstrString
0x18003e99e  call    cs:__imp_SysFreeString
0x18003e9a4  mov     eax, ebx
0x18003e9a6  mov     rbx, [rsp+48h+arg_0]
0x18003e9ab  mov     rsi, [rsp+48h+arg_8]
0x18003e9b0  add     rsp, 40h
0x18003e9b4  pop     rdi
0x18003e9b5  retn
0x18003e9b6  mov     rcx, [rsp+48h+string]; string
0x18003e9bb  call    cs:__imp_WindowsDeleteString
0x18003e9c1  jmp     short loc_18003E995
0x18003e9c3  xor     edx, edx
0x18003e9c5  mov     ecx, ebx
0x18003e9c7  call    cs:__imp_RoOriginateError
0x18003e9cd  jmp     short loc_18003E999
```
