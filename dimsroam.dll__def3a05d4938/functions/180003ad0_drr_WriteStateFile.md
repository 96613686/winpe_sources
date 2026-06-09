# _drr_WriteStateFile

- ea: `0x180003ad0`
- end: `0x180003d7d`
- name: `_drr_WriteStateFile`
- size: `685`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, const void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003e70`

## callees

- `0x1800035f4`
- `0x180003ad0`
- `0x18000cebc`
- `0x18000d3cc`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c53`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180003d0c`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180003d0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003b23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003bbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003b23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003bbc`

## pseudocode

```c
__int64 __fastcall drr_WriteStateFile(LPCWSTR lpFileName, __int64 a2, const void *a3)
{
  HANDLE FileW; // rdi
  DWORD Directory; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  FileW = CreateFileW(lpFileName, 2u, 0, 0, 2u, 0x8000006u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_12;
  if ( GetLastError() == 3 )
  {
    Directory = DRR_CreateDirectory(Src);
    if ( Directory )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v8 = 19;
LABEL_7:
        WPP_SF_D(v7[2], v8, WPP_fefedfb84db73ff4a9615eb38da9dc9d_Traceguids, Directory);
        return Directory;
      }
      return Directory;
    }
    FileW = CreateFileW(lpFileName, 2u, 0, 0, 2u, 0x8000006u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
LABEL_12:
      Directory = DRR_WriteFile(FileW, a3, 0x70u);
      if ( !Directory )
        Directory = 29;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_fefedfb84db73ff4a9615eb38da9dc9d_Traceguids, Directory);
      CloseHandle(FileW);
      return Directory;
    }
  }
  Directory = GetLastError();
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = 20;
    goto LABEL_7;
  }
  return Directory;
}

```

## disassembly

```asm
0x180003ad0  mov     r11, rsp
0x180003ad3  mov     [r11+10h], rbx
0x180003ad7  mov     [r11+20h], rbp
0x180003adb  push    rsi
0x180003adc  push    rdi
0x180003add  push    r14
0x180003adf  sub     rsp, 60h
0x180003ae3  mov     rax, cs:__security_cookie
0x180003aea  xor     rax, rsp
0x180003aed  mov     [rsp+78h+var_20], rax
0x180003af2  mov     qword ptr [r11-48h], 0
0x180003afa  mov     r14d, 2
0x180003b00  mov     rbp, r8
0x180003b03  mov     [rsp+78h+dwFlagsAndAttributes], 8000006h; dwFlagsAndAttributes
0x180003b0b  mov     edx, r14d; dwDesiredAccess
0x180003b0e  mov     [rsp+78h+var_38], 0
0x180003b16  xor     r9d, r9d; lpSecurityAttributes
0x180003b19  mov     [r11-58h], r14d
0x180003b1d  xor     r8d, r8d; dwShareMode
0x180003b20  mov     rsi, rcx
0x180003b23  call    cs:__imp_CreateFileW
0x180003b29  mov     rdi, rax
0x180003b2c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003b30  jnz     loc_180003BF3
0x180003b36  call    cs:__imp_GetLastError
0x180003b3c  cmp     eax, 3
0x180003b3f  jnz     loc_180003BCB
0x180003b45  mov     rdx, cs:qword_180013868
0x180003b4c  mov     rcx, cs:Src; Src
0x180003b53  call    DRR_CreateDirectory
0x180003b58  mov     ebx, eax
0x180003b5a  test    eax, eax
0x180003b5c  jz      short loc_180003B9A
0x180003b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b65  lea     rax, WPP_GLOBAL_Control
0x180003b6c  cmp     rcx, rax
0x180003b6f  jz      loc_180003C59
0x180003b75  test    [rcx+1Ch], r14b
0x180003b79  jz      loc_180003C59
0x180003b7f  lea     edx, [rdi+14h]
0x180003b82  mov     rcx, [rcx+10h]
0x180003b86  lea     r8, WPP_fefedfb84db73ff4a9615eb38da9dc9d_Traceguids
0x180003b8d  mov     r9d, ebx
0x180003b90  call    WPP_SF_D
0x180003b95  jmp     loc_180003C59
0x180003b9a  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180003ba3  xor     r9d, r9d; lpSecurityAttributes
0x180003ba6  mov     [rsp+78h+dwFlagsAndAttributes], 8000006h; dwFlagsAndAttributes
0x180003bae  xor     r8d, r8d; dwShareMode
0x180003bb1  mov     edx, r14d; dwDesiredAccess
0x180003bb4  mov     [rsp+78h+dwCreationDisposition], r14d; dwCreationDisposition
0x180003bb9  mov     rcx, rsi; lpFileName
0x180003bbc  call    cs:__imp_CreateFileW
0x180003bc2  mov     rdi, rax
0x180003bc5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003bc9  jnz     short loc_180003BF3
0x180003bcb  call    cs:__imp_GetLastError
0x180003bd1  mov     ebx, eax
0x180003bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bda  lea     rax, WPP_GLOBAL_Control
0x180003be1  cmp     rcx, rax
0x180003be4  jz      short loc_180003C59
0x180003be6  test    [rcx+1Ch], r14b
0x180003bea  jz      short loc_180003C59
0x180003bec  mov     edx, 14h
0x180003bf1  jmp     short loc_180003B82
0x180003bf3  lea     r9, [rsp+78h+var_38]
0x180003bf8  mov     r8d, 70h ; 'p'; nNumberOfBytesToWrite
0x180003bfe  mov     rdx, rbp; lpBuffer
0x180003c01  mov     rcx, rdi; hFile
0x180003c04  call    DRR_WriteFile
0x180003c09  mov     ebx, eax
0x180003c0b  test    eax, eax
0x180003c0d  jnz     short loc_180003C19
0x180003c0f  cmp     [rsp+78h+var_38], 70h ; 'p'
0x180003c14  jnb     short loc_180003C7D
0x180003c16  lea     ebx, [rax+1Dh]
0x180003c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c20  lea     rax, WPP_GLOBAL_Control
0x180003c27  cmp     rcx, rax
0x180003c2a  jz      short loc_180003C4A
0x180003c2c  test    [rcx+1Ch], r14b
0x180003c30  jz      short loc_180003C4A
0x180003c32  mov     edx, 15h
0x180003c37  mov     rcx, [rcx+10h]
0x180003c3b  lea     r8, WPP_fefedfb84db73ff4a9615eb38da9dc9d_Traceguids
0x180003c42  mov     r9d, ebx
0x180003c45  call    WPP_SF_D
0x180003c4a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180003c4e  jz      short loc_180003C59
0x180003c50  mov     rcx, rdi; hObject
0x180003c53  call    cs:__imp_CloseHandle
0x180003c59  mov     eax, ebx
0x180003c5b  mov     rcx, [rsp+78h+var_20]
0x180003c60  xor     rcx, rsp; StackCookie
0x180003c63  call    __security_check_cookie
0x180003c68  lea     r11, [rsp+78h+var_18]
0x180003c6d  mov     rbx, [r11+28h]
0x180003c71  mov     rbp, [r11+38h]
0x180003c75  mov     rsp, r11
0x180003c78  pop     r14
0x180003c7a  pop     rdi
0x180003c7b  pop     rsi
0x180003c7c  retn
0x180003c7d  xorps   xmm0, xmm0
0x180003c80  lea     r9, [rsp+78h+var_38]
0x180003c85  mov     r8d, 10h; nNumberOfBytesToWrite
0x180003c8b  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180003c90  mov     rcx, rdi; hFile
0x180003c93  movups  [rsp+78h+Buffer], xmm0
0x180003c98  call    DRR_WriteFile
0x180003c9d  mov     ebx, eax
0x180003c9f  test    eax, eax
0x180003ca1  jnz     short loc_180003CAD
0x180003ca3  cmp     [rsp+78h+var_38], 10h
0x180003ca8  jnb     short loc_180003CD0
0x180003caa  lea     ebx, [rax+1Dh]
0x180003cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cb4  lea     rax, WPP_GLOBAL_Control
0x180003cbb  cmp     rcx, rax
0x180003cbe  jz      short loc_180003C4A
0x180003cc0  test    [rcx+1Ch], r14b
0x180003cc4  jz      short loc_180003C4A
0x180003cc6  mov     edx, 16h
0x180003ccb  jmp     loc_180003C37
0x180003cd0  xor     esi, esi
0x180003cd2  cmp     [rbp+78h], esi
0x180003cd5  jbe     short loc_180003D09
0x180003cd7  mov     rdx, [rbp+70h]
0x180003cdb  lea     r9, [rsp+78h+var_38]
0x180003ce0  mov     r8d, 80h; nNumberOfBytesToWrite
0x180003ce6  mov     rcx, rdi; hFile
0x180003ce9  mov     rdx, [rdx+rsi*8]; lpBuffer
0x180003ced  call    DRR_WriteFile
0x180003cf2  mov     ebx, eax
0x180003cf4  test    eax, eax
0x180003cf6  jnz     short loc_180003D52
0x180003cf8  cmp     [rsp+78h+var_38], 80h
0x180003d00  jb      short loc_180003D4D
0x180003d02  inc     esi
0x180003d04  cmp     esi, [rbp+78h]
0x180003d07  jb      short loc_180003CD7
0x180003d09  mov     rcx, rdi; hFile
0x180003d0c  call    cs:__imp_FlushFileBuffers
0x180003d12  test    eax, eax
0x180003d14  jnz     loc_180003C4A
0x180003d1a  call    cs:__imp_GetLastError
0x180003d20  mov     ebx, eax
0x180003d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d29  lea     rax, WPP_GLOBAL_Control
0x180003d30  cmp     rcx, rax
0x180003d33  jz      loc_180003C4A
0x180003d39  test    [rcx+1Ch], r14b
0x180003d3d  jz      loc_180003C4A
0x180003d43  mov     edx, 18h
0x180003d48  jmp     loc_180003C37
0x180003d4d  mov     ebx, 1Dh
0x180003d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d59  lea     rax, WPP_GLOBAL_Control
0x180003d60  cmp     rcx, rax
0x180003d63  jz      loc_180003C4A
0x180003d69  test    [rcx+1Ch], r14b
0x180003d6d  jz      loc_180003C4A
0x180003d73  mov     edx, 17h
0x180003d78  jmp     loc_180003C37
```
