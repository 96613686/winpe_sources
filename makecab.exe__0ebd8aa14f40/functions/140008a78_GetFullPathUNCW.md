# GetFullPathUNCW

- ea: `0x140008a78`
- end: `0x140008b8a`
- name: `GetFullPathUNCW`
- size: `274`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14000488c`
- `0x140005c80`
- `0x14000895c`
- `0x140008b90`
- `0x140009454`

## callees

- `0x140008620`
- `0x140008a78`
- `0x14000e450`
- `0x14000e4e0`

## import_xrefs

- `msvcrt!memmove_s` at `0x140008b2e`
- `msvcrt!memmove_s` at `0x140008b2e`
- `KERNEL32!MultiByteToWideChar` at `0x140008ac6`
- `KERNEL32!MultiByteToWideChar` at `0x140008ac6`
- `KERNEL32!GetFullPathNameW` at `0x140008add`
- `KERNEL32!GetFullPathNameW` at `0x140008add`

## string_xrefs

- `0x140008b4c`: `Cannot open file: %1`

## pseudocode

```c
__int64 __fastcall GetFullPathUNCW(const CHAR *a1, WCHAR *a2, __int64 a3, __int64 a4)
{
  DWORD FullPathNameW; // eax
  int v8; // eax
  const char *v10; // rdx
  WCHAR WideCharStr[4096]; // [rsp+30h] [rbp-2028h] BYREF

  if ( !MultiByteToWideChar(0, 0, a1, -1, WideCharStr, 4096)
    || (FullPathNameW = GetFullPathNameW(WideCharStr, 0x1000u, a2, 0)) == 0 )
  {
LABEL_13:
    v10 = "Cannot open file: %1";
    goto LABEL_14;
  }
  v8 = FullPathNameW + 1;
  if ( v8 <= 4096 )
  {
    if ( *a2 == 92 )
    {
      if ( v8 > 3 && a2[1] == 92 && a2[2] == 63 && a2[3] == 92 )
        return 1;
      goto LABEL_13;
    }
    if ( v8 < 4092 )
    {
      memmove_s(a2 + 4, 0xFF8u, a2, 0xFF8u);
      *(_DWORD *)a2 = 6029404;
      *((_DWORD *)a2 + 1) = 6029375;
      return 1;
    }
  }
  v10 = "File name too long: %1";
LABEL_14:
  ErrSet(a4, v10, "%s", a1);
  return 0;
}

```

## disassembly

```asm
0x140008a78  mov     [rsp+arg_10], rbx
0x140008a7d  push    rbp
0x140008a7e  push    rsi
0x140008a7f  push    rdi
0x140008a80  mov     eax, 2040h
0x140008a85  call    _alloca_probe
0x140008a8a  sub     rsp, rax
0x140008a8d  mov     rax, cs:__security_cookie
0x140008a94  xor     rax, rsp
0x140008a97  mov     [rsp+2058h+var_28], rax
0x140008a9f  mov     rsi, r9
0x140008aa2  lea     rax, [rsp+2058h+WideCharStr]
0x140008aa7  mov     rbx, rdx
0x140008aaa  mov     rdi, rcx
0x140008aad  mov     r8, rcx; lpMultiByteStr
0x140008ab0  mov     ebp, 1000h
0x140008ab5  mov     [rsp+2058h+cchWideChar], ebp; cchWideChar
0x140008ab9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140008abd  xor     edx, edx; dwFlags
0x140008abf  mov     [rsp+2058h+lpWideCharStr], rax; lpWideCharStr
0x140008ac4  xor     ecx, ecx; CodePage
0x140008ac6  call    cs:__imp_MultiByteToWideChar
0x140008acc  test    eax, eax
0x140008ace  jz      short loc_140008B4C
0x140008ad0  xor     r9d, r9d; lpFilePart
0x140008ad3  lea     rcx, [rsp+2058h+WideCharStr]; lpFileName
0x140008ad8  mov     r8, rbx; lpBuffer
0x140008adb  mov     edx, ebp; nBufferLength
0x140008add  call    cs:__imp_GetFullPathNameW
0x140008ae3  test    eax, eax
0x140008ae5  jz      short loc_140008B4C
0x140008ae7  inc     eax
0x140008ae9  cmp     eax, ebp
0x140008aeb  jg      short loc_140008B43
0x140008aed  mov     ebp, 5Ch ; '\'
0x140008af2  cmp     [rbx], bp
0x140008af5  jnz     short loc_140008B18
0x140008af7  cmp     eax, 3
0x140008afa  jle     short loc_140008B4C
0x140008afc  cmp     [rbx+2], bp
0x140008b00  jnz     short loc_140008B4C
0x140008b02  lea     eax, [rbp-1Dh]
0x140008b05  cmp     [rbx+4], ax
0x140008b09  jnz     short loc_140008B4C
0x140008b0b  cmp     [rbx+6], bp
0x140008b0f  jnz     short loc_140008B4C
0x140008b11  mov     eax, 1
0x140008b16  jmp     short loc_140008B67
0x140008b18  cmp     eax, 0FFCh
0x140008b1d  jge     short loc_140008B43
0x140008b1f  mov     edx, 0FF8h; DestinationSize
0x140008b24  lea     rcx, [rbx+8]; Destination
0x140008b28  mov     r9d, edx; SourceSize
0x140008b2b  mov     r8, rbx; Source
0x140008b2e  call    cs:__imp_memmove_s
0x140008b34  mov     dword ptr [rbx], 5C005Ch
0x140008b3a  mov     dword ptr [rbx+4], 5C003Fh
0x140008b41  jmp     short loc_140008B11
0x140008b43  lea     rdx, aFileNameTooLon; "File name too long: %1"
0x140008b4a  jmp     short loc_140008B53
0x140008b4c  lea     rdx, aCannotOpenFile; "Cannot open file: %1"
0x140008b53  mov     r9, rdi
0x140008b56  lea     r8, aS_4; "%s"
0x140008b5d  mov     rcx, rsi
0x140008b60  call    ErrSet
0x140008b65  xor     eax, eax
0x140008b67  mov     rcx, [rsp+2058h+var_28]
0x140008b6f  xor     rcx, rsp; StackCookie
0x140008b72  call    __security_check_cookie
0x140008b77  mov     rbx, [rsp+2058h+arg_10]
0x140008b7f  add     rsp, 2040h
0x140008b86  pop     rdi
0x140008b87  pop     rsi
0x140008b88  pop     rbp
0x140008b89  retn
```
