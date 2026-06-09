# __std_fs_remove

- ea: `0x18000ab1c`
- end: `0x18000ae5e`
- name: `__std_fs_remove`
- size: `834`
- prototype: `HANDLE __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180033bb0`
- `0x180037b20`

## callees

- `0x180004f70`
- `0x18000a394`
- `0x18000aac0`
- `0x18000ab1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000ad7b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000ae23`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000ad7b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000ae23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000adc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae19`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ab85`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ad01`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ad55`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ab85`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ad01`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ad55`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000aca8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000aca8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ab1c  mov     [rsp-18h+arg_8], rbx
0x18000ab21  mov     [rsp-18h+arg_10], rsi
0x18000ab26  push    rbp
0x18000ab27  push    rdi
0x18000ab28  push    r15
0x18000ab2a  mov     rbp, rsp
0x18000ab2d  sub     rsp, 60h
0x18000ab31  mov     rax, cs:__security_cookie
0x18000ab38  xor     rax, rsp
0x18000ab3b  mov     [rbp+var_8], rax
0x18000ab3f  mov     rdi, rcx
0x18000ab42  mov     rdx, rcx
0x18000ab45  lea     rcx, [rbp+hFile]
0x18000ab49  mov     r9d, 2200000h
0x18000ab4f  mov     r8d, 10180h
0x18000ab55  call    __std_fs_open_handle
0x18000ab5a  mov     ebx, eax
0x18000ab5c  mov     r15d, 5
0x18000ab62  test    eax, eax
0x18000ab64  jnz     short loc_18000ABBD
0x18000ab66  mov     sil, 1
0x18000ab69  mov     rbx, [rbp+hFile]
0x18000ab6d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18000ab71  mov     r9d, 4; dwBufferSize
0x18000ab77  mov     dword ptr [rbp+FileInformation], 13h
0x18000ab7e  mov     rcx, rbx; hFile
0x18000ab81  lea     edx, [r9+11h]; FileInformationClass
0x18000ab85  call    cs:__imp_SetFileInformationByHandle
0x18000ab8b  test    eax, eax
0x18000ab8d  jz      loc_18000AC1C
0x18000ab93  xor     edi, edi
0x18000ab95  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ab99  jz      short loc_18000ABAC
0x18000ab9b  mov     rcx, rbx; hObject
0x18000ab9e  call    cs:__imp_CloseHandle
0x18000aba4  test    eax, eax
0x18000aba6  jz      loc_18000AE23
0x18000abac  mov     byte ptr [rbp+FileInformation], 1
0x18000abb0  mov     word ptr [rbp+FileInformation+1], di
0x18000abb4  mov     byte ptr [rbp+FileInformation+3], dil
0x18000abb8  mov     dword ptr [rbp+FileInformation+4], edi
0x18000abbb  jmp     short loc_18000AC13
0x18000abbd  cmp     eax, r15d
0x18000abc0  jnz     loc_18000ADE5
0x18000abc6  mov     r9d, 2200000h
0x18000abcc  lea     rcx, [rbp+hFile]
0x18000abd0  mov     r8d, 10000h
0x18000abd6  mov     rdx, rdi
0x18000abd9  xor     sil, sil
0x18000abdc  call    __std_fs_open_handle
0x18000abe1  mov     ebx, eax
0x18000abe3  test    eax, eax
0x18000abe5  jz      short loc_18000AB69
0x18000abe7  mov     rcx, [rbp+hFile]; hObject
0x18000abeb  xor     dil, dil
0x18000abee  xor     esi, esi
0x18000abf0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000abf4  jz      short loc_18000AC04
0x18000abf6  call    cs:__imp_CloseHandle
0x18000abfc  test    eax, eax
0x18000abfe  jz      loc_18000AE23
0x18000ac04  mov     byte ptr [rbp+FileInformation], dil
0x18000ac08  mov     word ptr [rbp+FileInformation+1], si
0x18000ac0c  mov     byte ptr [rbp+FileInformation+3], sil
0x18000ac10  mov     dword ptr [rbp+FileInformation+4], ebx
0x18000ac13  mov     rax, [rbp+FileInformation]
0x18000ac17  jmp     loc_18000AE3D
0x18000ac1c  call    cs:__imp_GetLastError
0x18000ac22  mov     ecx, eax
0x18000ac24  mov     edi, eax
0x18000ac26  sub     ecx, 1
0x18000ac29  jz      short loc_18000AC64
0x18000ac2b  sub     ecx, 31h ; '1'
0x18000ac2e  jz      short loc_18000AC64
0x18000ac30  cmp     ecx, 25h ; '%'
0x18000ac33  jz      short loc_18000AC64
0x18000ac35  xor     sil, sil
0x18000ac38  xor     r15d, r15d
0x18000ac3b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ac3f  jz      short loc_18000AC52
0x18000ac41  mov     rcx, rbx; hObject
0x18000ac44  call    cs:__imp_CloseHandle
0x18000ac4a  test    eax, eax
0x18000ac4c  jz      loc_18000AE23
0x18000ac52  mov     byte ptr [rbp+FileInformation], sil
0x18000ac56  mov     word ptr [rbp+FileInformation+1], r15w
0x18000ac5b  mov     byte ptr [rbp+FileInformation+3], r15b
0x18000ac5f  jmp     loc_18000ABB8
0x18000ac64  mov     rcx, rbx; hFile
0x18000ac67  call    _anonymous_namespace____Set_delete_flag
0x18000ac6c  mov     edi, eax
0x18000ac6e  test    eax, eax
0x18000ac70  jz      loc_18000AB93
0x18000ac76  cmp     eax, r15d
0x18000ac79  jnz     loc_18000ADBA
0x18000ac7f  test    sil, sil
0x18000ac82  jz      loc_18000ADBA
0x18000ac88  xor     eax, eax
0x18000ac8a  lea     r8, [rbp+var_30]; lpFileInformation
0x18000ac8e  xorps   xmm0, xmm0
0x18000ac91  mov     [rbp+var_10], rax
0x18000ac95  xor     edx, edx; FileInformationClass
0x18000ac97  mov     rcx, rbx; hFile
0x18000ac9a  movups  [rbp+var_30], xmm0
0x18000ac9e  lea     edi, [rax+28h]
0x18000aca1  mov     r9d, edi; dwBufferSize
0x18000aca4  movups  [rbp+var_20], xmm0
0x18000aca8  call    cs:__imp_GetFileInformationByHandleEx
0x18000acae  test    eax, eax
0x18000acb0  jnz     short loc_18000ACE8
0x18000acb2  xor     eax, eax
0x18000acb4  mov     byte ptr [rbp+hFile], 0
0x18000acb8  mov     word ptr [rbp+hFile+1], ax
0x18000acbc  mov     byte ptr [rbp+hFile+3], al
0x18000acbf  call    cs:__imp_GetLastError
0x18000acc5  mov     dword ptr [rbp+hFile+4], eax
0x18000acc8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000accc  jz      loc_18000AE39
0x18000acd2  mov     rcx, rbx; hObject
0x18000acd5  call    cs:__imp_CloseHandle
0x18000acdb  test    eax, eax
0x18000acdd  jz      loc_18000AD7B
0x18000ace3  jmp     loc_18000AE39
0x18000ace8  mov     eax, dword ptr [rbp+var_10]
0x18000aceb  test    al, 1
0x18000aced  jz      short loc_18000AD63
0x18000acef  xor     eax, 1
0x18000acf2  lea     r8, [rbp+var_30]; lpFileInformation
0x18000acf6  mov     r9d, edi; dwBufferSize
0x18000acf9  mov     dword ptr [rbp+var_10], eax
0x18000acfc  xor     edx, edx; FileInformationClass
0x18000acfe  mov     rcx, rbx; hFile
0x18000ad01  call    cs:__imp_SetFileInformationByHandle
0x18000ad07  test    eax, eax
0x18000ad09  jz      short loc_18000ACB2
0x18000ad0b  mov     rcx, rbx; hFile
0x18000ad0e  call    _anonymous_namespace____Set_delete_flag
0x18000ad13  test    eax, eax
0x18000ad15  jnz     short loc_18000AD40
0x18000ad17  xor     edi, edi
0x18000ad19  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ad1d  jz      short loc_18000AD2C
0x18000ad1f  mov     rcx, rbx; hObject
0x18000ad22  call    cs:__imp_CloseHandle
0x18000ad28  test    eax, eax
0x18000ad2a  jz      short loc_18000AD7B
0x18000ad2c  mov     byte ptr [rbp+hFile], 1
0x18000ad30  mov     word ptr [rbp+hFile+1], di
0x18000ad34  mov     byte ptr [rbp+hFile+3], dil
0x18000ad38  mov     dword ptr [rbp+hFile+4], edi
0x18000ad3b  jmp     loc_18000AE39
0x18000ad40  cmp     eax, r15d
0x18000ad43  jnz     short loc_18000AD8B
0x18000ad45  or      dword ptr [rbp+var_10], 1
0x18000ad49  lea     r8, [rbp+var_30]; lpFileInformation
0x18000ad4d  mov     r9d, edi; dwBufferSize
0x18000ad50  xor     edx, edx; FileInformationClass
0x18000ad52  mov     rcx, rbx; hFile
0x18000ad55  call    cs:__imp_SetFileInformationByHandle
0x18000ad5b  test    eax, eax
0x18000ad5d  jz      loc_18000ACB2
0x18000ad63  xor     dil, dil
0x18000ad66  xor     esi, esi
0x18000ad68  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ad6c  jz      short loc_18000AD82
0x18000ad6e  mov     rcx, rbx; hObject
0x18000ad71  call    cs:__imp_CloseHandle
0x18000ad77  test    eax, eax
0x18000ad79  jnz     short loc_18000AD82
0x18000ad7b  call    cs:__imp_abort
0x18000ad82  mov     dword ptr [rbp+hFile+4], r15d
0x18000ad86  jmp     loc_18000AE2D
0x18000ad8b  xor     eax, eax
0x18000ad8d  mov     byte ptr [rbp+hFile], 0
0x18000ad91  mov     word ptr [rbp+hFile+1], ax
0x18000ad95  mov     byte ptr [rbp+hFile+3], al
0x18000ad98  call    cs:__imp_GetLastError
0x18000ad9e  mov     dword ptr [rbp+hFile+4], eax
0x18000ada1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ada5  jz      loc_18000AE39
0x18000adab  mov     rcx, rbx; hObject
0x18000adae  call    cs:__imp_CloseHandle
0x18000adb4  test    eax, eax
0x18000adb6  jz      short loc_18000AE23
0x18000adb8  jmp     short loc_18000AE39
0x18000adba  xor     sil, sil
0x18000adbd  xor     r15d, r15d
0x18000adc0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000adc4  jz      short loc_18000ADD3
0x18000adc6  mov     rcx, rbx; hObject
0x18000adc9  call    cs:__imp_CloseHandle
0x18000adcf  test    eax, eax
0x18000add1  jz      short loc_18000AE23
0x18000add3  mov     byte ptr [rbp+hFile], sil
0x18000add7  mov     word ptr [rbp+hFile+1], r15w
0x18000addc  mov     byte ptr [rbp+hFile+3], r15b
0x18000ade0  jmp     loc_18000AD38
0x18000ade5  xor     dil, dil
0x18000ade8  xor     esi, esi
0x18000adea  sub     eax, 2
0x18000aded  jz      short loc_18000AE0D
0x18000adef  sub     eax, 1
0x18000adf2  jz      short loc_18000AE0D
0x18000adf4  sub     eax, 32h ; '2'
0x18000adf7  jz      short loc_18000AE0D
0x18000adf9  sub     eax, 0Bh
0x18000adfc  jz      short loc_18000AE0D
0x18000adfe  sub     eax, 3Bh ; ';'
0x18000ae01  jz      short loc_18000AE0D
0x18000ae03  sub     eax, 26h ; '&'
0x18000ae06  jz      short loc_18000AE0D
0x18000ae08  cmp     eax, 6Ah ; 'j'
0x18000ae0b  jnz     short loc_18000AE0F
0x18000ae0d  xor     ebx, ebx
0x18000ae0f  mov     rcx, [rbp+hFile]; hObject
0x18000ae13  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ae17  jz      short loc_18000AE2A
0x18000ae19  call    cs:__imp_CloseHandle
0x18000ae1f  test    eax, eax
0x18000ae21  jnz     short loc_18000AE2A
0x18000ae23  call    cs:__imp_abort
0x18000ae2a  mov     dword ptr [rbp+hFile+4], ebx
0x18000ae2d  mov     byte ptr [rbp+hFile], dil
0x18000ae31  mov     word ptr [rbp+hFile+1], si
0x18000ae35  mov     byte ptr [rbp+hFile+3], sil
0x18000ae39  mov     rax, [rbp+hFile]
0x18000ae3d  mov     rcx, [rbp+var_8]
0x18000ae41  xor     rcx, rsp; StackCookie
0x18000ae44  call    __security_check_cookie
0x18000ae49  lea     r11, [rsp+60h+var_s0]
0x18000ae4e  mov     rbx, [r11+28h]
0x18000ae52  mov     rsi, [r11+30h]
0x18000ae56  mov     rsp, r11
0x18000ae59  pop     r15
0x18000ae5b  pop     rdi
0x18000ae5c  pop     rbp
0x18000ae5d  retn
```
