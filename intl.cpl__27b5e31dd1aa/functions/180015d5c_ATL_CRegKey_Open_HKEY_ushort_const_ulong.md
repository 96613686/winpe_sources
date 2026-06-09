# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180015d5c`
- end: `0x180015dad`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016038`
- `0x18001646c`

## callees

- `0x1800143d4`
- `0x180015d5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d87`

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
0x180015d5c  push    rbx
0x180015d5e  sub     rsp, 40h
0x180015d62  mov     rax, r8
0x180015d65  mov     r10, rdx
0x180015d68  mov     rbx, rcx
0x180015d6b  mov     [rsp+48h+var_18], 0
0x180015d74  lea     rcx, [rsp+48h+var_18]
0x180015d79  mov     [rsp+48h+phkResult], rcx; phkResult
0x180015d7e  xor     r8d, r8d; ulOptions
0x180015d81  mov     rdx, rax; lpSubKey
0x180015d84  mov     rcx, r10; hKey
0x180015d87  call    cs:__imp_RegOpenKeyExW
0x180015d8d  mov     edx, eax
0x180015d8f  test    eax, eax
0x180015d91  jnz     short loc_180015DA5
0x180015d93  mov     rcx, rbx; this
0x180015d96  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015d9b  mov     edx, eax
0x180015d9d  mov     rax, [rsp+48h+var_18]
0x180015da2  mov     [rbx], rax
0x180015da5  mov     eax, edx
0x180015da7  add     rsp, 40h
0x180015dab  pop     rbx
0x180015dac  retn
```
