# NatInitializeDynamicTicketManagement

- ea: `0x14001d888`
- end: `0x14001d965`
- name: `NatInitializeDynamicTicketManagement`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006f00`

## callees

- `0x14000218c`
- `0x14001d888`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d924`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d924`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d8df`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d8df`

## pseudocode

```c
void NatInitializeDynamicTicketManagement()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  qword_140031F58 = (__int64)&DynamicTicketList;
  DynamicTicketList = &DynamicTicketList;
  KeInitializeSpinLock(&DynamicTicketLock);
  DynamicTicketCount = 0;
  ExInitializeNPagedLookasideList(&TicketLookasideList, NatAllocateFunction, 0, 0x200u, 0x40u, 0x5474614Eu, 0x14u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
}

```

## disassembly

```asm
0x14001d888  push    rbx
0x14001d88a  sub     rsp, 40h
0x14001d88e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d895  lea     rbx, WPP_GLOBAL_Control
0x14001d89c  cmp     rcx, rbx
0x14001d89f  jz      short loc_14001D8C3
0x14001d8a1  mov     eax, [rcx+2Ch]
0x14001d8a4  test    al, 1
0x14001d8a6  jz      short loc_14001D8C3
0x14001d8a8  cmp     byte ptr [rcx+29h], 6
0x14001d8ac  jb      short loc_14001D8C3
0x14001d8ae  mov     rcx, [rcx+18h]
0x14001d8b2  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d8b9  mov     edx, 32h ; '2'
0x14001d8be  call    WPP_SF_
0x14001d8c3  lea     rax, DynamicTicketList
0x14001d8ca  lea     rcx, DynamicTicketLock; SpinLock
0x14001d8d1  mov     cs:qword_140031F58, rax
0x14001d8d8  mov     cs:DynamicTicketList, rax
0x14001d8df  call    cs:__imp_KeInitializeSpinLock
0x14001d8e6  nop     dword ptr [rax+rax+00h]
0x14001d8eb  mov     [rsp+48h+Depth], 14h; Depth
0x14001d8f2  lea     rdx, NatAllocateFunction; Allocate
0x14001d8f9  mov     [rsp+48h+Tag], 5474614Eh; Tag
0x14001d901  lea     rcx, TicketLookasideList; Lookaside
0x14001d908  mov     r9d, 200h; Flags
0x14001d90e  mov     [rsp+48h+Size], 40h ; '@'; Size
0x14001d917  xor     r8d, r8d; Free
0x14001d91a  mov     cs:DynamicTicketCount, 0
0x14001d924  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001d92b  nop     dword ptr [rax+rax+00h]
0x14001d930  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d937  cmp     rcx, rbx
0x14001d93a  jz      short loc_14001D95E
0x14001d93c  mov     eax, [rcx+2Ch]
0x14001d93f  test    al, 1
0x14001d941  jz      short loc_14001D95E
0x14001d943  cmp     byte ptr [rcx+29h], 6
0x14001d947  jb      short loc_14001D95E
0x14001d949  mov     rcx, [rcx+18h]
0x14001d94d  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d954  mov     edx, 33h ; '3'
0x14001d959  call    WPP_SF_
0x14001d95e  add     rsp, 40h
0x14001d962  pop     rbx
0x14001d963  retn
```
