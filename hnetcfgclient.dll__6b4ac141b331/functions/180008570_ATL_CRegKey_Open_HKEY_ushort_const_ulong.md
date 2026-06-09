# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180008570`
- end: `0x1800085c1`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800076f8`
- `0x180008998`
- `0x180008e68`
- `0x18002a31c`
- `0x18002a3ec`

## callees

- `0x180007b74`
- `0x180008570`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000859b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000859b`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x180008570  push    rbx
0x180008572  sub     rsp, 40h
0x180008576  mov     rbx, rcx
0x180008579  mov     [rsp+48h+var_18], 0
0x180008582  mov     rax, r8
0x180008585  lea     rcx, [rsp+48h+var_18]
0x18000858a  mov     r10, rdx
0x18000858d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180008592  mov     rcx, r10; hKey
0x180008595  xor     r8d, r8d; ulOptions
0x180008598  mov     rdx, rax; lpSubKey
0x18000859b  call    cs:__imp_RegOpenKeyExW
0x1800085a1  mov     edx, eax
0x1800085a3  test    eax, eax
0x1800085a5  jnz     short loc_1800085B9
0x1800085a7  mov     rcx, rbx; this
0x1800085aa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800085af  mov     edx, eax
0x1800085b1  mov     rax, [rsp+48h+var_18]
0x1800085b6  mov     [rbx], rax
0x1800085b9  mov     eax, edx
0x1800085bb  add     rsp, 40h
0x1800085bf  pop     rbx
0x1800085c0  retn
```
