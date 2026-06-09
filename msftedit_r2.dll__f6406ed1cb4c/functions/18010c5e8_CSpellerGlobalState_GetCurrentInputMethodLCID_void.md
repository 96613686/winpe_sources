# CSpellerGlobalState::GetCurrentInputMethodLCID(void)

- ea: `0x18010c5e8`
- end: `0x18010c6e7`
- name: `?GetCurrentInputMethodLCID@CSpellerGlobalState@@QEBAKXZ`
- size: `255`
- prototype: `unsigned int __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800d7998`
- `0x18010c330`
- `0x180274b8c`
- `0x18027b7a0`

## callees

- `0x18010c5e8`
- `0x18013ce80`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18010c689`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18010c689`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18010c6a0`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18010c6a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010c671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010c671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010c6b3`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x18010c611`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x18010c611`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::GetCurrentInputMethodLCID(CSpellerGlobalState *this)
{
  unsigned __int16 KeyboardLayout; // ax
  LCID v3; // esi
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  HSTRING string[2]; // [rsp+20h] [rbp-D8h] BYREF
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-C8h] BYREF

  KeyboardLayout = (unsigned __int16)GetKeyboardLayout(0);
  v3 = KeyboardLayout;
  if ( !KeyboardLayout )
  {
    v4 = *((_QWORD *)this + 37);
    string[0] = 0;
    v5 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v4 + 56LL);
    WindowsDeleteString(0);
    string[0] = 0;
    if ( v5(v4, string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      if ( ResolveLocaleName(StringRawBuffer, LocaleName, v3 + 85) )
        v3 = LocaleNameToLCID(LocaleName, 0);
    }
    WindowsDeleteString(string[0]);
  }
  return v3;
}

```

## disassembly

```asm
0x18010c5e8  mov     [rsp+arg_8], rbx
0x18010c5ed  mov     [rsp+arg_10], rsi
0x18010c5f2  push    rdi
0x18010c5f3  sub     rsp, 0F0h
0x18010c5fa  mov     rax, cs:__security_cookie
0x18010c601  xor     rax, rsp
0x18010c604  mov     [rsp+0F8h+var_18], rax
0x18010c60c  mov     rdi, rcx
0x18010c60f  xor     ecx, ecx; idThread
0x18010c611  call    cs:__imp_GetKeyboardLayout
0x18010c618  nop     dword ptr [rax+rax+00h]
0x18010c61d  movzx   esi, ax
0x18010c620  test    esi, esi
0x18010c622  jnz     loc_18010C6BF
0x18010c628  mov     rdi, [rdi+128h]
0x18010c62f  xor     ecx, ecx; string
0x18010c631  mov     [rsp+0F8h+string], 0
0x18010c63a  mov     rax, [rdi]
0x18010c63d  mov     rbx, [rax+38h]
0x18010c641  call    cs:__imp_WindowsDeleteString
0x18010c648  nop     dword ptr [rax+rax+00h]
0x18010c64d  lea     rdx, [rsp+0F8h+string]
0x18010c652  mov     [rsp+0F8h+string], 0
0x18010c65b  mov     rcx, rdi
0x18010c65e  mov     rax, rbx
0x18010c661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c666  test    eax, eax
0x18010c668  js      short loc_18010C6AE
0x18010c66a  mov     rcx, [rsp+0F8h+string]; string
0x18010c66f  xor     edx, edx; length
0x18010c671  call    cs:__imp_WindowsGetStringRawBuffer
0x18010c678  nop     dword ptr [rax+rax+00h]
0x18010c67d  mov     rcx, rax; lpNameToResolve
0x18010c680  lea     r8d, [rsi+55h]; cchLocaleName
0x18010c684  lea     rdx, [rsp+0F8h+LocaleName]; lpLocaleName
0x18010c689  call    cs:__imp_ResolveLocaleName
0x18010c690  nop     dword ptr [rax+rax+00h]
0x18010c695  test    eax, eax
0x18010c697  jz      short loc_18010C6AE
0x18010c699  xor     edx, edx; dwFlags
0x18010c69b  lea     rcx, [rsp+0F8h+LocaleName]; lpName
0x18010c6a0  call    cs:__imp_LocaleNameToLCID
0x18010c6a7  nop     dword ptr [rax+rax+00h]
0x18010c6ac  mov     esi, eax
0x18010c6ae  mov     rcx, [rsp+0F8h+string]; string
0x18010c6b3  call    cs:__imp_WindowsDeleteString
0x18010c6ba  nop     dword ptr [rax+rax+00h]
0x18010c6bf  mov     eax, esi
0x18010c6c1  mov     rcx, [rsp+0F8h+var_18]
0x18010c6c9  xor     rcx, rsp; StackCookie
0x18010c6cc  call    __security_check_cookie
0x18010c6d1  lea     r11, [rsp+0F8h+var_8]
0x18010c6d9  mov     rbx, [r11+18h]
0x18010c6dd  mov     rsi, [r11+20h]
0x18010c6e1  mov     rsp, r11
0x18010c6e4  pop     rdi
0x18010c6e5  retn
```
