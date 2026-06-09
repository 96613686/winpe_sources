# FileStream::SetFileSize(TXLargeIntegerWrapper<_ULARGE_INTEGER,ulong,unsigned __int64> const &)

- ea: `0x180133818`
- end: `0x1801338d1`
- name: `?SetFileSize@FileStream@@AEAAJAEBV?$TXLargeIntegerWrapper@T_ULARGE_INTEGER@@K_K@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801338e0`

## callees

- `0x180133818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801338a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801338a8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18013386d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18013386d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180133898`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180133898`

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
0x180133818  mov     [rsp+arg_0], rbx
0x18013381d  push    rdi
0x18013381e  sub     rsp, 20h
0x180133822  mov     eax, [rdx+4]
0x180133825  mov     rdi, rcx
0x180133828  mov     r10d, [rdx]
0x18013382b  mov     [rsp+28h+arg_8], 0
0x180133834  mov     dword ptr [rsp+28h+arg_8+4], eax
0x180133838  mov     dword ptr [rsp+28h+arg_8], r10d
0x18013383d  mov     rax, [rsp+28h+arg_8]
0x180133842  mov     rdx, rax
0x180133845  mov     dword ptr [rsp+28h+arg_10], r10d
0x18013384a  sar     rdx, 20h
0x18013384e  mov     dword ptr [rsp+28h+arg_10+4], edx
0x180133852  test    rax, rax
0x180133855  jns     short loc_18013385E
0x180133857  mov     ebx, 80030057h
0x18013385c  jmp     short loc_1801338C3
0x18013385e  mov     rcx, [rcx+48h]; hFile
0x180133862  lea     r8, [rsp+28h+arg_10+4]; lpDistanceToMoveHigh
0x180133867  xor     r9d, r9d; dwMoveMethod
0x18013386a  mov     edx, r10d; lDistanceToMove
0x18013386d  call    cs:__imp_SetFilePointer
0x180133874  nop     dword ptr [rax+rax+00h]
0x180133879  mov     dword ptr [rsp+28h+arg_10], eax
0x18013387d  cmp     eax, 0FFFFFFFFh
0x180133880  jnz     short loc_180133892
0x180133882  call    cs:__imp_GetLastError
0x180133889  nop     dword ptr [rax+rax+00h]
0x18013388e  test    eax, eax
0x180133890  jnz     short loc_1801338A8
0x180133892  mov     rcx, [rdi+48h]; hFile
0x180133896  xor     ebx, ebx
0x180133898  call    cs:__imp_SetEndOfFile
0x18013389f  nop     dword ptr [rax+rax+00h]
0x1801338a4  test    eax, eax
0x1801338a6  jnz     short loc_1801338C3
0x1801338a8  call    cs:__imp_GetLastError
0x1801338af  nop     dword ptr [rax+rax+00h]
0x1801338b4  mov     ebx, eax
0x1801338b6  test    eax, eax
0x1801338b8  jle     short loc_1801338C3
0x1801338ba  movzx   ebx, ax
0x1801338bd  or      ebx, 80070000h
0x1801338c3  mov     eax, ebx
0x1801338c5  mov     rbx, [rsp+28h+arg_0]
0x1801338ca  add     rsp, 20h
0x1801338ce  pop     rdi
0x1801338cf  retn
```
