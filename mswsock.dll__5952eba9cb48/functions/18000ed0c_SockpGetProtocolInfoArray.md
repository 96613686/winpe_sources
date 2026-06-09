# SockpGetProtocolInfoArray

- ea: `0x18000ed0c`
- end: `0x18000ee14`
- name: `SockpGetProtocolInfoArray`
- size: `264`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cc50`
- `0x18000f844`
- `0x180023540`
- `0x180042bc8`
- `0x180042c70`

## callees

- `0x18000ca20`
- `0x18000db30`
- `0x18000ed0c`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000ede1`
- `ntdll!RtlFreeHeap` at `0x18000edf8`
- `ntdll!RtlFreeHeap` at `0x18000ede1`
- `ntdll!RtlFreeHeap` at `0x18000edf8`
- `WS2_32!WSCEnumProtocols` at `0x18000ed32`
- `WS2_32!WSCEnumProtocols` at `0x18000ed87`
- `WS2_32!WSCEnumProtocols` at `0x18000ed32`
- `WS2_32!WSCEnumProtocols` at `0x18000ed87`

## pseudocode

```c
__int64 SockpGetProtocolInfoArray()
{
  __int64 result; // rax
  struct _WSAPROTOCOL_INFOW *v1; // rax
  struct _WSAPROTOCOL_INFOW *v2; // rbx
  int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r9
  PVOID v7; // r8
  int Errno; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwBufferLength; // [rsp+38h] [rbp+10h] BYREF

  Errno = 0;
  dwBufferLength = 0;
  if ( WSCEnumProtocols(0, 0, &dwBufferLength, &Errno) != -1 )
    return 10107;
  result = (unsigned int)Errno;
  if ( Errno == 10055 )
  {
    v1 = (struct _WSAPROTOCOL_INFOW *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                                        SockPrivateHeap,
                                        0,
                                        dwBufferLength);
    v2 = v1;
    if ( v1 )
    {
      v3 = WSCEnumProtocols(0, v1, &dwBufferLength, &Errno);
      if ( v3 == -1 )
      {
        RtlFreeHeap(SockPrivateHeap, 0, v2);
      }
      else
      {
        Errno = 0;
        SockAcquireRwLockExclusive();
        v7 = SockProtocolInfoArray;
        if ( SockProtocolInfoArray )
          RtlFreeHeap(SockPrivateHeap, 0, SockProtocolInfoArray);
        SockProtocolInfoArray = v2;
        SockProtocolInfoCount = v3;
        SockReleaseRwLockExclusive(v5, v4, v7, v6);
      }
      return (unsigned int)Errno;
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ed0c  mov     rax, rsp
0x18000ed0f  mov     [rax+18h], rbx
0x18000ed13  push    rdi
0x18000ed14  sub     rsp, 20h
0x18000ed18  lea     r9, [rax+8]; lpErrno
0x18000ed1c  mov     dword ptr [rax+8], 0
0x18000ed23  lea     r8, [rax+10h]; lpdwBufferLength
0x18000ed27  mov     dword ptr [rax+10h], 0
0x18000ed2e  xor     edx, edx; lpProtocolBuffer
0x18000ed30  xor     ecx, ecx; lpiProtocols
0x18000ed32  call    cs:__imp_WSCEnumProtocols
0x18000ed39  nop     dword ptr [rax+rax+00h]
0x18000ed3e  cmp     eax, 0FFFFFFFFh
0x18000ed41  jnz     loc_18000EE0D
0x18000ed47  mov     eax, [rsp+28h+Errno]
0x18000ed4b  cmp     eax, 2747h
0x18000ed50  jnz     short loc_18000EDC9
0x18000ed52  mov     r8d, [rsp+28h+dwBufferLength]
0x18000ed57  xor     edx, edx
0x18000ed59  mov     rcx, cs:SockPrivateHeap
0x18000ed60  mov     rax, cs:SockAllocateHeapRoutine
0x18000ed67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed6c  mov     rbx, rax
0x18000ed6f  test    rax, rax
0x18000ed72  jz      loc_18000EE06
0x18000ed78  lea     r9, [rsp+28h+Errno]; lpErrno
0x18000ed7d  mov     rdx, rax; lpProtocolBuffer
0x18000ed80  lea     r8, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x18000ed85  xor     ecx, ecx; lpiProtocols
0x18000ed87  call    cs:__imp_WSCEnumProtocols
0x18000ed8e  nop     dword ptr [rax+rax+00h]
0x18000ed93  mov     edi, eax
0x18000ed95  cmp     eax, 0FFFFFFFFh
0x18000ed98  jz      short loc_18000EDD5
0x18000ed9a  mov     [rsp+28h+Errno], 0
0x18000eda2  call    SockAcquireRwLockExclusive
0x18000eda7  mov     r8, cs:SockProtocolInfoArray; P
0x18000edae  test    r8, r8
0x18000edb1  jnz     short loc_18000EDEF
0x18000edb3  mov     cs:SockProtocolInfoArray, rbx
0x18000edba  mov     cs:SockProtocolInfoCount, edi
0x18000edc0  call    SockReleaseRwLockExclusive
0x18000edc5  mov     eax, [rsp+28h+Errno]
0x18000edc9  mov     rbx, [rsp+28h+arg_10]
0x18000edce  add     rsp, 20h
0x18000edd2  pop     rdi
0x18000edd3  retn
0x18000edd5  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000eddc  mov     r8, rbx; P
0x18000eddf  xor     edx, edx; Flags
0x18000ede1  call    cs:__imp_RtlFreeHeap
0x18000ede8  nop     dword ptr [rax+rax+00h]
0x18000eded  jmp     short loc_18000EDC5
0x18000edef  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000edf6  xor     edx, edx; Flags
0x18000edf8  call    cs:__imp_RtlFreeHeap
0x18000edff  nop     dword ptr [rax+rax+00h]
0x18000ee04  jmp     short loc_18000EDB3
0x18000ee06  mov     eax, 8
0x18000ee0b  jmp     short loc_18000EDC9
0x18000ee0d  mov     eax, 277Bh
0x18000ee12  jmp     short loc_18000EDC9
```
