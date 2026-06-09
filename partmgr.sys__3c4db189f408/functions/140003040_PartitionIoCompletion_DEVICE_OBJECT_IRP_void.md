# PartitionIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140003040`
- end: `0x140003098`
- name: `?PartitionIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `88`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003040`
- `0x14000ae88`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140003066`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140003066`

## pseudocode

```c
__int64 __fastcall PartitionIoCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  PVOID DeviceExtension; // r8
  __int64 v5; // rdx

  DeviceExtension = a1->DeviceExtension;
  if ( a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  if ( a2->IoStatus.Status < 0 && (ScReadNoFence((unsigned int *)DeviceExtension + 10) & 0x80u) != 0 )
  {
    *(_DWORD *)(v5 + 48) = -1073741810;
    *(_QWORD *)(v5 + 56) = 0;
  }
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 50));
  return 0;
}

```

## disassembly

```asm
0x140003040  sub     rsp, 28h
0x140003044  cmp     byte ptr [rdx+41h], 0
0x140003048  mov     r8, [rcx+40h]
0x14000304c  jz      short loc_140003059
0x14000304e  mov     rax, [rdx+0B8h]
0x140003055  or      byte ptr [rax+3], 1
0x140003059  cmp     dword ptr [rdx+30h], 0
0x14000305d  jl      short loc_14000307A
0x14000305f  mov     rcx, [r8+190h]; RunRefCacheAware
0x140003066  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14000306d  nop     dword ptr [rax+rax+00h]
0x140003072  xor     eax, eax
0x140003074  add     rsp, 28h
0x140003078  retn
0x14000307a  lea     rcx, [r8+28h]; unsigned int *
0x14000307e  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x140003083  test    al, al
0x140003085  jns     short loc_14000305F
0x140003087  mov     dword ptr [rdx+30h], 0C000000Eh
0x14000308e  mov     qword ptr [rdx+38h], 0
0x140003096  jmp     short loc_14000305F
```
