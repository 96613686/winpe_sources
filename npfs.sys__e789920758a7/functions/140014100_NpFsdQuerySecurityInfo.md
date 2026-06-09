# NpFsdQuerySecurityInfo

- ea: `0x140014100`
- end: `0x14001415f`
- name: `NpFsdQuerySecurityInfo`
- size: `95`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140014100`
- `0x140014170`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140014110`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014110`
- `ntoskrnl!IofCompleteRequest` at `0x140014145`
- `ntoskrnl!IofCompleteRequest` at `0x140014145`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014129`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014129`

## pseudocode

```c
__int64 __fastcall NpFsdQuerySecurityInfo(__int64 a1, IRP *a2)
{
  unsigned int SecurityInfo; // ebx

  KeEnterCriticalRegion();
  SecurityInfo = NpCommonQuerySecurityInfo(a1, (__int64)a2);
  KeLeaveCriticalRegion();
  if ( SecurityInfo != 259 )
  {
    a2->IoStatus.Status = SecurityInfo;
    IofCompleteRequest(a2, 2);
  }
  return SecurityInfo;
}

```

## disassembly

```asm
0x140014100  mov     [rsp+arg_0], rbx
0x140014105  push    rdi
0x140014106  sub     rsp, 20h
0x14001410a  mov     rdi, rdx
0x14001410d  mov     rbx, rcx
0x140014110  call    cs:__imp_KeEnterCriticalRegion
0x140014117  nop     dword ptr [rax+rax+00h]
0x14001411c  mov     rdx, rdi
0x14001411f  mov     rcx, rbx
0x140014122  call    NpCommonQuerySecurityInfo
0x140014127  mov     ebx, eax
0x140014129  call    cs:__imp_KeLeaveCriticalRegion
0x140014130  nop     dword ptr [rax+rax+00h]
0x140014135  cmp     ebx, 103h
0x14001413b  jz      short loc_140014151
0x14001413d  mov     dl, 2; PriorityBoost
0x14001413f  mov     [rdi+30h], ebx
0x140014142  mov     rcx, rdi; Irp
0x140014145  call    cs:__imp_IofCompleteRequest
0x14001414c  nop     dword ptr [rax+rax+00h]
0x140014151  mov     eax, ebx
0x140014153  mov     rbx, [rsp+28h+arg_0]
0x140014158  add     rsp, 20h
0x14001415c  pop     rdi
0x14001415d  retn
```
