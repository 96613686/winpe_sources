# NameSrvCompletionRoutine

- ea: `0x14002f230`
- end: `0x14002f366`
- name: `NameSrvCompletionRoutine`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006878`
- `0x140009150`
- `0x14002f230`
- `0x140042f5c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f2aa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f2aa`
- `ntoskrnl!IoFreeMdl` at `0x14002f337`
- `ntoskrnl!IoFreeMdl` at `0x14002f337`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f327`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f327`

## pseudocode

```c
__int64 __fastcall NameSrvCompletionRoutine(struct _DEVICE_OBJECT *a1, IRP *a2, __int64 a3)
{
  int v3; // r14d
  PDEVICE_OBJECT DeviceObject; // rbp
  PMDL MdlAddress; // rcx
  char *MappedSystemVa; // rdi
  int v9; // [rsp+88h] [rbp+10h] BYREF
  __int64 v10; // [rsp+90h] [rbp+18h] BYREF

  v3 = a3;
  v10 = 0;
  v9 = 0;
  DeviceObject = a1;
  if ( (BYTE2(xmmword_140038420) & 4) != 0 )
    WPP_SF_qDP(a1, 64, a3, a3, a2->IoStatus.Status, a2->IoStatus.Information);
  MdlAddress = a2->MdlAddress;
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000020u);
  if ( MappedSystemVa )
  {
    if ( !DeviceObject )
      DeviceObject = a2->Tail.Overlay.CurrentStackLocation[-1].DeviceObject;
    TdiRcvNameSrvHandler(
      DeviceObject,
      *(unsigned int *)&MappedSystemVa[v3],
      &MappedSystemVa[v3 + 4],
      0,
      0,
      32,
      a2->IoStatus.Information,
      a2->IoStatus.Information,
      &v9,
      MappedSystemVa,
      &v10);
    ExFreePoolWithTag(MappedSystemVa, 0);
  }
  IoFreeMdl(a2->MdlAddress);
  NbtFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14002f230  mov     rax, rsp
0x14002f233  mov     [rax+8], rbx
0x14002f237  mov     [rax+20h], rbp
0x14002f23b  push    rsi
0x14002f23c  push    rdi
0x14002f23d  push    r14
0x14002f23f  sub     rsp, 60h
0x14002f243  mov     r14, r8
0x14002f246  mov     qword ptr [rax+18h], 0
0x14002f24e  mov     rbx, rdx
0x14002f251  mov     dword ptr [rax+10h], 0
0x14002f258  mov     rbp, rcx
0x14002f25b  test    byte ptr cs:xmmword_140038420+2, 4
0x14002f262  jz      short loc_14002F281
0x14002f264  mov     rax, [rbx+38h]
0x14002f268  mov     edx, 40h ; '@'
0x14002f26d  mov     qword ptr [rsp+78h+Priority], rax
0x14002f272  mov     r9, r8
0x14002f275  mov     eax, [rbx+30h]
0x14002f278  mov     [rsp+78h+BugCheckOnFailure], eax
0x14002f27c  call    WPP_SF_qDP
0x14002f281  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14002f285  test    byte ptr [rcx+0Ah], 5
0x14002f289  jz      short loc_14002F291
0x14002f28b  mov     rdi, [rcx+18h]
0x14002f28f  jmp     short loc_14002F2B9
0x14002f291  xor     r9d, r9d; RequestedAddress
0x14002f294  mov     [rsp+78h+Priority], 40000020h; Priority
0x14002f29c  xor     edx, edx; AccessMode
0x14002f29e  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002f2a6  lea     r8d, [r9+1]; CacheType
0x14002f2aa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f2b1  nop     dword ptr [rax+rax+00h]
0x14002f2b6  mov     rdi, rax
0x14002f2b9  test    rdi, rdi
0x14002f2bc  jz      short loc_14002F333
0x14002f2be  mov     r8d, r14d
0x14002f2c1  mov     edx, [r8+rdi]
0x14002f2c5  test    rbp, rbp
0x14002f2c8  jnz     short loc_14002F2D5
0x14002f2ca  mov     rcx, [rbx+0B8h]
0x14002f2d1  mov     rbp, [rcx-20h]
0x14002f2d5  mov     eax, [rbx+38h]
0x14002f2d8  lea     rcx, [rsp+78h+arg_10]
0x14002f2e0  mov     [rsp+78h+var_28], rcx
0x14002f2e5  add     r8, 4
0x14002f2e9  mov     [rsp+78h+var_30], rdi
0x14002f2ee  lea     rcx, [rsp+78h+arg_8]
0x14002f2f6  mov     [rsp+78h+var_38], rcx
0x14002f2fb  add     r8, rdi
0x14002f2fe  mov     [rsp+78h+var_40], eax
0x14002f302  xor     r9d, r9d
0x14002f305  mov     [rsp+78h+var_48], eax
0x14002f309  mov     rcx, rbp
0x14002f30c  mov     [rsp+78h+Priority], 20h ; ' '
0x14002f314  mov     qword ptr [rsp+78h+BugCheckOnFailure], 0
0x14002f31d  call    TdiRcvNameSrvHandler
0x14002f322  xor     edx, edx; Tag
0x14002f324  mov     rcx, rdi; P
0x14002f327  call    cs:__imp_ExFreePoolWithTag
0x14002f32e  nop     dword ptr [rax+rax+00h]
0x14002f333  mov     rcx, [rbx+8]; Mdl
0x14002f337  call    cs:__imp_IoFreeMdl
0x14002f33e  nop     dword ptr [rax+rax+00h]
0x14002f343  mov     rcx, rbx; Irp
0x14002f346  call    NbtFreeIrp
0x14002f34b  lea     r11, [rsp+78h+var_18]
0x14002f350  mov     eax, 0C0000016h
0x14002f355  mov     rbx, [r11+20h]
0x14002f359  mov     rbp, [r11+38h]
0x14002f35d  mov     rsp, r11
0x14002f360  pop     r14
0x14002f362  pop     rdi
0x14002f363  pop     rsi
0x14002f364  retn
```
