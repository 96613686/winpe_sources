# FileStream::SetFileSize(TXLargeIntegerWrapper<_ULARGE_INTEGER,ulong,unsigned __int64> const &)

- ea: `0x18012b4b8`
- end: `0x18012b558`
- name: `?SetFileSize@FileStream@@AEAAJAEBV?$TXLargeIntegerWrapper@T_ULARGE_INTEGER@@K_K@@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18012b560`

## callees

- `0x18012b4b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b536`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18012b50d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18012b50d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18012b52c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18012b52c`

## pseudocode

```c
__int64 __fastcall FileStream::SetFileSize(__int64 a1, __int64 *a2)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = *a2;
  if ( v6 >= 0 )
  {
    if ( SetFilePointer(*(HANDLE *)(a1 + 72), v6, (PLONG)&v6 + 1, 0) == -1 && GetLastError()
      || (v3 = 0, !SetEndOfFile(*(HANDLE *)(a1 + 72))) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147286953;
  }
  return v3;
}

```

## disassembly

```asm
0x18012b4b8  mov     [rsp+arg_0], rbx
0x18012b4bd  push    rdi
0x18012b4be  sub     rsp, 20h
0x18012b4c2  mov     eax, [rdx+4]
0x18012b4c5  mov     rdi, rcx
0x18012b4c8  mov     r10d, [rdx]
0x18012b4cb  mov     [rsp+28h+arg_8], 0
0x18012b4d4  mov     dword ptr [rsp+28h+arg_8+4], eax
0x18012b4d8  mov     dword ptr [rsp+28h+arg_8], r10d
0x18012b4dd  mov     rax, [rsp+28h+arg_8]
0x18012b4e2  mov     rdx, rax
0x18012b4e5  mov     dword ptr [rsp+28h+arg_10], r10d
0x18012b4ea  sar     rdx, 20h
0x18012b4ee  mov     dword ptr [rsp+28h+arg_10+4], edx
0x18012b4f2  test    rax, rax
0x18012b4f5  jns     short loc_18012B4FE
0x18012b4f7  mov     ebx, 80030057h
0x18012b4fc  jmp     short loc_18012B54B
0x18012b4fe  mov     rcx, [rcx+48h]; hFile
0x18012b502  lea     r8, [rsp+28h+arg_10+4]; lpDistanceToMoveHigh
0x18012b507  xor     r9d, r9d; dwMoveMethod
0x18012b50a  mov     edx, r10d; lDistanceToMove
0x18012b50d  call    cs:__imp_SetFilePointer
0x18012b513  mov     dword ptr [rsp+28h+arg_10], eax
0x18012b517  cmp     eax, 0FFFFFFFFh
0x18012b51a  jnz     short loc_18012B526
0x18012b51c  call    cs:__imp_GetLastError
0x18012b522  test    eax, eax
0x18012b524  jnz     short loc_18012B536
0x18012b526  mov     rcx, [rdi+48h]; hFile
0x18012b52a  xor     ebx, ebx
0x18012b52c  call    cs:__imp_SetEndOfFile
0x18012b532  test    eax, eax
0x18012b534  jnz     short loc_18012B54B
0x18012b536  call    cs:__imp_GetLastError
0x18012b53c  mov     ebx, eax
0x18012b53e  test    eax, eax
0x18012b540  jle     short loc_18012B54B
0x18012b542  movzx   ebx, ax
0x18012b545  or      ebx, 80070000h
0x18012b54b  mov     eax, ebx
0x18012b54d  mov     rbx, [rsp+28h+arg_0]
0x18012b552  add     rsp, 20h
0x18012b556  pop     rdi
0x18012b557  retn
```
