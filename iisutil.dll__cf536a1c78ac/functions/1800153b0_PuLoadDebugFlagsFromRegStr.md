# PuLoadDebugFlagsFromRegStr

- ea: `0x1800153b0`
- end: `0x180015416`
- name: `PuLoadDebugFlagsFromRegStr`
- size: `102`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800153b0`
- `0x180020510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800153de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800153de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015401`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015401`

## pseudocode

```c
__int64 __fastcall PuLoadDebugFlagsFromRegStr(LPCSTR lpSubKey, unsigned int DebugFlagsFromReg)
{
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    DebugFlagsFromReg = PuLoadDebugFlagsFromReg(hKey, DebugFlagsFromReg);
    RegCloseKey(hKey);
  }
  return DebugFlagsFromReg;
}

```

## disassembly

```asm
0x1800153b0  push    rbx
0x1800153b2  sub     rsp, 30h
0x1800153b6  mov     ebx, edx
0x1800153b8  mov     [rsp+38h+hKey], 0
0x1800153c1  mov     rdx, rcx; lpSubKey
0x1800153c4  lea     rax, [rsp+38h+hKey]
0x1800153c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800153d0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800153d5  mov     r9d, 20019h; samDesired
0x1800153db  xor     r8d, r8d; ulOptions
0x1800153de  call    cs:__imp_RegOpenKeyExA
0x1800153e5  nop     dword ptr [rax+rax+00h]
0x1800153ea  test    eax, eax
0x1800153ec  jnz     short loc_18001540D
0x1800153ee  mov     rcx, [rsp+38h+hKey]
0x1800153f3  mov     edx, ebx
0x1800153f5  call    PuLoadDebugFlagsFromReg
0x1800153fa  mov     rcx, [rsp+38h+hKey]; hKey
0x1800153ff  mov     ebx, eax
0x180015401  call    cs:__imp_RegCloseKey
0x180015408  nop     dword ptr [rax+rax+00h]
0x18001540d  mov     eax, ebx
0x18001540f  add     rsp, 30h
0x180015413  pop     rbx
0x180015414  retn
```
