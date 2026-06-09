# CscTpp_ReadConfigValue(ushort const *,ulong *)

- ea: `0x1800698e0`
- end: `0x18006998d`
- name: `?CscTpp_ReadConfigValue@@YAKPEBGPEAK@Z`
- size: `173`
- prototype: `unsigned int __fastcall(LPCWSTR lpValueName, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006969c`

## callees

- `0x1800698e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006991d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006991d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069956`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069956`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069978`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069978`

## string_xrefs

- `0x180069901`: `Software\Microsoft\Windows\CurrentVersion\NetCache`

## pseudocode

```c
__int64 __fastcall CscTpp_ReadConfigValue(LPCWSTR lpValueName, unsigned int *a2)
{
  unsigned int v4; // ebx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache", 0, 0x20019u, &hKey);
  if ( !v4 )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v4 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v4 )
    {
      if ( Type == 4 )
        *a2 = Data;
      else
        v4 = 13;
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800698e0  mov     [rsp-18h+arg_0], rbx
0x1800698e5  push    rbp
0x1800698e6  push    rsi
0x1800698e7  push    rdi
0x1800698e8  mov     rbp, rsp
0x1800698eb  sub     rsp, 40h
0x1800698ef  mov     rdi, rdx
0x1800698f2  mov     [rbp+hKey], 0
0x1800698fa  mov     rsi, rcx
0x1800698fd  lea     rax, [rbp+hKey]
0x180069901  lea     rdx, REGSTR_KEY_OFFLINEFILES; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180069908  mov     [rsp+40h+phkResult], rax; phkResult
0x18006990d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180069914  mov     r9d, 20019h; samDesired
0x18006991a  xor     r8d, r8d; ulOptions
0x18006991d  call    cs:__imp_RegOpenKeyExW
0x180069923  mov     ebx, eax
0x180069925  test    eax, eax
0x180069927  jnz     short loc_18006997E
0x180069929  mov     rcx, [rbp+hKey]; hKey
0x18006992d  lea     r9, [rbp+Type]; lpType
0x180069931  mov     [rbp+Data], eax
0x180069934  xor     r8d, r8d; lpReserved
0x180069937  mov     [rbp+Type], eax
0x18006993a  mov     rdx, rsi; lpValueName
0x18006993d  lea     rax, [rbp+cbData]
0x180069941  mov     [rbp+cbData], 4
0x180069948  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18006994d  lea     rax, [rbp+Data]
0x180069951  mov     [rsp+40h+phkResult], rax; lpData
0x180069956  call    cs:__imp_RegQueryValueExW
0x18006995c  mov     ebx, eax
0x18006995e  test    eax, eax
0x180069960  jnz     short loc_180069974
0x180069962  cmp     [rbp+Type], 4
0x180069966  jnz     short loc_18006996F
0x180069968  mov     eax, [rbp+Data]
0x18006996b  mov     [rdi], eax
0x18006996d  jmp     short loc_180069974
0x18006996f  mov     ebx, 0Dh
0x180069974  mov     rcx, [rbp+hKey]; hKey
0x180069978  call    cs:__imp_RegCloseKey
0x18006997e  mov     eax, ebx
0x180069980  mov     rbx, [rsp+40h+arg_0]
0x180069985  add     rsp, 40h
0x180069989  pop     rdi
0x18006998a  pop     rsi
0x18006998b  pop     rbp
0x18006998c  retn
```
