# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180010818`
- end: `0x180010869`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f430`
- `0x180010bb8`
- `0x1800110f4`

## callees

- `0x18000fa64`
- `0x180010818`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180010843`
- `ADVAPI32!RegOpenKeyExW` at `0x180010843`

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
0x180010818  push    rbx
0x18001081a  sub     rsp, 40h
0x18001081e  mov     rbx, rcx
0x180010821  mov     [rsp+48h+var_18], 0
0x18001082a  mov     rax, r8
0x18001082d  lea     rcx, [rsp+48h+var_18]
0x180010832  mov     r10, rdx
0x180010835  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001083a  mov     rcx, r10; hKey
0x18001083d  xor     r8d, r8d; ulOptions
0x180010840  mov     rdx, rax; lpSubKey
0x180010843  call    cs:__imp_RegOpenKeyExW
0x180010849  mov     edx, eax
0x18001084b  test    eax, eax
0x18001084d  jnz     short loc_180010861
0x18001084f  mov     rcx, rbx; this
0x180010852  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010857  mov     edx, eax
0x180010859  mov     rax, [rsp+48h+var_18]
0x18001085e  mov     [rbx], rax
0x180010861  mov     eax, edx
0x180010863  add     rsp, 40h
0x180010867  pop     rbx
0x180010868  retn
```
