# Rust_MsWansung_StringToUnicode

- ea: `0x18010de40`
- end: `0x18010df25`
- name: `Rust_MsWansung_StringToUnicode`
- size: `229`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1802e12a4`

## callees

- `0x18010de40`
- `0x180316ae0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010de9d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010deda`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010de9d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010deda`

## string_xrefs

- `0x18010def1`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x18010df0b`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
__int64 __fastcall Rust_MsWansung_StringToUnicode(__int64 lpMultiByteStr, __int64 cbMultiByte, WCHAR *a3, __int64 a4)
{
  int v5; // esi
  __int64 v6; // rdi
  __int64 v7; // r14
  int cchWideChar; // eax

  v5 = cbMultiByte;
  if ( cbMultiByte )
  {
    v6 = lpMultiByteStr;
    if ( !lpMultiByteStr )
    {
      try
      {
        core::panicking::panic(
          "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_"
          "utils\\src\\lib.rs",
          32,
          &off_1803491E0);
      }
      catch ( ... )
      {
        core::panicking::panic_cannot_unwind();
      }
    }
    if ( a4 )
      goto LABEL_4;
    return MultiByteToWideChar(0x3B5u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
  }
  v6 = 1;
  if ( !a4 )
    return MultiByteToWideChar(0x3B5u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
LABEL_4:
  if ( !a3 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_180348CA0);
  v7 = 0;
  cchWideChar = MultiByteToWideChar(0x3B5u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
  if ( cchWideChar )
    return MultiByteToWideChar(0x3B5u, 0, (LPCCH)v6, v5, a3, cchWideChar);
  return v7;
}

```

## disassembly

```asm
0x18010de40  push    rbp
0x18010de41  push    r14
0x18010de43  push    rsi
0x18010de44  push    rdi
0x18010de45  push    rbx
0x18010de46  sub     rsp, 40h
0x18010de4a  lea     rbp, [rsp+40h]
0x18010de4f  mov     [rbp+20h+var_28], 0FFFFFFFFFFFFFFFEh
0x18010de57  mov     rbx, r8
0x18010de5a  mov     rsi, rdx
0x18010de5d  test    rdx, rdx
0x18010de60  jz      short loc_18010DEB2
0x18010de62  mov     rdi, rcx
0x18010de65  test    rcx, rcx
0x18010de68  jz      loc_18010DEF1
0x18010de6e  test    r9, r9
0x18010de71  jz      short loc_18010DEBC
0x18010de73  test    rbx, rbx
0x18010de76  jz      loc_18010DF0B
0x18010de7c  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18010de84  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18010de8d  xor     r14d, r14d
0x18010de90  mov     ecx, 3B5h; CodePage
0x18010de95  xor     edx, edx; dwFlags
0x18010de97  mov     r8, rdi; lpMultiByteStr
0x18010de9a  mov     r9d, esi; cbMultiByte
0x18010de9d  call    cs:__imp_MultiByteToWideChar
0x18010dea3  test    eax, eax
0x18010dea5  jz      short loc_18010DEE3
0x18010dea7  mov     [rsp+60h+cchWideChar], eax
0x18010deab  mov     [rsp+60h+lpWideCharStr], rbx
0x18010deb0  jmp     short loc_18010DECD
0x18010deb2  mov     edi, 1
0x18010deb7  test    r9, r9
0x18010deba  jnz     short loc_18010DE73
0x18010debc  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18010dec4  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18010decd  mov     ecx, 3B5h; CodePage
0x18010ded2  xor     edx, edx; dwFlags
0x18010ded4  mov     r8, rdi; lpMultiByteStr
0x18010ded7  mov     r9d, esi; cbMultiByte
0x18010deda  call    cs:__imp_MultiByteToWideChar
0x18010dee0  movsxd  r14, eax
0x18010dee3  mov     rax, r14
0x18010dee6  add     rsp, 40h
0x18010deea  pop     rbx
0x18010deeb  pop     rdi
0x18010deec  pop     rsi
0x18010deed  pop     r14
0x18010deef  pop     rbp
0x18010def0  retn
0x18010def1  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18010def8  lea     r8, off_1803491E0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18010deff  mov     edx, 20h ; ' '
0x18010df04  call    core__panicking__panic
0x18010df09  jmp     short loc_18010DF23
0x18010df0b  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18010df12  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18010df19  mov     edx, 20h ; ' '
0x18010df1e  call    core__panicking__panic
0x18010df23  ud2
```
