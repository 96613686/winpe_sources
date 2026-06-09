# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18000f788`
- end: `0x18000f7d9`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fa68`
- `0x18000fea0`

## callees

- `0x18000f1b4`
- `0x18000f788`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f7b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f7b3`

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
0x18000f788  push    rbx
0x18000f78a  sub     rsp, 40h
0x18000f78e  mov     rbx, rcx
0x18000f791  mov     [rsp+48h+var_18], 0
0x18000f79a  mov     rax, r8
0x18000f79d  lea     rcx, [rsp+48h+var_18]
0x18000f7a2  mov     r10, rdx
0x18000f7a5  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000f7aa  mov     rcx, r10; hKey
0x18000f7ad  xor     r8d, r8d; ulOptions
0x18000f7b0  mov     rdx, rax; lpSubKey
0x18000f7b3  call    cs:__imp_RegOpenKeyExW
0x18000f7b9  mov     edx, eax
0x18000f7bb  test    eax, eax
0x18000f7bd  jnz     short loc_18000F7D1
0x18000f7bf  mov     rcx, rbx; this
0x18000f7c2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f7c7  mov     edx, eax
0x18000f7c9  mov     rax, [rsp+48h+var_18]
0x18000f7ce  mov     [rbx], rax
0x18000f7d1  mov     eax, edx
0x18000f7d3  add     rsp, 40h
0x18000f7d7  pop     rbx
0x18000f7d8  retn
```
