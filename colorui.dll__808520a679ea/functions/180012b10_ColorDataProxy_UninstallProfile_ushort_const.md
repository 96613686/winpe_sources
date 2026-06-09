# ColorDataProxy::UninstallProfile(ushort const *)

- ea: `0x180012b10`
- end: `0x180012b5e`
- name: `?UninstallProfile@ColorDataProxy@@UEAAJPEBG@Z`
- size: `78`
- prototype: `signed int __fastcall(ColorDataProxy *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012b10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012b32`
- `KERNEL32!GetLastError` at `0x180012b32`
- `mscms!UninstallColorProfileW` at `0x180012b28`
- `mscms!UninstallColorProfileW` at `0x180012b28`

## pseudocode

```c
signed int __fastcall ColorDataProxy::UninstallProfile(ColorDataProxy *this, const unsigned __int16 *a2)
{
  signed int result; // eax

  if ( !a2 || !*a2 )
    return -2147024809;
  if ( UninstallColorProfileW(0, a2, 1) )
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
0x180012b10  push    rbx
0x180012b12  sub     rsp, 20h
0x180012b16  xor     ebx, ebx
0x180012b18  test    rdx, rdx
0x180012b1b  jz      short loc_180012B53
0x180012b1d  cmp     [rdx], bx
0x180012b20  jz      short loc_180012B53
0x180012b22  xor     ecx, ecx; pMachineName
0x180012b24  lea     r8d, [rbx+1]; bDelete
0x180012b28  call    cs:__imp_UninstallColorProfileW
0x180012b2e  test    eax, eax
0x180012b30  jnz     short loc_180012B4F
0x180012b32  call    cs:__imp_GetLastError
0x180012b38  test    eax, eax
0x180012b3a  jz      short loc_180012B48
0x180012b3c  jle     short loc_180012B58
0x180012b3e  movzx   eax, ax
0x180012b41  or      eax, 80070000h
0x180012b46  jmp     short loc_180012B58
0x180012b48  mov     eax, 80004005h
0x180012b4d  jmp     short loc_180012B58
0x180012b4f  xor     eax, eax
0x180012b51  jmp     short loc_180012B58
0x180012b53  mov     eax, 80070057h
0x180012b58  add     rsp, 20h
0x180012b5c  pop     rbx
0x180012b5d  retn
```
