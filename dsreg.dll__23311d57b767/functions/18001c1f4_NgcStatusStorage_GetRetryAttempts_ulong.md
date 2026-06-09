# NgcStatusStorage::GetRetryAttempts(ulong *)

- ea: `0x18001c1f4`
- end: `0x18001c3e2`
- name: `?GetRetryAttempts@NgcStatusStorage@@SAJPEAK@Z`
- size: `494`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f610`
- `0x18004aa30`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18001c1f4`
- `0x180043e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c313`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c313`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001c228`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001c228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3b9`

## string_xrefs

- `0x18001c2d9`: `RegOpenKeyExW`
- `0x18001c23d`: `RegOpenCurrentUser`
- `0x18001c24c`: `RegOpenCurrentUserKey`
- `0x18001c256`: `%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.`
- `0x18001c2b7`: `%s: The registry key "%s\%s" does not exist. Noting to read.`
- `0x18001c26c`: `NgcStatusStorage::GetRetryAttempts`
- `0x18001c2be`: `NgcStatusStorage::GetRetryAttempts`
- `0x18001c346`: `NgcStatusStorage::GetRetryAttempts`
- `0x18001c379`: `NgcStatusStorage::GetRetryAttempts`
- `0x18001c3c2`: `NgcStatusStorage::GetRetryAttempts`
- `0x18001c262`: `OpenRootKey`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::GetRetryAttempts(unsigned int *a1)
{
  LSTATUS v2; // eax
  int v3; // ebx
  const wchar_t *v4; // r8
  __int64 v5; // r9
  unsigned int v6; // edi
  unsigned int v7; // eax
  unsigned int v8; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  *a1 = 0;
  hKey = 0;
  phkResult = 0;
  v2 = RegOpenCurrentUser(0x20019u, &phkResult);
  v3 = v2;
  if ( !v2 )
  {
    v6 = 0;
    v7 = RegOpenKeyExW(
           phkResult,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           0,
           0x20019u,
           &hKey);
    v3 = v7;
    if ( v7 == 2 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: The registry key \"%s\\%s\" does not exist. Noting to read.",
        L"NgcStatusStorage::GetRetryAttempts",
        L"HKEY_CURRENT_USER",
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      goto LABEL_21;
    }
    if ( v7 )
    {
      v5 = v7;
      v4 = L"RegOpenKeyExW";
      goto LABEL_4;
    }
    Data = 0;
    Type = 0;
    cbData = 4;
    v8 = RegQueryValueExW(hKey, L"NumOfAttRetry", 0, &Type, (LPBYTE)&Data, &cbData);
    v3 = v8;
    if ( v8 == 2 )
    {
      Logger::TraceVerbose(
        L"%s: The value '%s' in the given key was not found, so returning default value. Key: %s",
        L"NgcStatusStorage::GetRetryAttempts",
        L"NumOfAttRetry",
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      goto LABEL_21;
    }
    if ( v8 != 234 )
    {
      if ( v8 )
      {
        v4 = L"RegQueryValueExW";
        goto LABEL_3;
      }
      if ( Type == 4 )
      {
        *a1 = Data;
        Logger::TraceVerbose(
          (wchar_t *)L"%s: The NGC Attestation retry count is: %d",
          L"NgcStatusStorage::GetRetryAttempts");
        goto LABEL_21;
      }
    }
    Logger::TraceWarning(
      (wchar_t *)L"%s: The value '%s' in the given key is not of type DWORD, so returning the default value. Error: 0x%08. Key: %s",
      L"NgcStatusStorage::GetRetryAttempts",
      L"NumOfAttRetry",
      v8,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    if ( !v3 )
      goto LABEL_21;
    goto LABEL_18;
  }
  Logger::WriteRegistryFailureEvent(v2, L"RegOpenCurrentUser", L"HKEY_CURRENT_USER");
  Logger::TraceError(
    L"%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.",
    L"RegOpenCurrentUserKey",
    (unsigned int)v3,
    131097);
  v4 = L"OpenRootKey";
LABEL_3:
  v5 = (unsigned int)v3;
LABEL_4:
  Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::GetRetryAttempts", v4, v5);
LABEL_18:
  if ( v3 > 0 )
    v6 = (unsigned __int16)v3 | 0x80070000;
  else
    v6 = v3;
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcStatusStorage::GetRetryAttempts", v6);
  return v6;
}

```

## disassembly

```asm
0x18001c1f4  push    rbp
0x18001c1f6  push    rbx
0x18001c1f7  push    rsi
0x18001c1f8  push    rdi
0x18001c1f9  push    r15
0x18001c1fb  mov     rbp, rsp
0x18001c1fe  sub     rsp, 40h
0x18001c202  mov     rsi, rcx
0x18001c205  mov     dword ptr [rcx], 0
0x18001c20b  mov     r15d, 20019h
0x18001c211  mov     [rbp+hKey], 0
0x18001c219  mov     ecx, r15d; samDesired
0x18001c21c  mov     [rbp+phkResult], 0
0x18001c224  lea     rdx, [rbp+phkResult]; phkResult
0x18001c228  call    cs:__imp_RegOpenCurrentUser
0x18001c22e  mov     ebx, eax
0x18001c230  test    eax, eax
0x18001c232  jz      short loc_18001C284
0x18001c234  lea     r8, aHkeyCurrentUse
0x18001c23b  mov     ecx, eax; unsigned int
0x18001c23d  lea     rdx, aRegopencurrent
0x18001c244  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z
0x18001c249  mov     r9d, r15d
0x18001c24c  lea     rdx, aRegopencurrent_0
0x18001c253  mov     r8d, ebx
0x18001c256  lea     rcx, aSRegopencurren
0x18001c25d  call    ?TraceError@Logger@@SAJPEBGZZ
0x18001c262  lea     r8, aOpenrootkey
0x18001c269  mov     r9d, ebx
0x18001c26c  lea     rdx, aNgcstatusstora_2
0x18001c273  lea     rcx, Str
0x18001c27a  call    ?TraceError@Logger@@SAJPEBGZZ
0x18001c27f  jmp     loc_18001C390
0x18001c284  mov     rcx, [rbp+phkResult]; hKey
0x18001c288  lea     rax, [rbp+hKey]
0x18001c28c  mov     r9d, r15d; samDesired
0x18001c28f  mov     [rsp+40h+var_20], rax; phkResult
0x18001c294  lea     r15, aSoftwareMicros_6
0x18001c29b  xor     r8d, r8d; ulOptions
0x18001c29e  mov     rdx, r15; lpSubKey
0x18001c2a1  xor     edi, edi
0x18001c2a3  call    cs:__imp_RegOpenKeyExW
0x18001c2a9  mov     ebx, eax
0x18001c2ab  cmp     eax, 2
0x18001c2ae  jnz     short loc_18001C2D2
0x18001c2b0  lea     r8, aHkeyCurrentUse
0x18001c2b7  lea     rcx, aSTheRegistryKe_9
0x18001c2be  lea     rdx, aNgcstatusstora_2
0x18001c2c5  mov     r9, r15
0x18001c2c8  call    ?TraceVerbose@Logger@@SAJPEBGZZ
0x18001c2cd  jmp     loc_18001C3A1
0x18001c2d2  test    eax, eax
0x18001c2d4  jz      short loc_18001C2E2
0x18001c2d6  mov     r9d, eax
0x18001c2d9  lea     r8, aRegopenkeyexw
0x18001c2e0  jmp     short loc_18001C26C
0x18001c2e2  mov     rcx, [rbp+hKey]; hKey
0x18001c2e6  lea     rax, [rbp+cbData]
0x18001c2ea  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001c2ef  lea     r9, [rbp+Type]; lpType
0x18001c2f3  lea     rax, [rbp+Data]
0x18001c2f7  mov     [rbp+Data], edi
0x18001c2fa  xor     r8d, r8d; lpReserved
0x18001c2fd  mov     [rsp+40h+var_20], rax; lpData
0x18001c302  lea     rdx, ValueName
0x18001c309  mov     [rbp+Type], edi
0x18001c30c  mov     [rbp+cbData], 4
0x18001c313  call    cs:__imp_RegQueryValueExW
0x18001c319  mov     ebx, eax
0x18001c31b  cmp     eax, 2
0x18001c31e  jnz     short loc_18001C330
0x18001c320  lea     r8, ValueName
0x18001c327  lea     rcx, aSTheValueSInTh
0x18001c32e  jmp     short loc_18001C2BE
0x18001c330  cmp     ebx, 0EAh
0x18001c336  jz      short loc_18001C36A
0x18001c338  test    ebx, ebx
0x18001c33a  jnz     short loc_18001C35E
0x18001c33c  cmp     [rbp+Type], 4
0x18001c340  jnz     short loc_18001C36A
0x18001c342  mov     r8d, [rbp+Data]
0x18001c346  lea     rdx, aNgcstatusstora_2
0x18001c34d  lea     rcx, aSTheNgcAttesta
0x18001c354  mov     [rsi], r8d
0x18001c357  call    ?TraceVerbose@Logger@@SAJPEBGZZ
0x18001c35c  jmp     short loc_18001C3A1
0x18001c35e  lea     r8, aRegqueryvaluee_0
0x18001c365  jmp     loc_18001C269
0x18001c36a  mov     r9d, ebx
0x18001c36d  mov     [rsp+40h+var_20], r15
0x18001c372  lea     r8, ValueName
0x18001c379  lea     rdx, aNgcstatusstora_2
0x18001c380  lea     rcx, aSTheValueSInTh_0
0x18001c387  call    ?TraceWarning@Logger@@SAJPEBGZZ
0x18001c38c  test    ebx, ebx
0x18001c38e  jz      short loc_18001C3A1
0x18001c390  test    ebx, ebx
0x18001c392  jg      short loc_18001C398
0x18001c394  mov     edi, ebx
0x18001c396  jmp     short loc_18001C3A1
0x18001c398  movzx   edi, bx
0x18001c39b  or      edi, 80070000h
0x18001c3a1  mov     rcx, [rbp+hKey]; hKey
0x18001c3a5  test    rcx, rcx
0x18001c3a8  jz      short loc_18001C3B0
0x18001c3aa  call    cs:__imp_RegCloseKey
0x18001c3b0  mov     rcx, [rbp+phkResult]; hKey
0x18001c3b4  test    rcx, rcx
0x18001c3b7  jz      short loc_18001C3BF
0x18001c3b9  call    cs:__imp_RegCloseKey
0x18001c3bf  mov     r8d, edi
0x18001c3c2  lea     rdx, aNgcstatusstora_2
0x18001c3c9  lea     rcx, aSHr0x08x
0x18001c3d0  call    ?TraceVerbose@Logger@@SAJPEBGZZ
0x18001c3d5  mov     eax, edi
0x18001c3d7  add     rsp, 40h
0x18001c3db  pop     r15
0x18001c3dd  pop     rdi
0x18001c3de  pop     rsi
0x18001c3df  pop     rbx
0x18001c3e0  pop     rbp
0x18001c3e1  retn
```
