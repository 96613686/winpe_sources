# CryptUninstallCancelRetrieval

- ea: `0x18001fc70`
- end: `0x18001fca5`
- name: `CryptUninstallCancelRetrieval`
- size: `53`
- prototype: `BOOL __stdcall(DWORD dwFlags, void *pvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18001fbe0`

## callees

- `0x18000a990`
- `0x18001fc70`

## import_xrefs

- `CRYPT32!I_CryptSetTls` at `0x18001fc95`
- `CRYPT32!I_CryptSetTls` at `0x18001fc95`
- `CRYPT32!I_CryptGetTls` at `0x18001fc7a`
- `CRYPT32!I_CryptGetTls` at `0x18001fc7a`

## pseudocode

```c
BOOL __stdcall CryptUninstallCancelRetrieval(DWORD dwFlags, void *pvReserved)
{
  void *Tls; // rax

  Tls = (void *)I_CryptGetTls((unsigned int)hCryptNetCancelTls);
  if ( Tls )
  {
    operator delete(Tls);
    I_CryptSetTls((unsigned int)hCryptNetCancelTls, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x18001fc70  sub     rsp, 28h
0x18001fc74  mov     ecx, cs:hCryptNetCancelTls
0x18001fc7a  call    cs:__imp_I_CryptGetTls
0x18001fc80  test    rax, rax
0x18001fc83  jz      short loc_18001FC9B
0x18001fc85  mov     rcx, rax; hMem
0x18001fc88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fc8d  mov     ecx, cs:hCryptNetCancelTls
0x18001fc93  xor     edx, edx
0x18001fc95  call    cs:__imp_I_CryptSetTls
0x18001fc9b  mov     eax, 1
0x18001fca0  add     rsp, 28h
0x18001fca4  retn
```
