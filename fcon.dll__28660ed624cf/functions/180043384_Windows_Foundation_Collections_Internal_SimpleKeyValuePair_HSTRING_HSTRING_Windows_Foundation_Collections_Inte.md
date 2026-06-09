# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Initialize(HSTRING__ * const &,HSTRING__ * const &)

- ea: `0x180043384`
- end: `0x180043409`
- name: `?Initialize@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@AEAAJAEBQEAUHSTRING__@@0@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180044370`

## callees

- `0x18002bfcc`
- `0x180043384`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800433ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800433f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800433ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800433f8`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Initialize(
        __int64 a1)
{
  HSTRING v2; // rcx
  HSTRING v3; // rcx
  HSTRING string; // [rsp+20h] [rbp-18h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-10h] BYREF

  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&newString);
  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
  v2 = *(HSTRING *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = newString;
  newString = v2;
  v3 = *(HSTRING *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = string;
  string = v3;
  WindowsDeleteString(v3);
  WindowsDeleteString(newString);
  return 0;
}

```

## disassembly

```asm
0x180043384  push    rbp
0x180043386  push    rbx
0x180043387  push    rsi
0x180043388  push    rdi
0x180043389  mov     rbp, rsp
0x18004338c  sub     rsp, 38h
0x180043390  mov     rsi, r8
0x180043393  mov     [rbp+arg_18], 0
0x18004339a  mov     rdi, rcx
0x18004339d  lea     r8, [rbp+arg_18]
0x1800433a1  lea     rcx, [rbp+newString]; newString
0x1800433a5  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x1800433aa  mov     ebx, [rbp+arg_18]
0x1800433ad  test    ebx, ebx
0x1800433af  js      short loc_1800433F4
0x1800433b1  lea     r8, [rbp+arg_18]
0x1800433b5  mov     rdx, rsi
0x1800433b8  lea     rcx, [rbp+string]; newString
0x1800433bc  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x1800433c1  mov     ebx, [rbp+arg_18]
0x1800433c4  test    ebx, ebx
0x1800433c6  js      short loc_1800433EA
0x1800433c8  mov     rcx, [rdi+20h]
0x1800433cc  mov     rax, [rbp+newString]
0x1800433d0  mov     [rdi+20h], rax
0x1800433d4  mov     rax, [rbp+string]
0x1800433d8  mov     [rbp+newString], rcx
0x1800433dc  mov     rcx, [rdi+28h]
0x1800433e0  mov     [rdi+28h], rax
0x1800433e4  mov     [rbp+string], rcx
0x1800433e8  jmp     short loc_1800433EE
0x1800433ea  mov     rcx, [rbp+string]; string
0x1800433ee  call    cs:__imp_WindowsDeleteString
0x1800433f4  mov     rcx, [rbp+newString]; string
0x1800433f8  call    cs:__imp_WindowsDeleteString
0x1800433fe  mov     eax, ebx
0x180043400  add     rsp, 38h
0x180043404  pop     rdi
0x180043405  pop     rsi
0x180043406  pop     rbx
0x180043407  pop     rbp
0x180043408  retn
```
