# MdaUserCacheFinish

- ea: `0x140036f30`
- end: `0x140036fbe`
- name: `MdaUserCacheFinish`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002edd4`

## callees

- `0x140036f30`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140036f58`
- `ntoskrnl!KeSetEvent` at `0x140036f58`
- `ntoskrnl!KeWaitForSingleObject` at `0x140036f7c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140036f7c`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140036f90`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140036f90`
- `ntoskrnl!ZwClose` at `0x140036f9f`
- `ntoskrnl!ZwClose` at `0x140036f9f`

## pseudocode

```c
NTSTATUS __fastcall MdaUserCacheFinish(__int64 a1)
{
  HANDLE *v1; // rbx
  NTSTATUS result; // eax

  v1 = (HANDLE *)(a1 + 1432);
  if ( *(_QWORD *)(a1 + 1432) )
  {
    KeSetEvent((PRKEVENT)(a1 + 2264), 16, 0);
    KeWaitForSingleObject((PVOID)(a1 + 2288), Executive, 0, 0, 0);
    ZwWaitForSingleObject(v1, 0, 0);
    result = ZwClose(*v1);
    *v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140036f30  mov     [rsp+arg_0], rbx
0x140036f35  push    rdi
0x140036f36  sub     rsp, 30h
0x140036f3a  lea     rbx, [rcx+598h]
0x140036f41  mov     rdi, rcx
0x140036f44  cmp     qword ptr [rbx], 0
0x140036f48  jz      short loc_140036FB2
0x140036f4a  xor     r8d, r8d; Wait
0x140036f4d  add     rcx, 8D8h; Event
0x140036f54  lea     edx, [r8+10h]; Increment
0x140036f58  call    cs:__imp_KeSetEvent
0x140036f5f  nop     dword ptr [rax+rax+00h]
0x140036f64  lea     rcx, [rdi+8F0h]; Object
0x140036f6b  mov     [rsp+38h+Timeout], 0; Timeout
0x140036f74  xor     r9d, r9d; Alertable
0x140036f77  xor     r8d, r8d; WaitMode
0x140036f7a  xor     edx, edx; WaitReason
0x140036f7c  call    cs:__imp_KeWaitForSingleObject
0x140036f83  nop     dword ptr [rax+rax+00h]
0x140036f88  xor     r8d, r8d; Timeout
0x140036f8b  xor     edx, edx; Alertable
0x140036f8d  mov     rcx, rbx; Handle
0x140036f90  call    cs:__imp_ZwWaitForSingleObject
0x140036f97  nop     dword ptr [rax+rax+00h]
0x140036f9c  mov     rcx, [rbx]; Handle
0x140036f9f  call    cs:__imp_ZwClose
0x140036fa6  nop     dword ptr [rax+rax+00h]
0x140036fab  mov     qword ptr [rbx], 0
0x140036fb2  mov     rbx, [rsp+38h+arg_0]
0x140036fb7  add     rsp, 30h
0x140036fbb  pop     rdi
0x140036fbc  retn
```
