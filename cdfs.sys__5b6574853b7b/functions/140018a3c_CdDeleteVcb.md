# CdDeleteVcb

- ea: `0x140018a3c`
- end: `0x140018bc2`
- name: `CdDeleteVcb`
- size: `390`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400024e0`
- `0x140002630`

## callees

- `0x140018a3c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018a53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018a75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018aa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018acb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018a53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018a75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018aa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018acb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b71`
- `ntoskrnl!ObfDereferenceObject` at `0x140018a92`
- `ntoskrnl!ObfDereferenceObject` at `0x140018a92`
- `ntoskrnl!IoDeleteDevice` at `0x140018ba8`
- `ntoskrnl!IoDeleteDevice` at `0x140018ba8`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018b0c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018b44`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018b57`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018b0c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018b44`
- `ntoskrnl!ExDeleteResourceLite` at `0x140018b57`
- `ntoskrnl!IoFreeIrp` at `0x140018aee`
- `ntoskrnl!IoFreeIrp` at `0x140018aee`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140018b95`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140018b95`

## pseudocode

```c
void __fastcall CdDeleteVcb(__int64 a1, __int64 a2)
{
  void *v2; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  IRP *v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  void *v11; // rcx

  v2 = *(void **)(a2 + 560);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a2 + 560) = 0;
  }
  v4 = *(void **)(a2 + 8);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *(_QWORD *)(a2 + 8) = 0;
  }
  v5 = *(void **)(a2 + 16);
  if ( v5 )
    ObfDereferenceObject(v5);
  v6 = *(void **)(a2 + 112);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *(_QWORD *)(a2 + 112) = 0;
  }
  v7 = *(void **)(a2 + 568);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0);
    *(_QWORD *)(a2 + 568) = 0;
  }
  v8 = *(IRP **)(a2 + 648);
  if ( v8 )
  {
    IoFreeIrp(v8);
    *(_QWORD *)(a2 + 648) = 0;
    ExDeleteResourceLite((PERESOURCE)(a2 + 680));
  }
  v9 = *(_QWORD *)(a2 + 32);
  if ( *(_QWORD *)(v9 + 8) != a2 + 32 || (v10 = *(_QWORD **)(a2 + 40), *v10 != a2 + 32) )
    __fastfail(3u);
  *v10 = v9;
  *(_QWORD *)(v9 + 8) = v10;
  ExDeleteResourceLite((PERESOURCE)(a2 + 128));
  ExDeleteResourceLite((PERESOURCE)(a2 + 232));
  v11 = *(void **)(a2 + 520);
  if ( v11 )
  {
    ExFreePoolWithTag(v11, 0);
    *(_QWORD *)(a2 + 520) = 0;
  }
  if ( *(_QWORD *)(a2 + 400) )
    FsRtlNotifyUninitializeSync((PNOTIFY_SYNC *)(a2 + 400));
  IoDeleteDevice((PDEVICE_OBJECT)(a2 - 368));
}

```

## disassembly

```asm
0x140018a3c  push    rbx
0x140018a3e  sub     rsp, 20h
0x140018a42  mov     rcx, [rdx+230h]; P
0x140018a49  mov     rbx, rdx
0x140018a4c  test    rcx, rcx
0x140018a4f  jz      short loc_140018A6A
0x140018a51  xor     edx, edx; Tag
0x140018a53  call    cs:__imp_ExFreePoolWithTag
0x140018a5a  nop     dword ptr [rax+rax+00h]
0x140018a5f  mov     qword ptr [rbx+230h], 0
0x140018a6a  mov     rcx, [rbx+8]; P
0x140018a6e  test    rcx, rcx
0x140018a71  jz      short loc_140018A89
0x140018a73  xor     edx, edx; Tag
0x140018a75  call    cs:__imp_ExFreePoolWithTag
0x140018a7c  nop     dword ptr [rax+rax+00h]
0x140018a81  mov     qword ptr [rbx+8], 0
0x140018a89  mov     rcx, [rbx+10h]; Object
0x140018a8d  test    rcx, rcx
0x140018a90  jz      short loc_140018A9E
0x140018a92  call    cs:__imp_ObfDereferenceObject
0x140018a99  nop     dword ptr [rax+rax+00h]
0x140018a9e  mov     rcx, [rbx+70h]; P
0x140018aa2  test    rcx, rcx
0x140018aa5  jz      short loc_140018ABD
0x140018aa7  xor     edx, edx; Tag
0x140018aa9  call    cs:__imp_ExFreePoolWithTag
0x140018ab0  nop     dword ptr [rax+rax+00h]
0x140018ab5  mov     qword ptr [rbx+70h], 0
0x140018abd  mov     rcx, [rbx+238h]; P
0x140018ac4  test    rcx, rcx
0x140018ac7  jz      short loc_140018AE2
0x140018ac9  xor     edx, edx; Tag
0x140018acb  call    cs:__imp_ExFreePoolWithTag
0x140018ad2  nop     dword ptr [rax+rax+00h]
0x140018ad7  mov     qword ptr [rbx+238h], 0
0x140018ae2  mov     rcx, [rbx+288h]; Irp
0x140018ae9  test    rcx, rcx
0x140018aec  jz      short loc_140018B18
0x140018aee  call    cs:__imp_IoFreeIrp
0x140018af5  nop     dword ptr [rax+rax+00h]
0x140018afa  lea     rcx, [rbx+2A8h]; Resource
0x140018b01  mov     qword ptr [rbx+288h], 0
0x140018b0c  call    cs:__imp_ExDeleteResourceLite
0x140018b13  nop     dword ptr [rax+rax+00h]
0x140018b18  lea     rax, [rbx+20h]
0x140018b1c  mov     rcx, [rax]
0x140018b1f  cmp     [rcx+8], rax
0x140018b23  jnz     loc_140018BBB
0x140018b29  mov     rdx, [rax+8]
0x140018b2d  cmp     [rdx], rax
0x140018b30  jnz     loc_140018BBB
0x140018b36  mov     [rdx], rcx
0x140018b39  mov     [rcx+8], rdx
0x140018b3d  lea     rcx, [rbx+80h]; Resource
0x140018b44  call    cs:__imp_ExDeleteResourceLite
0x140018b4b  nop     dword ptr [rax+rax+00h]
0x140018b50  lea     rcx, [rbx+0E8h]; Resource
0x140018b57  call    cs:__imp_ExDeleteResourceLite
0x140018b5e  nop     dword ptr [rax+rax+00h]
0x140018b63  mov     rcx, [rbx+208h]; P
0x140018b6a  test    rcx, rcx
0x140018b6d  jz      short loc_140018B88
0x140018b6f  xor     edx, edx; Tag
0x140018b71  call    cs:__imp_ExFreePoolWithTag
0x140018b78  nop     dword ptr [rax+rax+00h]
0x140018b7d  mov     qword ptr [rbx+208h], 0
0x140018b88  lea     rcx, [rbx+190h]; NotifySync
0x140018b8f  cmp     qword ptr [rcx], 0
0x140018b93  jz      short loc_140018BA1
0x140018b95  call    cs:__imp_FsRtlNotifyUninitializeSync
0x140018b9c  nop     dword ptr [rax+rax+00h]
0x140018ba1  lea     rcx, [rbx-170h]; DeviceObject
0x140018ba8  call    cs:__imp_IoDeleteDevice
0x140018baf  nop     dword ptr [rax+rax+00h]
0x140018bb4  add     rsp, 20h
0x140018bb8  pop     rbx
0x140018bb9  retn
0x140018bbb  mov     ecx, 3
0x140018bc0  int     29h; Win8: RtlFailFast(ecx)
```
