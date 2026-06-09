# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong,ulong)

- ea: `0x180010074`
- end: `0x1800100c5`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WKK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011038`
- `0x180011504`

## callees

- `0x18000cb08`
- `0x180010074`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001009f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001009f`

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
0x180010074  push    rbx
0x180010076  sub     rsp, 40h
0x18001007a  mov     rbx, rcx
0x18001007d  mov     [rsp+48h+var_18], 0
0x180010086  mov     rax, r8
0x180010089  lea     rcx, [rsp+48h+var_18]
0x18001008e  mov     r10, rdx
0x180010091  mov     [rsp+48h+phkResult], rcx; phkResult
0x180010096  mov     rcx, r10; hKey
0x180010099  xor     r8d, r8d; ulOptions
0x18001009c  mov     rdx, rax; lpSubKey
0x18001009f  call    cs:__imp_RegOpenKeyExW
0x1800100a5  mov     edx, eax
0x1800100a7  test    eax, eax
0x1800100a9  jnz     short loc_1800100BD
0x1800100ab  mov     rcx, rbx; this
0x1800100ae  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800100b3  mov     edx, eax
0x1800100b5  mov     rax, [rsp+48h+var_18]
0x1800100ba  mov     [rbx], rax
0x1800100bd  mov     eax, edx
0x1800100bf  add     rsp, 40h
0x1800100c3  pop     rbx
0x1800100c4  retn
```
