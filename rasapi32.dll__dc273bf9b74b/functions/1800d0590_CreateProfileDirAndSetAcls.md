# CreateProfileDirAndSetAcls

- ea: `0x1800d0590`
- end: `0x1800d07d9`
- name: `CreateProfileDirAndSetAcls`
- size: `585`
- prototype: `__int64 __fastcall(char *hToken, __int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d0b08`

## callees

- `0x180006afc`
- `0x1800c06c8`
- `0x1800cf300`
- `0x1800d0590`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d06b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d0782`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d06b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d0782`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d0604`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d0604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d060e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d06be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d075b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d078c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d060e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d06be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d075b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d078c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d074b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d074b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d070a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d070a`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800d071c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800d071c`
- `rtutils!TracePrintfExA` at `0x1800d066d`
- `rtutils!TracePrintfExA` at `0x1800d06a6`
- `rtutils!TracePrintfExA` at `0x1800d0742`
- `rtutils!TracePrintfExA` at `0x1800d0773`
- `rtutils!TracePrintfExA` at `0x1800d07aa`
- `rtutils!TracePrintfExA` at `0x1800d066d`
- `rtutils!TracePrintfExA` at `0x1800d06a6`
- `rtutils!TracePrintfExA` at `0x1800d0742`
- `rtutils!TracePrintfExA` at `0x1800d0773`
- `rtutils!TracePrintfExA` at `0x1800d07aa`

## string_xrefs

- `0x1800d0664`: `CreateProfileDirAndSetAcls: CreateDirectoriesOnPath: Failed %d`
- `0x1800d0627`: `CreateProfileDirAndSetAcls: ImpersonateLoggedOnUser Failed %d`
- `0x1800d0767`: `CreateProfileDirAndSetAcls: CreateFile: Failed %d`
- `0x1800d0739`: `CreateProfileDirAndSetAcls: Invalid filetype %d`
- `0x1800d06d4`: `CreateProfileDirAndSetAcls: RevertToSelf: Failed %d`
- `0x1800d069d`: `CreateProfileDirAndSetAcls: UpdateAclsOnPhonebookFolder: Failed %d. Ignoring`
- `0x1800d079e`: `CreateProfileDirAndSetAcls: RevertToSelf before returning: Failed %d`

## pseudocode

```c
__int64 __fastcall CreateProfileDirAndSetAcls(char *hToken, __int64 a2, int a3, unsigned int a4)
{
  unsigned int v7; // ebx
  int v8; // ebp
  DWORD v9; // eax
  unsigned int DirectoriesOnPath; // eax
  __int64 v11; // rdx
  unsigned int updated; // eax
  DWORD LastError; // eax
  DWORD v14; // ecx
  const CHAR *v15; // r8
  HANDLE FileW; // rax
  void *v17; // r14
  DWORD v18; // eax
  WCHAR FileName[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(FileName, 0, 0x20Au);
  v7 = StringCchCopyWrapW(FileName);
  if ( v7 )
    return v7;
  v8 = 0;
  if ( a3 == 4 || (unsigned __int64)(hToken - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_8:
    DirectoriesOnPath = CreateDirectoriesOnPath(FileName);
    v7 = DirectoriesOnPath;
    if ( DirectoriesOnPath )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "CreateProfileDirAndSetAcls: CreateDirectoriesOnPath: Failed %d",
          DirectoriesOnPath);
    }
    else
    {
      if ( !a3 )
      {
        updated = UpdateAclsOnPhonebookFolder(FileName, v11, a4);
        v7 = updated;
        if ( updated )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "CreateProfileDirAndSetAcls: UpdateAclsOnPhonebookFolder: Failed %d. Ignoring",
              updated);
          v7 = 0;
        }
      }
      if ( v8 )
      {
        v8 = 0;
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v14 = g_dwTraceId;
          v7 = LastError;
          if ( g_dwTraceId == -1 )
            return v7;
          v15 = "CreateProfileDirAndSetAcls: RevertToSelf: Failed %d";
          goto LABEL_32;
        }
      }
      FileW = CreateFileW(FileName, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
      v17 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        if ( g_dwTraceId != -1 )
        {
          v18 = GetLastError();
          TracePrintfExA(g_dwTraceId, 0xCu, "CreateProfileDirAndSetAcls: CreateFile: Failed %d", v18);
        }
        v7 = 621;
      }
      else
      {
        if ( GetFileType(FileW) != 1 )
        {
          v7 = 621;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "CreateProfileDirAndSetAcls: Invalid filetype %d", 621);
        }
        CloseHandle(v17);
      }
    }
    if ( !v8 )
      return v7;
    if ( RevertToSelf() )
      return v7;
    LastError = GetLastError();
    v14 = g_dwTraceId;
    v7 = LastError;
    if ( g_dwTraceId == -1 )
      return v7;
    v15 = "CreateProfileDirAndSetAcls: RevertToSelf before returning: Failed %d";
LABEL_32:
    TracePrintfExA(v14, 0xCu, v15, LastError);
    return v7;
  }
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v8 = 1;
    goto LABEL_8;
  }
  v9 = GetLastError();
  v7 = v9;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CreateProfileDirAndSetAcls: ImpersonateLoggedOnUser Failed %d", v9);
  return v7;
}

```

## disassembly

```asm
0x1800d0590  mov     [rsp+arg_10], rbx
0x1800d0595  push    rbp
0x1800d0596  push    rsi
0x1800d0597  push    rdi
0x1800d0598  push    r14
0x1800d059a  push    r15
0x1800d059c  sub     rsp, 260h
0x1800d05a3  mov     rax, cs:__security_cookie
0x1800d05aa  xor     rax, rsp
0x1800d05ad  mov     [rsp+288h+var_38], rax
0x1800d05b5  mov     r14d, r8d
0x1800d05b8  mov     rbx, rdx
0x1800d05bb  mov     rdi, rcx
0x1800d05be  xor     edx, edx; Val
0x1800d05c0  mov     r8d, 20Ah; Size
0x1800d05c6  lea     rcx, [rsp+288h+FileName]; void *
0x1800d05cb  mov     r15d, r9d
0x1800d05ce  call    memset_0
0x1800d05d3  mov     r8, rbx
0x1800d05d6  lea     rcx, [rsp+288h+FileName]; pszDest
0x1800d05db  mov     edx, 105h
0x1800d05e0  call    StringCchCopyWrapW
0x1800d05e5  mov     ebx, eax
0x1800d05e7  test    eax, eax
0x1800d05e9  jnz     loc_1800D07B0
0x1800d05ef  xor     ebp, ebp
0x1800d05f1  cmp     r14d, 4
0x1800d05f5  jz      short loc_1800D063B
0x1800d05f7  lea     rax, [rdi-1]
0x1800d05fb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d05ff  ja      short loc_1800D063B
0x1800d0601  mov     rcx, rdi; hToken
0x1800d0604  call    cs:__imp_ImpersonateLoggedOnUser
0x1800d060a  test    eax, eax
0x1800d060c  jnz     short loc_1800D0636
0x1800d060e  call    cs:__imp_GetLastError
0x1800d0614  mov     ecx, cs:g_dwTraceId
0x1800d061a  or      edi, 0FFFFFFFFh
0x1800d061d  mov     ebx, eax
0x1800d061f  cmp     ecx, edi
0x1800d0621  jz      loc_1800D07B0
0x1800d0627  lea     r8, aCreateprofiled_3; "CreateProfileDirAndSetAcls: Impersonate"...
0x1800d062e  lea     edx, [rbp+0Ch]
0x1800d0631  jmp     loc_1800D07A7
0x1800d0636  mov     ebp, 1
0x1800d063b  lea     rcx, [rsp+288h+FileName]; lpPathName
0x1800d0640  call    CreateDirectoriesOnPath
0x1800d0645  or      edi, 0FFFFFFFFh
0x1800d0648  mov     ebx, eax
0x1800d064a  mov     esi, 0Ch
0x1800d064f  test    eax, eax
0x1800d0651  jz      short loc_1800D0678
0x1800d0653  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d0659  cmp     ecx, edi
0x1800d065b  jz      loc_1800D077E
0x1800d0661  mov     r9d, eax
0x1800d0664  lea     r8, aCreateprofiled; "CreateProfileDirAndSetAcls: CreateDirec"...
0x1800d066b  mov     edx, esi; dwFlags
0x1800d066d  call    cs:__imp_TracePrintfExA
0x1800d0673  jmp     loc_1800D077E
0x1800d0678  test    r14d, r14d
0x1800d067b  jnz     short loc_1800D06AE
0x1800d067d  mov     r8d, r15d
0x1800d0680  lea     rcx, [rsp+288h+FileName]
0x1800d0685  call    UpdateAclsOnPhonebookFolder
0x1800d068a  mov     ebx, eax
0x1800d068c  test    eax, eax
0x1800d068e  jz      short loc_1800D06AE
0x1800d0690  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d0696  cmp     ecx, edi
0x1800d0698  jz      short loc_1800D06AC
0x1800d069a  mov     r9d, eax
0x1800d069d  lea     r8, aCreateprofiled_5; "CreateProfileDirAndSetAcls: UpdateAclsO"...
0x1800d06a4  mov     edx, esi; dwFlags
0x1800d06a6  call    cs:__imp_TracePrintfExA
0x1800d06ac  xor     ebx, ebx
0x1800d06ae  test    ebp, ebp
0x1800d06b0  jz      short loc_1800D06E0
0x1800d06b2  xor     ebp, ebp
0x1800d06b4  call    cs:__imp_RevertToSelf
0x1800d06ba  test    eax, eax
0x1800d06bc  jnz     short loc_1800D06E0
0x1800d06be  call    cs:__imp_GetLastError
0x1800d06c4  mov     ecx, cs:g_dwTraceId
0x1800d06ca  mov     ebx, eax
0x1800d06cc  cmp     ecx, edi
0x1800d06ce  jz      loc_1800D07B0
0x1800d06d4  lea     r8, aCreateprofiled_4; "CreateProfileDirAndSetAcls: RevertToSel"...
0x1800d06db  jmp     loc_1800D07A5
0x1800d06e0  xor     r9d, r9d; lpSecurityAttributes
0x1800d06e3  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x1800d06ec  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d06f4  lea     rcx, [rsp+288h+FileName]; lpFileName
0x1800d06f9  mov     edx, 0C0000000h; dwDesiredAccess
0x1800d06fe  mov     [rsp+288h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d0706  lea     r8d, [r9+1]; dwShareMode
0x1800d070a  call    cs:__imp_CreateFileW
0x1800d0710  mov     r14, rax
0x1800d0713  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d0717  jz      short loc_1800D0753
0x1800d0719  mov     rcx, rax; hFile
0x1800d071c  call    cs:__imp_GetFileType
0x1800d0722  cmp     eax, 1
0x1800d0725  jz      short loc_1800D0748
0x1800d0727  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d072d  mov     ebx, 26Dh
0x1800d0732  cmp     ecx, edi
0x1800d0734  jz      short loc_1800D0748
0x1800d0736  mov     r9d, ebx
0x1800d0739  lea     r8, aCreateprofiled_2; "CreateProfileDirAndSetAcls: Invalid fil"...
0x1800d0740  mov     edx, esi; dwFlags
0x1800d0742  call    cs:__imp_TracePrintfExA
0x1800d0748  mov     rcx, r14; hObject
0x1800d074b  call    cs:__imp_CloseHandle
0x1800d0751  jmp     short loc_1800D077E
0x1800d0753  cmp     cs:g_dwTraceId, edi
0x1800d0759  jz      short loc_1800D0779
0x1800d075b  call    cs:__imp_GetLastError
0x1800d0761  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d0767  lea     r8, aCreateprofiled_1; "CreateProfileDirAndSetAcls: CreateFile:"...
0x1800d076e  mov     r9d, eax
0x1800d0771  mov     edx, esi; dwFlags
0x1800d0773  call    cs:__imp_TracePrintfExA
0x1800d0779  mov     ebx, 26Dh
0x1800d077e  test    ebp, ebp
0x1800d0780  jz      short loc_1800D07B0
0x1800d0782  call    cs:__imp_RevertToSelf
0x1800d0788  test    eax, eax
0x1800d078a  jnz     short loc_1800D07B0
0x1800d078c  call    cs:__imp_GetLastError
0x1800d0792  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d0798  mov     ebx, eax
0x1800d079a  cmp     ecx, edi
0x1800d079c  jz      short loc_1800D07B0
0x1800d079e  lea     r8, aCreateprofiled_0; "CreateProfileDirAndSetAcls: RevertToSel"...
0x1800d07a5  mov     edx, esi; dwFlags
0x1800d07a7  mov     r9d, eax
0x1800d07aa  call    cs:__imp_TracePrintfExA
0x1800d07b0  mov     eax, ebx
0x1800d07b2  mov     rcx, [rsp+288h+var_38]
0x1800d07ba  xor     rcx, rsp; StackCookie
0x1800d07bd  call    __security_check_cookie
0x1800d07c2  mov     rbx, [rsp+288h+arg_10]
0x1800d07ca  add     rsp, 260h
0x1800d07d1  pop     r15
0x1800d07d3  pop     r14
0x1800d07d5  pop     rdi
0x1800d07d6  pop     rsi
0x1800d07d7  pop     rbp
0x1800d07d8  retn
```
