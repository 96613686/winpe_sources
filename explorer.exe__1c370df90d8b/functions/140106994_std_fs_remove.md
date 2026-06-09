# __std_fs_remove

- ea: `0x140106994`
- end: `0x140106cd6`
- name: `__std_fs_remove`
- size: `834`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14019f9f4`
- `0x1401a6970`

## callees

- `0x1401040e0`
- `0x140106304`
- `0x140106938`
- `0x140106994`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140106bf3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140106c9b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140106bf3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140106c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140106a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140106b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140106c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140106a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140106b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140106c10`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1401069fd`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140106b79`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140106bcd`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1401069fd`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140106b79`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140106bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106abc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106b4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106b9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106c26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106c91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106abc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106b4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106b9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106c26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140106c91`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140106b20`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x140106b20`

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
0x140106994  mov     [rsp-18h+arg_8], rbx
0x140106999  mov     [rsp-18h+arg_10], rsi
0x14010699e  push    rbp
0x14010699f  push    rdi
0x1401069a0  push    r15
0x1401069a2  mov     rbp, rsp
0x1401069a5  sub     rsp, 60h
0x1401069a9  mov     rax, cs:__security_cookie
0x1401069b0  xor     rax, rsp
0x1401069b3  mov     [rbp+var_8], rax
0x1401069b7  mov     rdi, rcx
0x1401069ba  mov     rdx, rcx
0x1401069bd  lea     rcx, [rbp+hFile]
0x1401069c1  mov     r9d, 2200000h
0x1401069c7  mov     r8d, 10180h
0x1401069cd  call    __std_fs_open_handle
0x1401069d2  mov     ebx, eax
0x1401069d4  mov     r15d, 5
0x1401069da  test    eax, eax
0x1401069dc  jnz     short loc_140106A35
0x1401069de  mov     sil, 1
0x1401069e1  mov     rbx, [rbp+hFile]
0x1401069e5  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1401069e9  mov     r9d, 4; dwBufferSize
0x1401069ef  mov     dword ptr [rbp+FileInformation], 13h
0x1401069f6  mov     rcx, rbx; hFile
0x1401069f9  lea     edx, [r9+11h]; FileInformationClass
0x1401069fd  call    cs:__imp_SetFileInformationByHandle
0x140106a03  test    eax, eax
0x140106a05  jz      loc_140106A94
0x140106a0b  xor     edi, edi
0x140106a0d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140106a11  jz      short loc_140106A24
0x140106a13  mov     rcx, rbx; hObject
0x140106a16  call    cs:__imp_CloseHandle
0x140106a1c  test    eax, eax
0x140106a1e  jz      loc_140106C9B
0x140106a24  mov     byte ptr [rbp+FileInformation], 1
0x140106a28  mov     word ptr [rbp+FileInformation+1], di
0x140106a2c  mov     byte ptr [rbp+FileInformation+3], dil
0x140106a30  mov     dword ptr [rbp+FileInformation+4], edi
0x140106a33  jmp     short loc_140106A8B
0x140106a35  cmp     eax, r15d
0x140106a38  jnz     loc_140106C5D
0x140106a3e  mov     r9d, 2200000h
0x140106a44  lea     rcx, [rbp+hFile]
0x140106a48  mov     r8d, 10000h
0x140106a4e  mov     rdx, rdi
0x140106a51  xor     sil, sil
0x140106a54  call    __std_fs_open_handle
0x140106a59  mov     ebx, eax
0x140106a5b  test    eax, eax
0x140106a5d  jz      short loc_1401069E1
0x140106a5f  mov     rcx, [rbp+hFile]; hObject
0x140106a63  xor     dil, dil
0x140106a66  xor     esi, esi
0x140106a68  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140106a6c  jz      short loc_140106A7C
0x140106a6e  call    cs:__imp_CloseHandle
0x140106a74  test    eax, eax
0x140106a76  jz      loc_140106C9B
0x140106a7c  mov     byte ptr [rbp+FileInformation], dil
0x140106a80  mov     word ptr [rbp+FileInformation+1], si
0x140106a84  mov     byte ptr [rbp+FileInformation+3], sil
0x140106a88  mov     dword ptr [rbp+FileInformation+4], ebx
0x140106a8b  mov     rax, [rbp+FileInformation]
0x140106a8f  jmp     loc_140106CB5
0x140106a94  call    cs:__imp_GetLastError
0x140106a9a  mov     ecx, eax
0x140106a9c  mov     edi, eax
0x140106a9e  sub     ecx, 1
0x140106aa1  jz      short loc_140106ADC
0x140106aa3  sub     ecx, 31h ; '1'
0x140106aa6  jz      short loc_140106ADC
0x140106aa8  cmp     ecx, 25h ; '%'
0x140106aab  jz      short loc_140106ADC
0x140106aad  xor     sil, sil
0x140106ab0  xor     r15d, r15d
0x140106ab3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140106ab7  jz      short loc_140106ACA
0x140106ab9  mov     rcx, rbx; hObject
0x140106abc  call    cs:__imp_CloseHandle
0x140106ac2  test    eax, eax
0x140106ac4  jz      loc_140106C9B
0x140106aca  mov     byte ptr [rbp+FileInformation], sil
0x140106ace  mov     word ptr [rbp+FileInformation+1], r15w
0x140106ad3  mov     byte ptr [rbp+FileInformation+3], r15b
0x140106ad7  jmp     loc_140106A30
0x140106adc  mov     rcx, rbx; hFile
0x140106adf  call    _anonymous_namespace____Set_delete_flag
0x140106ae4  mov     edi, eax
0x140106ae6  test    eax, eax
0x140106ae8  jz      loc_140106A0B
0x140106aee  cmp     eax, r15d
0x140106af1  jnz     loc_140106C32
0x140106af7  test    sil, sil
0x140106afa  jz      loc_140106C32
0x140106b00  xor     eax, eax
0x140106b02  lea     r8, [rbp+var_30]; lpFileInformation
0x140106b06  xorps   xmm0, xmm0
0x140106b09  mov     [rbp+var_10], rax
0x140106b0d  xor     edx, edx; FileInformationClass
0x140106b0f  mov     rcx, rbx; hFile
0x140106b12  movups  [rbp+var_30], xmm0
0x140106b16  lea     edi, [rax+28h]
0x140106b19  mov     r9d, edi; dwBufferSize
0x140106b1c  movups  [rbp+var_20], xmm0
0x140106b20  call    cs:__imp_GetFileInformationByHandleEx
0x140106b26  test    eax, eax
0x140106b28  jnz     short loc_140106B60
0x140106b2a  xor     eax, eax
0x140106b2c  mov     byte ptr [rbp+hFile], 0
0x140106b30  mov     word ptr [rbp+hFile+1], ax
0x140106b34  mov     byte ptr [rbp+hFile+3], al
0x140106b37  call    cs:__imp_GetLastError
0x140106b3d  mov     dword ptr [rbp+hFile+4], eax
0x140106b40  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140106b44  jz      loc_140106CB1
0x140106b4a  mov     rcx, rbx; hObject
0x140106b4d  call    cs:__imp_CloseHandle
0x140106b53  test    eax, eax
0x140106b55  jz      loc_140106BF3
0x140106b5b  jmp     loc_140106CB1
0x140106b60  mov     eax, dword ptr [rbp+var_10]
0x140106b63  test    al, 1
0x140106b65  jz      short loc_140106BDB
0x140106b67  xor     eax, 1
0x140106b6a  lea     r8, [rbp+var_30]; lpFileInformation
0x140106b6e  mov     r9d, edi; dwBufferSize
0x140106b71  mov     dword ptr [rbp+var_10], eax
0x140106b74  xor     edx, edx; FileInformationClass
0x140106b76  mov     rcx, rbx; hFile
0x140106b79  call    cs:__imp_SetFileInformationByHandle
0x140106b7f  test    eax, eax
0x140106b81  jz      short loc_140106B2A
0x140106b83  mov     rcx, rbx; hFile
0x140106b86  call    _anonymous_namespace____Set_delete_flag
0x140106b8b  test    eax, eax
0x140106b8d  jnz     short loc_140106BB8
0x140106b8f  xor     edi, edi
0x140106b91  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140106b95  jz      short loc_140106BA4
0x140106b97  mov     rcx, rbx; hObject
0x140106b9a  call    cs:__imp_CloseHandle
0x140106ba0  test    eax, eax
0x140106ba2  jz      short loc_140106BF3
0x140106ba4  mov     byte ptr [rbp+hFile], 1
0x140106ba8  mov     word ptr [rbp+hFile+1], di
0x140106bac  mov     byte ptr [rbp+hFile+3], dil
0x140106bb0  mov     dword ptr [rbp+hFile+4], edi
0x140106bb3  jmp     loc_140106CB1
0x140106bb8  cmp     eax, r15d
0x140106bbb  jnz     short loc_140106C03
0x140106bbd  or      dword ptr [rbp+var_10], 1
0x140106bc1  lea     r8, [rbp+var_30]; lpFileInformation
0x140106bc5  mov     r9d, edi; dwBufferSize
0x140106bc8  xor     edx, edx; FileInformationClass
0x140106bca  mov     rcx, rbx; hFile
0x140106bcd  call    cs:__imp_SetFileInformationByHandle
0x140106bd3  test    eax, eax
0x140106bd5  jz      loc_140106B2A
0x140106bdb  xor     dil, dil
0x140106bde  xor     esi, esi
0x140106be0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140106be4  jz      short loc_140106BFA
0x140106be6  mov     rcx, rbx; hObject
0x140106be9  call    cs:__imp_CloseHandle
0x140106bef  test    eax, eax
0x140106bf1  jnz     short loc_140106BFA
0x140106bf3  call    cs:__imp_abort
0x140106bfa  mov     dword ptr [rbp+hFile+4], r15d
0x140106bfe  jmp     loc_140106CA5
0x140106c03  xor     eax, eax
0x140106c05  mov     byte ptr [rbp+hFile], 0
0x140106c09  mov     word ptr [rbp+hFile+1], ax
0x140106c0d  mov     byte ptr [rbp+hFile+3], al
0x140106c10  call    cs:__imp_GetLastError
0x140106c16  mov     dword ptr [rbp+hFile+4], eax
0x140106c19  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140106c1d  jz      loc_140106CB1
0x140106c23  mov     rcx, rbx; hObject
0x140106c26  call    cs:__imp_CloseHandle
0x140106c2c  test    eax, eax
0x140106c2e  jz      short loc_140106C9B
0x140106c30  jmp     short loc_140106CB1
0x140106c32  xor     sil, sil
0x140106c35  xor     r15d, r15d
0x140106c38  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140106c3c  jz      short loc_140106C4B
0x140106c3e  mov     rcx, rbx; hObject
0x140106c41  call    cs:__imp_CloseHandle
0x140106c47  test    eax, eax
0x140106c49  jz      short loc_140106C9B
0x140106c4b  mov     byte ptr [rbp+hFile], sil
0x140106c4f  mov     word ptr [rbp+hFile+1], r15w
0x140106c54  mov     byte ptr [rbp+hFile+3], r15b
0x140106c58  jmp     loc_140106BB0
0x140106c5d  xor     dil, dil
0x140106c60  xor     esi, esi
0x140106c62  sub     eax, 2
0x140106c65  jz      short loc_140106C85
0x140106c67  sub     eax, 1
0x140106c6a  jz      short loc_140106C85
0x140106c6c  sub     eax, 32h ; '2'
0x140106c6f  jz      short loc_140106C85
0x140106c71  sub     eax, 0Bh
0x140106c74  jz      short loc_140106C85
0x140106c76  sub     eax, 3Bh ; ';'
0x140106c79  jz      short loc_140106C85
0x140106c7b  sub     eax, 26h ; '&'
0x140106c7e  jz      short loc_140106C85
0x140106c80  cmp     eax, 6Ah ; 'j'
0x140106c83  jnz     short loc_140106C87
0x140106c85  xor     ebx, ebx
0x140106c87  mov     rcx, [rbp+hFile]; hObject
0x140106c8b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140106c8f  jz      short loc_140106CA2
0x140106c91  call    cs:__imp_CloseHandle
0x140106c97  test    eax, eax
0x140106c99  jnz     short loc_140106CA2
0x140106c9b  call    cs:__imp_abort
0x140106ca2  mov     dword ptr [rbp+hFile+4], ebx
0x140106ca5  mov     byte ptr [rbp+hFile], dil
0x140106ca9  mov     word ptr [rbp+hFile+1], si
0x140106cad  mov     byte ptr [rbp+hFile+3], sil
0x140106cb1  mov     rax, [rbp+hFile]
0x140106cb5  mov     rcx, [rbp+var_8]
0x140106cb9  xor     rcx, rsp; StackCookie
0x140106cbc  call    __security_check_cookie
0x140106cc1  lea     r11, [rsp+60h+var_s0]
0x140106cc6  mov     rbx, [r11+28h]
0x140106cca  mov     rsi, [r11+30h]
0x140106cce  mov     rsp, r11
0x140106cd1  pop     r15
0x140106cd3  pop     rdi
0x140106cd4  pop     rbp
0x140106cd5  retn
```
