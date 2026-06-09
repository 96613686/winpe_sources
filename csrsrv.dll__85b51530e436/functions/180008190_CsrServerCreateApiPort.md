# CsrServerCreateApiPort

- ea: `0x180008190`
- end: `0x180008208`
- name: `CsrServerCreateApiPort`
- size: `120`
- prototype: `NTSTATUS __fastcall(void **Reserved6)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005180`

## callees

- `0x180008190`
- `0x1800095c0`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x1800081bd`
- `ntdll!NtCreateEvent` at `0x1800081bd`

## pseudocode

```c
NTSTATUS __fastcall CsrServerCreateApiPort(void **Reserved6)
{
  NTSTATUS result; // eax

  *(_DWORD *)Reserved6 = 0;
  result = NtCreateEvent(Reserved6 + 1, 0x1F0003u, 0, SynchronizationEvent, 0);
  if ( result >= 0 )
  {
    result = CsrApiPortInitialize(Reserved6);
    if ( result < 0 )
      CsrInitFailReason = 10;
  }
  else
  {
    CsrInitFailReason = 9;
  }
  return result;
}

```

## disassembly

```asm
0x180008190  mov     [rsp+arg_0], rbx
0x180008195  push    rdi
0x180008196  sub     rsp, 30h
0x18000819a  mov     rdi, rdx
0x18000819d  mov     dword ptr [rcx], 0
0x1800081a3  mov     rbx, rcx
0x1800081a6  mov     [rsp+38h+InitialState], 0; InitialState
0x1800081ab  add     rcx, 8; EventHandle
0x1800081af  mov     edx, 1F0003h; DesiredAccess
0x1800081b4  mov     r9d, 1; EventType
0x1800081ba  xor     r8d, r8d; ObjectAttributes
0x1800081bd  call    cs:__imp_NtCreateEvent
0x1800081c4  nop     dword ptr [rax+rax+00h]
0x1800081c9  test    eax, eax
0x1800081cb  jns     short loc_1800081E3
0x1800081cd  mov     cs:CsrInitFailReason, 9
0x1800081d7  mov     rbx, [rsp+38h+arg_0]
0x1800081dc  add     rsp, 30h
0x1800081e0  pop     rdi
0x1800081e1  retn
0x1800081e3  mov     rdx, rdi
0x1800081e6  mov     rcx, rbx; Reserved6
0x1800081e9  call    CsrApiPortInitialize
0x1800081ee  test    eax, eax
0x1800081f0  jns     short loc_1800081FC
0x1800081f2  mov     cs:CsrInitFailReason, 0Ah
0x1800081fc  mov     rbx, [rsp+38h+arg_0]
0x180008201  add     rsp, 30h
0x180008205  pop     rdi
0x180008206  retn
```
