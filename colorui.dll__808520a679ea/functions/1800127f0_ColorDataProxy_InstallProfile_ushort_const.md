# ColorDataProxy::InstallProfile(ushort const *)

- ea: `0x1800127f0`
- end: `0x18001283a`
- name: `?InstallProfile@ColorDataProxy@@UEAAJPEBG@Z`
- size: `74`
- prototype: `signed int __fastcall(ColorDataProxy *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800127f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001280e`
- `KERNEL32!GetLastError` at `0x18001280e`
- `mscms!InstallColorProfileW` at `0x180012804`
- `mscms!InstallColorProfileW` at `0x180012804`

## pseudocode

```c
signed int __fastcall ColorDataProxy::InstallProfile(ColorDataProxy *this, const unsigned __int16 *a2)
{
  signed int result; // eax

  if ( !a2 || !*a2 )
    return -2147024809;
  if ( InstallColorProfileW(0, a2) )
    return 0;
  result = GetLastError();
  if ( !result )
    return -2147467259;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800127f0  push    rbx
0x1800127f2  sub     rsp, 20h
0x1800127f6  xor     ebx, ebx
0x1800127f8  test    rdx, rdx
0x1800127fb  jz      short loc_18001282F
0x1800127fd  cmp     [rdx], bx
0x180012800  jz      short loc_18001282F
0x180012802  xor     ecx, ecx; pMachineName
0x180012804  call    cs:__imp_InstallColorProfileW
0x18001280a  test    eax, eax
0x18001280c  jnz     short loc_18001282B
0x18001280e  call    cs:__imp_GetLastError
0x180012814  test    eax, eax
0x180012816  jz      short loc_180012824
0x180012818  jle     short loc_180012834
0x18001281a  movzx   eax, ax
0x18001281d  or      eax, 80070000h
0x180012822  jmp     short loc_180012834
0x180012824  mov     eax, 80004005h
0x180012829  jmp     short loc_180012834
0x18001282b  xor     eax, eax
0x18001282d  jmp     short loc_180012834
0x18001282f  mov     eax, 80070057h
0x180012834  add     rsp, 20h
0x180012838  pop     rbx
0x180012839  retn
```
