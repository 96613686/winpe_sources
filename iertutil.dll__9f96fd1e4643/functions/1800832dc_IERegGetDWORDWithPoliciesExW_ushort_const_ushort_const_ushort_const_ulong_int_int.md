# IERegGetDWORDWithPoliciesExW(ushort const *,ushort const *,ushort const *,ulong,int *,int *)

- ea: `0x1800832dc`
- end: `0x1800834ea`
- name: `?IERegGetDWORDWithPoliciesExW@@YAKPEBG00KPEAH1@Z`
- size: `526`
- prototype: `unsigned int __usercall@<eax>(PCWSTR pwszKey@<rcx>, LPCWSTR lpSubKey@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180078b90`

## callees

- `0x18003f2a0`
- `0x1800832dc`
- `0x180083a78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800833a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083427`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800833a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083427`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800833dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008345b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800833dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008345b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083359`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800834ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083359`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800834ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083467`

## string_xrefs

- `0x180083346`: `Security_HKLM_Only`

## pseudocode

```c
__int64 __fastcall IERegGetDWORDWithPoliciesExW(
        PCWSTR pwszKey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        DWORD a4,
        int *pvData,
        int *pcbData)
{
  int v6; // edi
  LSTATUS v9; // ebx
  const WCHAR *v10; // rdx
  SRRF v11; // r8d
  DWORD *v12; // r9
  LSTATUS ValueW; // eax
  HKEY phkResult[2]; // [rsp+40h] [rbp-10h] BYREF
  const unsigned __int16 *Data; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  cbData = a4;
  Data = a3;
  v6 = 0;
  LODWORD(pvData) = 0;
  LODWORD(pcbData) = 4;
  v9 = 1;
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
    v6 = (int)pvData;
  }
  LODWORD(Data) = 0;
  cbData = 0;
  phkResult[0] = 0;
  if ( (unsigned int)IsPolicyKeyPresentW(lpSubKey, 0, 2) )
  {
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, phkResult);
    if ( !v9 )
    {
      cbData = 4;
      v9 = RegQueryValueExW(phkResult[0], L"PunycodeEncoding", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(phkResult[0]);
    }
  }
  if ( v6 )
  {
LABEL_12:
    if ( !v9 )
      return (unsigned int)Data;
    goto LABEL_13;
  }
  if ( !v9 )
    return (unsigned int)Data;
  if ( (unsigned int)IsPolicyKeyPresentW(lpSubKey, 1, 2)
    && !RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 1u, phkResult) )
  {
    cbData = 4;
    v9 = RegQueryValueExW(phkResult[0], L"PunycodeEncoding", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(phkResult[0]);
    goto LABEL_12;
  }
LABEL_13:
  cbData = 4;
  if ( v6 )
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, pwszKey, L"PunycodeEncoding", 0x18u, 0, &Data, &cbData);
  else
    ValueW = SHRegGetValueFromHKCUHKLM(pwszKey, v10, v11, v12, &Data, &cbData);
  if ( ValueW )
    return 0;
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x1800832dc  mov     rax, rsp
0x1800832df  mov     [rax+8], rbx
0x1800832e3  mov     [rax+10h], rsi
0x1800832e7  mov     [rax+20h], r9d
0x1800832eb  mov     [rax+18h], r8
0x1800832ef  push    rbp
0x1800832f0  push    rdi
0x1800832f1  push    r14
0x1800832f3  mov     rbp, rsp
0x1800832f6  sub     rsp, 50h
0x1800832fa  xor     edi, edi
0x1800832fc  mov     dword ptr [rbp+arg_20], 0
0x180083303  mov     rsi, rdx
0x180083306  mov     [rbp+arg_28], 4
0x18008330d  mov     r14, rcx
0x180083310  xor     edx, edx
0x180083312  lea     rcx, aSoftwarePolici_14; "Software\\Policies\\Microsoft\\Internet"...
0x180083319  lea     r8d, [rdi+2]
0x18008331d  lea     ebx, [rdi+1]
0x180083320  call    IsPolicyKeyPresentW
0x180083325  test    eax, eax
0x180083327  jz      short loc_180083365
0x180083329  lea     rax, [rbp+arg_28]
0x18008332d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180083334  mov     [rsp+50h+pcbData], rax; pcbData
0x180083339  lea     r9d, [rdi+18h]; dwFlags
0x18008333d  lea     rax, [rbp+arg_20]
0x180083341  mov     [rsp+50h+pvData], rax; pvData
0x180083346  lea     r8, aSecurityHklmOn_1; "Security_HKLM_Only"
0x18008334d  lea     rdx, aSoftwarePolici_14; "Software\\Policies\\Microsoft\\Internet"...
0x180083354  mov     [rsp+50h+pdwType], rdi; pdwType
0x180083359  call    cs:__imp_RegGetValueW
0x18008335f  test    eax, eax
0x180083361  cmovz   edi, dword ptr [rbp+arg_20]
0x180083365  xor     edx, edx
0x180083367  mov     dword ptr [rbp+Data], 0
0x18008336e  mov     rcx, rsi
0x180083371  mov     [rbp+cbData], 0
0x180083378  mov     [rbp+phkResult], 0
0x180083380  lea     r8d, [rdx+2]
0x180083384  call    IsPolicyKeyPresentW
0x180083389  test    eax, eax
0x18008338b  jz      short loc_1800833EE
0x18008338d  lea     rax, [rbp+phkResult]
0x180083391  mov     r9d, ebx; samDesired
0x180083394  xor     r8d, r8d; ulOptions
0x180083397  mov     [rsp+50h+pdwType], rax; phkResult
0x18008339c  mov     rdx, rsi; lpSubKey
0x18008339f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800833a6  call    cs:__imp_RegOpenKeyExW
0x1800833ac  mov     ebx, eax
0x1800833ae  test    eax, eax
0x1800833b0  jnz     short loc_1800833EE
0x1800833b2  mov     rcx, [rbp+phkResult]; hKey
0x1800833b6  lea     rax, [rbp+cbData]
0x1800833ba  mov     [rsp+50h+pvData], rax; lpcbData
0x1800833bf  lea     rdx, aPunycodeencodi; "PunycodeEncoding"
0x1800833c6  lea     rax, [rbp+Data]
0x1800833ca  mov     [rbp+cbData], 4
0x1800833d1  xor     r9d, r9d; lpType
0x1800833d4  mov     [rsp+50h+pdwType], rax; lpData
0x1800833d9  xor     r8d, r8d; lpReserved
0x1800833dc  call    cs:__imp_RegQueryValueExW
0x1800833e2  mov     rcx, [rbp+phkResult]; hKey
0x1800833e6  mov     ebx, eax
0x1800833e8  call    cs:__imp_RegCloseKey
0x1800833ee  test    edi, edi
0x1800833f0  jnz     short loc_18008346D
0x1800833f2  test    ebx, ebx
0x1800833f4  jz      loc_1800834D4
0x1800833fa  lea     edx, [rdi+1]
0x1800833fd  mov     rcx, rsi
0x180083400  lea     r8d, [rdi+2]
0x180083404  call    IsPolicyKeyPresentW
0x180083409  test    eax, eax
0x18008340b  jz      short loc_180083471
0x18008340d  lea     rax, [rbp+phkResult]
0x180083411  xor     r8d, r8d; ulOptions
0x180083414  lea     r9d, [rdi+1]; samDesired
0x180083418  mov     [rsp+50h+pdwType], rax; phkResult
0x18008341d  mov     rdx, rsi; lpSubKey
0x180083420  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180083427  call    cs:__imp_RegOpenKeyExW
0x18008342d  test    eax, eax
0x18008342f  jnz     short loc_180083471
0x180083431  mov     rcx, [rbp+phkResult]; hKey
0x180083435  lea     rax, [rbp+cbData]
0x180083439  mov     [rsp+50h+pvData], rax; lpcbData
0x18008343e  lea     rdx, aPunycodeencodi; "PunycodeEncoding"
0x180083445  lea     rax, [rbp+Data]
0x180083449  mov     [rbp+cbData], 4
0x180083450  xor     r9d, r9d; lpType
0x180083453  mov     [rsp+50h+pdwType], rax; lpData
0x180083458  xor     r8d, r8d; lpReserved
0x18008345b  call    cs:__imp_RegQueryValueExW
0x180083461  mov     rcx, [rbp+phkResult]; hKey
0x180083465  mov     ebx, eax
0x180083467  call    cs:__imp_RegCloseKey
0x18008346d  test    ebx, ebx
0x18008346f  jz      short loc_1800834D4
0x180083471  mov     [rbp+cbData], 4
0x180083478  lea     rax, [rbp+cbData]
0x18008347c  test    edi, edi
0x18008347e  jz      short loc_1800834B6
0x180083480  mov     [rsp+50h+pcbData], rax; pcbData
0x180083485  lea     r8, aPunycodeencodi; "PunycodeEncoding"
0x18008348c  lea     rax, [rbp+Data]
0x180083490  mov     r9d, 18h; dwFlags
0x180083496  mov     [rsp+50h+pvData], rax; pvData
0x18008349b  mov     rdx, r14; lpSubKey
0x18008349e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800834a5  mov     [rsp+50h+pdwType], 0; pdwType
0x1800834ae  call    cs:__imp_RegGetValueW
0x1800834b4  jmp     short loc_1800834CC
0x1800834b6  mov     [rsp+50h+pvData], rax; pcbData
0x1800834bb  mov     rcx, r14; pwszKey
0x1800834be  lea     rax, [rbp+Data]
0x1800834c2  mov     [rsp+50h+pdwType], rax; pvData
0x1800834c7  call    SHRegGetValueFromHKCUHKLM
0x1800834cc  test    eax, eax
0x1800834ce  jz      short loc_1800834D4
0x1800834d0  xor     eax, eax
0x1800834d2  jmp     short loc_1800834D7
0x1800834d4  mov     eax, dword ptr [rbp+Data]
0x1800834d7  mov     rbx, [rsp+50h+arg_0]
0x1800834dc  mov     rsi, [rsp+50h+arg_8]
0x1800834e1  add     rsp, 50h
0x1800834e5  pop     r14
0x1800834e7  pop     rdi
0x1800834e8  pop     rbp
0x1800834e9  retn
```
