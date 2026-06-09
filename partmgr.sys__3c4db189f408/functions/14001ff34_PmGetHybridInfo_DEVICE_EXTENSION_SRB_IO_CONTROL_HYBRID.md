# PmGetHybridInfo(_DEVICE_EXTENSION *,_SRB_IO_CONTROL_HYBRID * *)

- ea: `0x14001ff34`
- end: `0x140020048`
- name: `?PmGetHybridInfo@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_SRB_IO_CONTROL_HYBRID@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SRB_IO_CONTROL_HYBRID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400261fc`

## callees

- `0x14001ff34`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001fff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002000c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020024`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002000c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020024`
- `ntoskrnl!ExAllocatePool2` at `0x14001ff57`
- `ntoskrnl!ExAllocatePool2` at `0x14001ff57`

## pseudocode

```c
__int64 __fastcall PmGetHybridInfo(PDEVICE_OBJECT *a1, PVOID *a2)
{
  ULONG i; // esi
  char *Pool2; // rax
  void *v6; // rbx
  NTSTATUS v7; // eax
  unsigned int v8; // edi

  for ( i = 152; ; i *= 2 )
  {
    Pool2 = (char *)ExAllocatePool2(64, i, 1112108368);
    v6 = Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    *(_DWORD *)Pool2 = 28;
    *(_QWORD *)(Pool2 + 4) = 0x4B53494452425948LL;
    *((_DWORD *)Pool2 + 3) = 30;
    *((_DWORD *)Pool2 + 12) = i - 64;
    *((_DWORD *)Pool2 + 4) = 1771040;
    *((_DWORD *)Pool2 + 6) = i - 28;
    *((_DWORD *)Pool2 + 7) = 1;
    *((_DWORD *)Pool2 + 8) = 24;
    *((_DWORD *)Pool2 + 9) = 1;
    *((_DWORD *)Pool2 + 11) = 64;
    v7 = PmSendDeviceControl(a1[2], 0x4D008u, Pool2, i, Pool2, i, 0);
    v8 = v7;
    if ( v7 >= 0 )
      break;
    if ( v7 != -1073741789 && v7 != -2147483643 )
    {
      ExFreePoolWithTag(v6, 0);
      return v8;
    }
    ExFreePoolWithTag(v6, 0);
  }
  if ( *a2 )
    ExFreePoolWithTag(*a2, 0);
  *a2 = v6;
  return v8;
}

```

## disassembly

```asm
0x14001ff34  push    rbx
0x14001ff36  push    rbp
0x14001ff37  push    rsi
0x14001ff38  push    rdi
0x14001ff39  push    r14
0x14001ff3b  sub     rsp, 40h
0x14001ff3f  mov     r14, rdx
0x14001ff42  mov     rbp, rcx
0x14001ff45  mov     esi, 98h
0x14001ff4a  mov     edx, esi
0x14001ff4c  mov     ecx, 40h ; '@'
0x14001ff51  mov     r8d, 42496D50h
0x14001ff57  call    cs:__imp_ExAllocatePool2
0x14001ff5e  nop     dword ptr [rax+rax+00h]
0x14001ff63  mov     rbx, rax
0x14001ff66  test    rax, rax
0x14001ff69  jz      loc_140020035
0x14001ff6f  mov     rax, 4B53494452425948h
0x14001ff79  mov     dword ptr [rbx], 1Ch
0x14001ff7f  mov     [rbx+4], rax
0x14001ff83  lea     ecx, [rsi-1Ch]
0x14001ff86  lea     eax, [rsi-40h]
0x14001ff89  mov     dword ptr [rbx+0Ch], 1Eh
0x14001ff90  mov     [rbx+30h], eax
0x14001ff93  mov     r9d, esi; InputBufferLength
0x14001ff96  mov     dword ptr [rbx+10h], 1B0620h
0x14001ff9d  mov     r8, rbx; InputBuffer
0x14001ffa0  mov     [rbx+18h], ecx
0x14001ffa3  mov     edx, 4D008h; IoControlCode
0x14001ffa8  mov     dword ptr [rbx+1Ch], 1
0x14001ffaf  mov     dword ptr [rbx+20h], 18h
0x14001ffb6  mov     dword ptr [rbx+24h], 1
0x14001ffbd  mov     dword ptr [rbx+2Ch], 40h ; '@'
0x14001ffc4  mov     rcx, [rbp+10h]; DeviceObject
0x14001ffc8  mov     [rsp+68h+var_38], 0; BOOLEAN
0x14001ffcd  mov     [rsp+68h+var_40], esi; ULONG
0x14001ffd1  mov     [rsp+68h+var_48], rbx; PVOID
0x14001ffd6  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14001ffdb  mov     edi, eax
0x14001ffdd  test    eax, eax
0x14001ffdf  jns     short loc_14002001A
0x14001ffe1  cmp     eax, 0C0000023h
0x14001ffe6  jz      short loc_14001FFEF
0x14001ffe8  cmp     eax, 80000005h
0x14001ffed  jnz     short loc_140020007
0x14001ffef  add     esi, esi
0x14001fff1  xor     edx, edx; Tag
0x14001fff3  mov     rcx, rbx; P
0x14001fff6  call    cs:__imp_ExFreePoolWithTag
0x14001fffd  nop     dword ptr [rax+rax+00h]
0x140020002  jmp     loc_14001FF4A
0x140020007  xor     edx, edx; Tag
0x140020009  mov     rcx, rbx; P
0x14002000c  call    cs:__imp_ExFreePoolWithTag
0x140020013  nop     dword ptr [rax+rax+00h]
0x140020018  jmp     short loc_14002003A
0x14002001a  mov     rcx, [r14]; P
0x14002001d  test    rcx, rcx
0x140020020  jz      short loc_140020030
0x140020022  xor     edx, edx; Tag
0x140020024  call    cs:__imp_ExFreePoolWithTag
0x14002002b  nop     dword ptr [rax+rax+00h]
0x140020030  mov     [r14], rbx
0x140020033  jmp     short loc_14002003A
0x140020035  mov     edi, 0C000009Ah
0x14002003a  mov     eax, edi
0x14002003c  add     rsp, 40h
0x140020040  pop     r14
0x140020042  pop     rdi
0x140020043  pop     rsi
0x140020044  pop     rbp
0x140020045  pop     rbx
0x140020046  retn
```
