# EsVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)

- ea: `0x1800338bc`
- end: `0x180033a45`
- name: `?ReadBooleanFromImageOptionsKey@EsVerifierSettings@@CA_NPEBG_N@Z`
- size: `393`
- prototype: `bool __fastcall(const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800248bc`

## callees

- `0x1800338bc`
- `0x180043510`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180033921`
- `msvcrt!wcsrchr` at `0x180033921`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800338ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800338ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180033902`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180033902`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800339e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800339e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033964`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033996`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033964`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a19`

## string_xrefs

- `0x1800339ae`: `EsEnableRemoveQueryValidityHeuristics`

## pseudocode

```c
char __fastcall EsVerifierSettings::ReadBooleanFromImageOptionsKey(const unsigned __int16 *a1)
{
  char v1; // bl
  HMODULE ModuleHandleW; // rax
  wchar_t *v3; // rax
  const WCHAR *v4; // rdi
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v11; // [rsp+50h] [rbp-B0h]
  WCHAR Filename[512]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = 1;
  ModuleHandleW = GetModuleHandleW(0);
  if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x200u) )
  {
    Filename[511] = 0;
    v3 = wcsrchr(Filename, 0x5Cu);
    v4 = v3 ? v3 + 1 : Filename;
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options",
            0,
            0x20019u,
            &hKey) )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, v4, 0, 0x20019u, &phkResult) )
      {
        Type = 0;
        cbData = 10;
        *(_QWORD *)Data = 0;
        v11 = 0;
        if ( !RegQueryValueExW(phkResult, L"EsEnableRemoveQueryValidityHeuristics", 0, &Type, Data, &cbData)
          && Type == 1
          && *(_WORD *)Data != 121
          && *(_WORD *)Data != 89
          && *(_WORD *)Data != 49 )
        {
          v1 = 0;
        }
        RegCloseKey(phkResult);
      }
      RegCloseKey(hKey);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800338bc  mov     [rsp-8+arg_0], rbx
0x1800338c1  mov     [rsp-8+arg_8], rdi
0x1800338c6  push    rbp
0x1800338c7  lea     rbp, [rsp-370h]
0x1800338cf  sub     rsp, 470h
0x1800338d6  mov     rax, cs:__security_cookie
0x1800338dd  xor     rax, rsp
0x1800338e0  mov     [rbp+370h+var_10], rax
0x1800338e7  xor     ecx, ecx; lpModuleName
0x1800338e9  mov     ebx, 1
0x1800338ee  call    cs:__imp_GetModuleHandleW
0x1800338f4  mov     r8d, 200h; nSize
0x1800338fa  lea     rdx, [rsp+470h+Filename]; lpFilename
0x1800338ff  mov     rcx, rax; hModule
0x180033902  call    cs:__imp_GetModuleFileNameW
0x180033908  test    eax, eax
0x18003390a  jz      loc_180033A1F
0x180033910  xor     eax, eax
0x180033912  lea     edx, [rbx+5Bh]; Ch
0x180033915  lea     rcx, [rsp+470h+Filename]; Str
0x18003391a  mov     [rbp+370h+var_12], ax
0x180033921  call    cs:__imp_wcsrchr
0x180033927  mov     rdi, rax
0x18003392a  test    rax, rax
0x18003392d  jz      short loc_180033935
0x18003392f  add     rdi, 2
0x180033933  jmp     short loc_18003393A
0x180033935  lea     rdi, [rsp+470h+Filename]
0x18003393a  lea     rax, [rsp+470h+hKey]
0x18003393f  mov     [rsp+470h+hKey], 0
0x180033948  mov     r9d, 20019h; samDesired
0x18003394e  mov     [rsp+470h+phkResult], rax; phkResult
0x180033953  xor     r8d, r8d; ulOptions
0x180033956  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003395d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033964  call    cs:__imp_RegOpenKeyExW
0x18003396a  test    eax, eax
0x18003396c  jnz     loc_180033A1F
0x180033972  mov     rcx, [rsp+470h+hKey]; hKey
0x180033977  lea     rax, [rsp+470h+var_438]
0x18003397c  mov     r9d, 20019h; samDesired
0x180033982  mov     [rsp+470h+phkResult], rax; phkResult
0x180033987  xor     r8d, r8d; ulOptions
0x18003398a  mov     [rsp+470h+var_438], 0
0x180033993  mov     rdx, rdi; lpSubKey
0x180033996  call    cs:__imp_RegOpenKeyExW
0x18003399c  test    eax, eax
0x18003399e  jnz     short loc_180033A14
0x1800339a0  mov     rcx, [rsp+470h+var_438]; hKey
0x1800339a5  lea     r9, [rsp+470h+Type]; lpType
0x1800339aa  mov     [rsp+470h+Type], eax
0x1800339ae  lea     rdx, aEsenableremove; "EsEnableRemoveQueryValidityHeuristics"
0x1800339b5  xor     eax, eax
0x1800339b7  mov     [rsp+470h+cbData], 0Ah
0x1800339bf  mov     qword ptr [rsp+470h+Data], rax
0x1800339c4  xor     r8d, r8d; lpReserved
0x1800339c7  mov     [rsp+470h+var_420], ax
0x1800339cc  lea     rax, [rsp+470h+cbData]
0x1800339d1  mov     [rsp+470h+lpcbData], rax; lpcbData
0x1800339d6  lea     rax, [rsp+470h+Data]
0x1800339db  mov     [rsp+470h+phkResult], rax; lpData
0x1800339e0  call    cs:__imp_RegQueryValueExW
0x1800339e6  test    eax, eax
0x1800339e8  jnz     short loc_180033A09
0x1800339ea  cmp     [rsp+470h+Type], ebx
0x1800339ee  jnz     short loc_180033A09
0x1800339f0  movzx   eax, word ptr [rsp+470h+Data]
0x1800339f5  cmp     ax, 79h ; 'y'
0x1800339f9  jz      short loc_180033A09
0x1800339fb  cmp     ax, 59h ; 'Y'
0x1800339ff  jz      short loc_180033A09
0x180033a01  cmp     ax, 31h ; '1'
0x180033a05  jz      short loc_180033A09
0x180033a07  xor     bl, bl
0x180033a09  mov     rcx, [rsp+470h+var_438]; hKey
0x180033a0e  call    cs:__imp_RegCloseKey
0x180033a14  mov     rcx, [rsp+470h+hKey]; hKey
0x180033a19  call    cs:__imp_RegCloseKey
0x180033a1f  mov     al, bl
0x180033a21  mov     rcx, [rbp+370h+var_10]
0x180033a28  xor     rcx, rsp; StackCookie
0x180033a2b  call    __security_check_cookie
0x180033a30  lea     r11, [rsp+470h+var_s0]
0x180033a38  mov     rbx, [r11+10h]
0x180033a3c  mov     rdi, [r11+18h]
0x180033a40  mov     rsp, r11
0x180033a43  pop     rbp
0x180033a44  retn
```
