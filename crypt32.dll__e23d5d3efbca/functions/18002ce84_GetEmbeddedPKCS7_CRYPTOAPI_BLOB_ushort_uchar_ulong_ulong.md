# GetEmbeddedPKCS7(_CRYPTOAPI_BLOB *,ushort *,uchar * *,ulong *,ulong *)

- ea: `0x18002ce84`
- end: `0x18002d14e`
- name: `?GetEmbeddedPKCS7@@YAHPEAU_CRYPTOAPI_BLOB@@PEAGPEAPEAEPEAK3@Z`
- size: `714`
- prototype: `int(struct _CRYPTOAPI_BLOB *, unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18002db94`

## callees

- `0x180024490`
- `0x1800257d0`
- `0x180028d60`
- `0x18002ce84`
- `0x18004d730`
- `0x1800a4914`
- `0x1800bec20`
- `0x1800bf63c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d008`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d02d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d05e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d128`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d02d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d05e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d128`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d0af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d0af`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d0d6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d0d6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d025`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d025`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002d07d`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002d07d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d118`

## pseudocode

```c
__int64 __fastcall GetEmbeddedPKCS7(
        struct _CRYPTOAPI_BLOB *a1,
        unsigned __int16 *a2,
        HLOCAL *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v5; // rdi
  WCHAR *v9; // rbx
  __int64 v11; // rcx
  unsigned int v12; // r14d
  unsigned __int8 *v13; // rax
  DWORD LastError; // esi
  void *v15; // rdi
  DWORD v17; // ecx
  HANDLE FileW; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v20; // [rsp+48h] [rbp-B8h]
  SIP_DISPATCH_INFO pSipDispatch; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+90h] [rbp-70h] BYREF
  GUID *p_pgSubject; // [rsp+98h] [rbp-68h]
  __int64 v24; // [rsp+A0h] [rbp-60h]
  WCHAR *v25; // [rsp+A8h] [rbp-58h]
  unsigned int v26; // [rsp+E4h] [rbp-1Ch]
  GUID pgSubject; // [rsp+110h] [rbp+10h] BYREF
  WCHAR TempFileName[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR PathName[264]; // [rsp+330h] [rbp+230h] BYREF

  v5 = a5;
  v20 = a5;
  v9 = 0;
  NumberOfBytesWritten = 0;
  pgSubject = 0;
  memset_0(&v22, 0, 0x80u);
  *a3 = 0;
  v12 = 1;
  *a4 = 0;
  *a5 = 0;
  if ( a2 )
  {
    v9 = a2;
LABEL_3:
    if ( CryptSIPRetrieveSubjectGuid(v9, 0, &pgSubject) )
    {
      memset(&pSipDispatch, 0, sizeof(pSipDispatch));
      pSipDispatch.cbSize = 56;
      if ( CryptSIPLoad(&pgSubject, 0, &pSipDispatch) )
      {
        memset_0(&v22, 0, 0x80u);
        v22 = 128;
        p_pgSubject = &pgSubject;
        v26 = *v5;
        v24 = -1;
        v25 = v9;
        ((void (__fastcall *)(int *, unsigned int *, _QWORD, unsigned int *, _QWORD))pSipDispatch.pfGet)(
          &v22,
          v5,
          0,
          a4,
          0);
        if ( *a4 )
        {
          v13 = (unsigned __int8 *)PkiAlloc(*a4);
          *a3 = v13;
          if ( !v13 )
          {
            v17 = -2147024882;
            goto LABEL_18;
          }
          if ( ((unsigned int (__fastcall *)(int *, unsigned int *, _QWORD, unsigned int *, unsigned __int8 *))pSipDispatch.pfGet)(
                 &v22,
                 v5,
                 0,
                 a4,
                 v13) )
          {
            LastError = GetLastError();
            goto LABEL_14;
          }
        }
      }
    }
    v17 = -2146885623;
LABEL_18:
    SetLastError(v17);
    goto LABEL_19;
  }
  v15 = 0;
  if ( !(unsigned int)MyGetTempPathC(v11, PathName) )
    goto LABEL_10;
  if ( !GetTempFileNameW(PathName, L"Tmp", 0, TempFileName) )
    goto LABEL_10;
  FileW = CreateFileW(TempFileName, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
  v15 = FileW;
  if ( FileW == (HANDLE)-1LL || !WriteFile(FileW, a1->pbData, a1->cbData, &NumberOfBytesWritten, 0) )
    goto LABEL_10;
  if ( NumberOfBytesWritten != a1->cbData )
  {
    SetLastError(0x80004005);
    goto LABEL_10;
  }
  if ( CloseHandle(v15) )
  {
    v9 = TempFileName;
    v5 = v20;
    goto LABEL_3;
  }
LABEL_19:
  v15 = 0;
LABEL_10:
  if ( *a3 )
  {
    PkiDefaultCryptFree(*a3);
    *a3 = 0;
  }
  LastError = GetLastError();
  if ( v15 != (void *)-1LL && v15 )
    CloseHandle(v15);
  v12 = 0;
LABEL_14:
  if ( !a2 )
    DeleteFileW(v9);
  SetLastError(LastError);
  return v12;
}

```

## disassembly

```asm
0x18002ce84  push    rbp
0x18002ce86  push    rbx
0x18002ce87  push    rsi
0x18002ce88  push    rdi
0x18002ce89  push    r12
0x18002ce8b  push    r13
0x18002ce8d  push    r14
0x18002ce8f  push    r15
0x18002ce91  lea     rbp, [rsp-458h]
0x18002ce99  sub     rsp, 558h
0x18002cea0  mov     rax, cs:__security_cookie
0x18002cea7  xor     rax, rsp
0x18002ceaa  mov     [rbp+490h+var_50], rax
0x18002ceb1  mov     rdi, [rbp+490h+arg_20]
0x18002ceb8  mov     rsi, r8
0x18002cebb  mov     r12, rdx
0x18002cebe  mov     [rsp+590h+var_548], rdi
0x18002cec3  mov     r15, rcx
0x18002cec6  xorps   xmm0, xmm0
0x18002cec9  xor     ebx, ebx
0x18002cecb  lea     rcx, [rbp+490h+var_500]; void *
0x18002cecf  xor     edx, edx; Val
0x18002ced1  mov     [rsp+590h+NumberOfBytesWritten], ebx
0x18002ced5  mov     r8d, 80h; Size
0x18002cedb  mov     r13, r9
0x18002cede  movups  xmmword ptr [rbp+490h+pgSubject.Data1], xmm0
0x18002cee2  call    memset_0
0x18002cee7  mov     [rsi], rbx
0x18002ceea  lea     r14d, [rbx+1]
0x18002ceee  mov     [r13+0], ebx
0x18002cef2  mov     [rdi], ebx
0x18002cef4  test    r12, r12
0x18002cef7  jz      loc_18002CFE9
0x18002cefd  mov     rbx, r12
0x18002cf00  lea     r8, [rbp+490h+pgSubject]; pgSubject
0x18002cf04  xor     edx, edx; hFileIn
0x18002cf06  mov     rcx, rbx; FileName
0x18002cf09  call    CryptSIPRetrieveSubjectGuid
0x18002cf0e  test    eax, eax
0x18002cf10  jz      loc_18002D059
0x18002cf16  xorps   xmm0, xmm0
0x18002cf19  lea     r8, [rsp+590h+pSipDispatch]; pSipDispatch
0x18002cf1e  xor     eax, eax
0x18002cf20  lea     rcx, [rbp+490h+pgSubject]; pgSubject
0x18002cf24  movups  xmmword ptr [rsp+590h+pSipDispatch.cbSize], xmm0
0x18002cf29  xor     edx, edx; dwFlags
0x18002cf2b  mov     [rsp+590h+pSipDispatch.cbSize], 38h ; '8'
0x18002cf33  movups  xmmword ptr [rsp+590h+pSipDispatch.pfGet], xmm0
0x18002cf38  mov     [rbp+490h+pSipDispatch.pfRemove], rax
0x18002cf3c  movups  xmmword ptr [rsp+590h+pSipDispatch.pfCreate], xmm0
0x18002cf41  call    CryptSIPLoad
0x18002cf46  test    eax, eax
0x18002cf48  jz      loc_18002D059
0x18002cf4e  mov     r15d, 80h
0x18002cf54  lea     rcx, [rbp+490h+var_500]; void *
0x18002cf58  mov     r8d, r15d; Size
0x18002cf5b  xor     edx, edx; Val
0x18002cf5d  call    memset_0
0x18002cf62  lea     rax, [rbp+490h+pgSubject]
0x18002cf66  mov     [rbp+490h+var_500], r15d
0x18002cf6a  mov     [rbp+490h+var_4F8], rax
0x18002cf6e  lea     rcx, [rbp+490h+var_500]
0x18002cf72  mov     eax, [rdi]
0x18002cf74  mov     r9, r13
0x18002cf77  mov     [rbp+490h+var_4AC], eax
0x18002cf7a  xor     r8d, r8d
0x18002cf7d  mov     rax, [rsp+590h+pSipDispatch.pfGet]
0x18002cf82  mov     rdx, rdi
0x18002cf85  mov     [rbp+490h+var_4F0], 0FFFFFFFFFFFFFFFFh
0x18002cf8d  mov     [rbp+490h+var_4E8], rbx
0x18002cf91  mov     qword ptr [rsp+590h+dwCreationDisposition], 0
0x18002cf9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf9f  cmp     dword ptr [r13+0], 0
0x18002cfa4  jz      loc_18002D059
0x18002cfaa  mov     ecx, [r13+0]; uBytes
0x18002cfae  call    PkiAlloc
0x18002cfb3  mov     [rsi], rax
0x18002cfb6  test    rax, rax
0x18002cfb9  jz      loc_18002D133
0x18002cfbf  mov     qword ptr [rsp+590h+dwCreationDisposition], rax
0x18002cfc4  lea     rcx, [rbp+490h+var_500]
0x18002cfc8  mov     rax, [rsp+590h+pSipDispatch.pfGet]
0x18002cfcd  mov     r9, r13
0x18002cfd0  xor     r8d, r8d
0x18002cfd3  mov     rdx, rdi
0x18002cfd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfdb  test    eax, eax
0x18002cfdd  jz      short loc_18002D059
0x18002cfdf  call    cs:__imp_GetLastError
0x18002cfe5  mov     esi, eax
0x18002cfe7  jmp     short loc_18002D01D
0x18002cfe9  lea     rdx, [rbp+490h+PathName]
0x18002cff0  mov     rdi, rbx
0x18002cff3  call    MyGetTempPathC
0x18002cff8  test    eax, eax
0x18002cffa  jnz     short loc_18002D068
0x18002cffc  mov     rcx, [rsi]; hMem
0x18002cfff  test    rcx, rcx
0x18002d002  jnz     loc_18002D13D
0x18002d008  call    cs:__imp_GetLastError
0x18002d00e  mov     esi, eax
0x18002d010  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002d014  jnz     loc_18002D10C
0x18002d01a  xor     r14d, r14d
0x18002d01d  test    r12, r12
0x18002d020  jnz     short loc_18002D02B
0x18002d022  mov     rcx, rbx; lpFileName
0x18002d025  call    cs:__imp_DeleteFileW
0x18002d02b  mov     ecx, esi; dwErrCode
0x18002d02d  call    cs:__imp_SetLastError
0x18002d033  mov     eax, r14d
0x18002d036  mov     rcx, [rbp+490h+var_50]
0x18002d03d  xor     rcx, rsp; StackCookie
0x18002d040  call    __security_check_cookie
0x18002d045  add     rsp, 558h
0x18002d04c  pop     r15
0x18002d04e  pop     r14
0x18002d050  pop     r13
0x18002d052  pop     r12
0x18002d054  pop     rdi
0x18002d055  pop     rsi
0x18002d056  pop     rbx
0x18002d057  pop     rbp
0x18002d058  retn
0x18002d059  mov     ecx, 80092009h; dwErrCode
0x18002d05e  call    cs:__imp_SetLastError
0x18002d064  xor     edi, edi
0x18002d066  jmp     short loc_18002CFFC
0x18002d068  lea     r9, [rbp+490h+TempFileName]; lpTempFileName
0x18002d06c  xor     r8d, r8d; uUnique
0x18002d06f  lea     rdx, PrefixString; "Tmp"
0x18002d076  lea     rcx, [rbp+490h+PathName]; lpPathName
0x18002d07d  call    cs:__imp_GetTempFileNameW
0x18002d083  test    eax, eax
0x18002d085  jz      loc_18002CFFC
0x18002d08b  mov     [rsp+590h+hTemplateFile], rbx; hTemplateFile
0x18002d090  lea     rcx, [rbp+490h+TempFileName]; lpFileName
0x18002d094  mov     [rsp+590h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002d09c  xor     r9d, r9d; lpSecurityAttributes
0x18002d09f  mov     r8d, r14d; dwShareMode
0x18002d0a2  mov     [rsp+590h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d0aa  mov     edx, 0C0000000h; dwDesiredAccess
0x18002d0af  call    cs:__imp_CreateFileW
0x18002d0b5  mov     rdi, rax
0x18002d0b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d0bc  jz      loc_18002CFFC
0x18002d0c2  mov     r8d, [r15]; nNumberOfBytesToWrite
0x18002d0c5  lea     r9, [rsp+590h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d0ca  mov     rdx, [r15+8]; lpBuffer
0x18002d0ce  mov     rcx, rax; hFile
0x18002d0d1  mov     qword ptr [rsp+590h+dwCreationDisposition], rbx; lpOverlapped
0x18002d0d6  call    cs:__imp_WriteFile
0x18002d0dc  test    eax, eax
0x18002d0de  jz      loc_18002CFFC
0x18002d0e4  mov     eax, [r15]
0x18002d0e7  cmp     [rsp+590h+NumberOfBytesWritten], eax
0x18002d0eb  jnz     short loc_18002D123
0x18002d0ed  mov     rcx, rdi; hObject
0x18002d0f0  call    cs:__imp_CloseHandle
0x18002d0f6  test    eax, eax
0x18002d0f8  jz      loc_18002D064
0x18002d0fe  lea     rbx, [rbp+490h+TempFileName]
0x18002d102  mov     rdi, [rsp+590h+var_548]
0x18002d107  jmp     loc_18002CF00
0x18002d10c  test    rdi, rdi
0x18002d10f  jz      loc_18002D01A
0x18002d115  mov     rcx, rdi; hObject
0x18002d118  call    cs:__imp_CloseHandle
0x18002d11e  jmp     loc_18002D01A
0x18002d123  mov     ecx, 80004005h; dwErrCode
0x18002d128  call    cs:__imp_SetLastError
0x18002d12e  jmp     loc_18002CFFC
0x18002d133  mov     ecx, 8007000Eh
0x18002d138  jmp     loc_18002D05E
0x18002d13d  call    PkiDefaultCryptFree
0x18002d142  mov     qword ptr [rsi], 0
0x18002d149  jmp     loc_18002D008
```
