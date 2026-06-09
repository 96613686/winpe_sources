# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800128a4`
- end: `0x180012911`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `109`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014780`
- `0x180014d38`

## callees

- `0x180001710`
- `0x18000aeb8`
- `0x1800128a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800128de`
- `ADVAPI32!RegOpenKeyExW` at `0x1800128de`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // ecx
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
0x1800128a4  push    rbx
0x1800128a6  sub     rsp, 40h
0x1800128aa  mov     rax, cs:__security_cookie
0x1800128b1  xor     rax, rsp
0x1800128b4  mov     [rsp+48h+var_10], rax
0x1800128b9  mov     rbx, rcx
0x1800128bc  mov     [rsp+48h+var_18], 0
0x1800128c5  mov     r10, r8
0x1800128c8  lea     rcx, [rsp+48h+var_18]
0x1800128cd  mov     rax, rdx
0x1800128d0  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800128d5  mov     rcx, rax; hKey
0x1800128d8  xor     r8d, r8d; ulOptions
0x1800128db  mov     rdx, r10; lpSubKey
0x1800128de  call    cs:__imp_RegOpenKeyExW
0x1800128e4  mov     ecx, eax
0x1800128e6  test    eax, eax
0x1800128e8  jnz     short loc_1800128FC
0x1800128ea  mov     rcx, rbx; this
0x1800128ed  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800128f2  mov     ecx, eax
0x1800128f4  mov     rax, [rsp+48h+var_18]
0x1800128f9  mov     [rbx], rax
0x1800128fc  mov     eax, ecx
0x1800128fe  mov     rcx, [rsp+48h+var_10]
0x180012903  xor     rcx, rsp; StackCookie
0x180012906  call    __security_check_cookie
0x18001290b  add     rsp, 40h
0x18001290f  pop     rbx
0x180012910  retn
```
