# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000c9f4`
- end: `0x18000ca45`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007214`
- `0x18000dcc8`
- `0x18000e1a8`

## callees

- `0x180007b44`
- `0x18000c9f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca1f`

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
0x18000c9f4  push    rbx
0x18000c9f6  sub     rsp, 40h
0x18000c9fa  mov     rbx, rcx
0x18000c9fd  mov     [rsp+48h+var_18], 0
0x18000ca06  mov     rax, r8
0x18000ca09  lea     rcx, [rsp+48h+var_18]
0x18000ca0e  mov     r10, rdx
0x18000ca11  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000ca16  mov     rcx, r10; hKey
0x18000ca19  xor     r8d, r8d; ulOptions
0x18000ca1c  mov     rdx, rax; lpSubKey
0x18000ca1f  call    cs:__imp_RegOpenKeyExW
0x18000ca25  mov     edx, eax
0x18000ca27  test    eax, eax
0x18000ca29  jnz     short loc_18000CA3D
0x18000ca2b  mov     rcx, rbx; this
0x18000ca2e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ca33  mov     edx, eax
0x18000ca35  mov     rax, [rsp+48h+var_18]
0x18000ca3a  mov     [rbx], rax
0x18000ca3d  mov     eax, edx
0x18000ca3f  add     rsp, 40h
0x18000ca43  pop     rbx
0x18000ca44  retn
```
