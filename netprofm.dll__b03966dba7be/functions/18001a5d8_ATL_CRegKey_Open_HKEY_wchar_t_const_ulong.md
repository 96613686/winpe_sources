# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18001a5d8`
- end: `0x18001a64b`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001690c`

## callees

- `0x1800120d0`
- `0x180016fb8`
- `0x18001a5d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a618`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a618`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // ecx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v4 )
  {
    v4 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v4;
}

```

## disassembly

```asm
0x18001a5d8  push    rbx
0x18001a5da  sub     rsp, 40h
0x18001a5de  mov     rax, cs:__security_cookie
0x18001a5e5  xor     rax, rsp
0x18001a5e8  mov     [rsp+48h+var_10], rax
0x18001a5ed  mov     rbx, rcx
0x18001a5f0  mov     [rsp+48h+var_18], 0
0x18001a5f9  mov     r10, r8
0x18001a5fc  lea     rcx, [rsp+48h+var_18]
0x18001a601  mov     rax, rdx
0x18001a604  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001a609  mov     rcx, rax; hKey
0x18001a60c  mov     r9d, 20019h; samDesired
0x18001a612  xor     r8d, r8d; ulOptions
0x18001a615  mov     rdx, r10; lpSubKey
0x18001a618  call    cs:__imp_RegOpenKeyExW
0x18001a61e  mov     ecx, eax
0x18001a620  test    eax, eax
0x18001a622  jnz     short loc_18001A636
0x18001a624  mov     rcx, rbx; this
0x18001a627  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a62c  mov     ecx, eax
0x18001a62e  mov     rax, [rsp+48h+var_18]
0x18001a633  mov     [rbx], rax
0x18001a636  mov     eax, ecx
0x18001a638  mov     rcx, [rsp+48h+var_10]
0x18001a63d  xor     rcx, rsp; StackCookie
0x18001a640  call    __security_check_cookie
0x18001a645  add     rsp, 40h
0x18001a649  pop     rbx
0x18001a64a  retn
```
