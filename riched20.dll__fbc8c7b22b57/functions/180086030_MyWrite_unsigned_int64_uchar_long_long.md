# MyWrite(unsigned __int64,uchar *,long,long *)

- ea: `0x180086030`
- end: `0x180086093`
- name: `?MyWrite@@YAK_KPEAEJPEAJ@Z`
- size: `99`
- prototype: `unsigned int __fastcall(unsigned __int64, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180086030`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180086055`
- `KERNEL32!WriteFile` at `0x180086055`
- `KERNEL32!GetLastError` at `0x180086065`
- `KERNEL32!GetLastError` at `0x180086065`

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
0x180086030  push    rbx
0x180086032  sub     rsp, 30h
0x180086036  mov     rbx, r9
0x180086039  test    rcx, rcx
0x18008603c  jnz     short loc_180086045
0x18008603e  mov     eax, 80004005h
0x180086043  jmp     short loc_18008608C
0x180086045  mov     dword ptr [r9], 0
0x18008604c  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180086055  call    cs:__imp_WriteFile
0x18008605c  nop     dword ptr [rax+rax+00h]
0x180086061  test    eax, eax
0x180086063  jnz     short loc_18008607F
0x180086065  call    cs:__imp_GetLastError
0x18008606c  nop     dword ptr [rax+rax+00h]
0x180086071  test    eax, eax
0x180086073  jle     short loc_18008608C
0x180086075  movzx   eax, ax
0x180086078  or      eax, 80070000h
0x18008607d  jmp     short loc_18008608C
0x18008607f  mov     eax, [rbx]
0x180086081  neg     eax
0x180086083  sbb     eax, eax
0x180086085  not     eax
0x180086087  and     eax, 80004005h
0x18008608c  add     rsp, 30h
0x180086090  pop     rbx
0x180086091  retn
```
