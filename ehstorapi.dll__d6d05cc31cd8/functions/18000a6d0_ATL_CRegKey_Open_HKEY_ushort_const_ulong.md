# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000a6d0`
- end: `0x18000a721`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a9f8`
- `0x18000ae30`

## callees

- `0x180009a94`
- `0x18000a6d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000a6fb`
- `ADVAPI32!RegOpenKeyExW` at `0x18000a6fb`

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
0x18000a6d0  push    rbx
0x18000a6d2  sub     rsp, 40h
0x18000a6d6  mov     rbx, rcx
0x18000a6d9  mov     [rsp+48h+var_18], 0
0x18000a6e2  mov     rax, r8
0x18000a6e5  lea     rcx, [rsp+48h+var_18]
0x18000a6ea  mov     r10, rdx
0x18000a6ed  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000a6f2  mov     rcx, r10; hKey
0x18000a6f5  xor     r8d, r8d; ulOptions
0x18000a6f8  mov     rdx, rax; lpSubKey
0x18000a6fb  call    cs:__imp_RegOpenKeyExW
0x18000a701  mov     edx, eax
0x18000a703  test    eax, eax
0x18000a705  jnz     short loc_18000A719
0x18000a707  mov     rcx, rbx; this
0x18000a70a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000a70f  mov     edx, eax
0x18000a711  mov     rax, [rsp+48h+var_18]
0x18000a716  mov     [rbx], rax
0x18000a719  mov     eax, edx
0x18000a71b  add     rsp, 40h
0x18000a71f  pop     rbx
0x18000a720  retn
```
