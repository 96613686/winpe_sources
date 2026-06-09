# CscCancellableIrpWait

- ea: `0x14001dce4`
- end: `0x14001dd68`
- name: `CscCancellableIrpWait`
- size: `132`
- prototype: `NTSTATUS __fastcall(PIRP Irp, struct _KEVENT *Object)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008610`
- `0x140009320`

## callees

- `0x14001dce4`

## import_xrefs

- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14001dcfc`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14001dcfc`
- `ntoskrnl!KeReadStateEvent` at `0x14001dd2c`
- `ntoskrnl!KeReadStateEvent` at `0x14001dd2c`
- `ntoskrnl!IoCancelIrp` at `0x14001dd19`
- `ntoskrnl!IoCancelIrp` at `0x14001dd19`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001dd50`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001dd50`

## pseudocode

```c
NTSTATUS __fastcall CscCancellableIrpWait(PIRP Irp, struct _KEVENT *Object)
{
  NTSTATUS result; // eax

  result = FsRtlCancellableWaitForSingleObject(Object, 0, 0);
  if ( result == -1073741536 || result == -1073741749 )
  {
    if ( !IoCancelIrp(Irp) )
      return KeWaitForSingleObject(Object, Executive, 0, 0, 0);
    result = KeReadStateEvent(Object);
    if ( !result )
      return KeWaitForSingleObject(Object, Executive, 0, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x14001dce4  mov     [rsp+arg_0], rbx
0x14001dce9  push    rdi
0x14001dcea  sub     rsp, 30h
0x14001dcee  mov     rbx, rdx
0x14001dcf1  mov     rdi, rcx
0x14001dcf4  mov     rcx, rbx; Object
0x14001dcf7  xor     r8d, r8d; Irp
0x14001dcfa  xor     edx, edx; Timeout
0x14001dcfc  call    cs:__imp_FsRtlCancellableWaitForSingleObject
0x14001dd03  nop     dword ptr [rax+rax+00h]
0x14001dd08  cmp     eax, 0C0000120h
0x14001dd0d  jz      short loc_14001DD16
0x14001dd0f  cmp     eax, 0C000004Bh
0x14001dd14  jnz     short loc_14001DD5C
0x14001dd16  mov     rcx, rdi; Irp
0x14001dd19  call    cs:__imp_IoCancelIrp
0x14001dd20  nop     dword ptr [rax+rax+00h]
0x14001dd25  test    al, al
0x14001dd27  jz      short loc_14001DD3C
0x14001dd29  mov     rcx, rbx; Event
0x14001dd2c  call    cs:__imp_KeReadStateEvent
0x14001dd33  nop     dword ptr [rax+rax+00h]
0x14001dd38  test    eax, eax
0x14001dd3a  jnz     short loc_14001DD5C
0x14001dd3c  xor     r9d, r9d; Alertable
0x14001dd3f  mov     [rsp+38h+Timeout], 0; Timeout
0x14001dd48  xor     r8d, r8d; WaitMode
0x14001dd4b  xor     edx, edx; WaitReason
0x14001dd4d  mov     rcx, rbx; Object
0x14001dd50  call    cs:__imp_KeWaitForSingleObject
0x14001dd57  nop     dword ptr [rax+rax+00h]
0x14001dd5c  mov     rbx, [rsp+38h+arg_0]
0x14001dd61  add     rsp, 30h
0x14001dd65  pop     rdi
0x14001dd66  retn
```
