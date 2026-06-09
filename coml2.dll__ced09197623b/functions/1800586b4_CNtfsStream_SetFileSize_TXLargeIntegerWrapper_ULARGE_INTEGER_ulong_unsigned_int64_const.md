# CNtfsStream::SetFileSize(TXLargeIntegerWrapper<_ULARGE_INTEGER,ulong,unsigned __int64> const &)

- ea: `0x1800586b4`
- end: `0x180058754`
- name: `?SetFileSize@CNtfsStream@@AEAAJAEBV?$TXLargeIntegerWrapper@T_ULARGE_INTEGER@@K_K@@@Z`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180058760`
- `0x18005a300`

## callees

- `0x1800586b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058732`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180058709`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180058709`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180058728`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180058728`

## pseudocode

```c
__int64 __fastcall CNtfsStream::SetFileSize(__int64 a1, __int64 *a2)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = *a2;
  if ( v6 >= 0 )
  {
    if ( SetFilePointer(*(HANDLE *)(a1 + 96), v6, (PLONG)&v6 + 1, 0) == -1 && GetLastError()
      || (v3 = 0, !SetEndOfFile(*(HANDLE *)(a1 + 96))) )
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
0x1800586b4  mov     [rsp+arg_0], rbx
0x1800586b9  push    rdi
0x1800586ba  sub     rsp, 20h
0x1800586be  mov     eax, [rdx+4]
0x1800586c1  mov     rdi, rcx
0x1800586c4  mov     r10d, [rdx]
0x1800586c7  mov     [rsp+28h+arg_8], 0
0x1800586d0  mov     dword ptr [rsp+28h+arg_8+4], eax
0x1800586d4  mov     dword ptr [rsp+28h+arg_8], r10d
0x1800586d9  mov     rax, [rsp+28h+arg_8]
0x1800586de  mov     rdx, rax
0x1800586e1  mov     dword ptr [rsp+28h+arg_10], r10d
0x1800586e6  sar     rdx, 20h
0x1800586ea  mov     dword ptr [rsp+28h+arg_10+4], edx
0x1800586ee  test    rax, rax
0x1800586f1  jns     short loc_1800586FA
0x1800586f3  mov     ebx, 80030057h
0x1800586f8  jmp     short loc_180058747
0x1800586fa  mov     rcx, [rcx+60h]; hFile
0x1800586fe  lea     r8, [rsp+28h+arg_10+4]; lpDistanceToMoveHigh
0x180058703  xor     r9d, r9d; dwMoveMethod
0x180058706  mov     edx, r10d; lDistanceToMove
0x180058709  call    cs:__imp_SetFilePointer
0x18005870f  mov     dword ptr [rsp+28h+arg_10], eax
0x180058713  cmp     eax, 0FFFFFFFFh
0x180058716  jnz     short loc_180058722
0x180058718  call    cs:__imp_GetLastError
0x18005871e  test    eax, eax
0x180058720  jnz     short loc_180058732
0x180058722  mov     rcx, [rdi+60h]; hFile
0x180058726  xor     ebx, ebx
0x180058728  call    cs:__imp_SetEndOfFile
0x18005872e  test    eax, eax
0x180058730  jnz     short loc_180058747
0x180058732  call    cs:__imp_GetLastError
0x180058738  mov     ebx, eax
0x18005873a  test    eax, eax
0x18005873c  jle     short loc_180058747
0x18005873e  movzx   ebx, ax
0x180058741  or      ebx, 80070000h
0x180058747  mov     eax, ebx
0x180058749  mov     rbx, [rsp+28h+arg_0]
0x18005874e  add     rsp, 20h
0x180058752  pop     rdi
0x180058753  retn
```
