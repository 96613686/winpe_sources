# GetLUAPhonebookPath

- ea: `0x18000b960`
- end: `0x18000bea5`
- name: `GetLUAPhonebookPath`
- size: `1349`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops, reparse_path`

## callers

- `0x18002092c`
- `0x1800c8358`
- `0x1800d0b08`
- `0x1800da2bc`

## callees

- `0x180009cb4`
- `0x18000a0a8`
- `0x18000b0f4`
- `0x18000b960`
- `0x18000c190`
- `0x18000ce90`
- `0x18000d83c`
- `0x180020c78`
- `0x180027724`
- `0x180063d80`
- `0x1800c06c8`
- `0x1800c11d8`
- `0x1800d0084`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be57`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bc7e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bc7e`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000bc94`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000bc94`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000be68`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000be68`
- `rtutils!TracePrintfExA` at `0x18000bb0d`
- `rtutils!TracePrintfExA` at `0x18000bba3`
- `rtutils!TracePrintfExA` at `0x18000bcf9`
- `rtutils!TracePrintfExA` at `0x18000bd61`
- `rtutils!TracePrintfExA` at `0x18000bdf9`
- `rtutils!TracePrintfExA` at `0x18000be49`
- `rtutils!TracePrintfExA` at `0x18000bb0d`
- `rtutils!TracePrintfExA` at `0x18000bba3`
- `rtutils!TracePrintfExA` at `0x18000bcf9`
- `rtutils!TracePrintfExA` at `0x18000bd61`
- `rtutils!TracePrintfExA` at `0x18000bdf9`
- `rtutils!TracePrintfExA` at `0x18000be49`

## string_xrefs

- `0x18000bb92`: `GetLUAPhonebookPath: Return value %d hiddenpbk path %S\n`
- `0x18000b9e7`: `\system32\`
- `0x18000bcdd`: ` GetLUAPhonebookPath: GetPhonebookDirectory  for PBK File %S failed. Error = %d`
- `0x18000bcea`: ` GetLUAPhonebookPath: CopyFile  for PBK File %S failed. Error = %d`
- `0x18000be3d`: ` GetLUAPhonebookPath: IsFileNotASymlink for PBK File %S failed. Error = %d`
- `0x18000bb01`: ` GetLUAPhonebookPath: GetFileNameFromPath  for PBK File %S failed. Error = %d`
- `0x18000bd93`: ` GetLUAPhonebookPath: CreateDirectoriesOnPath  for PBK File %S failed. Error = %d`

## pseudocode

```c
__int64 __fastcall GetLUAPhonebookPath(LPCWSTR lpFileName, __int64 *a2)
{
  unsigned int v4; // r15d
  __int64 v5; // r12
  HRESULT v6; // esi
  size_t v7; // r10
  size_t v8; // rdx
  __int64 v9; // rax
  wchar_t *v10; // r8
  const wchar_t *v11; // rcx
  wchar_t *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ebx
  wchar_t *v16; // rcx
  __int64 v17; // rax
  HRESULT v19; // eax
  wchar_t *v20; // r11
  size_t v21; // rdx
  size_t v22; // rdi
  wchar_t *v23; // r8
  HANDLE FileW; // rax
  void *v25; // rdi
  bool v26; // zf
  unsigned int DirectoriesOnPath; // eax
  unsigned int v28; // eax
  DWORD LastError; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  size_t pcchLength; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h]
  STRSAFE_LPWSTR ppszDestEnd[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR psz[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(psz, 0, 0x20Au);
  v33 = 0;
  if ( !a2 || !lpFileName )
  {
    v15 = 87;
    goto LABEL_26;
  }
  *a2 = 0;
  if ( !(unsigned int)GetPhonebookDirectory(1u, psz, 0x105u) )
  {
    v15 = 621;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        " GetLUAPhonebookPath: GetPhonebookDirectory  for PBK File %S failed. Error = %d",
        lpFileName,
        621);
    goto LABEL_26;
  }
  v4 = -2147024774;
  v5 = 2147483646;
  if ( wcsstr_0(lpFileName, L"\\system32\\") )
  {
    v15 = StringCchCatWrapW(psz);
    v26 = v15 == 0;
  }
  else
  {
    pcchLength = 0;
    v6 = StringLengthWorkerW(psz, 0x105u, &pcchLength);
    if ( v6 >= 0 )
    {
      v7 = pcchLength;
      v8 = 261 - pcchLength;
      if ( 261 - pcchLength <= 1 )
      {
        v6 = -2147024774;
      }
      else
      {
        v9 = 2147483646;
        v10 = &psz[pcchLength];
        v11 = L"_hiddenPbk\\";
        do
        {
          if ( !v9 )
            break;
          if ( !*v11 )
            break;
          *v10++ = *v11++;
          --v9;
          --v8;
        }
        while ( v8 );
        v12 = v10 - 1;
        v6 = v8 == 0 ? 0x8007007A : 0;
        if ( v8 )
          v12 = v10;
        *v12 = 0;
        if ( v8 )
          goto LABEL_14;
      }
      StringExHandleOtherFlagsW_0(psz, 0x20Au, v7, ppszDestEnd, &pcchLength, 0x900u);
    }
    v15 = (unsigned __int16)v6;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCat failed due to error 0x%x", v6);
    v26 = (unsigned __int16)v6 == 0;
  }
  if ( !v26 )
    goto LABEL_26;
LABEL_14:
  if ( !(unsigned int)FFolderExists(psz) )
  {
    DirectoriesOnPath = CreateDirectoriesOnPath(psz);
    v15 = DirectoriesOnPath;
    if ( DirectoriesOnPath )
    {
      if ( g_dwTraceId != -1 )
      {
        dwCreationDisposition[0] = DirectoriesOnPath;
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          " GetLUAPhonebookPath: CreateDirectoriesOnPath  for PBK File %S failed. Error = %d",
          lpFileName,
          *(_QWORD *)dwCreationDisposition);
      }
      goto LABEL_26;
    }
  }
  PbkPathInfoLoad(&g_PbkPathInfo);
  if ( !qword_1800FF988 )
  {
    v15 = 127;
LABEL_18:
    Free0(0);
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        " GetLUAPhonebookPath: GetFileNameFromPath  for PBK File %S failed. Error = %d",
        lpFileName,
        v15);
    goto LABEL_26;
  }
  v13 = qword_1800FF988(lpFileName);
  v14 = StrDup(v13);
  if ( !v14 )
  {
    v15 = 8;
    goto LABEL_18;
  }
  v33 = v14;
  pcchLength = 0;
  v19 = StringLengthWorkerW(psz, 0x105u, &pcchLength);
  if ( v19 < 0 )
  {
    v4 = v19;
LABEL_61:
    v15 = (unsigned __int16)v4;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCat failed due to error 0x%x", v4);
    goto LABEL_25;
  }
  v21 = pcchLength;
  v15 = 0;
  v22 = 261 - pcchLength;
  if ( pcchLength != 261 && pcchLength != 260 )
  {
    v23 = &psz[pcchLength];
    do
    {
      if ( !v5 )
        break;
      if ( !*v20 )
        break;
      *v23++ = *v20++;
      --v5;
      --v22;
    }
    while ( v22 );
    v4 = v22 == 0 ? 0x8007007A : 0;
    v16 = v23 - 1;
    if ( v22 )
      v16 = v23;
    *v16 = 0;
    if ( v22 )
      goto LABEL_25;
    goto LABEL_59;
  }
  if ( *v20 )
  {
LABEL_59:
    StringExHandleOtherFlagsW_0(psz, 0x20Au, v21, (STRSAFE_LPWSTR *)&pcchLength, (size_t *)ppszDestEnd, 0x900u);
    goto LABEL_61;
  }
LABEL_25:
  if ( v15 || (unsigned int)FFileExists(psz) )
    goto LABEL_26;
  FileW = CreateFileW(psz, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
  v25 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v15 = 621;
    goto LABEL_26;
  }
  if ( GetFileType(FileW) != 1 )
  {
    v15 = 621;
LABEL_44:
    CloseHandle(v25);
    goto LABEL_26;
  }
  if ( !(unsigned int)FFileExists(lpFileName) )
    goto LABEL_44;
  v28 = IsFileNotASymlink(v25, psz);
  v15 = v28;
  if ( v28 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        " GetLUAPhonebookPath: IsFileNotASymlink for PBK File %S failed. Error = %d",
        lpFileName,
        v28);
    goto LABEL_44;
  }
  CloseHandle(v25);
  if ( !CopyFileW(lpFileName, psz, 0) )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( g_dwTraceId != -1 )
    {
      dwCreationDispositiona[0] = LastError;
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        " GetLUAPhonebookPath: CopyFile  for PBK File %S failed. Error = %d",
        lpFileName,
        *(_QWORD *)dwCreationDispositiona);
    }
  }
LABEL_26:
  Free0(v33);
  if ( a2 )
  {
    if ( v15 )
    {
      *a2 = 0;
    }
    else
    {
      v17 = StrDup(psz);
      *a2 = v17;
      if ( !v17 )
        v15 = 8;
    }
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "GetLUAPhonebookPath: Return value %d hiddenpbk path %S\n", v15, psz);
  }
  return v15;
}

```

## disassembly

```asm
0x18000b960  mov     [rsp-8+arg_10], rbx
0x18000b965  push    rbp
0x18000b966  push    rsi
0x18000b967  push    rdi
0x18000b968  push    r12
0x18000b96a  push    r13
0x18000b96c  push    r14
0x18000b96e  push    r15
0x18000b970  lea     rbp, [rsp-180h]
0x18000b978  sub     rsp, 280h
0x18000b97f  mov     rax, cs:__security_cookie
0x18000b986  xor     rax, rsp
0x18000b989  mov     [rbp+1B0h+var_40], rax
0x18000b990  mov     r13, rdx
0x18000b993  mov     r14, rcx
0x18000b996  mov     ebx, 20Ah
0x18000b99b  lea     rcx, [rsp+2B0h+psz]; void *
0x18000b9a0  mov     r8d, ebx; Size
0x18000b9a3  xor     edx, edx; Val
0x18000b9a5  call    memset_0
0x18000b9aa  xor     esi, esi
0x18000b9ac  mov     [rsp+2B0h+var_268], rsi
0x18000b9b1  lea     edi, [rsi+8]
0x18000b9b4  test    r13, r13
0x18000b9b7  jz      loc_18000BB1F
0x18000b9bd  test    r14, r14
0x18000b9c0  jz      loc_18000BB1F
0x18000b9c6  mov     edi, 105h
0x18000b9cb  mov     [r13+0], rsi
0x18000b9cf  mov     r8d, edi
0x18000b9d2  lea     rdx, [rsp+2B0h+psz]
0x18000b9d7  lea     ecx, [rsi+1]
0x18000b9da  call    GetPhonebookDirectory
0x18000b9df  test    eax, eax
0x18000b9e1  jz      loc_18000BCC5
0x18000b9e7  lea     rdx, aSystem32; "\\system32\\"
0x18000b9ee  mov     rcx, r14; Str
0x18000b9f1  call    wcsstr_0
0x18000b9f6  lea     rcx, [rsp+2B0h+psz]; pszDest
0x18000b9fb  mov     r15d, 8007007Ah
0x18000ba01  mov     r12d, 7FFFFFFEh
0x18000ba07  mov     edx, edi; cchMax
0x18000ba09  test    rax, rax
0x18000ba0c  jnz     loc_18000BD04
0x18000ba12  lea     r8, [rsp+2B0h+pcchLength]; pcchLength
0x18000ba17  mov     [rsp+2B0h+pcchLength], rsi
0x18000ba1c  call    StringLengthWorkerW
0x18000ba21  xor     r11d, r11d
0x18000ba24  mov     esi, eax
0x18000ba26  test    eax, eax
0x18000ba28  js      loc_18000BD40
0x18000ba2e  mov     r10, [rsp+2B0h+pcchLength]
0x18000ba33  mov     edx, edi
0x18000ba35  sub     rdx, r10
0x18000ba38  cmp     rdx, 1
0x18000ba3c  jbe     loc_18000BD16
0x18000ba42  lea     r8, [rsp+2B0h+psz]
0x18000ba47  mov     eax, r12d
0x18000ba4a  lea     r8, [r8+r10*2]
0x18000ba4e  lea     rcx, aHiddenpbk; "_hiddenPbk\\"
0x18000ba55  test    rax, rax
0x18000ba58  jz      short loc_18000BA79
0x18000ba5a  movzx   r9d, word ptr [rcx]
0x18000ba5e  test    r9w, r9w
0x18000ba62  jz      short loc_18000BA79
0x18000ba64  mov     [r8], r9w
0x18000ba68  add     rcx, 2
0x18000ba6c  add     r8, 2
0x18000ba70  dec     rax
0x18000ba73  sub     rdx, 1
0x18000ba77  jnz     short loc_18000BA55
0x18000ba79  mov     rax, rdx
0x18000ba7c  lea     rcx, [r8-2]
0x18000ba80  neg     rax
0x18000ba83  sbb     esi, esi
0x18000ba85  not     esi
0x18000ba87  and     esi, r15d
0x18000ba8a  test    rdx, rdx
0x18000ba8d  cmovnz  rcx, r8
0x18000ba91  mov     [rcx], r11w
0x18000ba95  jz      loc_18000BD19
0x18000ba9b  xor     esi, esi
0x18000ba9d  lea     rcx, [rsp+2B0h+psz]
0x18000baa2  call    FFolderExists
0x18000baa7  test    eax, eax
0x18000baa9  jz      loc_18000BD6C
0x18000baaf  lea     rcx, g_PbkPathInfo; lpCriticalSection
0x18000bab6  call    PbkPathInfoLoad
0x18000babb  mov     rax, cs:qword_1800FF988
0x18000bac2  test    rax, rax
0x18000bac5  jz      short loc_18000BB15
0x18000bac7  mov     rcx, r14
0x18000baca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bacf  mov     rcx, rax
0x18000bad2  call    StrDup
0x18000bad7  mov     r11, rax
0x18000bada  test    rax, rax
0x18000badd  jnz     loc_18000BBD5
0x18000bae3  lea     edi, [rax+8]
0x18000bae6  mov     ebx, edi
0x18000bae8  xor     ecx, ecx
0x18000baea  call    Free0
0x18000baef  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000baf5  cmp     ecx, 0FFFFFFFFh
0x18000baf8  jz      short loc_18000BB54
0x18000bafa  mov     r9, r14
0x18000bafd  mov     [rsp+2B0h+dwCreationDisposition], ebx
0x18000bb01  lea     r8, aGetluaphoneboo_2; " GetLUAPhonebookPath: GetFileNameFromPa"...
0x18000bb08  mov     edx, 0Ch; dwFlags
0x18000bb0d  call    cs:__imp_TracePrintfExA
0x18000bb13  jmp     short loc_18000BB54
0x18000bb15  mov     ebx, 7Fh
0x18000bb1a  lea     edi, [rbx-77h]
0x18000bb1d  jmp     short loc_18000BAE8
0x18000bb1f  mov     ebx, 57h ; 'W'
0x18000bb24  jmp     short loc_18000BB54
0x18000bb26  mov     rax, rdi
0x18000bb29  neg     rax
0x18000bb2c  sbb     ecx, ecx
0x18000bb2e  not     ecx
0x18000bb30  and     r15d, ecx
0x18000bb33  lea     rcx, [r8-2]
0x18000bb37  test    rdi, rdi
0x18000bb3a  cmovnz  rcx, r8
0x18000bb3e  mov     [rcx], si
0x18000bb41  jz      loc_18000BDA9
0x18000bb47  test    ebx, ebx
0x18000bb49  jz      loc_18000BC46
0x18000bb4f  mov     edi, 8
0x18000bb54  mov     rcx, [rsp+2B0h+var_268]
0x18000bb59  call    Free0
0x18000bb5e  test    r13, r13
0x18000bb61  jz      short loc_18000BBA9
0x18000bb63  test    ebx, ebx
0x18000bb65  jnz     loc_18000BE9C
0x18000bb6b  lea     rcx, [rsp+2B0h+psz]
0x18000bb70  call    StrDup
0x18000bb75  test    rax, rax
0x18000bb78  mov     [r13+0], rax
0x18000bb7c  cmovz   ebx, edi
0x18000bb7f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000bb85  cmp     ecx, 0FFFFFFFFh
0x18000bb88  jz      short loc_18000BBA9
0x18000bb8a  lea     rax, [rsp+2B0h+psz]
0x18000bb8f  mov     r9d, ebx
0x18000bb92  lea     r8, aGetluaphoneboo_4; "GetLUAPhonebookPath: Return value %d hi"...
0x18000bb99  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax
0x18000bb9e  mov     edx, 0Ch; dwFlags
0x18000bba3  call    cs:__imp_TracePrintfExA
0x18000bba9  mov     eax, ebx
0x18000bbab  mov     rcx, [rbp+1B0h+var_40]
0x18000bbb2  xor     rcx, rsp; StackCookie
0x18000bbb5  call    __security_check_cookie
0x18000bbba  mov     rbx, [rsp+2B0h+arg_10]
0x18000bbc2  add     rsp, 280h
0x18000bbc9  pop     r15
0x18000bbcb  pop     r14
0x18000bbcd  pop     r13
0x18000bbcf  pop     r12
0x18000bbd1  pop     rdi
0x18000bbd2  pop     rsi
0x18000bbd3  pop     rbp
0x18000bbd4  retn
0x18000bbd5  mov     [rsp+2B0h+var_268], r11
0x18000bbda  lea     r8, [rsp+2B0h+pcchLength]; pcchLength
0x18000bbdf  mov     [rsp+2B0h+pcchLength], rsi
0x18000bbe4  mov     rdx, rdi; cchMax
0x18000bbe7  lea     rcx, [rsp+2B0h+psz]; psz
0x18000bbec  call    StringLengthWorkerW
0x18000bbf1  test    eax, eax
0x18000bbf3  js      loc_18000BDD4
0x18000bbf9  mov     rdx, [rsp+2B0h+pcchLength]
0x18000bbfe  mov     ebx, esi
0x18000bc00  sub     rdi, rdx
0x18000bc03  cmp     rdi, 1
0x18000bc07  jbe     loc_18000BD9F
0x18000bc0d  lea     r8, [rsp+2B0h+psz]
0x18000bc12  lea     r8, [r8+rdx*2]
0x18000bc16  test    r12, r12
0x18000bc19  jz      loc_18000BB26
0x18000bc1f  movzx   eax, word ptr [r11]
0x18000bc23  test    ax, ax
0x18000bc26  jz      loc_18000BB26
0x18000bc2c  mov     [r8], ax
0x18000bc30  add     r11, 2
0x18000bc34  add     r8, 2
0x18000bc38  dec     r12
0x18000bc3b  sub     rdi, 1
0x18000bc3f  jnz     short loc_18000BC16
0x18000bc41  jmp     loc_18000BB26
0x18000bc46  lea     rcx, [rsp+2B0h+psz]; lpFileName
0x18000bc4b  call    FFileExists
0x18000bc50  test    eax, eax
0x18000bc52  jnz     loc_18000BB4F
0x18000bc58  mov     [rsp+2B0h+hTemplateFile], rsi; hTemplateFile
0x18000bc5d  lea     r8d, [rax+1]; dwShareMode
0x18000bc61  mov     [rsp+2B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000bc69  lea     rcx, [rsp+2B0h+psz]; lpFileName
0x18000bc6e  xor     r9d, r9d; lpSecurityAttributes
0x18000bc71  mov     [rsp+2B0h+dwCreationDisposition], 2; dwCreationDisposition
0x18000bc79  mov     edx, 0C0000000h; dwDesiredAccess
0x18000bc7e  call    cs:__imp_CreateFileW
0x18000bc84  mov     rdi, rax
0x18000bc87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bc8b  jz      loc_18000BE92
0x18000bc91  mov     rcx, rax; hFile
0x18000bc94  call    cs:__imp_GetFileType
0x18000bc9a  cmp     eax, 1
0x18000bc9d  jz      loc_18000BE04
0x18000bca3  mov     ebx, 26Dh
0x18000bca8  mov     rcx, rdi; hObject
0x18000bcab  call    cs:__imp_CloseHandle
0x18000bcb1  jmp     loc_18000BB4F
0x18000bcb6  xor     esi, esi
0x18000bcb8  test    ebx, ebx
0x18000bcba  jnz     loc_18000BB4F
0x18000bcc0  jmp     loc_18000BA9D
0x18000bcc5  mov     ecx, cs:g_dwTraceId
0x18000bccb  mov     ebx, 26Dh
0x18000bcd0  cmp     ecx, 0FFFFFFFFh
0x18000bcd3  jz      loc_18000BB4F
0x18000bcd9  mov     [rsp+2B0h+dwCreationDisposition], ebx
0x18000bcdd  lea     r8, aGetluaphoneboo_3; " GetLUAPhonebookPath: GetPhonebookDirec"...
0x18000bce4  jmp     short loc_18000BCF1
0x18000bce6  mov     [rsp+2B0h+dwCreationDisposition], eax
0x18000bcea  lea     r8, aGetluaphoneboo_1; " GetLUAPhonebookPath: CopyFile  for PBK"...
0x18000bcf1  mov     r9, r14
0x18000bcf4  mov     edx, 0Ch; dwFlags
0x18000bcf9  call    cs:__imp_TracePrintfExA
0x18000bcff  jmp     loc_18000BB4F
0x18000bd04  lea     r8, aHiddenpbkSyste; "_hiddenPBK\\System\\"
0x18000bd0b  call    StringCchCatWrapW
0x18000bd10  mov     ebx, eax
0x18000bd12  test    eax, eax
0x18000bd14  jmp     short loc_18000BCBA
0x18000bd16  mov     esi, r15d
0x18000bd19  lea     rax, [rsp+2B0h+pcchLength]
0x18000bd1e  mov     [rsp+2B0h+dwFlagsAndAttributes], 900h; dwFlags
0x18000bd26  lea     r9, [rsp+2B0h+ppszDestEnd]; ppszDestEnd
0x18000bd2b  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; pcchRemaining
0x18000bd30  mov     r8, r10; cchOriginalDestLength
0x18000bd33  lea     rcx, [rsp+2B0h+psz]; pszDest
0x18000bd38  mov     rdx, rbx; cbDest
0x18000bd3b  call    StringExHandleOtherFlagsW_0
0x18000bd40  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000bd46  movzx   ebx, si
0x18000bd49  cmp     ecx, 0FFFFFFFFh
0x18000bd4c  jz      loc_18000BCB6
0x18000bd52  mov     r9d, esi
0x18000bd55  lea     r8, aStringcchcatFa; "StringCchCat failed due to error 0x%x"
0x18000bd5c  mov     edx, 0Ch; dwFlags
0x18000bd61  call    cs:__imp_TracePrintfExA
0x18000bd67  jmp     loc_18000BCB6
0x18000bd6c  lea     rcx, [rsp+2B0h+psz]; lpPathName
0x18000bd71  call    CreateDirectoriesOnPath
0x18000bd76  mov     ebx, eax
0x18000bd78  test    eax, eax
0x18000bd7a  jz      loc_18000BAAF
0x18000bd80  mov     ecx, cs:g_dwTraceId
0x18000bd86  cmp     ecx, 0FFFFFFFFh
0x18000bd89  jz      loc_18000BB4F
0x18000bd8f  mov     [rsp+2B0h+dwCreationDisposition], eax
0x18000bd93  lea     r8, aGetluaphoneboo_0; " GetLUAPhonebookPath: CreateDirectories"...
0x18000bd9a  jmp     loc_18000BCF1
0x18000bd9f  cmp     [r11], si
0x18000bda3  jz      loc_18000BB47
0x18000bda9  lea     rax, [rsp+2B0h+ppszDestEnd]
0x18000bdae  mov     [rsp+2B0h+dwFlagsAndAttributes], 900h; dwFlags
0x18000bdb6  mov     r8, rdx; cchOriginalDestLength
0x18000bdb9  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax; pcchRemaining
0x18000bdbe  mov     edx, 20Ah; cbDest
0x18000bdc3  lea     r9, [rsp+2B0h+pcchLength]; ppszDestEnd
0x18000bdc8  lea     rcx, [rsp+2B0h+psz]; pszDest
0x18000bdcd  call    StringExHandleOtherFlagsW_0
0x18000bdd2  jmp     short loc_18000BDD7
0x18000bdd4  mov     r15d, eax
0x18000bdd7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000bddd  movzx   ebx, r15w
0x18000bde1  cmp     ecx, 0FFFFFFFFh
0x18000bde4  jz      loc_18000BB47
0x18000bdea  mov     r9d, r15d
0x18000bded  lea     r8, aStringcchcatFa; "StringCchCat failed due to error 0x%x"
0x18000bdf4  mov     edx, 0Ch; dwFlags
0x18000bdf9  call    cs:__imp_TracePrintfExA
0x18000bdff  jmp     loc_18000BB47
0x18000be04  mov     rcx, r14; lpFileName
0x18000be07  call    FFileExists
0x18000be0c  test    eax, eax
0x18000be0e  jz      loc_18000BCA8
0x18000be14  lea     rdx, [rsp+2B0h+psz]; String1
0x18000be19  mov     rcx, rdi; hFile
0x18000be1c  call    IsFileNotASymlink
0x18000be21  mov     ebx, eax
0x18000be23  test    eax, eax
0x18000be25  jz      short loc_18000BE54
0x18000be27  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000be2d  cmp     ecx, 0FFFFFFFFh
0x18000be30  jz      loc_18000BCA8
0x18000be36  mov     r9, r14
0x18000be39  mov     [rsp+2B0h+dwCreationDisposition], eax
  ... truncated ...
```
