# DeleteFileInStorageArea

- ea: `0x180004850`
- end: `0x180004bfd`
- name: `DeleteFileInStorageArea`
- size: `941`
- prototype: `__int64 __fastcall(__int64, void *, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800044d0`
- `0x18005cd34`

## callees

- `0x180004850`
- `0x180004c04`
- `0x180004d18`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x180011548`
- `0x180051e8c`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bdf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800048e1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800048e1`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004b45`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180004b45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180004b7c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180004b7c`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180004ace`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180004ace`
- `bcrypt!BCryptGenRandom` at `0x180004af3`
- `bcrypt!BCryptGenRandom` at `0x180004af3`

## string_xrefs

- `0x18000494e`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x1800049f9`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180004a2a`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180004a59`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall DeleteFileInStorageArea(__int64 a1, void *a2, void *a3)
{
  void *v3; // rsi
  void *v4; // r15
  unsigned int KeyFileFullPath; // eax
  unsigned int v6; // ebx
  const WCHAR *v7; // r14
  unsigned int v8; // eax
  signed int v10; // eax
  __int64 v11; // r9
  const char *v12; // rdx
  __int64 v13; // rcx
  DWORD LastError; // eax
  unsigned int v15; // eax
  BOOL v16; // r12d
  DWORD v17; // eax
  __int64 v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // r12d
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  void *v22; // [rsp+48h] [rbp-B8h] BYREF
  void *v23; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR TempFileName[264]; // [rsp+270h] [rbp+170h] BYREF

  v3 = 0;
  v4 = 0;
  lpFileName = 0;
  v22 = 0;
  v23 = 0;
  if ( !a2 || !a3 )
  {
    v6 = -2146893785;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v6;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      (unsigned int)"status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
      228);
    goto LABEL_15;
  }
  KeyFileFullPath = GetKeyFileFullPath(a2, a3);
  v6 = KeyFileFullPath;
  if ( KeyFileFullPath )
  {
    DebugTraceError(KeyFileFullPath, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 1010);
    return v6;
  }
  v7 = lpFileName;
  v8 = ZeroizeFile(lpFileName);
  v6 = v8;
  if ( !v8 )
  {
    if ( DeleteFileW(lpFileName) )
      return v6;
    LODWORD(lpFileName) = 0;
    LastError = GetLastError();
    DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 1040);
    v15 = ChangeThreadILToMedium(&v22, &v23);
    v6 = v15;
    if ( v15 )
    {
      DebugTraceError(v15, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 1050);
      v3 = v22;
      v4 = v23;
LABEL_15:
      if ( v4 )
        CloseHandle(v4);
      if ( v3 )
        CloseHandle(v3);
      return v6;
    }
    v4 = v23;
    v16 = v23 != 0;
    if ( GetTempPathW(0x104u, Buffer) )
    {
      if ( BCryptGenRandom(0, (PUCHAR)&lpFileName, 4u, 2u) >= 0 )
      {
        if ( GetTempFileNameW(Buffer, L"csp", (UINT)lpFileName, TempFileName) )
        {
          if ( MoveFileExW(v7, TempFileName, 1u) )
            goto LABEL_14;
          v17 = GetLastError();
          v18 = 1097;
        }
        else
        {
          v17 = GetLastError();
          v18 = 1089;
        }
        v6 = v17;
        DebugTraceError(v17, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", v18);
        if ( (int)v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_14;
      }
      v6 = -2146893779;
      v12 = "status";
      v11 = 1078;
      v13 = 2148073517LL;
    }
    else
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      else
        v6 = v10;
      v11 = 1064;
      v12 = "dwReturn";
      v13 = (unsigned int)v10;
    }
    DebugTraceError(v13, v12, "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", v11);
LABEL_14:
    v3 = v22;
    if ( v16 )
    {
      v19 = RevertBackToCallerToken(v22);
      v20 = v19;
      if ( v19 )
      {
        DebugTraceError(v19, "RevertStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 1115);
        if ( !v6 )
          v6 = v20;
      }
    }
    goto LABEL_15;
  }
  DebugTraceError(v8, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 1022);
  if ( (int)v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x180004850  mov     [rsp-8+arg_0], rbx
0x180004855  mov     [rsp-8+arg_18], rsi
0x18000485a  push    rbp
0x18000485b  push    rdi
0x18000485c  push    r12
0x18000485e  push    r14
0x180004860  push    r15
0x180004862  lea     rbp, [rsp-390h]
0x18000486a  sub     rsp, 490h
0x180004871  mov     rax, cs:__security_cookie
0x180004878  xor     rax, rsp
0x18000487b  mov     [rbp+3B0h+var_30], rax
0x180004882  xor     r14d, r14d
0x180004885  xor     esi, esi
0x180004887  xor     r15d, r15d
0x18000488a  mov     [rsp+4B0h+lpFileName], r14
0x18000488f  mov     [rsp+4B0h+var_468], rsi
0x180004894  mov     rax, r8
0x180004897  mov     [rsp+4B0h+var_460], r15
0x18000489c  mov     r9, rdx
0x18000489f  test    rdx, rdx
0x1800048a2  jz      loc_18000492C
0x1800048a8  test    rax, rax
0x1800048ab  jz      short loc_18000492C
0x1800048ad  lea     r8, [rsp+4B0h+lpFileName]
0x1800048b2  mov     rdx, rax; void *
0x1800048b5  mov     rcx, r9; Src
0x1800048b8  call    GetKeyFileFullPath
0x1800048bd  mov     ebx, eax
0x1800048bf  test    eax, eax
0x1800048c1  jnz     loc_180004A24
0x1800048c7  mov     r14, [rsp+4B0h+lpFileName]
0x1800048cc  mov     rcx, r14
0x1800048cf  call    ZeroizeFile
0x1800048d4  mov     ebx, eax
0x1800048d6  test    eax, eax
0x1800048d8  jnz     loc_1800049F3
0x1800048de  mov     rcx, r14; lpFileName
0x1800048e1  call    cs:__imp_DeleteFileW
0x1800048e8  nop     dword ptr [rax+rax+00h]
0x1800048ed  test    eax, eax
0x1800048ef  jz      loc_180004A49
0x1800048f5  test    r14, r14
0x1800048f8  jnz     loc_180004BF0
0x1800048fe  mov     eax, ebx
0x180004900  mov     rcx, [rbp+3B0h+var_30]
0x180004907  xor     rcx, rsp; StackCookie
0x18000490a  call    __security_check_cookie
0x18000490f  lea     r11, [rsp+4B0h+var_20]
0x180004917  mov     rbx, [r11+30h]
0x18000491b  mov     rsi, [r11+48h]
0x18000491f  mov     rsp, r11
0x180004922  pop     r15
0x180004924  pop     r14
0x180004926  pop     r12
0x180004928  pop     rdi
0x180004929  pop     rbp
0x18000492a  retn
0x18000492c  mov     ebx, 80090027h
0x180004931  mov     rcx, cs:WPP_GLOBAL_Control
0x180004938  lea     rax, WPP_GLOBAL_Control
0x18000493f  cmp     rcx, rax
0x180004942  jz      short loc_1800048FE
0x180004944  test    byte ptr [rcx+1Ch], 1
0x180004948  jz      short loc_1800048FE
0x18000494a  mov     rcx, [rcx+10h]
0x18000494e  lea     rdi, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004955  mov     [rsp+4B0h+var_480], 3E4h
0x18000495d  lea     r9, aStatus_0; "status"
0x180004964  mov     [rsp+4B0h+var_488], rdi
0x180004969  mov     [rsp+4B0h+var_490], 80090027h
0x180004971  call    WPP_SF_sDsd
0x180004976  jmp     short loc_1800049AF
0x180004978  call    cs:__imp_GetLastError
0x18000497f  nop     dword ptr [rax+rax+00h]
0x180004984  test    eax, eax
0x180004986  jg      loc_180004B1F
0x18000498c  mov     ebx, eax
0x18000498e  mov     r9d, 428h
0x180004994  mov     rdx, rsi
0x180004997  mov     ecx, eax
0x180004999  mov     r8, rdi
0x18000499c  call    DebugTraceError
0x1800049a1  mov     rsi, [rsp+4B0h+var_468]
0x1800049a6  test    r12d, r12d
0x1800049a9  jnz     loc_180004BA7
0x1800049af  test    r15, r15
0x1800049b2  jnz     loc_180004BDC
0x1800049b8  test    rsi, rsi
0x1800049bb  jz      loc_1800048F5
0x1800049c1  mov     rcx, rsi; hObject
0x1800049c4  call    cs:__imp_CloseHandle
0x1800049cb  nop     dword ptr [rax+rax+00h]
0x1800049d0  jmp     loc_1800048F5
0x1800049d5  mov     r8, rdi
0x1800049d8  mov     rdx, rsi
0x1800049db  mov     ecx, eax
0x1800049dd  mov     ebx, eax
0x1800049df  call    DebugTraceError
0x1800049e4  test    ebx, ebx
0x1800049e6  jle     short loc_1800049A1
0x1800049e8  movzx   ebx, bx
0x1800049eb  or      ebx, 80070000h
0x1800049f1  jmp     short loc_1800049A1
0x1800049f3  mov     r9d, 3FEh
0x1800049f9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004a00  lea     rdx, aDwreturn; "dwReturn"
0x180004a07  mov     ecx, ebx
0x180004a09  call    DebugTraceError
0x180004a0e  test    ebx, ebx
0x180004a10  jle     loc_1800048F5
0x180004a16  movzx   ebx, bx
0x180004a19  or      ebx, 80070000h
0x180004a1f  jmp     loc_1800048F5
0x180004a24  mov     r9d, 3F2h
0x180004a2a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004a31  lea     rdx, aStatus_0; "status"
0x180004a38  mov     ecx, eax
0x180004a3a  call    DebugTraceError
0x180004a3f  mov     r14, [rsp+4B0h+lpFileName]
0x180004a44  jmp     loc_1800048F5
0x180004a49  mov     dword ptr [rsp+4B0h+lpFileName], esi
0x180004a4d  call    cs:__imp_GetLastError
0x180004a54  nop     dword ptr [rax+rax+00h]
0x180004a59  lea     rdi, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004a60  mov     r9d, 410h
0x180004a66  lea     rsi, aDwreturn; "dwReturn"
0x180004a6d  mov     r8, rdi
0x180004a70  mov     rdx, rsi
0x180004a73  mov     ecx, eax
0x180004a75  call    DebugTraceError
0x180004a7a  lea     rdx, [rsp+4B0h+var_460]
0x180004a7f  lea     rcx, [rsp+4B0h+var_468]
0x180004a84  call    ChangeThreadILToMedium
0x180004a89  mov     ebx, eax
0x180004a8b  test    eax, eax
0x180004a8d  jz      short loc_180004AB5
0x180004a8f  mov     r9d, 41Ah
0x180004a95  lea     rdx, aStatus_0; "status"
0x180004a9c  mov     r8, rdi
0x180004a9f  mov     ecx, eax
0x180004aa1  call    DebugTraceError
0x180004aa6  mov     rsi, [rsp+4B0h+var_468]
0x180004aab  mov     r15, [rsp+4B0h+var_460]
0x180004ab0  jmp     loc_1800049AF
0x180004ab5  mov     r15, [rsp+4B0h+var_460]
0x180004aba  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x180004abf  xor     r12d, r12d
0x180004ac2  mov     ecx, 104h; nBufferLength
0x180004ac7  test    r15, r15
0x180004aca  setnz   r12b
0x180004ace  call    cs:__imp_GetTempPathW
0x180004ad5  nop     dword ptr [rax+rax+00h]
0x180004ada  test    eax, eax
0x180004adc  jz      loc_180004978
0x180004ae2  mov     r9d, 2; dwFlags
0x180004ae8  lea     rdx, [rsp+4B0h+lpFileName]; pbBuffer
0x180004aed  xor     ecx, ecx; hAlgorithm
0x180004aef  lea     r8d, [r9+2]; cbBuffer
0x180004af3  call    cs:__imp_BCryptGenRandom
0x180004afa  nop     dword ptr [rax+rax+00h]
0x180004aff  test    eax, eax
0x180004b01  jns     short loc_180004B2D
0x180004b03  mov     ebx, 8009002Dh
0x180004b08  lea     rdx, aStatus_0; "status"
0x180004b0f  mov     r9d, 436h
0x180004b15  mov     ecx, 8009002Dh
0x180004b1a  jmp     loc_180004999
0x180004b1f  movzx   ebx, ax
0x180004b22  or      ebx, 80070000h
0x180004b28  jmp     loc_18000498E
0x180004b2d  mov     r8d, dword ptr [rsp+4B0h+lpFileName]; uUnique
0x180004b32  lea     r9, [rbp+3B0h+TempFileName]; lpTempFileName
0x180004b39  lea     rdx, PrefixString; "csp"
0x180004b40  lea     rcx, [rsp+4B0h+Buffer]; lpPathName
0x180004b45  call    cs:__imp_GetTempFileNameW
0x180004b4c  nop     dword ptr [rax+rax+00h]
0x180004b51  test    eax, eax
0x180004b53  jnz     short loc_180004B6C
0x180004b55  call    cs:__imp_GetLastError
0x180004b5c  nop     dword ptr [rax+rax+00h]
0x180004b61  mov     r9d, 441h
0x180004b67  jmp     loc_1800049D5
0x180004b6c  mov     r8d, 1; dwFlags
0x180004b72  lea     rdx, [rbp+3B0h+TempFileName]; lpNewFileName
0x180004b79  mov     rcx, r14; lpExistingFileName
0x180004b7c  call    cs:__imp_MoveFileExW
0x180004b83  nop     dword ptr [rax+rax+00h]
0x180004b88  test    eax, eax
0x180004b8a  jnz     loc_1800049A1
0x180004b90  call    cs:__imp_GetLastError
0x180004b97  nop     dword ptr [rax+rax+00h]
0x180004b9c  mov     r9d, 449h
0x180004ba2  jmp     loc_1800049D5
0x180004ba7  mov     rcx, rsi
0x180004baa  call    RevertBackToCallerToken
0x180004baf  mov     r12d, eax
0x180004bb2  test    eax, eax
0x180004bb4  jz      loc_1800049AF
0x180004bba  mov     r9d, 45Bh
0x180004bc0  lea     rdx, aRevertstatus; "RevertStatus"
0x180004bc7  mov     r8, rdi
0x180004bca  mov     ecx, eax
0x180004bcc  call    DebugTraceError
0x180004bd1  test    ebx, ebx
0x180004bd3  cmovz   ebx, r12d
0x180004bd7  jmp     loc_1800049AF
0x180004bdc  mov     rcx, r15; hObject
0x180004bdf  call    cs:__imp_CloseHandle
0x180004be6  nop     dword ptr [rax+rax+00h]
0x180004beb  jmp     loc_1800049B8
0x180004bf0  mov     rcx, r14
0x180004bf3  call    MSCryptFree
0x180004bf8  jmp     loc_1800048FE
```
