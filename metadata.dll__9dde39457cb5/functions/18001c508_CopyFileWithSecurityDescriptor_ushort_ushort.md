# CopyFileWithSecurityDescriptor(ushort *,ushort *)

- ea: `0x18001c508`
- end: `0x18001c57a`
- name: `?CopyFileWithSecurityDescriptor@@YAJPEAG0@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009c14`
- `0x18000a638`
- `0x18000aed0`
- `0x18001cf00`
- `0x18001d6d4`
- `0x180020f18`

## callees

- `0x18001c508`
- `0x180025e98`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18001c525`
- `KERNEL32!CopyFileW` at `0x18001c525`
- `KERNEL32!DeleteFileW` at `0x18001c567`
- `KERNEL32!DeleteFileW` at `0x18001c567`
- `KERNEL32!GetLastError` at `0x18001c52f`
- `KERNEL32!GetLastError` at `0x18001c52f`

## pseudocode

```c
__int64 __fastcall CopyFileWithSecurityDescriptor(unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx

  if ( !a1 || !a2 )
  {
    v5 = -2147024809;
    goto LABEL_11;
  }
  if ( CopyFileW(a1, a2, 0) )
  {
    v5 = SetSecurityOnFile(a1, a2);
    if ( v5 >= 0 )
      return 0;
LABEL_11:
    DeleteFileW(a2);
    return (unsigned int)v5;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_11;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c508  mov     [rsp+arg_0], rbx
0x18001c50d  push    rdi
0x18001c50e  sub     rsp, 20h
0x18001c512  mov     rdi, rdx
0x18001c515  mov     rbx, rcx
0x18001c518  test    rcx, rcx
0x18001c51b  jz      short loc_18001C55F
0x18001c51d  test    rdx, rdx
0x18001c520  jz      short loc_18001C55F
0x18001c522  xor     r8d, r8d; bFailIfExists
0x18001c525  call    cs:__imp_CopyFileW
0x18001c52b  test    eax, eax
0x18001c52d  jnz     short loc_18001C54A
0x18001c52f  call    cs:__imp_GetLastError
0x18001c535  mov     ebx, eax
0x18001c537  test    eax, eax
0x18001c539  jle     short loc_18001C544
0x18001c53b  movzx   ebx, ax
0x18001c53e  or      ebx, 80070000h
0x18001c544  test    ebx, ebx
0x18001c546  jns     short loc_18001C56D
0x18001c548  jmp     short loc_18001C564
0x18001c54a  mov     rdx, rdi; unsigned __int16 *
0x18001c54d  mov     rcx, rbx; unsigned __int16 *
0x18001c550  call    ?SetSecurityOnFile@@YAJPEAG0@Z; SetSecurityOnFile(ushort *,ushort *)
0x18001c555  mov     ebx, eax
0x18001c557  test    eax, eax
0x18001c559  js      short loc_18001C564
0x18001c55b  xor     ebx, ebx
0x18001c55d  jmp     short loc_18001C56D
0x18001c55f  mov     ebx, 80070057h
0x18001c564  mov     rcx, rdi; lpFileName
0x18001c567  call    cs:__imp_DeleteFileW
0x18001c56d  mov     eax, ebx
0x18001c56f  mov     rbx, [rsp+28h+arg_0]
0x18001c574  add     rsp, 20h
0x18001c578  pop     rdi
0x18001c579  retn
```
