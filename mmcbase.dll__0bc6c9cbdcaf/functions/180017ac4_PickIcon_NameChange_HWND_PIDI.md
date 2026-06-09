# PickIcon_NameChange(HWND__ *,PIDI *)

- ea: `0x180017ac4`
- end: `0x180017b53`
- name: `?PickIcon_NameChange@@YAHPEAUHWND__@@PEAUPIDI@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(HWND, struct PIDI *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017550`
- `0x180017e40`

## callees

- `0x180017ac4`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017b16`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017b16`
- `USER32!GetDlgItemTextW` at `0x180017af2`
- `USER32!GetDlgItemTextW` at `0x180017af2`

## pseudocode

```c
__int64 __fastcall PickIcon_NameChange(HWND a1, const WCHAR *a2)
{
  int v3; // eax
  int v4; // edx
  unsigned int v5; // ecx
  __int64 result; // rax
  WCHAR String[264]; // [rsp+30h] [rbp-228h] BYREF

  GetDlgItemTextW(a1, 1005, String, 260);
  v3 = CompareStringW(0x400u, 0, String, -1, a2 + 12, -1);
  v4 = v3;
  if ( v3 == 1004 )
    return 1;
  v5 = v3 - 2;
  result = 1;
  if ( v4 != 87 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x180017ac4  push    rbx
0x180017ac6  sub     rsp, 250h
0x180017acd  mov     rax, cs:__security_cookie
0x180017ad4  xor     rax, rsp
0x180017ad7  mov     [rsp+258h+var_18], rax
0x180017adf  mov     rbx, rdx
0x180017ae2  lea     r8, [rsp+258h+String]; lpString
0x180017ae7  mov     edx, 3EDh; nIDDlgItem
0x180017aec  mov     r9d, 104h; cchMax
0x180017af2  call    cs:__imp_GetDlgItemTextW
0x180017af8  or      r9d, 0FFFFFFFFh; cchCount1
0x180017afc  lea     rax, [rbx+18h]
0x180017b00  mov     [rsp+258h+cchCount2], r9d; cchCount2
0x180017b05  lea     r8, [rsp+258h+String]; lpString1
0x180017b0a  xor     edx, edx; dwCmpFlags
0x180017b0c  mov     [rsp+258h+lpString2], rax; lpString2
0x180017b11  mov     ecx, 400h; Locale
0x180017b16  call    cs:__imp_CompareStringW
0x180017b1c  mov     edx, eax
0x180017b1e  cmp     eax, 3ECh
0x180017b23  jz      short loc_180017B35
0x180017b25  lea     ecx, [rax-2]
0x180017b28  cmp     edx, 57h ; 'W'
0x180017b2b  mov     eax, 1
0x180017b30  cmovnz  eax, ecx
0x180017b33  jmp     short loc_180017B3A
0x180017b35  mov     eax, 1
0x180017b3a  mov     rcx, [rsp+258h+var_18]
0x180017b42  xor     rcx, rsp; StackCookie
0x180017b45  call    __security_check_cookie
0x180017b4a  add     rsp, 250h
0x180017b51  pop     rbx
0x180017b52  retn
```
