# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800146d4`
- end: `0x180014725`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800151dc`
- `0x1800155fc`
- `0x1800180bc`

## callees

- `0x180012144`
- `0x1800146d4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800146ff`
- `ADVAPI32!RegOpenKeyExW` at `0x1800146ff`

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
0x1800146d4  push    rbx
0x1800146d6  sub     rsp, 40h
0x1800146da  mov     rbx, rcx
0x1800146dd  mov     [rsp+48h+var_18], 0
0x1800146e6  mov     rax, r8
0x1800146e9  lea     rcx, [rsp+48h+var_18]
0x1800146ee  mov     r10, rdx
0x1800146f1  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800146f6  mov     rcx, r10; hKey
0x1800146f9  xor     r8d, r8d; ulOptions
0x1800146fc  mov     rdx, rax; lpSubKey
0x1800146ff  call    cs:__imp_RegOpenKeyExW
0x180014705  mov     edx, eax
0x180014707  test    eax, eax
0x180014709  jnz     short loc_18001471D
0x18001470b  mov     rcx, rbx; this
0x18001470e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014713  mov     edx, eax
0x180014715  mov     rax, [rsp+48h+var_18]
0x18001471a  mov     [rbx], rax
0x18001471d  mov     eax, edx
0x18001471f  add     rsp, 40h
0x180014723  pop     rbx
0x180014724  retn
```
