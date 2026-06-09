# FileStream::SetFileSize(TXLargeIntegerWrapper<_ULARGE_INTEGER,ulong,unsigned __int64> const &)

- ea: `0x180120018`
- end: `0x1801200bf`
- name: `?SetFileSize@FileStream@@AEAAJAEBV?$TXLargeIntegerWrapper@T_ULARGE_INTEGER@@K_K@@@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801200d0`

## callees

- `0x180120018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120094`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18012005b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18012005b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180120084`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180120084`

## pseudocode

```c
__int64 __fastcall FileStream::SetFileSize(__int64 a1, LONG *a2)
{
  LONG v2; // eax
  unsigned int v3; // ebx
  LONG v4; // edx
  signed int LastError; // eax
  __int64 DistanceToMoveHigh; // [rsp+38h] [rbp+10h] BYREF

  v2 = a2[1];
  v3 = 0;
  v4 = *a2;
  DistanceToMoveHigh = __PAIR64__(v2, v4);
  if ( DistanceToMoveHigh >= 0 )
  {
    if ( SetFilePointer(*(HANDLE *)(a1 + 72), v4, (PLONG)&DistanceToMoveHigh + 1, 0) == -1 && GetLastError()
      || !SetEndOfFile(*(HANDLE *)(a1 + 72)) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
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
0x180120018  mov     [rsp+arg_0], rbx
0x18012001d  push    rdi
0x18012001e  sub     rsp, 20h
0x180120022  mov     eax, [rdx+4]
0x180120025  xor     ebx, ebx
0x180120027  mov     edx, [rdx]; lDistanceToMove
0x180120029  mov     rdi, rcx
0x18012002c  mov     [rsp+28h+DistanceToMoveHigh], rbx
0x180120031  mov     dword ptr [rsp+28h+DistanceToMoveHigh+4], eax
0x180120035  mov     dword ptr [rsp+28h+DistanceToMoveHigh], edx
0x180120039  mov     rax, [rsp+28h+DistanceToMoveHigh]
0x18012003e  mov     [rsp+28h+DistanceToMoveHigh], rax
0x180120043  test    rax, rax
0x180120046  jns     short loc_18012004F
0x180120048  mov     ebx, 80030057h
0x18012004d  jmp     short loc_1801200B1
0x18012004f  mov     rcx, [rcx+48h]; hFile
0x180120053  lea     r8, [rsp+28h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x180120058  xor     r9d, r9d; dwMoveMethod
0x18012005b  call    cs:__imp_SetFilePointer
0x180120062  nop     dword ptr [rax+rax+00h]
0x180120067  mov     dword ptr [rsp+28h+DistanceToMoveHigh], eax
0x18012006b  cmp     eax, 0FFFFFFFFh
0x18012006e  jnz     short loc_180120080
0x180120070  call    cs:__imp_GetLastError
0x180120077  nop     dword ptr [rax+rax+00h]
0x18012007c  test    eax, eax
0x18012007e  jnz     short loc_180120094
0x180120080  mov     rcx, [rdi+48h]; hFile
0x180120084  call    cs:__imp_SetEndOfFile
0x18012008b  nop     dword ptr [rax+rax+00h]
0x180120090  test    eax, eax
0x180120092  jnz     short loc_1801200B1
0x180120094  call    cs:__imp_GetLastError
0x18012009b  nop     dword ptr [rax+rax+00h]
0x1801200a0  test    eax, eax
0x1801200a2  jg      short loc_1801200A8
0x1801200a4  mov     ebx, eax
0x1801200a6  jmp     short loc_1801200B1
0x1801200a8  movzx   ebx, ax
0x1801200ab  or      ebx, 80070000h
0x1801200b1  mov     eax, ebx
0x1801200b3  mov     rbx, [rsp+28h+arg_0]
0x1801200b8  add     rsp, 20h
0x1801200bc  pop     rdi
0x1801200bd  retn
```
