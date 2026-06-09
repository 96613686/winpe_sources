# SockSanIncludeWait

- ea: `0x18004aa80`
- end: `0x18004aaa5`
- name: `SockSanIncludeWait`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180044f0c`
- `0x18004e7fc`

## callees

- `0x18004aa80`

## import_xrefs

- `ntdll!NtAlertThread` at `0x18004aa93`
- `ntdll!NtAlertThread` at `0x18004aa93`

## pseudocode

```c
NTSTATUS __fastcall SockSanIncludeWait(int a1)
{
  NTSTATUS result; // eax

  if ( a1 >= SockSanCurrentWaitEvents )
    return NtAlertThread(ConnectThreadHandle);
  return result;
}

```

## disassembly

```asm
0x18004aa80  sub     rsp, 28h
0x18004aa84  cmp     ecx, cs:SockSanCurrentWaitEvents
0x18004aa8a  jl      short loc_18004AA9F
0x18004aa8c  mov     rcx, cs:ConnectThreadHandle; ThreadHandle
0x18004aa93  call    cs:__imp_NtAlertThread
0x18004aa9a  nop     dword ptr [rax+rax+00h]
0x18004aa9f  add     rsp, 28h
0x18004aaa3  retn
```
