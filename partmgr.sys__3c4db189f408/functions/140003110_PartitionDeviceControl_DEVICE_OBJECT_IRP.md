# PartitionDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140003110`
- end: `0x140003427`
- name: `?PartitionDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `791`
- prototype: `int __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400030a0`
- `0x140003110`
- `0x140003430`
- `0x140006840`
- `0x14000aee0`
- `0x14001c008`
- `0x14001ca0c`
- `0x14001d25c`
- `0x14001d370`
- `0x14001d538`
- `0x14001d604`
- `0x140022df0`
- `0x140023ecc`
- `0x14002470c`
- `0x140024b3c`
- `0x140024d04`
- `0x14002532c`
- `0x1400257f8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400031ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400031ad`
- `ntoskrnl!IofCallDriver` at `0x14000319c`
- `ntoskrnl!IofCallDriver` at `0x14000319c`
- `ntoskrnl!IofCompleteRequest` at `0x140003218`
- `ntoskrnl!IofCompleteRequest` at `0x140003218`

## pseudocode

```c
int __fastcall PartitionDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int LowPart; // eax
  struct _DEVICE_OBJECT *v6; // rdi
  NTSTATUS v7; // ebx
  NTSTATUS DeviceNumber; // eax
  NTSTATUS v9; // edi
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax

  a2->IoStatus.Information = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  switch ( LowPart )
  {
    case 0x560030u:
      goto LABEL_8;
    case 0x2D1400u:
      return PartitionIoctlQueryProperty(a1, a2);
    case 0x2D9404u:
      return PartitionIoctlDsm(a1, a2);
  }
  if ( LowPart > 0x2D0C14 )
  {
    if ( LowPart <= 0x2DD498 )
    {
      if ( LowPart != 3003544 )
      {
        if ( LowPart > 0x2D4800 )
        {
          v29 = LowPart - 2967556;
          if ( !v29 )
            goto LABEL_8;
          v30 = v29 - 4;
          if ( !v30 )
            goto LABEL_8;
          v31 = v30 - 33808;
          if ( !v31 )
            goto LABEL_8;
          if ( v31 != 2172 )
            return PartitionPassThrough(a1, a2);
        }
        else
        {
          if ( LowPart == 2967552 )
            goto LABEL_8;
          v10 = LowPart - 2953344;
          if ( !v10 )
          {
            DeviceNumber = PartitionIoctlGetDeviceNumber(a1, a2);
            goto LABEL_17;
          }
          v12 = v10 - 4;
          if ( !v12 )
          {
            DeviceNumber = PartitionIoctlGetDeviceNumberEx(a1, a2);
            goto LABEL_17;
          }
          v27 = v12 - 1032;
          if ( v27 )
          {
            v28 = v27 - 16;
            if ( v28 )
            {
              if ( v28 != 431 )
                return PartitionPassThrough(a1, a2);
              goto LABEL_8;
            }
          }
        }
      }
    }
    else
    {
      if ( LowPart > 0x4DC010 )
      {
        v33 = LowPart - 5095444;
        if ( !v33 )
          goto LABEL_8;
        v34 = v33 - 589812;
        if ( v34 )
        {
          v35 = v34 - 92;
          if ( v35 )
          {
            if ( v35 != 999351 )
              return PartitionPassThrough(a1, a2);
            goto LABEL_8;
          }
        }
        else
        {
          v9 = 0;
          if ( !a2->RequestorMode )
            goto LABEL_18;
        }
        DeviceNumber = PartitionIoctlVolumePostOnline(a1, (struct _IRP *)CurrentStackLocation);
        goto LABEL_17;
      }
      if ( LowPart == 5095440 )
        goto LABEL_8;
      v16 = LowPart - 3003552;
      if ( v16 )
      {
        v17 = v16 - 8;
        if ( v17 )
        {
          v32 = v17 - 2042728;
          if ( v32 && v32 != 4 )
            return PartitionPassThrough(a1, a2);
          goto LABEL_8;
        }
      }
    }
    return PartitionIoctlBandmgmt(a1, a2);
  }
  if ( LowPart == 2952212 )
    goto LABEL_8;
  if ( LowPart <= 0x74004 )
  {
    if ( LowPart == 475140 )
    {
      DeviceNumber = PartitionIoctlGetPartitionInfo(a1, a2);
      goto LABEL_17;
    }
    if ( LowPart > 0x70048 )
    {
      v13 = LowPart - 458832;
      if ( v13 )
      {
        v14 = v13 - 80;
        if ( v14 )
        {
          v15 = v14 - 72;
          if ( !v15 )
          {
            DeviceNumber = PartitionIoctlGetPartitionAttributes(a1, a2);
            goto LABEL_17;
          }
          if ( v15 != 2840 )
            return PartitionPassThrough(a1, a2);
        }
      }
    }
    else
    {
      if ( LowPart == 458824 )
      {
        DeviceNumber = PartitionIoctlGetPartitionInfoEx(a1, a2);
LABEL_17:
        v9 = DeviceNumber;
LABEL_18:
        a2->IoStatus.Status = v9;
        IofCompleteRequest(a2, 0);
        return v9;
      }
      v18 = LowPart - 266264;
      if ( v18 )
      {
        v19 = v18 - 8;
        if ( v19 )
        {
          v20 = v19 - 192480;
          if ( v20 )
          {
            v21 = v20 - 20;
            if ( !v21 )
              return PartitionIoctlVerify(a1, a2);
            if ( v21 != 16 )
              return PartitionPassThrough(a1, a2);
          }
        }
      }
    }
LABEL_8:
    ++a2->CurrentLocation;
    a2->Tail.Overlay.CurrentStackLocation = CurrentStackLocation + 1;
    v6 = PartitionReferenceParent((struct _PARTITION_EXTENSION *)a1->DeviceExtension);
    v7 = IofCallDriver(v6, a2);
    ObfDereferenceObject(v6);
    return v7;
  }
  if ( LowPart > 0x7480C )
  {
    v24 = LowPart - 507912;
    if ( !v24 )
    {
      DeviceNumber = PartitionIoctlSetPartitionInfo(a1, a2);
      goto LABEL_17;
    }
    v25 = v24 - 68;
    if ( !v25 )
    {
      DeviceNumber = PartitionIoctlSetPartitionInfoEx(a1, a2);
      goto LABEL_17;
    }
    v26 = v25 - 160;
    if ( !v26 )
    {
      DeviceNumber = PartitionIoctlSetPartitionAttributes(a1, a2);
      goto LABEL_17;
    }
    if ( v26 == 2443220 )
      return PartitionIoctlManageBypassIo(a1, a2);
    return PartitionPassThrough(a1, a2);
  }
  if ( LowPart == 477196 )
    goto LABEL_8;
  v11 = LowPart - 475228;
  if ( !v11 )
  {
    DeviceNumber = PartitionIoctlGetLengthInfo(a1, a2);
    goto LABEL_17;
  }
  v22 = v11 - 1956;
  if ( !v22 )
    goto LABEL_8;
  v23 = v22 - 4;
  if ( !v23 || v23 == 4 )
    goto LABEL_8;
  return PartitionPassThrough(a1, a2);
}

```

## disassembly

```asm
0x140003110  mov     [rsp+arg_0], rbx
0x140003115  push    rdi
0x140003116  sub     rsp, 20h
0x14000311a  mov     qword ptr [rdx+38h], 0
0x140003122  mov     rbx, rdx
0x140003125  mov     rdx, [rdx+0B8h]; struct _IRP *
0x14000312c  mov     eax, [rdx+18h]
0x14000312f  cmp     eax, 560030h
0x140003134  jz      short loc_14000317C
0x140003136  cmp     eax, 2D1400h
0x14000313b  jz      loc_1400031C7
0x140003141  cmp     eax, 2D9404h
0x140003146  jnz     loc_1400031DB
0x14000314c  mov     rdx, rbx; struct _IRP *
0x14000314f  call    ?PartitionIoctlDsm@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlDsm(_DEVICE_OBJECT *,_IRP *)
0x140003154  mov     rbx, [rsp+28h+arg_0]
0x140003159  add     rsp, 20h
0x14000315d  pop     rdi
0x14000315e  retn
0x140003160  cmp     eax, 2DD498h
0x140003165  jbe     loc_140003232
0x14000316b  cmp     eax, 4DC010h
0x140003170  ja      loc_1400033F8
0x140003176  jnz     loc_1400032BC
0x14000317c  inc     byte ptr [rbx+43h]
0x14000317f  lea     rax, [rdx+48h]
0x140003183  mov     [rbx+0B8h], rax
0x14000318a  mov     rcx, [rcx+40h]; struct _PARTITION_EXTENSION *
0x14000318e  call    ?PartitionReferenceParent@@YAPEAU_DEVICE_OBJECT@@PEAU_PARTITION_EXTENSION@@@Z; PartitionReferenceParent(_PARTITION_EXTENSION *)
0x140003193  mov     rdx, rbx; Irp
0x140003196  mov     rcx, rax; DeviceObject
0x140003199  mov     rdi, rax
0x14000319c  call    cs:__imp_IofCallDriver
0x1400031a3  nop     dword ptr [rax+rax+00h]
0x1400031a8  mov     rcx, rdi; Object
0x1400031ab  mov     ebx, eax
0x1400031ad  call    cs:__imp_ObfDereferenceObject
0x1400031b4  nop     dword ptr [rax+rax+00h]
0x1400031b9  mov     eax, ebx
0x1400031bb  mov     rbx, [rsp+28h+arg_0]
0x1400031c0  add     rsp, 20h
0x1400031c4  pop     rdi
0x1400031c5  retn
0x1400031c7  mov     rdx, rbx; struct _IRP *
0x1400031ca  call    ?PartitionIoctlQueryProperty@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlQueryProperty(_DEVICE_OBJECT *,_IRP *)
0x1400031cf  mov     rbx, [rsp+28h+arg_0]
0x1400031d4  add     rsp, 20h
0x1400031d8  pop     rdi
0x1400031d9  retn
0x1400031db  cmp     eax, 2D0C14h
0x1400031e0  ja      loc_140003160
0x1400031e6  jz      short loc_14000317C
0x1400031e8  cmp     eax, 74004h
0x1400031ed  ja      short loc_14000325A
0x1400031ef  jz      loc_140003326
0x1400031f5  cmp     eax, 70048h
0x1400031fa  ja      loc_140003296
0x140003200  jnz     loc_1400032E0
0x140003206  mov     rdx, rbx; struct _IRP *
0x140003209  call    ?PartitionIoctlGetPartitionInfoEx@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlGetPartitionInfoEx(_DEVICE_OBJECT *,_IRP *)
0x14000320e  mov     edi, eax
0x140003210  xor     edx, edx; PriorityBoost
0x140003212  mov     [rbx+30h], edi
0x140003215  mov     rcx, rbx; Irp
0x140003218  call    cs:__imp_IofCompleteRequest
0x14000321f  nop     dword ptr [rax+rax+00h]
0x140003224  mov     eax, edi
0x140003226  mov     rbx, [rsp+28h+arg_0]
0x14000322b  add     rsp, 20h
0x14000322f  pop     rdi
0x140003230  retn
0x140003232  jz      loc_1400032CC
0x140003238  cmp     eax, 2D4800h
0x14000323d  ja      loc_1400033B0
0x140003243  jz      loc_14000317C
0x140003249  sub     eax, 2D1080h
0x14000324e  jnz     short loc_140003280
0x140003250  mov     rdx, rbx; struct _IRP *
0x140003253  call    ?PartitionIoctlGetDeviceNumber@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlGetDeviceNumber(_DEVICE_OBJECT *,_IRP *)
0x140003258  jmp     short loc_14000320E
0x14000325a  cmp     eax, 7480Ch
0x14000325f  ja      loc_140003355
0x140003265  jz      loc_14000317C
0x14000326b  sub     eax, 7405Ch
0x140003270  jnz     loc_140003333
0x140003276  mov     rdx, rbx; struct _IRP *
0x140003279  call    ?PartitionIoctlGetLengthInfo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlGetLengthInfo(_DEVICE_OBJECT *,_IRP *)
0x14000327e  jmp     short loc_14000320E
0x140003280  sub     eax, 4
0x140003283  jnz     loc_14000338C
0x140003289  mov     rdx, rbx; struct _IRP *
0x14000328c  call    ?PartitionIoctlGetDeviceNumberEx@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlGetDeviceNumberEx(_DEVICE_OBJECT *,_IRP *)
0x140003291  jmp     loc_14000320E
0x140003296  sub     eax, 70050h
0x14000329b  jz      loc_14000317C
0x1400032a1  sub     eax, 50h ; 'P'
0x1400032a4  jz      loc_14000317C
0x1400032aa  sub     eax, 48h ; 'H'
0x1400032ad  jnz     short loc_140003316
0x1400032af  mov     rdx, rbx; struct _IRP *
0x1400032b2  call    ?PartitionIoctlGetPartitionAttributes@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlGetPartitionAttributes(_DEVICE_OBJECT *,_IRP *)
0x1400032b7  jmp     loc_14000320E
0x1400032bc  sub     eax, 2DD4A0h
0x1400032c1  jz      short loc_1400032CC
0x1400032c3  sub     eax, 8
0x1400032c6  jnz     loc_1400033DF
0x1400032cc  mov     rdx, rbx; struct _IRP *
0x1400032cf  call    ?PartitionIoctlBandmgmt@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlBandmgmt(_DEVICE_OBJECT *,_IRP *)
0x1400032d4  mov     rbx, [rsp+28h+arg_0]
0x1400032d9  add     rsp, 20h
0x1400032dd  pop     rdi
0x1400032de  retn
0x1400032e0  sub     eax, 41018h
0x1400032e5  jz      loc_14000317C
0x1400032eb  sub     eax, 8
0x1400032ee  jz      loc_14000317C
0x1400032f4  sub     eax, 2EFE0h
0x1400032f9  jz      loc_14000317C
0x1400032ff  sub     eax, 14h
0x140003302  jz      loc_140011CAE
0x140003308  cmp     eax, 10h
0x14000330b  jz      loc_14000317C
0x140003311  jmp     loc_140011CE6
0x140003316  cmp     eax, 0B18h
0x14000331b  jz      loc_14000317C
0x140003321  jmp     loc_140011CE6
0x140003326  mov     rdx, rbx; struct _IRP *
0x140003329  call    ?PartitionIoctlGetPartitionInfo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlGetPartitionInfo(_DEVICE_OBJECT *,_IRP *)
0x14000332e  jmp     loc_14000320E
0x140003333  sub     eax, 7A4h
0x140003338  jz      loc_14000317C
0x14000333e  sub     eax, 4
0x140003341  jz      loc_14000317C
0x140003347  cmp     eax, 4
0x14000334a  jz      loc_14000317C
0x140003350  jmp     loc_140011CE6
0x140003355  sub     eax, 7C008h
0x14000335a  jz      loc_140011CD8
0x140003360  sub     eax, 44h ; 'D'
0x140003363  jz      loc_140011CCA
0x140003369  sub     eax, 0A0h
0x14000336e  jz      loc_140011CBC
0x140003374  cmp     eax, 2547D4h
0x140003379  jnz     loc_140011CE6
0x14000337f  mov     rdx, rbx; struct _IRP *
0x140003382  call    ?PartitionIoctlManageBypassIo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlManageBypassIo(_DEVICE_OBJECT *,_IRP *)
0x140003387  jmp     loc_1400031BB
0x14000338c  sub     eax, 408h
0x140003391  jz      loc_1400032CC
0x140003397  sub     eax, 10h
0x14000339a  jz      loc_1400032CC
0x1400033a0  cmp     eax, 1AFh
0x1400033a5  jz      loc_14000317C
0x1400033ab  jmp     loc_140011CE6
0x1400033b0  sub     eax, 2D4804h
0x1400033b5  jz      loc_14000317C
0x1400033bb  sub     eax, 4
0x1400033be  jz      loc_14000317C
0x1400033c4  sub     eax, 8410h
0x1400033c9  jz      loc_14000317C
0x1400033cf  cmp     eax, 87Ch
0x1400033d4  jz      loc_1400032CC
0x1400033da  jmp     loc_140011CE6
0x1400033df  sub     eax, 1F2B68h
0x1400033e4  jz      loc_14000317C
0x1400033ea  cmp     eax, 4
0x1400033ed  jz      loc_14000317C
0x1400033f3  jmp     loc_140011CE6
0x1400033f8  sub     eax, 4DC014h
0x1400033fd  jz      loc_14000317C
0x140003403  sub     eax, 8FFF4h
0x140003408  jz      loc_140011CF4
0x14000340e  sub     eax, 5Ch ; '\'
0x140003411  jz      loc_140011D00
0x140003417  cmp     eax, 0F3FB7h
0x14000341c  jz      loc_14000317C
0x140003422  jmp     loc_140011CE6
0x140011cae  mov     rdx, rbx; struct _IRP *
0x140011cb1  call    ?PartitionIoctlVerify@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlVerify(_DEVICE_OBJECT *,_IRP *)
0x140011cb6  nop
0x140011cb7  jmp     loc_1400031BB
0x140011cbc  mov     rdx, rbx; struct _IRP *
0x140011cbf  call    ?PartitionIoctlSetPartitionAttributes@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlSetPartitionAttributes(_DEVICE_OBJECT *,_IRP *)
0x140011cc4  nop
0x140011cc5  jmp     loc_14000320E
0x140011cca  mov     rdx, rbx; struct _IRP *
0x140011ccd  call    ?PartitionIoctlSetPartitionInfoEx@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlSetPartitionInfoEx(_DEVICE_OBJECT *,_IRP *)
0x140011cd2  nop
0x140011cd3  jmp     loc_14000320E
0x140011cd8  mov     rdx, rbx; struct _IRP *
0x140011cdb  call    ?PartitionIoctlSetPartitionInfo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlSetPartitionInfo(_DEVICE_OBJECT *,_IRP *)
0x140011ce0  nop
0x140011ce1  jmp     loc_14000320E
0x140011ce6  mov     rdx, rbx; struct _IRP *
0x140011ce9  call    ?PartitionPassThrough@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionPassThrough(_DEVICE_OBJECT *,_IRP *)
0x140011cee  nop
0x140011cef  jmp     loc_1400031BB
0x140011cf4  xor     edi, edi
0x140011cf6  cmp     [rbx+40h], dil
0x140011cfa  jz      loc_140003210
0x140011d00  call    ?PartitionIoctlVolumePostOnline@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIoctlVolumePostOnline(_DEVICE_OBJECT *,_IRP *)
0x140011d05  nop
0x140011d06  jmp     loc_14000320E
```
