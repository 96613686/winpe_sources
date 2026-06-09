# PmQueryBusRelations(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400071b8`
- end: `0x1400072c3`
- name: `?PmQueryBusRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `267`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022800`

## callees

- `0x1400071b8`
- `0x14000a014`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000723f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000723f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000728c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000728c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140007252`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140007252`
- `ntoskrnl!IofCompleteRequest` at `0x1400072a9`
- `ntoskrnl!IofCompleteRequest` at `0x1400072a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007217`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007217`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400071ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400071ce`

## pseudocode

```c
__int64 __fastcall PmQueryBusRelations(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rbx
  KIRQL v4; // al
  int v5; // r8d
  KIRQL v6; // r14
  NTSTATUS Status; // esi
  _DWORD *Information; // rbx
  __int64 v9; // r14
  __int64 i; // rbp
  _DWORD *v11; // rcx

  DeviceExtension = (char *)a1->DeviceExtension;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DeviceExtension + 14);
  v5 = *((_DWORD *)DeviceExtension + 129);
  v6 = v4;
  if ( (v5 & 2) == 0 )
  {
    v5 = *((_DWORD *)DeviceExtension + 129) | 0x100002;
    *((_DWORD *)DeviceExtension + 129) = v5;
  }
  Status = PmQueueNotificationWorkItem((struct _DEVICE_EXTENSION *)DeviceExtension, "PmQueryBusRelations", v5);
  KeReleaseSpinLock((PKSPIN_LOCK)DeviceExtension + 14, v6);
  if ( Status >= 0 )
  {
    KeWaitForSingleObject(DeviceExtension + 824, Executive, 0, 0, 0);
    IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
    Status = a2->IoStatus.Status;
    if ( Status >= 0 )
    {
      Information = (_DWORD *)a2->IoStatus.Information;
      if ( Information )
      {
        v9 = 0;
        for ( i = 0; (unsigned int)i < *Information; i = (unsigned int)(i + 1) )
        {
          v11 = *(_DWORD **)&Information[2 * i + 2];
          if ( v11[18] == 70 )
          {
            *(_QWORD *)&Information[2 * v9 + 2] = v11;
            v9 = (unsigned int)(v9 + 1);
          }
          else
          {
            ObfDereferenceObject(v11);
          }
        }
        *Information = v9;
      }
    }
  }
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400071b8  push    rbx
0x1400071ba  push    rbp
0x1400071bb  push    rsi
0x1400071bc  push    rdi
0x1400071bd  push    r14
0x1400071bf  sub     rsp, 30h
0x1400071c3  mov     rbx, [rcx+40h]
0x1400071c7  mov     rdi, rdx
0x1400071ca  lea     rcx, [rbx+70h]; SpinLock
0x1400071ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400071d5  nop     dword ptr [rax+rax+00h]
0x1400071da  mov     r8d, [rbx+204h]
0x1400071e1  mov     r14b, al
0x1400071e4  test    r8b, 2
0x1400071e8  jnz     short loc_1400071FF
0x1400071ea  mov     r8d, [rbx+204h]
0x1400071f1  or      r8d, 100002h
0x1400071f8  mov     [rbx+204h], r8d
0x1400071ff  lea     rdx, aPmquerybusrela; "PmQueryBusRelations"
0x140007206  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007209  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000720e  mov     dl, r14b; NewIrql
0x140007211  lea     rcx, [rbx+70h]; SpinLock
0x140007215  mov     esi, eax
0x140007217  call    cs:__imp_KeReleaseSpinLock
0x14000721e  nop     dword ptr [rax+rax+00h]
0x140007223  test    esi, esi
0x140007225  js      short loc_1400072A1
0x140007227  lea     rcx, [rbx+338h]; Object
0x14000722e  mov     [rsp+58h+Timeout], 0; Timeout
0x140007237  xor     r9d, r9d; Alertable
0x14000723a  xor     r8d, r8d; WaitMode
0x14000723d  xor     edx, edx; WaitReason
0x14000723f  call    cs:__imp_KeWaitForSingleObject
0x140007246  nop     dword ptr [rax+rax+00h]
0x14000724b  mov     rcx, [rbx+10h]; DeviceObject
0x14000724f  mov     rdx, rdi; Irp
0x140007252  call    cs:__imp_IoForwardIrpSynchronously
0x140007259  nop     dword ptr [rax+rax+00h]
0x14000725e  mov     esi, [rdi+30h]
0x140007261  test    esi, esi
0x140007263  js      short loc_1400072A1
0x140007265  mov     rbx, [rdi+38h]
0x140007269  test    rbx, rbx
0x14000726c  jz      short loc_1400072A1
0x14000726e  xor     r14d, r14d
0x140007271  xor     ebp, ebp
0x140007273  cmp     [rbx], ebp
0x140007275  jbe     short loc_14000729E
0x140007277  mov     rcx, [rbx+rbp*8+8]; Object
0x14000727c  cmp     dword ptr [rcx+48h], 46h ; 'F'
0x140007280  jnz     short loc_14000728C
0x140007282  mov     [rbx+r14*8+8], rcx
0x140007287  inc     r14d
0x14000728a  jmp     short loc_140007298
0x14000728c  call    cs:__imp_ObfDereferenceObject
0x140007293  nop     dword ptr [rax+rax+00h]
0x140007298  inc     ebp
0x14000729a  cmp     ebp, [rbx]
0x14000729c  jb      short loc_140007277
0x14000729e  mov     [rbx], r14d
0x1400072a1  xor     edx, edx; PriorityBoost
0x1400072a3  mov     [rdi+30h], esi
0x1400072a6  mov     rcx, rdi; Irp
0x1400072a9  call    cs:__imp_IofCompleteRequest
0x1400072b0  nop     dword ptr [rax+rax+00h]
0x1400072b5  mov     eax, esi
0x1400072b7  add     rsp, 30h
0x1400072bb  pop     r14
0x1400072bd  pop     rdi
0x1400072be  pop     rsi
0x1400072bf  pop     rbp
0x1400072c0  pop     rbx
0x1400072c1  retn
```
