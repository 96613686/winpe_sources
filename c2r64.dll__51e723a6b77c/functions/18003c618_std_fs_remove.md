# __std_fs_remove

- ea: `0x18003c618`
- end: `0x18003c845`
- name: `__std_fs_remove`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800c9268`
- `0x1800c9430`

## callees

- `0x18003c150`
- `0x18003c5c0`
- `0x18003c618`
- `0x18003e690`
- `0x18004310d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003c708`
- `KERNEL32!GetLastError` at `0x18003c762`
- `KERNEL32!GetLastError` at `0x18003c7fa`
- `KERNEL32!GetLastError` at `0x18003c708`
- `KERNEL32!GetLastError` at `0x18003c762`
- `KERNEL32!GetLastError` at `0x18003c7fa`
- `KERNEL32!CloseHandle` at `0x18003c6d4`
- `KERNEL32!CloseHandle` at `0x18003c778`
- `KERNEL32!CloseHandle` at `0x18003c6d4`
- `KERNEL32!CloseHandle` at `0x18003c778`
- `KERNEL32!SetFileInformationByHandle` at `0x18003c682`
- `KERNEL32!SetFileInformationByHandle` at `0x18003c7a4`
- `KERNEL32!SetFileInformationByHandle` at `0x18003c7d8`
- `KERNEL32!SetFileInformationByHandle` at `0x18003c682`
- `KERNEL32!SetFileInformationByHandle` at `0x18003c7a4`
- `KERNEL32!SetFileInformationByHandle` at `0x18003c7d8`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18003c754`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18003c754`

## pseudocode

```c
__int64 __fastcall _std_fs_remove(__int64 a1)
{
  char v2; // di
  int v3; // eax
  int v4; // ecx
  HANDLE v5; // rbx
  HANDLE v6; // rcx
  int v7; // eax
  DWORD LastError; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-50h]
  HANDLE hFile; // [rsp+28h] [rbp-48h] BYREF
  int FileInformation; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-38h] BYREF
  int v20; // [rsp+58h] [rbp-18h]

  v2 = 0;
  v3 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  v4 = v3;
  if ( !v3 )
  {
    v2 = 1;
    goto LABEL_3;
  }
  if ( v3 != 5 )
  {
    LOBYTE(v16) = 0;
    v11 = v3 - 2;
    if ( !v11
      || (v12 = v11 - 1) == 0
      || (v13 = v12 - 50) == 0
      || (v14 = v13 - 11) == 0
      || (v15 = v14 - 59) == 0
      || v15 == 144 )
    {
      v4 = 0;
    }
    HIDWORD(v16) = v4;
LABEL_10:
    v6 = hFile;
    if ( hFile == (HANDLE)-1LL )
      return v16;
LABEL_11:
    if ( !CloseHandle(v6) )
      abort_0();
    return v16;
  }
  v7 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
  if ( v7 )
  {
    LOBYTE(v16) = 0;
    HIDWORD(v16) = v7;
    goto LABEL_10;
  }
LABEL_3:
  v5 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_4:
    LOBYTE(v16) = 1;
    HIDWORD(v16) = 0;
LABEL_5:
    if ( v5 == (HANDLE)-1LL )
      return v16;
    v6 = v5;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_16;
  LastError = sub_18003C150(v5);
  if ( !LastError )
    goto LABEL_4;
  if ( LastError != 5 || !v2 )
  {
LABEL_16:
    LOBYTE(v16) = 0;
    goto LABEL_17;
  }
  if ( GetFileInformationByHandleEx(v5, FileBasicInfo, v19, 0x28u) )
  {
    if ( (v20 & 1) == 0 )
    {
      LOBYTE(v16) = 0;
      goto LABEL_33;
    }
    v20 ^= 1u;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
      goto LABEL_22;
    v10 = sub_18003C150(v5);
    if ( !v10 )
    {
      LOBYTE(v16) = 1;
      HIDWORD(v16) = 0;
      goto LABEL_24;
    }
    if ( v10 == 5 )
    {
      v20 |= 1u;
      LOBYTE(v16) = 0;
      if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
        goto LABEL_23;
LABEL_33:
      HIDWORD(v16) = 5;
      goto LABEL_24;
    }
    LOBYTE(v16) = 0;
    LastError = GetLastError();
LABEL_17:
    HIDWORD(v16) = LastError;
    goto LABEL_5;
  }
LABEL_22:
  LOBYTE(v16) = 0;
LABEL_23:
  HIDWORD(v16) = GetLastError();
LABEL_24:
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    abort_0();
  return v16;
}

```

## disassembly

```asm
0x18003c618  mov     [rsp-8+arg_8], rbx
0x18003c61d  mov     [rsp-8+arg_10], rsi
0x18003c622  mov     [rsp-8+arg_18], rdi
0x18003c627  push    rbp
0x18003c628  mov     rbp, rsp
0x18003c62b  sub     rsp, 70h
0x18003c62f  mov     rax, cs:__security_cookie
0x18003c636  xor     rax, rsp
0x18003c639  mov     [rbp+var_10], rax
0x18003c63d  mov     rbx, rcx
0x18003c640  mov     rdx, rcx
0x18003c643  xor     esi, esi
0x18003c645  lea     rcx, [rbp+hFile]
0x18003c649  mov     r9d, 2200000h
0x18003c64f  mov     r8d, 10180h
0x18003c655  mov     dil, sil
0x18003c658  call    __std_fs_open_handle
0x18003c65d  mov     ecx, eax
0x18003c65f  test    eax, eax
0x18003c661  jnz     short loc_18003C69E
0x18003c663  mov     dil, 1
0x18003c666  mov     rbx, [rbp+hFile]
0x18003c66a  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18003c66e  mov     r9d, 4; dwBufferSize
0x18003c674  mov     [rbp+FileInformation], 13h
0x18003c67b  mov     rcx, rbx; hFile
0x18003c67e  lea     edx, [r9+11h]; FileInformationClass
0x18003c682  call    cs:__imp_SetFileInformationByHandle
0x18003c688  test    eax, eax
0x18003c68a  jz      short loc_18003C708
0x18003c68c  mov     byte ptr [rbp+var_50], 1
0x18003c690  mov     dword ptr [rbp+var_50+4], esi
0x18003c693  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003c697  jz      short loc_18003C6E2
0x18003c699  mov     rcx, rbx
0x18003c69c  jmp     short loc_18003C6D4
0x18003c69e  cmp     eax, 5
0x18003c6a1  jnz     loc_18003C80B
0x18003c6a7  mov     r9d, 2200000h
0x18003c6ad  lea     rcx, [rbp+hFile]
0x18003c6b1  mov     r8d, 10000h
0x18003c6b7  mov     rdx, rbx
0x18003c6ba  call    __std_fs_open_handle
0x18003c6bf  test    eax, eax
0x18003c6c1  jz      short loc_18003C666
0x18003c6c3  mov     byte ptr [rbp+var_50], sil
0x18003c6c7  mov     dword ptr [rbp+var_50+4], eax
0x18003c6ca  mov     rcx, [rbp+hFile]; hObject
0x18003c6ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003c6d2  jz      short loc_18003C6E2
0x18003c6d4  call    cs:__imp_CloseHandle
0x18003c6da  test    eax, eax
0x18003c6dc  jz      loc_18003C839
0x18003c6e2  mov     rax, [rbp+var_50]
0x18003c6e6  mov     rcx, [rbp+var_10]
0x18003c6ea  xor     rcx, rsp; StackCookie
0x18003c6ed  call    __security_check_cookie
0x18003c6f2  lea     r11, [rsp+70h+var_s0]
0x18003c6f7  mov     rbx, [r11+18h]
0x18003c6fb  mov     rsi, [r11+20h]
0x18003c6ff  mov     rdi, [r11+28h]
0x18003c703  mov     rsp, r11
0x18003c706  pop     rbp
0x18003c707  retn
0x18003c708  call    cs:__imp_GetLastError
0x18003c70e  mov     ecx, eax
0x18003c710  sub     ecx, 1
0x18003c713  jz      short loc_18003C72B
0x18003c715  sub     ecx, 31h ; '1'
0x18003c718  jz      short loc_18003C72B
0x18003c71a  cmp     ecx, 25h ; '%'
0x18003c71d  jz      short loc_18003C72B
0x18003c71f  mov     byte ptr [rbp+var_50], sil
0x18003c723  mov     dword ptr [rbp+var_50+4], eax
0x18003c726  jmp     loc_18003C693
0x18003c72b  mov     rcx, rbx; hFile
0x18003c72e  call    sub_18003C150
0x18003c733  test    eax, eax
0x18003c735  jz      loc_18003C68C
0x18003c73b  cmp     eax, 5
0x18003c73e  jnz     short loc_18003C71F
0x18003c740  test    dil, dil
0x18003c743  jz      short loc_18003C71F
0x18003c745  lea     edi, [rax+23h]
0x18003c748  xor     edx, edx; FileInformationClass
0x18003c74a  mov     r9d, edi; dwBufferSize
0x18003c74d  lea     r8, [rbp+var_38]; lpFileInformation
0x18003c751  mov     rcx, rbx; hFile
0x18003c754  call    cs:__imp_GetFileInformationByHandleEx
0x18003c75a  test    eax, eax
0x18003c75c  jnz     short loc_18003C78B
0x18003c75e  mov     byte ptr [rbp+var_50], sil
0x18003c762  call    cs:__imp_GetLastError
0x18003c768  mov     dword ptr [rbp+var_50+4], eax
0x18003c76b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003c76f  jz      loc_18003C6E2
0x18003c775  mov     rcx, rbx; hObject
0x18003c778  call    cs:__imp_CloseHandle
0x18003c77e  test    eax, eax
0x18003c780  jz      loc_18003C83F
0x18003c786  jmp     loc_18003C6E2
0x18003c78b  mov     eax, [rbp+var_18]
0x18003c78e  test    al, 1
0x18003c790  jz      short loc_18003C805
0x18003c792  xor     eax, 1
0x18003c795  lea     r8, [rbp+var_38]; lpFileInformation
0x18003c799  mov     r9d, edi; dwBufferSize
0x18003c79c  mov     [rbp+var_18], eax
0x18003c79f  xor     edx, edx; FileInformationClass
0x18003c7a1  mov     rcx, rbx; hFile
0x18003c7a4  call    cs:__imp_SetFileInformationByHandle
0x18003c7aa  test    eax, eax
0x18003c7ac  jz      short loc_18003C75E
0x18003c7ae  mov     rcx, rbx; hFile
0x18003c7b1  call    sub_18003C150
0x18003c7b6  test    eax, eax
0x18003c7b8  jnz     short loc_18003C7C3
0x18003c7ba  mov     byte ptr [rbp+var_50], 1
0x18003c7be  mov     dword ptr [rbp+var_50+4], esi
0x18003c7c1  jmp     short loc_18003C76B
0x18003c7c3  cmp     eax, 5
0x18003c7c6  jnz     short loc_18003C7F6
0x18003c7c8  or      [rbp+var_18], 1
0x18003c7cc  lea     r8, [rbp+var_38]; lpFileInformation
0x18003c7d0  mov     r9d, edi; dwBufferSize
0x18003c7d3  xor     edx, edx; FileInformationClass
0x18003c7d5  mov     rcx, rbx; hFile
0x18003c7d8  call    cs:__imp_SetFileInformationByHandle
0x18003c7de  mov     byte ptr [rbp+var_50], sil
0x18003c7e2  test    eax, eax
0x18003c7e4  jz      loc_18003C762
0x18003c7ea  mov     dword ptr [rbp+var_50+4], 5
0x18003c7f1  jmp     loc_18003C76B
0x18003c7f6  mov     byte ptr [rbp+var_50], sil
0x18003c7fa  call    cs:__imp_GetLastError
0x18003c800  jmp     loc_18003C723
0x18003c805  mov     byte ptr [rbp+var_50], sil
0x18003c809  jmp     short loc_18003C7EA
0x18003c80b  mov     byte ptr [rbp+var_50], sil
0x18003c80f  sub     eax, 2
0x18003c812  jz      short loc_18003C82F
0x18003c814  sub     eax, 1
0x18003c817  jz      short loc_18003C82F
0x18003c819  sub     eax, 32h ; '2'
0x18003c81c  jz      short loc_18003C82F
0x18003c81e  sub     eax, 0Bh
0x18003c821  jz      short loc_18003C82F
0x18003c823  sub     eax, 3Bh ; ';'
0x18003c826  jz      short loc_18003C82F
0x18003c828  cmp     eax, 90h
0x18003c82d  jnz     short loc_18003C831
0x18003c82f  mov     ecx, esi
0x18003c831  mov     dword ptr [rbp+var_50+4], ecx
0x18003c834  jmp     loc_18003C6CA
0x18003c839  call    abort_0
0x18003c83f  call    abort_0
```
