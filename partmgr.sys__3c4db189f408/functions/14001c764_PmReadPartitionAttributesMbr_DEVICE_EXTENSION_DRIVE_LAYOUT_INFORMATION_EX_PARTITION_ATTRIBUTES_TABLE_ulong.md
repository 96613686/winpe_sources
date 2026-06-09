# PmReadPartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_PARTITION_ATTRIBUTES_TABLE * *,ulong *)

- ea: `0x14001c764`
- end: `0x14001c878`
- name: `?PmReadPartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_PARTITION_ATTRIBUTES_TABLE@@PEAK@Z`
- size: `276`
- prototype: `int(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _PARTITION_ATTRIBUTES_TABLE **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000a964`

## callees

- `0x14000eea8`
- `0x140011020`
- `0x140011440`
- `0x14001c764`
- `0x14001cf74`
- `0x140020240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c86a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c86a`
- `ntoskrnl!ExAllocatePool2` at `0x14001c7d2`
- `ntoskrnl!ExAllocatePool2` at `0x14001c7d2`

## pseudocode

```c
__int64 __fastcall PmReadPartitionAttributesMbr(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        GUID **a3,
        unsigned int *a4)
{
  int BytesPerSector; // edi
  size_t v9; // rsi
  unsigned __int8 IsRegionFree; // r12
  GUID *Pool2; // rbx
  size_t Size; // [rsp+78h] [rbp+10h] BYREF
  union _LARGE_INTEGER v14; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(Size) = 0;
  v14.QuadPart = 0;
  *a3 = 0;
  *a4 = 0;
  BytesPerSector = PmGetBytesPerSector(a1, (unsigned int *)&Size);
  if ( BytesPerSector >= 0 )
  {
    v9 = (unsigned int)Size;
    v14.QuadPart = (unsigned int)(2 * Size);
    IsRegionFree = SC_DISK_LAYOUT::IsRegionFree((SC_DISK_LAYOUT *)a2, v14.QuadPart, Size);
    Pool2 = (GUID *)ExAllocatePool2(74, (unsigned int)v9, 1413573968);
    if ( Pool2 )
    {
      if ( !IsRegionFree )
        goto LABEL_7;
      BytesPerSector = PmSendIO(*((PDEVICE_OBJECT *)a1 + 1), 3u, Pool2, v9, &v14);
      if ( BytesPerSector < 0 )
      {
        ExFreePoolWithTag(Pool2, 0);
        return (unsigned int)BytesPerSector;
      }
      if ( memcmp(Pool2, &PARTITION_BASIC_DATA_GUID, 0x10u) )
      {
LABEL_7:
        memset(Pool2, 0, v9);
        *Pool2 = PARTITION_BASIC_DATA_GUID;
      }
      *a3 = Pool2;
      *a4 = v9;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)BytesPerSector;
}

```

## disassembly

```asm
0x14001c764  mov     rax, rsp
0x14001c767  mov     [rax+8], rbx
0x14001c76b  push    rbp
0x14001c76c  push    rsi
0x14001c76d  push    rdi
0x14001c76e  push    r12
0x14001c770  push    r13
0x14001c772  push    r14
0x14001c774  push    r15
0x14001c776  sub     rsp, 30h
0x14001c77a  xor     esi, esi
0x14001c77c  mov     rbx, rdx
0x14001c77f  lea     rdx, [rax+10h]; unsigned int *
0x14001c783  mov     [rax+10h], esi
0x14001c786  mov     [rax+18h], rsi
0x14001c78a  mov     r14, r9
0x14001c78d  mov     [r8], rsi
0x14001c790  mov     r15, r8
0x14001c793  mov     [r9], esi
0x14001c796  mov     rbp, rcx
0x14001c799  call    ?PmGetBytesPerSector@@YAJPEAU_DEVICE_EXTENSION@@PEAK@Z; PmGetBytesPerSector(_DEVICE_EXTENSION *,ulong *)
0x14001c79e  mov     edi, eax
0x14001c7a0  test    eax, eax
0x14001c7a2  js      loc_14001C850
0x14001c7a8  mov     esi, dword ptr [rsp+68h+Size]
0x14001c7ac  mov     rcx, rbx; this
0x14001c7af  mov     r8d, esi; unsigned int
0x14001c7b2  lea     edx, [rsi+rsi]; unsigned __int64
0x14001c7b5  mov     qword ptr [rsp+68h+arg_10], rdx
0x14001c7bd  call    ?IsRegionFree@SC_DISK_LAYOUT@@QEAAE_KK@Z; SC_DISK_LAYOUT::IsRegionFree(unsigned __int64,ulong)
0x14001c7c2  mov     r8d, 54416D50h
0x14001c7c8  mov     edx, esi
0x14001c7ca  mov     ecx, 4Ah ; 'J'
0x14001c7cf  mov     r12b, al
0x14001c7d2  call    cs:__imp_ExAllocatePool2
0x14001c7d9  nop     dword ptr [rax+rax+00h]
0x14001c7de  mov     rbx, rax
0x14001c7e1  test    rax, rax
0x14001c7e4  jnz     short loc_14001C7ED
0x14001c7e6  mov     edi, 0C000009Ah
0x14001c7eb  jmp     short loc_14001C850
0x14001c7ed  test    r12b, r12b
0x14001c7f0  jz      short loc_14001C832
0x14001c7f2  mov     rcx, [rbp+8]; DeviceObject
0x14001c7f6  lea     rax, [rsp+68h+arg_10]
0x14001c7fe  mov     r9d, esi; Length
0x14001c801  mov     [rsp+68h+var_48], rax; PLARGE_INTEGER
0x14001c806  mov     r8, rbx; Buffer
0x14001c809  mov     edx, 3; MajorFunction
0x14001c80e  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x14001c813  mov     edi, eax
0x14001c815  mov     rcx, rbx; P
0x14001c818  test    eax, eax
0x14001c81a  js      short loc_14001C868
0x14001c81c  mov     r8d, 10h; Size
0x14001c822  lea     rdx, PARTITION_BASIC_DATA_GUID; Buf2
0x14001c829  call    memcmp
0x14001c82e  test    eax, eax
0x14001c830  jz      short loc_14001C84A
0x14001c832  mov     r8, rsi; Size
0x14001c835  xor     edx, edx; Val
0x14001c837  mov     rcx, rbx; void *
0x14001c83a  call    memset
0x14001c83f  movups  xmm0, xmmword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x14001c846  movdqu  xmmword ptr [rbx], xmm0
0x14001c84a  mov     [r15], rbx
0x14001c84d  mov     [r14], esi
0x14001c850  mov     rbx, [rsp+68h+arg_0]
0x14001c855  mov     eax, edi
0x14001c857  add     rsp, 30h
0x14001c85b  pop     r15
0x14001c85d  pop     r14
0x14001c85f  pop     r13
0x14001c861  pop     r12
0x14001c863  pop     rdi
0x14001c864  pop     rsi
0x14001c865  pop     rbp
0x14001c866  retn
0x14001c868  xor     edx, edx; Tag
0x14001c86a  call    cs:__imp_ExFreePoolWithTag
0x14001c871  nop     dword ptr [rax+rax+00h]
0x14001c876  jmp     short loc_14001C850
```
