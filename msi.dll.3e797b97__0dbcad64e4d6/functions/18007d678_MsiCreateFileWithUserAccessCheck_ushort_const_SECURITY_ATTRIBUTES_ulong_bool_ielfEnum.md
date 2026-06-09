# MsiCreateFileWithUserAccessCheck(ushort const *,_SECURITY_ATTRIBUTES *,ulong,bool,ielfEnum)

- ea: `0x18007d678`
- end: `0x18007dc86`
- name: `?MsiCreateFileWithUserAccessCheck@@YAPEAXPEBGPEAU_SECURITY_ATTRIBUTES@@K_NW4ielfEnum@@@Z`
- size: `1550`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007d29c`
- `0x18009d8e0`

## callees

- `0x18000c4bc`
- `0x180013fe4`
- `0x180014528`
- `0x180067fec`
- `0x18007adb4`
- `0x18007b9e8`
- `0x18007d678`
- `0x18007f4c8`
- `0x1802651c6`
- `0x180265240`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x18007d78f`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18007d78f`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007d8f8`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007da61`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007d8f8`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007da61`
- `KERNEL32!CloseHandle` at `0x18007d763`
- `KERNEL32!CloseHandle` at `0x18007d9fe`
- `KERNEL32!CloseHandle` at `0x18007dc13`
- `KERNEL32!CloseHandle` at `0x18007d763`
- `KERNEL32!CloseHandle` at `0x18007d9fe`
- `KERNEL32!CloseHandle` at `0x18007dc13`
- `KERNEL32!GetLastError` at `0x18007d883`
- `KERNEL32!GetLastError` at `0x18007d908`
- `KERNEL32!GetLastError` at `0x18007da73`
- `KERNEL32!GetLastError` at `0x18007dbe3`
- `KERNEL32!GetLastError` at `0x18007d883`
- `KERNEL32!GetLastError` at `0x18007d908`
- `KERNEL32!GetLastError` at `0x18007da73`
- `KERNEL32!GetLastError` at `0x18007dbe3`
- `KERNEL32!SetLastError` at `0x18007d777`
- `KERNEL32!SetLastError` at `0x18007dc24`
- `KERNEL32!SetLastError` at `0x18007d777`
- `KERNEL32!SetLastError` at `0x18007dc24`
- `KERNEL32!CreateFileW` at `0x18007d6dd`
- `KERNEL32!CreateFileW` at `0x18007d7fe`
- `KERNEL32!CreateFileW` at `0x18007d8cf`
- `KERNEL32!CreateFileW` at `0x18007da2e`
- `KERNEL32!CreateFileW` at `0x18007d6dd`
- `KERNEL32!CreateFileW` at `0x18007d7fe`
- `KERNEL32!CreateFileW` at `0x18007d8cf`
- `KERNEL32!CreateFileW` at `0x18007da2e`
- `KERNEL32!GetFileType` at `0x18007d6fc`
- `KERNEL32!GetFileType` at `0x18007d815`
- `KERNEL32!GetFileType` at `0x18007d96e`
- `KERNEL32!GetFileType` at `0x18007d6fc`
- `KERNEL32!GetFileType` at `0x18007d815`
- `KERNEL32!GetFileType` at `0x18007d96e`
- `KERNEL32!SetFileAttributesW` at `0x18007db4e`
- `KERNEL32!SetFileAttributesW` at `0x18007db4e`
- `USER32!SetUserObjectSecurity` at `0x18007dbd3`
- `USER32!SetUserObjectSecurity` at `0x18007dbd3`

## string_xrefs

- `0x18007d72e`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18007d838`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18007d99a`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18007da99`: `Error: Get opened file info failed: %s`
- `0x18007d934`: `Error: Get created file info failed: %s`
- `0x18007db08`: `Error: The file was replaced to another file, hence failing to open: %s`

## pseudocode

```c
__int64 __fastcall MsiCreateFileWithUserAccessCheck(const WCHAR *a1, __int64 a2, DWORD a3, char a4, char a5)
{
  HANDLE v8; // rax
  __int64 v9; // rdi
  int v11; // eax
  DWORD v12; // edi
  HANDLE FileW; // rax
  __int64 v14; // r14
  DWORD v15; // ebx
  DWORD LastError; // eax
  HANDLE v17; // rax
  CElevate *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r13
  unsigned int v21; // esi
  __int64 v22; // rdx
  unsigned int v23; // edi
  int v24; // r12d
  __int64 v25; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-31h] BYREF
  DWORD pSIRequested; // [rsp+78h] [rbp-29h] BYREF
  _BYTE v28[8]; // [rsp+80h] [rbp-21h] BYREF
  __int128 Buf2; // [rsp+88h] [rbp-19h] BYREF
  __int64 v30; // [rsp+98h] [rbp-9h]
  __int128 FileInformation; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v32; // [rsp+B0h] [rbp+Fh]

  v25 = a2;
  if ( a2 )
  {
    if ( !IsValidSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8)) )
      return -1;
    FileInformation = 0;
    v32 = 0;
    v11 = RunningAsLocalSystem();
    if ( v11 == -1 )
      return -1;
    v12 = 1074528256;
    if ( v11 == 1 && !a4 )
      v12 = 1091305472;
    FileW = CreateFileW(a1, v12, 0, 0, 2u, a3 | 0x100000, 0);
    v14 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL && GetFileType(FileW) - 2 <= 1 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: This is not a valid file, hence failing to create: %s",
          a1,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v15 = 110;
      goto LABEL_51;
    }
    LastError = GetLastError();
    if ( v14 == -1 )
    {
      if ( LastError != 5 && LastError != 1314 )
        return v14;
      v17 = CreateFileW(a1, 0x40000000u, 0, 0, 2u, 0x100000u, 0);
      v14 = (__int64)v17;
      if ( v17 == (HANDLE)-1LL )
        return v14;
      if ( !GetFileInformationByHandleEx(v17, MaximumFileInfoByHandleClass, &FileInformation, 0x18u) )
      {
        v15 = GetLastError();
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error: Get created file info failed: %s",
            a1,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
LABEL_50:
        if ( v15 )
        {
LABEL_51:
          CloseHandle((HANDLE)v14);
          v14 = -1;
          SetLastError(v15);
        }
        return v14;
      }
      if ( GetFileType((HANDLE)v14) - 2 <= 1 )
      {
        v15 = 110;
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error: This is not a valid file, hence failing to create: %s",
            a1,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_51;
      }
      CElevate::CElevate((CElevate *)&v26, 1);
      CloseHandle((HANDLE)v14);
      v14 = (__int64)CreateFileW(a1, v12, 0, 0, 4u, 0x100000u, 0);
      if ( v14 != -1 )
      {
        v30 = 0;
        Buf2 = 0;
        if ( !GetFileInformationByHandleEx((HANDLE)v14, MaximumFileInfoByHandleClass, &Buf2, 0x18u) )
        {
          v15 = GetLastError();
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"Error: Get opened file info failed: %s",
              a1,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          v18 = (CElevate *)&v26;
LABEL_49:
          CElevate::~CElevate(v18);
          goto LABEL_50;
        }
        if ( memcmp_0(&FileInformation, &Buf2, 0x18u) )
        {
          v15 = 110;
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"Error: The file was replaced to another file, hence failing to open: %s",
              a1,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          CElevate::~CElevate((CElevate *)&v26);
          goto LABEL_51;
        }
        SetFileAttributesW(a1, a3);
      }
      CElevate::~CElevate((CElevate *)&v26);
      if ( v14 == -1 )
        return v14;
    }
    CElevate::CElevate((CElevate *)v28, (a5 & 8) != 0);
    LOBYTE(v19) = 1;
    v20 = v25;
    v21 = 2;
    if ( (unsigned __int8)RefCountedTokenPrivilegesCore(1, v19) )
      v21 = 1;
    v26 = v21;
    pSIRequested = GetSecurityInformation(*(PSECURITY_DESCRIPTOR *)(v25 + 8));
    v23 = 2;
    LODWORD(v25) = 2;
    if ( (pSIRequested & 8) != 0 && (LOBYTE(v22) = 1, (unsigned __int8)RefCountedTokenPrivilegesCore(0, v22)) )
    {
      v23 = 0;
      LODWORD(v25) = 0;
      v24 = 0;
    }
    else
    {
      v24 = 2;
    }
    if ( SetUserObjectSecurity((HANDLE)v14, &pSIRequested, *(PSECURITY_DESCRIPTOR *)(v20 + 8)) )
    {
      if ( v24 != 2 )
        RefCountedTokenPrivilegesCore(v23, 0);
      if ( v21 != 2 )
        RefCountedTokenPrivilegesCore(v21, 0);
      CElevate::~CElevate((CElevate *)v28);
      return v14;
    }
    v15 = GetLastError();
    CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v25);
    CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v26);
    v18 = (CElevate *)v28;
    goto LABEL_49;
  }
  v8 = CreateFileW(a1, 0x40000000u, 0, 0, 2u, a3 | 0x100000, 0);
  v9 = (__int64)v8;
  if ( v8 != (HANDLE)-1LL && GetFileType(v8) - 2 <= 1 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Error: This is not a valid file, hence failing to create: %s",
        a1,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    CloseHandle((HANDLE)v9);
    v9 = -1;
    SetLastError(0x6Eu);
  }
  return v9;
}

```

## disassembly

```asm
0x18007d678  mov     [rsp-8+arg_18], rbx
0x18007d67d  push    rbp
0x18007d67e  push    rsi
0x18007d67f  push    rdi
0x18007d680  push    r12
0x18007d682  push    r13
0x18007d684  push    r14
0x18007d686  push    r15
0x18007d688  lea     rbp, [rsp-1Fh]
0x18007d68d  sub     rsp, 0C0h
0x18007d694  mov     rax, cs:__security_cookie
0x18007d69b  xor     rax, rsp
0x18007d69e  mov     [rbp+4Fh+var_38], rax
0x18007d6a2  xor     r14d, r14d
0x18007d6a5  mov     [rbp+4Fh+var_88], rdx
0x18007d6a9  mov     bl, r9b
0x18007d6ac  mov     r13d, r8d
0x18007d6af  mov     rsi, rcx
0x18007d6b2  test    rdx, rdx
0x18007d6b5  jnz     loc_18007D78B
0x18007d6bb  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x18007d6c0  bts     r13d, 14h
0x18007d6c5  mov     [rsp+0F0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18007d6ca  xor     r9d, r9d; lpSecurityAttributes
0x18007d6cd  xor     r8d, r8d; dwShareMode
0x18007d6d0  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x18007d6d8  mov     edx, 40000000h; dwDesiredAccess
0x18007d6dd  call    cs:__imp_CreateFileW
0x18007d6e4  nop     dword ptr [rax+rax+00h]
0x18007d6e9  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007d6ed  mov     rdi, rax
0x18007d6f0  cmp     rax, r15
0x18007d6f3  jz      loc_18007D783
0x18007d6f9  mov     rcx, rax; hFile
0x18007d6fc  call    cs:__imp_GetFileType
0x18007d703  nop     dword ptr [rax+rax+00h]
0x18007d708  add     eax, 0FFFFFFFEh
0x18007d70b  lea     r12d, [r14+1]
0x18007d70f  cmp     eax, r12d
0x18007d712  ja      short loc_18007D783
0x18007d714  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18007d71b  jz      short loc_18007D760
0x18007d71d  mov     [rsp+0F0h+var_98], r14; void *
0x18007d722  lea     rax, aNull; "(NULL)"
0x18007d729  mov     [rsp+0F0h+var_A0], r14d; unsigned int
0x18007d72e  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18007d735  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007d73a  xor     edx, edx; unsigned __int16
0x18007d73c  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007d741  xor     r8d, r8d; int
0x18007d744  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007d749  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007d74e  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007d753  lea     ecx, [rdx+9]; int
0x18007d756  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007d75b  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007d760  mov     rcx, rdi; hObject
0x18007d763  call    cs:__imp_CloseHandle
0x18007d76a  nop     dword ptr [rax+rax+00h]
0x18007d76f  mov     ecx, 6Eh ; 'n'; dwErrCode
0x18007d774  mov     rdi, r15
0x18007d777  call    cs:__imp_SetLastError
0x18007d77e  nop     dword ptr [rax+rax+00h]
0x18007d783  mov     rax, rdi
0x18007d786  jmp     loc_18007DC5E
0x18007d78b  mov     rcx, [rdx+8]; pSecurityDescriptor
0x18007d78f  call    cs:__imp_IsValidSecurityDescriptor
0x18007d796  nop     dword ptr [rax+rax+00h]
0x18007d79b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007d79f  test    eax, eax
0x18007d7a1  jz      loc_18007DC5B
0x18007d7a7  xorps   xmm0, xmm0
0x18007d7aa  xor     eax, eax
0x18007d7ac  movups  [rbp+4Fh+FileInformation], xmm0
0x18007d7b0  mov     [rbp+4Fh+var_40], rax
0x18007d7b4  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x18007d7b9  cmp     eax, r15d
0x18007d7bc  jz      loc_18007DC5B
0x18007d7c2  lea     r12d, [r15+2]
0x18007d7c6  mov     edi, 400C0000h
0x18007d7cb  cmp     eax, r12d
0x18007d7ce  jnz     short loc_18007D7DA
0x18007d7d0  test    bl, bl
0x18007d7d2  mov     eax, 410C0000h
0x18007d7d7  cmovz   edi, eax
0x18007d7da  mov     eax, r13d
0x18007d7dd  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x18007d7e2  bts     eax, 14h
0x18007d7e6  mov     ebx, 2
0x18007d7eb  mov     [rsp+0F0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18007d7ef  xor     r9d, r9d; lpSecurityAttributes
0x18007d7f2  xor     r8d, r8d; dwShareMode
0x18007d7f5  mov     [rsp+0F0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18007d7f9  mov     edx, edi; dwDesiredAccess
0x18007d7fb  mov     rcx, rsi; lpFileName
0x18007d7fe  call    cs:__imp_CreateFileW
0x18007d805  nop     dword ptr [rax+rax+00h]
0x18007d80a  mov     r14, rax
0x18007d80d  cmp     rax, r15
0x18007d810  jz      short loc_18007D87F
0x18007d812  mov     rcx, rax; hFile
0x18007d815  call    cs:__imp_GetFileType
0x18007d81c  nop     dword ptr [rax+rax+00h]
0x18007d821  add     eax, 0FFFFFFFEh
0x18007d824  cmp     eax, r12d
0x18007d827  ja      short loc_18007D87F
0x18007d829  xor     eax, eax
0x18007d82b  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18007d831  jz      short loc_18007D875
0x18007d833  mov     [rsp+0F0h+var_98], rax; void *
0x18007d838  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18007d83f  mov     [rsp+0F0h+var_A0], eax; unsigned int
0x18007d843  lea     ecx, [rbx+7]; int
0x18007d846  lea     rax, aNull; "(NULL)"
0x18007d84d  xor     edx, edx; unsigned __int16
0x18007d84f  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007d854  xor     r8d, r8d; int
0x18007d857  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007d85c  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007d861  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007d866  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007d86b  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007d870  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007d875  mov     ebx, 6Eh ; 'n'
0x18007d87a  jmp     loc_18007DC10
0x18007d87f  mov     [rbp+4Fh+var_90], 0
0x18007d883  call    cs:__imp_GetLastError
0x18007d88a  nop     dword ptr [rax+rax+00h]
0x18007d88f  cmp     r14, r15
0x18007d892  jnz     loc_18007D9E5
0x18007d898  cmp     eax, 5
0x18007d89b  jz      short loc_18007D8A8
0x18007d89d  cmp     eax, 522h
0x18007d8a2  jnz     loc_18007DC56
0x18007d8a8  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18007d8b1  xor     r9d, r9d; lpSecurityAttributes
0x18007d8b4  mov     [rsp+0F0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18007d8bc  xor     r8d, r8d; dwShareMode
0x18007d8bf  mov     edx, 40000000h; dwDesiredAccess
0x18007d8c4  mov     [rsp+0F0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18007d8c8  mov     rcx, rsi; lpFileName
0x18007d8cb  mov     [rbp+4Fh+var_90], r12b
0x18007d8cf  call    cs:__imp_CreateFileW
0x18007d8d6  nop     dword ptr [rax+rax+00h]
0x18007d8db  mov     r14, rax
0x18007d8de  cmp     rax, r15
0x18007d8e1  jz      loc_18007D9DC
0x18007d8e7  mov     r9d, 18h; dwBufferSize
0x18007d8ed  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x18007d8f1  mov     rcx, rax; hFile
0x18007d8f4  lea     edx, [r9-6]; FileInformationClass
0x18007d8f8  call    cs:__imp_GetFileInformationByHandleEx
0x18007d8ff  nop     dword ptr [rax+rax+00h]
0x18007d904  test    eax, eax
0x18007d906  jnz     short loc_18007D96B
0x18007d908  call    cs:__imp_GetLastError
0x18007d90f  nop     dword ptr [rax+rax+00h]
0x18007d914  xor     edi, edi
0x18007d916  mov     ebx, eax
0x18007d918  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18007d91e  jz      loc_18007DC0C
0x18007d924  mov     [rsp+0F0h+var_98], rdi; void *
0x18007d929  lea     rax, aNull; "(NULL)"
0x18007d930  mov     [rsp+0F0h+var_A0], edi; unsigned int
0x18007d934  lea     r9, aErrorGetCreate; "Error: Get created file info failed: %s"
0x18007d93b  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007d940  lea     ecx, [rdi+9]; int
0x18007d943  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007d948  xor     edx, edx; unsigned __int16
0x18007d94a  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007d94f  xor     r8d, r8d; int
0x18007d952  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007d957  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007d95c  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007d961  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007d966  jmp     loc_18007DC0C
0x18007d96b  mov     rcx, r14; hFile
0x18007d96e  call    cs:__imp_GetFileType
0x18007d975  nop     dword ptr [rax+rax+00h]
0x18007d97a  add     eax, 0FFFFFFFEh
0x18007d97d  cmp     eax, r12d
0x18007d980  ja      short loc_18007D9EF
0x18007d982  xor     eax, eax
0x18007d984  mov     ebx, 6Eh ; 'n'
0x18007d989  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18007d98f  jz      loc_18007DC10
0x18007d995  mov     [rsp+0F0h+var_98], rax; void *
0x18007d99a  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18007d9a1  mov     [rsp+0F0h+var_A0], eax; unsigned int
0x18007d9a5  lea     ecx, [rbx-65h]; int
0x18007d9a8  lea     rax, aNull; "(NULL)"
0x18007d9af  xor     edx, edx; unsigned __int16
0x18007d9b1  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007d9b6  xor     r8d, r8d; int
0x18007d9b9  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007d9be  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007d9c3  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007d9c8  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007d9cd  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007d9d2  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007d9d7  jmp     loc_18007DC10
0x18007d9dc  cmp     r14, r15
0x18007d9df  jz      loc_18007DC56
0x18007d9e5  cmp     [rbp+4Fh+var_90], 0
0x18007d9e9  jz      loc_18007DB6C
0x18007d9ef  mov     dl, r12b; bool
0x18007d9f2  lea     rcx, [rbp+4Fh+var_80]; this
0x18007d9f6  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18007d9fb  mov     rcx, r14; hObject
0x18007d9fe  call    cs:__imp_CloseHandle
0x18007da05  nop     dword ptr [rax+rax+00h]
0x18007da0a  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18007da13  xor     r9d, r9d; lpSecurityAttributes
0x18007da16  mov     [rsp+0F0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18007da1e  xor     r8d, r8d; dwShareMode
0x18007da21  mov     edx, edi; dwDesiredAccess
0x18007da23  mov     [rsp+0F0h+dwCreationDisposition], 4; dwCreationDisposition
0x18007da2b  mov     rcx, rsi; lpFileName
0x18007da2e  call    cs:__imp_CreateFileW
0x18007da35  nop     dword ptr [rax+rax+00h]
0x18007da3a  mov     r14, rax
0x18007da3d  cmp     rax, r15
0x18007da40  jz      loc_18007DB5A
0x18007da46  xor     eax, eax
0x18007da48  lea     r8, [rbp+4Fh+Buf2]; lpFileInformation
0x18007da4c  xorps   xmm0, xmm0
0x18007da4f  mov     [rbp+4Fh+var_58], rax
0x18007da53  mov     rcx, r14; hFile
0x18007da56  movups  [rbp+4Fh+Buf2], xmm0
0x18007da5a  lea     r9d, [rax+18h]; dwBufferSize
0x18007da5e  lea     edx, [rax+12h]; FileInformationClass
0x18007da61  call    cs:__imp_GetFileInformationByHandleEx
0x18007da68  nop     dword ptr [rax+rax+00h]
0x18007da6d  xor     edi, edi
0x18007da6f  test    eax, eax
0x18007da71  jnz     short loc_18007DAD4
0x18007da73  call    cs:__imp_GetLastError
0x18007da7a  nop     dword ptr [rax+rax+00h]
0x18007da7f  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18007da85  mov     ebx, eax
0x18007da87  jz      short loc_18007DACB
0x18007da89  mov     [rsp+0F0h+var_98], rdi; void *
0x18007da8e  lea     rax, aNull; "(NULL)"
0x18007da95  mov     [rsp+0F0h+var_A0], edi; unsigned int
0x18007da99  lea     r9, aErrorGetOpened; "Error: Get opened file info failed: %s"
0x18007daa0  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007daa5  lea     ecx, [rdi+9]; int
0x18007daa8  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007daad  xor     edx, edx; unsigned __int16
0x18007daaf  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007dab4  xor     r8d, r8d; int
0x18007dab7  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007dabc  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007dac1  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007dac6  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007dacb  lea     rcx, [rbp+4Fh+var_80]
0x18007dacf  jmp     loc_18007DC07
0x18007dad4  mov     r8d, 18h; Size
0x18007dada  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x18007dade  lea     rcx, [rbp+4Fh+FileInformation]; Buf1
0x18007dae2  call    memcmp_0
0x18007dae7  test    eax, eax
0x18007dae9  jz      short loc_18007DB48
0x18007daeb  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18007daf1  mov     ebx, 6Eh ; 'n'
0x18007daf6  jz      short loc_18007DB3A
0x18007daf8  mov     [rsp+0F0h+var_98], rdi; void *
0x18007dafd  lea     rax, aNull; "(NULL)"
0x18007db04  mov     [rsp+0F0h+var_A0], edi; unsigned int
0x18007db08  lea     r9, aErrorTheFileWa; "Error: The file was replaced to another"...
0x18007db0f  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007db14  lea     ecx, [rbx-65h]; int
0x18007db17  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007db1c  xor     edx, edx; unsigned __int16
0x18007db1e  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007db23  xor     r8d, r8d; int
0x18007db26  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007db2b  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007db30  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007db35  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007db3a  lea     rcx, [rbp+4Fh+var_80]; this
0x18007db3e  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18007db43  jmp     loc_18007DC10
0x18007db48  mov     edx, r13d; dwFileAttributes
0x18007db4b  mov     rcx, rsi; lpFileName
0x18007db4e  call    cs:__imp_SetFileAttributesW
0x18007db55  nop     dword ptr [rax+rax+00h]
0x18007db5a  lea     rcx, [rbp+4Fh+var_80]; this
0x18007db5e  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18007db63  cmp     r14, r15
0x18007db66  jz      loc_18007DC56
0x18007db6c  mov     edx, [rbp+4Fh+arg_20]
0x18007db6f  lea     rcx, [rbp+4Fh+var_70]; this
0x18007db73  shr     edx, 3
0x18007db76  and     dl, r12b; bool
0x18007db79  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18007db7e  mov     dl, r12b
0x18007db81  mov     ecx, r12d
0x18007db84  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x18007db89  mov     r13, [rbp+4Fh+var_88]
  ... truncated ...
```
