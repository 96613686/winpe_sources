# InstallPackage(ushort const *,ushort const *)

- ea: `0x140006300`
- end: `0x14000633b`
- name: `?InstallPackage@@YAHPEBG0@Z`
- size: `59`
- prototype: `__int64 __fastcall(const unsigned __int16 *, WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140004444`
- `0x140004ca8`
- `0x140006300`
- `0x140006384`

## pseudocode

```c
__int64 __fastcall InstallPackage(const unsigned __int16 *a1, WCHAR *a2)
{
  if ( IsGUID(a2) )
    return ConfigureOrRemoveProduct(a2, 0);
  else
    return DoInstallPackage(a2, &dword_14000B81C, INSTALLUILEVEL_FULL);
}

```

## disassembly

```asm
0x140006300  push    rbx
0x140006302  sub     rsp, 20h
0x140006306  mov     rcx, rdx; unsigned __int16 *
0x140006309  mov     rbx, rdx
0x14000630c  call    ?IsGUID@@YA_NPEBG@Z; IsGUID(ushort const *)
0x140006311  mov     rcx, rbx; unsigned __int16 *
0x140006314  test    al, al
0x140006316  jz      short loc_140006324
0x140006318  xor     edx, edx
0x14000631a  add     rsp, 20h
0x14000631e  pop     rbx
0x14000631f  jmp     ?ConfigureOrRemoveProduct@@YAHPEBGW4Bool@@@Z; ConfigureOrRemoveProduct(ushort const *,Bool)
0x140006324  mov     r8d, 5; enum tagINSTALLUILEVEL
0x14000632a  lea     rdx, dword_14000B81C; unsigned __int16 *
0x140006331  add     rsp, 20h
0x140006335  pop     rbx
0x140006336  jmp     ?DoInstallPackage@@YAHPEBG0W4tagINSTALLUILEVEL@@@Z; DoInstallPackage(ushort const *,ushort const *,tagINSTALLUILEVEL)
```
