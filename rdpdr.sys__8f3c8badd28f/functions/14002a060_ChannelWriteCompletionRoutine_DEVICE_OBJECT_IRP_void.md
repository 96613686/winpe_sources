# _ChannelWriteCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14002a060`
- end: `0x14002a0bf`
- name: `?_ChannelWriteCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006560`
- `0x14002a060`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002a0aa`
- `ntoskrnl!KeSetEvent` at `0x14002a0aa`

## pseudocode

```c
__int64 __fastcall _ChannelWriteCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, char *a3)
{
  unsigned int v5; // ebx

  if ( !a2 || a2->PendingReturned != 1 )
    return (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *, struct _IRP *, _QWORD))a3)(a1, a2, *((_QWORD *)a3 + 1));
  *((_DWORD *)a3 + 10) = a2->IoStatus.Status;
  v5 = (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *, struct _IRP *, _QWORD))a3)(a1, a2, *((_QWORD *)a3 + 1));
  KeSetEvent((PRKEVENT)(a3 + 16), 0, 0);
  return v5;
}

```

## disassembly

```asm
0x14002a060  push    rdi
0x14002a062  sub     rsp, 20h
0x14002a066  mov     rdi, r8
0x14002a069  test    rdx, rdx
0x14002a06c  jnz     short loc_14002A081
0x14002a06e  mov     rax, [r8]
0x14002a071  mov     r8, [r8+8]
0x14002a075  call    _guard_dispatch_icall
0x14002a07a  add     rsp, 20h
0x14002a07e  pop     rdi
0x14002a07f  retn
0x14002a081  cmp     byte ptr [rdx+41h], 1
0x14002a085  jnz     short loc_14002A06E
0x14002a087  mov     eax, [rdx+30h]
0x14002a08a  mov     [r8+28h], eax
0x14002a08e  mov     rax, [r8]
0x14002a091  mov     r8, [r8+8]
0x14002a095  mov     [rsp+28h+arg_0], rbx
0x14002a09a  call    _guard_dispatch_icall
0x14002a09f  lea     rcx, [rdi+10h]; Event
0x14002a0a3  xor     r8d, r8d; Wait
0x14002a0a6  xor     edx, edx; Increment
0x14002a0a8  mov     ebx, eax
0x14002a0aa  call    cs:__imp_KeSetEvent
0x14002a0b1  nop     dword ptr [rax+rax+00h]
0x14002a0b6  mov     eax, ebx
0x14002a0b8  mov     rbx, [rsp+28h+arg_0]
0x14002a0bd  jmp     short loc_14002A07A
```
