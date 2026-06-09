# ISDKRegOpenKey

- ea: `0x180012ae8`
- end: `0x180012b2b`
- name: `ISDKRegOpenKey`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800127a4`

## callees

- `0x180012ae8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012b14`
- `KERNEL32!SetLastError` at `0x180012b14`
- `ADVAPI32!RegOpenKeyExW` at `0x180012b02`
- `ADVAPI32!RegOpenKeyExW` at `0x180012b02`

## pseudocode

```c
HKEY __fastcall ISDKRegOpenKey(HKEY a1, const WCHAR *a2, __int64 a3, REGSAM a4)
{
  LSTATUS v4; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, a4, &phkResult);
  if ( v4 )
    SetLastError(v4);
  return phkResult;
}

```

## disassembly

```asm
0x180012ae8  sub     rsp, 48h
0x180012aec  lea     rax, [rsp+48h+var_18]
0x180012af1  mov     [rsp+48h+var_18], 0
0x180012afa  xor     r8d, r8d; ulOptions
0x180012afd  mov     [rsp+48h+phkResult], rax; phkResult
0x180012b02  call    cs:__imp_RegOpenKeyExW
0x180012b09  nop     dword ptr [rax+rax+00h]
0x180012b0e  test    eax, eax
0x180012b10  jz      short loc_180012B20
0x180012b12  mov     ecx, eax; dwErrCode
0x180012b14  call    cs:__imp_SetLastError
0x180012b1b  nop     dword ptr [rax+rax+00h]
0x180012b20  mov     rax, [rsp+48h+var_18]
0x180012b25  add     rsp, 48h
0x180012b29  retn
```
