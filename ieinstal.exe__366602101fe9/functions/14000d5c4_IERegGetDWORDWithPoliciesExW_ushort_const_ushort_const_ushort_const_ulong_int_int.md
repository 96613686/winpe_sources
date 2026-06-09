# IERegGetDWORDWithPoliciesExW(ushort const *,ushort const *,ushort const *,ulong,int *,int *)

- ea: `0x14000d5c4`
- end: `0x14000d83a`
- name: `?IERegGetDWORDWithPoliciesExW@@YAKPEBG00KPEAH1@Z`
- size: `630`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009c48`

## callees

- `0x14000d5c4`
- `0x14000d840`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000d6f3`
- `ADVAPI32!RegCloseKey` at `0x14000d792`
- `ADVAPI32!RegCloseKey` at `0x14000d6f3`
- `ADVAPI32!RegCloseKey` at `0x14000d792`
- `ADVAPI32!RegQueryValueExW` at `0x14000d6e1`
- `ADVAPI32!RegQueryValueExW` at `0x14000d780`
- `ADVAPI32!RegQueryValueExW` at `0x14000d6e1`
- `ADVAPI32!RegQueryValueExW` at `0x14000d780`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d6a9`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d74a`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d6a9`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d74a`
- `ADVAPI32!RegGetValueW` at `0x14000d647`
- `ADVAPI32!RegGetValueW` at `0x14000d7df`
- `ADVAPI32!RegGetValueW` at `0x14000d647`
- `ADVAPI32!RegGetValueW` at `0x14000d7df`
- `iertutil!__imp_IsPolicyKeyPresentW` at `0x14000d607`
- `iertutil!__imp_IsPolicyKeyPresentW` at `0x14000d67c`
- `iertutil!__imp_IsPolicyKeyPresentW` at `0x14000d71d`
- `iertutil!__imp_IsPolicyKeyPresentW` at `0x14000d607`
- `iertutil!__imp_IsPolicyKeyPresentW` at `0x14000d67c`
- `iertutil!__imp_IsPolicyKeyPresentW` at `0x14000d71d`

## string_xrefs

- `0x14000d634`: `Security_HKLM_Only`

## pseudocode

```c
__int64 __fastcall IERegGetDWORDWithPoliciesExW(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        int *pcbData,
        int *a6)
{
  int v6; // edi
  LSTATUS v8; // ebx
  const WCHAR *v9; // rcx
  SRRF v10; // r8d
  DWORD *v11; // r9
  LSTATUS ValueW; // eax
  HKEY phkResult[2]; // [rsp+40h] [rbp-10h] BYREF
  int pvData; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+84h] [rbp+34h]
  const unsigned __int16 *Data; // [rsp+88h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+48h] BYREF

  cbData = a4;
  Data = a2;
  v16 = HIDWORD(a1);
  v6 = 0;
  pvData = 0;
  LODWORD(pcbData) = 4;
  v8 = 1;
  if ( (unsigned int)IsPolicyKeyPresentW(L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 2)
    && !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Internet Explorer\\Main",
          L"Security_HKLM_Only",
          0x18u,
          0,
          &pvData,
          (LPDWORD)&pcbData) )
  {
    v6 = pvData;
  }
  LODWORD(Data) = 0;
  cbData = 0;
  phkResult[0] = 0;
  if ( (unsigned int)IsPolicyKeyPresentW(
                       L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
                       0,
                       2) )
  {
    v8 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
           0,
           1u,
           phkResult);
    if ( !v8 )
    {
      cbData = 4;
      v8 = RegQueryValueExW(phkResult[0], a3, 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(phkResult[0]);
    }
  }
  if ( !v6 )
  {
    if ( !v8 )
      goto LABEL_20;
    if ( !(unsigned int)IsPolicyKeyPresentW(
                          L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
                          1,
                          2)
      || RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
           0,
           1u,
           phkResult) )
    {
LABEL_13:
      cbData = 4;
      if ( v6 )
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
                   a3,
                   0x18u,
                   0,
                   &Data,
                   &cbData);
      else
        ValueW = SHRegGetValueFromHKCUHKLM(v9, a3, v10, v11, &Data, &cbData);
      if ( ValueW )
        LODWORD(Data) = 0;
      if ( a6 )
        *a6 = 0;
      return (unsigned int)Data;
    }
    cbData = 4;
    v8 = RegQueryValueExW(phkResult[0], a3, 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(phkResult[0]);
  }
  if ( v8 )
    goto LABEL_13;
LABEL_20:
  if ( a6 )
    *a6 = 1;
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x14000d5c4  mov     [rsp-28h+cbData], r9d
0x14000d5c9  mov     [rsp-28h+Data], rdx
0x14000d5ce  mov     [rsp-28h+arg_0], rcx
0x14000d5d3  push    rbp
0x14000d5d4  push    rbx
0x14000d5d5  push    rsi
0x14000d5d6  push    rdi
0x14000d5d7  push    r15
0x14000d5d9  mov     rbp, rsp
0x14000d5dc  sub     rsp, 50h
0x14000d5e0  xor     edi, edi
0x14000d5e2  mov     dword ptr [rbp+arg_0], 0
0x14000d5e9  mov     rsi, r8
0x14000d5ec  mov     dword ptr [rbp+arg_20], 4
0x14000d5f3  xor     edx, edx
0x14000d5f5  lea     rcx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Internet"...
0x14000d5fc  lea     r15d, [rdi+1]
0x14000d600  lea     r8d, [rdi+2]
0x14000d604  mov     ebx, r15d
0x14000d607  call    cs:__imp_IsPolicyKeyPresentW
0x14000d60e  nop     dword ptr [rax+rax+00h]
0x14000d613  test    eax, eax
0x14000d615  jz      short loc_14000D659
0x14000d617  lea     rax, [rbp+arg_20]
0x14000d61b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000d622  mov     [rsp+50h+pcbData], rax; pcbData
0x14000d627  lea     r9d, [rdi+18h]; dwFlags
0x14000d62b  lea     rax, [rbp+arg_0]
0x14000d62f  mov     [rsp+50h+pvData], rax; pvData
0x14000d634  lea     r8, Value; "Security_HKLM_Only"
0x14000d63b  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Internet"...
0x14000d642  mov     [rsp+50h+pdwType], rdi; pdwType
0x14000d647  call    cs:__imp_RegGetValueW
0x14000d64e  nop     dword ptr [rax+rax+00h]
0x14000d653  test    eax, eax
0x14000d655  cmovz   edi, dword ptr [rbp+arg_0]
0x14000d659  xor     edx, edx
0x14000d65b  mov     dword ptr [rbp+Data], 0
0x14000d662  lea     rcx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x14000d669  mov     [rbp+cbData], 0
0x14000d670  mov     [rbp+phkResult], 0
0x14000d678  lea     r8d, [rdx+2]
0x14000d67c  call    cs:__imp_IsPolicyKeyPresentW
0x14000d683  nop     dword ptr [rax+rax+00h]
0x14000d688  test    eax, eax
0x14000d68a  jz      short loc_14000D6FF
0x14000d68c  lea     rax, [rbp+phkResult]
0x14000d690  mov     r9d, r15d; samDesired
0x14000d693  xor     r8d, r8d; ulOptions
0x14000d696  mov     [rsp+50h+pdwType], rax; phkResult
0x14000d69b  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x14000d6a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d6a9  call    cs:__imp_RegOpenKeyExW
0x14000d6b0  nop     dword ptr [rax+rax+00h]
0x14000d6b5  mov     ebx, eax
0x14000d6b7  test    eax, eax
0x14000d6b9  jnz     short loc_14000D6FF
0x14000d6bb  mov     rcx, [rbp+phkResult]; hKey
0x14000d6bf  lea     rax, [rbp+cbData]
0x14000d6c3  mov     [rsp+50h+pvData], rax; lpcbData
0x14000d6c8  xor     r9d, r9d; lpType
0x14000d6cb  lea     rax, [rbp+Data]
0x14000d6cf  mov     [rbp+cbData], 4
0x14000d6d6  xor     r8d, r8d; lpReserved
0x14000d6d9  mov     [rsp+50h+pdwType], rax; lpData
0x14000d6de  mov     rdx, rsi; lpValueName
0x14000d6e1  call    cs:__imp_RegQueryValueExW
0x14000d6e8  nop     dword ptr [rax+rax+00h]
0x14000d6ed  mov     rcx, [rbp+phkResult]; hKey
0x14000d6f1  mov     ebx, eax
0x14000d6f3  call    cs:__imp_RegCloseKey
0x14000d6fa  nop     dword ptr [rax+rax+00h]
0x14000d6ff  test    edi, edi
0x14000d701  jnz     loc_14000D79E
0x14000d707  test    ebx, ebx
0x14000d709  jz      loc_14000D81F
0x14000d70f  lea     r8d, [rdi+2]
0x14000d713  mov     edx, r15d
0x14000d716  lea     rcx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x14000d71d  call    cs:__imp_IsPolicyKeyPresentW
0x14000d724  nop     dword ptr [rax+rax+00h]
0x14000d729  test    eax, eax
0x14000d72b  jz      short loc_14000D7A2
0x14000d72d  lea     rax, [rbp+phkResult]
0x14000d731  mov     r9d, r15d; samDesired
0x14000d734  xor     r8d, r8d; ulOptions
0x14000d737  mov     [rsp+50h+pdwType], rax; phkResult
0x14000d73c  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x14000d743  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000d74a  call    cs:__imp_RegOpenKeyExW
0x14000d751  nop     dword ptr [rax+rax+00h]
0x14000d756  test    eax, eax
0x14000d758  jnz     short loc_14000D7A2
0x14000d75a  mov     rcx, [rbp+phkResult]; hKey
0x14000d75e  lea     rax, [rbp+cbData]
0x14000d762  mov     [rsp+50h+pvData], rax; lpcbData
0x14000d767  xor     r9d, r9d; lpType
0x14000d76a  lea     rax, [rbp+Data]
0x14000d76e  mov     [rbp+cbData], 4
0x14000d775  xor     r8d, r8d; lpReserved
0x14000d778  mov     [rsp+50h+pdwType], rax; lpData
0x14000d77d  mov     rdx, rsi; lpValueName
0x14000d780  call    cs:__imp_RegQueryValueExW
0x14000d787  nop     dword ptr [rax+rax+00h]
0x14000d78c  mov     rcx, [rbp+phkResult]; hKey
0x14000d790  mov     ebx, eax
0x14000d792  call    cs:__imp_RegCloseKey
0x14000d799  nop     dword ptr [rax+rax+00h]
0x14000d79e  test    ebx, ebx
0x14000d7a0  jz      short loc_14000D81F
0x14000d7a2  mov     [rbp+cbData], 4
0x14000d7a9  lea     rax, [rbp+cbData]
0x14000d7ad  test    edi, edi
0x14000d7af  jz      short loc_14000D7ED
0x14000d7b1  mov     [rsp+50h+pcbData], rax; pcbData
0x14000d7b6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Internet Explorer"...
0x14000d7bd  lea     rax, [rbp+Data]
0x14000d7c1  mov     r9d, 18h; dwFlags
0x14000d7c7  mov     [rsp+50h+pvData], rax; pvData
0x14000d7cc  mov     r8, rsi; lpValue
0x14000d7cf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000d7d6  mov     [rsp+50h+pdwType], 0; pdwType
0x14000d7df  call    cs:__imp_RegGetValueW
0x14000d7e6  nop     dword ptr [rax+rax+00h]
0x14000d7eb  jmp     short loc_14000D803
0x14000d7ed  mov     [rsp+50h+pvData], rax; pcbData
0x14000d7f2  mov     rdx, rsi; pwszValue
0x14000d7f5  lea     rax, [rbp+Data]
0x14000d7f9  mov     [rsp+50h+pdwType], rax; pvData
0x14000d7fe  call    SHRegGetValueFromHKCUHKLM
0x14000d803  test    eax, eax
0x14000d805  jz      short loc_14000D80E
0x14000d807  mov     dword ptr [rbp+Data], 0
0x14000d80e  mov     rax, [rbp+arg_28]
0x14000d812  test    rax, rax
0x14000d815  jz      short loc_14000D82B
0x14000d817  mov     dword ptr [rax], 0
0x14000d81d  jmp     short loc_14000D82B
0x14000d81f  mov     rax, [rbp+arg_28]
0x14000d823  test    rax, rax
0x14000d826  jz      short loc_14000D82B
0x14000d828  mov     [rax], r15d
0x14000d82b  mov     eax, dword ptr [rbp+Data]
0x14000d82e  add     rsp, 50h
0x14000d832  pop     r15
0x14000d834  pop     rdi
0x14000d835  pop     rsi
0x14000d836  pop     rbx
0x14000d837  pop     rbp
0x14000d838  retn
```
