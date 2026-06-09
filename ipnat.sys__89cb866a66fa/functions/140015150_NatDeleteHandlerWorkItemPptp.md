# NatDeleteHandlerWorkItemPptp

- ea: `0x140015150`
- end: `0x140015263`
- name: `NatDeleteHandlerWorkItemPptp`
- size: `275`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000218c`
- `0x140015150`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140015196`
- `ntoskrnl!IoFreeWorkItem` at `0x140015196`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001521d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001521d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001520c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001520c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151a9`

## pseudocode

```c
void __fastcall NatDeleteHandlerWorkItemPptp(PDEVICE_OBJECT DeviceObject, PIO_WORKITEM *Context)
{
  KIRQL v3; // al
  PVOID *i; // rdx
  __int64 j; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
  IoFreeWorkItem(Context[1]);
  v3 = KeAcquireSpinLockRaiseToDpc(&PptpMappingLock);
  for ( i = (PVOID *)PptpMappingList; i != &PptpMappingList; i = (PVOID *)*i )
  {
    if ( *Context == i[4] )
      *((_DWORD *)i + 14) |= 2u;
  }
  for ( j = qword_1400320D0; (__int64 *)j != &qword_1400320D0; j = *(_QWORD *)j )
  {
    if ( *Context == *(PIO_WORKITEM *)(j + 16) )
      *(_DWORD *)(j + 40) |= 2u;
  }
  KeReleaseSpinLock(&PptpMappingLock, v3);
  ExFreePoolWithTag(Context, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
}

```

## disassembly

```asm
0x140015150  mov     [rsp+arg_0], rbx
0x140015155  push    rdi
0x140015156  sub     rsp, 20h
0x14001515a  mov     rbx, rdx
0x14001515d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015164  lea     rdi, WPP_GLOBAL_Control
0x14001516b  cmp     rcx, rdi
0x14001516e  jz      short loc_140015192
0x140015170  mov     eax, [rcx+2Ch]
0x140015173  test    al, 1
0x140015175  jz      short loc_140015192
0x140015177  cmp     byte ptr [rcx+29h], 6
0x14001517b  jb      short loc_140015192
0x14001517d  mov     rcx, [rcx+18h]
0x140015181  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140015188  mov     edx, 47h ; 'G'
0x14001518d  call    WPP_SF_
0x140015192  mov     rcx, [rbx+8]; IoWorkItem
0x140015196  call    cs:__imp_IoFreeWorkItem
0x14001519d  nop     dword ptr [rax+rax+00h]
0x1400151a2  lea     rcx, PptpMappingLock; SpinLock
0x1400151a9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400151b0  nop     dword ptr [rax+rax+00h]
0x1400151b5  mov     rdx, cs:PptpMappingList
0x1400151bc  mov     r8b, al
0x1400151bf  lea     rax, PptpMappingList
0x1400151c6  jmp     short loc_1400151D8
0x1400151c8  mov     rcx, [rdx+20h]
0x1400151cc  cmp     [rbx], rcx
0x1400151cf  jnz     short loc_1400151D5
0x1400151d1  or      dword ptr [rdx+38h], 2
0x1400151d5  mov     rdx, [rdx]
0x1400151d8  cmp     rdx, rax
0x1400151db  jnz     short loc_1400151C8
0x1400151dd  mov     rdx, cs:qword_1400320D0
0x1400151e4  lea     r9, qword_1400320D0
0x1400151eb  jmp     short loc_1400151FD
0x1400151ed  mov     rax, [rdx+10h]
0x1400151f1  cmp     [rbx], rax
0x1400151f4  jnz     short loc_1400151FA
0x1400151f6  or      dword ptr [rdx+28h], 2
0x1400151fa  mov     rdx, [rdx]
0x1400151fd  cmp     rdx, r9
0x140015200  jnz     short loc_1400151ED
0x140015202  mov     dl, r8b; NewIrql
0x140015205  lea     rcx, PptpMappingLock; SpinLock
0x14001520c  call    cs:__imp_KeReleaseSpinLock
0x140015213  nop     dword ptr [rax+rax+00h]
0x140015218  xor     edx, edx; Tag
0x14001521a  mov     rcx, rbx; P
0x14001521d  call    cs:__imp_ExFreePoolWithTag
0x140015224  nop     dword ptr [rax+rax+00h]
0x140015229  mov     rcx, cs:WPP_GLOBAL_Control
0x140015230  cmp     rcx, rdi
0x140015233  jz      short loc_140015257
0x140015235  mov     eax, [rcx+2Ch]
0x140015238  test    al, 1
0x14001523a  jz      short loc_140015257
0x14001523c  cmp     byte ptr [rcx+29h], 6
0x140015240  jb      short loc_140015257
0x140015242  mov     rcx, [rcx+18h]
0x140015246  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x14001524d  mov     edx, 48h ; 'H'
0x140015252  call    WPP_SF_
0x140015257  mov     rbx, [rsp+28h+arg_0]
0x14001525c  add     rsp, 20h
0x140015260  pop     rdi
0x140015261  retn
```
