# SockDeleteRwLock

- ea: `0x18001e560`
- end: `0x18001e59e`
- name: `SockDeleteRwLock`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000dbb0`
- `0x180020d30`

## callees

- `0x18001e560`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18001e592`
- `ntdll!NtClose` at `0x18001e570`
- `ntdll!NtClose` at `0x18001e570`

## pseudocode

```c
NTSTATUS SockDeleteRwLock()
{
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  return RtlDeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18001e560  sub     rsp, 28h
0x18001e564  mov     rcx, cs:Handle; Handle
0x18001e56b  test    rcx, rcx
0x18001e56e  jz      short loc_18001E587
0x18001e570  call    cs:__imp_NtClose
0x18001e577  nop     dword ptr [rax+rax+00h]
0x18001e57c  mov     cs:Handle, 0
0x18001e587  lea     rcx, CriticalSection
0x18001e58e  add     rsp, 28h
0x18001e592  jmp     cs:__imp_RtlDeleteCriticalSection
```
