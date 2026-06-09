# SetMountOptions

- ea: `0x18000e454`
- end: `0x18000e4ea`
- name: `SetMountOptions`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000be24`

## callees

- `0x18000d884`
- `0x18000dc1c`
- `0x18000dd70`
- `0x18000df74`
- `0x18000e094`
- `0x18000e4f0`
- `0x18000e87c`
- `0x18000e984`
- `0x18000ebc4`
- `0x18000efac`

## pseudocode

```c
__int64 __fastcall SetMountOptions(__int64 a1, __int64 a2, HINSTANCE *a3)
{
  HINSTANCE v3; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx

  v3 = *a3;
  SetVersion3AndLocking(a1, a2, a3);
  SetBufferSizes(
    HKEY_LOCAL_MACHINE,
    (wchar_t *)L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
    (__int64)v3);
  SetTimeout(
    HKEY_LOCAL_MACHINE,
    (wchar_t *)L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
    (__int64)v3);
  SetRetrans(
    HKEY_LOCAL_MACHINE,
    (wchar_t *)L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
    (__int64)v3);
  SetFilenameOptions(v6, v5, (__int64)v3);
  SetMountType(
    HKEY_LOCAL_MACHINE,
    (wchar_t *)L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
    (__int64)a3);
  SetCacheOptions(v8, v7, (BYTE *)a3);
  SetFileAccess(v10, v9, (__int64)v3);
  SetAnon(
    HKEY_LOCAL_MACHINE,
    (wchar_t *)L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
    (__int64)v3);
  return SetSecFlags(
           HKEY_LOCAL_MACHINE,
           (wchar_t *)L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default",
           (__int64)v3);
}

```

## disassembly

```asm
0x18000e454  push    rbx
0x18000e456  push    rbp
0x18000e457  push    rsi
0x18000e458  push    rdi
0x18000e459  sub     rsp, 28h
0x18000e45d  mov     rdi, [r8]
0x18000e460  mov     rbx, r8
0x18000e463  call    SetVersion3AndLocking
0x18000e468  lea     rbp, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000e46f  mov     rsi, 0FFFFFFFF80000002h
0x18000e476  mov     rdx, rbp; Source
0x18000e479  mov     rcx, rsi; hKey
0x18000e47c  mov     r8, rdi
0x18000e47f  call    SetBufferSizes
0x18000e484  mov     r8, rdi
0x18000e487  mov     rdx, rbp; Source
0x18000e48a  mov     rcx, rsi; hKey
0x18000e48d  call    SetTimeout
0x18000e492  mov     r8, rdi
0x18000e495  mov     rdx, rbp; Source
0x18000e498  mov     rcx, rsi; hKey
0x18000e49b  call    SetRetrans
0x18000e4a0  mov     r8, rdi
0x18000e4a3  call    SetFilenameOptions
0x18000e4a8  mov     r8, rbx
0x18000e4ab  mov     rdx, rbp; Source
0x18000e4ae  mov     rcx, rsi; hKey
0x18000e4b1  call    SetMountType
0x18000e4b6  mov     r8, rbx
0x18000e4b9  call    SetCacheOptions
0x18000e4be  mov     r8, rdi
0x18000e4c1  call    SetFileAccess
0x18000e4c6  mov     r8, rdi
0x18000e4c9  mov     rdx, rbp; Source
0x18000e4cc  mov     rcx, rsi; hKey
0x18000e4cf  call    SetAnon
0x18000e4d4  mov     r8, rdi
0x18000e4d7  mov     rdx, rbp; Source
0x18000e4da  mov     rcx, rsi; hKey
0x18000e4dd  add     rsp, 28h
0x18000e4e1  pop     rdi
0x18000e4e2  pop     rsi
0x18000e4e3  pop     rbp
0x18000e4e4  pop     rbx
0x18000e4e5  jmp     SetSecFlags
```
