# CheckAppReadinessForWork

- ea: `0x1400472a0`
- end: `0x1400473bc`
- name: `CheckAppReadinessForWork`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140048db0`

## callees

- `0x140003450`
- `0x14000bf50`
- `0x1400472a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140047312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140047312`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004735a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004735a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004737f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004737f`

## string_xrefs

- `0x1400472ce`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness\%ls`

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
      if ( !RegQueryValueExW(hKey, L"UserState", 0, &Type, Data, &cbData) && Type == 4 )
        v1 = *(_DWORD *)Data != 3;
      RegCloseKey(hKey);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400472a0  mov     [rsp-8+arg_8], rbx
0x1400472a5  mov     [rsp-8+arg_10], rsi
0x1400472aa  push    rbp
0x1400472ab  lea     rbp, [rsp-370h]
0x1400472b3  sub     rsp, 470h
0x1400472ba  mov     rax, cs:__security_cookie
0x1400472c1  xor     rax, rsp
0x1400472c4  mov     [rbp+370h+var_10], rax
0x1400472cb  mov     r9, rcx
0x1400472ce  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400472d5  lea     rcx, [rsp+470h+SubKey]; unsigned __int16 *
0x1400472da  mov     edx, 208h; unsigned __int64
0x1400472df  xor     ebx, ebx
0x1400472e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400472e6  test    eax, eax
0x1400472e8  js      loc_140047395
0x1400472ee  lea     rax, [rsp+470h+hKey]
0x1400472f3  mov     [rsp+470h+hKey], rbx
0x1400472f8  lea     esi, [rbx+1]
0x1400472fb  mov     [rsp+470h+phkResult], rax; phkResult
0x140047300  mov     r9d, esi; samDesired
0x140047303  lea     rdx, [rsp+470h+SubKey]; lpSubKey
0x140047308  xor     r8d, r8d; ulOptions
0x14004730b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140047312  call    cs:__imp_RegOpenKeyExW
0x140047319  nop     dword ptr [rax+rax+00h]
0x14004731e  test    eax, eax
0x140047320  jnz     short loc_14004738D
0x140047322  mov     rcx, [rsp+470h+hKey]; hKey
0x140047327  lea     rax, [rsp+470h+cbData]
0x14004732c  mov     [rsp+470h+lpcbData], rax; lpcbData
0x140047331  lea     r9, [rsp+470h+Type]; lpType
0x140047336  lea     rax, [rsp+470h+Data]
0x14004733b  mov     dword ptr [rsp+470h+Data], ebx
0x14004733f  xor     r8d, r8d; lpReserved
0x140047342  mov     [rsp+470h+phkResult], rax; lpData
0x140047347  lea     rdx, aUserstate; "UserState"
0x14004734e  mov     [rsp+470h+Type], ebx
0x140047352  mov     [rsp+470h+cbData], 4
0x14004735a  call    cs:__imp_RegQueryValueExW
0x140047361  nop     dword ptr [rax+rax+00h]
0x140047366  test    eax, eax
0x140047368  jnz     short loc_14004737A
0x14004736a  cmp     [rsp+470h+Type], 4
0x14004736f  jnz     short loc_14004737A
0x140047371  cmp     dword ptr [rsp+470h+Data], 3
0x140047376  jz      short loc_14004737A
0x140047378  mov     ebx, esi
0x14004737a  mov     rcx, [rsp+470h+hKey]; hKey
0x14004737f  call    cs:__imp_RegCloseKey
0x140047386  nop     dword ptr [rax+rax+00h]
0x14004738b  jmp     short loc_140047395
0x14004738d  lea     ecx, [rax-2]
0x140047390  cmp     ecx, esi
0x140047392  cmovbe  ebx, esi
0x140047395  mov     eax, ebx
0x140047397  mov     rcx, [rbp+370h+var_10]
0x14004739e  xor     rcx, rsp; StackCookie
0x1400473a1  call    __security_check_cookie
0x1400473a6  lea     r11, [rsp+470h+var_s0]
0x1400473ae  mov     rbx, [r11+18h]
0x1400473b2  mov     rsi, [r11+20h]
0x1400473b6  mov     rsp, r11
0x1400473b9  pop     rbp
0x1400473ba  retn
```
