# SetAuthOptions

- ea: `0x18000e5f4`
- end: `0x18000e8a6`
- name: `SetAuthOptions`
- size: `690`
- prototype: `LSTATUS __fastcall(HKEY hKey, LPCWSTR lpSubKey, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c738`

## callees

- `0x18000e5f4`
- `0x18000f384`
- `0x18000fb1c`
- `0x180012e32`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000e760`
- `msvcrt!_snwprintf_s` at `0x18000e760`
- `KERNEL32!GlobalFree` at `0x18000e7dd`
- `KERNEL32!GlobalFree` at `0x18000e7dd`
- `KERNEL32!GlobalAlloc` at `0x18000e719`
- `KERNEL32!GlobalAlloc` at `0x18000e719`
- `ADVAPI32!RegCloseKey` at `0x18000e6ba`
- `ADVAPI32!RegCloseKey` at `0x18000e7ce`
- `ADVAPI32!RegCloseKey` at `0x18000e881`
- `ADVAPI32!RegCloseKey` at `0x18000e6ba`
- `ADVAPI32!RegCloseKey` at `0x18000e7ce`
- `ADVAPI32!RegCloseKey` at `0x18000e881`
- `ADVAPI32!RegQueryValueExW` at `0x18000e6a8`
- `ADVAPI32!RegQueryValueExW` at `0x18000e7be`
- `ADVAPI32!RegQueryValueExW` at `0x18000e83b`
- `ADVAPI32!RegQueryValueExW` at `0x18000e871`
- `ADVAPI32!RegQueryValueExW` at `0x18000e6a8`
- `ADVAPI32!RegQueryValueExW` at `0x18000e7be`
- `ADVAPI32!RegQueryValueExW` at `0x18000e83b`
- `ADVAPI32!RegQueryValueExW` at `0x18000e871`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e66e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e784`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e801`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e66e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e784`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e801`

## pseudocode

```c
LSTATUS __fastcall SetAuthOptions(HKEY hKey, LPCWSTR lpSubKey, __int64 a3)
{
  __int64 v3; // rsi
  LSTATUS Value; // ebx
  DWORD v8; // eax
  __int64 v9; // rax
  __int64 v10; // rsi
  unsigned int v11; // r14d
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  LSTATUS result; // eax
  __int64 cbData; // [rsp+30h] [rbp-20h] BYREF
  BYTE v16[8]; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-8h] BYREF
  DWORD lpcbData; // [rsp+A0h] [rbp+50h] BYREF
  DWORD Data; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  lpcbData = 0;
  phkResult = 0;
  *(_DWORD *)v16 = 1;
  SetUserName();
  SetPasswd(hKey, lpSubKey, a3);
  hKeya = 0;
  cbData = 0x100000000LL;
  Data = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
         0,
         0x20019u,
         &hKeya)
    || (LODWORD(cbData) = 4,
        Value = RegQueryValueExW(hKeya, L"AuthType", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData),
        RegCloseKey(hKeya),
        Value) )
  {
    v8 = Data;
  }
  else
  {
    v8 = Data;
    if ( Data == 5 )
    {
LABEL_8:
      *(_DWORD *)(v3 + 1056) = 5;
      goto LABEL_9;
    }
    if ( Data )
      v8 = 0;
  }
  if ( v8 == 5 )
    goto LABEL_8;
LABEL_9:
  hKeya = 0;
  v9 = -1;
  Data = 0;
  LODWORD(cbData) = 1;
  do
    ++v9;
  while ( lpSubKey[v9] );
  v10 = (unsigned int)(v9 + 8);
  v11 = v9 + 8;
  v12 = (wchar_t *)GlobalAlloc(0x40u, 2 * v10);
  v13 = v12;
  if ( v12 )
  {
    memset_0(v12, 0, 2 * v10);
    _snwprintf_s(v13, v11, (unsigned int)(v10 - 1), L"%s%s", lpSubKey, L"\\Auth", cbData);
    if ( !RegOpenKeyExW(hKey, v13, 0, 0x20019u, &hKeya) )
    {
      Data = 4;
      RegQueryValueExW(hKeya, L"AuthenticateAtLogon", 0, 0, (LPBYTE)&cbData, &Data);
      RegCloseKey(hKeya);
    }
    GlobalFree(v13);
  }
  result = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !result )
  {
    lpcbData = 4;
    RegQueryValueExW(phkResult, L"ConnectDisplay", 0, 0, (LPBYTE)&cbData + 4, &lpcbData);
    lpcbData = 4;
    RegQueryValueExW(phkResult, L"DisplayConfirmation", 0, 0, v16, &lpcbData);
    return RegCloseKey(phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x18000e5f4  mov     [rsp-38h+arg_0], rbx
0x18000e5f9  push    rbp
0x18000e5fa  push    rsi
0x18000e5fb  push    rdi
0x18000e5fc  push    r12
0x18000e5fe  push    r13
0x18000e600  push    r14
0x18000e602  push    r15
0x18000e604  mov     rbp, rsp
0x18000e607  sub     rsp, 50h
0x18000e60b  mov     rsi, [r8+8]
0x18000e60f  xor     r13d, r13d
0x18000e612  mov     rbx, r8
0x18000e615  mov     [rbp+arg_10], r13d
0x18000e619  mov     rdi, rdx
0x18000e61c  mov     [rbp+var_10], r13
0x18000e620  mov     r12, rcx
0x18000e623  lea     r14d, [r13+1]
0x18000e627  mov     dword ptr [rbp+var_1C], r14d
0x18000e62b  mov     dword ptr [rbp+var_18], r14d
0x18000e62f  call    SetUserName
0x18000e634  mov     r8, rbx
0x18000e637  mov     rdx, rdi
0x18000e63a  mov     rcx, r12
0x18000e63d  call    SetPasswd
0x18000e642  lea     rax, [rbp+hKey]
0x18000e646  mov     [rbp+hKey], r13
0x18000e64a  mov     r9d, 20019h; samDesired
0x18000e650  mov     [rsp+50h+phkResult], rax; phkResult
0x18000e655  xor     r8d, r8d; ulOptions
0x18000e658  mov     [rbp+cbData], r13d
0x18000e65c  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000e663  mov     [rbp+Data], r13d
0x18000e667  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e66e  call    cs:__imp_RegOpenKeyExW
0x18000e675  nop     dword ptr [rax+rax+00h]
0x18000e67a  test    eax, eax
0x18000e67c  jnz     short loc_18000E6DB
0x18000e67e  mov     rcx, [rbp+hKey]; hKey
0x18000e682  lea     rax, [rbp+cbData]
0x18000e686  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000e68b  lea     rdx, aAuthtype; "AuthType"
0x18000e692  lea     rax, [rbp+Data]
0x18000e696  mov     [rbp+cbData], 4
0x18000e69d  xor     r9d, r9d; lpType
0x18000e6a0  mov     [rsp+50h+phkResult], rax; lpData
0x18000e6a5  xor     r8d, r8d; lpReserved
0x18000e6a8  call    cs:__imp_RegQueryValueExW
0x18000e6af  nop     dword ptr [rax+rax+00h]
0x18000e6b4  mov     rcx, [rbp+hKey]; hKey
0x18000e6b8  mov     ebx, eax
0x18000e6ba  call    cs:__imp_RegCloseKey
0x18000e6c1  nop     dword ptr [rax+rax+00h]
0x18000e6c6  test    ebx, ebx
0x18000e6c8  jnz     short loc_18000E6DB
0x18000e6ca  mov     eax, [rbp+Data]
0x18000e6cd  cmp     eax, 5
0x18000e6d0  jz      short loc_18000E6E3
0x18000e6d2  test    eax, eax
0x18000e6d4  jz      short loc_18000E6DE
0x18000e6d6  mov     eax, r13d
0x18000e6d9  jmp     short loc_18000E6DE
0x18000e6db  mov     eax, [rbp+Data]
0x18000e6de  cmp     eax, 5
0x18000e6e1  jnz     short loc_18000E6ED
0x18000e6e3  mov     dword ptr [rsi+420h], 5
0x18000e6ed  mov     [rbp+hKey], r13
0x18000e6f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e6f5  mov     [rbp+Data], r13d
0x18000e6f9  mov     [rbp+cbData], r14d
0x18000e6fd  inc     rax
0x18000e700  cmp     [rdi+rax*2], r13w
0x18000e705  jnz     short loc_18000E6FD
0x18000e707  lea     esi, [rax+8]
0x18000e70a  mov     ecx, 40h ; '@'; uFlags
0x18000e70f  lea     r15, [rsi+rsi]
0x18000e713  mov     r14d, esi
0x18000e716  mov     rdx, r15; dwBytes
0x18000e719  call    cs:__imp_GlobalAlloc
0x18000e720  nop     dword ptr [rax+rax+00h]
0x18000e725  mov     rbx, rax
0x18000e728  test    rax, rax
0x18000e72b  jz      loc_18000E7E9
0x18000e731  mov     r8, r15; Size
0x18000e734  xor     edx, edx; Val
0x18000e736  mov     rcx, rax; void *
0x18000e739  call    memset_0
0x18000e73e  lea     rax, aAuth; "\\Auth"
0x18000e745  mov     edx, r14d; BufferCount
0x18000e748  mov     [rsp+50h+lpcbData], rax
0x18000e74d  lea     r8d, [rsi-1]; MaxCount
0x18000e751  lea     r9, aSS_0; "%s%s"
0x18000e758  mov     [rsp+50h+phkResult], rdi
0x18000e75d  mov     rcx, rbx; Buffer
0x18000e760  call    cs:__imp__snwprintf_s
0x18000e767  nop     dword ptr [rax+rax+00h]
0x18000e76c  lea     rax, [rbp+hKey]
0x18000e770  mov     r9d, 20019h; samDesired
0x18000e776  xor     r8d, r8d; ulOptions
0x18000e779  mov     [rsp+50h+phkResult], rax; phkResult
0x18000e77e  mov     rdx, rbx; lpSubKey
0x18000e781  mov     rcx, r12; hKey
0x18000e784  call    cs:__imp_RegOpenKeyExW
0x18000e78b  nop     dword ptr [rax+rax+00h]
0x18000e790  test    eax, eax
0x18000e792  jnz     short loc_18000E7DA
0x18000e794  mov     rcx, [rbp+hKey]; hKey
0x18000e798  lea     rax, [rbp+Data]
0x18000e79c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000e7a1  lea     rdx, aAuthenticateat; "AuthenticateAtLogon"
0x18000e7a8  lea     rax, [rbp+cbData]
0x18000e7ac  mov     [rbp+Data], 4
0x18000e7b3  xor     r9d, r9d; lpType
0x18000e7b6  mov     [rsp+50h+phkResult], rax; lpData
0x18000e7bb  xor     r8d, r8d; lpReserved
0x18000e7be  call    cs:__imp_RegQueryValueExW
0x18000e7c5  nop     dword ptr [rax+rax+00h]
0x18000e7ca  mov     rcx, [rbp+hKey]; hKey
0x18000e7ce  call    cs:__imp_RegCloseKey
0x18000e7d5  nop     dword ptr [rax+rax+00h]
0x18000e7da  mov     rcx, rbx; hMem
0x18000e7dd  call    cs:__imp_GlobalFree
0x18000e7e4  nop     dword ptr [rax+rax+00h]
0x18000e7e9  lea     rax, [rbp+var_10]
0x18000e7ed  mov     r9d, 20019h; samDesired
0x18000e7f3  xor     r8d, r8d; ulOptions
0x18000e7f6  mov     [rsp+50h+phkResult], rax; phkResult
0x18000e7fb  mov     rdx, rdi; lpSubKey
0x18000e7fe  mov     rcx, r12; hKey
0x18000e801  call    cs:__imp_RegOpenKeyExW
0x18000e808  nop     dword ptr [rax+rax+00h]
0x18000e80d  test    eax, eax
0x18000e80f  jnz     short loc_18000E88D
0x18000e811  mov     rcx, [rbp+var_10]; hKey
0x18000e815  lea     rax, [rbp+arg_10]
0x18000e819  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000e81e  lea     rdx, aConnectdisplay; "ConnectDisplay"
0x18000e825  lea     rax, [rbp+var_1C]
0x18000e829  mov     [rbp+arg_10], 4
0x18000e830  xor     r9d, r9d; lpType
0x18000e833  mov     [rsp+50h+phkResult], rax; lpData
0x18000e838  xor     r8d, r8d; lpReserved
0x18000e83b  call    cs:__imp_RegQueryValueExW
0x18000e842  nop     dword ptr [rax+rax+00h]
0x18000e847  mov     rcx, [rbp+var_10]; hKey
0x18000e84b  lea     rax, [rbp+arg_10]
0x18000e84f  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000e854  lea     rdx, aDisplayconfirm; "DisplayConfirmation"
0x18000e85b  lea     rax, [rbp+var_18]
0x18000e85f  mov     [rbp+arg_10], 4
0x18000e866  xor     r9d, r9d; lpType
0x18000e869  mov     [rsp+50h+phkResult], rax; lpData
0x18000e86e  xor     r8d, r8d; lpReserved
0x18000e871  call    cs:__imp_RegQueryValueExW
0x18000e878  nop     dword ptr [rax+rax+00h]
0x18000e87d  mov     rcx, [rbp+var_10]; hKey
0x18000e881  call    cs:__imp_RegCloseKey
0x18000e888  nop     dword ptr [rax+rax+00h]
0x18000e88d  mov     rbx, [rsp+50h+arg_0]
0x18000e895  add     rsp, 50h
0x18000e899  pop     r15
0x18000e89b  pop     r14
0x18000e89d  pop     r13
0x18000e89f  pop     r12
0x18000e8a1  pop     rdi
0x18000e8a2  pop     rsi
0x18000e8a3  pop     rbp
0x18000e8a4  retn
```
