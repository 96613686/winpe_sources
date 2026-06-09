# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180019ad0`
- end: `0x180019b21`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018020`
- `0x18001a2b8`
- `0x18001a8b0`

## callees

- `0x180018494`
- `0x180019ad0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019afb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019afb`

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
0x180019ad0  push    rbx
0x180019ad2  sub     rsp, 40h
0x180019ad6  mov     rbx, rcx
0x180019ad9  mov     [rsp+48h+var_18], 0
0x180019ae2  mov     rax, r8
0x180019ae5  lea     rcx, [rsp+48h+var_18]
0x180019aea  mov     r10, rdx
0x180019aed  mov     [rsp+48h+phkResult], rcx; phkResult
0x180019af2  mov     rcx, r10; hKey
0x180019af5  xor     r8d, r8d; ulOptions
0x180019af8  mov     rdx, rax; lpSubKey
0x180019afb  call    cs:__imp_RegOpenKeyExW
0x180019b01  mov     edx, eax
0x180019b03  test    eax, eax
0x180019b05  jnz     short loc_180019B19
0x180019b07  mov     rcx, rbx; this
0x180019b0a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019b0f  mov     edx, eax
0x180019b11  mov     rax, [rsp+48h+var_18]
0x180019b16  mov     [rbx], rax
0x180019b19  mov     eax, edx
0x180019b1b  add     rsp, 40h
0x180019b1f  pop     rbx
0x180019b20  retn
```
