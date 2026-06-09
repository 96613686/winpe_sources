# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x14000601c`
- end: `0x14000606d`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400066b8`
- `0x140006af0`

## callees

- `0x140005644`
- `0x14000601c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140006047`
- `ADVAPI32!RegOpenKeyExW` at `0x140006047`

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
0x14000601c  push    rbx
0x14000601e  sub     rsp, 40h
0x140006022  mov     rbx, rcx
0x140006025  mov     [rsp+48h+var_18], 0
0x14000602e  mov     rax, r8
0x140006031  lea     rcx, [rsp+48h+var_18]
0x140006036  mov     r10, rdx
0x140006039  mov     [rsp+48h+phkResult], rcx; phkResult
0x14000603e  mov     rcx, r10; hKey
0x140006041  xor     r8d, r8d; ulOptions
0x140006044  mov     rdx, rax; lpSubKey
0x140006047  call    cs:__imp_RegOpenKeyExW
0x14000604d  mov     edx, eax
0x14000604f  test    eax, eax
0x140006051  jnz     short loc_140006065
0x140006053  mov     rcx, rbx; this
0x140006056  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000605b  mov     edx, eax
0x14000605d  mov     rax, [rsp+48h+var_18]
0x140006062  mov     [rbx], rax
0x140006065  mov     eax, edx
0x140006067  add     rsp, 40h
0x14000606b  pop     rbx
0x14000606c  retn
```
