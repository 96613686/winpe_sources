# FeAllocateNblTrackerContext

- ea: `0x140065c8c`
- end: `0x140065d88`
- name: `FeAllocateNblTrackerContext`
- size: `252`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001ba48`
- `0x140066954`

## callees

- `0x140065c8c`
- `0x140078400`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140065d6e`
- `ntoskrnl!IoFreeWorkItem` at `0x140065d6e`
- `ntoskrnl!IoAllocateWorkItem` at `0x140065cde`
- `ntoskrnl!IoAllocateWorkItem` at `0x140065cde`
- `ntoskrnl!ExAllocatePool2` at `0x140065cc1`
- `ntoskrnl!ExAllocatePool2` at `0x140065cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065d58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065d58`
- `NDIS!NdisNblTrackerRegisterComponentEx` at `0x140065d30`
- `NDIS!NdisNblTrackerRegisterComponentEx` at `0x140065d30`

## pseudocode

```c
struct _IO_WORKITEM **__fastcall FeAllocateNblTrackerContext(unsigned __int64 a1, __int64 a2, int a3)
{
  struct _IO_WORKITEM **Pool2; // rbx
  struct _IO_WORKITEM *WorkItem; // rax
  struct _IO_WORKITEM **result; // rax
  _OWORD v9[4]; // [rsp+20h] [rbp-40h] BYREF

  memset(v9, 0, sizeof(v9));
  Pool2 = (struct _IO_WORKITEM **)ExAllocatePool2(64, 32, 1131439703);
  WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)&gWfpGlobal[9].L.FreeMisses);
  if ( Pool2 )
  {
    if ( WorkItem )
    {
      *(_QWORD *)&v9[1] = &WfpCalloutNblTrackerName;
      v9[3] = 0;
      *(_QWORD *)&v9[0] = 0x10300390180LL;
      *((_QWORD *)&v9[0] + 1) = Pool2;
      v9[2] = a1;
      *((_QWORD *)&v9[1] + 1) = a2;
      *Pool2 = WorkItem;
      Pool2[1] = (struct _IO_WORKITEM *)NdisNblTrackerRegisterComponentEx(v9);
      result = Pool2;
      Pool2[2] = (struct _IO_WORKITEM *)1;
      *((_DWORD *)Pool2 + 6) = a3;
      return result;
    }
    ExFreePoolWithTag(Pool2, 0x43706657u);
  }
  else if ( WorkItem )
  {
    IoFreeWorkItem(WorkItem);
  }
  return 0;
}

```

## disassembly

```asm
0x140065c8c  push    rbp
0x140065c8e  push    rbx
0x140065c8f  push    rsi
0x140065c90  push    rdi
0x140065c91  push    r14
0x140065c93  mov     rbp, rsp
0x140065c96  sub     rsp, 60h
0x140065c9a  mov     edi, r8d
0x140065c9d  mov     rsi, rdx
0x140065ca0  mov     r14, rcx
0x140065ca3  mov     ebx, 40h ; '@'
0x140065ca8  mov     r8d, ebx; Size
0x140065cab  lea     rcx, [rbp+var_40]; void *
0x140065caf  xor     edx, edx; Val
0x140065cb1  call    memset
0x140065cb6  lea     edx, [rbx-20h]
0x140065cb9  mov     r8d, 43706657h
0x140065cbf  mov     ecx, ebx
0x140065cc1  call    cs:__imp_ExAllocatePool2
0x140065cc8  nop     dword ptr [rax+rax+00h]
0x140065ccd  mov     rcx, cs:gWfpGlobal
0x140065cd4  mov     rbx, rax
0x140065cd7  mov     rcx, [rcx+4A0h]; DeviceObject
0x140065cde  call    cs:__imp_IoAllocateWorkItem
0x140065ce5  nop     dword ptr [rax+rax+00h]
0x140065cea  test    rbx, rbx
0x140065ced  jz      short loc_140065D66
0x140065cef  test    rax, rax
0x140065cf2  jz      short loc_140065D50
0x140065cf4  lea     rcx, WfpCalloutNblTrackerName
0x140065cfb  mov     [rbp+var_18], 0
0x140065d03  mov     [rbp+var_30], rcx
0x140065d07  xorps   xmm0, xmm0
0x140065d0a  movdqa  [rbp+var_10], xmm0
0x140065d0f  lea     rcx, [rbp+var_40]
0x140065d13  mov     [rbp+var_40], 390180h
0x140065d1a  mov     [rbp+var_3C], 103h
0x140065d21  mov     [rbp+var_38], rbx
0x140065d25  mov     [rbp+var_20], r14
0x140065d29  mov     [rbp+var_28], rsi
0x140065d2d  mov     [rbx], rax
0x140065d30  call    cs:__imp_NdisNblTrackerRegisterComponentEx
0x140065d37  nop     dword ptr [rax+rax+00h]
0x140065d3c  mov     [rbx+8], rax
0x140065d40  mov     rax, rbx
0x140065d43  mov     qword ptr [rbx+10h], 1
0x140065d4b  mov     [rbx+18h], edi
0x140065d4e  jmp     short loc_140065D7C
0x140065d50  mov     edx, 43706657h; Tag
0x140065d55  mov     rcx, rbx; P
0x140065d58  call    cs:__imp_ExFreePoolWithTag
0x140065d5f  nop     dword ptr [rax+rax+00h]
0x140065d64  jmp     short loc_140065D7A
0x140065d66  test    rax, rax
0x140065d69  jz      short loc_140065D7A
0x140065d6b  mov     rcx, rax; IoWorkItem
0x140065d6e  call    cs:__imp_IoFreeWorkItem
0x140065d75  nop     dword ptr [rax+rax+00h]
0x140065d7a  xor     eax, eax
0x140065d7c  add     rsp, 60h
0x140065d80  pop     r14
0x140065d82  pop     rdi
0x140065d83  pop     rsi
0x140065d84  pop     rbx
0x140065d85  pop     rbp
0x140065d86  retn
```
