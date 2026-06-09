# NatDeleteHandlerPptp

- ea: `0x140014f30`
- end: `0x140015143`
- name: `NatDeleteHandlerPptp`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000f134`
- `0x140014f30`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140015064`
- `ntoskrnl!IoAllocateWorkItem` at `0x140015064`
- `ntoskrnl!IoQueueWorkItem` at `0x1400150fd`
- `ntoskrnl!IoQueueWorkItem` at `0x1400150fd`
- `ntoskrnl!ExAllocatePool2` at `0x140014fd3`
- `ntoskrnl!ExAllocatePool2` at `0x140014fd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400150ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400150ab`

## pseudocode

```c
__int64 __fastcall NatDeleteHandlerPptp(__int64 a1, int a2)
{
  unsigned __int64 *Pool2; // rbx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  struct _IO_WORKITEM *WorkItem; // rax
  unsigned int v8; // [rsp+50h] [rbp-38h] BYREF
  _DWORD v9[13]; // [rsp+54h] [rbp-34h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
  v8 = 0;
  v9[0] = 0;
  NatQueryInformationMapping(a2, 0, (unsigned int)&v8, 0, (__int64)v9, 0, 0, 0, 0);
  Pool2 = (unsigned __int64 *)ExAllocatePool2(64, 16, 1467244878);
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225473LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 3221225473LL);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v5 = 67;
LABEL_23:
    WPP_SF_d(v4->AttachedDevice, v5, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 3221225473LL);
    return 3221225473LL;
  }
  *Pool2 = v9[0] | ((unsigned __int64)v8 << 32);
  WorkItem = IoAllocateWorkItem(NatDeviceObject);
  Pool2[1] = (unsigned __int64)WorkItem;
  if ( !WorkItem )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 3221225473LL);
    }
    ExFreePoolWithTag(Pool2, 0);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v5 = 69;
    goto LABEL_23;
  }
  IoQueueWorkItem(WorkItem, NatDeleteHandlerWorkItemPptp, DelayedWorkQueue, Pool2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140014f30  push    rbx
0x140014f32  push    rbp
0x140014f33  push    rsi
0x140014f34  push    r14
0x140014f36  sub     rsp, 68h
0x140014f3a  mov     rbx, rdx
0x140014f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f44  lea     rsi, WPP_GLOBAL_Control
0x140014f4b  lea     rbp, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140014f52  cmp     rcx, rsi
0x140014f55  jz      short loc_140014F75
0x140014f57  mov     eax, [rcx+2Ch]
0x140014f5a  test    al, 1
0x140014f5c  jz      short loc_140014F75
0x140014f5e  cmp     byte ptr [rcx+29h], 6
0x140014f62  jb      short loc_140014F75
0x140014f64  mov     rcx, [rcx+18h]
0x140014f68  mov     edx, 41h ; 'A'
0x140014f6d  mov     r8, rbp
0x140014f70  call    WPP_SF_
0x140014f75  mov     [rsp+88h+var_48], 0
0x140014f7e  lea     rax, [rsp+88h+var_34]
0x140014f83  mov     [rsp+88h+var_50], 0
0x140014f8c  lea     r8, [rsp+88h+var_38]
0x140014f91  mov     [rsp+88h+var_58], 0
0x140014f9a  xor     r9d, r9d
0x140014f9d  mov     [rsp+88h+var_60], 0
0x140014fa6  xor     edx, edx
0x140014fa8  mov     rcx, rbx
0x140014fab  mov     [rsp+88h+var_68], rax
0x140014fb0  mov     [rsp+88h+var_38], 0
0x140014fb8  mov     [rsp+88h+var_34], 0
0x140014fc0  call    NatQueryInformationMapping
0x140014fc5  mov     edx, 10h
0x140014fca  mov     r8d, 5774614Eh
0x140014fd0  lea     ecx, [rdx+30h]
0x140014fd3  call    cs:__imp_ExAllocatePool2
0x140014fda  nop     dword ptr [rax+rax+00h]
0x140014fdf  mov     rbx, rax
0x140014fe2  mov     r14d, 0C0000001h
0x140014fe8  test    rax, rax
0x140014feb  jnz     short loc_14001504B
0x140014fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140014ff4  cmp     rcx, rsi
0x140014ff7  jz      loc_1400150E5
0x140014ffd  mov     eax, [rcx+2Ch]
0x140015000  test    al, 1
0x140015002  jz      short loc_14001501C
0x140015004  cmp     byte ptr [rcx+29h], 2
0x140015008  jb      short loc_14001501C
0x14001500a  mov     rcx, [rcx+18h]
0x14001500e  lea     edx, [rbx+42h]
0x140015011  mov     r9d, r14d
0x140015014  mov     r8, rbp
0x140015017  call    WPP_SF_d
0x14001501c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015023  cmp     rcx, rsi
0x140015026  jz      loc_1400150E5
0x14001502c  mov     eax, [rcx+2Ch]
0x14001502f  test    al, 1
0x140015031  jz      loc_1400150E5
0x140015037  cmp     byte ptr [rcx+29h], 6
0x14001503b  jb      loc_1400150E5
0x140015041  mov     edx, 43h ; 'C'
0x140015046  jmp     loc_1400150D6
0x14001504b  mov     eax, [rsp+88h+var_34]
0x14001504f  mov     ecx, [rsp+88h+var_38]
0x140015053  shl     rcx, 20h
0x140015057  or      rcx, rax
0x14001505a  mov     [rbx], rcx
0x14001505d  mov     rcx, cs:NatDeviceObject; DeviceObject
0x140015064  call    cs:__imp_IoAllocateWorkItem
0x14001506b  nop     dword ptr [rax+rax+00h]
0x140015070  mov     [rbx+8], rax
0x140015074  test    rax, rax
0x140015077  jnz     short loc_1400150EA
0x140015079  mov     rcx, cs:WPP_GLOBAL_Control
0x140015080  cmp     rcx, rsi
0x140015083  jz      short loc_1400150A6
0x140015085  mov     eax, [rcx+2Ch]
0x140015088  test    al, 1
0x14001508a  jz      short loc_1400150A6
0x14001508c  cmp     byte ptr [rcx+29h], 2
0x140015090  jb      short loc_1400150A6
0x140015092  mov     rcx, [rcx+18h]
0x140015096  mov     edx, 44h ; 'D'
0x14001509b  mov     r9d, r14d
0x14001509e  mov     r8, rbp
0x1400150a1  call    WPP_SF_d
0x1400150a6  xor     edx, edx; Tag
0x1400150a8  mov     rcx, rbx; P
0x1400150ab  call    cs:__imp_ExFreePoolWithTag
0x1400150b2  nop     dword ptr [rax+rax+00h]
0x1400150b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150be  cmp     rcx, rsi
0x1400150c1  jz      short loc_1400150E5
0x1400150c3  mov     edx, [rcx+2Ch]
0x1400150c6  test    dl, 1
0x1400150c9  jz      short loc_1400150E5
0x1400150cb  cmp     byte ptr [rcx+29h], 6
0x1400150cf  jb      short loc_1400150E5
0x1400150d1  mov     edx, 45h ; 'E'
0x1400150d6  mov     rcx, [rcx+18h]
0x1400150da  mov     r9d, r14d
0x1400150dd  mov     r8, rbp
0x1400150e0  call    WPP_SF_d
0x1400150e5  mov     eax, r14d
0x1400150e8  jmp     short loc_140015138
0x1400150ea  mov     r9, rbx; Context
0x1400150ed  lea     rdx, NatDeleteHandlerWorkItemPptp; WorkerRoutine
0x1400150f4  mov     r8d, 1; QueueType
0x1400150fa  mov     rcx, rax; IoWorkItem
0x1400150fd  call    cs:__imp_IoQueueWorkItem
0x140015104  nop     dword ptr [rax+rax+00h]
0x140015109  mov     rcx, cs:WPP_GLOBAL_Control
0x140015110  cmp     rcx, rsi
0x140015113  jz      short loc_140015136
0x140015115  mov     eax, [rcx+2Ch]
0x140015118  test    al, 1
0x14001511a  jz      short loc_140015136
0x14001511c  cmp     byte ptr [rcx+29h], 6
0x140015120  jb      short loc_140015136
0x140015122  mov     rcx, [rcx+18h]
0x140015126  mov     edx, 46h ; 'F'
0x14001512b  xor     r9d, r9d
0x14001512e  mov     r8, rbp
0x140015131  call    WPP_SF_d
0x140015136  xor     eax, eax
0x140015138  add     rsp, 68h
0x14001513c  pop     r14
0x14001513e  pop     rsi
0x14001513f  pop     rbp
0x140015140  pop     rbx
0x140015141  retn
```
