# NetpGetComputerNameEx2

- ea: `0x180002cc0`
- end: `0x180002dc8`
- name: `NetpGetComputerNameEx2`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a564`
- `0x180027fa4`

## callees

- `0x180002cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002cfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002cfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002d61`
- `netutils!NetApiBufferFree` at `0x180002d9f`
- `netutils!NetApiBufferFree` at `0x180002d9f`
- `netutils!NetApiBufferAllocate` at `0x180002d43`
- `netutils!NetApiBufferAllocate` at `0x180002d43`

## pseudocode

```c
__int64 __fastcall NetpGetComputerNameEx2(LPVOID *a1, COMPUTER_NAME_FORMAT a2)
{
  DWORD v4; // esi
  __int64 result; // rax
  DWORD LastError; // esi
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Buffer; // [rsp+40h] [rbp+18h] BYREF

  nSize = 0;
  Buffer = 0;
  if ( !a1 )
    return 87;
  *a1 = 0;
  if ( (unsigned int)a2 >= ComputerNameMax )
    return 87;
  if ( GetComputerNameExW(a2, 0, &nSize) || GetLastError() != 234 )
    return 87;
  v4 = NetApiBufferAllocate(2 * nSize, &Buffer);
  if ( v4 )
    return v4;
  if ( GetComputerNameExW(a2, (LPWSTR)Buffer, &nSize) )
  {
    result = 0;
    *a1 = Buffer;
  }
  else
  {
    LastError = GetLastError();
    NetApiBufferFree(Buffer);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180002cc0  mov     [rsp+arg_8], rbx
0x180002cc5  mov     [rsp+arg_18], rsi
0x180002cca  push    rdi
0x180002ccb  sub     rsp, 20h
0x180002ccf  xor     eax, eax
0x180002cd1  mov     edi, edx
0x180002cd3  mov     [rsp+28h+nSize], eax
0x180002cd7  mov     rbx, rcx
0x180002cda  mov     [rsp+28h+Buffer], rax
0x180002cdf  test    rcx, rcx
0x180002ce2  jz      loc_180002DBE
0x180002ce8  mov     [rcx], rax
0x180002ceb  cmp     edx, 8
0x180002cee  jnb     loc_180002DBE
0x180002cf4  lea     r8, [rsp+28h+nSize]; nSize
0x180002cf9  xor     edx, edx; lpBuffer
0x180002cfb  mov     ecx, edi; NameType
0x180002cfd  call    cs:__imp_GetComputerNameExW
0x180002d04  nop     dword ptr [rax+rax+00h]
0x180002d09  test    eax, eax
0x180002d0b  jnz     short loc_180002D20
0x180002d0d  call    cs:__imp_GetLastError
0x180002d14  nop     dword ptr [rax+rax+00h]
0x180002d19  cmp     eax, 0EAh
0x180002d1e  jz      short loc_180002D38
0x180002d20  mov     esi, 57h ; 'W'
0x180002d25  mov     eax, esi
0x180002d27  mov     rbx, [rsp+28h+arg_8]
0x180002d2c  mov     rsi, [rsp+28h+arg_18]
0x180002d31  add     rsp, 20h
0x180002d35  pop     rdi
0x180002d36  retn
0x180002d38  mov     ecx, [rsp+28h+nSize]
0x180002d3c  lea     rdx, [rsp+28h+Buffer]; Buffer
0x180002d41  add     ecx, ecx; ByteCount
0x180002d43  call    cs:__imp_NetApiBufferAllocate
0x180002d4a  nop     dword ptr [rax+rax+00h]
0x180002d4f  mov     esi, eax
0x180002d51  test    eax, eax
0x180002d53  jnz     short loc_180002D25
0x180002d55  mov     rdx, [rsp+28h+Buffer]; lpBuffer
0x180002d5a  lea     r8, [rsp+28h+nSize]; nSize
0x180002d5f  mov     ecx, edi; NameType
0x180002d61  call    cs:__imp_GetComputerNameExW
0x180002d68  nop     dword ptr [rax+rax+00h]
0x180002d6d  test    eax, eax
0x180002d6f  jz      short loc_180002D8C
0x180002d71  mov     rcx, [rsp+28h+Buffer]
0x180002d76  mov     eax, esi
0x180002d78  mov     [rbx], rcx
0x180002d7b  mov     rbx, [rsp+28h+arg_8]
0x180002d80  mov     rsi, [rsp+28h+arg_18]
0x180002d85  add     rsp, 20h
0x180002d89  pop     rdi
0x180002d8a  retn
0x180002d8c  call    cs:__imp_GetLastError
0x180002d93  nop     dword ptr [rax+rax+00h]
0x180002d98  mov     rcx, [rsp+28h+Buffer]; Buffer
0x180002d9d  mov     esi, eax
0x180002d9f  call    cs:__imp_NetApiBufferFree
0x180002da6  nop     dword ptr [rax+rax+00h]
0x180002dab  mov     rbx, [rsp+28h+arg_8]
0x180002db0  mov     eax, esi
0x180002db2  mov     rsi, [rsp+28h+arg_18]
0x180002db7  add     rsp, 20h
0x180002dbb  pop     rdi
0x180002dbc  retn
0x180002dbe  mov     eax, 57h ; 'W'
0x180002dc3  jmp     loc_180002D27
```
