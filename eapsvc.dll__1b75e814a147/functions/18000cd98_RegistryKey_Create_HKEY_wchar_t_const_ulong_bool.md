# RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)

- ea: `0x18000cd98`
- end: `0x18000ce4d`
- name: `?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, __int64, DWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a5cc`
- `0x18000c2a0`
- `0x18000dfb0`

## callees

- `0x18000a5ac`
- `0x18000cd98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000cdf3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000cdf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce2b`

## string_xrefs

- `0x18000ce40`: `RegCreateKeyExW`

## pseudocode

```c
__int64 __fastcall RegistryKey::Create(__int64 a1, __int64 a2, const WCHAR *a3, __int64 a4, DWORD a5)
{
  unsigned int v6; // eax
  HKEY v7; // rdi
  HKEY v8; // rcx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  int v11; // [rsp+58h] [rbp-10h]

  hKey = 0;
  v11 = 1;
  a5 = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x101u, 0, &hKey, &a5);
  if ( v6 )
    SystemError::Throw<long>(L"RegCreateKeyExW", v6);
  v7 = hKey;
  v8 = 0;
  hKey = 0;
  if ( *(_QWORD *)a1 )
  {
    RegCloseKey(*(HKEY *)a1);
    v8 = hKey;
  }
  *(_QWORD *)a1 = v7;
  *(_DWORD *)(a1 + 8) = 1;
  if ( v8 )
    RegCloseKey(v8);
  return 0;
}

```

## disassembly

```asm
0x18000cd98  mov     rax, rsp
0x18000cd9b  mov     [rax+8], rbx
0x18000cd9f  push    rdi
0x18000cda0  sub     rsp, 60h
0x18000cda4  mov     rdx, r8; lpSubKey
0x18000cda7  mov     rbx, rcx
0x18000cdaa  mov     qword ptr [rax-18h], 0
0x18000cdb2  mov     dword ptr [rax-10h], 1
0x18000cdb9  mov     dword ptr [rax+28h], 0
0x18000cdc0  lea     rcx, [rax+28h]
0x18000cdc4  mov     [rax-28h], rcx
0x18000cdc8  lea     rcx, [rax-18h]
0x18000cdcc  mov     [rax-30h], rcx
0x18000cdd0  mov     qword ptr [rax-38h], 0
0x18000cdd8  mov     dword ptr [rax-40h], 101h
0x18000cddf  mov     dword ptr [rax-48h], 0
0x18000cde6  xor     r9d, r9d; lpClass
0x18000cde9  xor     r8d, r8d; Reserved
0x18000cdec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cdf3  call    cs:__imp_RegCreateKeyExW
0x18000cdf9  test    eax, eax
0x18000cdfb  jnz     short loc_18000CE3E
0x18000cdfd  mov     rdi, [rsp+68h+hKey]
0x18000ce02  xor     ecx, ecx
0x18000ce04  mov     [rsp+68h+hKey], rcx
0x18000ce09  cmp     [rbx], rcx
0x18000ce0c  jz      short loc_18000CE1C
0x18000ce0e  mov     rcx, [rbx]; hKey
0x18000ce11  call    cs:__imp_RegCloseKey
0x18000ce17  mov     rcx, [rsp+68h+hKey]; hKey
0x18000ce1c  mov     [rbx], rdi
0x18000ce1f  mov     dword ptr [rbx+8], 1
0x18000ce26  test    rcx, rcx
0x18000ce29  jz      short loc_18000CE31
0x18000ce2b  call    cs:__imp_RegCloseKey
0x18000ce31  xor     eax, eax
0x18000ce33  mov     rbx, [rsp+68h+arg_0]
0x18000ce38  add     rsp, 60h
0x18000ce3c  pop     rdi
0x18000ce3d  retn
0x18000ce3e  mov     edx, eax
0x18000ce40  lea     rcx, aRegcreatekeyex; "RegCreateKeyExW"
0x18000ce47  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
