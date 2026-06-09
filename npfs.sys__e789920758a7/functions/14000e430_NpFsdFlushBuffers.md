# NpFsdFlushBuffers

- ea: `0x14000e430`
- end: `0x14000e489`
- name: `NpFsdFlushBuffers`
- size: `89`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000e430`
- `0x14000e490`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e43d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e43d`
- `ntoskrnl!IofCompleteRequest` at `0x14000e46f`
- `ntoskrnl!IofCompleteRequest` at `0x14000e46f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e453`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e453`

## pseudocode

```c
__int64 __fastcall NpFsdFlushBuffers(__int64 a1, IRP *a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // ebx

  KeEnterCriticalRegion();
  v6 = NpCommonFlushBuffers(v3, (__int64)a2, v4, v5);
  KeLeaveCriticalRegion();
  if ( v6 != 259 )
  {
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 2);
  }
  return v6;
}

```

## disassembly

```asm
0x14000e430  mov     [rsp+arg_0], rbx
0x14000e435  push    rdi
0x14000e436  sub     rsp, 20h
0x14000e43a  mov     rdi, rdx
0x14000e43d  call    cs:__imp_KeEnterCriticalRegion
0x14000e444  nop     dword ptr [rax+rax+00h]
0x14000e449  mov     rdx, rdi
0x14000e44c  call    NpCommonFlushBuffers
0x14000e451  mov     ebx, eax
0x14000e453  call    cs:__imp_KeLeaveCriticalRegion
0x14000e45a  nop     dword ptr [rax+rax+00h]
0x14000e45f  cmp     ebx, 103h
0x14000e465  jz      short loc_14000E47B
0x14000e467  mov     dl, 2; PriorityBoost
0x14000e469  mov     [rdi+30h], ebx
0x14000e46c  mov     rcx, rdi; Irp
0x14000e46f  call    cs:__imp_IofCompleteRequest
0x14000e476  nop     dword ptr [rax+rax+00h]
0x14000e47b  mov     eax, ebx
0x14000e47d  mov     rbx, [rsp+28h+arg_0]
0x14000e482  add     rsp, 20h
0x14000e486  pop     rdi
0x14000e487  retn
```
