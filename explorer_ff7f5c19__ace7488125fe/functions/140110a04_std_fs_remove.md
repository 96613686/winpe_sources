# __std_fs_remove

- ea: `0x140110a04`
- end: `0x140110d46`
- name: `__std_fs_remove`
- size: `834`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1401a1c2c`
- `0x1401a73e0`

## callees

- `0x14010e160`
- `0x140110374`
- `0x1401109a8`
- `0x140110a04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140110c63`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140110d0b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140110c63`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140110d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140110c80`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140110a6d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140110be9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140110c3d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140110a6d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140110be9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140110c3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110a86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110b2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110c59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110a86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110b2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110c59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140110d01`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140110b90`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140110b90`

## pseudocode

```c
HANDLE __fastcall _std_fs_remove(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  char v4; // si
  HANDLE v5; // rbx
  DWORD LastError; // edi
  int v7; // ebx
  int v9; // eax
  int v10; // edi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HANDLE hFile; // [rsp+20h] [rbp-40h] BYREF
  __int64 FileInformation; // [rsp+28h] [rbp-38h] BYREF
  _OWORD v20[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]

  v2 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 != 5 )
    {
      v12 = v2 - 2;
      if ( !v12
        || (v13 = v12 - 1) == 0
        || (v14 = v13 - 50) == 0
        || (v15 = v14 - 11) == 0
        || (v16 = v15 - 59) == 0
        || (v17 = v16 - 38) == 0
        || v17 == 106 )
      {
        v3 = 0;
      }
      if ( hFile != (HANDLE)-1LL && !CloseHandle(hFile) )
        goto LABEL_56;
      HIDWORD(hFile) = v3;
LABEL_58:
      LOBYTE(hFile) = 0;
      *(_WORD *)((char *)&hFile + 1) = 0;
      BYTE3(hFile) = 0;
      return hFile;
    }
    v4 = 0;
    v7 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
    if ( v7 )
    {
      if ( hFile == (HANDLE)-1LL || CloseHandle(hFile) )
      {
        LOBYTE(FileInformation) = 0;
        *(_WORD *)((char *)&FileInformation + 1) = 0;
        BYTE3(FileInformation) = 0;
        HIDWORD(FileInformation) = v7;
        return (HANDLE)FileInformation;
      }
      goto LABEL_56;
    }
  }
  else
  {
    v4 = 1;
  }
  v5 = hFile;
  LODWORD(FileInformation) = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    goto LABEL_4;
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
  {
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 0;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
      goto LABEL_7;
    }
LABEL_56:
    abort();
  }
  v9 = anonymous_namespace_::_Set_delete_flag(v5);
  v10 = v9;
  if ( !v9 )
  {
LABEL_4:
    LastError = 0;
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 1;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
LABEL_7:
      HIDWORD(FileInformation) = LastError;
      return (HANDLE)FileInformation;
    }
    goto LABEL_56;
  }
  if ( v9 != 5 || !v4 )
  {
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_56;
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
LABEL_33:
    HIDWORD(hFile) = v10;
    return hFile;
  }
  v21 = 0;
  memset(v20, 0, sizeof(v20));
  if ( !GetFileInformationByHandleEx(v5, FileBasicInfo, v20, 0x28u) )
  {
LABEL_24:
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    HIDWORD(hFile) = GetLastError();
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
      return hFile;
LABEL_38:
    abort();
  }
  if ( (v21 & 1) == 0 )
  {
LABEL_36:
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    HIDWORD(hFile) = 5;
    goto LABEL_58;
  }
  LODWORD(v21) = v21 ^ 1;
  if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
    goto LABEL_24;
  v11 = anonymous_namespace_::_Set_delete_flag(v5);
  if ( !v11 )
  {
    v10 = 0;
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    LOBYTE(hFile) = 1;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    goto LABEL_33;
  }
  if ( v11 == 5 )
  {
    LODWORD(v21) = v21 | 1;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
      goto LABEL_24;
    goto LABEL_36;
  }
  LOBYTE(hFile) = 0;
  *(_WORD *)((char *)&hFile + 1) = 0;
  BYTE3(hFile) = 0;
  HIDWORD(hFile) = GetLastError();
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    goto LABEL_56;
  return hFile;
}

```

## disassembly

```asm
0x140110a04  mov     [rsp-18h+arg_8], rbx
0x140110a09  mov     [rsp-18h+arg_10], rsi
0x140110a0e  push    rbp
0x140110a0f  push    rdi
0x140110a10  push    r15
0x140110a12  mov     rbp, rsp
0x140110a15  sub     rsp, 60h
0x140110a19  mov     rax, cs:__security_cookie
0x140110a20  xor     rax, rsp
0x140110a23  mov     [rbp+var_8], rax
0x140110a27  mov     rdi, rcx
0x140110a2a  mov     rdx, rcx
0x140110a2d  lea     rcx, [rbp+hFile]
0x140110a31  mov     r9d, 2200000h
0x140110a37  mov     r8d, 10180h
0x140110a3d  call    __std_fs_open_handle
0x140110a42  mov     ebx, eax
0x140110a44  mov     r15d, 5
0x140110a4a  test    eax, eax
0x140110a4c  jnz     short loc_140110AA5
0x140110a4e  mov     sil, 1
0x140110a51  mov     rbx, [rbp+hFile]
0x140110a55  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140110a59  mov     r9d, 4; dwBufferSize
0x140110a5f  mov     dword ptr [rbp+FileInformation], 13h
0x140110a66  mov     rcx, rbx; hFile
0x140110a69  lea     edx, [r9+11h]; FileInformationClass
0x140110a6d  call    cs:__imp_SetFileInformationByHandle
0x140110a73  test    eax, eax
0x140110a75  jz      loc_140110B04
0x140110a7b  xor     edi, edi
0x140110a7d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140110a81  jz      short loc_140110A94
0x140110a83  mov     rcx, rbx; hObject
0x140110a86  call    cs:__imp_CloseHandle
0x140110a8c  test    eax, eax
0x140110a8e  jz      loc_140110D0B
0x140110a94  mov     byte ptr [rbp+FileInformation], 1
0x140110a98  mov     word ptr [rbp+FileInformation+1], di
0x140110a9c  mov     byte ptr [rbp+FileInformation+3], dil
0x140110aa0  mov     dword ptr [rbp+FileInformation+4], edi
0x140110aa3  jmp     short loc_140110AFB
0x140110aa5  cmp     eax, r15d
0x140110aa8  jnz     loc_140110CCD
0x140110aae  mov     r9d, 2200000h
0x140110ab4  lea     rcx, [rbp+hFile]
0x140110ab8  mov     r8d, 10000h
0x140110abe  mov     rdx, rdi
0x140110ac1  xor     sil, sil
0x140110ac4  call    __std_fs_open_handle
0x140110ac9  mov     ebx, eax
0x140110acb  test    eax, eax
0x140110acd  jz      short loc_140110A51
0x140110acf  mov     rcx, [rbp+hFile]; hObject
0x140110ad3  xor     dil, dil
0x140110ad6  xor     esi, esi
0x140110ad8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140110adc  jz      short loc_140110AEC
0x140110ade  call    cs:__imp_CloseHandle
0x140110ae4  test    eax, eax
0x140110ae6  jz      loc_140110D0B
0x140110aec  mov     byte ptr [rbp+FileInformation], dil
0x140110af0  mov     word ptr [rbp+FileInformation+1], si
0x140110af4  mov     byte ptr [rbp+FileInformation+3], sil
0x140110af8  mov     dword ptr [rbp+FileInformation+4], ebx
0x140110afb  mov     rax, [rbp+FileInformation]
0x140110aff  jmp     loc_140110D25
0x140110b04  call    cs:__imp_GetLastError
0x140110b0a  mov     ecx, eax
0x140110b0c  mov     edi, eax
0x140110b0e  sub     ecx, 1
0x140110b11  jz      short loc_140110B4C
0x140110b13  sub     ecx, 31h ; '1'
0x140110b16  jz      short loc_140110B4C
0x140110b18  cmp     ecx, 25h ; '%'
0x140110b1b  jz      short loc_140110B4C
0x140110b1d  xor     sil, sil
0x140110b20  xor     r15d, r15d
0x140110b23  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140110b27  jz      short loc_140110B3A
0x140110b29  mov     rcx, rbx; hObject
0x140110b2c  call    cs:__imp_CloseHandle
0x140110b32  test    eax, eax
0x140110b34  jz      loc_140110D0B
0x140110b3a  mov     byte ptr [rbp+FileInformation], sil
0x140110b3e  mov     word ptr [rbp+FileInformation+1], r15w
0x140110b43  mov     byte ptr [rbp+FileInformation+3], r15b
0x140110b47  jmp     loc_140110AA0
0x140110b4c  mov     rcx, rbx; hFile
0x140110b4f  call    _anonymous_namespace____Set_delete_flag
0x140110b54  mov     edi, eax
0x140110b56  test    eax, eax
0x140110b58  jz      loc_140110A7B
0x140110b5e  cmp     eax, r15d
0x140110b61  jnz     loc_140110CA2
0x140110b67  test    sil, sil
0x140110b6a  jz      loc_140110CA2
0x140110b70  xor     eax, eax
0x140110b72  lea     r8, [rbp+var_30]; lpFileInformation
0x140110b76  xorps   xmm0, xmm0
0x140110b79  mov     [rbp+var_10], rax
0x140110b7d  xor     edx, edx; FileInformationClass
0x140110b7f  mov     rcx, rbx; hFile
0x140110b82  movups  [rbp+var_30], xmm0
0x140110b86  lea     edi, [rax+28h]
0x140110b89  mov     r9d, edi; dwBufferSize
0x140110b8c  movups  [rbp+var_20], xmm0
0x140110b90  call    cs:__imp_GetFileInformationByHandleEx
0x140110b96  test    eax, eax
0x140110b98  jnz     short loc_140110BD0
0x140110b9a  xor     eax, eax
0x140110b9c  mov     byte ptr [rbp+hFile], 0
0x140110ba0  mov     word ptr [rbp+hFile+1], ax
0x140110ba4  mov     byte ptr [rbp+hFile+3], al
0x140110ba7  call    cs:__imp_GetLastError
0x140110bad  mov     dword ptr [rbp+hFile+4], eax
0x140110bb0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140110bb4  jz      loc_140110D21
0x140110bba  mov     rcx, rbx; hObject
0x140110bbd  call    cs:__imp_CloseHandle
0x140110bc3  test    eax, eax
0x140110bc5  jz      loc_140110C63
0x140110bcb  jmp     loc_140110D21
0x140110bd0  mov     eax, dword ptr [rbp+var_10]
0x140110bd3  test    al, 1
0x140110bd5  jz      short loc_140110C4B
0x140110bd7  xor     eax, 1
0x140110bda  lea     r8, [rbp+var_30]; lpFileInformation
0x140110bde  mov     r9d, edi; dwBufferSize
0x140110be1  mov     dword ptr [rbp+var_10], eax
0x140110be4  xor     edx, edx; FileInformationClass
0x140110be6  mov     rcx, rbx; hFile
0x140110be9  call    cs:__imp_SetFileInformationByHandle
0x140110bef  test    eax, eax
0x140110bf1  jz      short loc_140110B9A
0x140110bf3  mov     rcx, rbx; hFile
0x140110bf6  call    _anonymous_namespace____Set_delete_flag
0x140110bfb  test    eax, eax
0x140110bfd  jnz     short loc_140110C28
0x140110bff  xor     edi, edi
0x140110c01  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140110c05  jz      short loc_140110C14
0x140110c07  mov     rcx, rbx; hObject
0x140110c0a  call    cs:__imp_CloseHandle
0x140110c10  test    eax, eax
0x140110c12  jz      short loc_140110C63
0x140110c14  mov     byte ptr [rbp+hFile], 1
0x140110c18  mov     word ptr [rbp+hFile+1], di
0x140110c1c  mov     byte ptr [rbp+hFile+3], dil
0x140110c20  mov     dword ptr [rbp+hFile+4], edi
0x140110c23  jmp     loc_140110D21
0x140110c28  cmp     eax, r15d
0x140110c2b  jnz     short loc_140110C73
0x140110c2d  or      dword ptr [rbp+var_10], 1
0x140110c31  lea     r8, [rbp+var_30]; lpFileInformation
0x140110c35  mov     r9d, edi; dwBufferSize
0x140110c38  xor     edx, edx; FileInformationClass
0x140110c3a  mov     rcx, rbx; hFile
0x140110c3d  call    cs:__imp_SetFileInformationByHandle
0x140110c43  test    eax, eax
0x140110c45  jz      loc_140110B9A
0x140110c4b  xor     dil, dil
0x140110c4e  xor     esi, esi
0x140110c50  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140110c54  jz      short loc_140110C6A
0x140110c56  mov     rcx, rbx; hObject
0x140110c59  call    cs:__imp_CloseHandle
0x140110c5f  test    eax, eax
0x140110c61  jnz     short loc_140110C6A
0x140110c63  call    cs:__imp_abort
0x140110c6a  mov     dword ptr [rbp+hFile+4], r15d
0x140110c6e  jmp     loc_140110D15
0x140110c73  xor     eax, eax
0x140110c75  mov     byte ptr [rbp+hFile], 0
0x140110c79  mov     word ptr [rbp+hFile+1], ax
0x140110c7d  mov     byte ptr [rbp+hFile+3], al
0x140110c80  call    cs:__imp_GetLastError
0x140110c86  mov     dword ptr [rbp+hFile+4], eax
0x140110c89  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140110c8d  jz      loc_140110D21
0x140110c93  mov     rcx, rbx; hObject
0x140110c96  call    cs:__imp_CloseHandle
0x140110c9c  test    eax, eax
0x140110c9e  jz      short loc_140110D0B
0x140110ca0  jmp     short loc_140110D21
0x140110ca2  xor     sil, sil
0x140110ca5  xor     r15d, r15d
0x140110ca8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140110cac  jz      short loc_140110CBB
0x140110cae  mov     rcx, rbx; hObject
0x140110cb1  call    cs:__imp_CloseHandle
0x140110cb7  test    eax, eax
0x140110cb9  jz      short loc_140110D0B
0x140110cbb  mov     byte ptr [rbp+hFile], sil
0x140110cbf  mov     word ptr [rbp+hFile+1], r15w
0x140110cc4  mov     byte ptr [rbp+hFile+3], r15b
0x140110cc8  jmp     loc_140110C20
0x140110ccd  xor     dil, dil
0x140110cd0  xor     esi, esi
0x140110cd2  sub     eax, 2
0x140110cd5  jz      short loc_140110CF5
0x140110cd7  sub     eax, 1
0x140110cda  jz      short loc_140110CF5
0x140110cdc  sub     eax, 32h ; '2'
0x140110cdf  jz      short loc_140110CF5
0x140110ce1  sub     eax, 0Bh
0x140110ce4  jz      short loc_140110CF5
0x140110ce6  sub     eax, 3Bh ; ';'
0x140110ce9  jz      short loc_140110CF5
0x140110ceb  sub     eax, 26h ; '&'
0x140110cee  jz      short loc_140110CF5
0x140110cf0  cmp     eax, 6Ah ; 'j'
0x140110cf3  jnz     short loc_140110CF7
0x140110cf5  xor     ebx, ebx
0x140110cf7  mov     rcx, [rbp+hFile]; hObject
0x140110cfb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140110cff  jz      short loc_140110D12
0x140110d01  call    cs:__imp_CloseHandle
0x140110d07  test    eax, eax
0x140110d09  jnz     short loc_140110D12
0x140110d0b  call    cs:__imp_abort
0x140110d12  mov     dword ptr [rbp+hFile+4], ebx
0x140110d15  mov     byte ptr [rbp+hFile], dil
0x140110d19  mov     word ptr [rbp+hFile+1], si
0x140110d1d  mov     byte ptr [rbp+hFile+3], sil
0x140110d21  mov     rax, [rbp+hFile]
0x140110d25  mov     rcx, [rbp+var_8]
0x140110d29  xor     rcx, rsp; StackCookie
0x140110d2c  call    __security_check_cookie
0x140110d31  lea     r11, [rsp+60h+var_s0]
0x140110d36  mov     rbx, [r11+28h]
0x140110d3a  mov     rsi, [r11+30h]
0x140110d3e  mov     rsp, r11
0x140110d41  pop     r15
0x140110d43  pop     rdi
0x140110d44  pop     rbp
0x140110d45  retn
```
