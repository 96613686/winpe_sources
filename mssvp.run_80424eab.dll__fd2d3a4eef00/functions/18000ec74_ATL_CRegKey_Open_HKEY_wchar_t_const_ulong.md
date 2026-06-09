# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18000ec74`
- end: `0x18000ecc5`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bee8`
- `0x180010154`
- `0x180010624`
- `0x18002d71c`
- `0x18002fa78`

## callees

- `0x18000c344`
- `0x18000ec74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec9f`

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
0x18000ec74  push    rbx
0x18000ec76  sub     rsp, 40h
0x18000ec7a  mov     rbx, rcx
0x18000ec7d  mov     [rsp+48h+var_18], 0
0x18000ec86  mov     rax, r8
0x18000ec89  lea     rcx, [rsp+48h+var_18]
0x18000ec8e  mov     r10, rdx
0x18000ec91  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000ec96  mov     rcx, r10; hKey
0x18000ec99  xor     r8d, r8d; ulOptions
0x18000ec9c  mov     rdx, rax; lpSubKey
0x18000ec9f  call    cs:__imp_RegOpenKeyExW
0x18000eca5  mov     edx, eax
0x18000eca7  test    eax, eax
0x18000eca9  jnz     short loc_18000ECBD
0x18000ecab  mov     rcx, rbx; this
0x18000ecae  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ecb3  mov     edx, eax
0x18000ecb5  mov     rax, [rsp+48h+var_18]
0x18000ecba  mov     [rbx], rax
0x18000ecbd  mov     eax, edx
0x18000ecbf  add     rsp, 40h
0x18000ecc3  pop     rbx
0x18000ecc4  retn
```
