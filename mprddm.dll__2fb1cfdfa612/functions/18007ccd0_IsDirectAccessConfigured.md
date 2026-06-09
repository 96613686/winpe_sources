# IsDirectAccessConfigured

- ea: `0x18007ccd0`
- end: `0x18007cd8b`
- name: `IsDirectAccessConfigured`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18004e370`
- `0x18004f4e4`

## callees

- `0x18007ccd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18007cd10`
- `ADVAPI32!RegOpenKeyExW` at `0x18007cd10`
- `ADVAPI32!RegQueryValueExW` at `0x18007cd40`
- `ADVAPI32!RegQueryValueExW` at `0x18007cd40`
- `ADVAPI32!RegCloseKey` at `0x18007cd68`
- `ADVAPI32!RegCloseKey` at `0x18007cd78`
- `ADVAPI32!RegCloseKey` at `0x18007cd68`
- `ADVAPI32!RegCloseKey` at `0x18007cd78`

## string_xrefs

- `0x18007ccf5`: `System\CurrentControlSet\Services\RamgmtSvc\Config`

## pseudocode

```c
__int64 __fastcall IsDirectAccessConfigured(__int64 a1, _DWORD *a2)
{
  unsigned int v3; // ebx
  LSTATUS Value; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\RamgmtSvc\\Config", 0, 0x20019u, &hKey);
  if ( !v3 )
  {
    Value = RegQueryValueExW(hKey, L"ServerGPO", 0, 0, 0, 0);
    v3 = Value;
    if ( Value )
    {
      if ( Value == 2 )
      {
        *a2 = 0;
        v3 = 0;
      }
    }
    else
    {
      *a2 = 1;
    }
  }
  RegCloseKey(HKEY_LOCAL_MACHINE);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18007ccd0  mov     r11, rsp
0x18007ccd3  mov     [r11+10h], rbx
0x18007ccd7  mov     [r11+8], rcx
0x18007ccdb  push    rdi
0x18007ccdc  sub     rsp, 30h
0x18007cce0  mov     rdi, rdx
0x18007cce3  mov     dword ptr [rdx], 0
0x18007cce9  lea     rax, [r11+8]
0x18007cced  mov     qword ptr [r11+8], 0
0x18007ccf5  lea     rdx, aSystemCurrentc_38; "System\\CurrentControlSet\\Services\\Ra"...
0x18007ccfc  mov     [r11-18h], rax
0x18007cd00  mov     r9d, 20019h; samDesired
0x18007cd06  xor     r8d, r8d; ulOptions
0x18007cd09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cd10  call    cs:__imp_RegOpenKeyExW
0x18007cd16  mov     ebx, eax
0x18007cd18  test    eax, eax
0x18007cd1a  jnz     short loc_18007CD61
0x18007cd1c  mov     rcx, [rsp+38h+hKey]; hKey
0x18007cd21  lea     rdx, aServergpo; "ServerGPO"
0x18007cd28  mov     [rsp+38h+lpcbData], 0; lpcbData
0x18007cd31  xor     r9d, r9d; lpType
0x18007cd34  xor     r8d, r8d; lpReserved
0x18007cd37  mov     [rsp+38h+lpData], 0; lpData
0x18007cd40  call    cs:__imp_RegQueryValueExW
0x18007cd46  mov     ebx, eax
0x18007cd48  test    eax, eax
0x18007cd4a  jnz     short loc_18007CD54
0x18007cd4c  mov     dword ptr [rdi], 1
0x18007cd52  jmp     short loc_18007CD61
0x18007cd54  cmp     eax, 2
0x18007cd57  jnz     short loc_18007CD61
0x18007cd59  mov     dword ptr [rdi], 0
0x18007cd5f  xor     ebx, ebx
0x18007cd61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cd68  call    cs:__imp_RegCloseKey
0x18007cd6e  mov     rcx, [rsp+38h+hKey]; hKey
0x18007cd73  test    rcx, rcx
0x18007cd76  jz      short loc_18007CD7E
0x18007cd78  call    cs:__imp_RegCloseKey
0x18007cd7e  mov     eax, ebx
0x18007cd80  mov     rbx, [rsp+38h+arg_8]
0x18007cd85  add     rsp, 30h
0x18007cd89  pop     rdi
0x18007cd8a  retn
```
