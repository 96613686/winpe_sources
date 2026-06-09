# FileWriteRoutine

- ea: `0x180145910`
- end: `0x18014598f`
- name: `FileWriteRoutine`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180145910`
- `0x1801595f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180145941`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180145941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014594b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014594b`

## pseudocode

```c
__int64 __fastcall FileWriteRoutine(void *a1, DWORD a2, const void *a3)
{
  signed int LastError; // eax
  unsigned int v5; // r10d
  unsigned int v6; // r10d
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( !a1 || !a3 )
  {
    v5 = -2147024809;
    goto LABEL_10;
  }
  if ( !WriteFile(a1, a3, a2, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_10;
  }
  if ( NumberOfBytesWritten != a2 )
  {
    v5 = -2147024867;
LABEL_10:
    LogErrorFxn(a1, v5);
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180145910  push    rbx
0x180145912  sub     rsp, 30h
0x180145916  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18014591e  mov     rax, r8
0x180145921  mov     ebx, edx
0x180145923  test    rcx, rcx
0x180145926  jz      short loc_180145978
0x180145928  test    rax, rax
0x18014592b  jz      short loc_180145978
0x18014592d  mov     r8d, edx; nNumberOfBytesToWrite
0x180145930  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180145939  mov     rdx, rax; lpBuffer
0x18014593c  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180145941  call    cs:__imp_WriteFile
0x180145947  test    eax, eax
0x180145949  jnz     short loc_180145965
0x18014594b  call    cs:__imp_GetLastError
0x180145951  mov     r10d, eax
0x180145954  test    eax, eax
0x180145956  jle     short loc_18014597E
0x180145958  movzx   r10d, ax
0x18014595c  or      r10d, 80070000h
0x180145963  jmp     short loc_18014597E
0x180145965  cmp     [rsp+38h+NumberOfBytesWritten], ebx
0x180145969  jz      short loc_180145973
0x18014596b  mov     r10d, 8007001Dh
0x180145971  jmp     short loc_18014597E
0x180145973  xor     r10d, r10d
0x180145976  jmp     short loc_180145986
0x180145978  mov     r10d, 80070057h
0x18014597e  mov     edx, r10d
0x180145981  call    LogErrorFxn
0x180145986  mov     eax, r10d
0x180145989  add     rsp, 30h
0x18014598d  pop     rbx
0x18014598e  retn
```
