# ILS_ReadElementFromFile(ushort const *,ushort const *,ushort const * const,ulong,uchar * *,ulong *)

- ea: `0x18005a9f4`
- end: `0x18005abad`
- name: `?ILS_ReadElementFromFile@@YAHPEBG0QEBGKPEAPEAEPEAK@Z`
- size: `441`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *const, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180034c88`
- `0x18005a7cc`
- `0x180072e24`

## callees

- `0x180028d60`
- `0x180030e60`
- `0x180059df8`
- `0x18005a9f4`
- `0x18005b130`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ab89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ab61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ab61`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005ab4b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005ab4b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005aaf3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005aaf3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18005ab0b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18005ab0b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18011910a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18011910a`

## pseudocode

```c
__int64 __fastcall ILS_ReadElementFromFile(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *const a3,
        __int16 a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  __int64 v6; // rbp
  void *v8; // rsi
  unsigned int v9; // r14d
  WCHAR *v10; // r15
  SIZE_T v11; // rbx
  __int64 result; // rax
  __int64 v13; // rdi
  DWORD dwFlagsAndAttributes; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  void *v17; // rax
  DWORD LastError; // eax
  DWORD v19; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-70h] BYREF
  _QWORD v22[3]; // [rsp+58h] [rbp-60h] BYREF

  v6 = -1;
  v22[0] = a1;
  v22[1] = a2;
  v8 = 0;
  v22[2] = a3;
  v9 = 1;
  v21[0] = 3;
  NumberOfBytesRead = 0;
  v21[1] = v22;
  v10 = FormatSystemNamePath(1u, (struct _SYSTEM_NAME_GROUP *const)v21);
  if ( !v10 )
    goto LABEL_2;
  v13 = 0;
  dwFlagsAndAttributes = ((a4 & 0x800) << 14) | 0x80;
  while ( 1 )
  {
    FileW = CreateFileW(v10, 0x80000000, 1u, 0, 3u, dwFlagsAndAttributes, 0);
    v6 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL )
      break;
    LastError = GetLastError();
    if ( LastError != 32 || (unsigned int)v13 >= 6 )
    {
      if ( LastError != 5 )
      {
        if ( LastError == 3 )
          LastError = 2;
LABEL_13:
        v19 = LastError;
LABEL_14:
        SetLastError(v19);
        goto LABEL_2;
      }
      if ( (_DWORD)v13 )
        goto LABEL_13;
    }
    Sleep(*((_DWORD *)qword_18013E670 + v13));
    v13 = (unsigned int)(v13 + 1);
  }
  FileSize = GetFileSize(FileW, 0);
  v11 = FileSize;
  if ( FileSize == -1 )
  {
    if ( GetLastError() )
    {
LABEL_2:
      v9 = 0;
      PkiDefaultCryptFree(v8);
      v8 = 0;
      LODWORD(v11) = 0;
      goto LABEL_3;
    }
  }
  else if ( !FileSize )
  {
    v19 = -2146885629;
    goto LABEL_14;
  }
  v17 = (void *)PkiNonzeroAlloc(v11);
  v8 = v17;
  if ( !v17 )
    goto LABEL_2;
  if ( !ReadFile((HANDLE)v6, v17, v11, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    goto LABEL_13;
  }
LABEL_3:
  PkiDefaultCryptFree(v10);
  if ( v6 != -1 )
    ILS_CloseHandle((HANDLE)v6);
  *a5 = (unsigned __int8 *)v8;
  result = v9;
  *a6 = v11;
  return result;
}

```

## disassembly

```asm
0x18005a9f4  mov     r11, rsp
0x18005a9f7  mov     [r11+20h], rbx
0x18005a9fb  push    rbp
0x18005a9fc  push    rsi
0x18005a9fd  push    rdi
0x18005a9fe  push    r12
0x18005aa00  push    r13
0x18005aa02  push    r14
0x18005aa04  push    r15
0x18005aa06  sub     rsp, 80h
0x18005aa0d  mov     rax, cs:__security_cookie
0x18005aa14  xor     rax, rsp
0x18005aa17  mov     [rsp+0B8h+var_48], rax
0x18005aa1c  mov     r12, [rsp+0B8h+arg_20]
0x18005aa24  lea     rax, [r11-60h]
0x18005aa28  mov     r13, [rsp+0B8h+arg_28]
0x18005aa30  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18005aa34  mov     [r11-60h], rcx
0x18005aa38  mov     ebx, r9d
0x18005aa3b  mov     [r11-58h], rdx
0x18005aa3f  xor     esi, esi
0x18005aa41  lea     rdx, [r11-70h]; struct _SYSTEM_NAME_GROUP *
0x18005aa45  mov     [r11-50h], r8
0x18005aa49  lea     r14d, [rbp+2]
0x18005aa4d  mov     qword ptr [r11-70h], 3
0x18005aa55  mov     ecx, r14d; unsigned int
0x18005aa58  mov     [rsp+0B8h+NumberOfBytesRead], 0
0x18005aa60  mov     [r11-68h], rax
0x18005aa64  call    ?FormatSystemNamePath@@YAPEAGKQEAU_SYSTEM_NAME_GROUP@@@Z; FormatSystemNamePath(ulong,_SYSTEM_NAME_GROUP * const)
0x18005aa69  mov     r15, rax
0x18005aa6c  test    rax, rax
0x18005aa6f  jnz     short loc_18005AAC5
0x18005aa71  mov     rcx, rsi; hMem
0x18005aa74  xor     r14d, r14d
0x18005aa77  call    PkiDefaultCryptFree
0x18005aa7c  xor     esi, esi
0x18005aa7e  xor     ebx, ebx
0x18005aa80  mov     rcx, r15; hMem
0x18005aa83  call    PkiDefaultCryptFree
0x18005aa88  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18005aa8c  jnz     loc_18005AB7C
0x18005aa92  mov     [r12], rsi
0x18005aa96  mov     eax, r14d
0x18005aa99  mov     [r13+0], ebx
0x18005aa9d  mov     rcx, [rsp+0B8h+var_48]
0x18005aaa2  xor     rcx, rsp; StackCookie
0x18005aaa5  call    __security_check_cookie
0x18005aaaa  mov     rbx, [rsp+0B8h+arg_18]
0x18005aab2  add     rsp, 80h
0x18005aab9  pop     r15
0x18005aabb  pop     r14
0x18005aabd  pop     r13
0x18005aabf  pop     r12
0x18005aac1  pop     rdi
0x18005aac2  pop     rsi
0x18005aac3  pop     rbp
0x18005aac4  retn
0x18005aac5  and     ebx, 800h
0x18005aacb  xor     edi, edi
0x18005aacd  shl     ebx, 0Eh
0x18005aad0  bts     ebx, 7
0x18005aad4  mov     [rsp+0B8h+hTemplateFile], rsi; hTemplateFile
0x18005aad9  xor     r9d, r9d; lpSecurityAttributes
0x18005aadc  mov     [rsp+0B8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18005aae0  mov     r8d, r14d; dwShareMode
0x18005aae3  mov     edx, 80000000h; dwDesiredAccess
0x18005aae8  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x18005aaf0  mov     rcx, r15; lpFileName
0x18005aaf3  call    cs:__imp_CreateFileW
0x18005aaf9  mov     rbp, rax
0x18005aafc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005ab00  jz      loc_18005AB89
0x18005ab06  xor     edx, edx; lpFileSizeHigh
0x18005ab08  mov     rcx, rax; hFile
0x18005ab0b  call    cs:__imp_GetFileSize
0x18005ab11  mov     ebx, eax
0x18005ab13  cmp     eax, 0FFFFFFFFh
0x18005ab16  jz      short loc_18005AB6C
0x18005ab18  test    eax, eax
0x18005ab1a  jz      loc_18005ABA6
0x18005ab20  mov     rcx, rbx; uBytes
0x18005ab23  call    PkiNonzeroAlloc
0x18005ab28  mov     rsi, rax
0x18005ab2b  test    rax, rax
0x18005ab2e  jz      loc_18005AA71
0x18005ab34  lea     r9, [rsp+0B8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005ab39  mov     qword ptr [rsp+0B8h+dwCreationDisposition], 0; lpOverlapped
0x18005ab42  mov     r8d, ebx; nNumberOfBytesToRead
0x18005ab45  mov     rdx, rax; lpBuffer
0x18005ab48  mov     rcx, rbp; hFile
0x18005ab4b  call    cs:__imp_ReadFile
0x18005ab51  test    eax, eax
0x18005ab53  jnz     loc_18005AA80
0x18005ab59  call    cs:__imp_GetLastError
0x18005ab5f  mov     ecx, eax; dwErrCode
0x18005ab61  call    cs:__imp_SetLastError
0x18005ab67  jmp     loc_18005AA71
0x18005ab6c  call    cs:__imp_GetLastError
0x18005ab72  test    eax, eax
0x18005ab74  jnz     loc_18005AA71
0x18005ab7a  jmp     short loc_18005AB20
0x18005ab7c  mov     rcx, rbp; hObject
0x18005ab7f  call    ?ILS_CloseHandle@@YAXPEAX@Z; ILS_CloseHandle(void *)
0x18005ab84  jmp     loc_18005AA92
0x18005ab89  call    cs:__imp_GetLastError
0x18005ab8f  cmp     eax, 20h ; ' '
0x18005ab92  jnz     loc_1801190F2
0x18005ab98  cmp     edi, 6
0x18005ab9b  jnb     loc_1801190F2
0x18005aba1  jmp     loc_180119100
0x18005aba6  mov     ecx, 80092003h
0x18005abab  jmp     short loc_18005AB61
0x1801190f2  cmp     eax, 5
0x1801190f5  jnz     short loc_180119118
0x1801190f7  cmp     edi, r14d
0x1801190fa  jnb     loc_18005AB5F
0x180119100  lea     rax, qword_18013E670
0x180119107  mov     ecx, [rax+rdi*4]; dwMilliseconds
0x18011910a  call    cs:__imp_Sleep
0x180119110  add     edi, r14d
0x180119113  jmp     loc_18005AAD4
0x180119118  cmp     eax, 3
0x18011911b  mov     ecx, 2
0x180119120  cmovz   eax, ecx
0x180119123  jmp     loc_18005AB5F
```
