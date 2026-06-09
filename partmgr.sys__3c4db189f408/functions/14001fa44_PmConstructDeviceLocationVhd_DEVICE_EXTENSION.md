# PmConstructDeviceLocationVhd(_DEVICE_EXTENSION *)

- ea: `0x14001fa44`
- end: `0x14001faf2`
- name: `?PmConstructDeviceLocationVhd@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002366c`

## callees

- `0x14001fa44`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001faad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001faad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fabb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fad3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fad3`
- `ntoskrnl!ExAllocatePool2` at `0x14001fa62`
- `ntoskrnl!ExAllocatePool2` at `0x14001fa62`

## pseudocode

```c
__int64 __fastcall PmConstructDeviceLocationVhd(struct _DEVICE_EXTENSION *a1)
{
  ULONG i; // esi
  WCHAR *Pool2; // rax
  WCHAR *v4; // rbx
  NTSTATUS v5; // eax
  unsigned int v6; // edi

  for ( i = 64; ; i += 64 )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(66, i, 1112108368);
    v4 = Pool2;
    if ( !Pool2 )
      break;
    v5 = PmSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 2), 0x2D5928u, 0, 0, Pool2, i, 0);
    v6 = v5;
    if ( v5 >= 0 )
    {
      RtlInitUnicodeString((PUNICODE_STRING)a1 + 28, v4);
      return v6;
    }
    if ( v5 != -1073741789 )
    {
      ExFreePoolWithTag(v4, 0);
      return v6;
    }
    ExFreePoolWithTag(v4, 0);
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x14001fa44  push    rbx
0x14001fa46  push    rbp
0x14001fa47  push    rsi
0x14001fa48  push    rdi
0x14001fa49  sub     rsp, 48h
0x14001fa4d  mov     rbp, rcx
0x14001fa50  mov     esi, 40h ; '@'
0x14001fa55  mov     edx, esi
0x14001fa57  mov     ecx, 42h ; 'B'
0x14001fa5c  mov     r8d, 42496D50h
0x14001fa62  call    cs:__imp_ExAllocatePool2
0x14001fa69  nop     dword ptr [rax+rax+00h]
0x14001fa6e  mov     rbx, rax
0x14001fa71  test    rax, rax
0x14001fa74  jz      short loc_14001FAE1
0x14001fa76  mov     rcx, [rbp+10h]; DeviceObject
0x14001fa7a  xor     r9d, r9d; InputBufferLength
0x14001fa7d  mov     [rsp+68h+var_38], 0; BOOLEAN
0x14001fa82  xor     r8d, r8d; InputBuffer
0x14001fa85  mov     [rsp+68h+var_40], esi; ULONG
0x14001fa89  mov     edx, 2D5928h; IoControlCode
0x14001fa8e  mov     [rsp+68h+var_48], rax; PVOID
0x14001fa93  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14001fa98  mov     edi, eax
0x14001fa9a  test    eax, eax
0x14001fa9c  jns     short loc_14001FAC9
0x14001fa9e  xor     edx, edx; Tag
0x14001faa0  mov     rcx, rbx; P
0x14001faa3  cmp     eax, 0C0000023h
0x14001faa8  jnz     short loc_14001FABB
0x14001faaa  add     esi, 40h ; '@'
0x14001faad  call    cs:__imp_ExFreePoolWithTag
0x14001fab4  nop     dword ptr [rax+rax+00h]
0x14001fab9  jmp     short loc_14001FA55
0x14001fabb  call    cs:__imp_ExFreePoolWithTag
0x14001fac2  nop     dword ptr [rax+rax+00h]
0x14001fac7  jmp     short loc_14001FAE6
0x14001fac9  lea     rcx, [rbp+1C0h]; DestinationString
0x14001fad0  mov     rdx, rbx; SourceString
0x14001fad3  call    cs:__imp_RtlInitUnicodeString
0x14001fada  nop     dword ptr [rax+rax+00h]
0x14001fadf  jmp     short loc_14001FAE6
0x14001fae1  mov     edi, 0C000009Ah
0x14001fae6  mov     eax, edi
0x14001fae8  add     rsp, 48h
0x14001faec  pop     rdi
0x14001faed  pop     rsi
0x14001faee  pop     rbp
0x14001faef  pop     rbx
0x14001faf0  retn
```
