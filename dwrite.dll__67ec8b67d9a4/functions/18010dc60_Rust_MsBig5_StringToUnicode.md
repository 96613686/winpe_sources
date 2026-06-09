# Rust_MsBig5_StringToUnicode

- ea: `0x18010dc60`
- end: `0x18010dd45`
- name: `Rust_MsBig5_StringToUnicode`
- size: `229`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1802e1124`

## callees

- `0x18010dc60`
- `0x180316ae0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010dcbd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010dcfa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010dcbd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010dcfa`

## string_xrefs

- `0x18010dd11`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x18010dd2b`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
__int64 __fastcall Rust_MsBig5_StringToUnicode(__int64 lpMultiByteStr, __int64 cbMultiByte, WCHAR *a3, __int64 a4)
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
    return MultiByteToWideChar(0x3B6u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
  }
  v6 = 1;
  if ( !a4 )
    return MultiByteToWideChar(0x3B6u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
LABEL_4:
  if ( !a3 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_180348CA0);
  v7 = 0;
  cchWideChar = MultiByteToWideChar(0x3B6u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
  if ( cchWideChar )
    return MultiByteToWideChar(0x3B6u, 0, (LPCCH)v6, v5, a3, cchWideChar);
  return v7;
}

```

## disassembly

```asm
0x18010dc60  push    rbp
0x18010dc61  push    r14
0x18010dc63  push    rsi
0x18010dc64  push    rdi
0x18010dc65  push    rbx
0x18010dc66  sub     rsp, 40h
0x18010dc6a  lea     rbp, [rsp+40h]
0x18010dc6f  mov     [rbp+20h+var_28], 0FFFFFFFFFFFFFFFEh
0x18010dc77  mov     rbx, r8
0x18010dc7a  mov     rsi, rdx
0x18010dc7d  test    rdx, rdx
0x18010dc80  jz      short loc_18010DCD2
0x18010dc82  mov     rdi, rcx
0x18010dc85  test    rcx, rcx
0x18010dc88  jz      loc_18010DD11
0x18010dc8e  test    r9, r9
0x18010dc91  jz      short loc_18010DCDC
0x18010dc93  test    rbx, rbx
0x18010dc96  jz      loc_18010DD2B
0x18010dc9c  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18010dca4  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18010dcad  xor     r14d, r14d
0x18010dcb0  mov     ecx, 3B6h; CodePage
0x18010dcb5  xor     edx, edx; dwFlags
0x18010dcb7  mov     r8, rdi; lpMultiByteStr
0x18010dcba  mov     r9d, esi; cbMultiByte
0x18010dcbd  call    cs:__imp_MultiByteToWideChar
0x18010dcc3  test    eax, eax
0x18010dcc5  jz      short loc_18010DD03
0x18010dcc7  mov     [rsp+60h+cchWideChar], eax
0x18010dccb  mov     [rsp+60h+lpWideCharStr], rbx
0x18010dcd0  jmp     short loc_18010DCED
0x18010dcd2  mov     edi, 1
0x18010dcd7  test    r9, r9
0x18010dcda  jnz     short loc_18010DC93
0x18010dcdc  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18010dce4  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18010dced  mov     ecx, 3B6h; CodePage
0x18010dcf2  xor     edx, edx; dwFlags
0x18010dcf4  mov     r8, rdi; lpMultiByteStr
0x18010dcf7  mov     r9d, esi; cbMultiByte
0x18010dcfa  call    cs:__imp_MultiByteToWideChar
0x18010dd00  movsxd  r14, eax
0x18010dd03  mov     rax, r14
0x18010dd06  add     rsp, 40h
0x18010dd0a  pop     rbx
0x18010dd0b  pop     rdi
0x18010dd0c  pop     rsi
0x18010dd0d  pop     r14
0x18010dd0f  pop     rbp
0x18010dd10  retn
0x18010dd11  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18010dd18  lea     r8, off_1803491E0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18010dd1f  mov     edx, 20h ; ' '
0x18010dd24  call    core__panicking__panic
0x18010dd29  jmp     short loc_18010DD43
0x18010dd2b  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18010dd32  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18010dd39  mov     edx, 20h ; ' '
0x18010dd3e  call    core__panicking__panic
0x18010dd43  ud2
```
