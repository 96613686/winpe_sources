# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000fc40`
- end: `0x18000fc98`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `88`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f760`
- `0x18002099c`

## callees

- `0x18000f63c`
- `0x18000fc40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc6b`

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
0x18000fc40  push    rbx
0x18000fc42  sub     rsp, 40h
0x18000fc46  mov     rbx, rcx
0x18000fc49  mov     [rsp+48h+var_18], 0
0x18000fc52  mov     rax, r8
0x18000fc55  lea     rcx, [rsp+48h+var_18]
0x18000fc5a  mov     r10, rdx
0x18000fc5d  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000fc62  mov     rcx, r10; hKey
0x18000fc65  xor     r8d, r8d; ulOptions
0x18000fc68  mov     rdx, rax; lpSubKey
0x18000fc6b  call    cs:__imp_RegOpenKeyExW
0x18000fc72  nop     dword ptr [rax+rax+00h]
0x18000fc77  mov     edx, eax
0x18000fc79  test    eax, eax
0x18000fc7b  jnz     short loc_18000FC8F
0x18000fc7d  mov     rcx, rbx; this
0x18000fc80  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fc85  mov     edx, eax
0x18000fc87  mov     rax, [rsp+48h+var_18]
0x18000fc8c  mov     [rbx], rax
0x18000fc8f  mov     eax, edx
0x18000fc91  add     rsp, 40h
0x18000fc95  pop     rbx
0x18000fc96  retn
```
