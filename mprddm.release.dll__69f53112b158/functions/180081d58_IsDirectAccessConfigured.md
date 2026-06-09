# IsDirectAccessConfigured

- ea: `0x180081d58`
- end: `0x180081e1d`
- name: `IsDirectAccessConfigured`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18004fac4`
- `0x180050d54`

## callees

- `0x180081d58`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180081d92`
- `ADVAPI32!RegOpenKeyExW` at `0x180081d92`
- `ADVAPI32!RegQueryValueExW` at `0x180081dc2`
- `ADVAPI32!RegQueryValueExW` at `0x180081dc2`
- `ADVAPI32!RegCloseKey` at `0x180081ded`
- `ADVAPI32!RegCloseKey` at `0x180081e03`
- `ADVAPI32!RegCloseKey` at `0x180081ded`
- `ADVAPI32!RegCloseKey` at `0x180081e03`

## string_xrefs

- `0x180081d77`: `System\CurrentControlSet\Services\RamgmtSvc\Config`

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
0x180081d58  mov     r11, rsp
0x180081d5b  mov     [r11+10h], rbx
0x180081d5f  mov     [r11+8], rcx
0x180081d63  push    rdi
0x180081d64  sub     rsp, 30h
0x180081d68  and     dword ptr [rdx], 0
0x180081d6b  lea     rax, [r11+8]
0x180081d6f  and     qword ptr [r11+8], 0
0x180081d74  mov     rdi, rdx
0x180081d77  lea     rdx, aSystemCurrentc_36; "System\\CurrentControlSet\\Services\\Ra"...
0x180081d7e  mov     [r11-18h], rax
0x180081d82  mov     r9d, 20019h; samDesired
0x180081d88  xor     r8d, r8d; ulOptions
0x180081d8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081d92  call    cs:__imp_RegOpenKeyExW
0x180081d99  nop     dword ptr [rax+rax+00h]
0x180081d9e  mov     ebx, eax
0x180081da0  test    eax, eax
0x180081da2  jnz     short loc_180081DE6
0x180081da4  and     [rsp+38h+var_10], 0
0x180081daa  lea     rdx, aServergpo; "ServerGPO"
0x180081db1  mov     rcx, [rsp+38h+hKey]; hKey
0x180081db6  xor     r9d, r9d; lpType
0x180081db9  and     [rsp+38h+var_18], 0
0x180081dbf  xor     r8d, r8d; lpReserved
0x180081dc2  call    cs:__imp_RegQueryValueExW
0x180081dc9  nop     dword ptr [rax+rax+00h]
0x180081dce  mov     ebx, eax
0x180081dd0  test    eax, eax
0x180081dd2  jnz     short loc_180081DDC
0x180081dd4  mov     dword ptr [rdi], 1
0x180081dda  jmp     short loc_180081DE6
0x180081ddc  cmp     eax, 2
0x180081ddf  jnz     short loc_180081DE6
0x180081de1  and     dword ptr [rdi], 0
0x180081de4  xor     ebx, ebx
0x180081de6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081ded  call    cs:__imp_RegCloseKey
0x180081df4  nop     dword ptr [rax+rax+00h]
0x180081df9  mov     rcx, [rsp+38h+hKey]; hKey
0x180081dfe  test    rcx, rcx
0x180081e01  jz      short loc_180081E0F
0x180081e03  call    cs:__imp_RegCloseKey
0x180081e0a  nop     dword ptr [rax+rax+00h]
0x180081e0f  mov     eax, ebx
0x180081e11  mov     rbx, [rsp+38h+arg_8]
0x180081e16  add     rsp, 30h
0x180081e1a  pop     rdi
0x180081e1b  retn
```
