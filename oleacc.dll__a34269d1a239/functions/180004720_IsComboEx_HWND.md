# IsComboEx(HWND__ *)

- ea: `0x180004720`
- end: `0x1800047bd`
- name: `?IsComboEx@@YAHPEAUHWND__@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002dd4`
- `0x180003c18`
- `0x180003d54`
- `0x180003f38`
- `0x1800040d8`
- `0x180004218`
- `0x1800043b8`
- `0x180004550`
- `0x1800046e0`
- `0x180029610`

## callees

- `0x180004720`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004789`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004789`
- `USER32!GetClassNameW` at `0x1800047b5`
- `USER32!GetClassNameW` at `0x1800047b5`

## string_xrefs

- `0x180004760`: `ComboBoxEx32`

## pseudocode

```c
_BOOL8 __fastcall IsComboEx(HWND a1)
{
  int WindowClass; // eax
  WCHAR String1[128]; // [rsp+30h] [rbp-118h] BYREF

  String1[0] = 0;
  if ( lpfnRealGetWindowClass )
    WindowClass = lpfnRealGetWindowClass(a1, String1, 0x80u);
  else
    WindowClass = GetClassNameW(a1, String1, 128);
  return WindowClass && CompareStringW(0x7Fu, 1u, String1, -1, L"ComboBoxEx32", -1) == 2;
}

```

## disassembly

```asm
0x180004720  sub     rsp, 148h
0x180004727  mov     rax, cs:__security_cookie
0x18000472e  xor     rax, rsp
0x180004731  mov     [rsp+148h+var_18], rax
0x180004739  xor     eax, eax
0x18000473b  lea     rdx, [rsp+148h+String1]; lpClassName
0x180004740  mov     [rsp+148h+String1], ax
0x180004745  mov     r8d, 80h; nMaxCount
0x18000474b  mov     rax, cs:?lpfnRealGetWindowClass@@3P6AIPEAUHWND__@@PEAGI@ZEA; uint (*lpfnRealGetWindowClass)(HWND__ *,ushort *,uint)
0x180004752  test    rax, rax
0x180004755  jz      short loc_1800047B5
0x180004757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475c  test    eax, eax
0x18000475e  jz      short loc_1800047B1
0x180004760  lea     rax, String2; "ComboBoxEx32"
0x180004767  mov     [rsp+148h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000476f  mov     r9d, 0FFFFFFFFh; cchCount1
0x180004775  mov     [rsp+148h+lpString2], rax; lpString2
0x18000477a  lea     r8, [rsp+148h+String1]; lpString1
0x18000477f  mov     edx, 1; dwCmpFlags
0x180004784  mov     ecx, 7Fh; Locale
0x180004789  call    cs:__imp_CompareStringW
0x18000478f  cmp     eax, 2
0x180004792  jnz     short loc_1800047B1
0x180004794  mov     eax, 1
0x180004799  mov     rcx, [rsp+148h+var_18]
0x1800047a1  xor     rcx, rsp; StackCookie
0x1800047a4  call    __security_check_cookie
0x1800047a9  add     rsp, 148h
0x1800047b0  retn
0x1800047b1  xor     eax, eax
0x1800047b3  jmp     short loc_180004799
0x1800047b5  call    cs:__imp_GetClassNameW
0x1800047bb  jmp     short loc_18000475C
```
