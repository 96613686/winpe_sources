# DWriteCore::Binding::Windows::GetSystemFontsPath(void)

- ea: `0x180290c90`
- end: `0x180290d92`
- name: `?GetSystemFontsPath@Windows@Binding@DWriteCore@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1802929f0`

## callees

- `0x180212490`
- `0x18029032c`
- `0x180290c90`
- `0x180290fac`
- `0x1802911d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180290d63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180290d63`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180290cfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180290d20`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180290cfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180290d20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DWriteCore::Binding::Windows::GetSystemFontsPath(__int64 a1)
{
  UINT WindowsDirectoryW; // eax
  DWriteCore::Binding::Windows *v3; // rcx
  _QWORD v5[5]; // [rsp+28h] [rbp-D8h] BYREF
  LPWSTR lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  UINT uSize[2]; // [rsp+58h] [rbp-A8h]
  void *Block; // [rsp+60h] [rbp-A0h]
  int v9; // [rsp+68h] [rbp-98h]
  int v10; // [rsp+70h] [rbp-90h]
  char v11; // [rsp+78h] [rbp-88h] BYREF

  v5[4] = a1;
  lpBuffer = (LPWSTR)&v11;
  *(_QWORD *)uSize = 0;
  Block = 0;
  v9 = 0;
  v10 = 128;
  DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::resize(&lpBuffer, 128);
  WindowsDirectoryW = GetWindowsDirectoryW(lpBuffer, uSize[0]);
  if ( WindowsDirectoryW >= uSize[0] )
  {
    DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::resize(&lpBuffer, WindowsDirectoryW + 1);
    WindowsDirectoryW = GetWindowsDirectoryW(lpBuffer, uSize[0]);
  }
  if ( !WindowsDirectoryW )
    DWriteCore::Binding::Windows::ThrowLastError(v3);
  v5[0] = lpBuffer;
  v5[1] = WindowsDirectoryW;
  v5[2] = L"\\Fonts\\";
  v5[3] = 7;
  DWriteCore::StringExprInternal::StringExpr<DWriteCore::StringExprInternal::SumBuilder<DWriteCore::StringExprInternal::StringBuilder<wchar_t>,DWriteCore::StringExprInternal::StringBuilder<wchar_t>>>::operator<wchar_t> std::wstring(
    v5,
    a1);
  free(Block);
  return a1;
}

```

## disassembly

```asm
0x180290c90  mov     [rsp-8+arg_8], rbx
0x180290c95  push    rbp
0x180290c96  lea     rbp, [rsp-90h]
0x180290c9e  sub     rsp, 190h
0x180290ca5  mov     rax, cs:__security_cookie
0x180290cac  xor     rax, rsp
0x180290caf  mov     [rbp+90h+var_10], rax
0x180290cb6  mov     rbx, rcx
0x180290cb9  mov     [rsp+190h+var_148], rcx
0x180290cbe  lea     rax, [rsp+190h+var_118]
0x180290cc3  mov     [rsp+190h+lpBuffer], rax
0x180290cc8  mov     qword ptr [rsp+190h+uSize], 0
0x180290cd1  mov     [rsp+190h+Block], 0
0x180290cda  mov     [rsp+190h+var_128], 0
0x180290ce2  mov     edx, 80h
0x180290ce7  mov     [rsp+190h+var_120], edx
0x180290ceb  lea     rcx, [rsp+190h+lpBuffer]
0x180290cf0  call    ?resize@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAX_K@Z; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::resize(unsigned __int64)
0x180290cf5  mov     edx, [rsp+190h+uSize]; uSize
0x180290cf9  mov     rcx, [rsp+190h+lpBuffer]; lpBuffer
0x180290cfe  call    cs:__imp_GetWindowsDirectoryW
0x180290d04  cmp     eax, [rsp+190h+uSize]
0x180290d08  jb      short loc_180290D26
0x180290d0a  lea     edx, [rax+1]
0x180290d0d  lea     rcx, [rsp+190h+lpBuffer]
0x180290d12  call    ?resize@?$ScopedArrayWithFixedBuffer@_W@ScopedArrayInternal@DWriteCore@@QEAAX_K@Z; DWriteCore::ScopedArrayInternal::ScopedArrayWithFixedBuffer<wchar_t>::resize(unsigned __int64)
0x180290d17  mov     edx, [rsp+190h+uSize]; uSize
0x180290d1b  mov     rcx, [rsp+190h+lpBuffer]; lpBuffer
0x180290d20  call    cs:__imp_GetWindowsDirectoryW
0x180290d26  test    eax, eax
0x180290d28  jz      short loc_180290D8C
0x180290d2a  mov     rcx, [rsp+190h+lpBuffer]
0x180290d2f  mov     [rsp+190h+var_168], rcx
0x180290d34  mov     ecx, eax
0x180290d36  mov     [rsp+190h+var_160], rcx
0x180290d3b  lea     rax, aFonts_1; "\\Fonts\\"
0x180290d42  mov     [rsp+190h+var_158], rax
0x180290d47  mov     [rsp+190h+var_150], 7
0x180290d50  mov     rdx, rbx
0x180290d53  lea     rcx, [rsp+190h+var_168]
0x180290d58  call    ??$?B_W@?$StringExpr@V?$SumBuilder@V?$StringBuilder@_W@StringExprInternal@DWriteCore@@V123@@StringExprInternal@DWriteCore@@@StringExprInternal@DWriteCore@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; DWriteCore::StringExprInternal::StringExpr<DWriteCore::StringExprInternal::SumBuilder<DWriteCore::StringExprInternal::StringBuilder<wchar_t>,DWriteCore::StringExprInternal::StringBuilder<wchar_t>>>::operator<wchar_t> std::wstring(void)
0x180290d5d  nop
0x180290d5e  mov     rcx, [rsp+190h+Block]; Block
0x180290d63  call    cs:__imp_free
0x180290d69  mov     rax, rbx
0x180290d6c  mov     rcx, [rbp+90h+var_10]
0x180290d73  xor     rcx, rsp; StackCookie
0x180290d76  call    __security_check_cookie
0x180290d7b  mov     rbx, [rsp+190h+arg_8]
0x180290d83  add     rsp, 190h
0x180290d8a  pop     rbp
0x180290d8b  retn
0x180290d8c  call    ?ThrowLastError@Windows@Binding@DWriteCore@@YAXXZ; DWriteCore::Binding::Windows::ThrowLastError(void)
```
