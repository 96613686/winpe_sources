# PmWritePartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_PARTITION_ATTRIBUTES_TABLE *,ulong)

- ea: `0x14001cde0`
- end: `0x14001cece`
- name: `?PmWritePartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_PARTITION_ATTRIBUTES_TABLE@@K@Z`
- size: `238`
- prototype: `int(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _PARTITION_ATTRIBUTES_TABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000ada0`

## callees

- `0x14000eea8`
- `0x140011440`
- `0x14001cde0`
- `0x14001cf74`
- `0x140020240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001ceb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ceb2`
- `ntoskrnl!ExAllocatePool2` at `0x14001ce59`
- `ntoskrnl!ExAllocatePool2` at `0x14001ce59`

## pseudocode

```c
__int64 __fastcall PmWritePartitionAttributesMbr(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        struct _PARTITION_ATTRIBUTES_TABLE *a3)
{
  int BytesPerSector; // ebx
  __int64 v7; // rbx
  __int64 Pool2; // rax
  void *v9; // rdi
  __int64 v10; // xmm1_8
  union _LARGE_INTEGER v12; // [rsp+58h] [rbp+10h] BYREF
  ULONG Length; // [rsp+68h] [rbp+20h] BYREF

  Length = 0;
  v12.QuadPart = 0;
  BytesPerSector = PmGetBytesPerSector(a1, &Length);
  if ( BytesPerSector >= 0 )
  {
    v7 = Length;
    v12.QuadPart = 2 * Length;
    if ( SC_DISK_LAYOUT::IsRegionFree((SC_DISK_LAYOUT *)a2, v12.QuadPart, Length) )
    {
      if ( (unsigned int)v7 >= 0x18 && (Pool2 = ExAllocatePool2(74, v7, 1413573968), (v9 = (void *)Pool2) != 0) )
      {
        v10 = *((_QWORD *)a3 + 2);
        *(_OWORD *)Pool2 = *(_OWORD *)a3;
        *(_QWORD *)(Pool2 + 16) = v10;
        memset((void *)(Pool2 + 24), 0, (unsigned int)(v7 - 24));
        BytesPerSector = PmSendIO(*((PDEVICE_OBJECT *)a1 + 1), 4u, v9, v7, &v12);
        ExFreePoolWithTag(v9, 0);
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
    else
    {
      return (unsigned int)-1073741275;
    }
  }
  return (unsigned int)BytesPerSector;
}

```

## disassembly

```asm
0x14001cde0  mov     rax, rsp
0x14001cde3  mov     [rax+8], rbx
0x14001cde7  mov     [rax+20h], r9d
0x14001cdeb  push    rbp
0x14001cdec  push    rsi
0x14001cded  push    rdi
0x14001cdee  sub     rsp, 30h
0x14001cdf2  mov     rdi, rdx
0x14001cdf5  mov     dword ptr [rax+20h], 0
0x14001cdfc  lea     rdx, [rax+20h]; unsigned int *
0x14001ce00  mov     qword ptr [rax+10h], 0
0x14001ce08  mov     rbp, r8
0x14001ce0b  mov     rsi, rcx
0x14001ce0e  call    ?PmGetBytesPerSector@@YAJPEAU_DEVICE_EXTENSION@@PEAK@Z; PmGetBytesPerSector(_DEVICE_EXTENSION *,ulong *)
0x14001ce13  mov     ebx, eax
0x14001ce15  test    eax, eax
0x14001ce17  js      loc_14001CEBE
0x14001ce1d  mov     ebx, [rsp+48h+Length]
0x14001ce21  mov     rcx, rdi; this
0x14001ce24  mov     r8d, ebx; unsigned int
0x14001ce27  lea     edx, [rbx+rbx]; unsigned __int64
0x14001ce2a  mov     qword ptr [rsp+48h+arg_8], rdx
0x14001ce2f  call    ?IsRegionFree@SC_DISK_LAYOUT@@QEAAE_KK@Z; SC_DISK_LAYOUT::IsRegionFree(unsigned __int64,ulong)
0x14001ce34  test    al, al
0x14001ce36  jnz     short loc_14001CE3F
0x14001ce38  mov     ebx, 0C0000225h
0x14001ce3d  jmp     short loc_14001CEBE
0x14001ce3f  cmp     ebx, 18h
0x14001ce42  jnb     short loc_14001CE4B
0x14001ce44  mov     ebx, 0C000009Ah
0x14001ce49  jmp     short loc_14001CEBE
0x14001ce4b  mov     rdx, rbx
0x14001ce4e  mov     ecx, 4Ah ; 'J'
0x14001ce53  mov     r8d, 54416D50h
0x14001ce59  call    cs:__imp_ExAllocatePool2
0x14001ce60  nop     dword ptr [rax+rax+00h]
0x14001ce65  mov     rdi, rax
0x14001ce68  test    rax, rax
0x14001ce6b  jz      short loc_14001CE44
0x14001ce6d  movups  xmm0, xmmword ptr [rbp+0]
0x14001ce71  lea     r8d, [rbx-18h]; Size
0x14001ce75  xor     edx, edx; Val
0x14001ce77  movsd   xmm1, qword ptr [rbp+10h]
0x14001ce7c  lea     rcx, [rax+18h]; void *
0x14001ce80  movups  xmmword ptr [rax], xmm0
0x14001ce83  movsd   qword ptr [rax+10h], xmm1
0x14001ce88  call    memset
0x14001ce8d  mov     rcx, [rsi+8]; DeviceObject
0x14001ce91  lea     rax, [rsp+48h+arg_8]
0x14001ce96  mov     r9d, ebx; Length
0x14001ce99  mov     [rsp+48h+var_28], rax; PLARGE_INTEGER
0x14001ce9e  mov     r8, rdi; Buffer
0x14001cea1  mov     edx, 4; MajorFunction
0x14001cea6  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x14001ceab  xor     edx, edx; Tag
0x14001cead  mov     rcx, rdi; P
0x14001ceb0  mov     ebx, eax
0x14001ceb2  call    cs:__imp_ExFreePoolWithTag
0x14001ceb9  nop     dword ptr [rax+rax+00h]
0x14001cebe  mov     eax, ebx
0x14001cec0  mov     rbx, [rsp+48h+arg_0]
0x14001cec5  add     rsp, 30h
0x14001cec9  pop     rdi
0x14001ceca  pop     rsi
0x14001cecb  pop     rbp
0x14001cecc  retn
```
