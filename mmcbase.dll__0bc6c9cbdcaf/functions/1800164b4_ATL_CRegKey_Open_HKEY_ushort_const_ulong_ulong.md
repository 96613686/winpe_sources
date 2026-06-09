# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)

- ea: `0x1800164b4`
- end: `0x180016505`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008670`
- `0x180015ca0`
- `0x180016738`

## callees

- `0x180008cdc`
- `0x1800164b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800164df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800164df`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x1800164b4  push    rbx
0x1800164b6  sub     rsp, 40h
0x1800164ba  mov     rbx, rcx
0x1800164bd  mov     [rsp+48h+var_18], 0
0x1800164c6  mov     rax, r8
0x1800164c9  lea     rcx, [rsp+48h+var_18]
0x1800164ce  mov     r10, rdx
0x1800164d1  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800164d6  mov     rcx, r10; hKey
0x1800164d9  xor     r8d, r8d; ulOptions
0x1800164dc  mov     rdx, rax; lpSubKey
0x1800164df  call    cs:__imp_RegOpenKeyExW
0x1800164e5  mov     edx, eax
0x1800164e7  test    eax, eax
0x1800164e9  jnz     short loc_1800164FD
0x1800164eb  mov     rcx, rbx; this
0x1800164ee  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800164f3  mov     edx, eax
0x1800164f5  mov     rax, [rsp+48h+var_18]
0x1800164fa  mov     [rbx], rax
0x1800164fd  mov     eax, edx
0x1800164ff  add     rsp, 40h
0x180016503  pop     rbx
0x180016504  retn
```
