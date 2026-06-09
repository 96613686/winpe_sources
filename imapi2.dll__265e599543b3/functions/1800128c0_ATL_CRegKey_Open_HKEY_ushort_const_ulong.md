# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800128c0`
- end: `0x180012911`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012d14`
- `0x180013134`
- `0x180041a34`

## callees

- `0x180011c94`
- `0x1800128c0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800128eb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800128eb`

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
0x1800128c0  push    rbx
0x1800128c2  sub     rsp, 40h
0x1800128c6  mov     rbx, rcx
0x1800128c9  mov     [rsp+48h+var_18], 0
0x1800128d2  mov     rax, r8
0x1800128d5  lea     rcx, [rsp+48h+var_18]
0x1800128da  mov     r10, rdx
0x1800128dd  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800128e2  mov     rcx, r10; hKey
0x1800128e5  xor     r8d, r8d; ulOptions
0x1800128e8  mov     rdx, rax; lpSubKey
0x1800128eb  call    cs:__imp_RegOpenKeyExW
0x1800128f1  mov     edx, eax
0x1800128f3  test    eax, eax
0x1800128f5  jnz     short loc_180012909
0x1800128f7  mov     rcx, rbx; this
0x1800128fa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800128ff  mov     edx, eax
0x180012901  mov     rax, [rsp+48h+var_18]
0x180012906  mov     [rbx], rax
0x180012909  mov     eax, edx
0x18001290b  add     rsp, 40h
0x18001290f  pop     rbx
0x180012910  retn
```
