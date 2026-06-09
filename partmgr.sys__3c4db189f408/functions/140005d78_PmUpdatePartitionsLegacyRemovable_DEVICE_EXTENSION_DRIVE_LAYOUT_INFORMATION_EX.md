# PmUpdatePartitionsLegacyRemovable(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140005d78`
- end: `0x140006002`
- name: `?PmUpdatePartitionsLegacyRemovable@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x140005b2c`

## callees

- `0x140004e44`
- `0x140004ef8`
- `0x140005ab0`
- `0x140005d78`
- `0x140010f20`
- `0x140011440`
- `0x140023cb4`
- `0x1400254c8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005ec4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ec4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f9b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e89`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005edc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e89`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005edc`

## pseudocode

```c
__int64 __fastcall PmUpdatePartitionsLegacyRemovable(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  char v4; // r12
  DWORD v5; // edx
  __int64 v6; // rax
  __int64 v7; // rcx
  DWORD PartitionCount; // r10d
  int v9; // r9d
  PARTITION_INFORMATION_EX *v10; // rdi
  SC_PART_ENTRY *v11; // rcx
  unsigned int v12; // r10d
  char v13; // cl
  char *v14; // rsi
  unsigned int v15; // ebp
  int v16; // r15d
  KIRQL v17; // al
  __int64 v18; // rcx
  KIRQL v19; // dl
  char *v20; // rax
  KIRQL v21; // al
  __int64 v22; // rsi
  int v23; // ebx
  KIRQL NewIrql; // [rsp+40h] [rbp-E8h]
  struct _PARTITION_EXTENSION *v26; // [rsp+48h] [rbp-E0h] BYREF
  _DWORD v27[36]; // [rsp+50h] [rbp-D8h] BYREF

  v4 = 0;
  memset(v27, 0, sizeof(v27));
  v5 = 0;
  v26 = 0;
  if ( !a2->PartitionCount )
  {
    v9 = 0;
LABEL_10:
    v10 = (PARTITION_INFORMATION_EX *)v27;
    v27[0] = a2->PartitionStyle;
    v13 = 0;
    goto LABEL_11;
  }
  do
  {
    v6 = v5++;
    v7 = v6;
    a2->PartitionEntry[v7].PartitionNumber = 0;
    a2->PartitionEntry[v7].PartitionStyle = a2->PartitionStyle;
    PartitionCount = a2->PartitionCount;
  }
  while ( v5 < PartitionCount );
  v9 = 0;
  if ( !PartitionCount )
    goto LABEL_10;
  while ( 1 )
  {
    v10 = &a2->PartitionEntry[v9];
    if ( !SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)v10) && !SC_PART_ENTRY::IsContainer(v11) )
      break;
    if ( ++v9 >= v12 )
      goto LABEL_10;
  }
  v13 = 1;
LABEL_11:
  v14 = (char *)a1 + 896;
  v15 = v13 != 0 ? v9 : 0;
  if ( *(char **)v14 == v14 )
  {
    v10->PartitionNumber = 1;
    v16 = PmCreatePartition(a1, a2, v15, v10, &v26);
    if ( v16 >= 0 )
    {
      v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
      v18 = *(_QWORD *)v14;
      v19 = v17;
      if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
        __fastfail(3u);
      v20 = (char *)v26 + 144;
      *((_QWORD *)v26 + 18) = v18;
      *((_QWORD *)v20 + 1) = v14;
      *(_QWORD *)(v18 + 8) = v20;
      *(_QWORD *)v14 = v20;
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v19);
    }
    else
    {
      v10->PartitionNumber = 0;
    }
  }
  else
  {
    v16 = 0;
    v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    v22 = *(_QWORD *)v14;
    NewIrql = v21;
    *(_DWORD *)(v22 - 104) &= ~4u;
    v10->PartitionNumber = *(_DWORD *)(v22 + 48);
    if ( v10->StartingOffset.QuadPart != *(_QWORD *)(v22 + 32) || v10->PartitionLength.QuadPart != *(_QWORD *)(v22 + 40) )
    {
      v4 = 1;
      *(_DWORD *)(*(_QWORD *)(v22 - 136) + 48LL) |= 2u;
    }
    *(_DWORD *)(v22 + 16) = v15;
    v23 = *(_DWORD *)(v22 - 104);
    *(_DWORD *)(v22 - 104) = v23 | PmVerifyPropertyChange(v10, (struct _PARTITION_INFORMATION_EX *)(v22 + 24));
    *(_OWORD *)(v22 + 24) = *(_OWORD *)&v10->PartitionStyle;
    *(_OWORD *)(v22 + 40) = *(_OWORD *)&v10->PartitionLength.LowPart;
    *(_OWORD *)(v22 + 56) = *(_OWORD *)&v10->Mbr.PartitionType;
    *(GUID *)(v22 + 72) = v10->Gpt.PartitionId;
    *(_OWORD *)(v22 + 88) = *(_OWORD *)&v10->Gpt.Attributes;
    *(_OWORD *)(v22 + 104) = *(_OWORD *)&v10->Gpt.Name[4];
    *(_OWORD *)(v22 + 120) = *(_OWORD *)&v10->Gpt.Name[12];
    *(_OWORD *)(v22 + 136) = *(_OWORD *)&v10->Gpt.Name[20];
    *(_OWORD *)(v22 + 152) = *(_OWORD *)&v10->Gpt.Name[28];
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, NewIrql);
    if ( v4 )
      PmSendDeviceControl(*(PDEVICE_OBJECT *)(*(_QWORD *)(v22 - 120) + 16LL), 0x70407u, 0, 0, 0, 0, 0);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140005d78  mov     [rsp+arg_10], rbx
0x140005d7d  push    rbp
0x140005d7e  push    rsi
0x140005d7f  push    rdi
0x140005d80  push    r12
0x140005d82  push    r13
0x140005d84  push    r14
0x140005d86  push    r15
0x140005d88  sub     rsp, 0F0h
0x140005d8f  mov     rax, cs:__security_cookie
0x140005d96  xor     rax, rsp
0x140005d99  mov     [rsp+128h+var_48], rax
0x140005da1  mov     rbx, rdx
0x140005da4  mov     r14, rcx
0x140005da7  xor     r12d, r12d
0x140005daa  lea     rcx, [rsp+128h+var_D4]; void *
0x140005daf  xor     edx, edx; Val
0x140005db1  mov     [rsp+128h+var_D8], r12d
0x140005db6  mov     r8d, 8Ch; Size
0x140005dbc  call    memset
0x140005dc1  mov     edx, r12d
0x140005dc4  mov     [rsp+128h+var_E0], r12
0x140005dc9  cmp     [rbx+4], r12d
0x140005dcd  jbe     short loc_140005E2B
0x140005dcf  mov     eax, edx
0x140005dd1  inc     edx
0x140005dd3  lea     rcx, [rax+rax*8]
0x140005dd7  add     rcx, rcx
0x140005dda  mov     [rbx+rcx*8+48h], r12d
0x140005ddf  mov     eax, [rbx]
0x140005de1  mov     [rbx+rcx*8+30h], eax
0x140005de5  mov     r10d, [rbx+4]
0x140005de9  cmp     edx, r10d
0x140005dec  jb      short loc_140005DCF
0x140005dee  mov     r9d, r12d
0x140005df1  test    r10d, r10d
0x140005df4  jz      short loc_140005E2E
0x140005df6  mov     eax, r9d
0x140005df9  lea     rdi, [rax+rax*8]
0x140005dfd  shl     rdi, 4
0x140005e01  add     rdi, 30h ; '0'
0x140005e05  add     rdi, rbx
0x140005e08  mov     rcx, rdi; this
0x140005e0b  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x140005e10  test    al, al
0x140005e12  jnz     short loc_140005E1D
0x140005e14  call    ?IsContainer@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsContainer(void)
0x140005e19  test    al, al
0x140005e1b  jz      short loc_140005E27
0x140005e1d  inc     r9d
0x140005e20  cmp     r9d, r10d
0x140005e23  jb      short loc_140005DF6
0x140005e25  jmp     short loc_140005E2E
0x140005e27  mov     cl, 1
0x140005e29  jmp     short loc_140005E3C
0x140005e2b  mov     r9d, r12d
0x140005e2e  mov     eax, [rbx]
0x140005e30  lea     rdi, [rsp+128h+var_D8]
0x140005e35  mov     [rsp+128h+var_D8], eax
0x140005e39  mov     cl, r12b
0x140005e3c  neg     cl
0x140005e3e  lea     rsi, [r14+380h]
0x140005e45  sbb     ebp, ebp
0x140005e47  and     ebp, r9d
0x140005e4a  cmp     [rsi], rsi
0x140005e4d  jnz     loc_140005ED5
0x140005e53  lea     rax, [rsp+128h+var_E0]
0x140005e58  mov     dword ptr [rdi+18h], 1
0x140005e5f  mov     r9, rdi; struct _PARTITION_INFORMATION_EX *
0x140005e62  mov     [rsp+128h+var_108], rax; struct _PARTITION_EXTENSION **
0x140005e67  mov     r8d, ebp; unsigned int
0x140005e6a  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005e6d  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x140005e70  call    ?PmCreatePartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@KPEAU_PARTITION_INFORMATION_EX@@PEAPEAU_PARTITION_EXTENSION@@@Z; PmCreatePartition(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,ulong,_PARTITION_INFORMATION_EX *,_PARTITION_EXTENSION * *)
0x140005e75  mov     r15d, eax
0x140005e78  test    eax, eax
0x140005e7a  jns     short loc_140005E85
0x140005e7c  mov     [rdi+18h], r12d
0x140005e80  jmp     loc_140005FD3
0x140005e85  lea     rcx, [r14+70h]; SpinLock
0x140005e89  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005e90  nop     dword ptr [rax+rax+00h]
0x140005e95  mov     rcx, [rsi]
0x140005e98  mov     dl, al; NewIrql
0x140005e9a  cmp     [rcx+8], rsi
0x140005e9e  jz      short loc_140005EA7
0x140005ea0  mov     ecx, 3
0x140005ea5  int     29h; Win8: RtlFailFast(ecx)
0x140005ea7  mov     rax, [rsp+128h+var_E0]
0x140005eac  add     rax, 90h
0x140005eb2  mov     [rax], rcx
0x140005eb5  mov     [rax+8], rsi
0x140005eb9  mov     [rcx+8], rax
0x140005ebd  lea     rcx, [r14+70h]; SpinLock
0x140005ec1  mov     [rsi], rax
0x140005ec4  call    cs:__imp_KeReleaseSpinLock
0x140005ecb  nop     dword ptr [rax+rax+00h]
0x140005ed0  jmp     loc_140005FD3
0x140005ed5  lea     rcx, [r14+70h]; SpinLock
0x140005ed9  mov     r15d, r12d
0x140005edc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005ee3  nop     dword ptr [rax+rax+00h]
0x140005ee8  mov     rsi, [rsi]
0x140005eeb  mov     [rsp+128h+NewIrql], al
0x140005eef  mov     ecx, [rsi-68h]
0x140005ef2  and     ecx, 0FFFFFFFBh
0x140005ef5  mov     [rsi-68h], ecx
0x140005ef8  mov     ecx, [rsi+30h]
0x140005efb  mov     [rdi+18h], ecx
0x140005efe  mov     rcx, [rsi+20h]
0x140005f02  cmp     [rdi+8], rcx
0x140005f06  jnz     short loc_140005F12
0x140005f08  mov     rax, [rsi+28h]
0x140005f0c  cmp     [rdi+10h], rax
0x140005f10  jz      short loc_140005F2C
0x140005f12  mov     rax, [rsi-88h]
0x140005f19  mov     r12b, 1
0x140005f1c  mov     ecx, [rax+30h]
0x140005f1f  mov     rax, [rsi-88h]
0x140005f26  or      ecx, 2
0x140005f29  mov     [rax+30h], ecx
0x140005f2c  mov     [rsi+10h], ebp
0x140005f2f  lea     rdx, [rsi+18h]; struct _PARTITION_INFORMATION_EX *
0x140005f33  mov     ebx, [rsi-68h]
0x140005f36  mov     rcx, rdi; struct _PARTITION_INFORMATION_EX *
0x140005f39  call    ?PmVerifyPropertyChange@@YAKPEAU_PARTITION_INFORMATION_EX@@0@Z; PmVerifyPropertyChange(_PARTITION_INFORMATION_EX *,_PARTITION_INFORMATION_EX *)
0x140005f3e  mov     dl, [rsp+128h+NewIrql]; NewIrql
0x140005f42  lea     rcx, [r14+70h]; SpinLock
0x140005f46  or      eax, ebx
0x140005f48  mov     [rsi-68h], eax
0x140005f4b  movups  xmm0, xmmword ptr [rdi]
0x140005f4e  movups  xmmword ptr [rsi+18h], xmm0
0x140005f52  movups  xmm1, xmmword ptr [rdi+10h]
0x140005f56  movups  xmmword ptr [rsi+28h], xmm1
0x140005f5a  movups  xmm0, xmmword ptr [rdi+20h]
0x140005f5e  movups  xmmword ptr [rsi+38h], xmm0
0x140005f62  movups  xmm1, xmmword ptr [rdi+30h]
0x140005f66  movups  xmmword ptr [rsi+48h], xmm1
0x140005f6a  movups  xmm0, xmmword ptr [rdi+40h]
0x140005f6e  movups  xmmword ptr [rsi+58h], xmm0
0x140005f72  movups  xmm1, xmmword ptr [rdi+50h]
0x140005f76  movups  xmmword ptr [rsi+68h], xmm1
0x140005f7a  movups  xmm0, xmmword ptr [rdi+60h]
0x140005f7e  movups  xmmword ptr [rsi+78h], xmm0
0x140005f82  movups  xmm1, xmmword ptr [rdi+70h]
0x140005f86  movups  xmmword ptr [rsi+88h], xmm1
0x140005f8d  movups  xmm0, xmmword ptr [rdi+80h]
0x140005f94  movups  xmmword ptr [rsi+98h], xmm0
0x140005f9b  call    cs:__imp_KeReleaseSpinLock
0x140005fa2  nop     dword ptr [rax+rax+00h]
0x140005fa7  xor     eax, eax
0x140005fa9  test    r12b, r12b
0x140005fac  jz      short loc_140005FD3
0x140005fae  mov     rcx, [rsi-78h]
0x140005fb2  xor     r9d, r9d; InputBufferLength
0x140005fb5  mov     [rsp+128h+var_F8], al; BOOLEAN
0x140005fb9  xor     r8d, r8d; InputBuffer
0x140005fbc  mov     [rsp+128h+var_100], eax; ULONG
0x140005fc0  mov     edx, 70407h; IoControlCode
0x140005fc5  mov     [rsp+128h+var_108], rax; PVOID
0x140005fca  mov     rcx, [rcx+10h]; DeviceObject
0x140005fce  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140005fd3  mov     eax, r15d
0x140005fd6  mov     rcx, [rsp+128h+var_48]
0x140005fde  xor     rcx, rsp; StackCookie
0x140005fe1  call    __security_check_cookie
0x140005fe6  mov     rbx, [rsp+128h+arg_10]
0x140005fee  add     rsp, 0F0h
0x140005ff5  pop     r15
0x140005ff7  pop     r14
0x140005ff9  pop     r13
0x140005ffb  pop     r12
0x140005ffd  pop     rdi
0x140005ffe  pop     rsi
0x140005fff  pop     rbp
0x140006000  retn
```
