# CheckAppReadinessForWork

- ea: `0x18000bf38`
- end: `0x18000c055`
- name: `CheckAppReadinessForWork`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x18000bf38`
- `0x18000c17c`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bfa6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bfa6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c01d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c01d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c039`

## string_xrefs

- `0x18000bf66`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness\%ls`

## pseudocode

```c
_BOOL8 __fastcall CheckAppReadinessForWork(__int64 a1)
{
  BOOL v1; // ebx
  LSTATUS v2; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[520]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  if ( (int)StringCchPrintfW(SubKey, 0x208u, L"Software\\Microsoft\\Windows\\CurrentVersion\\AppReadiness\\%ls", a1) >= 0 )
  {
    hKey = 0;
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
    if ( v2 )
    {
      return (unsigned int)(v2 - 2) <= 1;
    }
    else
    {
      *(_DWORD *)Data = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UserState", 0, &Type, Data, &cbData) && *(_DWORD *)Data != 3 )
        v1 = Type == 4;
      RegCloseKey(hKey);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000bf38  mov     [rsp-8+arg_8], rbx
0x18000bf3d  mov     [rsp-8+arg_10], rsi
0x18000bf42  push    rbp
0x18000bf43  lea     rbp, [rsp-370h]
0x18000bf4b  sub     rsp, 470h
0x18000bf52  mov     rax, cs:__security_cookie
0x18000bf59  xor     rax, rsp
0x18000bf5c  mov     [rbp+370h+var_10], rax
0x18000bf63  mov     r9, rcx
0x18000bf66  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000bf6d  lea     rcx, [rsp+470h+SubKey]; unsigned __int16 *
0x18000bf72  mov     edx, 208h; unsigned __int64
0x18000bf77  xor     ebx, ebx
0x18000bf79  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bf7e  test    eax, eax
0x18000bf80  js      short loc_18000BFBE
0x18000bf82  lea     rax, [rsp+470h+hKey]
0x18000bf87  mov     [rsp+470h+hKey], rbx
0x18000bf8c  lea     esi, [rbx+1]
0x18000bf8f  mov     [rsp+470h+phkResult], rax; phkResult
0x18000bf94  mov     r9d, esi; samDesired
0x18000bf97  lea     rdx, [rsp+470h+SubKey]; lpSubKey
0x18000bf9c  xor     r8d, r8d; ulOptions
0x18000bf9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bfa6  call    cs:__imp_RegOpenKeyExW
0x18000bfad  nop     dword ptr [rax+rax+00h]
0x18000bfb2  test    eax, eax
0x18000bfb4  jz      short loc_18000BFE5
0x18000bfb6  lea     ecx, [rax-2]
0x18000bfb9  cmp     ecx, esi
0x18000bfbb  cmovbe  ebx, esi
0x18000bfbe  mov     eax, ebx
0x18000bfc0  mov     rcx, [rbp+370h+var_10]
0x18000bfc7  xor     rcx, rsp; StackCookie
0x18000bfca  call    __security_check_cookie
0x18000bfcf  lea     r11, [rsp+470h+var_s0]
0x18000bfd7  mov     rbx, [r11+18h]
0x18000bfdb  mov     rsi, [r11+20h]
0x18000bfdf  mov     rsp, r11
0x18000bfe2  pop     rbp
0x18000bfe3  retn
0x18000bfe5  mov     rcx, [rsp+470h+hKey]; hKey
0x18000bfea  lea     rax, [rsp+470h+cbData]
0x18000bfef  mov     [rsp+470h+lpcbData], rax; lpcbData
0x18000bff4  lea     r9, [rsp+470h+Type]; lpType
0x18000bff9  lea     rax, [rsp+470h+Data]
0x18000bffe  mov     dword ptr [rsp+470h+Data], ebx
0x18000c002  xor     r8d, r8d; lpReserved
0x18000c005  mov     [rsp+470h+phkResult], rax; lpData
0x18000c00a  lea     rdx, aUserstate; "UserState"
0x18000c011  mov     [rsp+470h+Type], ebx
0x18000c015  mov     [rsp+470h+cbData], 4
0x18000c01d  call    cs:__imp_RegQueryValueExW
0x18000c024  nop     dword ptr [rax+rax+00h]
0x18000c029  test    eax, eax
0x18000c02b  jnz     short loc_18000C034
0x18000c02d  cmp     dword ptr [rsp+470h+Data], 3
0x18000c032  jnz     short loc_18000C04A
0x18000c034  mov     rcx, [rsp+470h+hKey]; hKey
0x18000c039  call    cs:__imp_RegCloseKey
0x18000c040  nop     dword ptr [rax+rax+00h]
0x18000c045  jmp     loc_18000BFBE
0x18000c04a  cmp     [rsp+470h+Type], 4
0x18000c04f  jnz     short loc_18000C034
0x18000c051  mov     ebx, esi
0x18000c053  jmp     short loc_18000C034
```
