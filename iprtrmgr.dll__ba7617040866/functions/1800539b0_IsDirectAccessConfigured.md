# IsDirectAccessConfigured

- ea: `0x1800539b0`
- end: `0x180053a6b`
- name: `IsDirectAccessConfigured`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180050434`

## callees

- `0x1800539b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180053a48`
- `ADVAPI32!RegCloseKey` at `0x180053a58`
- `ADVAPI32!RegCloseKey` at `0x180053a48`
- `ADVAPI32!RegCloseKey` at `0x180053a58`
- `ADVAPI32!RegOpenKeyExW` at `0x1800539f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800539f0`
- `ADVAPI32!RegQueryValueExW` at `0x180053a20`
- `ADVAPI32!RegQueryValueExW` at `0x180053a20`

## string_xrefs

- `0x1800539d5`: `System\CurrentControlSet\Services\RamgmtSvc\Config`

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
0x1800539b0  mov     r11, rsp
0x1800539b3  mov     [r11+10h], rbx
0x1800539b7  mov     [r11+8], rcx
0x1800539bb  push    rdi
0x1800539bc  sub     rsp, 30h
0x1800539c0  mov     rdi, rdx
0x1800539c3  mov     dword ptr [rdx], 0
0x1800539c9  lea     rax, [r11+8]
0x1800539cd  mov     qword ptr [r11+8], 0
0x1800539d5  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\Ra"...
0x1800539dc  mov     [r11-18h], rax
0x1800539e0  mov     r9d, 20019h; samDesired
0x1800539e6  xor     r8d, r8d; ulOptions
0x1800539e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800539f0  call    cs:__imp_RegOpenKeyExW
0x1800539f6  mov     ebx, eax
0x1800539f8  test    eax, eax
0x1800539fa  jnz     short loc_180053A41
0x1800539fc  mov     rcx, [rsp+38h+hKey]; hKey
0x180053a01  lea     rdx, aServergpo; "ServerGPO"
0x180053a08  mov     [rsp+38h+lpcbData], 0; lpcbData
0x180053a11  xor     r9d, r9d; lpType
0x180053a14  xor     r8d, r8d; lpReserved
0x180053a17  mov     [rsp+38h+lpData], 0; lpData
0x180053a20  call    cs:__imp_RegQueryValueExW
0x180053a26  mov     ebx, eax
0x180053a28  test    eax, eax
0x180053a2a  jnz     short loc_180053A34
0x180053a2c  mov     dword ptr [rdi], 1
0x180053a32  jmp     short loc_180053A41
0x180053a34  cmp     eax, 2
0x180053a37  jnz     short loc_180053A41
0x180053a39  mov     dword ptr [rdi], 0
0x180053a3f  xor     ebx, ebx
0x180053a41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053a48  call    cs:__imp_RegCloseKey
0x180053a4e  mov     rcx, [rsp+38h+hKey]; hKey
0x180053a53  test    rcx, rcx
0x180053a56  jz      short loc_180053A5E
0x180053a58  call    cs:__imp_RegCloseKey
0x180053a5e  mov     eax, ebx
0x180053a60  mov     rbx, [rsp+38h+arg_8]
0x180053a65  add     rsp, 30h
0x180053a69  pop     rdi
0x180053a6a  retn
```
