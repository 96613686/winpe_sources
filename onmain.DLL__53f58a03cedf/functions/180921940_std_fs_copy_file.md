# __std_fs_copy_file

- ea: `0x180921940`
- end: `0x180921bdf`
- name: `__std_fs_copy_file`
- size: `671`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180d7ed98`

## callees

- `0x1800982ed`
- `0x1802e5170`
- `0x180921570`
- `0x18092160c`
- `0x180921940`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180921a56`
- `KERNEL32!CloseHandle` at `0x180921a8a`
- `KERNEL32!CloseHandle` at `0x180921ab9`
- `KERNEL32!CloseHandle` at `0x180921ad0`
- `KERNEL32!CloseHandle` at `0x180921b05`
- `KERNEL32!CloseHandle` at `0x180921b1c`
- `KERNEL32!CloseHandle` at `0x180921a56`
- `KERNEL32!CloseHandle` at `0x180921a8a`
- `KERNEL32!CloseHandle` at `0x180921ab9`
- `KERNEL32!CloseHandle` at `0x180921ad0`
- `KERNEL32!CloseHandle` at `0x180921b05`
- `KERNEL32!CloseHandle` at `0x180921b1c`
- `KERNEL32!GetLastError` at `0x1809219a3`
- `KERNEL32!GetLastError` at `0x1809219fb`
- `KERNEL32!GetLastError` at `0x180921a38`
- `KERNEL32!GetLastError` at `0x180921b98`
- `KERNEL32!GetLastError` at `0x1809219a3`
- `KERNEL32!GetLastError` at `0x1809219fb`
- `KERNEL32!GetLastError` at `0x180921a38`
- `KERNEL32!GetLastError` at `0x180921b98`
- `KERNEL32!CreateFileW` at `0x1809219ec`
- `KERNEL32!CreateFileW` at `0x180921a29`
- `KERNEL32!CreateFileW` at `0x1809219ec`
- `KERNEL32!CreateFileW` at `0x180921a29`
- `KERNEL32!CopyFileW` at `0x18092198c`
- `KERNEL32!CopyFileW` at `0x180921b77`
- `KERNEL32!CopyFileW` at `0x18092198c`
- `KERNEL32!CopyFileW` at `0x180921b77`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180921ade`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180921b2a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180921ade`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180921b2a`

## pseudocode

```c
__int64 __fastcall _std_fs_copy_file(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, char a3)
{
  int v3; // esi
  __int64 result; // rax
  DWORD v7; // edi
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  HANDLE v10; // rdi
  DWORD v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  _BYTE Buf2[24]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE Buf1[24]; // [rsp+68h] [rbp+Fh] BYREF

  v3 = a3 & 0xF;
  if ( v3 == 2 )
    goto LABEL_40;
  if ( CopyFileW(lpExistingFileName, lpNewFileName, 1) )
  {
    LOBYTE(v15) = 1;
    HIDWORD(v15) = 0;
  }
  else
  {
    LOBYTE(v15) = 0;
    HIDWORD(v15) = GetLastError();
  }
  result = v15;
  if ( HIDWORD(v15) == 80 && v3 )
  {
    v7 = HIDWORD(v15) - 77;
    if ( v3 != 1 )
      v7 = 1;
    FileW = CreateFileW(lpExistingFileName, HIDWORD(v15) + 48, v7, 0, HIDWORD(v15) - 77, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_43;
    }
    v10 = CreateFileW(lpNewFileName, 0x80u, v7, 0, 3u, 0, 0);
    if ( v10 == (HANDLE)-1LL )
    {
      v11 = GetLastError();
      if ( v11 )
      {
        LOBYTE(v15) = 0;
        HIDWORD(v15) = v11;
LABEL_14:
        if ( FileW == (HANDLE)-1LL || CloseHandle(FileW) )
          return v15;
LABEL_28:
        abort();
      }
    }
    if ( v3 != 4 )
      goto LABEL_29;
    v12 = sub_18092160C(FileW, &v15);
    if ( v12 || (v12 = sub_18092160C(v10, &v16)) != 0 )
    {
      LOBYTE(v15) = 0;
      HIDWORD(v15) = v12;
      if ( v10 != (HANDLE)-1LL && !CloseHandle(v10) )
        goto LABEL_28;
      goto LABEL_14;
    }
    if ( v16 >= v15 )
    {
LABEL_29:
      v13 = sub_180921570(FileW, Buf1);
      if ( v13 || (v13 = sub_180921570(v10, Buf2)) != 0 )
      {
        LOBYTE(v15) = 0;
        HIDWORD(v15) = v13;
      }
      else
      {
        v14 = memcmp_0(Buf1, Buf2, 0x18u);
        LOBYTE(v15) = 0;
        if ( v14 )
          HIDWORD(v15) = 0;
        else
          HIDWORD(v15) = 32;
      }
      if ( v10 != (HANDLE)-1LL && !CloseHandle(v10) || FileW != (HANDLE)-1LL && !CloseHandle(FileW) )
        abort();
      return v15;
    }
    if ( v10 != (HANDLE)-1LL && !CloseHandle(v10) || FileW != (HANDLE)-1LL && !CloseHandle(FileW) )
      goto LABEL_28;
LABEL_40:
    if ( CopyFileW(lpExistingFileName, lpNewFileName, 0) )
    {
      *(_WORD *)((char *)&v15 + 1) = *(_WORD *)((char *)&v16 + 1);
      BYTE3(v15) = BYTE3(v16);
      LOBYTE(v15) = 1;
      HIDWORD(v15) = 0;
      return v15;
    }
    LastError = GetLastError();
    *(_WORD *)((char *)&v15 + 1) = *(_WORD *)((char *)&v16 + 1);
    BYTE3(v15) = BYTE3(v16);
LABEL_43:
    HIDWORD(v15) = LastError;
    LOBYTE(v15) = 0;
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x180921940  mov     [rsp-8+arg_10], rbx
0x180921945  mov     [rsp-8+arg_18], rsi
0x18092194a  push    rbp
0x18092194b  push    rdi
0x18092194c  push    r12
0x18092194e  push    r14
0x180921950  push    r15
0x180921952  lea     rbp, [rsp-37h]
0x180921957  sub     rsp, 90h
0x18092195e  mov     rax, cs:__security_cookie
0x180921965  xor     rax, rsp
0x180921968  mov     [rbp+57h+var_30], rax
0x18092196c  mov     esi, r8d
0x18092196f  xor     r12d, r12d
0x180921972  and     esi, 0Fh
0x180921975  mov     r14, rdx
0x180921978  mov     r15, rcx
0x18092197b  mov     ebx, 1
0x180921980  cmp     esi, 2
0x180921983  jz      loc_180921B6E
0x180921989  mov     r8d, ebx; bFailIfExists
0x18092198c  call    cs:__imp_CopyFileW
0x180921992  test    eax, eax
0x180921994  jz      short loc_18092199F
0x180921996  mov     byte ptr [rbp+57h+var_70], bl
0x180921999  mov     dword ptr [rbp+57h+var_70+4], r12d
0x18092199d  jmp     short loc_1809219AC
0x18092199f  mov     byte ptr [rbp+57h+var_70], r12b
0x1809219a3  call    cs:__imp_GetLastError
0x1809219a9  mov     dword ptr [rbp+57h+var_70+4], eax
0x1809219ac  mov     rax, [rbp+57h+var_70]
0x1809219b0  mov     rcx, rax
0x1809219b3  shr     rcx, 20h
0x1809219b7  cmp     ecx, 50h ; 'P'
0x1809219ba  jnz     loc_180921BB7
0x1809219c0  test    esi, esi
0x1809219c2  jz      loc_180921BB7
0x1809219c8  lea     eax, [rcx-4Dh]
0x1809219cb  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x1809219d0  mov     edi, eax
0x1809219d2  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1809219d7  lea     edx, [rcx+30h]; dwDesiredAccess
0x1809219da  mov     [rsp+0B0h+dwCreationDisposition], eax; dwCreationDisposition
0x1809219de  cmp     esi, ebx
0x1809219e0  mov     rcx, r15; lpFileName
0x1809219e3  cmovnz  edi, ebx
0x1809219e6  xor     r9d, r9d; lpSecurityAttributes
0x1809219e9  mov     r8d, edi; dwShareMode
0x1809219ec  call    cs:__imp_CreateFileW
0x1809219f2  mov     rbx, rax
0x1809219f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1809219f9  jnz     short loc_180921A09
0x1809219fb  call    cs:__imp_GetLastError
0x180921a01  test    eax, eax
0x180921a03  jnz     loc_180921BAC
0x180921a09  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x180921a0e  xor     r9d, r9d; lpSecurityAttributes
0x180921a11  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180921a16  mov     r8d, edi; dwShareMode
0x180921a19  mov     edx, 80h; dwDesiredAccess
0x180921a1e  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180921a26  mov     rcx, r14; lpFileName
0x180921a29  call    cs:__imp_CreateFileW
0x180921a2f  mov     rdi, rax
0x180921a32  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180921a36  jnz     short loc_180921A65
0x180921a38  call    cs:__imp_GetLastError
0x180921a3e  test    eax, eax
0x180921a40  jz      short loc_180921A65
0x180921a42  mov     byte ptr [rbp+57h+var_70], r12b
0x180921a46  mov     dword ptr [rbp+57h+var_70+4], eax
0x180921a49  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180921a4d  jz      loc_180921BB3
0x180921a53  mov     rcx, rbx; hObject
0x180921a56  call    cs:__imp_CloseHandle
0x180921a5c  test    eax, eax
0x180921a5e  jz      short loc_180921ADE
0x180921a60  jmp     loc_180921BB3
0x180921a65  cmp     esi, 4
0x180921a68  jnz     short loc_180921AE5
0x180921a6a  lea     rdx, [rbp+57h+var_70]
0x180921a6e  mov     rcx, rbx
0x180921a71  call    sub_18092160C
0x180921a76  test    eax, eax
0x180921a78  jz      short loc_180921A96
0x180921a7a  mov     byte ptr [rbp+57h+var_70], r12b
0x180921a7e  mov     dword ptr [rbp+57h+var_70+4], eax
0x180921a81  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180921a85  jz      short loc_180921A49
0x180921a87  mov     rcx, rdi; hObject
0x180921a8a  call    cs:__imp_CloseHandle
0x180921a90  test    eax, eax
0x180921a92  jz      short loc_180921ADE
0x180921a94  jmp     short loc_180921A49
0x180921a96  lea     rdx, [rbp+57h+var_68]
0x180921a9a  mov     rcx, rdi
0x180921a9d  call    sub_18092160C
0x180921aa2  test    eax, eax
0x180921aa4  jnz     short loc_180921A7A
0x180921aa6  mov     rax, [rbp+57h+var_70]
0x180921aaa  cmp     [rbp+57h+var_68], rax
0x180921aae  jge     short loc_180921AE5
0x180921ab0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180921ab4  jz      short loc_180921AC3
0x180921ab6  mov     rcx, rdi; hObject
0x180921ab9  call    cs:__imp_CloseHandle
0x180921abf  test    eax, eax
0x180921ac1  jz      short loc_180921ADE
0x180921ac3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180921ac7  jz      loc_180921B69
0x180921acd  mov     rcx, rbx; hObject
0x180921ad0  call    cs:__imp_CloseHandle
0x180921ad6  test    eax, eax
0x180921ad8  jnz     loc_180921B69
0x180921ade  call    cs:__imp_abort
0x180921ae5  lea     rdx, [rbp+57h+Buf1]; lpFileInformation
0x180921ae9  mov     rcx, rbx; hFile
0x180921aec  call    sub_180921570
0x180921af1  test    eax, eax
0x180921af3  jz      short loc_180921B31
0x180921af5  mov     byte ptr [rbp+57h+var_70], r12b
0x180921af9  mov     dword ptr [rbp+57h+var_70+4], eax
0x180921afc  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180921b00  jz      short loc_180921B0F
0x180921b02  mov     rcx, rdi; hObject
0x180921b05  call    cs:__imp_CloseHandle
0x180921b0b  test    eax, eax
0x180921b0d  jz      short loc_180921B2A
0x180921b0f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180921b13  jz      loc_180921BB3
0x180921b19  mov     rcx, rbx; hObject
0x180921b1c  call    cs:__imp_CloseHandle
0x180921b22  test    eax, eax
0x180921b24  jnz     loc_180921BB3
0x180921b2a  call    cs:__imp_abort
0x180921b31  lea     rdx, [rbp+57h+Buf2]; lpFileInformation
0x180921b35  mov     rcx, rdi; hFile
0x180921b38  call    sub_180921570
0x180921b3d  test    eax, eax
0x180921b3f  jnz     short loc_180921AF5
0x180921b41  lea     r8d, [rax+18h]; Size
0x180921b45  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180921b49  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180921b4d  call    memcmp_0
0x180921b52  mov     byte ptr [rbp+57h+var_70], r12b
0x180921b56  test    eax, eax
0x180921b58  jnz     short loc_180921B63
0x180921b5a  mov     dword ptr [rbp+57h+var_70+4], 20h ; ' '
0x180921b61  jmp     short loc_180921AFC
0x180921b63  mov     dword ptr [rbp+57h+var_70+4], r12d
0x180921b67  jmp     short loc_180921AFC
0x180921b69  mov     ebx, 1
0x180921b6e  xor     r8d, r8d; bFailIfExists
0x180921b71  mov     rdx, r14; lpNewFileName
0x180921b74  mov     rcx, r15; lpExistingFileName
0x180921b77  call    cs:__imp_CopyFileW
0x180921b7d  test    eax, eax
0x180921b7f  jz      short loc_180921B98
0x180921b81  movzx   eax, word ptr [rbp+57h+var_68+1]
0x180921b85  mov     word ptr [rbp+57h+var_70+1], ax
0x180921b89  mov     al, byte ptr [rbp+57h+var_68+3]
0x180921b8c  mov     byte ptr [rbp+57h+var_70+3], al
0x180921b8f  mov     byte ptr [rbp+57h+var_70], bl
0x180921b92  mov     dword ptr [rbp+57h+var_70+4], r12d
0x180921b96  jmp     short loc_180921BB3
0x180921b98  call    cs:__imp_GetLastError
0x180921b9e  movzx   ecx, word ptr [rbp+57h+var_68+1]
0x180921ba2  mov     word ptr [rbp+57h+var_70+1], cx
0x180921ba6  mov     cl, byte ptr [rbp+57h+var_68+3]
0x180921ba9  mov     byte ptr [rbp+57h+var_70+3], cl
0x180921bac  mov     dword ptr [rbp+57h+var_70+4], eax
0x180921baf  mov     byte ptr [rbp+57h+var_70], r12b
0x180921bb3  mov     rax, [rbp+57h+var_70]
0x180921bb7  mov     rcx, [rbp+57h+var_30]
0x180921bbb  xor     rcx, rsp; StackCookie
0x180921bbe  call    __security_check_cookie
0x180921bc3  lea     r11, [rsp+0B0h+var_20]
0x180921bcb  mov     rbx, [r11+40h]
0x180921bcf  mov     rsi, [r11+48h]
0x180921bd3  mov     rsp, r11
0x180921bd6  pop     r15
0x180921bd8  pop     r14
0x180921bda  pop     r12
0x180921bdc  pop     rdi
0x180921bdd  pop     rbp
0x180921bde  retn
```
