# MyWrite(unsigned __int64,uchar *,long,long *)

- ea: `0x18018a700`
- end: `0x18018a763`
- name: `?MyWrite@@YAK_KPEAEJPEAJ@Z`
- size: `99`
- prototype: `unsigned int __fastcall(unsigned __int64, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18018a700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018a735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018a735`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18018a725`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18018a725`

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
0x18018a700  push    rbx
0x18018a702  sub     rsp, 30h
0x18018a706  mov     rbx, r9
0x18018a709  test    rcx, rcx
0x18018a70c  jnz     short loc_18018A715
0x18018a70e  mov     eax, 80004005h
0x18018a713  jmp     short loc_18018A75C
0x18018a715  mov     dword ptr [r9], 0
0x18018a71c  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18018a725  call    cs:__imp_WriteFile
0x18018a72c  nop     dword ptr [rax+rax+00h]
0x18018a731  test    eax, eax
0x18018a733  jnz     short loc_18018A74F
0x18018a735  call    cs:__imp_GetLastError
0x18018a73c  nop     dword ptr [rax+rax+00h]
0x18018a741  test    eax, eax
0x18018a743  jle     short loc_18018A75C
0x18018a745  movzx   eax, ax
0x18018a748  or      eax, 80070000h
0x18018a74d  jmp     short loc_18018A75C
0x18018a74f  mov     eax, [rbx]
0x18018a751  neg     eax
0x18018a753  sbb     eax, eax
0x18018a755  not     eax
0x18018a757  and     eax, 80004005h
0x18018a75c  add     rsp, 30h
0x18018a760  pop     rbx
0x18018a761  retn
```
