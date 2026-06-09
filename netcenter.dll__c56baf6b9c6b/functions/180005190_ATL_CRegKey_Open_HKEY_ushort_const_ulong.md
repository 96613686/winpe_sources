# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180005190`
- end: `0x1800051e1`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800054d8`
- `0x180005910`

## callees

- `0x180004c64`
- `0x180005190`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800051bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800051bb`

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
0x180005190  push    rbx
0x180005192  sub     rsp, 40h
0x180005196  mov     rbx, rcx
0x180005199  mov     [rsp+48h+var_18], 0
0x1800051a2  mov     rax, r8
0x1800051a5  lea     rcx, [rsp+48h+var_18]
0x1800051aa  mov     r10, rdx
0x1800051ad  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800051b2  mov     rcx, r10; hKey
0x1800051b5  xor     r8d, r8d; ulOptions
0x1800051b8  mov     rdx, rax; lpSubKey
0x1800051bb  call    cs:__imp_RegOpenKeyExW
0x1800051c1  mov     edx, eax
0x1800051c3  test    eax, eax
0x1800051c5  jnz     short loc_1800051D9
0x1800051c7  mov     rcx, rbx; this
0x1800051ca  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800051cf  mov     edx, eax
0x1800051d1  mov     rax, [rsp+48h+var_18]
0x1800051d6  mov     [rbx], rax
0x1800051d9  mov     eax, edx
0x1800051db  add     rsp, 40h
0x1800051df  pop     rbx
0x1800051e0  retn
```
