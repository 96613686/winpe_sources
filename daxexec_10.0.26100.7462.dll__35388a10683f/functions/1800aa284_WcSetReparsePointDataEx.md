# WcSetReparsePointDataEx

- ea: `0x1800aa284`
- end: `0x1800aa5ab`
- name: `WcSetReparsePointDataEx`
- size: `807`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180035950`
- `0x1800aa6cc`

## callees

- `0x1800053a0`
- `0x1800aa00c`
- `0x1800aa284`
- `0x1800aa7b4`
- `0x1800aabf0`
- `0x1800aacf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aa575`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aa575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa47d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa54b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aa54b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa560`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aa3e2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aa3e2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aa415`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aa415`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800aa52c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800aa52c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aa341`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aa449`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aa341`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aa449`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800aa46d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800aa46d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa4fe`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aa4fe`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800aa3b3`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800aa3b3`

## pseudocode

```c
__int64 __fastcall WcSetReparsePointDataEx(__int64 a1, void *a2, __int64 a3, unsigned int a4)
{
  int v6; // r14d
  int v7; // r12d
  signed int FilterInstanceReparseTag; // ebx
  WCHAR *v9; // rsi
  HANDLE FileW; // rdi
  signed int LastError; // eax
  bool v12; // cc
  DWORD FileAttributesW; // eax
  __int64 v14; // rcx
  signed int v15; // eax
  bool v16; // cc
  int v18; // [rsp+44h] [rbp-4Dh] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-49h] BYREF
  PACL ppDacl; // [rsp+50h] [rbp-41h] BYREF
  PSID ppsidGroup; // [rsp+58h] [rbp-39h] BYREF
  PSID ppsidOwner; // [rsp+60h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+68h] [rbp-29h] BYREF
  void *Block; // [rsp+70h] [rbp-21h] BYREF
  _OWORD FileInformation[2]; // [rsp+78h] [rbp-19h] BYREF
  __int64 v26; // [rsp+98h] [rbp+7h]

  v18 = 0;
  v26 = 0;
  lpFileName = 0;
  v6 = 0;
  ppsidOwner = 0;
  v7 = 0;
  ppsidGroup = 0;
  ppDacl = 0;
  hMem = 0;
  Block = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !a2 && a4 != 2 )
    return (unsigned int)-2147024809;
  FilterInstanceReparseTag = WcpConstructLongPath(a1, &Block, &lpFileName);
  if ( FilterInstanceReparseTag >= 0 )
  {
    v9 = (WCHAR *)lpFileName;
    FileW = CreateFileW(lpFileName, 0x100u, 1u, 0, 3u, 0x2200000u, 0);
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_17;
    LastError = GetLastError();
    FilterInstanceReparseTag = LastError;
    if ( LastError != 5 )
    {
LABEL_7:
      v12 = LastError <= 0;
      goto LABEL_8;
    }
    LastError = GetNamedSecurityInfoW(v9, SE_FILE_OBJECT, 7u, &ppsidOwner, &ppsidGroup, &ppDacl, 0, &hMem);
    FilterInstanceReparseTag = LastError;
    v12 = LastError <= 0;
    if ( LastError )
    {
LABEL_8:
      if ( !v12 )
        FilterInstanceReparseTag = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_30;
    }
    FilterInstanceReparseTag = WcpTakeOwnership(v9);
    if ( FilterInstanceReparseTag >= 0 )
    {
      v6 = 1;
      FileAttributesW = GetFileAttributesW(v9);
      if ( FileAttributesW == -1
        || (FileAttributesW & 1) != 0 && (v7 = 1, !SetFileAttributesW(v9, FileAttributesW & 0xFFFFFFFE))
        || (FileW = CreateFileW(v9, 0x100u, 1u, 0, 3u, 0x2200000u, 0), FileW == (HANDLE)-1LL) )
      {
        LastError = GetLastError();
        FilterInstanceReparseTag = LastError;
        goto LABEL_7;
      }
LABEL_17:
      if ( !GetFileInformationByHandleEx(FileW, FileBasicInfo, FileInformation, 0x28u) )
        goto LABEL_18;
      FilterInstanceReparseTag = WcGetFilterInstanceReparseTag(v14, a4, &v18);
      if ( FilterInstanceReparseTag >= 0 )
      {
        FilterInstanceReparseTag = WcpWriteReparsePoint(FileW, a2);
        if ( FilterInstanceReparseTag >= 0 )
        {
          if ( v6 )
          {
            v15 = SetNamedSecurityInfoW(v9, SE_FILE_OBJECT, 7u, ppsidOwner, ppsidGroup, ppDacl, 0);
            FilterInstanceReparseTag = v15;
            v16 = v15 <= 0;
            if ( v15 )
            {
LABEL_19:
              if ( !v16 )
                FilterInstanceReparseTag = (unsigned __int16)v15 | 0x80070000;
              goto LABEL_29;
            }
          }
          if ( v7 )
            LODWORD(v26) = v26 | 1;
          if ( !SetFileInformationByHandle(FileW, FileBasicInfo, FileInformation, 0x28u) )
          {
LABEL_18:
            v15 = GetLastError();
            FilterInstanceReparseTag = v15;
            v16 = v15 <= 0;
            goto LABEL_19;
          }
          FilterInstanceReparseTag = 0;
        }
      }
LABEL_29:
      CloseHandle(FileW);
    }
  }
LABEL_30:
  if ( hMem )
    LocalFree(hMem);
  if ( Block )
    free(Block);
  return (unsigned int)FilterInstanceReparseTag;
}

```

## disassembly

```asm
0x1800aa284  mov     [rsp-8+arg_18], rbx
0x1800aa289  push    rbp
0x1800aa28a  push    rsi
0x1800aa28b  push    rdi
0x1800aa28c  push    r12
0x1800aa28e  push    r13
0x1800aa290  push    r14
0x1800aa292  push    r15
0x1800aa294  lea     rbp, [rsp-1Fh]
0x1800aa299  sub     rsp, 0B0h
0x1800aa2a0  mov     rax, cs:__security_cookie
0x1800aa2a7  xor     rax, rsp
0x1800aa2aa  mov     [rbp+4Fh+var_40], rax
0x1800aa2ae  mov     r13, rdx
0x1800aa2b1  mov     [rbp+4Fh+var_A0], r8w
0x1800aa2b6  xor     edx, edx
0x1800aa2b8  xor     eax, eax
0x1800aa2ba  mov     [rbp+4Fh+var_9C], edx
0x1800aa2bd  xorps   xmm0, xmm0
0x1800aa2c0  mov     [rbp+4Fh+var_48], rax
0x1800aa2c4  mov     r15d, r9d
0x1800aa2c7  mov     [rbp+4Fh+lpFileName], rdx
0x1800aa2cb  mov     r14d, edx
0x1800aa2ce  mov     [rbp+4Fh+ppsidOwner], rdx
0x1800aa2d2  mov     r12d, edx
0x1800aa2d5  mov     [rbp+4Fh+ppsidGroup], rdx
0x1800aa2d9  mov     [rbp+4Fh+ppDacl], rdx
0x1800aa2dd  mov     [rbp+4Fh+hMem], rdx
0x1800aa2e1  mov     [rbp+4Fh+Block], rdx
0x1800aa2e5  movups  [rbp+4Fh+FileInformation], xmm0
0x1800aa2e9  movups  [rbp+4Fh+var_58], xmm0
0x1800aa2ed  test    r13, r13
0x1800aa2f0  jnz     short loc_1800AA302
0x1800aa2f2  cmp     r9d, 2
0x1800aa2f6  jz      short loc_1800AA302
0x1800aa2f8  mov     ebx, 80070057h
0x1800aa2fd  jmp     loc_1800AA581
0x1800aa302  lea     r8, [rbp+4Fh+lpFileName]
0x1800aa306  lea     rdx, [rbp+4Fh+Block]
0x1800aa30a  call    WcpConstructLongPath
0x1800aa30f  mov     ebx, eax
0x1800aa311  test    eax, eax
0x1800aa313  js      loc_1800AA557
0x1800aa319  and     [rsp+0E0h+var_B0], r12
0x1800aa31e  xor     r9d, r9d; lpSecurityAttributes
0x1800aa321  mov     rsi, [rbp+4Fh+lpFileName]
0x1800aa325  mov     edx, 100h; dwDesiredAccess
0x1800aa32a  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800aa332  mov     rcx, rsi; lpFileName
0x1800aa335  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800aa33d  lea     r8d, [r9+1]; dwShareMode
0x1800aa341  call    cs:__imp_CreateFileW
0x1800aa348  nop     dword ptr [rax+rax+00h]
0x1800aa34d  mov     rdi, rax
0x1800aa350  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800aa354  jnz     loc_1800AA45E
0x1800aa35a  call    cs:__imp_GetLastError
0x1800aa361  nop     dword ptr [rax+rax+00h]
0x1800aa366  mov     ebx, eax
0x1800aa368  cmp     eax, 5
0x1800aa36b  jz      short loc_1800AA383
0x1800aa36d  test    eax, eax
0x1800aa36f  jle     loc_1800AA557
0x1800aa375  movzx   ebx, ax
0x1800aa378  or      ebx, 80070000h
0x1800aa37e  jmp     loc_1800AA557
0x1800aa383  lea     rax, [rbp+4Fh+hMem]
0x1800aa387  mov     edx, 1; ObjectType
0x1800aa38c  mov     [rsp+0E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800aa391  lea     r9, [rbp+4Fh+ppsidOwner]; ppsidOwner
0x1800aa395  and     [rsp+0E0h+var_B0], r12
0x1800aa39a  lea     rax, [rbp+4Fh+ppDacl]
0x1800aa39e  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; ppDacl
0x1800aa3a3  mov     rcx, rsi; pObjectName
0x1800aa3a6  lea     rax, [rbp+4Fh+ppsidGroup]
0x1800aa3aa  lea     r8d, [rdx+6]; SecurityInfo
0x1800aa3ae  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; ppsidGroup
0x1800aa3b3  call    cs:__imp_GetNamedSecurityInfoW
0x1800aa3ba  nop     dword ptr [rax+rax+00h]
0x1800aa3bf  mov     ebx, eax
0x1800aa3c1  test    eax, eax
0x1800aa3c3  jnz     short loc_1800AA36F
0x1800aa3c5  mov     rcx, rsi; pObjectName
0x1800aa3c8  call    WcpTakeOwnership
0x1800aa3cd  mov     ebx, eax
0x1800aa3cf  test    eax, eax
0x1800aa3d1  js      loc_1800AA557
0x1800aa3d7  mov     ebx, 1
0x1800aa3dc  mov     rcx, rsi; lpFileName
0x1800aa3df  mov     r14d, ebx
0x1800aa3e2  call    cs:__imp_GetFileAttributesW
0x1800aa3e9  nop     dword ptr [rax+rax+00h]
0x1800aa3ee  cmp     eax, 0FFFFFFFFh
0x1800aa3f1  jnz     short loc_1800AA406
0x1800aa3f3  call    cs:__imp_GetLastError
0x1800aa3fa  nop     dword ptr [rax+rax+00h]
0x1800aa3ff  mov     ebx, eax
0x1800aa401  jmp     loc_1800AA36D
0x1800aa406  test    bl, al
0x1800aa408  jz      short loc_1800AA425
0x1800aa40a  and     eax, 0FFFFFFFEh
0x1800aa40d  mov     rcx, rsi; lpFileName
0x1800aa410  mov     edx, eax; dwFileAttributes
0x1800aa412  mov     r12d, ebx
0x1800aa415  call    cs:__imp_SetFileAttributesW
0x1800aa41c  nop     dword ptr [rax+rax+00h]
0x1800aa421  test    eax, eax
0x1800aa423  jz      short loc_1800AA3F3
0x1800aa425  and     [rsp+0E0h+var_B0], 0
0x1800aa42b  xor     r9d, r9d; lpSecurityAttributes
0x1800aa42e  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800aa436  mov     r8d, ebx; dwShareMode
0x1800aa439  mov     edx, 100h; dwDesiredAccess
0x1800aa43e  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800aa446  mov     rcx, rsi; lpFileName
0x1800aa449  call    cs:__imp_CreateFileW
0x1800aa450  nop     dword ptr [rax+rax+00h]
0x1800aa455  mov     rdi, rax
0x1800aa458  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800aa45c  jz      short loc_1800AA3F3
0x1800aa45e  mov     r9d, 28h ; '('; dwBufferSize
0x1800aa464  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x1800aa468  xor     edx, edx; FileInformationClass
0x1800aa46a  mov     rcx, rdi; hFile
0x1800aa46d  call    cs:__imp_GetFileInformationByHandleEx
0x1800aa474  nop     dword ptr [rax+rax+00h]
0x1800aa479  test    eax, eax
0x1800aa47b  jnz     short loc_1800AA4A1
0x1800aa47d  call    cs:__imp_GetLastError
0x1800aa484  nop     dword ptr [rax+rax+00h]
0x1800aa489  mov     ebx, eax
0x1800aa48b  test    eax, eax
0x1800aa48d  jle     loc_1800AA542
0x1800aa493  movzx   ebx, ax
0x1800aa496  or      ebx, 80070000h
0x1800aa49c  jmp     loc_1800AA542
0x1800aa4a1  lea     r8, [rbp+4Fh+var_9C]
0x1800aa4a5  mov     edx, r15d
0x1800aa4a8  call    WcGetFilterInstanceReparseTag
0x1800aa4ad  mov     ebx, eax
0x1800aa4af  test    eax, eax
0x1800aa4b1  js      loc_1800AA542
0x1800aa4b7  mov     r9d, [rbp+4Fh+var_9C]
0x1800aa4bb  mov     rdx, r13; Src
0x1800aa4be  movzx   r8d, [rbp+4Fh+var_A0]
0x1800aa4c3  mov     rcx, rdi; hDevice
0x1800aa4c6  call    WcpWriteReparsePoint
0x1800aa4cb  mov     ebx, eax
0x1800aa4cd  test    eax, eax
0x1800aa4cf  js      short loc_1800AA542
0x1800aa4d1  test    r14d, r14d
0x1800aa4d4  jz      short loc_1800AA514
0x1800aa4d6  mov     rax, [rbp+4Fh+ppDacl]
0x1800aa4da  mov     edx, 1; ObjectType
0x1800aa4df  and     [rsp+0E0h+var_B0], 0
0x1800aa4e5  mov     rcx, rsi; pObjectName
0x1800aa4e8  mov     r9, [rbp+4Fh+ppsidOwner]; psidOwner
0x1800aa4ec  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; pDacl
0x1800aa4f1  mov     rax, [rbp+4Fh+ppsidGroup]
0x1800aa4f5  lea     r8d, [rdx+6]; SecurityInfo
0x1800aa4f9  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; psidGroup
0x1800aa4fe  call    cs:__imp_SetNamedSecurityInfoW
0x1800aa505  nop     dword ptr [rax+rax+00h]
0x1800aa50a  mov     ebx, eax
0x1800aa50c  test    eax, eax
0x1800aa50e  jnz     loc_1800AA48D
0x1800aa514  test    r12d, r12d
0x1800aa517  jz      short loc_1800AA51D
0x1800aa519  or      dword ptr [rbp+4Fh+var_48], 1
0x1800aa51d  mov     r9d, 28h ; '('; dwBufferSize
0x1800aa523  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x1800aa527  xor     edx, edx; FileInformationClass
0x1800aa529  mov     rcx, rdi; hFile
0x1800aa52c  call    cs:__imp_SetFileInformationByHandle
0x1800aa533  nop     dword ptr [rax+rax+00h]
0x1800aa538  test    eax, eax
0x1800aa53a  jz      loc_1800AA47D
0x1800aa540  xor     ebx, ebx
0x1800aa542  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800aa546  jz      short loc_1800AA557
0x1800aa548  mov     rcx, rdi; hObject
0x1800aa54b  call    cs:__imp_CloseHandle
0x1800aa552  nop     dword ptr [rax+rax+00h]
0x1800aa557  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800aa55b  test    rcx, rcx
0x1800aa55e  jz      short loc_1800AA56C
0x1800aa560  call    cs:__imp_LocalFree
0x1800aa567  nop     dword ptr [rax+rax+00h]
0x1800aa56c  mov     rcx, [rbp+4Fh+Block]; Block
0x1800aa570  test    rcx, rcx
0x1800aa573  jz      short loc_1800AA581
0x1800aa575  call    cs:__imp_free
0x1800aa57c  nop     dword ptr [rax+rax+00h]
0x1800aa581  mov     eax, ebx
0x1800aa583  mov     rcx, [rbp+4Fh+var_40]
0x1800aa587  xor     rcx, rsp; StackCookie
0x1800aa58a  call    __security_check_cookie
0x1800aa58f  mov     rbx, [rsp+0E0h+arg_18]
0x1800aa597  add     rsp, 0B0h
0x1800aa59e  pop     r15
0x1800aa5a0  pop     r14
0x1800aa5a2  pop     r13
0x1800aa5a4  pop     r12
0x1800aa5a6  pop     rdi
0x1800aa5a7  pop     rsi
0x1800aa5a8  pop     rbp
0x1800aa5a9  retn
```
