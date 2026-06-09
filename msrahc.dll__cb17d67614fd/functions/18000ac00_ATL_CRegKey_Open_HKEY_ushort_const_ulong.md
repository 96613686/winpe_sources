# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000ac00`
- end: `0x18000ac51`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800099a8`
- `0x18000af48`
- `0x18000b44c`

## callees

- `0x18000a064`
- `0x18000ac00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000ac2b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ac2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ac00  push    rbx
0x18000ac02  sub     rsp, 40h
0x18000ac06  mov     rbx, rcx
0x18000ac09  mov     [rsp+48h+var_18], 0
0x18000ac12  mov     rax, r8
0x18000ac15  lea     rcx, [rsp+48h+var_18]
0x18000ac1a  mov     r10, rdx
0x18000ac1d  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000ac22  mov     rcx, r10; hKey
0x18000ac25  xor     r8d, r8d; ulOptions
0x18000ac28  mov     rdx, rax; lpSubKey
0x18000ac2b  call    cs:__imp_RegOpenKeyExW
0x18000ac31  mov     edx, eax
0x18000ac33  test    eax, eax
0x18000ac35  jnz     short loc_18000AC49
0x18000ac37  mov     rcx, rbx; this
0x18000ac3a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ac3f  mov     edx, eax
0x18000ac41  mov     rax, [rsp+48h+var_18]
0x18000ac46  mov     [rbx], rax
0x18000ac49  mov     eax, edx
0x18000ac4b  add     rsp, 40h
0x18000ac4f  pop     rbx
0x18000ac50  retn
```
