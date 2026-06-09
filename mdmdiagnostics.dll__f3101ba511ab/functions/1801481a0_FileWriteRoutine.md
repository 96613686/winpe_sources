# FileWriteRoutine

- ea: `0x1801481a0`
- end: `0x18014822c`
- name: `FileWriteRoutine`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1801481a0`
- `0x18015c080`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801481d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801481d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801481e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801481e1`

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
0x1801481a0  push    rbx
0x1801481a2  sub     rsp, 30h
0x1801481a6  mov     [rsp+38h+NumberOfBytesWritten], 0
0x1801481ae  mov     rax, r8
0x1801481b1  mov     ebx, edx
0x1801481b3  test    rcx, rcx
0x1801481b6  jz      short loc_180148214
0x1801481b8  test    rax, rax
0x1801481bb  jz      short loc_180148214
0x1801481bd  mov     r8d, edx; nNumberOfBytesToWrite
0x1801481c0  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1801481c9  mov     rdx, rax; lpBuffer
0x1801481cc  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801481d1  call    cs:__imp_WriteFile
0x1801481d8  nop     dword ptr [rax+rax+00h]
0x1801481dd  test    eax, eax
0x1801481df  jnz     short loc_180148201
0x1801481e1  call    cs:__imp_GetLastError
0x1801481e8  nop     dword ptr [rax+rax+00h]
0x1801481ed  mov     r10d, eax
0x1801481f0  test    eax, eax
0x1801481f2  jle     short loc_18014821A
0x1801481f4  movzx   r10d, ax
0x1801481f8  or      r10d, 80070000h
0x1801481ff  jmp     short loc_18014821A
0x180148201  cmp     [rsp+38h+NumberOfBytesWritten], ebx
0x180148205  jz      short loc_18014820F
0x180148207  mov     r10d, 8007001Dh
0x18014820d  jmp     short loc_18014821A
0x18014820f  xor     r10d, r10d
0x180148212  jmp     short loc_180148222
0x180148214  mov     r10d, 80070057h
0x18014821a  mov     edx, r10d
0x18014821d  call    LogErrorFxn
0x180148222  mov     eax, r10d
0x180148225  add     rsp, 30h
0x180148229  pop     rbx
0x18014822a  retn
```
