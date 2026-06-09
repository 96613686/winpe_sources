# SystemFunction040

- ea: `0x180001110`
- end: `0x1800011d0`
- name: `SystemFunction040`
- size: `192`
- prototype: `NTSTATUS __stdcall(PVOID Memory, ULONG MemorySize, ULONG OptionFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001110`
- `0x1800016e0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180001191`
- `ntdll!NtDeviceIoControlFile` at `0x180001191`

## pseudocode

```c
NTSTATUS __stdcall SystemFunction040(PVOID Memory, ULONG MemorySize, ULONG OptionFlags)
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
        IoControlCode = 3735674;
      }
      else
      {
        IoControlCode = 3735582;
      }
    }
    else
    {
      IoControlCode = 3735574;
    }
  }
  else
  {
    IoControlCode = 3735566;
  }
  return NtDeviceIoControlFile(v4, 0, 0, 0, &IoStatusBlock, IoControlCode, Memory, MemorySize, Memory, MemorySize);
}

```

## disassembly

```asm
0x180001110  mov     [rsp+arg_0], rbx
0x180001115  mov     [rsp+arg_8], rsi
0x18000111a  push    rdi
0x18000111b  sub     rsp, 60h
0x18000111f  mov     rsi, rcx
0x180001122  xorps   xmm0, xmm0
0x180001125  mov     rcx, cs:g_hKsecDD; FileHandle
0x18000112c  mov     ebx, r8d
0x18000112f  mov     edi, edx
0x180001131  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180001136  test    rcx, rcx
0x180001139  jz      short loc_1800011AD
0x18000113b  test    ebx, ebx
0x18000113d  jz      short loc_18000119F
0x18000113f  sub     ebx, 1
0x180001142  jz      short loc_1800011A6
0x180001144  sub     ebx, 1
0x180001147  jz      short loc_180001164
0x180001149  cmp     ebx, 2
0x18000114c  jz      short loc_1800011C9
0x18000114e  mov     eax, 0C000000Dh
0x180001153  mov     rbx, [rsp+68h+arg_0]
0x180001158  mov     rsi, [rsp+68h+arg_8]
0x18000115d  add     rsp, 60h
0x180001161  pop     rdi
0x180001162  retn
0x180001164  mov     eax, 39001Eh
0x180001169  mov     [rsp+68h+OutputBufferLength], edi; OutputBufferLength
0x18000116d  xor     r9d, r9d; ApcContext
0x180001170  mov     [rsp+68h+OutputBuffer], rsi; OutputBuffer
0x180001175  xor     r8d, r8d; ApcRoutine
0x180001178  mov     [rsp+68h+InputBufferLength], edi; InputBufferLength
0x18000117c  xor     edx, edx; Event
0x18000117e  mov     [rsp+68h+InputBuffer], rsi; InputBuffer
0x180001183  mov     [rsp+68h+IoControlCode], eax; IoControlCode
0x180001187  lea     rax, [rsp+68h+var_18]
0x18000118c  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x180001191  call    cs:__imp_NtDeviceIoControlFile
0x180001198  nop     dword ptr [rax+rax+00h]
0x18000119d  jmp     short loc_180001153
0x18000119f  mov     eax, 39000Eh
0x1800011a4  jmp     short loc_180001169
0x1800011a6  mov     eax, 390016h
0x1800011ab  jmp     short loc_180001169
0x1800011ad  call    EncryptMemoryInitialize
0x1800011b2  test    al, al
0x1800011b4  jnz     short loc_1800011BD
0x1800011b6  mov     eax, 0C0000001h
0x1800011bb  jmp     short loc_180001153
0x1800011bd  mov     rcx, cs:g_hKsecDD
0x1800011c4  jmp     loc_18000113B
0x1800011c9  mov     eax, 39007Ah
0x1800011ce  jmp     short loc_180001169
```
