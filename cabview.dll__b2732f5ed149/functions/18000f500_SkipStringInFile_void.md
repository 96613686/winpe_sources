# SkipStringInFile(void *)

- ea: `0x18000f500`
- end: `0x18000f565`
- name: `?SkipStringInFile@@YAHPEAX@Z`
- size: `101`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d678`
- `0x18000d81c`

## callees

- `0x180002620`
- `0x18000f500`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000f541`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000f541`

## pseudocode

```c
BOOL __fastcall SkipStringInFile(HANDLE hFile)
{
  BOOL result; // eax
  _BYTE Buffer[4]; // [rsp+30h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+34h] [rbp-14h] BYREF

  Buffer[0] = 0;
  NumberOfBytesRead = 0;
  do
    result = ReadFile(hFile, Buffer, 1u, &NumberOfBytesRead, 0);
  while ( result && Buffer[0] );
  return result;
}

```

## disassembly

```asm
0x18000f500  push    rbx
0x18000f502  sub     rsp, 40h
0x18000f506  mov     rax, cs:__security_cookie
0x18000f50d  xor     rax, rsp
0x18000f510  mov     [rsp+48h+var_10], rax
0x18000f515  mov     rbx, rcx
0x18000f518  mov     [rsp+48h+Buffer], 0
0x18000f51d  mov     [rsp+48h+NumberOfBytesRead], 0
0x18000f525  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000f52a  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18000f533  mov     r8d, 1; nNumberOfBytesToRead
0x18000f539  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x18000f53e  mov     rcx, rbx; hFile
0x18000f541  call    cs:__imp_ReadFile
0x18000f547  test    eax, eax
0x18000f549  jz      short loc_18000F552
0x18000f54b  cmp     [rsp+48h+Buffer], 0
0x18000f550  jnz     short loc_18000F525
0x18000f552  mov     rcx, [rsp+48h+var_10]
0x18000f557  xor     rcx, rsp; StackCookie
0x18000f55a  call    __security_check_cookie
0x18000f55f  add     rsp, 40h
0x18000f563  pop     rbx
0x18000f564  retn
```
