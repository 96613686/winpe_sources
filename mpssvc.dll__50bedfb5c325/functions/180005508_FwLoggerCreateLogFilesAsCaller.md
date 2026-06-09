# FwLoggerCreateLogFilesAsCaller

- ea: `0x180005508`
- end: `0x180005aad`
- name: `FwLoggerCreateLogFilesAsCaller`
- size: `1445`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800068fc`
- `0x1800993a4`

## callees

- `0x180005508`
- `0x18000a710`
- `0x1800192e0`
- `0x1800729c0`
- `0x1800749bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800057fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005984`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800057fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005984`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005651`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005651`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180005854`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180005854`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000569a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000569a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005729`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000594b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005729`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000594b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180005719`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180005719`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800058b0`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800059e6`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800058b0`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800059e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a4c`
- `RPCRT4!RpcImpersonateClient` at `0x180005582`
- `RPCRT4!RpcImpersonateClient` at `0x180005582`
- `RPCRT4!RpcRevertToSelf` at `0x180005a37`
- `RPCRT4!RpcRevertToSelf` at `0x180005a37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005785`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180005785`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x180005614`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x180005614`
- `fwbase!FwExpandEnvironmentStrings` at `0x1800055ce`
- `fwbase!FwExpandEnvironmentStrings` at `0x1800055ce`
- `fwbase!FwCreateDirectory` at `0x18000573d`
- `fwbase!FwCreateDirectory` at `0x18000573d`
- `fwbase!FwStringBuild` at `0x180005911`
- `fwbase!FwStringBuild` at `0x180005911`
- `fwbase!FwStringCopy` at `0x1800056df`
- `fwbase!FwStringCopy` at `0x1800056df`
- `fwbase!FwFree` at `0x180005a5c`
- `fwbase!FwFree` at `0x180005a6c`
- `fwbase!FwFree` at `0x180005a7c`
- `fwbase!FwFree` at `0x180005a5c`
- `fwbase!FwFree` at `0x180005a6c`
- `fwbase!FwFree` at `0x180005a7c`

## pseudocode

```c
__int64 __fastcall FwLoggerCreateLogFilesAsCaller(__int64 a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  int Directory; // eax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  HANDLE FileW; // rax
  void *v11; // rdi
  signed int v12; // eax
  DWORD FileType; // ebx
  signed int v14; // eax
  HANDLE v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  LPCWSTR pszPath; // [rsp+40h] [rbp-30h] BYREF
  LPWSTR v20; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-18h] BYREF

  SecurityDescriptor = 0;
  pszPath = 0;
  lpFileName = 0;
  v20 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids);
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    Directory = FwExpandEnvironmentStrings(a1, &pszPath);
    v3 = Directory;
    if ( Directory < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 54;
      goto LABEL_12;
    }
    if ( (unsigned __int8)IsPathIsDirectoryWPresent() )
    {
      if ( PathIsDirectoryW(pszPath) )
      {
        v7 = 2147942487LL;
        v3 = -2147024809;
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 55;
        goto LABEL_77;
      }
    }
    else
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW - 1 <= 0xFFFFFFFD && (FileAttributesW & 0x10) != 0 )
      {
        v7 = 2147942487LL;
        v3 = -2147024809;
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 56;
        goto LABEL_77;
      }
    }
    if ( PathIsRelativeW(pszPath) )
    {
      v7 = 2147942487LL;
      v3 = -2147024809;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 57;
      goto LABEL_77;
    }
    Directory = FwStringCopy(pszPath, &v20);
    v3 = Directory;
    if ( Directory < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 58;
      goto LABEL_12;
    }
    PathRemoveFileSpecW(v20);
    if ( !PathFileExistsW(v20) )
    {
      Directory = FwCreateDirectory(v20);
      v3 = Directory;
      if ( Directory < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 59;
        goto LABEL_12;
      }
    }
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:PAI(A;;FA;;;S-1-5-80-3088073201-1464728630-1879813800-1107566885-823218052)(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;NO)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 60;
      goto LABEL_76;
    }
    FileW = CreateFileW(pszPath, 0x80000000, 3u, 0, 4u, 0x80u, 0);
    v11 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v12 = GetLastError();
      v3 = v12;
      if ( v12 > 0 )
        v3 = (unsigned __int16)v12 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 61;
      goto LABEL_76;
    }
    FileType = GetFileType(FileW);
    CloseHandle(v11);
    if ( FileType != 1 )
    {
      v7 = 2147942487LL;
      v3 = -2147024809;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 62;
      goto LABEL_77;
    }
    if ( !SetFileSecurityW(pszPath, 4u, SecurityDescriptor) )
    {
      v14 = GetLastError();
      v3 = v14;
      if ( v14 > 0 )
        v3 = (unsigned __int16)v14 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 63;
      goto LABEL_76;
    }
    Directory = FwStringBuild(&lpFileName, pszPath, L".old", 0);
    v3 = Directory;
    if ( Directory < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 64;
LABEL_12:
      v7 = (unsigned int)Directory;
LABEL_77:
      WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, v7);
LABEL_78:
      RpcRevertToSelf();
      goto LABEL_79;
    }
    if ( !PathFileExistsW(lpFileName) )
    {
      v15 = CreateFileW(lpFileName, 0x80000000, 3u, 0, 4u, 0x80u, 0);
      if ( v15 == (HANDLE)-1LL )
      {
        v16 = GetLastError();
        v3 = v16;
        if ( v16 > 0 )
          v3 = (unsigned __int16)v16 | 0x80070000;
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 65;
        goto LABEL_76;
      }
      CloseHandle(v15);
    }
    if ( SetFileSecurityW(lpFileName, 4u, SecurityDescriptor) )
      goto LABEL_78;
    v17 = GetLastError();
    v3 = v17;
    if ( v17 > 0 )
      v3 = (unsigned __int16)v17 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_78;
    v6 = 66;
LABEL_76:
    v7 = v3;
    goto LABEL_77;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      53,
      WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids,
      (unsigned int)v2);
LABEL_79:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  FwFree(pszPath);
  FwFree(v20);
  FwFree(lpFileName);
  return v3;
}

```

## disassembly

```asm
0x180005508  mov     [rsp-18h+arg_8], rbx
0x18000550d  mov     [rsp-18h+arg_10], rdi
0x180005512  push    rbp
0x180005513  push    r14
0x180005515  push    r15
0x180005517  mov     rbp, rsp
0x18000551a  sub     rsp, 70h
0x18000551e  mov     rax, cs:__security_cookie
0x180005525  xor     rax, rsp
0x180005528  mov     [rbp+var_10], rax
0x18000552c  mov     rdi, rcx
0x18000552f  mov     [rbp+SecurityDescriptor], 0
0x180005537  mov     [rbp+pszPath], 0
0x18000553f  mov     [rbp+lpFileName], 0
0x180005547  mov     [rbp+var_28], 0
0x18000554f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005556  lea     r14, WPP_GLOBAL_Control
0x18000555d  lea     r15, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x180005564  cmp     rcx, r14
0x180005567  jz      short loc_180005580
0x180005569  test    byte ptr [rcx+1Ch], 8
0x18000556d  jz      short loc_180005580
0x18000556f  mov     rcx, [rcx+10h]
0x180005573  mov     edx, 34h ; '4'
0x180005578  mov     r8, r15
0x18000557b  call    WPP_SF_
0x180005580  xor     ecx, ecx; BindingHandle
0x180005582  call    cs:__imp_RpcImpersonateClient
0x180005589  nop     dword ptr [rax+rax+00h]
0x18000558e  mov     ebx, eax
0x180005590  test    eax, eax
0x180005592  jns     short loc_1800055C7
0x180005594  mov     rcx, cs:WPP_GLOBAL_Control
0x18000559b  cmp     rcx, r14
0x18000559e  jz      loc_180005A43
0x1800055a4  test    byte ptr [rcx+1Ch], 1
0x1800055a8  jz      loc_180005A43
0x1800055ae  mov     rcx, [rcx+10h]
0x1800055b2  mov     edx, 35h ; '5'
0x1800055b7  mov     r9d, eax
0x1800055ba  mov     r8, r15
0x1800055bd  call    WPP_SF_d
0x1800055c2  jmp     loc_180005A43
0x1800055c7  lea     rdx, [rbp+pszPath]
0x1800055cb  mov     rcx, rdi
0x1800055ce  call    cs:__imp_FwExpandEnvironmentStrings
0x1800055d5  nop     dword ptr [rax+rax+00h]
0x1800055da  mov     ebx, eax
0x1800055dc  test    eax, eax
0x1800055de  jns     short loc_180005607
0x1800055e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e7  cmp     rcx, r14
0x1800055ea  jz      loc_180005A37
0x1800055f0  test    byte ptr [rcx+1Ch], 1
0x1800055f4  jz      loc_180005A37
0x1800055fa  mov     edx, 36h ; '6'
0x1800055ff  mov     r9d, eax
0x180005602  jmp     loc_180005A2B
0x180005607  call    IsPathIsDirectoryWPresent
0x18000560c  mov     rcx, [rbp+pszPath]; lpFileName
0x180005610  test    al, al
0x180005612  jz      short loc_180005651
0x180005614  call    cs:__imp_PathIsDirectoryW
0x18000561b  nop     dword ptr [rax+rax+00h]
0x180005620  test    eax, eax
0x180005622  jz      short loc_180005696
0x180005624  mov     r9d, 80070057h
0x18000562a  mov     ebx, r9d
0x18000562d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005634  cmp     rcx, r14
0x180005637  jz      loc_180005A37
0x18000563d  test    byte ptr [rcx+1Ch], 1
0x180005641  jz      loc_180005A37
0x180005647  mov     edx, 37h ; '7'
0x18000564c  jmp     loc_180005A2B
0x180005651  call    cs:__imp_GetFileAttributesW
0x180005658  nop     dword ptr [rax+rax+00h]
0x18000565d  lea     ecx, [rax-1]
0x180005660  cmp     ecx, 0FFFFFFFDh
0x180005663  ja      short loc_180005696
0x180005665  test    al, 10h
0x180005667  jz      short loc_180005696
0x180005669  mov     r9d, 80070057h
0x18000566f  mov     ebx, r9d
0x180005672  mov     rcx, cs:WPP_GLOBAL_Control
0x180005679  cmp     rcx, r14
0x18000567c  jz      loc_180005A37
0x180005682  test    byte ptr [rcx+1Ch], 1
0x180005686  jz      loc_180005A37
0x18000568c  mov     edx, 38h ; '8'
0x180005691  jmp     loc_180005A2B
0x180005696  mov     rcx, [rbp+pszPath]; pszPath
0x18000569a  call    cs:__imp_PathIsRelativeW
0x1800056a1  nop     dword ptr [rax+rax+00h]
0x1800056a6  test    eax, eax
0x1800056a8  jz      short loc_1800056D7
0x1800056aa  mov     r9d, 80070057h
0x1800056b0  mov     ebx, r9d
0x1800056b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056ba  cmp     rcx, r14
0x1800056bd  jz      loc_180005A37
0x1800056c3  test    byte ptr [rcx+1Ch], 1
0x1800056c7  jz      loc_180005A37
0x1800056cd  mov     edx, 39h ; '9'
0x1800056d2  jmp     loc_180005A2B
0x1800056d7  mov     rcx, [rbp+pszPath]
0x1800056db  lea     rdx, [rbp+var_28]
0x1800056df  call    cs:__imp_FwStringCopy
0x1800056e6  nop     dword ptr [rax+rax+00h]
0x1800056eb  mov     ebx, eax
0x1800056ed  test    eax, eax
0x1800056ef  jns     short loc_180005715
0x1800056f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056f8  cmp     rcx, r14
0x1800056fb  jz      loc_180005A37
0x180005701  test    byte ptr [rcx+1Ch], 1
0x180005705  jz      loc_180005A37
0x18000570b  mov     edx, 3Ah ; ':'
0x180005710  jmp     loc_1800055FF
0x180005715  mov     rcx, [rbp+var_28]; pszPath
0x180005719  call    cs:__imp_PathRemoveFileSpecW
0x180005720  nop     dword ptr [rax+rax+00h]
0x180005725  mov     rcx, [rbp+var_28]; pszPath
0x180005729  call    cs:__imp_PathFileExistsW
0x180005730  nop     dword ptr [rax+rax+00h]
0x180005735  test    eax, eax
0x180005737  jnz     short loc_180005773
0x180005739  mov     rcx, [rbp+var_28]
0x18000573d  call    cs:__imp_FwCreateDirectory
0x180005744  nop     dword ptr [rax+rax+00h]
0x180005749  mov     ebx, eax
0x18000574b  test    eax, eax
0x18000574d  jns     short loc_180005773
0x18000574f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005756  cmp     rcx, r14
0x180005759  jz      loc_180005A37
0x18000575f  test    byte ptr [rcx+1Ch], 1
0x180005763  jz      loc_180005A37
0x180005769  mov     edx, 3Bh ; ';'
0x18000576e  jmp     loc_1800055FF
0x180005773  xor     r9d, r9d; SecurityDescriptorSize
0x180005776  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000577a  lea     rcx, StringSecurityDescriptor; "D:PAI(A;;FA;;;S-1-5-80-3088073201-14647"...
0x180005781  lea     edx, [r9+1]; StringSDRevision
0x180005785  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000578c  nop     dword ptr [rax+rax+00h]
0x180005791  test    eax, eax
0x180005793  jnz     short loc_1800057D4
0x180005795  call    cs:__imp_GetLastError
0x18000579c  nop     dword ptr [rax+rax+00h]
0x1800057a1  mov     ebx, eax
0x1800057a3  test    eax, eax
0x1800057a5  jle     short loc_1800057B0
0x1800057a7  movzx   ebx, ax
0x1800057aa  or      ebx, 80070000h
0x1800057b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057b7  cmp     rcx, r14
0x1800057ba  jz      loc_180005A37
0x1800057c0  test    byte ptr [rcx+1Ch], 1
0x1800057c4  jz      loc_180005A37
0x1800057ca  mov     edx, 3Ch ; '<'
0x1800057cf  jmp     loc_180005A28
0x1800057d4  mov     rcx, [rbp+pszPath]; lpFileName
0x1800057d8  xor     r9d, r9d; lpSecurityAttributes
0x1800057db  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800057e4  mov     edx, 80000000h; dwDesiredAccess
0x1800057e9  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800057f1  mov     [rsp+70h+dwCreationDisposition], 4; dwCreationDisposition
0x1800057f9  lea     r8d, [r9+3]; dwShareMode
0x1800057fd  call    cs:__imp_CreateFileW
0x180005804  nop     dword ptr [rax+rax+00h]
0x180005809  mov     rdi, rax
0x18000580c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005810  jnz     short loc_180005851
0x180005812  call    cs:__imp_GetLastError
0x180005819  nop     dword ptr [rax+rax+00h]
0x18000581e  mov     ebx, eax
0x180005820  test    eax, eax
0x180005822  jle     short loc_18000582D
0x180005824  movzx   ebx, ax
0x180005827  or      ebx, 80070000h
0x18000582d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005834  cmp     rcx, r14
0x180005837  jz      loc_180005A37
0x18000583d  test    byte ptr [rcx+1Ch], 1
0x180005841  jz      loc_180005A37
0x180005847  mov     edx, 3Dh ; '='
0x18000584c  jmp     loc_180005A28
0x180005851  mov     rcx, rdi; hFile
0x180005854  call    cs:__imp_GetFileType
0x18000585b  nop     dword ptr [rax+rax+00h]
0x180005860  mov     rcx, rdi; hObject
0x180005863  mov     ebx, eax
0x180005865  call    cs:__imp_CloseHandle
0x18000586c  nop     dword ptr [rax+rax+00h]
0x180005871  cmp     ebx, 1
0x180005874  jz      short loc_1800058A3
0x180005876  mov     r9d, 80070057h
0x18000587c  mov     ebx, r9d
0x18000587f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005886  cmp     rcx, r14
0x180005889  jz      loc_180005A37
0x18000588f  test    byte ptr [rcx+1Ch], 1
0x180005893  jz      loc_180005A37
0x180005899  mov     edx, 3Eh ; '>'
0x18000589e  jmp     loc_180005A2B
0x1800058a3  mov     r8, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800058a7  mov     edx, 4; SecurityInformation
0x1800058ac  mov     rcx, [rbp+pszPath]; lpFileName
0x1800058b0  call    cs:__imp_SetFileSecurityW
0x1800058b7  nop     dword ptr [rax+rax+00h]
0x1800058bc  test    eax, eax
0x1800058be  jnz     short loc_1800058FF
0x1800058c0  call    cs:__imp_GetLastError
0x1800058c7  nop     dword ptr [rax+rax+00h]
0x1800058cc  mov     ebx, eax
0x1800058ce  test    eax, eax
0x1800058d0  jle     short loc_1800058DB
0x1800058d2  movzx   ebx, ax
0x1800058d5  or      ebx, 80070000h
0x1800058db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058e2  cmp     rcx, r14
0x1800058e5  jz      loc_180005A37
0x1800058eb  test    byte ptr [rcx+1Ch], 1
0x1800058ef  jz      loc_180005A37
0x1800058f5  mov     edx, 3Fh ; '?'
0x1800058fa  jmp     loc_180005A28
0x1800058ff  mov     rdx, [rbp+pszPath]
0x180005903  lea     r8, aOld; ".old"
0x18000590a  xor     r9d, r9d
0x18000590d  lea     rcx, [rbp+lpFileName]
0x180005911  call    cs:__imp_FwStringBuild
0x180005918  nop     dword ptr [rax+rax+00h]
0x18000591d  mov     ebx, eax
0x18000591f  test    eax, eax
0x180005921  jns     short loc_180005947
0x180005923  mov     rcx, cs:WPP_GLOBAL_Control
0x18000592a  cmp     rcx, r14
0x18000592d  jz      loc_180005A37
0x180005933  test    byte ptr [rcx+1Ch], 1
0x180005937  jz      loc_180005A37
0x18000593d  mov     edx, 40h ; '@'
0x180005942  jmp     loc_1800055FF
0x180005947  mov     rcx, [rbp+lpFileName]; pszPath
0x18000594b  call    cs:__imp_PathFileExistsW
0x180005952  nop     dword ptr [rax+rax+00h]
0x180005957  test    eax, eax
0x180005959  jnz     short loc_1800059D9
0x18000595b  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000595f  lea     r8d, [rax+3]; dwShareMode
0x180005963  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18000596c  xor     r9d, r9d; lpSecurityAttributes
0x18000596f  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180005977  mov     edx, 80000000h; dwDesiredAccess
0x18000597c  mov     [rsp+70h+dwCreationDisposition], 4; dwCreationDisposition
0x180005984  call    cs:__imp_CreateFileW
0x18000598b  nop     dword ptr [rax+rax+00h]
0x180005990  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005994  jnz     short loc_1800059CA
0x180005996  call    cs:__imp_GetLastError
0x18000599d  nop     dword ptr [rax+rax+00h]
0x1800059a2  mov     ebx, eax
0x1800059a4  test    eax, eax
0x1800059a6  jle     short loc_1800059B1
0x1800059a8  movzx   ebx, ax
0x1800059ab  or      ebx, 80070000h
0x1800059b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059b8  cmp     rcx, r14
0x1800059bb  jz      short loc_180005A37
0x1800059bd  test    byte ptr [rcx+1Ch], 1
0x1800059c1  jz      short loc_180005A37
0x1800059c3  mov     edx, 41h ; 'A'
0x1800059c8  jmp     short loc_180005A28
0x1800059ca  mov     rcx, rax; hObject
0x1800059cd  call    cs:__imp_CloseHandle
0x1800059d4  nop     dword ptr [rax+rax+00h]
0x1800059d9  mov     r8, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800059dd  mov     edx, 4; SecurityInformation
0x1800059e2  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800059e6  call    cs:__imp_SetFileSecurityW
0x1800059ed  nop     dword ptr [rax+rax+00h]
0x1800059f2  test    eax, eax
0x1800059f4  jnz     short loc_180005A37
0x1800059f6  call    cs:__imp_GetLastError
0x1800059fd  nop     dword ptr [rax+rax+00h]
0x180005a02  mov     ebx, eax
0x180005a04  test    eax, eax
0x180005a06  jle     short loc_180005A11
0x180005a08  movzx   ebx, ax
0x180005a0b  or      ebx, 80070000h
0x180005a11  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a18  cmp     rcx, r14
0x180005a1b  jz      short loc_180005A37
0x180005a1d  test    byte ptr [rcx+1Ch], 1
0x180005a21  jz      short loc_180005A37
0x180005a23  mov     edx, 42h ; 'B'
0x180005a28  mov     r9d, ebx
0x180005a2b  mov     rcx, [rcx+10h]
0x180005a2f  mov     r8, r15
0x180005a32  call    WPP_SF_d
  ... truncated ...
```
