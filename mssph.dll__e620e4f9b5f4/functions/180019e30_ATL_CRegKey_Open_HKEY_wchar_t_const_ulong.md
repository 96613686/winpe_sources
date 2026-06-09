# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x180019e30`
- end: `0x180019e81`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017670`
- `0x18001a304`
- `0x18001a7d4`

## callees

- `0x180017ae4`
- `0x180019e30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e5b`

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
0x180019e30  push    rbx
0x180019e32  sub     rsp, 40h
0x180019e36  mov     rbx, rcx
0x180019e39  mov     [rsp+48h+var_18], 0
0x180019e42  mov     rax, r8
0x180019e45  lea     rcx, [rsp+48h+var_18]
0x180019e4a  mov     r10, rdx
0x180019e4d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180019e52  mov     rcx, r10; hKey
0x180019e55  xor     r8d, r8d; ulOptions
0x180019e58  mov     rdx, rax; lpSubKey
0x180019e5b  call    cs:__imp_RegOpenKeyExW
0x180019e61  mov     edx, eax
0x180019e63  test    eax, eax
0x180019e65  jnz     short loc_180019E79
0x180019e67  mov     rcx, rbx; this
0x180019e6a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019e6f  mov     edx, eax
0x180019e71  mov     rax, [rsp+48h+var_18]
0x180019e76  mov     [rbx], rax
0x180019e79  mov     eax, edx
0x180019e7b  add     rsp, 40h
0x180019e7f  pop     rbx
0x180019e80  retn
```
