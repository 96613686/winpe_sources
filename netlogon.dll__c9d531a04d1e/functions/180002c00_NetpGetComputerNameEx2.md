# NetpGetComputerNameEx2

- ea: `0x180002c00`
- end: `0x180002ce1`
- name: `NetpGetComputerNameEx2`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009fb0`
- `0x180026c90`

## callees

- `0x180002c00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002c3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002c8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002c3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180002c8e`
- `netutils!NetApiBufferFree` at `0x180002cbf`
- `netutils!NetApiBufferFree` at `0x180002cbf`
- `netutils!NetApiBufferAllocate` at `0x180002c76`
- `netutils!NetApiBufferAllocate` at `0x180002c76`

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
0x180002c00  mov     [rsp+arg_8], rbx
0x180002c05  mov     [rsp+arg_18], rsi
0x180002c0a  push    rdi
0x180002c0b  sub     rsp, 20h
0x180002c0f  xor     eax, eax
0x180002c11  mov     edi, edx
0x180002c13  mov     [rsp+28h+nSize], eax
0x180002c17  mov     rbx, rcx
0x180002c1a  mov     [rsp+28h+Buffer], rax
0x180002c1f  test    rcx, rcx
0x180002c22  jz      loc_180002CD7
0x180002c28  mov     [rcx], rax
0x180002c2b  cmp     edx, 8
0x180002c2e  jnb     loc_180002CD7
0x180002c34  lea     r8, [rsp+28h+nSize]; nSize
0x180002c39  xor     edx, edx; lpBuffer
0x180002c3b  mov     ecx, edi; NameType
0x180002c3d  call    cs:__imp_GetComputerNameExW
0x180002c43  test    eax, eax
0x180002c45  jnz     short loc_180002C54
0x180002c47  call    cs:__imp_GetLastError
0x180002c4d  cmp     eax, 0EAh
0x180002c52  jz      short loc_180002C6B
0x180002c54  mov     esi, 57h ; 'W'
0x180002c59  mov     eax, esi
0x180002c5b  mov     rbx, [rsp+28h+arg_8]
0x180002c60  mov     rsi, [rsp+28h+arg_18]
0x180002c65  add     rsp, 20h
0x180002c69  pop     rdi
0x180002c6a  retn
0x180002c6b  mov     ecx, [rsp+28h+nSize]
0x180002c6f  lea     rdx, [rsp+28h+Buffer]; Buffer
0x180002c74  add     ecx, ecx; ByteCount
0x180002c76  call    cs:__imp_NetApiBufferAllocate
0x180002c7c  mov     esi, eax
0x180002c7e  test    eax, eax
0x180002c80  jnz     short loc_180002C59
0x180002c82  mov     rdx, [rsp+28h+Buffer]; lpBuffer
0x180002c87  lea     r8, [rsp+28h+nSize]; nSize
0x180002c8c  mov     ecx, edi; NameType
0x180002c8e  call    cs:__imp_GetComputerNameExW
0x180002c94  test    eax, eax
0x180002c96  jz      short loc_180002CB2
0x180002c98  mov     rcx, [rsp+28h+Buffer]
0x180002c9d  mov     eax, esi
0x180002c9f  mov     [rbx], rcx
0x180002ca2  mov     rbx, [rsp+28h+arg_8]
0x180002ca7  mov     rsi, [rsp+28h+arg_18]
0x180002cac  add     rsp, 20h
0x180002cb0  pop     rdi
0x180002cb1  retn
0x180002cb2  call    cs:__imp_GetLastError
0x180002cb8  mov     rcx, [rsp+28h+Buffer]; Buffer
0x180002cbd  mov     esi, eax
0x180002cbf  call    cs:__imp_NetApiBufferFree
0x180002cc5  mov     rbx, [rsp+28h+arg_8]
0x180002cca  mov     eax, esi
0x180002ccc  mov     rsi, [rsp+28h+arg_18]
0x180002cd1  add     rsp, 20h
0x180002cd5  pop     rdi
0x180002cd6  retn
0x180002cd7  mov     eax, 57h ; 'W'
0x180002cdc  jmp     loc_180002C5B
```
