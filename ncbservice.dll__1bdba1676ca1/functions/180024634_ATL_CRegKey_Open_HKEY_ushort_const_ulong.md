# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180024634`
- end: `0x180024685`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024918`
- `0x180024d50`

## callees

- `0x180024224`
- `0x180024634`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002465f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002465f`

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
0x180024634  push    rbx
0x180024636  sub     rsp, 40h
0x18002463a  mov     rax, r8
0x18002463d  mov     r10, rdx
0x180024640  mov     rbx, rcx
0x180024643  mov     [rsp+48h+var_18], 0
0x18002464c  lea     rcx, [rsp+48h+var_18]
0x180024651  mov     [rsp+48h+phkResult], rcx; phkResult
0x180024656  xor     r8d, r8d; ulOptions
0x180024659  mov     rdx, rax; lpSubKey
0x18002465c  mov     rcx, r10; hKey
0x18002465f  call    cs:__imp_RegOpenKeyExW
0x180024665  mov     edx, eax
0x180024667  test    eax, eax
0x180024669  jnz     short loc_18002467D
0x18002466b  mov     rcx, rbx; this
0x18002466e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180024673  mov     edx, eax
0x180024675  mov     rax, [rsp+48h+var_18]
0x18002467a  mov     [rbx], rax
0x18002467d  mov     eax, edx
0x18002467f  add     rsp, 40h
0x180024683  pop     rbx
0x180024684  retn
```
