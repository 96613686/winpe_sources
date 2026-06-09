# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180004570`
- end: `0x1800045cd`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `93`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800045d4`
- `0x180004788`
- `0x180004ae4`

## callees

- `0x180004570`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045a1`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(HKEY *this, HKEY a2, const unsigned __int16 *a3)
{
  unsigned int v4; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(a2, a3, 0, 0xF003Fu, &phkResult);
  if ( !v4 )
  {
    if ( *this )
      v4 = RegCloseKey(*this);
    *this = phkResult;
  }
  return v4;
}

```

## disassembly

```asm
0x180004570  push    rbx
0x180004572  sub     rsp, 40h
0x180004576  mov     rbx, rcx
0x180004579  mov     [rsp+48h+var_18], 0
0x180004582  mov     rax, r8
0x180004585  lea     rcx, [rsp+48h+var_18]
0x18000458a  mov     r10, rdx
0x18000458d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180004592  mov     rcx, r10; hKey
0x180004595  mov     r9d, 0F003Fh; samDesired
0x18000459b  xor     r8d, r8d; ulOptions
0x18000459e  mov     rdx, rax; lpSubKey
0x1800045a1  call    cs:__imp_RegOpenKeyExW
0x1800045a7  mov     edx, eax
0x1800045a9  test    eax, eax
0x1800045ab  jnz     short loc_1800045C5
0x1800045ad  mov     rcx, [rbx]; hKey
0x1800045b0  test    rcx, rcx
0x1800045b3  jz      short loc_1800045BD
0x1800045b5  call    cs:__imp_RegCloseKey
0x1800045bb  mov     edx, eax
0x1800045bd  mov     rax, [rsp+48h+var_18]
0x1800045c2  mov     [rbx], rax
0x1800045c5  mov     eax, edx
0x1800045c7  add     rsp, 40h
0x1800045cb  pop     rbx
0x1800045cc  retn
```
