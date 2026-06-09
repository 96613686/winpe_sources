# FixCorruptFileEx

- ea: `0x1800ddb70`
- end: `0x1800dde9a`
- name: `FixCorruptFileEx`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000e820`

## callees

- `0x18002c3a4`
- `0x180063d74`
- `0x180063d8c`
- `0x18007e3a8`
- `0x1800ddb70`
- `0x1800ddea0`
- `0x1800de078`
- `0x1800de184`
- `0x1800decee`
- `0x1800ded50`

## import_xrefs

- `msvcrt!calloc` at `0x1800ddde3`
- `msvcrt!calloc` at `0x1800ddde3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ddc05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ddc05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ddcf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ddcf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dde5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dde5b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800dde73`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800dde73`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ddc29`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ddc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dde2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dde2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddbd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddbde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dddc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dde43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dde52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddbd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddbde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dddc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dde43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dde52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ddd46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ddd6d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ddd46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ddd6d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800dddc0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800dde22`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800dddc0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800dde22`
- `RPCRT4!RpcRevertToSelf` at `0x1800dde66`
- `RPCRT4!RpcRevertToSelf` at `0x1800dde66`
- `RPCRT4!RpcImpersonateClient` at `0x1800ddbe6`
- `RPCRT4!RpcImpersonateClient` at `0x1800ddbe6`

## pseudocode

```c
void __fastcall FixCorruptFileEx(__int64 a1)
{
  wchar_t *v1; // rbx
  int v2; // r13d
  __int64 RpcImpersonatedThreadToken; // rax
  void *v4; // rdi
  BOOL v5; // r14d
  LPVOID Value; // rax
  void *v7; // rdi
  int v8; // edi
  size_t v9; // rax
  const wchar_t *v10; // rcx
  unsigned int v11; // r15d
  unsigned int v12; // edi
  wchar_t *v13; // rsi
  HANDLE FileW; // rbp
  __int64 v15; // rdi
  char *v16; // rax
  void *v17; // rbx
  size_t v18; // r8
  char FileInformation[8]; // [rsp+40h] [rbp-88h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp-80h] BYREF
  wchar_t String2[8]; // [rsp+50h] [rbp-78h] BYREF
  __int64 v22; // [rsp+60h] [rbp-68h] BYREF
  wchar_t v23; // [rsp+68h] [rbp-60h]

  if ( a1 )
  {
    v1 = (wchar_t *)(a1 + 52);
    pcchLength = 0;
    if ( a1 != -52 )
    {
      v2 = 0;
      RpcImpersonatedThreadToken = GetRpcImpersonatedThreadToken();
      v4 = (void *)RpcImpersonatedThreadToken;
      if ( RpcImpersonatedThreadToken != -1 )
      {
        if ( !(unsigned int)IsPhoneBookPathValidEx(RpcImpersonatedThreadToken, v1) )
        {
          CloseHandle(v4);
          return;
        }
        CloseHandle(v4);
        v5 = RpcImpersonateClient(0) == 0;
LABEL_12:
        if ( StringCchLengthW(v1, 0x104u, &pcchLength) < 0 )
          goto LABEL_36;
        v8 = pcchLength;
        if ( !pcchLength )
          goto LABEL_36;
        v23 = aBad[4];
        v22 = *(_QWORD *)L".bad";
        v9 = pcchLength;
        wcscpy(String2, L".pbk");
        while ( 1 )
        {
          v10 = &v1[v9 - 1];
          if ( *v10 == 46 )
            break;
          if ( *v10 != 92 && *v10 != 47 )
          {
            if ( --v9 )
              continue;
          }
          goto LABEL_36;
        }
        if ( wcsicmp_0(v10, String2) )
          goto LABEL_36;
        v12 = v8 + 5;
        v11 = v12;
        pcchLength = 2LL * v12;
        v13 = (wchar_t *)LocalAlloc(0x40u, pcchLength);
        if ( !v13 )
          goto LABEL_36;
        StringCchPrintfW(v13, v12, L"%s%s", v1, &v22);
        FileW = CreateFileW(v1, 0x10000u, 3u, 0, 3u, 0, 0);
        v15 = (__int64)CreateFileW(v13, 0x10000u, 3u, 0, 3u, 0, 0);
        if ( FileW != (HANDLE)-1LL && !(unsigned int)IsFileNotSymlink(FileW, v1) )
        {
          if ( v15 != -1 )
          {
            if ( (unsigned int)IsFileNotSymlink((HANDLE)v15, v13) )
            {
LABEL_32:
              CloseHandle((HANDLE)v15);
LABEL_33:
              if ( FileW == (HANDLE)-1LL )
              {
LABEL_35:
                LocalFree(v13);
LABEL_36:
                if ( v5 )
                {
                  RpcRevertToSelf();
                }
                else if ( v2 )
                {
                  RevertToSelf();
                }
                return;
              }
LABEL_34:
              CloseHandle(FileW);
              goto LABEL_35;
            }
            FileInformation[0] = 1;
            SetFileInformationByHandle((HANDLE)v15, FileDispositionInfo, FileInformation, 1u);
            CloseHandle((HANDLE)v15);
            v15 = -1;
          }
          v16 = (char *)calloc(1u, 2 * v11 + 22);
          v17 = v16;
          if ( !v16 )
            goto LABEL_34;
          v18 = pcchLength;
          *((_DWORD *)v16 + 4) = 2 * v11;
          *v16 = 0;
          *((_QWORD *)v16 + 1) = 0;
          memcpy_0(v16 + 20, v13, v18);
          if ( !SetFileInformationByHandle(FileW, FileRenameInfo, v17, 2 * v11 + 22) )
            GetLastError();
          free_0(v17);
        }
        if ( v15 == -1 )
          goto LABEL_33;
        goto LABEL_32;
      }
      v5 = 0;
      if ( dwTlsIndex == -1 )
        goto LABEL_12;
      Value = TlsGetValue(dwTlsIndex);
      v7 = Value;
      if ( !Value )
        goto LABEL_12;
      if ( (unsigned int)IsPhoneBookPathValidEx(Value, v1) && ImpersonateLoggedOnUser(v7) )
      {
        v2 = 1;
        goto LABEL_12;
      }
    }
  }
}

```

## disassembly

```asm
0x1800ddb70  test    rcx, rcx
0x1800ddb73  jz      locret_1800DDE99
0x1800ddb79  push    rbx
0x1800ddb7a  push    rbp
0x1800ddb7b  push    rsi
0x1800ddb7c  push    rdi
0x1800ddb7d  push    r12
0x1800ddb7f  push    r13
0x1800ddb81  push    r14
0x1800ddb83  push    r15
0x1800ddb85  sub     rsp, 88h
0x1800ddb8c  mov     rax, cs:__security_cookie
0x1800ddb93  xor     rax, rsp
0x1800ddb96  mov     [rsp+0C8h+var_58], rax
0x1800ddb9b  xor     r12d, r12d
0x1800ddb9e  lea     rbx, [rcx+34h]
0x1800ddba2  mov     [rsp+0C8h+pcchLength], r12
0x1800ddba7  test    rbx, rbx
0x1800ddbaa  jz      loc_1800DDE79
0x1800ddbb0  mov     r13d, r12d
0x1800ddbb3  call    GetRpcImpersonatedThreadToken
0x1800ddbb8  mov     rdi, rax
0x1800ddbbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ddbbf  jz      short loc_1800DDBF7
0x1800ddbc1  mov     rdx, rbx
0x1800ddbc4  mov     rcx, rax
0x1800ddbc7  call    IsPhoneBookPathValidEx
0x1800ddbcc  mov     rcx, rdi; hObject
0x1800ddbcf  test    eax, eax
0x1800ddbd1  jnz     short loc_1800DDBDE
0x1800ddbd3  call    cs:__imp_CloseHandle
0x1800ddbd9  jmp     loc_1800DDE79
0x1800ddbde  call    cs:__imp_CloseHandle
0x1800ddbe4  xor     ecx, ecx; BindingHandle
0x1800ddbe6  call    cs:__imp_RpcImpersonateClient
0x1800ddbec  test    eax, eax
0x1800ddbee  mov     r14d, r12d
0x1800ddbf1  setz    r14b
0x1800ddbf5  jmp     short loc_1800DDC3D
0x1800ddbf7  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800ddbfd  mov     r14d, r12d
0x1800ddc00  cmp     ecx, 0FFFFFFFFh
0x1800ddc03  jz      short loc_1800DDC3D
0x1800ddc05  call    cs:__imp_TlsGetValue
0x1800ddc0b  mov     rdi, rax
0x1800ddc0e  test    rax, rax
0x1800ddc11  jz      short loc_1800DDC3D
0x1800ddc13  mov     rdx, rbx
0x1800ddc16  mov     rcx, rax
0x1800ddc19  call    IsPhoneBookPathValidEx
0x1800ddc1e  test    eax, eax
0x1800ddc20  jz      loc_1800DDE79
0x1800ddc26  mov     rcx, rdi; hToken
0x1800ddc29  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ddc2f  test    eax, eax
0x1800ddc31  jz      loc_1800DDE79
0x1800ddc37  mov     r13d, 1
0x1800ddc3d  lea     r8, [rsp+0C8h+pcchLength]; pcchLength
0x1800ddc42  mov     edx, 104h; cchMax
0x1800ddc47  mov     rcx, rbx; psz
0x1800ddc4a  call    StringCchLengthW
0x1800ddc4f  test    eax, eax
0x1800ddc51  js      loc_1800DDE61
0x1800ddc57  mov     rdi, [rsp+0C8h+pcchLength]
0x1800ddc5c  test    rdi, rdi
0x1800ddc5f  jz      loc_1800DDE61
0x1800ddc65  movzx   eax, word ptr cs:aBad+8; ""
0x1800ddc6c  movsd   xmm0, qword ptr cs:aBad; ".bad"
0x1800ddc74  mov     [rsp+0C8h+var_60], ax
0x1800ddc79  movzx   eax, word ptr cs:aPbk_0+8; ""
0x1800ddc80  movsd   [rsp+0C8h+var_68], xmm0
0x1800ddc86  movsd   xmm0, qword ptr cs:aPbk_0; ".pbk"
0x1800ddc8e  mov     [rsp+0C8h+var_70], ax
0x1800ddc93  mov     rax, rdi
0x1800ddc96  movsd   qword ptr [rsp+0C8h+String2], xmm0
0x1800ddc9c  lea     rcx, [rbx-2]
0x1800ddca0  lea     rcx, [rcx+rax*2]; String1
0x1800ddca4  cmp     word ptr [rcx], 2Eh ; '.'
0x1800ddca8  jz      short loc_1800DDCC9
0x1800ddcaa  cmp     word ptr [rcx], 5Ch ; '\'
0x1800ddcae  jz      loc_1800DDE61
0x1800ddcb4  cmp     word ptr [rcx], 2Fh ; '/'
0x1800ddcb8  jz      loc_1800DDE61
0x1800ddcbe  sub     rax, 1
0x1800ddcc2  jnz     short loc_1800DDC9C
0x1800ddcc4  jmp     loc_1800DDE61
0x1800ddcc9  lea     rdx, [rsp+0C8h+String2]; String2
0x1800ddcce  call    _wcsicmp_0
0x1800ddcd3  test    eax, eax
0x1800ddcd5  jnz     loc_1800DDE61
0x1800ddcdb  lea     r15d, [rdi+5]
0x1800ddcdf  mov     ecx, 40h ; '@'; uFlags
0x1800ddce4  lea     rax, [r15+r15]
0x1800ddce8  mov     edi, r15d
0x1800ddceb  mov     rdx, rax; uBytes
0x1800ddcee  mov     [rsp+0C8h+pcchLength], rax
0x1800ddcf3  call    cs:__imp_LocalAlloc
0x1800ddcf9  mov     rsi, rax
0x1800ddcfc  test    rax, rax
0x1800ddcff  jz      loc_1800DDE61
0x1800ddd05  lea     rax, [rsp+0C8h+var_68]
0x1800ddd0a  mov     r9, rbx
0x1800ddd0d  lea     r8, aSS_3; "%s%s"
0x1800ddd14  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rax
0x1800ddd19  mov     edx, edi; cchDest
0x1800ddd1b  mov     rcx, rsi; pszDest
0x1800ddd1e  call    StringCchPrintfW
0x1800ddd23  mov     eax, 3
0x1800ddd28  mov     [rsp+0C8h+hTemplateFile], r12; hTemplateFile
0x1800ddd2d  mov     edi, 10000h
0x1800ddd32  mov     [rsp+0C8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800ddd37  mov     r8d, eax; dwShareMode
0x1800ddd3a  mov     [rsp+0C8h+dwCreationDisposition], eax; dwCreationDisposition
0x1800ddd3e  xor     r9d, r9d; lpSecurityAttributes
0x1800ddd41  mov     edx, edi; dwDesiredAccess
0x1800ddd43  mov     rcx, rbx; lpFileName
0x1800ddd46  call    cs:__imp_CreateFileW
0x1800ddd4c  mov     [rsp+0C8h+hTemplateFile], r12; hTemplateFile
0x1800ddd51  xor     r9d, r9d; lpSecurityAttributes
0x1800ddd54  mov     rbp, rax
0x1800ddd57  mov     [rsp+0C8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800ddd5c  mov     eax, 3
0x1800ddd61  mov     edx, edi; dwDesiredAccess
0x1800ddd63  mov     r8d, eax; dwShareMode
0x1800ddd66  mov     [rsp+0C8h+dwCreationDisposition], eax; dwCreationDisposition
0x1800ddd6a  mov     rcx, rsi; lpFileName
0x1800ddd6d  call    cs:__imp_CreateFileW
0x1800ddd73  mov     rdi, rax
0x1800ddd76  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800ddd7a  jz      loc_1800DDE3A
0x1800ddd80  mov     rdx, rbx; String1
0x1800ddd83  mov     rcx, rbp; hFile
0x1800ddd86  call    IsFileNotSymlink
0x1800ddd8b  test    eax, eax
0x1800ddd8d  jnz     loc_1800DDE3A
0x1800ddd93  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ddd97  jz      short loc_1800DDDD3
0x1800ddd99  mov     rdx, rsi; String1
0x1800ddd9c  mov     rcx, rdi; hFile
0x1800ddd9f  call    IsFileNotSymlink
0x1800ddda4  test    eax, eax
0x1800ddda6  jnz     loc_1800DDE40
0x1800dddac  lea     r9d, [rax+1]; dwBufferSize
0x1800dddb0  mov     [rsp+0C8h+FileInformation], 1
0x1800dddb5  lea     r8, [rsp+0C8h+FileInformation]; lpFileInformation
0x1800dddba  mov     rcx, rdi; hFile
0x1800dddbd  lea     edx, [rax+4]; FileInformationClass
0x1800dddc0  call    cs:__imp_SetFileInformationByHandle
0x1800dddc6  mov     rcx, rdi; hObject
0x1800dddc9  call    cs:__imp_CloseHandle
0x1800dddcf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800dddd3  lea     r12d, ds:16h[r15*2]
0x1800ddddb  mov     ecx, 1; Count
0x1800ddde0  mov     edx, r12d; Size
0x1800ddde3  call    cs:__imp_calloc
0x1800ddde9  mov     rbx, rax
0x1800dddec  test    rax, rax
0x1800dddef  jz      short loc_1800DDE4F
0x1800dddf1  mov     r8, [rsp+0C8h+pcchLength]; Size
0x1800dddf6  lea     ecx, [r15+r15]
0x1800dddfa  mov     [rax+10h], ecx
0x1800dddfd  mov     rdx, rsi; Src
0x1800dde00  lea     rcx, [rax+14h]; void *
0x1800dde04  mov     byte ptr [rax], 0
0x1800dde07  mov     qword ptr [rax+8], 0
0x1800dde0f  call    memcpy_0
0x1800dde14  mov     r9d, r12d; dwBufferSize
0x1800dde17  mov     r8, rbx; lpFileInformation
0x1800dde1a  mov     edx, 3; FileInformationClass
0x1800dde1f  mov     rcx, rbp; hFile
0x1800dde22  call    cs:__imp_SetFileInformationByHandle
0x1800dde28  test    eax, eax
0x1800dde2a  jnz     short loc_1800DDE32
0x1800dde2c  call    cs:__imp_GetLastError
0x1800dde32  mov     rcx, rbx; Block
0x1800dde35  call    free_0
0x1800dde3a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800dde3e  jz      short loc_1800DDE49
0x1800dde40  mov     rcx, rdi; hObject
0x1800dde43  call    cs:__imp_CloseHandle
0x1800dde49  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800dde4d  jz      short loc_1800DDE58
0x1800dde4f  mov     rcx, rbp; hObject
0x1800dde52  call    cs:__imp_CloseHandle
0x1800dde58  mov     rcx, rsi; hMem
0x1800dde5b  call    cs:__imp_LocalFree
0x1800dde61  test    r14d, r14d
0x1800dde64  jz      short loc_1800DDE6E
0x1800dde66  call    cs:__imp_RpcRevertToSelf
0x1800dde6c  jmp     short loc_1800DDE79
0x1800dde6e  test    r13d, r13d
0x1800dde71  jz      short loc_1800DDE79
0x1800dde73  call    cs:__imp_RevertToSelf
0x1800dde79  mov     rcx, [rsp+0C8h+var_58]
0x1800dde7e  xor     rcx, rsp; StackCookie
0x1800dde81  call    __security_check_cookie
0x1800dde86  add     rsp, 88h
0x1800dde8d  pop     r15
0x1800dde8f  pop     r14
0x1800dde91  pop     r13
0x1800dde93  pop     r12
0x1800dde95  pop     rdi
0x1800dde96  pop     rsi
0x1800dde97  pop     rbp
0x1800dde98  pop     rbx
0x1800dde99  retn
```
