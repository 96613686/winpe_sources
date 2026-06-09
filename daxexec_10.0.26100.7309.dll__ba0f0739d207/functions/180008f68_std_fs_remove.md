# __std_fs_remove

- ea: `0x180008f68`
- end: `0x1800091ee`
- name: `__std_fs_remove`
- size: `646`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180031fc0`
- `0x1800361c0`

## callees

- `0x1800053a0`
- `0x180008850`
- `0x180008f08`
- `0x180008f68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000910f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800091e7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000910f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800091e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000906e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000906e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000903a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000903a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009101`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180008fd2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180009133`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180009170`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180008fd2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180009133`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180009170`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800090d4`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800090d4`

## pseudocode

```c
__int64 __fastcall _std_fs_remove(__int64 a1)
{
  char v2; // di
  int v3; // ecx
  HANDLE v4; // rbx
  HANDLE v5; // rcx
  int v6; // eax
  DWORD LastError; // eax
  int v9; // eax
  __int64 v10; // [rsp+20h] [rbp-50h]
  HANDLE hFile; // [rsp+28h] [rbp-48h] BYREF
  int FileInformation; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v13[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h]

  v2 = 0;
  v3 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  if ( !v3 )
  {
    v2 = 1;
    goto LABEL_3;
  }
  if ( v3 != 5 )
  {
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    if ( v3 == 2 || v3 == 3 || v3 == 53 || (HIDWORD(v10) = v3, v3 == 123) )
      HIDWORD(v10) = 0;
LABEL_10:
    v5 = hFile;
    if ( hFile == (HANDLE)-1LL )
      return v10;
LABEL_11:
    if ( !CloseHandle(v5) )
      abort();
    return v10;
  }
  v6 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
  if ( v6 )
  {
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    HIDWORD(v10) = v6;
    goto LABEL_10;
  }
LABEL_3:
  v4 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_4:
    v10 = 1;
LABEL_5:
    if ( v4 == (HANDLE)-1LL )
      return v10;
    v5 = v4;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_16;
  LastError = anonymous_namespace_::_Set_delete_flag(v4);
  if ( !LastError )
    goto LABEL_4;
  if ( LastError != 5 || !v2 )
  {
LABEL_16:
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    goto LABEL_17;
  }
  v14 = 0;
  memset(v13, 0, sizeof(v13));
  if ( GetFileInformationByHandleEx(v4, FileBasicInfo, v13, 0x28u) )
  {
    if ( (v14 & 1) == 0 )
    {
      LOBYTE(v10) = 0;
      goto LABEL_33;
    }
    LODWORD(v14) = v14 ^ 1;
    if ( !SetFileInformationByHandle(v4, FileBasicInfo, v13, 0x28u) )
      goto LABEL_22;
    v9 = anonymous_namespace_::_Set_delete_flag(v4);
    if ( !v9 )
    {
      v10 = 1;
      goto LABEL_24;
    }
    if ( v9 == 5 )
    {
      LODWORD(v14) = v14 | 1;
      LOBYTE(v10) = 0;
      if ( !SetFileInformationByHandle(v4, FileBasicInfo, v13, 0x28u) )
        goto LABEL_23;
LABEL_33:
      HIDWORD(v10) = 5;
      *(_WORD *)((char *)&v10 + 1) = 0;
      BYTE3(v10) = 0;
      goto LABEL_24;
    }
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    LastError = GetLastError();
LABEL_17:
    HIDWORD(v10) = LastError;
    goto LABEL_5;
  }
LABEL_22:
  LOBYTE(v10) = 0;
LABEL_23:
  *(_WORD *)((char *)&v10 + 1) = 0;
  BYTE3(v10) = 0;
  HIDWORD(v10) = GetLastError();
LABEL_24:
  if ( v4 != (HANDLE)-1LL && !CloseHandle(v4) )
    abort();
  return v10;
}

```

## disassembly

```asm
0x180008f68  mov     [rsp-8+arg_8], rbx
0x180008f6d  mov     [rsp-8+arg_10], rsi
0x180008f72  mov     [rsp-8+arg_18], rdi
0x180008f77  push    rbp
0x180008f78  mov     rbp, rsp
0x180008f7b  sub     rsp, 70h
0x180008f7f  mov     rax, cs:__security_cookie
0x180008f86  xor     rax, rsp
0x180008f89  mov     [rbp+var_10], rax
0x180008f8d  mov     rbx, rcx
0x180008f90  mov     rdx, rcx
0x180008f93  xor     esi, esi
0x180008f95  lea     rcx, [rbp+hFile]
0x180008f99  mov     r9d, 2200000h
0x180008f9f  mov     r8d, 10180h
0x180008fa5  mov     dil, sil
0x180008fa8  call    __std_fs_open_handle
0x180008fad  mov     ecx, eax
0x180008faf  test    eax, eax
0x180008fb1  jnz     short loc_180008FFB
0x180008fb3  mov     dil, 1
0x180008fb6  mov     rbx, [rbp+hFile]
0x180008fba  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180008fbe  mov     r9d, 4; dwBufferSize
0x180008fc4  mov     [rbp+FileInformation], 13h
0x180008fcb  mov     rcx, rbx; hFile
0x180008fce  lea     edx, [r9+11h]; FileInformationClass
0x180008fd2  call    cs:__imp_SetFileInformationByHandle
0x180008fd8  test    eax, eax
0x180008fda  jz      loc_18000906E
0x180008fe0  xor     eax, eax
0x180008fe2  mov     byte ptr [rbp+var_50], 1
0x180008fe6  mov     word ptr [rbp+var_50+1], ax
0x180008fea  mov     byte ptr [rbp+var_50+3], al
0x180008fed  mov     dword ptr [rbp+var_50+4], esi
0x180008ff0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008ff4  jz      short loc_180009048
0x180008ff6  mov     rcx, rbx
0x180008ff9  jmp     short loc_18000903A
0x180008ffb  cmp     ecx, 5
0x180008ffe  jnz     loc_1800091B5
0x180009004  mov     r9d, 2200000h
0x18000900a  lea     rcx, [rbp+hFile]
0x18000900e  mov     r8d, 10000h
0x180009014  mov     rdx, rbx
0x180009017  call    __std_fs_open_handle
0x18000901c  test    eax, eax
0x18000901e  jz      short loc_180008FB6
0x180009020  xor     ecx, ecx
0x180009022  mov     byte ptr [rbp+var_50], sil
0x180009026  mov     word ptr [rbp+var_50+1], cx
0x18000902a  mov     byte ptr [rbp+var_50+3], cl
0x18000902d  mov     dword ptr [rbp+var_50+4], eax
0x180009030  mov     rcx, [rbp+hFile]; hObject
0x180009034  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009038  jz      short loc_180009048
0x18000903a  call    cs:__imp_CloseHandle
0x180009040  test    eax, eax
0x180009042  jz      loc_1800091E7
0x180009048  mov     rax, [rbp+var_50]
0x18000904c  mov     rcx, [rbp+var_10]
0x180009050  xor     rcx, rsp; StackCookie
0x180009053  call    __security_check_cookie
0x180009058  lea     r11, [rsp+70h+var_s0]
0x18000905d  mov     rbx, [r11+18h]
0x180009061  mov     rsi, [r11+20h]
0x180009065  mov     rdi, [r11+28h]
0x180009069  mov     rsp, r11
0x18000906c  pop     rbp
0x18000906d  retn
0x18000906e  call    cs:__imp_GetLastError
0x180009074  mov     ecx, eax
0x180009076  sub     ecx, 1
0x180009079  jz      short loc_18000909A
0x18000907b  sub     ecx, 31h ; '1'
0x18000907e  jz      short loc_18000909A
0x180009080  cmp     ecx, 25h ; '%'
0x180009083  jz      short loc_18000909A
0x180009085  xor     ecx, ecx
0x180009087  mov     byte ptr [rbp+var_50], sil
0x18000908b  mov     word ptr [rbp+var_50+1], cx
0x18000908f  mov     byte ptr [rbp+var_50+3], cl
0x180009092  mov     dword ptr [rbp+var_50+4], eax
0x180009095  jmp     loc_180008FF0
0x18000909a  mov     rcx, rbx; hFile
0x18000909d  call    _anonymous_namespace____Set_delete_flag
0x1800090a2  test    eax, eax
0x1800090a4  jz      loc_180008FE0
0x1800090aa  cmp     eax, 5
0x1800090ad  jnz     short loc_180009085
0x1800090af  test    dil, dil
0x1800090b2  jz      short loc_180009085
0x1800090b4  xor     eax, eax
0x1800090b6  lea     r8, [rbp+var_38]; lpFileInformation
0x1800090ba  xorps   xmm0, xmm0
0x1800090bd  mov     [rbp+var_18], rax
0x1800090c1  xor     edx, edx; FileInformationClass
0x1800090c3  mov     rcx, rbx; hFile
0x1800090c6  movups  [rbp+var_38], xmm0
0x1800090ca  lea     edi, [rax+28h]
0x1800090cd  mov     r9d, edi; dwBufferSize
0x1800090d0  movups  [rbp+var_28], xmm0
0x1800090d4  call    cs:__imp_GetFileInformationByHandleEx
0x1800090da  test    eax, eax
0x1800090dc  jnz     short loc_180009116
0x1800090de  mov     byte ptr [rbp+var_50], sil
0x1800090e2  xor     eax, eax
0x1800090e4  mov     word ptr [rbp+var_50+1], ax
0x1800090e8  mov     byte ptr [rbp+var_50+3], al
0x1800090eb  call    cs:__imp_GetLastError
0x1800090f1  mov     dword ptr [rbp+var_50+4], eax
0x1800090f4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800090f8  jz      loc_180009048
0x1800090fe  mov     rcx, rbx; hObject
0x180009101  call    cs:__imp_CloseHandle
0x180009107  test    eax, eax
0x180009109  jnz     loc_180009048
0x18000910f  call    cs:__imp_abort
0x180009116  mov     eax, dword ptr [rbp+var_18]
0x180009119  test    al, 1
0x18000911b  jz      loc_1800091AF
0x180009121  xor     eax, 1
0x180009124  lea     r8, [rbp+var_38]; lpFileInformation
0x180009128  mov     r9d, edi; dwBufferSize
0x18000912b  mov     dword ptr [rbp+var_18], eax
0x18000912e  xor     edx, edx; FileInformationClass
0x180009130  mov     rcx, rbx; hFile
0x180009133  call    cs:__imp_SetFileInformationByHandle
0x180009139  test    eax, eax
0x18000913b  jz      short loc_1800090DE
0x18000913d  mov     rcx, rbx; hFile
0x180009140  call    _anonymous_namespace____Set_delete_flag
0x180009145  test    eax, eax
0x180009147  jnz     short loc_18000915B
0x180009149  xor     eax, eax
0x18000914b  mov     byte ptr [rbp+var_50], 1
0x18000914f  mov     word ptr [rbp+var_50+1], ax
0x180009153  mov     byte ptr [rbp+var_50+3], al
0x180009156  mov     dword ptr [rbp+var_50+4], esi
0x180009159  jmp     short loc_1800090F4
0x18000915b  cmp     eax, 5
0x18000915e  jnz     short loc_180009197
0x180009160  or      dword ptr [rbp+var_18], 1
0x180009164  lea     r8, [rbp+var_38]; lpFileInformation
0x180009168  mov     r9d, edi; dwBufferSize
0x18000916b  xor     edx, edx; FileInformationClass
0x18000916d  mov     rcx, rbx; hFile
0x180009170  call    cs:__imp_SetFileInformationByHandle
0x180009176  mov     byte ptr [rbp+var_50], sil
0x18000917a  test    eax, eax
0x18000917c  jz      loc_1800090E2
0x180009182  xor     eax, eax
0x180009184  mov     dword ptr [rbp+var_50+4], 5
0x18000918b  mov     word ptr [rbp+var_50+1], ax
0x18000918f  mov     byte ptr [rbp+var_50+3], al
0x180009192  jmp     loc_1800090F4
0x180009197  xor     eax, eax
0x180009199  mov     byte ptr [rbp+var_50], sil
0x18000919d  mov     word ptr [rbp+var_50+1], ax
0x1800091a1  mov     byte ptr [rbp+var_50+3], al
0x1800091a4  call    cs:__imp_GetLastError
0x1800091aa  jmp     loc_180009092
0x1800091af  mov     byte ptr [rbp+var_50], sil
0x1800091b3  jmp     short loc_180009182
0x1800091b5  xor     eax, eax
0x1800091b7  mov     byte ptr [rbp+var_50], sil
0x1800091bb  mov     word ptr [rbp+var_50+1], ax
0x1800091bf  mov     byte ptr [rbp+var_50+3], al
0x1800091c2  mov     eax, ecx
0x1800091c4  sub     eax, 2
0x1800091c7  jz      short loc_1800091DF
0x1800091c9  sub     eax, 1
0x1800091cc  jz      short loc_1800091DF
0x1800091ce  sub     eax, 32h ; '2'
0x1800091d1  jz      short loc_1800091DF
0x1800091d3  mov     dword ptr [rbp+var_50+4], ecx
0x1800091d6  cmp     eax, 46h ; 'F'
0x1800091d9  jnz     loc_180009030
0x1800091df  mov     dword ptr [rbp+var_50+4], esi
0x1800091e2  jmp     loc_180009030
0x1800091e7  call    cs:__imp_abort
```
