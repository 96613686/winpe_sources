# CNtfsStorage::Stat(tagSTATSTG *,ulong)

- ea: `0x180054b10`
- end: `0x180054ccd`
- name: `?Stat@CNtfsStorage@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `445`
- prototype: `__int64 __fastcall(CNtfsStorage *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023e70`
- `0x180042800`
- `0x1800537f8`
- `0x180054b10`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bed`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180054be3`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180054be3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054c93`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::Stat(CNtfsStorage *this, struct tagSTATSTG *a2, int a3)
{
  void *v5; // rdi
  int FilePath; // eax
  unsigned int v9; // ebx
  void *v10; // rcx
  signed int LastError; // eax
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  int v14; // eax
  __int32 v15; // eax
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  LPVOID pv; // [rsp+20h] [rbp-69h] BYREF
  __int128 v20; // [rsp+30h] [rbp-59h]
  __int128 v21; // [rsp+40h] [rbp-49h]
  __int128 v22; // [rsp+50h] [rbp-39h]
  __m256i v23; // [rsp+60h] [rbp-29h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+80h] [rbp-9h] BYREF

  HIDWORD(v20) = 0;
  v5 = 0;
  *(_OWORD *)&v23.m256i_u64[1] = 0u;
  pv = 0;
  v23.m256i_i32[7] = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !(unsigned int)IsValidReadPtrIn(a2, 0x50u) )
    return 2147680265LL;
  if ( (a3 & 0xFFFFFFFE) != 0 )
    return 2147680511LL;
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8, 0xFFFFFFFFLL);
  if ( (*((_BYTE *)this + 200) & 4) != 0 )
  {
    v9 = -2147286782;
LABEL_13:
    if ( v5 )
      CoTaskMemFree(v5);
    goto LABEL_15;
  }
  if ( (a3 & 1) == 0 )
  {
    FilePath = CNtfsStorage::GetFilePath(this, (unsigned __int16 **)&pv);
    v5 = pv;
    v9 = FilePath;
    if ( FilePath < 0 )
      goto LABEL_13;
  }
  v10 = (void *)*((_QWORD *)this + 13);
  DWORD2(v20) = 1;
  if ( !GetFileInformationByHandle(v10, &FileInformation) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_13;
  }
  v12 = *((_OWORD *)this + 8);
  *(_QWORD *)&v21 = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow);
  *((_QWORD *)&v21 + 1) = FileInformation.ftLastWriteTime;
  v13 = v21;
  v22 = *(_OWORD *)&FileInformation.ftCreationTime.dwLowDateTime;
  v14 = *((_DWORD *)this + 18);
  *(_OWORD *)&v23.m256i_u64[1] = v12;
  *(_QWORD *)&v20 = v5;
  v9 = 0;
  v23.m256i_i32[0] = v14 & 0xFFFFEFFF;
  v15 = *((_DWORD *)this + 31);
  *(_OWORD *)a2 = v20;
  v23.m256i_i32[1] = 0;
  v16 = v22;
  *((_OWORD *)a2 + 1) = v13;
  v23.m256i_i32[6] = v15;
  v17 = *(_OWORD *)v23.m256i_i8;
  *((_OWORD *)a2 + 2) = v16;
  v18 = *(_OWORD *)&v23.m256i_u64[2];
  *((_OWORD *)a2 + 3) = v17;
  *((_OWORD *)a2 + 4) = v18;
LABEL_15:
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 32LL))((char *)this + 8);
  return v9;
}

```

## disassembly

```asm
0x180054b10  mov     [rsp-8+arg_10], rbx
0x180054b15  push    rbp
0x180054b16  push    rsi
0x180054b17  push    rdi
0x180054b18  push    r14
0x180054b1a  push    r15
0x180054b1c  lea     rbp, [rsp-37h]
0x180054b21  sub     rsp, 0C0h
0x180054b28  mov     rax, cs:__security_cookie
0x180054b2f  xor     rax, rsp
0x180054b32  mov     [rbp+57h+var_28], rax
0x180054b36  xor     eax, eax
0x180054b38  xorps   xmm0, xmm0
0x180054b3b  mov     r15, rdx
0x180054b3e  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180054b41  mov     rsi, rcx
0x180054b44  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x180054b47  xor     edi, edi
0x180054b49  mov     qword ptr [rbp+57h+var_80+8], rax
0x180054b4d  lea     edx, [rax+50h]; unsigned __int64
0x180054b50  mov     [rbp+57h+pv], rdi
0x180054b54  mov     rcx, r15; void *
0x180054b57  mov     qword ptr [rbp+57h+var_80+10h], rax
0x180054b5b  mov     ebx, r8d
0x180054b5e  mov     [rbp+57h+var_64], eax
0x180054b61  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180054b65  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180054b69  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180054b6d  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x180054b72  test    eax, eax
0x180054b74  jnz     short loc_180054B80
0x180054b76  mov     eax, 80030009h
0x180054b7b  jmp     loc_180054CAA
0x180054b80  test    ebx, 0FFFFFFFEh
0x180054b86  jz      short loc_180054B92
0x180054b88  mov     eax, 800300FFh
0x180054b8d  jmp     loc_180054CAA
0x180054b92  lea     r14, [rsi+8]
0x180054b96  or      edx, 0FFFFFFFFh
0x180054b99  mov     rax, [r14]
0x180054b9c  mov     rcx, r14
0x180054b9f  mov     rax, [rax+18h]
0x180054ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ba8  test    byte ptr [rsi+0C8h], 4
0x180054baf  jnz     loc_180054C86
0x180054bb5  test    bl, 1
0x180054bb8  jnz     short loc_180054BD4
0x180054bba  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x180054bbe  mov     rcx, rsi; this
0x180054bc1  call    ?GetFilePath@CNtfsStorage@@AEAAJPEAPEAG@Z; CNtfsStorage::GetFilePath(ushort * *)
0x180054bc6  mov     rdi, [rbp+57h+pv]
0x180054bca  mov     ebx, eax
0x180054bcc  test    eax, eax
0x180054bce  js      loc_180054C8B
0x180054bd4  mov     rcx, [rsi+68h]; hFile
0x180054bd8  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180054bdc  mov     dword ptr [rbp+57h+var_B0+8], 1
0x180054be3  call    cs:__imp_GetFileInformationByHandle
0x180054be9  test    eax, eax
0x180054beb  jnz     short loc_180054C0B
0x180054bed  call    cs:__imp_GetLastError
0x180054bf3  mov     ebx, eax
0x180054bf5  test    eax, eax
0x180054bf7  jle     loc_180054C8B
0x180054bfd  movzx   ebx, ax
0x180054c00  or      ebx, 80070000h
0x180054c06  jmp     loc_180054C8B
0x180054c0b  movups  xmm0, xmmword ptr [rsi+80h]
0x180054c12  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x180054c15  mov     dword ptr [rbp+57h+var_A0], eax
0x180054c18  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x180054c1b  mov     dword ptr [rbp+57h+var_A0+4], eax
0x180054c1e  mov     rax, qword ptr [rbp+57h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x180054c22  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180054c26  mov     rax, qword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x180054c2a  movaps  xmm1, [rbp+57h+var_A0]
0x180054c2e  mov     qword ptr [rbp+57h+var_90+8], rax
0x180054c32  mov     rax, qword ptr [rbp+57h+FileInformation.ftCreationTime.dwLowDateTime]
0x180054c36  mov     qword ptr [rbp+57h+var_90], rax
0x180054c3a  mov     eax, [rsi+48h]
0x180054c3d  movdqu  xmmword ptr [rbp+57h+var_80+8], xmm0
0x180054c42  btr     eax, 0Ch
0x180054c46  mov     qword ptr [rbp+57h+var_B0], rdi
0x180054c4a  movaps  xmm0, [rbp+57h+var_B0]
0x180054c4e  xor     ebx, ebx
0x180054c50  mov     dword ptr [rbp+57h+var_80], eax
0x180054c53  mov     eax, [rsi+7Ch]
0x180054c56  movups  xmmword ptr [r15], xmm0
0x180054c5a  mov     dword ptr [rbp+57h+var_80+4], 0
0x180054c61  movaps  xmm0, [rbp+57h+var_90]
0x180054c65  movups  xmmword ptr [r15+10h], xmm1
0x180054c6a  mov     [rbp+57h+var_68], eax
0x180054c6d  movaps  xmm1, xmmword ptr [rbp+57h+var_80]
0x180054c71  movups  xmmword ptr [r15+20h], xmm0
0x180054c76  movaps  xmm0, xmmword ptr [rbp-19h]
0x180054c7a  movups  xmmword ptr [r15+30h], xmm1
0x180054c7f  movups  xmmword ptr [r15+40h], xmm0
0x180054c84  jmp     short loc_180054C99
0x180054c86  mov     ebx, 80030102h
0x180054c8b  test    rdi, rdi
0x180054c8e  jz      short loc_180054C99
0x180054c90  mov     rcx, rdi; pv
0x180054c93  call    cs:__imp_CoTaskMemFree
0x180054c99  mov     rax, [r14]
0x180054c9c  mov     rcx, r14
0x180054c9f  mov     rax, [rax+20h]
0x180054ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ca8  mov     eax, ebx
0x180054caa  mov     rcx, [rbp+57h+var_28]
0x180054cae  xor     rcx, rsp; StackCookie
0x180054cb1  call    __security_check_cookie
0x180054cb6  mov     rbx, [rsp+0E0h+arg_10]
0x180054cbe  add     rsp, 0C0h
0x180054cc5  pop     r15
0x180054cc7  pop     r14
0x180054cc9  pop     rdi
0x180054cca  pop     rsi
0x180054ccb  pop     rbp
0x180054ccc  retn
```
