# I_CertGetAutoUpdateFlags

- ea: `0x180009388`
- end: `0x180009420`
- name: `I_CertGetAutoUpdateFlags`
- size: `152`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180008a10`

## callees

- `0x180009388`
- `0x180009530`
- `0x1800095e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800093de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800093de`

## pseudocode

```c
__int64 I_CertGetAutoUpdateFlags()
{
  unsigned int v0; // ebx
  HKEY updated; // rdi
  LSTATUS v2; // eax
  DWORD v3; // ecx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  updated = OpenAutoUpdateKey(HKEY_LOCAL_MACHINE);
  if ( updated )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    v2 = RegQueryValueExW(updated, L"Flags", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v2 )
    {
      v3 = v2;
    }
    else
    {
      if ( Type == 4 && cbData == 4 )
      {
        v0 = Data;
        goto LABEL_5;
      }
      v3 = 13;
    }
    SetLastError(v3);
  }
LABEL_5:
  CloseRegistryKey(updated);
  return v0;
}

```

## disassembly

```asm
0x180009388  mov     [rsp+arg_18], rbx
0x18000938d  push    rdi
0x18000938e  sub     rsp, 30h
0x180009392  mov     rcx, 0FFFFFFFF80000002h
0x180009399  xor     ebx, ebx
0x18000939b  call    _OpenAutoUpdateKey
0x1800093a0  mov     rdi, rax
0x1800093a3  test    rax, rax
0x1800093a6  jz      short loc_1800093F0
0x1800093a8  lea     rax, [rsp+38h+cbData]
0x1800093ad  mov     [rsp+38h+Type], ebx
0x1800093b1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800093b6  lea     r9, [rsp+38h+Type]; lpType
0x1800093bb  lea     rax, [rsp+38h+Data]
0x1800093c0  mov     [rsp+38h+Data], ebx
0x1800093c4  xor     r8d, r8d; lpReserved
0x1800093c7  mov     [rsp+38h+lpData], rax; lpData
0x1800093cc  lea     rdx, aFlags; "Flags"
0x1800093d3  mov     [rsp+38h+cbData], 4
0x1800093db  mov     rcx, rdi; hKey
0x1800093de  call    cs:__imp_RegQueryValueExW
0x1800093e4  test    eax, eax
0x1800093e6  jz      short loc_180009405
0x1800093e8  mov     ecx, eax; dwErrCode
0x1800093ea  call    cs:__imp_SetLastError
0x1800093f0  mov     rcx, rdi; hKey
0x1800093f3  call    _CloseRegistryKey
0x1800093f8  mov     eax, ebx
0x1800093fa  mov     rbx, [rsp+38h+arg_18]
0x1800093ff  add     rsp, 30h
0x180009403  pop     rdi
0x180009404  retn
0x180009405  cmp     [rsp+38h+Type], 4
0x18000940a  jnz     short loc_180009419
0x18000940c  cmp     [rsp+38h+cbData], 4
0x180009411  jnz     short loc_180009419
0x180009413  mov     ebx, [rsp+38h+Data]
0x180009417  jmp     short loc_1800093F0
0x180009419  mov     ecx, 0Dh
0x18000941e  jmp     short loc_1800093EA
```
