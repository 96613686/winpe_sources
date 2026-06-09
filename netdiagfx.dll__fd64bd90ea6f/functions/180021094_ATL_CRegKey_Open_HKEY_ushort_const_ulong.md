# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180021094`
- end: `0x1800210e5`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f510`
- `0x18001f71c`
- `0x18001f924`
- `0x18001fe0c`
- `0x180020024`
- `0x1800203c0`
- `0x180020698`
- `0x180020abc`
- `0x180020ce4`
- `0x180029584`
- `0x180029788`

## callees

- `0x18001f0a4`
- `0x180021094`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800210bf`
- `ADVAPI32!RegOpenKeyExW` at `0x1800210bf`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x180021094  push    rbx
0x180021096  sub     rsp, 40h
0x18002109a  mov     rbx, rcx
0x18002109d  mov     [rsp+48h+var_18], 0
0x1800210a6  mov     rax, r8
0x1800210a9  lea     rcx, [rsp+48h+var_18]
0x1800210ae  mov     r10, rdx
0x1800210b1  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800210b6  mov     rcx, r10; hKey
0x1800210b9  xor     r8d, r8d; ulOptions
0x1800210bc  mov     rdx, rax; lpSubKey
0x1800210bf  call    cs:__imp_RegOpenKeyExW
0x1800210c5  mov     edx, eax
0x1800210c7  test    eax, eax
0x1800210c9  jnz     short loc_1800210DD
0x1800210cb  mov     rcx, rbx; this
0x1800210ce  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800210d3  mov     edx, eax
0x1800210d5  mov     rax, [rsp+48h+var_18]
0x1800210da  mov     [rbx], rax
0x1800210dd  mov     eax, edx
0x1800210df  add     rsp, 40h
0x1800210e3  pop     rbx
0x1800210e4  retn
```
