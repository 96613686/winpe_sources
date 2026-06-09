# SaveHive

- ea: `0x14000496c`
- end: `0x140004ce7`
- name: `SaveHive`
- size: `891`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1400031f4`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002004`
- `0x140002090`
- `0x1400022dc`
- `0x140002b6c`
- `0x140002c20`
- `0x140002ce4`
- `0x140003068`
- `0x14000426c`
- `0x140004678`
- `0x14000496c`
- `0x14000d694`
- `0x14000e75c`
- `0x14000e798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004ae9`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004b19`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004bb2`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004be2`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004ae9`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004b19`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004bb2`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140004be2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004aaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004aaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004c9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004c9c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140004aff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140004bc8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140004c1e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140004aff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140004bc8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140004c1e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140004bfd`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140004bfd`

## pseudocode

```c
__int64 __fastcall SaveHive(unsigned int a1, PCNZWCH *a2)
{
  FILE *v4; // rax
  unsigned int v5; // edi
  DWORD v6; // r14d
  FILE *v7; // rax
  DWORD LastError; // ebx
  unsigned int v10; // esi
  WCHAR *v11; // r13
  __int64 v12; // rcx
  const WCHAR *ResString2FromModule; // rbx
  __int64 v14; // rcx
  int v15; // eax
  WCHAR *TemporaryFileName; // rax
  const WCHAR *v17; // r12
  unsigned int v18; // ebx
  FILE *v19; // rax
  FILE *v20; // rax
  HKEY phkResult; // [rsp+30h] [rbp-99h] BYREF
  int v22; // [rsp+38h] [rbp-91h] BYREF
  int v23[2]; // [rsp+40h] [rbp-89h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-81h]
  int v25; // [rsp+70h] [rbp-59h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-39h]
  LPCWSTR lpFile; // [rsp+A0h] [rbp-29h]
  WCHAR *v28; // [rsp+A8h] [rbp-21h]
  int v29; // [rsp+CCh] [rbp+3h]

  phkResult = 0;
  v22 = 0;
  v23[1] = 0;
  memset_0(v23, 0, 0x94u);
  if ( !a1 || !a2 )
  {
    SetLastError(0x57u);
    v20 = o___acrt_iob_func_0(2u);
    ShowLastError(v20);
    return 1;
  }
  InitGlobalData(4, v23);
  if ( !(unsigned int)ParseSaveCmdLine(a1, a2, L"SAVE", v23, &v22) )
  {
    v4 = o___acrt_iob_func_0(2u);
    ShowLastErrorEx(v4);
    v5 = 1;
LABEL_9:
    FreeGlobalData(v23);
    return v5;
  }
  v5 = 1;
  if ( v22 == 1 )
  {
    Usage(4);
    v5 = 0;
    goto LABEL_9;
  }
  v6 = v25 != 0 ? 2 : 4;
  if ( !RegConnectMachine((__int64)v23) )
  {
    SaveErrorMessage(0xFFFFFFFFLL);
    v7 = o___acrt_iob_func_0(2u);
    ShowLastErrorEx(v7);
    goto LABEL_9;
  }
  LastError = RegOpenKeyExW(hKey, lpSubKey, 0, v29 | 0x20000, &phkResult);
  v10 = 2;
  if ( !LastError )
  {
    LastError = RegAdjustTokenPrivileges(17);
    if ( LastError )
      goto LABEL_29;
    v11 = (WCHAR *)lpFile;
    LastError = RegSaveKeyExW(phkResult, lpFile, 0, v6);
    if ( LastError == 87 )
    {
      DeleteFileW(v11);
      LastError = RegSaveKeyExW(phkResult, v11, 0, 1u);
    }
    if ( LastError == 183 )
    {
      ResString2FromModule = (const WCHAR *)GetResString2FromModule(v12, 207, 0);
      GetResString2FromModule(v14, 206, 1);
      do
        v15 = Prompt(ResString2FromModule);
      while ( v15 > 2 );
      if ( v15 != 1 )
      {
        LastError = 1223;
LABEL_29:
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        goto LABEL_31;
      }
      v28 = v11;
      TemporaryFileName = GetTemporaryFileName(v11);
      lpFile = TemporaryFileName;
      v17 = TemporaryFileName;
      if ( TemporaryFileName )
      {
        LastError = RegSaveKeyExW(phkResult, TemporaryFileName, 0, v6);
        if ( LastError == 87 )
        {
          DeleteFileW(v17);
          LastError = RegSaveKeyExW(phkResult, v17, 0, 1u);
        }
        if ( !LastError && !CopyFileW(v17, v11, 0) )
          LastError = GetLastError();
        DeleteFileW(v17);
      }
      else
      {
        LastError = GetLastError();
      }
    }
    if ( LastError == 87 )
      LastError = 206;
    goto LABEL_29;
  }
LABEL_31:
  SaveErrorMessage(LastError);
  if ( !LastError || LastError == 1223 )
  {
    v18 = 0;
    v10 = 1;
  }
  else
  {
    v18 = 1;
  }
  v19 = o___acrt_iob_func_0(v10);
  ShowLastErrorEx(v19);
  FreeGlobalData(v23);
  return v18;
}

```

## disassembly

```asm
0x14000496c  mov     [rsp-8+arg_10], rbx
0x140004971  push    rbp
0x140004972  push    rsi
0x140004973  push    rdi
0x140004974  push    r12
0x140004976  push    r13
0x140004978  push    r14
0x14000497a  push    r15
0x14000497c  lea     rbp, [rsp-27h]
0x140004981  sub     rsp, 0F0h
0x140004988  mov     rax, cs:__security_cookie
0x14000498f  xor     rax, rsp
0x140004992  mov     [rbp+57h+var_40], rax
0x140004996  mov     rbx, rdx
0x140004999  mov     [rsp+120h+var_F0], 0
0x1400049a2  mov     edi, ecx
0x1400049a4  mov     [rsp+120h+var_E8], 0
0x1400049ac  xor     eax, eax
0x1400049ae  lea     rcx, [rsp+120h+var_E0]; void *
0x1400049b3  xor     edx, edx; Val
0x1400049b5  mov     [rsp+120h+var_DC], eax
0x1400049b9  mov     r8d, 94h; Size
0x1400049bf  call    memset_0
0x1400049c4  test    edi, edi
0x1400049c6  jz      loc_140004C97
0x1400049cc  test    rbx, rbx
0x1400049cf  jz      loc_140004C97
0x1400049d5  mov     esi, 4
0x1400049da  lea     rdx, [rsp+120h+var_E0]
0x1400049df  mov     ecx, esi
0x1400049e1  call    InitGlobalData
0x1400049e6  lea     rax, [rsp+120h+var_E8]
0x1400049eb  mov     rdx, rbx
0x1400049ee  lea     r9, [rsp+120h+var_E0]
0x1400049f3  mov     [rsp+120h+phkResult], rax
0x1400049f8  lea     r8, aSave; "SAVE"
0x1400049ff  mov     ecx, edi
0x140004a01  call    ParseSaveCmdLine
0x140004a06  test    eax, eax
0x140004a08  jnz     short loc_140004A24
0x140004a0a  lea     ecx, [rsi-2]; Ix
0x140004a0d  call    _o___acrt_iob_func_0
0x140004a12  mov     rcx, rax
0x140004a15  mov     edx, 20000h
0x140004a1a  call    ShowLastErrorEx
0x140004a1f  lea     edi, [rsi-3]
0x140004a22  jmp     short loc_140004A76
0x140004a24  mov     edi, 1
0x140004a29  cmp     [rsp+120h+var_E8], edi
0x140004a2d  jnz     short loc_140004A3A
0x140004a2f  mov     ecx, esi
0x140004a31  call    Usage
0x140004a36  xor     edi, edi
0x140004a38  jmp     short loc_140004A76
0x140004a3a  mov     eax, [rbp+57h+var_B0]
0x140004a3d  lea     rcx, [rsp+120h+var_E0]
0x140004a42  neg     eax
0x140004a44  sbb     r14d, r14d
0x140004a47  and     r14d, 0FFFFFFFEh
0x140004a4b  add     r14d, esi
0x140004a4e  call    RegConnectMachine
0x140004a53  test    eax, eax
0x140004a55  jnz     short loc_140004A87
0x140004a57  or      ecx, 0FFFFFFFFh
0x140004a5a  call    SaveErrorMessage
0x140004a5f  mov     ecx, 2; Ix
0x140004a64  call    _o___acrt_iob_func_0
0x140004a69  mov     rcx, rax
0x140004a6c  mov     edx, 20001h
0x140004a71  call    ShowLastErrorEx
0x140004a76  lea     rcx, [rsp+120h+var_E0]
0x140004a7b  call    FreeGlobalData
0x140004a80  mov     eax, edi
0x140004a82  jmp     loc_140004CBF
0x140004a87  mov     r9d, [rbp+57h+var_54]
0x140004a8b  lea     rax, [rsp+120h+var_F0]
0x140004a90  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140004a94  mov     r15d, 20000h
0x140004a9a  mov     rcx, [rsp+120h+hKey]; hKey
0x140004a9f  or      r9d, r15d; samDesired
0x140004aa2  xor     r8d, r8d; ulOptions
0x140004aa5  mov     [rsp+120h+phkResult], rax; phkResult
0x140004aaa  call    cs:__imp_RegOpenKeyExW
0x140004ab1  nop     dword ptr [rax+rax+00h]
0x140004ab6  mov     ebx, eax
0x140004ab8  mov     esi, 2
0x140004abd  test    eax, eax
0x140004abf  jnz     loc_140004C56
0x140004ac5  lea     ecx, [rax+11h]
0x140004ac8  call    RegAdjustTokenPrivileges
0x140004acd  mov     ebx, eax
0x140004acf  test    eax, eax
0x140004ad1  jnz     loc_140004C37
0x140004ad7  mov     r13, [rbp+57h+lpFile]
0x140004adb  mov     r9d, r14d; Flags
0x140004ade  mov     rcx, [rsp+120h+var_F0]; hKey
0x140004ae3  mov     rdx, r13; lpFile
0x140004ae6  xor     r8d, r8d; lpSecurityAttributes
0x140004ae9  call    cs:__imp_RegSaveKeyExW
0x140004af0  nop     dword ptr [rax+rax+00h]
0x140004af5  mov     ebx, eax
0x140004af7  cmp     eax, 57h ; 'W'
0x140004afa  jnz     short loc_140004B27
0x140004afc  mov     rcx, r13; lpFileName
0x140004aff  call    cs:__imp_DeleteFileW
0x140004b06  nop     dword ptr [rax+rax+00h]
0x140004b0b  mov     rcx, [rsp+120h+var_F0]; hKey
0x140004b10  mov     r9d, edi; Flags
0x140004b13  xor     r8d, r8d; lpSecurityAttributes
0x140004b16  mov     rdx, r13; lpFile
0x140004b19  call    cs:__imp_RegSaveKeyExW
0x140004b20  nop     dword ptr [rax+rax+00h]
0x140004b25  mov     ebx, eax
0x140004b27  mov     r12d, 0CEh
0x140004b2d  cmp     ebx, 0B7h
0x140004b33  jnz     loc_140004C30
0x140004b39  xor     r8d, r8d
0x140004b3c  lea     edx, [rbx+18h]
0x140004b3f  call    GetResString2FromModule
0x140004b44  mov     r8d, edi
0x140004b47  mov     edx, r12d
0x140004b4a  mov     rbx, rax
0x140004b4d  call    GetResString2FromModule
0x140004b52  mov     r12, rax
0x140004b55  mov     r9d, [rbp+57h+var_C8]
0x140004b59  mov     r8, r12
0x140004b5c  mov     rdx, r13
0x140004b5f  mov     rcx, rbx
0x140004b62  call    Prompt
0x140004b67  cmp     eax, esi
0x140004b69  jg      short loc_140004B55
0x140004b6b  cmp     eax, edi
0x140004b6d  jz      short loc_140004B79
0x140004b6f  mov     ebx, 4C7h
0x140004b74  jmp     loc_140004C37
0x140004b79  mov     rcx, r13; lpString
0x140004b7c  mov     [rbp+57h+var_78], r13
0x140004b80  call    GetTemporaryFileName
0x140004b85  mov     [rbp+57h+lpFile], rax
0x140004b89  mov     r12, rax
0x140004b8c  test    rax, rax
0x140004b8f  jnz     short loc_140004BA4
0x140004b91  call    cs:__imp_GetLastError
0x140004b98  nop     dword ptr [rax+rax+00h]
0x140004b9d  mov     ebx, eax
0x140004b9f  jmp     loc_140004C2A
0x140004ba4  mov     rcx, [rsp+120h+var_F0]; hKey
0x140004ba9  mov     r9d, r14d; Flags
0x140004bac  xor     r8d, r8d; lpSecurityAttributes
0x140004baf  mov     rdx, r12; lpFile
0x140004bb2  call    cs:__imp_RegSaveKeyExW
0x140004bb9  nop     dword ptr [rax+rax+00h]
0x140004bbe  mov     ebx, eax
0x140004bc0  cmp     eax, 57h ; 'W'
0x140004bc3  jnz     short loc_140004BF0
0x140004bc5  mov     rcx, r12; lpFileName
0x140004bc8  call    cs:__imp_DeleteFileW
0x140004bcf  nop     dword ptr [rax+rax+00h]
0x140004bd4  mov     rcx, [rsp+120h+var_F0]; hKey
0x140004bd9  mov     r9d, edi; Flags
0x140004bdc  xor     r8d, r8d; lpSecurityAttributes
0x140004bdf  mov     rdx, r12; lpFile
0x140004be2  call    cs:__imp_RegSaveKeyExW
0x140004be9  nop     dword ptr [rax+rax+00h]
0x140004bee  mov     ebx, eax
0x140004bf0  test    ebx, ebx
0x140004bf2  jnz     short loc_140004C1B
0x140004bf4  xor     r8d, r8d; bFailIfExists
0x140004bf7  mov     rdx, r13; lpNewFileName
0x140004bfa  mov     rcx, r12; lpExistingFileName
0x140004bfd  call    cs:__imp_CopyFileW
0x140004c04  nop     dword ptr [rax+rax+00h]
0x140004c09  test    eax, eax
0x140004c0b  jnz     short loc_140004C1B
0x140004c0d  call    cs:__imp_GetLastError
0x140004c14  nop     dword ptr [rax+rax+00h]
0x140004c19  mov     ebx, eax
0x140004c1b  mov     rcx, r12; lpFileName
0x140004c1e  call    cs:__imp_DeleteFileW
0x140004c25  nop     dword ptr [rax+rax+00h]
0x140004c2a  mov     r12d, 0CEh
0x140004c30  cmp     ebx, 57h ; 'W'
0x140004c33  cmovz   ebx, r12d
0x140004c37  mov     rcx, [rsp+120h+var_F0]; hKey
0x140004c3c  test    rcx, rcx
0x140004c3f  jz      short loc_140004C56
0x140004c41  call    cs:__imp_RegCloseKey
0x140004c48  nop     dword ptr [rax+rax+00h]
0x140004c4d  mov     [rsp+120h+var_F0], 0
0x140004c56  mov     ecx, ebx
0x140004c58  call    SaveErrorMessage
0x140004c5d  test    ebx, ebx
0x140004c5f  jz      short loc_140004C73
0x140004c61  cmp     ebx, 4C7h
0x140004c67  jz      short loc_140004C73
0x140004c69  mov     ebx, edi
0x140004c6b  mov     r15d, 20001h
0x140004c71  jmp     short loc_140004C77
0x140004c73  xor     ebx, ebx
0x140004c75  mov     esi, edi
0x140004c77  mov     ecx, esi; Ix
0x140004c79  call    _o___acrt_iob_func_0
0x140004c7e  mov     rcx, rax
0x140004c81  mov     edx, r15d
0x140004c84  call    ShowLastErrorEx
0x140004c89  lea     rcx, [rsp+120h+var_E0]
0x140004c8e  call    FreeGlobalData
0x140004c93  mov     eax, ebx
0x140004c95  jmp     short loc_140004CBF
0x140004c97  mov     ecx, 57h ; 'W'; dwErrCode
0x140004c9c  call    cs:__imp_SetLastError
0x140004ca3  nop     dword ptr [rax+rax+00h]
0x140004ca8  mov     ecx, 2; Ix
0x140004cad  call    _o___acrt_iob_func_0
0x140004cb2  mov     rcx, rax
0x140004cb5  call    ShowLastError
0x140004cba  mov     eax, 1
0x140004cbf  mov     rcx, [rbp+57h+var_40]
0x140004cc3  xor     rcx, rsp; StackCookie
0x140004cc6  call    __security_check_cookie
0x140004ccb  mov     rbx, [rsp+120h+arg_10]
0x140004cd3  add     rsp, 0F0h
0x140004cda  pop     r15
0x140004cdc  pop     r14
0x140004cde  pop     r13
0x140004ce0  pop     r12
0x140004ce2  pop     rdi
0x140004ce3  pop     rsi
0x140004ce4  pop     rbp
0x140004ce5  retn
```
