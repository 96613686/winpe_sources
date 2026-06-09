# MyRead(unsigned __int64,uchar *,long,long *)

- ea: `0x18018a630`
- end: `0x18018a682`
- name: `?MyRead@@YAK_KPEAEJPEAJ@Z`
- size: `82`
- prototype: `unsigned int __fastcall(unsigned __int64, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18018a630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018a660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018a660`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18018a650`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18018a650`

## pseudocode

```c
signed int __fastcall MyRead(void *a1, unsigned __int8 *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( !a1 )
    return -2147467259;
  *a4 = 0;
  if ( ReadFile(a1, a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18018a630  sub     rsp, 38h
0x18018a634  test    rcx, rcx
0x18018a637  jnz     short loc_18018A640
0x18018a639  mov     eax, 80004005h
0x18018a63e  jmp     short loc_18018A67C
0x18018a640  mov     dword ptr [r9], 0
0x18018a647  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18018a650  call    cs:__imp_ReadFile
0x18018a657  nop     dword ptr [rax+rax+00h]
0x18018a65c  test    eax, eax
0x18018a65e  jnz     short loc_18018A67A
0x18018a660  call    cs:__imp_GetLastError
0x18018a667  nop     dword ptr [rax+rax+00h]
0x18018a66c  test    eax, eax
0x18018a66e  jle     short loc_18018A67C
0x18018a670  movzx   eax, ax
0x18018a673  or      eax, 80070000h
0x18018a678  jmp     short loc_18018A67C
0x18018a67a  xor     eax, eax
0x18018a67c  add     rsp, 38h
0x18018a680  retn
```
