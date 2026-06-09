# NpFsdQueryVolumeInformation

- ea: `0x140016390`
- end: `0x1400163d0`
- name: `NpFsdQueryVolumeInformation`
- size: `64`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140016390`
- `0x1400163d8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400163b6`
- `ntoskrnl!IofCompleteRequest` at `0x1400163b6`

## pseudocode

```c
__int64 __fastcall NpFsdQueryVolumeInformation(__int64 a1, IRP *a2)
{
  NTSTATUS VolumeInformation; // eax
  unsigned int v4; // ebx

  VolumeInformation = NpCommonQueryVolumeInformation(a2);
  v4 = VolumeInformation;
  if ( VolumeInformation != 259 )
  {
    a2->IoStatus.Status = VolumeInformation;
    IofCompleteRequest(a2, 2);
  }
  return v4;
}

```

## disassembly

```asm
0x140016390  mov     [rsp+arg_0], rbx
0x140016395  push    rdi
0x140016396  sub     rsp, 20h
0x14001639a  mov     rcx, rdx
0x14001639d  mov     rdi, rdx
0x1400163a0  call    NpCommonQueryVolumeInformation
0x1400163a5  mov     ebx, eax
0x1400163a7  cmp     eax, 103h
0x1400163ac  jz      short loc_1400163C2
0x1400163ae  mov     dl, 2; PriorityBoost
0x1400163b0  mov     [rdi+30h], eax
0x1400163b3  mov     rcx, rdi; Irp
0x1400163b6  call    cs:__imp_IofCompleteRequest
0x1400163bd  nop     dword ptr [rax+rax+00h]
0x1400163c2  mov     eax, ebx
0x1400163c4  mov     rbx, [rsp+28h+arg_0]
0x1400163c9  add     rsp, 20h
0x1400163cd  pop     rdi
0x1400163ce  retn
```
