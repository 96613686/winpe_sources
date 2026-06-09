# MsiCreateFileWithUserAccessCheck(ushort const *,_SECURITY_ATTRIBUTES *,ulong,bool,ielfEnum)

- ea: `0x18007f42c`
- end: `0x18007f9b7`
- name: `?MsiCreateFileWithUserAccessCheck@@YAPEAXPEBGPEAU_SECURITY_ATTRIBUTES@@K_NW4ielfEnum@@@Z`
- size: `1419`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007f080`
- `0x180081b34`

## callees

- `0x180024f9c`
- `0x180025904`
- `0x180025a18`
- `0x180068680`
- `0x18007ccec`
- `0x18007d8cc`
- `0x18007f42c`
- `0x18011d2c4`
- `0x18025ab06`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x18007f527`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18007f527`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007f672`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007f7bd`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007f672`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18007f7bd`
- `KERNEL32!CloseHandle` at `0x18007f507`
- `KERNEL32!CloseHandle` at `0x18007f766`
- `KERNEL32!CloseHandle` at `0x18007f951`
- `KERNEL32!CloseHandle` at `0x18007f507`
- `KERNEL32!CloseHandle` at `0x18007f766`
- `KERNEL32!CloseHandle` at `0x18007f951`
- `KERNEL32!GetLastError` at `0x18007f609`
- `KERNEL32!GetLastError` at `0x18007f67c`
- `KERNEL32!GetLastError` at `0x18007f7c9`
- `KERNEL32!GetLastError` at `0x18007f927`
- `KERNEL32!GetLastError` at `0x18007f609`
- `KERNEL32!GetLastError` at `0x18007f67c`
- `KERNEL32!GetLastError` at `0x18007f7c9`
- `KERNEL32!GetLastError` at `0x18007f927`
- `KERNEL32!SetLastError` at `0x18007f515`
- `KERNEL32!SetLastError` at `0x18007f95c`
- `KERNEL32!SetLastError` at `0x18007f515`
- `KERNEL32!SetLastError` at `0x18007f95c`
- `KERNEL32!CreateFileW` at `0x18007f491`
- `KERNEL32!CreateFileW` at `0x18007f590`
- `KERNEL32!CreateFileW` at `0x18007f64f`
- `KERNEL32!CreateFileW` at `0x18007f790`
- `KERNEL32!CreateFileW` at `0x18007f491`
- `KERNEL32!CreateFileW` at `0x18007f590`
- `KERNEL32!CreateFileW` at `0x18007f64f`
- `KERNEL32!CreateFileW` at `0x18007f790`
- `KERNEL32!GetFileType` at `0x18007f4a6`
- `KERNEL32!GetFileType` at `0x18007f5a1`
- `KERNEL32!GetFileType` at `0x18007f6dc`
- `KERNEL32!GetFileType` at `0x18007f4a6`
- `KERNEL32!GetFileType` at `0x18007f5a1`
- `KERNEL32!GetFileType` at `0x18007f6dc`
- `KERNEL32!SetFileAttributesW` at `0x18007f89e`
- `KERNEL32!SetFileAttributesW` at `0x18007f89e`
- `USER32!SetUserObjectSecurity` at `0x18007f91d`
- `USER32!SetUserObjectSecurity` at `0x18007f91d`

## string_xrefs

- `0x18007f4d2`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18007f5be`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18007f702`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18007f7e9`: `Error: Get opened file info failed: %s`
- `0x18007f6a2`: `Error: Get created file info failed: %s`
- `0x18007f858`: `Error: The file was replaced to another file, hence failing to open: %s`

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
0x18007f42c  mov     [rsp-8+arg_18], rbx
0x18007f431  push    rbp
0x18007f432  push    rsi
0x18007f433  push    rdi
0x18007f434  push    r12
0x18007f436  push    r13
0x18007f438  push    r14
0x18007f43a  push    r15
0x18007f43c  lea     rbp, [rsp-1Fh]
0x18007f441  sub     rsp, 0C0h
0x18007f448  mov     rax, cs:__security_cookie
0x18007f44f  xor     rax, rsp
0x18007f452  mov     [rbp+4Fh+var_38], rax
0x18007f456  xor     r14d, r14d
0x18007f459  mov     [rbp+4Fh+var_88], rdx
0x18007f45d  mov     bl, r9b
0x18007f460  mov     r13d, r8d
0x18007f463  mov     rsi, rcx
0x18007f466  test    rdx, rdx
0x18007f469  jnz     loc_18007F523
0x18007f46f  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x18007f474  bts     r13d, 14h
0x18007f479  mov     [rsp+0F0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18007f47e  xor     r9d, r9d; lpSecurityAttributes
0x18007f481  xor     r8d, r8d; dwShareMode
0x18007f484  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x18007f48c  mov     edx, 40000000h; dwDesiredAccess
0x18007f491  call    cs:__imp_CreateFileW
0x18007f497  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007f49b  mov     rdi, rax
0x18007f49e  cmp     rax, r15
0x18007f4a1  jz      short loc_18007F51B
0x18007f4a3  mov     rcx, rax; hFile
0x18007f4a6  call    cs:__imp_GetFileType
0x18007f4ac  add     eax, 0FFFFFFFEh
0x18007f4af  lea     r12d, [r14+1]
0x18007f4b3  cmp     eax, r12d
0x18007f4b6  ja      short loc_18007F51B
0x18007f4b8  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18007f4bf  jz      short loc_18007F504
0x18007f4c1  mov     [rsp+0F0h+var_98], r14; void *
0x18007f4c6  lea     rax, aNull; "(NULL)"
0x18007f4cd  mov     [rsp+0F0h+var_A0], r14d; unsigned int
0x18007f4d2  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18007f4d9  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007f4de  xor     edx, edx; unsigned __int16
0x18007f4e0  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007f4e5  xor     r8d, r8d; int
0x18007f4e8  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007f4ed  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007f4f2  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007f4f7  lea     ecx, [rdx+9]; int
0x18007f4fa  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007f4ff  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007f504  mov     rcx, rdi; hObject
0x18007f507  call    cs:__imp_CloseHandle
0x18007f50d  mov     ecx, 6Eh ; 'n'; dwErrCode
0x18007f512  mov     rdi, r15
0x18007f515  call    cs:__imp_SetLastError
0x18007f51b  mov     rax, rdi
0x18007f51e  jmp     loc_18007F990
0x18007f523  mov     rcx, [rdx+8]; pSecurityDescriptor
0x18007f527  call    cs:__imp_IsValidSecurityDescriptor
0x18007f52d  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007f531  test    eax, eax
0x18007f533  jz      loc_18007F98D
0x18007f539  xorps   xmm0, xmm0
0x18007f53c  xor     eax, eax
0x18007f53e  movups  [rbp+4Fh+FileInformation], xmm0
0x18007f542  mov     [rbp+4Fh+var_40], rax
0x18007f546  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x18007f54b  cmp     eax, r15d
0x18007f54e  jz      loc_18007F98D
0x18007f554  lea     r12d, [r15+2]
0x18007f558  mov     edi, 400C0000h
0x18007f55d  cmp     eax, r12d
0x18007f560  jnz     short loc_18007F56C
0x18007f562  test    bl, bl
0x18007f564  mov     eax, 410C0000h
0x18007f569  cmovz   edi, eax
0x18007f56c  mov     eax, r13d
0x18007f56f  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x18007f574  bts     eax, 14h
0x18007f578  mov     ebx, 2
0x18007f57d  mov     [rsp+0F0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18007f581  xor     r9d, r9d; lpSecurityAttributes
0x18007f584  xor     r8d, r8d; dwShareMode
0x18007f587  mov     [rsp+0F0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18007f58b  mov     edx, edi; dwDesiredAccess
0x18007f58d  mov     rcx, rsi; lpFileName
0x18007f590  call    cs:__imp_CreateFileW
0x18007f596  mov     r14, rax
0x18007f599  cmp     rax, r15
0x18007f59c  jz      short loc_18007F605
0x18007f59e  mov     rcx, rax; hFile
0x18007f5a1  call    cs:__imp_GetFileType
0x18007f5a7  add     eax, 0FFFFFFFEh
0x18007f5aa  cmp     eax, r12d
0x18007f5ad  ja      short loc_18007F605
0x18007f5af  xor     eax, eax
0x18007f5b1  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18007f5b7  jz      short loc_18007F5FB
0x18007f5b9  mov     [rsp+0F0h+var_98], rax; void *
0x18007f5be  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18007f5c5  mov     [rsp+0F0h+var_A0], eax; unsigned int
0x18007f5c9  lea     ecx, [rbx+7]; int
0x18007f5cc  lea     rax, aNull; "(NULL)"
0x18007f5d3  xor     edx, edx; unsigned __int16
0x18007f5d5  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007f5da  xor     r8d, r8d; int
0x18007f5dd  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007f5e2  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007f5e7  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007f5ec  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007f5f1  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007f5f6  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007f5fb  mov     ebx, 6Eh ; 'n'
0x18007f600  jmp     loc_18007F94E
0x18007f605  mov     [rbp+4Fh+var_90], 0
0x18007f609  call    cs:__imp_GetLastError
0x18007f60f  cmp     r14, r15
0x18007f612  jnz     loc_18007F74D
0x18007f618  cmp     eax, 5
0x18007f61b  jz      short loc_18007F628
0x18007f61d  cmp     eax, 522h
0x18007f622  jnz     loc_18007F988
0x18007f628  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18007f631  xor     r9d, r9d; lpSecurityAttributes
0x18007f634  mov     [rsp+0F0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18007f63c  xor     r8d, r8d; dwShareMode
0x18007f63f  mov     edx, 40000000h; dwDesiredAccess
0x18007f644  mov     [rsp+0F0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18007f648  mov     rcx, rsi; lpFileName
0x18007f64b  mov     [rbp+4Fh+var_90], r12b
0x18007f64f  call    cs:__imp_CreateFileW
0x18007f655  mov     r14, rax
0x18007f658  cmp     rax, r15
0x18007f65b  jz      loc_18007F744
0x18007f661  mov     r9d, 18h; dwBufferSize
0x18007f667  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x18007f66b  mov     rcx, rax; hFile
0x18007f66e  lea     edx, [r9-6]; FileInformationClass
0x18007f672  call    cs:__imp_GetFileInformationByHandleEx
0x18007f678  test    eax, eax
0x18007f67a  jnz     short loc_18007F6D9
0x18007f67c  call    cs:__imp_GetLastError
0x18007f682  xor     edi, edi
0x18007f684  mov     ebx, eax
0x18007f686  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18007f68c  jz      loc_18007F94A
0x18007f692  mov     [rsp+0F0h+var_98], rdi; void *
0x18007f697  lea     rax, aNull; "(NULL)"
0x18007f69e  mov     [rsp+0F0h+var_A0], edi; unsigned int
0x18007f6a2  lea     r9, aErrorGetCreate; "Error: Get created file info failed: %s"
0x18007f6a9  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007f6ae  lea     ecx, [rdi+9]; int
0x18007f6b1  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007f6b6  xor     edx, edx; unsigned __int16
0x18007f6b8  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007f6bd  xor     r8d, r8d; int
0x18007f6c0  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007f6c5  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007f6ca  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007f6cf  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007f6d4  jmp     loc_18007F94A
0x18007f6d9  mov     rcx, r14; hFile
0x18007f6dc  call    cs:__imp_GetFileType
0x18007f6e2  add     eax, 0FFFFFFFEh
0x18007f6e5  cmp     eax, r12d
0x18007f6e8  ja      short loc_18007F757
0x18007f6ea  xor     eax, eax
0x18007f6ec  mov     ebx, 6Eh ; 'n'
0x18007f6f1  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18007f6f7  jz      loc_18007F94E
0x18007f6fd  mov     [rsp+0F0h+var_98], rax; void *
0x18007f702  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18007f709  mov     [rsp+0F0h+var_A0], eax; unsigned int
0x18007f70d  lea     ecx, [rbx-65h]; int
0x18007f710  lea     rax, aNull; "(NULL)"
0x18007f717  xor     edx, edx; unsigned __int16
0x18007f719  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007f71e  xor     r8d, r8d; int
0x18007f721  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007f726  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007f72b  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007f730  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007f735  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007f73a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007f73f  jmp     loc_18007F94E
0x18007f744  cmp     r14, r15
0x18007f747  jz      loc_18007F988
0x18007f74d  cmp     [rbp+4Fh+var_90], 0
0x18007f751  jz      loc_18007F8B6
0x18007f757  mov     dl, r12b; bool
0x18007f75a  lea     rcx, [rbp+4Fh+var_80]; this
0x18007f75e  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18007f763  mov     rcx, r14; hObject
0x18007f766  call    cs:__imp_CloseHandle
0x18007f76c  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18007f775  xor     r9d, r9d; lpSecurityAttributes
0x18007f778  mov     [rsp+0F0h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18007f780  xor     r8d, r8d; dwShareMode
0x18007f783  mov     edx, edi; dwDesiredAccess
0x18007f785  mov     [rsp+0F0h+dwCreationDisposition], 4; dwCreationDisposition
0x18007f78d  mov     rcx, rsi; lpFileName
0x18007f790  call    cs:__imp_CreateFileW
0x18007f796  mov     r14, rax
0x18007f799  cmp     rax, r15
0x18007f79c  jz      loc_18007F8A4
0x18007f7a2  xor     eax, eax
0x18007f7a4  lea     r8, [rbp+4Fh+Buf2]; lpFileInformation
0x18007f7a8  xorps   xmm0, xmm0
0x18007f7ab  mov     [rbp+4Fh+var_58], rax
0x18007f7af  mov     rcx, r14; hFile
0x18007f7b2  movups  [rbp+4Fh+Buf2], xmm0
0x18007f7b6  lea     r9d, [rax+18h]; dwBufferSize
0x18007f7ba  lea     edx, [rax+12h]; FileInformationClass
0x18007f7bd  call    cs:__imp_GetFileInformationByHandleEx
0x18007f7c3  xor     edi, edi
0x18007f7c5  test    eax, eax
0x18007f7c7  jnz     short loc_18007F824
0x18007f7c9  call    cs:__imp_GetLastError
0x18007f7cf  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18007f7d5  mov     ebx, eax
0x18007f7d7  jz      short loc_18007F81B
0x18007f7d9  mov     [rsp+0F0h+var_98], rdi; void *
0x18007f7de  lea     rax, aNull; "(NULL)"
0x18007f7e5  mov     [rsp+0F0h+var_A0], edi; unsigned int
0x18007f7e9  lea     r9, aErrorGetOpened; "Error: Get opened file info failed: %s"
0x18007f7f0  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007f7f5  lea     ecx, [rdi+9]; int
0x18007f7f8  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007f7fd  xor     edx, edx; unsigned __int16
0x18007f7ff  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007f804  xor     r8d, r8d; int
0x18007f807  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007f80c  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007f811  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007f816  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007f81b  lea     rcx, [rbp+4Fh+var_80]
0x18007f81f  jmp     loc_18007F945
0x18007f824  mov     r8d, 18h; Size
0x18007f82a  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x18007f82e  lea     rcx, [rbp+4Fh+FileInformation]; Buf1
0x18007f832  call    memcmp_0
0x18007f837  test    eax, eax
0x18007f839  jz      short loc_18007F898
0x18007f83b  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18007f841  mov     ebx, 6Eh ; 'n'
0x18007f846  jz      short loc_18007F88A
0x18007f848  mov     [rsp+0F0h+var_98], rdi; void *
0x18007f84d  lea     rax, aNull; "(NULL)"
0x18007f854  mov     [rsp+0F0h+var_A0], edi; unsigned int
0x18007f858  lea     r9, aErrorTheFileWa; "Error: The file was replaced to another"...
0x18007f85f  mov     [rsp+0F0h+var_A8], rax; unsigned __int16 *
0x18007f864  lea     ecx, [rbx-65h]; int
0x18007f867  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x18007f86c  xor     edx, edx; unsigned __int16
0x18007f86e  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x18007f873  xor     r8d, r8d; int
0x18007f876  mov     [rsp+0F0h+hTemplateFile], rax; unsigned __int16 *
0x18007f87b  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18007f880  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; unsigned __int16 *
0x18007f885  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18007f88a  lea     rcx, [rbp+4Fh+var_80]; this
0x18007f88e  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18007f893  jmp     loc_18007F94E
0x18007f898  mov     edx, r13d; dwFileAttributes
0x18007f89b  mov     rcx, rsi; lpFileName
0x18007f89e  call    cs:__imp_SetFileAttributesW
0x18007f8a4  lea     rcx, [rbp+4Fh+var_80]; this
0x18007f8a8  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18007f8ad  cmp     r14, r15
0x18007f8b0  jz      loc_18007F988
0x18007f8b6  mov     edx, [rbp+4Fh+arg_20]
0x18007f8b9  lea     rcx, [rbp+4Fh+var_70]; this
0x18007f8bd  shr     edx, 3
0x18007f8c0  and     dl, r12b; bool
0x18007f8c3  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18007f8c8  mov     dl, r12b
0x18007f8cb  mov     ecx, r12d
0x18007f8ce  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x18007f8d3  mov     r13, [rbp+4Fh+var_88]
0x18007f8d7  test    al, al
0x18007f8d9  mov     esi, ebx
0x18007f8db  cmovnz  esi, r12d
0x18007f8df  mov     [rbp+4Fh+var_80], esi
0x18007f8e2  mov     rcx, [r13+8]; pSecurityDescriptor
0x18007f8e6  call    ?GetSecurityInformation@@YAKPEAX@Z; GetSecurityInformation(void *)
0x18007f8eb  mov     [rbp+4Fh+pSIRequested], eax
0x18007f8ee  mov     edi, ebx
0x18007f8f0  mov     dword ptr [rbp+4Fh+var_88], ebx
0x18007f8f3  test    al, 8
0x18007f8f5  jz      short loc_18007F90F
0x18007f8f7  mov     dl, r12b
0x18007f8fa  xor     ecx, ecx
0x18007f8fc  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x18007f901  test    al, al
0x18007f903  jz      short loc_18007F90F
0x18007f905  xor     edi, edi
  ... truncated ...
```
