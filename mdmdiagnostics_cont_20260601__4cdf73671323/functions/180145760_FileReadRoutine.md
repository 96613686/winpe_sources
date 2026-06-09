# FileReadRoutine

- ea: `0x180145760`
- end: `0x1801457e2`
- name: `FileReadRoutine`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180145760`
- `0x1801595f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180145795`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180145795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014579f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014579f`

## pseudocode

```c
__int64 __fastcall FileReadRoutine(void *a1, DWORD a2, void *a3)
{
  signed int LastError; // eax
  unsigned int v5; // r10d
  unsigned int v6; // r10d
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v5 = -2147024809;
LABEL_9:
    LogErrorFxn(a1, v5);
    return v6;
  }
  if ( !ReadFile(a1, a3, a2, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  return NumberOfBytesRead != a2 ? 0x8007001E : 0;
}

```

## disassembly

```asm
0x180145760  push    rbx
0x180145762  sub     rsp, 30h
0x180145766  mov     [rsp+38h+NumberOfBytesRead], 0
0x18014576e  mov     rax, r8
0x180145771  mov     ebx, edx
0x180145773  test    rcx, rcx
0x180145776  jz      short loc_1801457CB
0x180145778  test    edx, edx
0x18014577a  jz      short loc_1801457CB
0x18014577c  test    rax, rax
0x18014577f  jz      short loc_1801457CB
0x180145781  mov     r8d, edx; nNumberOfBytesToRead
0x180145784  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18014578d  mov     rdx, rax; lpBuffer
0x180145790  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180145795  call    cs:__imp_ReadFile
0x18014579b  test    eax, eax
0x18014579d  jnz     short loc_1801457B9
0x18014579f  call    cs:__imp_GetLastError
0x1801457a5  mov     r10d, eax
0x1801457a8  test    eax, eax
0x1801457aa  jle     short loc_1801457D1
0x1801457ac  movzx   r10d, ax
0x1801457b0  or      r10d, 80070000h
0x1801457b7  jmp     short loc_1801457D1
0x1801457b9  sub     ebx, [rsp+38h+NumberOfBytesRead]
0x1801457bd  neg     ebx
0x1801457bf  sbb     r10d, r10d
0x1801457c2  and     r10d, 8007001Eh
0x1801457c9  jmp     short loc_1801457D9
0x1801457cb  mov     r10d, 80070057h
0x1801457d1  mov     edx, r10d
0x1801457d4  call    LogErrorFxn
0x1801457d9  mov     eax, r10d
0x1801457dc  add     rsp, 30h
0x1801457e0  pop     rbx
0x1801457e1  retn
```
