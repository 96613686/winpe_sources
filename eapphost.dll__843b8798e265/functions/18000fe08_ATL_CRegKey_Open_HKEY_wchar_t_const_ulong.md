# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18000fe08`
- end: `0x18000fe60`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `88`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001012c`
- `0x1800105a0`

## callees

- `0x18000f7b0`
- `0x18000fe08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fe33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fe33`

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
0x18000fe08  push    rbx
0x18000fe0a  sub     rsp, 40h
0x18000fe0e  mov     rbx, rcx
0x18000fe11  mov     [rsp+48h+var_18], 0
0x18000fe1a  mov     rax, r8
0x18000fe1d  lea     rcx, [rsp+48h+var_18]
0x18000fe22  mov     r10, rdx
0x18000fe25  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000fe2a  mov     rcx, r10; hKey
0x18000fe2d  xor     r8d, r8d; ulOptions
0x18000fe30  mov     rdx, rax; lpSubKey
0x18000fe33  call    cs:__imp_RegOpenKeyExW
0x18000fe3a  nop     dword ptr [rax+rax+00h]
0x18000fe3f  mov     edx, eax
0x18000fe41  test    eax, eax
0x18000fe43  jnz     short loc_18000FE57
0x18000fe45  mov     rcx, rbx; this
0x18000fe48  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fe4d  mov     edx, eax
0x18000fe4f  mov     rax, [rsp+48h+var_18]
0x18000fe54  mov     [rbx], rax
0x18000fe57  mov     eax, edx
0x18000fe59  add     rsp, 40h
0x18000fe5d  pop     rbx
0x18000fe5e  retn
```
