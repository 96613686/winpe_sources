# KsCompletePendingRequest

- ea: `0x180013760`
- end: `0x180013872`
- name: `KsCompletePendingRequest`
- size: `274`
- prototype: `void __stdcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006f5d0`

## callees

- `0x18000b7bc`
- `0x1800134a4`
- `0x180013760`
- `0x180019c60`
- `0x1800427ec`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800137e8`
- `ntoskrnl!KeGetCurrentIrql` at `0x180013802`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800137e8`
- `ntoskrnl!KeGetCurrentIrql` at `0x180013802`
- `ntoskrnl!IofCompleteRequest` at `0x1800137c8`
- `ntoskrnl!IofCompleteRequest` at `0x1800137c8`

## pseudocode

```c
void __stdcall KsCompletePendingRequest(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  PVOID FsContext; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        179,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction )
  {
    if ( CurrentStackLocation->MajorFunction != 2 )
    {
LABEL_6:
      IofCompleteRequest(Irp, 0);
      return;
    }
  }
  else if ( Irp->IoStatus.Status >= 0 )
  {
    if ( !CurrentStackLocation->FileObject->RelatedFileObject )
      goto LABEL_6;
    if ( !KeGetCurrentIrql() )
    {
      KspCompletePendedPinCreate(Irp);
      return;
    }
    goto LABEL_15;
  }
  if ( KeGetCurrentIrql() )
  {
LABEL_15:
    CKsDevice::QueuePendedCreateClose(
      (CKsDevice *)(*(_QWORD *)(*(_QWORD *)CurrentStackLocation->DeviceObject->DeviceExtension + 360LL) - 200LL),
      Irp);
    return;
  }
  FsContext = CurrentStackLocation->FileObject->FsContext;
  if ( !FsContext )
  {
    Irp->IoStatus.Status = -1073741811;
    goto LABEL_6;
  }
  (*(void (__fastcall **)(PDEVICE_OBJECT, PIRP))(**(_QWORD **)FsContext + 32LL))(
    CurrentStackLocation->DeviceObject,
    Irp);
}

```

## disassembly

```asm
0x180013760  mov     [rsp+arg_0], rbx
0x180013765  mov     [rsp+arg_8], rsi
0x18001376a  push    rdi
0x18001376b  sub     rsp, 30h
0x18001376f  mov     rbx, rcx
0x180013772  lea     rax, WPP_RECORDER_INITIALIZED
0x180013779  xor     esi, esi
0x18001377b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180013782  jz      short loc_1800137B2
0x180013784  mov     rcx, cs:WPP_GLOBAL_Control
0x18001378b  cmp     [rcx+48h], si
0x18001378f  jz      short loc_1800137B2
0x180013791  mov     rcx, [rcx+40h]
0x180013795  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18001379c  mov     r9d, 0B3h
0x1800137a2  mov     [rsp+38h+var_18], rax
0x1800137a7  lea     r8d, [rsi+1]
0x1800137ab  mov     dl, 5
0x1800137ad  call    WPP_RECORDER_SF_
0x1800137b2  mov     rdi, [rbx+0B8h]
0x1800137b9  mov     al, [rdi]
0x1800137bb  test    al, al
0x1800137bd  jz      short loc_1800137D9
0x1800137bf  cmp     al, 2
0x1800137c1  jz      short loc_180013802
0x1800137c3  xor     edx, edx; PriorityBoost
0x1800137c5  mov     rcx, rbx; Irp
0x1800137c8  call    cs:__imp_IofCompleteRequest
0x1800137cf  nop     dword ptr [rax+rax+00h]
0x1800137d4  jmp     loc_180013861
0x1800137d9  cmp     [rbx+30h], esi
0x1800137dc  jl      short loc_180013802
0x1800137de  mov     rax, [rdi+30h]
0x1800137e2  cmp     [rax+40h], rsi
0x1800137e6  jz      short loc_1800137C3
0x1800137e8  call    cs:__imp_KeGetCurrentIrql
0x1800137ef  nop     dword ptr [rax+rax+00h]
0x1800137f4  test    al, al
0x1800137f6  jnz     short loc_180013840
0x1800137f8  mov     rcx, rbx; struct _IRP *
0x1800137fb  call    KspCompletePendedPinCreate
0x180013800  jmp     short loc_180013861
0x180013802  call    cs:__imp_KeGetCurrentIrql
0x180013809  nop     dword ptr [rax+rax+00h]
0x18001380e  test    al, al
0x180013810  jnz     short loc_180013840
0x180013812  mov     rax, [rdi+30h]
0x180013816  mov     rax, [rax+18h]
0x18001381a  test    rax, rax
0x18001381d  jnz     short loc_180013828
0x18001381f  mov     dword ptr [rbx+30h], 0C000000Dh
0x180013826  jmp     short loc_1800137C3
0x180013828  mov     rax, [rax]
0x18001382b  mov     rcx, [rdi+28h]
0x18001382f  mov     rdx, [rax]
0x180013832  mov     rax, [rdx+20h]
0x180013836  mov     rdx, rbx
0x180013839  call    _guard_dispatch_icall
0x18001383e  jmp     short loc_180013861
0x180013840  mov     rax, [rdi+28h]
0x180013844  mov     rdx, rbx; struct _IRP *
0x180013847  mov     rcx, [rax+40h]
0x18001384b  mov     rax, [rcx]
0x18001384e  mov     rcx, [rax+168h]
0x180013855  sub     rcx, 0C8h; this
0x18001385c  call    ?QueuePendedCreateClose@CKsDevice@@QEAAXPEAU_IRP@@@Z; CKsDevice::QueuePendedCreateClose(_IRP *)
0x180013861  mov     rbx, [rsp+38h+arg_0]
0x180013866  mov     rsi, [rsp+38h+arg_8]
0x18001386b  add     rsp, 30h
0x18001386f  pop     rdi
0x180013870  retn
```
