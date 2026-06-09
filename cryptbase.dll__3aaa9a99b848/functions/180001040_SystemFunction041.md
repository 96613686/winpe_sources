# SystemFunction041

- ea: `0x180001040`
- end: `0x180001100`
- name: `SystemFunction041`
- size: `192`
- prototype: `NTSTATUS __stdcall(PVOID Memory, ULONG MemorySize, ULONG OptionFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001040`
- `0x1800016e0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800010c1`
- `ntdll!NtDeviceIoControlFile` at `0x1800010c1`

## pseudocode

```c
NTSTATUS __stdcall SystemFunction041(PVOID Memory, ULONG MemorySize, ULONG OptionFlags)
{
  HANDLE v4; // rcx
  ULONG v7; // ebx
  ULONG v8; // ebx
  ULONG IoControlCode; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  v4 = g_hKsecDD;
  IoStatusBlock = 0;
  if ( !g_hKsecDD )
  {
    if ( !EncryptMemoryInitialize() )
      return -1073741823;
    v4 = g_hKsecDD;
  }
  if ( OptionFlags )
  {
    v7 = OptionFlags - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 != 2 )
          return -1073741811;
        IoControlCode = 3735678;
      }
      else
      {
        IoControlCode = 3735586;
      }
    }
    else
    {
      IoControlCode = 3735578;
    }
  }
  else
  {
    IoControlCode = 3735570;
  }
  return NtDeviceIoControlFile(v4, 0, 0, 0, &IoStatusBlock, IoControlCode, Memory, MemorySize, Memory, MemorySize);
}

```

## disassembly

```asm
0x180001040  mov     [rsp+arg_0], rbx
0x180001045  mov     [rsp+arg_8], rsi
0x18000104a  push    rdi
0x18000104b  sub     rsp, 60h
0x18000104f  mov     rsi, rcx
0x180001052  xorps   xmm0, xmm0
0x180001055  mov     rcx, cs:g_hKsecDD; FileHandle
0x18000105c  mov     ebx, r8d
0x18000105f  mov     edi, edx
0x180001061  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180001066  test    rcx, rcx
0x180001069  jz      short loc_1800010DD
0x18000106b  test    ebx, ebx
0x18000106d  jz      short loc_1800010CF
0x18000106f  sub     ebx, 1
0x180001072  jz      short loc_1800010D6
0x180001074  sub     ebx, 1
0x180001077  jz      short loc_180001094
0x180001079  cmp     ebx, 2
0x18000107c  jz      short loc_1800010F9
0x18000107e  mov     eax, 0C000000Dh
0x180001083  mov     rbx, [rsp+68h+arg_0]
0x180001088  mov     rsi, [rsp+68h+arg_8]
0x18000108d  add     rsp, 60h
0x180001091  pop     rdi
0x180001092  retn
0x180001094  mov     eax, 390022h
0x180001099  mov     [rsp+68h+OutputBufferLength], edi; OutputBufferLength
0x18000109d  xor     r9d, r9d; ApcContext
0x1800010a0  mov     [rsp+68h+OutputBuffer], rsi; OutputBuffer
0x1800010a5  xor     r8d, r8d; ApcRoutine
0x1800010a8  mov     [rsp+68h+InputBufferLength], edi; InputBufferLength
0x1800010ac  xor     edx, edx; Event
0x1800010ae  mov     [rsp+68h+InputBuffer], rsi; InputBuffer
0x1800010b3  mov     [rsp+68h+IoControlCode], eax; IoControlCode
0x1800010b7  lea     rax, [rsp+68h+var_18]
0x1800010bc  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1800010c1  call    cs:__imp_NtDeviceIoControlFile
0x1800010c8  nop     dword ptr [rax+rax+00h]
0x1800010cd  jmp     short loc_180001083
0x1800010cf  mov     eax, 390012h
0x1800010d4  jmp     short loc_180001099
0x1800010d6  mov     eax, 39001Ah
0x1800010db  jmp     short loc_180001099
0x1800010dd  call    EncryptMemoryInitialize
0x1800010e2  test    al, al
0x1800010e4  jnz     short loc_1800010ED
0x1800010e6  mov     eax, 0C0000001h
0x1800010eb  jmp     short loc_180001083
0x1800010ed  mov     rcx, cs:g_hKsecDD
0x1800010f4  jmp     loc_18000106B
0x1800010f9  mov     eax, 39007Eh
0x1800010fe  jmp     short loc_180001099
```
