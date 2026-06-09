# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000d074`
- end: `0x18000d0c5`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d348`
- `0x18000d764`

## callees

- `0x18000c954`
- `0x18000d074`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d09f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d09f`

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
0x18000d074  push    rbx
0x18000d076  sub     rsp, 40h
0x18000d07a  mov     rbx, rcx
0x18000d07d  mov     [rsp+48h+var_18], 0
0x18000d086  mov     rax, r8
0x18000d089  lea     rcx, [rsp+48h+var_18]
0x18000d08e  mov     r10, rdx
0x18000d091  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000d096  mov     rcx, r10; hKey
0x18000d099  xor     r8d, r8d; ulOptions
0x18000d09c  mov     rdx, rax; lpSubKey
0x18000d09f  call    cs:__imp_RegOpenKeyExW
0x18000d0a5  mov     edx, eax
0x18000d0a7  test    eax, eax
0x18000d0a9  jnz     short loc_18000D0BD
0x18000d0ab  mov     rcx, rbx; this
0x18000d0ae  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d0b3  mov     edx, eax
0x18000d0b5  mov     rax, [rsp+48h+var_18]
0x18000d0ba  mov     [rbx], rax
0x18000d0bd  mov     eax, edx
0x18000d0bf  add     rsp, 40h
0x18000d0c3  pop     rbx
0x18000d0c4  retn
```
