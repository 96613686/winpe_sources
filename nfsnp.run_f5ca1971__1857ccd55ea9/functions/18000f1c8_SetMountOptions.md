# SetMountOptions

- ea: `0x18000f1c8`
- end: `0x18000f25e`
- name: `SetMountOptions`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c738`

## callees

- `0x18000e4a8`
- `0x18000e8ac`
- `0x18000ea28`
- `0x18000ec64`
- `0x18000eda4`
- `0x18000f264`
- `0x18000f64c`
- `0x18000f774`
- `0x18000f9f4`
- `0x18000fe44`

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
0x18000f1c8  push    rbx
0x18000f1ca  push    rbp
0x18000f1cb  push    rsi
0x18000f1cc  push    rdi
0x18000f1cd  sub     rsp, 28h
0x18000f1d1  mov     rdi, [r8]
0x18000f1d4  mov     rbx, r8
0x18000f1d7  call    SetVersion3AndLocking
0x18000f1dc  lea     rbp, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000f1e3  mov     rsi, 0FFFFFFFF80000002h
0x18000f1ea  mov     rdx, rbp; Source
0x18000f1ed  mov     rcx, rsi; hKey
0x18000f1f0  mov     r8, rdi
0x18000f1f3  call    SetBufferSizes
0x18000f1f8  mov     r8, rdi
0x18000f1fb  mov     rdx, rbp; Source
0x18000f1fe  mov     rcx, rsi; hKey
0x18000f201  call    SetTimeout
0x18000f206  mov     r8, rdi
0x18000f209  mov     rdx, rbp; Source
0x18000f20c  mov     rcx, rsi; hKey
0x18000f20f  call    SetRetrans
0x18000f214  mov     r8, rdi
0x18000f217  call    SetFilenameOptions
0x18000f21c  mov     r8, rbx
0x18000f21f  mov     rdx, rbp; Source
0x18000f222  mov     rcx, rsi; hKey
0x18000f225  call    SetMountType
0x18000f22a  mov     r8, rbx
0x18000f22d  call    SetCacheOptions
0x18000f232  mov     r8, rdi
0x18000f235  call    SetFileAccess
0x18000f23a  mov     r8, rdi
0x18000f23d  mov     rdx, rbp; Source
0x18000f240  mov     rcx, rsi; hKey
0x18000f243  call    SetAnon
0x18000f248  mov     r8, rdi
0x18000f24b  mov     rdx, rbp; Source
0x18000f24e  mov     rcx, rsi; hKey
0x18000f251  add     rsp, 28h
0x18000f255  pop     rdi
0x18000f256  pop     rsi
0x18000f257  pop     rbp
0x18000f258  pop     rbx
0x18000f259  jmp     SetSecFlags
```
