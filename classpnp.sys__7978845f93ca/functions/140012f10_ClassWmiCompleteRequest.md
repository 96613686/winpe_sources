# ClassWmiCompleteRequest

- ea: `0x140012f10`
- end: `0x140012ff4`
- name: `ClassWmiCompleteRequest`
- size: `228`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, NTSTATUS Status, ULONG BufferUsed, CCHAR PriorityBoost)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001f634`
- `0x14005eb30`

## callees

- `0x140005190`
- `0x140012f10`
- `0x1400134a0`

## pseudocode

```c
NTSTATUS __stdcall ClassWmiCompleteRequest(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        NTSTATUS Status,
        ULONG BufferUsed,
        CCHAR PriorityBoost)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  NTSTATUS v6; // ebx
  _NAMED_PIPE_CREATE_PARAMETERS *Parameters; // r10
  ULONG v10; // ecx
  __int64 v12; // rax

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v6 = Status;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 0u:
      v10 = BufferUsed + 72;
      if ( Status < 0 )
        goto LABEL_14;
      Parameters->NamedPipeType = v10;
      v12 = MEMORY[0xFFFFF78000000014];
      Parameters[1].ReadMode |= 0x10u;
      Parameters[1].MaximumInstances = 1;
LABEL_12:
      Parameters[1].OutboundQuota = BufferUsed;
      goto LABEL_13;
    case 1u:
      v10 = BufferUsed + Parameters[1].InboundQuota;
      if ( Status < 0 )
        goto LABEL_14;
      Parameters->NamedPipeType = v10;
      v12 = MEMORY[0xFFFFF78000000014];
      goto LABEL_12;
    case 9u:
      v10 = BufferUsed + Parameters[1].OutboundQuota;
      if ( Status >= 0 )
      {
        Parameters->NamedPipeType = v10;
        v12 = MEMORY[0xFFFFF78000000014];
        Parameters[1].DefaultTimeout.LowPart = BufferUsed;
LABEL_13:
        *(_QWORD *)&Parameters->InboundQuota = v12;
        goto LABEL_5;
      }
LABEL_14:
      if ( Status == -1073741789 )
      {
        Parameters[1].CompletionMode = v10;
        Parameters->NamedPipeType = 56;
        v10 = 56;
        Parameters[1].ReadMode = 32;
        v6 = 0;
        goto LABEL_5;
      }
      break;
  }
  v10 = 0;
LABEL_5:
  Irp->IoStatus.Information = v10;
  Irp->IoStatus.Status = v6;
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, PriorityBoost);
  return v6;
}

```

## disassembly

```asm
0x140012f10  mov     [rsp+arg_0], rbx
0x140012f15  mov     [rsp+arg_8], rsi
0x140012f1a  push    rdi
0x140012f1b  sub     rsp, 20h
0x140012f1f  mov     rax, [rdx+0B8h]
0x140012f26  mov     ebx, r8d
0x140012f29  mov     rdi, rdx
0x140012f2c  mov     rsi, rcx
0x140012f2f  movzx   r8d, byte ptr [rax+1]
0x140012f34  mov     r10, [rax+20h]
0x140012f38  test    r8d, r8d
0x140012f3b  jz      loc_140012FC9
0x140012f41  sub     r8d, 1
0x140012f45  jz      short loc_140012FA8
0x140012f47  cmp     r8d, 8
0x140012f4b  jz      short loc_140012F83
0x140012f4d  xor     ecx, ecx
0x140012f4f  mov     eax, ecx
0x140012f51  mov     rcx, rsi; DeviceObject
0x140012f54  mov     [rdx+38h], rax
0x140012f58  mov     [rdx+30h], ebx
0x140012f5b  call    ClassReleaseRemoveLock
0x140012f60  mov     r8b, [rsp+28h+PriorityBoost]; PriorityBoost
0x140012f65  mov     rdx, rdi; Irp
0x140012f68  mov     rcx, rsi; DeviceObject
0x140012f6b  call    ClassCompleteRequest
0x140012f70  mov     rsi, [rsp+28h+arg_8]
0x140012f75  mov     eax, ebx
0x140012f77  mov     rbx, [rsp+28h+arg_0]
0x140012f7c  add     rsp, 20h
0x140012f80  pop     rdi
0x140012f81  retn
0x140012f83  mov     ecx, [r10+3Ch]
0x140012f87  add     ecx, r9d
0x140012f8a  test    ebx, ebx
0x140012f8c  js      loc_14004023B
0x140012f92  mov     [r10], ecx
0x140012f95  mov     rax, ds:0FFFFF78000000014h
0x140012f9f  mov     [r10+40h], r9d
0x140012fa3  jmp     loc_140040232
0x140012fa8  mov     ecx, [r10+38h]
0x140012fac  add     ecx, r9d
0x140012faf  test    ebx, ebx
0x140012fb1  js      loc_14004023B
0x140012fb7  mov     [r10], ecx
0x140012fba  mov     rax, ds:0FFFFF78000000014h
0x140012fc4  jmp     loc_14004022E
0x140012fc9  lea     ecx, [r9+48h]
0x140012fcd  test    ebx, ebx
0x140012fcf  js      loc_14004023B
0x140012fd5  mov     [r10], ecx
0x140012fd8  mov     rax, ds:0FFFFF78000000014h
0x140012fe2  or      dword ptr [r10+2Ch], 10h
0x140012fe7  mov     dword ptr [r10+34h], 1
0x140012fef  jmp     loc_14004022E
0x14004022e  mov     [r10+3Ch], r9d
0x140040232  mov     [r10+10h], rax
0x140040236  jmp     loc_140012F4F
0x14004023b  cmp     ebx, 0C0000023h
0x140040241  jnz     loc_140012F4D
0x140040247  mov     eax, 38h ; '8'
0x14004024c  mov     [r10+30h], ecx
0x140040250  mov     [r10], eax
0x140040253  mov     ecx, eax
0x140040255  mov     dword ptr [r10+2Ch], 20h ; ' '
0x14004025d  xor     ebx, ebx
0x14004025f  jmp     loc_140012F4F
```
