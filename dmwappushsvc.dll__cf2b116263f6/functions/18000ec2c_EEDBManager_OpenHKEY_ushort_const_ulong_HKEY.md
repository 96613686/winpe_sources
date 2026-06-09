# EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)

- ea: `0x18000ec2c`
- end: `0x18000ec5f`
- name: `?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `51`
- prototype: `LSTATUS __fastcall(LPCWSTR lpSubKey, __int64, HKEY *phkResult)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ec08`
- `0x18000f0ec`
- `0x18000faf0`

## callees

- `0x18000ec2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec48`

## pseudocode

```c
LSTATUS __fastcall EEDBManager::OpenHKEY(LPCWSTR lpSubKey, __int64 a2, HKEY *phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000ec2c  sub     rsp, 38h
0x18000ec30  mov     [rsp+38h+phkResult], r8; phkResult
0x18000ec35  mov     rdx, rcx; lpSubKey
0x18000ec38  xor     r8d, r8d; ulOptions
0x18000ec3b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ec42  mov     r9d, 20119h; samDesired
0x18000ec48  call    cs:__imp_RegOpenKeyExW
0x18000ec4e  test    eax, eax
0x18000ec50  jle     short loc_18000EC5A
0x18000ec52  movzx   eax, ax
0x18000ec55  or      eax, 80070000h
0x18000ec5a  add     rsp, 38h
0x18000ec5e  retn
```
