# NpFsdFileSystemControl

- ea: `0x14000ef40`
- end: `0x14000ef9f`
- name: `NpFsdFileSystemControl`
- size: `95`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ef40`
- `0x14000efb0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ef50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ef50`
- `ntoskrnl!IofCompleteRequest` at `0x14000ef85`
- `ntoskrnl!IofCompleteRequest` at `0x14000ef85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ef69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ef69`

## pseudocode

```c
__int64 __fastcall NpFsdFileSystemControl(__int64 a1, IRP *a2)
{
  __int64 v4; // r8
  unsigned int v5; // ebx

  KeEnterCriticalRegion();
  v5 = NpCommonFileSystemControl(a1, (__int64)a2, v4);
  KeLeaveCriticalRegion();
  if ( v5 != 259 )
  {
    a2->IoStatus.Status = v5;
    IofCompleteRequest(a2, 2);
  }
  return v5;
}

```

## disassembly

```asm
0x14000ef40  mov     [rsp+arg_0], rbx
0x14000ef45  push    rdi
0x14000ef46  sub     rsp, 20h
0x14000ef4a  mov     rdi, rdx
0x14000ef4d  mov     rbx, rcx
0x14000ef50  call    cs:__imp_KeEnterCriticalRegion
0x14000ef57  nop     dword ptr [rax+rax+00h]
0x14000ef5c  mov     rdx, rdi
0x14000ef5f  mov     rcx, rbx
0x14000ef62  call    NpCommonFileSystemControl
0x14000ef67  mov     ebx, eax
0x14000ef69  call    cs:__imp_KeLeaveCriticalRegion
0x14000ef70  nop     dword ptr [rax+rax+00h]
0x14000ef75  cmp     ebx, 103h
0x14000ef7b  jz      short loc_14000EF91
0x14000ef7d  mov     dl, 2; PriorityBoost
0x14000ef7f  mov     [rdi+30h], ebx
0x14000ef82  mov     rcx, rdi; Irp
0x14000ef85  call    cs:__imp_IofCompleteRequest
0x14000ef8c  nop     dword ptr [rax+rax+00h]
0x14000ef91  mov     eax, ebx
0x14000ef93  mov     rbx, [rsp+28h+arg_0]
0x14000ef98  add     rsp, 20h
0x14000ef9c  pop     rdi
0x14000ef9d  retn
```
