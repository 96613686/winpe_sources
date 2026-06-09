# IsInLSAProcess

- ea: `0x18001810c`
- end: `0x180018231`
- name: `IsInLSAProcess`
- size: `293`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018070`
- `0x1800222fc`
- `0x18002247c`
- `0x180046190`

## callees

- `0x18001810c`
- `0x1800183e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800181ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800181ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800181a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800181a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018205`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800181dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800181dd`

## pseudocode

```c
_BOOL8 IsInLSAProcess()
{
  int v0; // ebx
  int v2; // eax
  char TrustedEnvironment; // cl
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v0 = dword_180079454;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( dword_180079454 == -1 )
  {
    v2 = g_TrustedEnvironment;
    if ( g_TrustedEnvironment )
    {
      TrustedEnvironment = g_TrustedEnvironment;
    }
    else
    {
      TrustedEnvironment = GetTrustedEnvironment();
      v2 = g_TrustedEnvironment;
    }
    if ( (TrustedEnvironment & 0x18) != 0 )
      goto LABEL_15;
    if ( !v2 )
      LOBYTE(v2) = GetTrustedEnvironment();
    if ( (v2 & 4) != 0 )
    {
LABEL_15:
      v0 = 0;
    }
    else
    {
      v0 = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlset\\Control\\Lsa", 0, 1u, &hKey) )
      {
        if ( !RegQueryValueExW(hKey, L"LsaPid", 0, &Type, (LPBYTE)&Data, &cbData) )
          v0 = Data == GetCurrentProcessId();
        RegCloseKey(hKey);
      }
    }
    dword_180079454 = v0;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x18001810c  mov     rax, rsp
0x18001810f  push    rbx
0x180018110  push    rsi
0x180018111  sub     rsp, 38h
0x180018115  mov     ebx, cs:dword_180079454
0x18001811b  mov     esi, 1
0x180018120  mov     qword ptr [rax+20h], 0
0x180018128  mov     dword ptr [rax+8], 0
0x18001812f  mov     dword ptr [rax+18h], 0
0x180018136  mov     dword ptr [rax+10h], 4
0x18001813d  cmp     ebx, 0FFFFFFFFh
0x180018140  jz      short loc_180018151
0x180018142  xor     eax, eax
0x180018144  cmp     ebx, esi
0x180018146  setz    al
0x180018149  add     rsp, 38h
0x18001814d  pop     rsi
0x18001814e  pop     rbx
0x18001814f  retn
0x180018151  mov     eax, cs:g_TrustedEnvironment
0x180018157  test    eax, eax
0x180018159  jnz     loc_18001821C
0x18001815f  call    GetTrustedEnvironment
0x180018164  mov     ecx, eax
0x180018166  mov     eax, cs:g_TrustedEnvironment
0x18001816c  test    cl, 18h
0x18001816f  jnz     loc_180018223
0x180018175  test    eax, eax
0x180018177  jz      loc_180018227
0x18001817d  test    al, 4
0x18001817f  jnz     loc_180018223
0x180018185  lea     rax, [rsp+48h+hKey]
0x18001818a  mov     r9d, esi; samDesired
0x18001818d  xor     r8d, r8d; ulOptions
0x180018190  mov     [rsp+48h+phkResult], rax; phkResult
0x180018195  lea     rdx, SubKey; "System\\CurrentControlset\\Control\\Lsa"
0x18001819c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800181a3  xor     ebx, ebx
0x1800181a5  call    cs:__imp_RegOpenKeyExW
0x1800181ac  nop     dword ptr [rax+rax+00h]
0x1800181b1  test    eax, eax
0x1800181b3  jnz     short loc_180018211
0x1800181b5  mov     rcx, [rsp+48h+hKey]; hKey
0x1800181ba  lea     rax, [rsp+48h+cbData]
0x1800181bf  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800181c4  lea     r9, [rsp+48h+Type]; lpType
0x1800181c9  lea     rax, [rsp+48h+Data]
0x1800181ce  xor     r8d, r8d; lpReserved
0x1800181d1  lea     rdx, ValueName; "LsaPid"
0x1800181d8  mov     [rsp+48h+phkResult], rax; lpData
0x1800181dd  call    cs:__imp_RegQueryValueExW
0x1800181e4  nop     dword ptr [rax+rax+00h]
0x1800181e9  test    eax, eax
0x1800181eb  jnz     short loc_180018200
0x1800181ed  call    cs:__imp_GetCurrentProcessId
0x1800181f4  nop     dword ptr [rax+rax+00h]
0x1800181f9  cmp     [rsp+48h+Data], eax
0x1800181fd  cmovz   ebx, esi
0x180018200  mov     rcx, [rsp+48h+hKey]; hKey
0x180018205  call    cs:__imp_RegCloseKey
0x18001820c  nop     dword ptr [rax+rax+00h]
0x180018211  mov     cs:dword_180079454, ebx
0x180018217  jmp     loc_180018142
0x18001821c  mov     ecx, eax
0x18001821e  jmp     loc_18001816C
0x180018223  xor     ebx, ebx
0x180018225  jmp     short loc_180018211
0x180018227  call    GetTrustedEnvironment
0x18001822c  jmp     loc_18001817D
```
