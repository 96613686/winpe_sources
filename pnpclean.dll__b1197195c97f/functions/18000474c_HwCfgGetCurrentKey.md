# HwCfgGetCurrentKey

- ea: `0x18000474c`
- end: `0x180004803`
- name: `HwCfgGetCurrentKey`
- size: `183`
- prototype: `__int64 __fastcall(REGSAM samDesired, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800045b8`
- `0x180004690`

## callees

- `0x18000474c`
- `0x18000480c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800047ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1800047ac`
- `ADVAPI32!RegCloseKey` at `0x1800047db`
- `ADVAPI32!RegCloseKey` at `0x1800047eb`
- `ADVAPI32!RegCloseKey` at `0x1800047db`
- `ADVAPI32!RegCloseKey` at `0x1800047eb`

## pseudocode

```c
__int64 __fastcall HwCfgGetCurrentKey(REGSAM samDesired, HKEY *a2)
{
  unsigned int RootKey; // ebx
  HKEY v5; // rcx
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h]

  hKey = 0;
  phkResult = 0;
  if ( a2 )
  {
    RootKey = HwCfgGetRootKey(8u);
    if ( RootKey || (RootKey = RegOpenKeyExW(hKey, L"Current", 0, samDesired, &phkResult)) != 0 )
    {
      v5 = phkResult;
    }
    else
    {
      v5 = 0;
      *a2 = phkResult;
      phkResult = 0;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      v5 = phkResult;
    }
    if ( v5 )
      RegCloseKey(v5);
  }
  else
  {
    return 87;
  }
  return RootKey;
}

```

## disassembly

```asm
0x18000474c  mov     rax, rsp
0x18000474f  mov     [rax+8], rbx
0x180004753  mov     [rax+20h], rbp
0x180004757  push    rsi
0x180004758  sub     rsp, 30h
0x18000475c  mov     qword ptr [rax+18h], 0
0x180004764  mov     rsi, rdx
0x180004767  mov     qword ptr [rax+10h], 0
0x18000476f  mov     ebp, ecx
0x180004771  test    rdx, rdx
0x180004774  jnz     short loc_18000477B
0x180004776  lea     ebx, [rdx+57h]
0x180004779  jmp     short loc_1800047F1
0x18000477b  lea     rdx, [rsp+38h+hKey]
0x180004780  mov     ecx, 8; samDesired
0x180004785  call    HwCfgGetRootKey
0x18000478a  mov     ebx, eax
0x18000478c  test    eax, eax
0x18000478e  jnz     short loc_1800047C9
0x180004790  mov     rcx, [rsp+38h+hKey]; hKey
0x180004795  lea     rax, [rsp+38h+arg_8]
0x18000479a  mov     r9d, ebp; samDesired
0x18000479d  mov     [rsp+38h+phkResult], rax; phkResult
0x1800047a2  xor     r8d, r8d; ulOptions
0x1800047a5  lea     rdx, SubKey; "Current"
0x1800047ac  call    cs:__imp_RegOpenKeyExW
0x1800047b2  mov     ebx, eax
0x1800047b4  test    eax, eax
0x1800047b6  jnz     short loc_1800047C9
0x1800047b8  mov     rax, [rsp+38h+arg_8]
0x1800047bd  xor     ecx, ecx
0x1800047bf  mov     [rsi], rax
0x1800047c2  mov     [rsp+38h+arg_8], rcx
0x1800047c7  jmp     short loc_1800047CE
0x1800047c9  mov     rcx, [rsp+38h+arg_8]
0x1800047ce  cmp     [rsp+38h+hKey], 0
0x1800047d4  jz      short loc_1800047E6
0x1800047d6  mov     rcx, [rsp+38h+hKey]; hKey
0x1800047db  call    cs:__imp_RegCloseKey
0x1800047e1  mov     rcx, [rsp+38h+arg_8]; hKey
0x1800047e6  test    rcx, rcx
0x1800047e9  jz      short loc_1800047F1
0x1800047eb  call    cs:__imp_RegCloseKey
0x1800047f1  mov     rbp, [rsp+38h+arg_18]
0x1800047f6  mov     eax, ebx
0x1800047f8  mov     rbx, [rsp+38h+arg_0]
0x1800047fd  add     rsp, 30h
0x180004801  pop     rsi
0x180004802  retn
```
