# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18001a50c`
- end: `0x18001a563`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `87`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a438`
- `0x1800ceb80`
- `0x1800cee94`

## callees

- `0x18001a50c`
- `0x18001a56c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a53d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a53d`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v4 )
  {
    v4 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v4;
}

```

## disassembly

```asm
0x18001a50c  push    rbx
0x18001a50e  sub     rsp, 40h
0x18001a512  mov     rbx, rcx
0x18001a515  mov     [rsp+48h+var_18], 0
0x18001a51e  mov     rax, r8
0x18001a521  lea     rcx, [rsp+48h+var_18]
0x18001a526  mov     r10, rdx
0x18001a529  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001a52e  mov     rcx, r10; hKey
0x18001a531  mov     r9d, 20019h; samDesired
0x18001a537  xor     r8d, r8d; ulOptions
0x18001a53a  mov     rdx, rax; lpSubKey
0x18001a53d  call    cs:__imp_RegOpenKeyExW
0x18001a543  mov     edx, eax
0x18001a545  test    eax, eax
0x18001a547  jnz     short loc_18001A55B
0x18001a549  mov     rcx, rbx; this
0x18001a54c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a551  mov     edx, eax
0x18001a553  mov     rax, [rsp+48h+var_18]
0x18001a558  mov     [rbx], rax
0x18001a55b  mov     eax, edx
0x18001a55d  add     rsp, 40h
0x18001a561  pop     rbx
0x18001a562  retn
```
