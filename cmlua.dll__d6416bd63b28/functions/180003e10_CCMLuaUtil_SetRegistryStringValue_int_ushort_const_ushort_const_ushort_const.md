# CCMLuaUtil::SetRegistryStringValue(int,ushort const *,ushort const *,ushort const *)

- ea: `0x180003e10`
- end: `0x180003ea3`
- name: `?SetRegistryStringValue@CCMLuaUtil@@UEAAJHPEBG00@Z`
- size: `147`
- prototype: `__int64 __fastcall(CCMLuaUtil *this, int, const unsigned __int16 *, const unsigned __int16 *, const BYTE *lpString)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003e10`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003e83`
- `ADVAPI32!RegCloseKey` at `0x180003e83`
- `ADVAPI32!RegSetValueExW` at `0x180003e76`
- `ADVAPI32!RegSetValueExW` at `0x180003e76`
- `ADVAPI32!RegCreateKeyW` at `0x180003e40`
- `ADVAPI32!RegCreateKeyW` at `0x180003e40`
- `KERNEL32!lstrlenW` at `0x180003e54`
- `KERNEL32!lstrlenW` at `0x180003e54`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::SetRegistryStringValue(
        CCMLuaUtil *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const BYTE *lpString)
{
  LSTATUS v6; // ebx
  const BYTE *lpData; // rbx
  int v8; // eax
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  phkResult = 0;
  v6 = RegCreateKeyW((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, &phkResult);
  if ( !v6 )
  {
    lpData = lpString;
    v8 = lstrlenW((LPCWSTR)lpString);
    v6 = RegSetValueExW(phkResult, a4, 0, 1u, lpData, 2 * v8);
    RegCloseKey(phkResult);
  }
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003e10  mov     [rsp+arg_0], rbx
0x180003e15  push    rdi
0x180003e16  sub     rsp, 30h
0x180003e1a  neg     edx
0x180003e1c  mov     [rsp+38h+phkResult], 0
0x180003e25  mov     rax, r8
0x180003e28  mov     rdi, r9
0x180003e2b  sbb     rcx, rcx
0x180003e2e  lea     r8, [rsp+38h+phkResult]; phkResult
0x180003e33  neg     rcx
0x180003e36  mov     rdx, rax; lpSubKey
0x180003e39  add     rcx, 0FFFFFFFF80000001h; hKey
0x180003e40  call    cs:__imp_RegCreateKeyW
0x180003e46  mov     ebx, eax
0x180003e48  test    eax, eax
0x180003e4a  jnz     short loc_180003E89
0x180003e4c  mov     rbx, [rsp+38h+lpString]
0x180003e51  mov     rcx, rbx; lpString
0x180003e54  call    cs:__imp_lstrlenW
0x180003e5a  mov     rcx, [rsp+38h+phkResult]; hKey
0x180003e5f  mov     r9d, 1; dwType
0x180003e65  add     eax, eax
0x180003e67  xor     r8d, r8d; Reserved
0x180003e6a  mov     [rsp+38h+cbData], eax; cbData
0x180003e6e  mov     rdx, rdi; lpValueName
0x180003e71  mov     [rsp+38h+lpData], rbx; lpData
0x180003e76  call    cs:__imp_RegSetValueExW
0x180003e7c  mov     rcx, [rsp+38h+phkResult]; hKey
0x180003e81  mov     ebx, eax
0x180003e83  call    cs:__imp_RegCloseKey
0x180003e89  test    ebx, ebx
0x180003e8b  jle     short loc_180003E96
0x180003e8d  movzx   ebx, bx
0x180003e90  or      ebx, 80070000h
0x180003e96  mov     eax, ebx
0x180003e98  mov     rbx, [rsp+38h+arg_0]
0x180003e9d  add     rsp, 30h
0x180003ea1  pop     rdi
0x180003ea2  retn
```
