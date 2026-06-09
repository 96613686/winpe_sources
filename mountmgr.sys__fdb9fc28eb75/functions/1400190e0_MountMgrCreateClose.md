# MountMgrCreateClose

- ea: `0x1400190e0`
- end: `0x14001912b`
- name: `MountMgrCreateClose`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400190e0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140019107`
- `ntoskrnl!IofCompleteRequest` at `0x140019107`

## pseudocode

```c
__int64 __fastcall MountMgrCreateClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int v3; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction || (CurrentStackLocation->Parameters.Create.Options & 1) == 0 )
    v3 = 0;
  else
    v3 = -1073741565;
  a2->IoStatus.Status = v3;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return v3;
}

```

## disassembly

```asm
0x1400190e0  push    rbx
0x1400190e2  sub     rsp, 20h
0x1400190e6  mov     rcx, [rdx+0B8h]
0x1400190ed  mov     rax, rdx
0x1400190f0  cmp     byte ptr [rcx], 0
0x1400190f3  jz      short loc_14001911C
0x1400190f5  xor     ebx, ebx
0x1400190f7  mov     [rdx+30h], ebx
0x1400190fa  mov     rcx, rax; Irp
0x1400190fd  mov     qword ptr [rdx+38h], 0
0x140019105  xor     edx, edx; PriorityBoost
0x140019107  call    cs:__imp_IofCompleteRequest
0x14001910e  nop     dword ptr [rax+rax+00h]
0x140019113  mov     eax, ebx
0x140019115  add     rsp, 20h
0x140019119  pop     rbx
0x14001911a  retn
0x14001911c  mov     ecx, [rcx+10h]
0x14001911f  test    cl, 1
0x140019122  jz      short loc_1400190F5
0x140019124  mov     ebx, 0C0000103h
0x140019129  jmp     short loc_1400190F7
```
