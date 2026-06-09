# EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)

- ea: `0x18003d170`
- end: `0x18003d1ab`
- name: `?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned int, HKEY *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e3f0`
- `0x180013790`
- `0x18003d4b0`
- `0x18003d69c`
- `0x18003d94c`
- `0x18003e540`

## callees

- `0x18003d170`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d18d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d18d`

## pseudocode

```c
LSTATUS __fastcall EEDBManager::OpenHKEY(LPCWSTR lpSubKey, int a2, HKEY *phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, a2 | 0x100, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003d170  sub     rsp, 38h
0x18003d174  bts     edx, 8
0x18003d178  mov     [rsp+38h+phkResult], r8; phkResult
0x18003d17d  mov     r9d, edx; samDesired
0x18003d180  xor     r8d, r8d; ulOptions
0x18003d183  mov     rdx, rcx; lpSubKey
0x18003d186  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d18d  call    cs:__imp_RegOpenKeyExW
0x18003d194  nop     dword ptr [rax+rax+00h]
0x18003d199  test    eax, eax
0x18003d19b  jle     short loc_18003D1A5
0x18003d19d  movzx   eax, ax
0x18003d1a0  or      eax, 80070000h
0x18003d1a5  add     rsp, 38h
0x18003d1a9  retn
```
