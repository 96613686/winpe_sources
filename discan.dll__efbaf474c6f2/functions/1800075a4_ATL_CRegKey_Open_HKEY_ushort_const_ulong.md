# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800075a4`
- end: `0x1800075fb`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `87`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006d40`
- `0x180007f18`

## callees

- `0x1800071c8`
- `0x1800075a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800075d5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800075d5`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v4 )
  {
    v4 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v4;
}

```

## disassembly

```asm
0x1800075a4  push    rbx
0x1800075a6  sub     rsp, 40h
0x1800075aa  mov     rbx, rcx
0x1800075ad  mov     [rsp+48h+var_18], 0
0x1800075b6  mov     rax, r8
0x1800075b9  lea     rcx, [rsp+48h+var_18]
0x1800075be  mov     r10, rdx
0x1800075c1  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800075c6  mov     rcx, r10; hKey
0x1800075c9  mov     r9d, 20019h; samDesired
0x1800075cf  xor     r8d, r8d; ulOptions
0x1800075d2  mov     rdx, rax; lpSubKey
0x1800075d5  call    cs:__imp_RegOpenKeyExW
0x1800075db  mov     edx, eax
0x1800075dd  test    eax, eax
0x1800075df  jnz     short loc_1800075F3
0x1800075e1  mov     rcx, rbx; this
0x1800075e4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800075e9  mov     edx, eax
0x1800075eb  mov     rax, [rsp+48h+var_18]
0x1800075f0  mov     [rbx], rax
0x1800075f3  mov     eax, edx
0x1800075f5  add     rsp, 40h
0x1800075f9  pop     rbx
0x1800075fa  retn
```
