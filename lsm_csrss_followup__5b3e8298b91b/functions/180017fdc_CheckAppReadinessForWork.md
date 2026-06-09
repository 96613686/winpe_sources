# CheckAppReadinessForWork

- ea: `0x180017fdc`
- end: `0x1800180e3`
- name: `CheckAppReadinessForWork`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017520`

## callees

- `0x180017fdc`
- `0x180018200`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001804a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001804a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800180ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800180ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800180d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800180d0`

## string_xrefs

- `0x18001800a`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness\%ls`

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
0x180017fdc  mov     [rsp-8+arg_8], rbx
0x180017fe1  mov     [rsp-8+arg_10], rsi
0x180017fe6  push    rbp
0x180017fe7  lea     rbp, [rsp-370h]
0x180017fef  sub     rsp, 470h
0x180017ff6  mov     rax, cs:__security_cookie
0x180017ffd  xor     rax, rsp
0x180018000  mov     [rbp+370h+var_10], rax
0x180018007  mov     r9, rcx
0x18001800a  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018011  lea     rcx, [rsp+470h+SubKey]; unsigned __int16 *
0x180018016  mov     edx, 208h; unsigned __int64
0x18001801b  xor     ebx, ebx
0x18001801d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018022  test    eax, eax
0x180018024  js      short loc_18001805C
0x180018026  lea     rax, [rsp+470h+hKey]
0x18001802b  mov     [rsp+470h+hKey], rbx
0x180018030  lea     esi, [rbx+1]
0x180018033  mov     [rsp+470h+phkResult], rax; phkResult
0x180018038  mov     r9d, esi; samDesired
0x18001803b  lea     rdx, [rsp+470h+SubKey]; lpSubKey
0x180018040  xor     r8d, r8d; ulOptions
0x180018043  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001804a  call    cs:__imp_RegOpenKeyExW
0x180018050  test    eax, eax
0x180018052  jz      short loc_180018082
0x180018054  lea     ecx, [rax-2]
0x180018057  cmp     ecx, esi
0x180018059  cmovbe  ebx, esi
0x18001805c  mov     eax, ebx
0x18001805e  mov     rcx, [rbp+370h+var_10]
0x180018065  xor     rcx, rsp; StackCookie
0x180018068  call    __security_check_cookie
0x18001806d  lea     r11, [rsp+470h+var_s0]
0x180018075  mov     rbx, [r11+18h]
0x180018079  mov     rsi, [r11+20h]
0x18001807d  mov     rsp, r11
0x180018080  pop     rbp
0x180018081  retn
0x180018082  mov     rcx, [rsp+470h+hKey]; hKey
0x180018087  lea     rax, [rsp+470h+cbData]
0x18001808c  mov     [rsp+470h+lpcbData], rax; lpcbData
0x180018091  lea     r9, [rsp+470h+Type]; lpType
0x180018096  lea     rax, [rsp+470h+Data]
0x18001809b  mov     dword ptr [rsp+470h+Data], ebx
0x18001809f  xor     r8d, r8d; lpReserved
0x1800180a2  mov     [rsp+470h+phkResult], rax; lpData
0x1800180a7  lea     rdx, aUserstate; "UserState"
0x1800180ae  mov     [rsp+470h+Type], ebx
0x1800180b2  mov     [rsp+470h+cbData], 4
0x1800180ba  call    cs:__imp_RegQueryValueExW
0x1800180c0  test    eax, eax
0x1800180c2  jnz     short loc_1800180CB
0x1800180c4  cmp     dword ptr [rsp+470h+Data], 3
0x1800180c9  jnz     short loc_1800180D8
0x1800180cb  mov     rcx, [rsp+470h+hKey]; hKey
0x1800180d0  call    cs:__imp_RegCloseKey
0x1800180d6  jmp     short loc_18001805C
0x1800180d8  cmp     [rsp+470h+Type], 4
0x1800180dd  jnz     short loc_1800180CB
0x1800180df  mov     ebx, esi
0x1800180e1  jmp     short loc_1800180CB
```
