# NpFsdQueryInformation

- ea: `0x140014370`
- end: `0x1400143c9`
- name: `NpFsdQueryInformation`
- size: `89`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140014370`
- `0x1400143d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001437d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001437d`
- `ntoskrnl!IofCompleteRequest` at `0x1400143af`
- `ntoskrnl!IofCompleteRequest` at `0x1400143af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014393`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014393`

## pseudocode

```c
__int64 __fastcall NpFsdQueryInformation(__int64 a1, IRP *a2)
{
  __int64 v3; // rcx
  unsigned int Information; // ebx

  KeEnterCriticalRegion();
  Information = NpCommonQueryInformation(v3, a2);
  KeLeaveCriticalRegion();
  if ( Information != 259 )
  {
    a2->IoStatus.Status = Information;
    IofCompleteRequest(a2, 2);
  }
  return Information;
}

```

## disassembly

```asm
0x140014370  mov     [rsp+arg_0], rbx
0x140014375  push    rdi
0x140014376  sub     rsp, 20h
0x14001437a  mov     rdi, rdx
0x14001437d  call    cs:__imp_KeEnterCriticalRegion
0x140014384  nop     dword ptr [rax+rax+00h]
0x140014389  mov     rdx, rdi
0x14001438c  call    NpCommonQueryInformation
0x140014391  mov     ebx, eax
0x140014393  call    cs:__imp_KeLeaveCriticalRegion
0x14001439a  nop     dword ptr [rax+rax+00h]
0x14001439f  cmp     ebx, 103h
0x1400143a5  jz      short loc_1400143BB
0x1400143a7  mov     dl, 2; PriorityBoost
0x1400143a9  mov     [rdi+30h], ebx
0x1400143ac  mov     rcx, rdi; Irp
0x1400143af  call    cs:__imp_IofCompleteRequest
0x1400143b6  nop     dword ptr [rax+rax+00h]
0x1400143bb  mov     eax, ebx
0x1400143bd  mov     rbx, [rsp+28h+arg_0]
0x1400143c2  add     rsp, 20h
0x1400143c6  pop     rdi
0x1400143c7  retn
```
