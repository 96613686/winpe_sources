# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000517c`
- end: `0x1800051cd`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005658`
- `0x180005a90`
- `0x180006b44`

## callees

- `0x180004464`
- `0x18000517c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800051a7`
- `ADVAPI32!RegOpenKeyExW` at `0x1800051a7`

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
0x18000517c  push    rbx
0x18000517e  sub     rsp, 40h
0x180005182  mov     rbx, rcx
0x180005185  mov     [rsp+48h+var_18], 0
0x18000518e  mov     rax, r8
0x180005191  lea     rcx, [rsp+48h+var_18]
0x180005196  mov     r10, rdx
0x180005199  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000519e  mov     rcx, r10; hKey
0x1800051a1  xor     r8d, r8d; ulOptions
0x1800051a4  mov     rdx, rax; lpSubKey
0x1800051a7  call    cs:__imp_RegOpenKeyExW
0x1800051ad  mov     edx, eax
0x1800051af  test    eax, eax
0x1800051b1  jnz     short loc_1800051C5
0x1800051b3  mov     rcx, rbx; this
0x1800051b6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800051bb  mov     edx, eax
0x1800051bd  mov     rax, [rsp+48h+var_18]
0x1800051c2  mov     [rbx], rax
0x1800051c5  mov     eax, edx
0x1800051c7  add     rsp, 40h
0x1800051cb  pop     rbx
0x1800051cc  retn
```
