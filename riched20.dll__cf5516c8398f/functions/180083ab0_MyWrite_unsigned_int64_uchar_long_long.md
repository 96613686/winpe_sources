# MyWrite(unsigned __int64,uchar *,long,long *)

- ea: `0x180083ab0`
- end: `0x180083b06`
- name: `?MyWrite@@YAK_KPEAEJPEAJ@Z`
- size: `86`
- prototype: `unsigned int __fastcall(unsigned __int64, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180083ab0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180083ad5`
- `KERNEL32!WriteFile` at `0x180083ad5`
- `KERNEL32!GetLastError` at `0x180083adf`
- `KERNEL32!GetLastError` at `0x180083adf`

## pseudocode

```c
signed int __fastcall MyWrite(void *a1, unsigned __int8 *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( !a1 )
    return -2147467259;
  *a4 = 0;
  if ( WriteFile(a1, a2, a3, a4, 0) )
    return *a4 == 0 ? 0x80004005 : 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180083ab0  push    rbx
0x180083ab2  sub     rsp, 30h
0x180083ab6  mov     rbx, r9
0x180083ab9  test    rcx, rcx
0x180083abc  jnz     short loc_180083AC5
0x180083abe  mov     eax, 80004005h
0x180083ac3  jmp     short loc_180083B00
0x180083ac5  mov     dword ptr [r9], 0
0x180083acc  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180083ad5  call    cs:__imp_WriteFile
0x180083adb  test    eax, eax
0x180083add  jnz     short loc_180083AF3
0x180083adf  call    cs:__imp_GetLastError
0x180083ae5  test    eax, eax
0x180083ae7  jle     short loc_180083B00
0x180083ae9  movzx   eax, ax
0x180083aec  or      eax, 80070000h
0x180083af1  jmp     short loc_180083B00
0x180083af3  mov     eax, [rbx]
0x180083af5  neg     eax
0x180083af7  sbb     eax, eax
0x180083af9  not     eax
0x180083afb  and     eax, 80004005h
0x180083b00  add     rsp, 30h
0x180083b04  pop     rbx
0x180083b05  retn
```
