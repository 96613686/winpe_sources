# PmPower(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400049f0`
- end: `0x140004b20`
- name: `?PmPower@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `304`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400049f0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140004b0d`
- `ntoskrnl!IofCompleteRequest` at `0x140004b0d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140004a28`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140004a28`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004a83`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004a83`
- `ntoskrnl!PoCallDriver` at `0x140004a66`
- `ntoskrnl!PoCallDriver` at `0x140004a66`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140004a47`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140004af9`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140004a47`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140004af9`

## pseudocode

```c
__int64 __fastcall PmPower(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  char v5; // di
  int v6; // esi
  unsigned int v7; // ebx
  struct _IO_STACK_LOCATION *v9; // rax
  struct _IO_STACK_LOCATION *v10; // rax

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = 1;
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), 0, File, 1u, 0x20u);
  if ( v6 < 0 )
  {
    PoStartNextPowerIrp(a2);
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 0);
    return (unsigned int)v6;
  }
  else
  {
    if ( CurrentStackLocation->MinorFunction == 2 && CurrentStackLocation->Parameters.Create.Options == 1 )
    {
      v9 = a2->Tail.Overlay.CurrentStackLocation;
      v5 = 0;
      *(_OWORD *)&v9[-1].MajorFunction = *(_OWORD *)&v9->MajorFunction;
      *(_OWORD *)&v9[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v9->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v9[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v9->Parameters.SetQuota + 6);
      v9[-1].FileObject = v9->FileObject;
      v9[-1].Control = 0;
      v10 = a2->Tail.Overlay.CurrentStackLocation;
      v10[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)PmPowerCompletion;
      v10[-1].Context = 0;
      v10[-1].Control = -32;
    }
    else
    {
      PoStartNextPowerIrp(a2);
      ++a2->CurrentLocation;
      ++a2->Tail.Overlay.CurrentStackLocation;
    }
    v7 = PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
    if ( v5 )
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), 0, 0x20u);
    return v7;
  }
}

```

## disassembly

```asm
0x1400049f0  push    rbx
0x1400049f2  push    rbp
0x1400049f3  push    rsi
0x1400049f4  push    rdi
0x1400049f5  push    r14
0x1400049f7  push    r15
0x1400049f9  sub     rsp, 38h
0x1400049fd  mov     r15, [rcx+40h]
0x140004a01  lea     r8, File; File
0x140004a08  mov     rbp, [rdx+0B8h]
0x140004a0f  mov     rbx, rdx
0x140004a12  mov     edi, 1
0x140004a17  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x140004a1f  mov     r9d, edi; Line
0x140004a22  xor     edx, edx; Tag
0x140004a24  lea     rcx, [r15+78h]; RemoveLock
0x140004a28  call    cs:__imp_IoAcquireRemoveLockEx
0x140004a2f  nop     dword ptr [rax+rax+00h]
0x140004a34  mov     esi, eax
0x140004a36  test    eax, eax
0x140004a38  js      loc_140004AF6
0x140004a3e  cmp     byte ptr [rbp+1], 2
0x140004a42  jz      short loc_140004A9F
0x140004a44  mov     rcx, rbx; Irp
0x140004a47  call    cs:__imp_PoStartNextPowerIrp
0x140004a4e  nop     dword ptr [rax+rax+00h]
0x140004a53  add     [rbx+43h], dil
0x140004a57  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140004a5f  mov     rcx, [r15+10h]; DeviceObject
0x140004a63  mov     rdx, rbx; Irp
0x140004a66  call    cs:__imp_PoCallDriver
0x140004a6d  nop     dword ptr [rax+rax+00h]
0x140004a72  mov     ebx, eax
0x140004a74  test    dil, dil
0x140004a77  jz      short loc_140004A8F
0x140004a79  xor     edx, edx; Tag
0x140004a7b  lea     rcx, [r15+78h]; RemoveLock
0x140004a7f  lea     r8d, [rdx+20h]; RemlockSize
0x140004a83  call    cs:__imp_IoReleaseRemoveLockEx
0x140004a8a  nop     dword ptr [rax+rax+00h]
0x140004a8f  mov     eax, ebx
0x140004a91  add     rsp, 38h
0x140004a95  pop     r15
0x140004a97  pop     r14
0x140004a99  pop     rdi
0x140004a9a  pop     rsi
0x140004a9b  pop     rbp
0x140004a9c  pop     rbx
0x140004a9d  retn
0x140004a9f  cmp     [rbp+10h], edi
0x140004aa2  jnz     short loc_140004A44
0x140004aa4  mov     rax, [rbx+0B8h]
0x140004aab  lea     rcx, ?PmPowerCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PmPowerCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x140004ab2  xor     dil, dil
0x140004ab5  movups  xmm0, xmmword ptr [rax]
0x140004ab8  movups  xmmword ptr [rax-48h], xmm0
0x140004abc  movups  xmm1, xmmword ptr [rax+10h]
0x140004ac0  movups  xmmword ptr [rax-38h], xmm1
0x140004ac4  movups  xmm0, xmmword ptr [rax+20h]
0x140004ac8  movups  xmmword ptr [rax-28h], xmm0
0x140004acc  movsd   xmm1, qword ptr [rax+30h]
0x140004ad1  movsd   qword ptr [rax-18h], xmm1
0x140004ad6  mov     byte ptr [rax-45h], 0
0x140004ada  mov     rax, [rbx+0B8h]
0x140004ae1  mov     [rax-10h], rcx
0x140004ae5  mov     qword ptr [rax-8], 0
0x140004aed  mov     byte ptr [rax-45h], 0E0h
0x140004af1  jmp     loc_140004A5F
0x140004af6  mov     rcx, rbx; Irp
0x140004af9  call    cs:__imp_PoStartNextPowerIrp
0x140004b00  nop     dword ptr [rax+rax+00h]
0x140004b05  xor     edx, edx; PriorityBoost
0x140004b07  mov     [rbx+30h], esi
0x140004b0a  mov     rcx, rbx; Irp
0x140004b0d  call    cs:__imp_IofCompleteRequest
0x140004b14  nop     dword ptr [rax+rax+00h]
0x140004b19  mov     eax, esi
0x140004b1b  jmp     loc_140004A91
```
