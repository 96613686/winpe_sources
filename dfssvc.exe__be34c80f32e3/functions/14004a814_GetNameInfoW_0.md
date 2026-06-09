# GetNameInfoW_0

- ea: `0x14004a814`
- end: `0x14004a8e6`
- name: `GetNameInfoW_0`
- size: `210`
- prototype: `INT __stdcall(const SOCKADDR *pSockaddr, socklen_t SockaddrLength, PWCHAR pNodeBuffer, DWORD NodeBufferSize, PWCHAR pServiceBuffer, DWORD ServiceBufferSize, INT Flags)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14004ab3c`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x14004a814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a8b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14004a838`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14004a8a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14004a838`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14004a8a0`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
INT __stdcall GetNameInfoW_0(
        const SOCKADDR *pSockaddr,
        socklen_t SockaddrLength,
        PWCHAR pNodeBuffer,
        DWORD NodeBufferSize,
        PWCHAR pServiceBuffer,
        DWORD ServiceBufferSize,
        INT Flags)
{
  WCHAR **v7; // r14
  COMPUTER_NAME_FORMAT v8; // esi
  INT LastError; // ebx
  WCHAR *v10; // rax
  WCHAR *v11; // rdi
  DWORD nSize; // [rsp+40h] [rbp+18h] BYREF

  nSize = 0;
  v7 = *(WCHAR ***)&SockaddrLength;
  v8 = (int)pSockaddr;
  if ( GetComputerNameExW((COMPUTER_NAME_FORMAT)pSockaddr, 0, &nSize) )
    return 668;
  LastError = GetLastError();
  if ( LastError != 234 )
    return LastError;
  if ( !nSize )
    return 668;
  v10 = (WCHAR *)operator new(saturated_mul(nSize, 2u));
  v11 = v10;
  if ( !v10 )
    return 8;
  if ( GetComputerNameExW(v8, v10, &nSize) )
  {
    *v7 = v11;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    operator delete(v11);
  }
  return LastError;
}

```

## disassembly

```asm
0x14004a814  mov     rax, rsp
0x14004a817  mov     [rax+8], rbx
0x14004a81b  mov     [rax+10h], rsi
0x14004a81f  mov     [rax+20h], rdi
0x14004a823  push    r14
0x14004a825  sub     rsp, 20h
0x14004a829  and     dword ptr [rax+18h], 0
0x14004a82d  lea     r8, [rax+18h]; nSize
0x14004a831  mov     r14, rdx
0x14004a834  mov     esi, ecx
0x14004a836  xor     edx, edx; lpBuffer
0x14004a838  call    cs:__imp_GetComputerNameExW
0x14004a83f  nop     dword ptr [rax+rax+00h]
0x14004a844  test    eax, eax
0x14004a846  jz      short loc_14004A84F
0x14004a848  mov     ebx, 29Ch
0x14004a84d  jmp     short loc_14004A8CD
0x14004a84f  call    cs:__imp_GetLastError
0x14004a856  nop     dword ptr [rax+rax+00h]
0x14004a85b  mov     ebx, eax
0x14004a85d  cmp     eax, 0EAh
0x14004a862  jnz     short loc_14004A8CD
0x14004a864  mov     eax, [rsp+28h+nSize]
0x14004a868  test    eax, eax
0x14004a86a  jz      short loc_14004A848
0x14004a86c  mov     ecx, eax
0x14004a86e  mov     eax, 2
0x14004a873  mul     rcx
0x14004a876  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14004a87d  cmovo   rax, rcx
0x14004a881  mov     rcx, rax; Size
0x14004a884  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004a889  mov     rdi, rax
0x14004a88c  test    rax, rax
0x14004a88f  jnz     short loc_14004A896
0x14004a891  lea     ebx, [rax+8]
0x14004a894  jmp     short loc_14004A8CD
0x14004a896  lea     r8, [rsp+28h+nSize]; nSize
0x14004a89b  mov     rdx, rdi; lpBuffer
0x14004a89e  mov     ecx, esi; NameType
0x14004a8a0  call    cs:__imp_GetComputerNameExW
0x14004a8a7  nop     dword ptr [rax+rax+00h]
0x14004a8ac  test    eax, eax
0x14004a8ae  jnz     short loc_14004A8C8
0x14004a8b0  call    cs:__imp_GetLastError
0x14004a8b7  nop     dword ptr [rax+rax+00h]
0x14004a8bc  mov     rcx, rdi; Block
0x14004a8bf  mov     ebx, eax
0x14004a8c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004a8c6  jmp     short loc_14004A8CD
0x14004a8c8  mov     [r14], rdi
0x14004a8cb  xor     ebx, ebx
0x14004a8cd  mov     rsi, [rsp+28h+arg_8]
0x14004a8d2  mov     eax, ebx
0x14004a8d4  mov     rbx, [rsp+28h+arg_0]
0x14004a8d9  mov     rdi, [rsp+28h+arg_18]
0x14004a8de  add     rsp, 20h
0x14004a8e2  pop     r14
0x14004a8e4  retn
```
