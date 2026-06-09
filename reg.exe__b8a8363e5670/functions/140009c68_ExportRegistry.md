# ExportRegistry

- ea: `0x140009c68`
- end: `0x140009f7a`
- name: `ExportRegistry`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

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
- `0x140002ce4`
- `0x140003068`
- `0x140009c68`
- `0x14000a0e0`
- `0x14000afd4`
- `0x14000d694`
- `0x14000e560`
- `0x14000e75c`
- `0x14000e798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009d59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009d7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009e57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140009ec1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140009ec1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140009dbe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140009dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009dd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009dd7`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140009ea1`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140009ea1`

## pseudocode

```c
__int64 __fastcall ExportRegistry(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // ebx
  BOOL v7; // r12d
  LSTATUS v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // esi
  WCHAR *v12; // r14
  HANDLE FileW; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  const WCHAR *v16; // r15
  int v17; // eax
  __int64 v18; // rdx
  __int64 ResString2FromModule; // rax
  WCHAR *TemporaryFileName; // rax
  const WCHAR *v21; // r15
  BOOL v22; // eax
  unsigned int v23; // r14d
  FILE *v24; // rax
  FILE *v25; // rax
  int v26; // [rsp+40h] [rbp-89h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v28[4]; // [rsp+50h] [rbp-79h] BYREF
  int v29; // [rsp+54h] [rbp-75h]
  HKEY hKey; // [rsp+58h] [rbp-71h]
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp-29h]
  const WCHAR *v32; // [rsp+A8h] [rbp-21h]
  LPCWSTR lpFileName; // [rsp+B0h] [rbp-19h]
  WCHAR *v34; // [rsp+B8h] [rbp-11h]
  int v35; // [rsp+DCh] [rbp+13h]

  phkResult = 0;
  v29 = 0;
  memset_0(v28, 0, 0x94u);
  v26 = 0;
  if ( a1 && a2 )
  {
    InitGlobalData(9, v28);
    if ( !(unsigned int)ParseExportCmdLine(a1, a2, v28, &v26) )
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
LABEL_7:
      FreeGlobalData(v28);
      return v5;
    }
    if ( v26 == 1 )
    {
      Usage(9);
      v5 = 0;
      goto LABEL_7;
    }
    v7 = 1;
    v8 = RegOpenKeyExW(hKey, lpSubKey, 0, v35 | 0x20019, &phkResult);
    v10 = v8;
    v11 = 2;
    if ( v8 )
    {
      if ( v8 == 6 )
      {
        v18 = 801;
        goto LABEL_17;
      }
LABEL_15:
      if ( v10 != 1223 )
      {
        v18 = v10;
        if ( v7 )
        {
          SaveErrorMessage(v10);
          goto LABEL_30;
        }
LABEL_17:
        ResString2FromModule = GetResString2FromModule(v9, v18, 0);
        SetReason(ResString2FromModule);
LABEL_30:
        v23 = 1;
        goto LABEL_26;
      }
LABEL_25:
      SaveErrorMessage(v10);
      v23 = 0;
      v11 = 1;
LABEL_26:
      v24 = o___acrt_iob_func_0(v11);
      ShowLastErrorEx(v24);
      FreeGlobalData(v28);
      return v23;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    v12 = (WCHAR *)lpFileName;
    FileW = CreateFileW(lpFileName, 0xC0010000, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      if ( GetLastError() != 2 )
        goto LABEL_21;
      v10 = 0;
    }
    else
    {
      CloseHandle(FileW);
      GetResString2FromModule(v14, 206, 1);
      v16 = (const WCHAR *)GetResString2FromModule(v15, 207, 0);
      do
        v17 = Prompt(v16);
      while ( v17 > 2 );
      v9 = (unsigned int)(1 - v17);
      v10 = v17 != 1 ? 0x4C7 : 0;
      if ( v17 != 1 )
        goto LABEL_15;
    }
    v34 = v12;
    TemporaryFileName = GetTemporaryFileName(v12);
    lpFileName = TemporaryFileName;
    v21 = TemporaryFileName;
    if ( TemporaryFileName )
    {
      ExportWinNT50RegFile(TemporaryFileName, v32);
      v22 = CopyFileW(v21, v12, 0);
      if ( !v22 )
        v10 = 802;
      v7 = v22;
      DeleteFileW(v21);
      if ( !v10 )
        goto LABEL_25;
      goto LABEL_15;
    }
LABEL_21:
    v18 = 802;
    goto LABEL_17;
  }
  SetLastError(0x57u);
  v25 = o___acrt_iob_func_0(2u);
  ShowLastError(v25);
  return 1;
}

```

## disassembly

```asm
0x140009c68  mov     [rsp-8+arg_10], rbx
0x140009c6d  mov     [rsp-8+arg_18], rsi
0x140009c72  push    rbp
0x140009c73  push    rdi
0x140009c74  push    r12
0x140009c76  push    r14
0x140009c78  push    r15
0x140009c7a  lea     rbp, [rsp-37h]
0x140009c7f  sub     rsp, 100h
0x140009c86  mov     rax, cs:__security_cookie
0x140009c8d  xor     rax, rsp
0x140009c90  mov     [rbp+57h+var_30], rax
0x140009c94  mov     rbx, rdx
0x140009c97  mov     [rsp+120h+var_D8], 0
0x140009ca0  mov     edi, ecx
0x140009ca2  xor     eax, eax
0x140009ca4  xor     edx, edx; Val
0x140009ca6  mov     [rbp+57h+var_CC], eax
0x140009ca9  lea     rcx, [rbp+57h+var_D0]; void *
0x140009cad  mov     r8d, 94h; Size
0x140009cb3  call    memset_0
0x140009cb8  mov     [rsp+120h+var_E0], 0
0x140009cc0  test    edi, edi
0x140009cc2  jz      loc_140009F29
0x140009cc8  test    rbx, rbx
0x140009ccb  jz      loc_140009F29
0x140009cd1  mov     esi, 9
0x140009cd6  lea     rdx, [rbp+57h+var_D0]
0x140009cda  mov     ecx, esi
0x140009cdc  call    InitGlobalData
0x140009ce1  lea     r9, [rsp+120h+var_E0]
0x140009ce6  mov     rdx, rbx
0x140009ce9  lea     r8, [rbp+57h+var_D0]
0x140009ced  mov     ecx, edi
0x140009cef  call    ParseExportCmdLine
0x140009cf4  test    eax, eax
0x140009cf6  jnz     short loc_140009D12
0x140009cf8  lea     ecx, [rsi-7]; Ix
0x140009cfb  call    _o___acrt_iob_func_0
0x140009d00  mov     rcx, rax
0x140009d03  mov     edx, 20000h
0x140009d08  call    ShowLastErrorEx
0x140009d0d  lea     ebx, [rsi-8]
0x140009d10  jmp     short loc_140009D26
0x140009d12  mov     ebx, 1
0x140009d17  cmp     [rsp+120h+var_E0], ebx
0x140009d1b  jnz     short loc_140009D36
0x140009d1d  mov     ecx, esi
0x140009d1f  call    Usage
0x140009d24  xor     ebx, ebx
0x140009d26  lea     rcx, [rbp+57h+var_D0]
0x140009d2a  call    FreeGlobalData
0x140009d2f  mov     eax, ebx
0x140009d31  jmp     loc_140009F51
0x140009d36  mov     r9d, [rbp+57h+var_44]
0x140009d3a  lea     rax, [rsp+120h+var_D8]
0x140009d3f  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140009d43  or      r9d, 20019h; samDesired
0x140009d4a  mov     rcx, [rbp+57h+hKey]; hKey
0x140009d4e  xor     r8d, r8d; ulOptions
0x140009d51  mov     r12d, ebx
0x140009d54  mov     [rsp+120h+phkResult], rax; phkResult
0x140009d59  call    cs:__imp_RegOpenKeyExW
0x140009d60  nop     dword ptr [rax+rax+00h]
0x140009d65  mov     edi, eax
0x140009d67  mov     esi, 2
0x140009d6c  test    eax, eax
0x140009d6e  jnz     loc_140009F05
0x140009d74  mov     rcx, [rsp+120h+var_D8]; hKey
0x140009d79  test    rcx, rcx
0x140009d7c  jz      short loc_140009D93
0x140009d7e  call    cs:__imp_RegCloseKey
0x140009d85  nop     dword ptr [rax+rax+00h]
0x140009d8a  mov     [rsp+120h+var_D8], 0
0x140009d93  mov     r14, [rbp+57h+lpFileName]
0x140009d97  xor     r9d, r9d; lpSecurityAttributes
0x140009d9a  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x140009da3  mov     rcx, r14; lpFileName
0x140009da6  mov     [rsp+120h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140009dae  xor     r8d, r8d; dwShareMode
0x140009db1  mov     edx, 0C0010000h; dwDesiredAccess
0x140009db6  mov     dword ptr [rsp+120h+phkResult], 3; dwCreationDisposition
0x140009dbe  call    cs:__imp_CreateFileW
0x140009dc5  nop     dword ptr [rax+rax+00h]
0x140009dca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009dce  jz      loc_140009E57
0x140009dd4  mov     rcx, rax; hObject
0x140009dd7  call    cs:__imp_CloseHandle
0x140009dde  nop     dword ptr [rax+rax+00h]
0x140009de3  mov     r8d, ebx
0x140009de6  mov     edx, 0CEh
0x140009deb  call    GetResString2FromModule
0x140009df0  xor     r8d, r8d
0x140009df3  mov     edx, 0CFh
0x140009df8  mov     rdi, rax
0x140009dfb  call    GetResString2FromModule
0x140009e00  mov     r15, rax
0x140009e03  mov     r9d, [rbp+57h+var_B8]
0x140009e07  mov     r8, rdi
0x140009e0a  mov     rdx, r14
0x140009e0d  mov     rcx, r15
0x140009e10  call    Prompt
0x140009e15  cmp     eax, esi
0x140009e17  jg      short loc_140009E03
0x140009e19  mov     ecx, eax
0x140009e1b  sub     ecx, ebx
0x140009e1d  neg     ecx
0x140009e1f  sbb     edi, edi
0x140009e21  and     edi, 4C7h
0x140009e27  cmp     eax, ebx
0x140009e29  jz      short loc_140009E69
0x140009e2b  cmp     edi, 4C7h
0x140009e31  jz      loc_140009ED5
0x140009e37  mov     edx, edi
0x140009e39  test    r12d, r12d
0x140009e3c  jnz     loc_140009F18
0x140009e42  xor     r8d, r8d
0x140009e45  call    GetResString2FromModule
0x140009e4a  mov     rcx, rax
0x140009e4d  call    SetReason
0x140009e52  jmp     loc_140009F1F
0x140009e57  call    cs:__imp_GetLastError
0x140009e5e  nop     dword ptr [rax+rax+00h]
0x140009e63  cmp     eax, esi
0x140009e65  jnz     short loc_140009E81
0x140009e67  xor     edi, edi
0x140009e69  mov     rcx, r14; lpString
0x140009e6c  mov     [rbp+57h+var_68], r14
0x140009e70  call    GetTemporaryFileName
0x140009e75  mov     [rbp+57h+lpFileName], rax
0x140009e79  mov     r15, rax
0x140009e7c  test    rax, rax
0x140009e7f  jnz     short loc_140009E88
0x140009e81  mov     edx, 322h
0x140009e86  jmp     short loc_140009E42
0x140009e88  mov     r8d, [rbp+57h+var_44]
0x140009e8c  mov     rcx, r15; lpFileName
0x140009e8f  mov     rdx, [rbp+57h+var_78]
0x140009e93  call    ExportWinNT50RegFile
0x140009e98  xor     r8d, r8d; bFailIfExists
0x140009e9b  mov     rdx, r14; lpNewFileName
0x140009e9e  mov     rcx, r15; lpExistingFileName
0x140009ea1  call    cs:__imp_CopyFileW
0x140009ea8  nop     dword ptr [rax+rax+00h]
0x140009ead  mov     edx, 322h
0x140009eb2  mov     rcx, r15; lpFileName
0x140009eb5  test    eax, eax
0x140009eb7  cmovz   edi, edx
0x140009eba  neg     eax
0x140009ebc  sbb     eax, eax
0x140009ebe  and     r12d, eax
0x140009ec1  call    cs:__imp_DeleteFileW
0x140009ec8  nop     dword ptr [rax+rax+00h]
0x140009ecd  test    edi, edi
0x140009ecf  jnz     loc_140009E2B
0x140009ed5  mov     ecx, edi
0x140009ed7  call    SaveErrorMessage
0x140009edc  xor     r14d, r14d
0x140009edf  mov     edi, 20000h
0x140009ee4  mov     esi, ebx
0x140009ee6  mov     ecx, esi; Ix
0x140009ee8  call    _o___acrt_iob_func_0
0x140009eed  mov     rcx, rax
0x140009ef0  mov     edx, edi
0x140009ef2  call    ShowLastErrorEx
0x140009ef7  lea     rcx, [rbp+57h+var_D0]
0x140009efb  call    FreeGlobalData
0x140009f00  mov     eax, r14d
0x140009f03  jmp     short loc_140009F51
0x140009f05  cmp     eax, 6
0x140009f08  jnz     loc_140009E2B
0x140009f0e  mov     edx, 321h
0x140009f13  jmp     loc_140009E42
0x140009f18  mov     ecx, edi
0x140009f1a  call    SaveErrorMessage
0x140009f1f  mov     r14d, ebx
0x140009f22  mov     edi, 20001h
0x140009f27  jmp     short loc_140009EE6
0x140009f29  mov     ecx, 57h ; 'W'; dwErrCode
0x140009f2e  call    cs:__imp_SetLastError
0x140009f35  nop     dword ptr [rax+rax+00h]
0x140009f3a  mov     ecx, 2; Ix
0x140009f3f  call    _o___acrt_iob_func_0
0x140009f44  mov     rcx, rax
0x140009f47  call    ShowLastError
0x140009f4c  mov     eax, 1
0x140009f51  mov     rcx, [rbp+57h+var_30]
0x140009f55  xor     rcx, rsp; StackCookie
0x140009f58  call    __security_check_cookie
0x140009f5d  lea     r11, [rsp+120h+var_20]
0x140009f65  mov     rbx, [r11+40h]
0x140009f69  mov     rsi, [r11+48h]
0x140009f6d  mov     rsp, r11
0x140009f70  pop     r15
0x140009f72  pop     r14
0x140009f74  pop     r12
0x140009f76  pop     rdi
0x140009f77  pop     rbp
0x140009f78  retn
```
