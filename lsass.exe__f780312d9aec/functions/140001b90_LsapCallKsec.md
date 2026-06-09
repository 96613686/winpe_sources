# LsapCallKsec

- ea: `0x140001b90`
- end: `0x140001bde`
- name: `LsapCallKsec`
- size: `78`
- prototype: `NTSTATUS __fastcall(ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140004750`
- `0x140005044`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x140001bd3`
- `ntdll!NtDeviceIoControlFile` at `0x140001bd3`

## pseudocode

```c
NTSTATUS __fastcall LsapCallKsec(
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  return NtDeviceIoControlFile(
           KsecDevice,
           0,
           0,
           0,
           &IoStatusBlock,
           IoControlCode,
           InputBuffer,
           InputBufferLength,
           OutputBuffer,
           OutputBufferLength);
}

```

## disassembly

```asm
0x140001b90  sub     rsp, 68h
0x140001b94  mov     eax, [rsp+68h+arg_20]
0x140001b9b  xorps   xmm0, xmm0
0x140001b9e  mov     [rsp+68h+OutputBufferLength], eax; OutputBufferLength
0x140001ba2  lea     rax, [rsp+68h+var_18]
0x140001ba7  mov     [rsp+68h+OutputBuffer], r9; OutputBuffer
0x140001bac  xor     r9d, r9d; ApcContext
0x140001baf  mov     [rsp+68h+InputBufferLength], r8d; InputBufferLength
0x140001bb4  xor     r8d, r8d; ApcRoutine
0x140001bb7  mov     [rsp+68h+InputBuffer], rdx; InputBuffer
0x140001bbc  xor     edx, edx; Event
0x140001bbe  mov     [rsp+68h+IoControlCode], ecx; IoControlCode
0x140001bc2  mov     rcx, cs:KsecDevice; FileHandle
0x140001bc9  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x140001bce  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140001bd3  call    cs:__imp_NtDeviceIoControlFile
0x140001bd9  add     rsp, 68h
0x140001bdd  retn
```
