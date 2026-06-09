# PmPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140022800`
- end: `0x140022981`
- name: `?PmPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400059c4`
- `0x140006280`
- `0x1400071b8`
- `0x1400072cc`
- `0x14000b904`
- `0x14000bda4`
- `0x140022800`
- `0x140022988`
- `0x14002579c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140022878`
- `ntoskrnl!IofCallDriver` at `0x140022878`
- `ntoskrnl!IofCompleteRequest` at `0x1400228c1`
- `ntoskrnl!IofCompleteRequest` at `0x1400228c1`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140022837`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140022837`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140022893`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140022893`

## pseudocode

```c
int __fastcall PmPnp(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  int v6; // eax
  int v7; // ebp
  ULONG Length; // eax
  IRP *v9; // rdx
  NTSTATUS RemovalRelations; // eax
  NTSTATUS v11; // edi
  int result; // eax

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), a2, File, 1u, 0x20u);
  v7 = v6;
  if ( v6 < 0 )
  {
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 0);
    return v7;
  }
  else if ( CurrentStackLocation->MinorFunction == 7 )
  {
    Length = CurrentStackLocation->Parameters.Read.Length;
    v9 = a2;
    if ( Length )
    {
      if ( Length == 3 )
      {
        RemovalRelations = PmQueryRemovalRelations(a1, a2);
      }
      else
      {
LABEL_5:
        ++a2->CurrentLocation;
        ++a2->Tail.Overlay.CurrentStackLocation;
        RemovalRelations = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), v9);
      }
    }
    else
    {
      RemovalRelations = PmQueryBusRelations(a1, a2);
    }
LABEL_6:
    v11 = RemovalRelations;
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), a2, 0x20u);
    return v11;
  }
  else
  {
    switch ( CurrentStackLocation->MinorFunction )
    {
      case 0u:
        return PmStartDevice(a1, a2);
      case 1u:
        RemovalRelations = PmQueryRemoveDevice(a1, a2);
        goto LABEL_6;
      case 2u:
        result = PmRemoveDevice(a1, a2);
        break;
      case 0x14u:
        RemovalRelations = PmQueryPnpDeviceState(a1, a2);
        goto LABEL_6;
      case 0x16u:
        RemovalRelations = PmDeviceUsageNotification(a1, a2);
        goto LABEL_6;
      case 0x17u:
        RemovalRelations = PmSurpriseRemoval(a1, a2);
        goto LABEL_6;
      default:
        v9 = a2;
        goto LABEL_5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140022800  push    rbx
0x140022802  push    rbp
0x140022803  push    rsi
0x140022804  push    rdi
0x140022805  push    r14
0x140022807  push    r15
0x140022809  sub     rsp, 38h
0x14002280d  mov     r14, [rcx+40h]
0x140022811  lea     r8, File; File
0x140022818  mov     rdi, [rdx+0B8h]
0x14002281f  mov     r15, rcx
0x140022822  mov     r9d, 1; Line
0x140022828  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x140022830  mov     rbx, rdx
0x140022833  lea     rcx, [r14+78h]; RemoveLock
0x140022837  call    cs:__imp_IoAcquireRemoveLockEx
0x14002283e  nop     dword ptr [rax+rax+00h]
0x140022843  mov     ebp, eax
0x140022845  test    eax, eax
0x140022847  js      short loc_1400228B9
0x140022849  movzx   eax, byte ptr [rdi+1]
0x14002284d  cmp     eax, 7
0x140022850  jnz     short loc_1400228AF
0x140022852  mov     eax, [rdi+8]
0x140022855  mov     rdx, rbx; struct _IRP *
0x140022858  test    eax, eax
0x14002285a  jz      loc_140022974
0x140022860  cmp     eax, 3
0x140022863  jz      loc_140022967
0x140022869  inc     byte ptr [rbx+43h]
0x14002286c  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140022874  mov     rcx, [r14+10h]; DeviceObject
0x140022878  call    cs:__imp_IofCallDriver
0x14002287f  nop     dword ptr [rax+rax+00h]
0x140022884  mov     r8d, 20h ; ' '; RemlockSize
0x14002288a  lea     rcx, [r14+78h]; RemoveLock
0x14002288e  mov     rdx, rbx; Tag
0x140022891  mov     edi, eax
0x140022893  call    cs:__imp_IoReleaseRemoveLockEx
0x14002289a  nop     dword ptr [rax+rax+00h]
0x14002289f  mov     eax, edi
0x1400228a1  add     rsp, 38h
0x1400228a5  pop     r15
0x1400228a7  pop     r14
0x1400228a9  pop     rdi
0x1400228aa  pop     rsi
0x1400228ab  pop     rbp
0x1400228ac  pop     rbx
0x1400228ad  retn
0x1400228af  cmp     eax, 17h; switch 24 cases
0x1400228b2  jbe     short loc_1400228DD
0x1400228b4  mov     rdx, rbx; jumptable 00000001400228F6 default case, cases 3-19,21
0x1400228b7  jmp     short loc_140022869
0x1400228b9  xor     edx, edx; PriorityBoost
0x1400228bb  mov     [rbx+30h], ebp
0x1400228be  mov     rcx, rbx; Irp
0x1400228c1  call    cs:__imp_IofCompleteRequest
0x1400228c8  nop     dword ptr [rax+rax+00h]
0x1400228cd  mov     eax, ebp
0x1400228cf  add     rsp, 38h
0x1400228d3  pop     r15
0x1400228d5  pop     r14
0x1400228d7  pop     rdi
0x1400228d8  pop     rsi
0x1400228d9  pop     rbp
0x1400228da  pop     rbx
0x1400228db  retn
0x1400228dd  lea     rdx, cs:140000000h
0x1400228e4  movzx   eax, ds:(byte_14001481C - 140000000h)[rdx+rax]
0x1400228ec  mov     ecx, ds:(jpt_1400228F6 - 140000000h)[rdx+rax*4]
0x1400228f3  add     rcx, rdx
0x1400228f6  jmp     rcx; switch jump
0x1400228fc  mov     rdx, rbx; jumptable 00000001400228F6 case 2
0x1400228ff  mov     rcx, r15; struct _DEVICE_OBJECT *
0x140022902  call    ?PmRemoveDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmRemoveDevice(_DEVICE_OBJECT *,_IRP *)
0x140022907  add     rsp, 38h
0x14002290b  pop     r15
0x14002290d  pop     r14
0x14002290f  pop     rdi
0x140022910  pop     rsi
0x140022911  pop     rbp
0x140022912  pop     rbx
0x140022913  retn
0x140022915  mov     rdx, rbx; jumptable 00000001400228F6 case 0
0x140022918  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14002291b  call    ?PmStartDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmStartDevice(_DEVICE_OBJECT *,_IRP *)
0x140022920  mov     edi, eax
0x140022922  jmp     loc_14002289F
0x140022927  mov     rdx, rbx; jumptable 00000001400228F6 case 23
0x14002292a  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14002292d  call    ?PmSurpriseRemoval@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmSurpriseRemoval(_DEVICE_OBJECT *,_IRP *)
0x140022932  jmp     loc_140022884
0x140022937  mov     rdx, rbx; jumptable 00000001400228F6 case 22
0x14002293a  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14002293d  call    ?PmDeviceUsageNotification@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmDeviceUsageNotification(_DEVICE_OBJECT *,_IRP *)
0x140022942  jmp     loc_140022884
0x140022947  mov     rdx, rbx; jumptable 00000001400228F6 case 20
0x14002294a  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14002294d  call    ?PmQueryPnpDeviceState@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmQueryPnpDeviceState(_DEVICE_OBJECT *,_IRP *)
0x140022952  jmp     loc_140022884
0x140022957  mov     rdx, rbx; jumptable 00000001400228F6 case 1
0x14002295a  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14002295d  call    ?PmQueryRemoveDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmQueryRemoveDevice(_DEVICE_OBJECT *,_IRP *)
0x140022962  jmp     loc_140022884
0x140022967  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14002296a  call    ?PmQueryRemovalRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmQueryRemovalRelations(_DEVICE_OBJECT *,_IRP *)
0x14002296f  jmp     loc_140022884
0x140022974  mov     rcx, r15; struct _DEVICE_OBJECT *
0x140022977  call    ?PmQueryBusRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmQueryBusRelations(_DEVICE_OBJECT *,_IRP *)
0x14002297c  jmp     loc_140022884
```
