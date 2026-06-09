# CWinRTextCharacterFormat::get_LanguageTag(HSTRING__ * *)

- ea: `0x1801e6650`
- end: `0x1801e66eb`
- name: `?get_LanguageTag@CWinRTextCharacterFormat@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `155`
- prototype: `int(CWinRTextCharacterFormat *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18013ce80`
- `0x1801e6650`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1801e66a2`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1801e66a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e66be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e66be`

## pseudocode

```c
HRESULT __fastcall CWinRTextCharacterFormat::get_LanguageTag(CWinRTextCharacterFormat *this, HSTRING *a2)
{
  __int64 v2; // rcx
  HRESULT result; // eax
  int v5; // eax
  LCID Locale[4]; // [rsp+20h] [rbp-D8h] BYREF
  WCHAR Name[88]; // [rsp+30h] [rbp-C8h] BYREF

  v2 = *((_QWORD *)this + 1);
  Locale[0] = 0;
  result = (*(__int64 (__fastcall **)(__int64, LCID *))(*(_QWORD *)v2 + 272LL))(v2, Locale);
  if ( result >= 0 )
  {
    v5 = LCIDToLocaleName(Locale[0], Name, 85, 0);
    if ( v5 <= 1 )
      return -2147467259;
    else
      return WindowsCreateString(Name, v5 - 1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x1801e6650  push    rbx
0x1801e6652  sub     rsp, 0F0h
0x1801e6659  mov     rax, cs:__security_cookie
0x1801e6660  xor     rax, rsp
0x1801e6663  mov     [rsp+0F8h+var_18], rax
0x1801e666b  mov     rcx, [rcx+8]
0x1801e666f  mov     rbx, rdx
0x1801e6672  mov     [rsp+0F8h+Locale], 0
0x1801e667a  lea     rdx, [rsp+0F8h+Locale]
0x1801e667f  mov     rax, [rcx]
0x1801e6682  mov     rax, [rax+110h]
0x1801e6689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e668e  test    eax, eax
0x1801e6690  js      short loc_1801E66D1
0x1801e6692  mov     ecx, [rsp+0F8h+Locale]; Locale
0x1801e6696  lea     rdx, [rsp+0F8h+Name]; lpName
0x1801e669b  xor     r9d, r9d; dwFlags
0x1801e669e  lea     r8d, [r9+55h]; cchName
0x1801e66a2  call    cs:__imp_LCIDToLocaleName
0x1801e66a9  nop     dword ptr [rax+rax+00h]
0x1801e66ae  cmp     eax, 1
0x1801e66b1  jle     short loc_1801E66CC
0x1801e66b3  lea     edx, [rax-1]; length
0x1801e66b6  mov     r8, rbx; string
0x1801e66b9  lea     rcx, [rsp+0F8h+Name]; sourceString
0x1801e66be  call    cs:__imp_WindowsCreateString
0x1801e66c5  nop     dword ptr [rax+rax+00h]
0x1801e66ca  jmp     short loc_1801E66D1
0x1801e66cc  mov     eax, 80004005h
0x1801e66d1  mov     rcx, [rsp+0F8h+var_18]
0x1801e66d9  xor     rcx, rsp; StackCookie
0x1801e66dc  call    __security_check_cookie
0x1801e66e1  add     rsp, 0F0h
0x1801e66e8  pop     rbx
0x1801e66e9  retn
```
