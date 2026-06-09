# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180027074`
- end: `0x1800270c5`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180026628`
- `0x180027338`
- `0x180027800`

## callees

- `0x180026c90`
- `0x180027074`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002709f`
- `ADVAPI32!RegOpenKeyExW` at `0x18002709f`

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
0x180027074  push    rbx
0x180027076  sub     rsp, 40h
0x18002707a  mov     rbx, rcx
0x18002707d  mov     [rsp+48h+var_18], 0
0x180027086  mov     rax, r8
0x180027089  lea     rcx, [rsp+48h+var_18]
0x18002708e  mov     r10, rdx
0x180027091  mov     [rsp+48h+phkResult], rcx; phkResult
0x180027096  mov     rcx, r10; hKey
0x180027099  xor     r8d, r8d; ulOptions
0x18002709c  mov     rdx, rax; lpSubKey
0x18002709f  call    cs:__imp_RegOpenKeyExW
0x1800270a5  mov     edx, eax
0x1800270a7  test    eax, eax
0x1800270a9  jnz     short loc_1800270BD
0x1800270ab  mov     rcx, rbx; this
0x1800270ae  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800270b3  mov     edx, eax
0x1800270b5  mov     rax, [rsp+48h+var_18]
0x1800270ba  mov     [rbx], rax
0x1800270bd  mov     eax, edx
0x1800270bf  add     rsp, 40h
0x1800270c3  pop     rbx
0x1800270c4  retn
```
