# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000747c`
- end: `0x1800074cd`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004860`
- `0x1800078c8`
- `0x180007e04`

## callees

- `0x180004f44`
- `0x18000747c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800074a7`
- `ADVAPI32!RegOpenKeyExW` at `0x1800074a7`

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
0x18000747c  push    rbx
0x18000747e  sub     rsp, 40h
0x180007482  mov     rbx, rcx
0x180007485  mov     [rsp+48h+var_18], 0
0x18000748e  mov     rax, r8
0x180007491  lea     rcx, [rsp+48h+var_18]
0x180007496  mov     r10, rdx
0x180007499  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000749e  mov     rcx, r10; hKey
0x1800074a1  xor     r8d, r8d; ulOptions
0x1800074a4  mov     rdx, rax; lpSubKey
0x1800074a7  call    cs:__imp_RegOpenKeyExW
0x1800074ad  mov     edx, eax
0x1800074af  test    eax, eax
0x1800074b1  jnz     short loc_1800074C5
0x1800074b3  mov     rcx, rbx; this
0x1800074b6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800074bb  mov     edx, eax
0x1800074bd  mov     rax, [rsp+48h+var_18]
0x1800074c2  mov     [rbx], rax
0x1800074c5  mov     eax, edx
0x1800074c7  add     rsp, 40h
0x1800074cb  pop     rbx
0x1800074cc  retn
```
