# RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18000ce54`
- end: `0x18000cee0`
- name: `?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f77c`
- `0x18001064c`

## callees

- `0x18000a5ac`
- `0x18000ce54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ceb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ceb3`

## string_xrefs

- `0x18000ced3`: `RegOpenKeyEx`

## pseudocode

```c
__int64 __fastcall RegistryKey::Open(__int64 a1, __int64 a2, const WCHAR *a3, int a4)
{
  LSTATUS v6; // eax
  __int64 result; // rax
  HKEY v8; // rdi
  HKEY v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, a4 | 0x100, &v9);
  if ( v6 )
  {
    if ( v6 != 2 )
      SystemError::Throw<long>((__int64)L"RegOpenKeyEx", v6);
    return 1;
  }
  else
  {
    v8 = v9;
    if ( *(_QWORD *)a1 )
      RegCloseKey(*(HKEY *)a1);
    *(_QWORD *)a1 = v8;
    result = 0;
    *(_DWORD *)(a1 + 8) = a4;
  }
  return result;
}

```

## disassembly

```asm
0x18000ce54  mov     rax, rsp
0x18000ce57  mov     [rax+8], rbx
0x18000ce5b  mov     [rax+18h], rsi
0x18000ce5f  mov     [rax+10h], rdx
0x18000ce63  push    rdi
0x18000ce64  sub     rsp, 30h
0x18000ce68  mov     rbx, rcx
0x18000ce6b  mov     qword ptr [rax+10h], 0
0x18000ce73  lea     rcx, [rax+10h]
0x18000ce77  mov     esi, r9d
0x18000ce7a  mov     [rax-18h], rcx
0x18000ce7e  mov     rdx, r8; lpSubKey
0x18000ce81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ce88  bts     r9d, 8; samDesired
0x18000ce8d  xor     r8d, r8d; ulOptions
0x18000ce90  call    cs:__imp_RegOpenKeyExW
0x18000ce96  test    eax, eax
0x18000ce98  jz      short loc_18000CEA6
0x18000ce9a  cmp     eax, 2
0x18000ce9d  jnz     short loc_18000CED1
0x18000ce9f  mov     eax, 1
0x18000cea4  jmp     short loc_18000CEC1
0x18000cea6  mov     rcx, [rbx]; hKey
0x18000cea9  mov     rdi, [rsp+38h+arg_8]
0x18000ceae  test    rcx, rcx
0x18000ceb1  jz      short loc_18000CEB9
0x18000ceb3  call    cs:__imp_RegCloseKey
0x18000ceb9  mov     [rbx], rdi
0x18000cebc  xor     eax, eax
0x18000cebe  mov     [rbx+8], esi
0x18000cec1  mov     rbx, [rsp+38h+arg_0]
0x18000cec6  mov     rsi, [rsp+38h+arg_10]
0x18000cecb  add     rsp, 30h
0x18000cecf  pop     rdi
0x18000ced0  retn
0x18000ced1  mov     edx, eax
0x18000ced3  lea     rcx, aRegopenkeyex; "RegOpenKeyEx"
0x18000ceda  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
