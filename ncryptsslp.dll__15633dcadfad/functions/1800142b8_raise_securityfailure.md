# __raise_securityfailure

- ea: `0x1800142b8`
- end: `0x1800142d3`
- name: `__raise_securityfailure`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001447c`

## callees

- `0x18001b0ae`
- `0x18001b0ba`

## pseudocode

```c
NTSTATUS __fastcall _raise_securityfailure(struct _EXCEPTION_POINTERS *a1)
{
  RtlUnhandledExceptionFilter_0(a1);
  return NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x1800142b8  sub     rsp, 28h
0x1800142bc  call    RtlUnhandledExceptionFilter_0
0x1800142c1  mov     edx, 0C0000409h; ExitStatus
0x1800142c6  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800142ca  add     rsp, 28h
0x1800142ce  jmp     NtTerminateProcess_0
```
