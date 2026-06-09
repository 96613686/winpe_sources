# WcSetReparsePointDataEx

- ea: `0x1800ab8c4`
- end: `0x1800abbf3`
- name: `WcSetReparsePointDataEx`
- size: `815`
- prototype: `__int64 __fastcall(__int64, void *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800372a0`
- `0x1800abcfc`

## callees

- `0x180004f70`
- `0x1800ab64c`
- `0x1800ab8c4`
- `0x1800abdd4`
- `0x1800ac1f0`
- `0x1800ac2fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800abbbd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800abbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aba2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aba2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abac2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800abb93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800abb93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800abba8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800abba8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aba1c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aba1c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800abb74`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800abb74`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aba54`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aba54`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ab983`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aba8e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ab983`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aba8e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800abab2`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800abab2`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800abb46`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800abb46`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800ab9f5`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800ab9f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WcSetReparsePointDataEx(__int64 a1, void *a2, __int64 a3, unsigned int a4)
{
  signed int FilterInstanceReparseTag; // ebx
  WCHAR *v7; // rsi
  int v8; // r14d
  int v9; // r12d
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
  ppsidOwner = 0;
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
    v7 = (WCHAR *)lpFileName;
    v8 = 0;
    v9 = 0;
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
    LastError = GetNamedSecurityInfoW(v7, SE_FILE_OBJECT, 7u, &ppsidOwner, &ppsidGroup, &ppDacl, 0, &hMem);
    FilterInstanceReparseTag = LastError;
    v12 = LastError <= 0;
    if ( LastError )
    {
LABEL_8:
      if ( !v12 )
        FilterInstanceReparseTag = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_30;
    }
    FilterInstanceReparseTag = WcpTakeOwnership(v7);
    if ( FilterInstanceReparseTag >= 0 )
    {
      FileAttributesW = GetFileAttributesW(v7);
      if ( FileAttributesW == -1
        || (FileAttributesW & 1) != 0 && (v9 = 1, !SetFileAttributesW(v7, FileAttributesW & 0xFFFFFFFE))
        || (v8 = 1, FileW = CreateFileW(v7, 0x100u, 1u, 0, 3u, 0x2200000u, 0), FileW == (HANDLE)-1LL) )
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
          if ( v8 )
          {
            v15 = SetNamedSecurityInfoW(v7, SE_FILE_OBJECT, 7u, ppsidOwner, ppsidGroup, ppDacl, 0);
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
          if ( v9 )
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
0x1800ab8c4  mov     [rsp-8+arg_18], rbx
0x1800ab8c9  push    rbp
0x1800ab8ca  push    rsi
0x1800ab8cb  push    rdi
0x1800ab8cc  push    r12
0x1800ab8ce  push    r13
0x1800ab8d0  push    r14
0x1800ab8d2  push    r15
0x1800ab8d4  lea     rbp, [rsp-1Fh]
0x1800ab8d9  sub     rsp, 0B0h
0x1800ab8e0  mov     rax, cs:__security_cookie
0x1800ab8e7  xor     rax, rsp
0x1800ab8ea  mov     [rbp+4Fh+var_40], rax
0x1800ab8ee  xor     eax, eax
0x1800ab8f0  mov     [rbp+4Fh+var_A0], r8w
0x1800ab8f5  mov     [rbp+4Fh+var_9C], 0
0x1800ab8fc  xorps   xmm0, xmm0
0x1800ab8ff  mov     [rbp+4Fh+var_48], rax
0x1800ab903  mov     r15d, r9d
0x1800ab906  mov     [rbp+4Fh+lpFileName], rax
0x1800ab90a  mov     r13, rdx
0x1800ab90d  mov     [rbp+4Fh+ppsidOwner], rax
0x1800ab911  mov     [rbp+4Fh+ppsidGroup], rax
0x1800ab915  mov     [rbp+4Fh+ppDacl], rax
0x1800ab919  mov     [rbp+4Fh+hMem], rax
0x1800ab91d  mov     [rbp+4Fh+Block], rax
0x1800ab921  movups  [rbp+4Fh+FileInformation], xmm0
0x1800ab925  movups  [rbp+4Fh+var_58], xmm0
0x1800ab929  test    rdx, rdx
0x1800ab92c  jnz     short loc_1800AB93E
0x1800ab92e  cmp     r9d, 2
0x1800ab932  jz      short loc_1800AB93E
0x1800ab934  mov     ebx, 80070057h
0x1800ab939  jmp     loc_1800ABBC9
0x1800ab93e  lea     r8, [rbp+4Fh+lpFileName]
0x1800ab942  lea     rdx, [rbp+4Fh+Block]
0x1800ab946  call    WcpConstructLongPath
0x1800ab94b  mov     ebx, eax
0x1800ab94d  test    eax, eax
0x1800ab94f  js      loc_1800ABB9F
0x1800ab955  mov     rsi, [rbp+4Fh+lpFileName]
0x1800ab959  xor     r14d, r14d
0x1800ab95c  xor     r12d, r12d
0x1800ab95f  xor     r9d, r9d; lpSecurityAttributes
0x1800ab962  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x1800ab967  mov     edx, 100h; dwDesiredAccess
0x1800ab96c  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800ab974  mov     rcx, rsi; lpFileName
0x1800ab977  lea     r8d, [r14+1]; dwShareMode
0x1800ab97b  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ab983  call    cs:__imp_CreateFileW
0x1800ab98a  nop     dword ptr [rax+rax+00h]
0x1800ab98f  mov     rdi, rax
0x1800ab992  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ab996  jnz     loc_1800ABAA3
0x1800ab99c  call    cs:__imp_GetLastError
0x1800ab9a3  nop     dword ptr [rax+rax+00h]
0x1800ab9a8  mov     ebx, eax
0x1800ab9aa  cmp     eax, 5
0x1800ab9ad  jz      short loc_1800AB9C5
0x1800ab9af  test    eax, eax
0x1800ab9b1  jle     loc_1800ABB9F
0x1800ab9b7  movzx   ebx, ax
0x1800ab9ba  or      ebx, 80070000h
0x1800ab9c0  jmp     loc_1800ABB9F
0x1800ab9c5  lea     rax, [rbp+4Fh+hMem]
0x1800ab9c9  mov     edx, 1; ObjectType
0x1800ab9ce  mov     [rsp+0E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800ab9d3  lea     r9, [rbp+4Fh+ppsidOwner]; ppsidOwner
0x1800ab9d7  lea     rax, [rbp+4Fh+ppDacl]
0x1800ab9db  mov     [rsp+0E0h+hTemplateFile], r12; ppSacl
0x1800ab9e0  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; ppDacl
0x1800ab9e5  mov     rcx, rsi; pObjectName
0x1800ab9e8  lea     rax, [rbp+4Fh+ppsidGroup]
0x1800ab9ec  lea     r8d, [rdx+6]; SecurityInfo
0x1800ab9f0  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; ppsidGroup
0x1800ab9f5  call    cs:__imp_GetNamedSecurityInfoW
0x1800ab9fc  nop     dword ptr [rax+rax+00h]
0x1800aba01  mov     ebx, eax
0x1800aba03  test    eax, eax
0x1800aba05  jnz     short loc_1800AB9B1
0x1800aba07  mov     rcx, rsi; pObjectName
0x1800aba0a  call    WcpTakeOwnership
0x1800aba0f  mov     ebx, eax
0x1800aba11  test    eax, eax
0x1800aba13  js      loc_1800ABB9F
0x1800aba19  mov     rcx, rsi; lpFileName
0x1800aba1c  call    cs:__imp_GetFileAttributesW
0x1800aba23  nop     dword ptr [rax+rax+00h]
0x1800aba28  cmp     eax, 0FFFFFFFFh
0x1800aba2b  jnz     short loc_1800ABA40
0x1800aba2d  call    cs:__imp_GetLastError
0x1800aba34  nop     dword ptr [rax+rax+00h]
0x1800aba39  mov     ebx, eax
0x1800aba3b  jmp     loc_1800AB9AF
0x1800aba40  mov     ebx, 1
0x1800aba45  test    bl, al
0x1800aba47  jz      short loc_1800ABA64
0x1800aba49  and     eax, 0FFFFFFFEh
0x1800aba4c  mov     rcx, rsi; lpFileName
0x1800aba4f  mov     edx, eax; dwFileAttributes
0x1800aba51  mov     r12d, ebx
0x1800aba54  call    cs:__imp_SetFileAttributesW
0x1800aba5b  nop     dword ptr [rax+rax+00h]
0x1800aba60  test    eax, eax
0x1800aba62  jz      short loc_1800ABA2D
0x1800aba64  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x1800aba6d  xor     r9d, r9d; lpSecurityAttributes
0x1800aba70  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800aba78  mov     r8d, ebx; dwShareMode
0x1800aba7b  mov     edx, 100h; dwDesiredAccess
0x1800aba80  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800aba88  mov     rcx, rsi; lpFileName
0x1800aba8b  mov     r14d, ebx
0x1800aba8e  call    cs:__imp_CreateFileW
0x1800aba95  nop     dword ptr [rax+rax+00h]
0x1800aba9a  mov     rdi, rax
0x1800aba9d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800abaa1  jz      short loc_1800ABA2D
0x1800abaa3  mov     r9d, 28h ; '('; dwBufferSize
0x1800abaa9  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x1800abaad  xor     edx, edx; FileInformationClass
0x1800abaaf  mov     rcx, rdi; hFile
0x1800abab2  call    cs:__imp_GetFileInformationByHandleEx
0x1800abab9  nop     dword ptr [rax+rax+00h]
0x1800ababe  test    eax, eax
0x1800abac0  jnz     short loc_1800ABAE6
0x1800abac2  call    cs:__imp_GetLastError
0x1800abac9  nop     dword ptr [rax+rax+00h]
0x1800abace  mov     ebx, eax
0x1800abad0  test    eax, eax
0x1800abad2  jle     loc_1800ABB8A
0x1800abad8  movzx   ebx, ax
0x1800abadb  or      ebx, 80070000h
0x1800abae1  jmp     loc_1800ABB8A
0x1800abae6  lea     r8, [rbp+4Fh+var_9C]
0x1800abaea  mov     edx, r15d
0x1800abaed  call    WcGetFilterInstanceReparseTag
0x1800abaf2  mov     ebx, eax
0x1800abaf4  test    eax, eax
0x1800abaf6  js      loc_1800ABB8A
0x1800abafc  mov     r9d, [rbp+4Fh+var_9C]
0x1800abb00  mov     rdx, r13; Src
0x1800abb03  movzx   r8d, [rbp+4Fh+var_A0]
0x1800abb08  mov     rcx, rdi; hDevice
0x1800abb0b  call    WcpWriteReparsePoint
0x1800abb10  mov     ebx, eax
0x1800abb12  test    eax, eax
0x1800abb14  js      short loc_1800ABB8A
0x1800abb16  test    r14d, r14d
0x1800abb19  jz      short loc_1800ABB5C
0x1800abb1b  mov     rax, [rbp+4Fh+ppDacl]
0x1800abb1f  mov     edx, 1; ObjectType
0x1800abb24  mov     r9, [rbp+4Fh+ppsidOwner]; psidOwner
0x1800abb28  mov     rcx, rsi; pObjectName
0x1800abb2b  mov     [rsp+0E0h+hTemplateFile], 0; pSacl
0x1800abb34  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; pDacl
0x1800abb39  mov     rax, [rbp+4Fh+ppsidGroup]
0x1800abb3d  lea     r8d, [rdx+6]; SecurityInfo
0x1800abb41  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; psidGroup
0x1800abb46  call    cs:__imp_SetNamedSecurityInfoW
0x1800abb4d  nop     dword ptr [rax+rax+00h]
0x1800abb52  mov     ebx, eax
0x1800abb54  test    eax, eax
0x1800abb56  jnz     loc_1800ABAD2
0x1800abb5c  test    r12d, r12d
0x1800abb5f  jz      short loc_1800ABB65
0x1800abb61  or      dword ptr [rbp+4Fh+var_48], 1
0x1800abb65  mov     r9d, 28h ; '('; dwBufferSize
0x1800abb6b  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x1800abb6f  xor     edx, edx; FileInformationClass
0x1800abb71  mov     rcx, rdi; hFile
0x1800abb74  call    cs:__imp_SetFileInformationByHandle
0x1800abb7b  nop     dword ptr [rax+rax+00h]
0x1800abb80  test    eax, eax
0x1800abb82  jz      loc_1800ABAC2
0x1800abb88  xor     ebx, ebx
0x1800abb8a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800abb8e  jz      short loc_1800ABB9F
0x1800abb90  mov     rcx, rdi; hObject
0x1800abb93  call    cs:__imp_CloseHandle
0x1800abb9a  nop     dword ptr [rax+rax+00h]
0x1800abb9f  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800abba3  test    rcx, rcx
0x1800abba6  jz      short loc_1800ABBB4
0x1800abba8  call    cs:__imp_LocalFree
0x1800abbaf  nop     dword ptr [rax+rax+00h]
0x1800abbb4  mov     rcx, [rbp+4Fh+Block]; Block
0x1800abbb8  test    rcx, rcx
0x1800abbbb  jz      short loc_1800ABBC9
0x1800abbbd  call    cs:__imp_free
0x1800abbc4  nop     dword ptr [rax+rax+00h]
0x1800abbc9  mov     eax, ebx
0x1800abbcb  mov     rcx, [rbp+4Fh+var_40]
0x1800abbcf  xor     rcx, rsp; StackCookie
0x1800abbd2  call    __security_check_cookie
0x1800abbd7  mov     rbx, [rsp+0E0h+arg_18]
0x1800abbdf  add     rsp, 0B0h
0x1800abbe6  pop     r15
0x1800abbe8  pop     r14
0x1800abbea  pop     r13
0x1800abbec  pop     r12
0x1800abbee  pop     rdi
0x1800abbef  pop     rsi
0x1800abbf0  pop     rbp
0x1800abbf1  retn
```
