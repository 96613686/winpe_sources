# Rust_MsPrc_StringToUnicode

- ea: `0x18010da80`
- end: `0x18010db65`
- name: `Rust_MsPrc_StringToUnicode`
- size: `229`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1802e11e4`

## callees

- `0x18010da80`
- `0x180316ae0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010dadd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010db1a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010dadd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18010db1a`

## string_xrefs

- `0x18010db31`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x18010db4b`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
__int64 __fastcall Rust_MsPrc_StringToUnicode(__int64 lpMultiByteStr, __int64 cbMultiByte, WCHAR *a3, __int64 a4)
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
    return MultiByteToWideChar(0x3A8u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
  }
  v6 = 1;
  if ( !a4 )
    return MultiByteToWideChar(0x3A8u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
LABEL_4:
  if ( !a3 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_180348CA0);
  v7 = 0;
  cchWideChar = MultiByteToWideChar(0x3A8u, 0, (LPCCH)v6, cbMultiByte, 0, 0);
  if ( cchWideChar )
    return MultiByteToWideChar(0x3A8u, 0, (LPCCH)v6, v5, a3, cchWideChar);
  return v7;
}

```

## disassembly

```asm
0x18010da80  push    rbp
0x18010da81  push    r14
0x18010da83  push    rsi
0x18010da84  push    rdi
0x18010da85  push    rbx
0x18010da86  sub     rsp, 40h
0x18010da8a  lea     rbp, [rsp+40h]
0x18010da8f  mov     [rbp+20h+var_28], 0FFFFFFFFFFFFFFFEh
0x18010da97  mov     rbx, r8
0x18010da9a  mov     rsi, rdx
0x18010da9d  test    rdx, rdx
0x18010daa0  jz      short loc_18010DAF2
0x18010daa2  mov     rdi, rcx
0x18010daa5  test    rcx, rcx
0x18010daa8  jz      loc_18010DB31
0x18010daae  test    r9, r9
0x18010dab1  jz      short loc_18010DAFC
0x18010dab3  test    rbx, rbx
0x18010dab6  jz      loc_18010DB4B
0x18010dabc  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18010dac4  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18010dacd  xor     r14d, r14d
0x18010dad0  mov     ecx, 3A8h; CodePage
0x18010dad5  xor     edx, edx; dwFlags
0x18010dad7  mov     r8, rdi; lpMultiByteStr
0x18010dada  mov     r9d, esi; cbMultiByte
0x18010dadd  call    cs:__imp_MultiByteToWideChar
0x18010dae3  test    eax, eax
0x18010dae5  jz      short loc_18010DB23
0x18010dae7  mov     [rsp+60h+cchWideChar], eax
0x18010daeb  mov     [rsp+60h+lpWideCharStr], rbx
0x18010daf0  jmp     short loc_18010DB0D
0x18010daf2  mov     edi, 1
0x18010daf7  test    r9, r9
0x18010dafa  jnz     short loc_18010DAB3
0x18010dafc  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18010db04  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18010db0d  mov     ecx, 3A8h; CodePage
0x18010db12  xor     edx, edx; dwFlags
0x18010db14  mov     r8, rdi; lpMultiByteStr
0x18010db17  mov     r9d, esi; cbMultiByte
0x18010db1a  call    cs:__imp_MultiByteToWideChar
0x18010db20  movsxd  r14, eax
0x18010db23  mov     rax, r14
0x18010db26  add     rsp, 40h
0x18010db2a  pop     rbx
0x18010db2b  pop     rdi
0x18010db2c  pop     rsi
0x18010db2d  pop     r14
0x18010db2f  pop     rbp
0x18010db30  retn
0x18010db31  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18010db38  lea     r8, off_1803491E0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18010db3f  mov     edx, 20h ; ' '
0x18010db44  call    core__panicking__panic
0x18010db49  jmp     short loc_18010DB63
0x18010db4b  lea     rcx, aAssertionFaile_0; "assertion failed: !ptr.is_null()d:\\os"...
0x18010db52  lea     r8, off_180348CA0; "d:\\os\\src\\onecoreuap\\windows\\direc"...
0x18010db59  mov     edx, 20h ; ' '
0x18010db5e  call    core__panicking__panic
0x18010db63  ud2
```
