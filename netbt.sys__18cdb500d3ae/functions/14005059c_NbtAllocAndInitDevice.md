# NbtAllocAndInitDevice

- ea: `0x14005059c`
- end: `0x1400507c7`
- name: `NbtAllocAndInitDevice`
- size: `555`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001aa0c`
- `0x140053828`

## callees

- `0x140031440`
- `0x140042a08`
- `0x14005059c`
- `0x1400507d0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140050724`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140050754`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140050724`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140050754`
- `ntoskrnl!KeInitializeEvent` at `0x1400506b4`
- `ntoskrnl!KeInitializeEvent` at `0x14005076c`
- `ntoskrnl!KeInitializeEvent` at `0x140050784`
- `ntoskrnl!KeInitializeEvent` at `0x1400506b4`
- `ntoskrnl!KeInitializeEvent` at `0x14005076c`
- `ntoskrnl!KeInitializeEvent` at `0x140050784`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400506d8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400506d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400507b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400507b9`
- `ntoskrnl!ExAllocatePool2` at `0x1400505e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400505e4`

## pseudocode

```c
__int64 __fastcall NbtAllocAndInitDevice(
        PCUNICODE_STRING SourceString,
        UNICODE_STRING *a2,
        PDEVICE_OBJECT *a3,
        LONG a4)
{
  __int64 MaximumLength; // rdx
  ULONG v9; // edx
  ULONG v10; // r9d
  struct _KDPC *Pool2; // r14
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  unsigned int v17; // esi
  PDEVICE_OBJECT v18; // rdi
  ULONG v19; // [rsp+20h] [rbp-58h]
  BOOLEAN v20; // [rsp+28h] [rbp-50h]
  const UNICODE_STRING *v21; // [rsp+30h] [rbp-48h]
  const GUID *v22; // [rsp+38h] [rbp-40h]
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp+8h] BYREF

  *a3 = 0;
  MaximumLength = SourceString->MaximumLength;
  DeviceObject = 0;
  Pool2 = (struct _KDPC *)ExAllocatePool2(64, a2->MaximumLength + MaximumLength, 2004116046);
  if ( !Pool2 )
    return 3221225626LL;
  v13 = WdmlibIoCreateDeviceSecure((PDRIVER_OBJECT)DriverObject, v9, a2, v10, v19, v20, v21, v22, &DeviceObject);
  v17 = v13;
  if ( v13 < 0 )
  {
    if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      WPP_SF_DZ(v15, v14, v16, v13, (__int64)a2);
    ExFreePoolWithTag(Pool2, 0);
  }
  else
  {
    v18 = DeviceObject;
    *a3 = DeviceObject;
    memset(&v18[1].DriverObject, 0, 0x328u);
    v18[1].NextDevice = (PDEVICE_OBJECT)((char *)v18 + 344);
    v18[1].DriverObject = (struct _DRIVER_OBJECT *)&v18[1].DriverObject;
    v18[1].Vpb = (PVPB)&v18[1].Flags;
    *(_QWORD *)&v18[1].Flags = (char *)v18 + 384;
    *(_QWORD *)&v18[1].DeviceType = (char *)v18 + 400;
    v18[1].DeviceExtension = &v18[1].DeviceExtension;
    v18[1].Queue.ListEntry.Blink = &v18[1].Queue.ListEntry;
    v18[1].Queue.ListEntry.Flink = &v18[1].Queue.ListEntry;
    v18[1].Timer = (PIO_TIMER)&v18[1].CurrentIrp;
    v18[1].CurrentIrp = (struct _IRP *)&v18[1].CurrentIrp;
    v18[2].DeviceLock.Header.LockNV = 0;
    KeInitializeEvent((PRKEVENT)&v18[2].DeviceLock.Header.WaitListHead, NotificationEvent, 0);
    LODWORD(v18[1].AttachedDevice) = 1131832644;
    v18[1].ReferenceCount = a4;
    KeInitializeSpinLock((PKSPIN_LOCK)&v18[2].DeviceQueue.DeviceListHead.Blink);
    ++HIDWORD(v18[3].Queue.Wcb.DeviceObject);
    HIDWORD(v18[1].AttachedDevice) = 1;
    v18[3].DeviceType = 1;
    HIDWORD(v18[2].AttachedDevice) = -1;
    WORD1(v18[1].Queue.Wcb.CurrentIrp) = a2->MaximumLength;
    v18[1].Queue.Wcb.BufferChainingDpc = Pool2;
    RtlCopyUnicodeString((PUNICODE_STRING)&v18[1].Queue.Wcb.CurrentIrp, a2);
    HIWORD(v18[1].Queue.Wcb.NumberOfMapRegisters) = SourceString->MaximumLength;
    v18[1].Queue.Wcb.DeviceObject = (char *)Pool2 + a2->MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)&v18[1].Queue.Wcb.NumberOfMapRegisters, SourceString);
    KeInitializeEvent((PRKEVENT)&v18[2], NotificationEvent, 0);
    KeInitializeEvent((PRKEVENT)&v18[3].Flags, NotificationEvent, 0);
    BYTE4(v18[2].Dpc.DeferredContext) = 0;
  }
  return v17;
}

```

## disassembly

```asm
0x14005059c  mov     rax, rsp
0x14005059f  mov     [rax+10h], rbx
0x1400505a3  mov     [rax+18h], rbp
0x1400505a7  push    rsi
0x1400505a8  push    rdi
0x1400505a9  push    r12
0x1400505ab  push    r14
0x1400505ad  push    r15
0x1400505af  sub     rsp, 50h
0x1400505b3  mov     rbp, rdx
0x1400505b6  mov     qword ptr [r8], 0
0x1400505bd  movzx   edx, word ptr [rcx+2]
0x1400505c1  mov     rbx, r8
0x1400505c4  mov     qword ptr [rax+8], 0
0x1400505cc  mov     r15, rcx
0x1400505cf  mov     ecx, 40h ; '@'
0x1400505d4  mov     r8d, 7774624Eh
0x1400505da  movzx   eax, word ptr [rbp+2]
0x1400505de  mov     r12d, r9d
0x1400505e1  add     rdx, rax
0x1400505e4  call    cs:__imp_ExAllocatePool2
0x1400505eb  nop     dword ptr [rax+rax+00h]
0x1400505f0  mov     r14, rax
0x1400505f3  test    rax, rax
0x1400505f6  jnz     short loc_140050617
0x1400505f8  mov     eax, 0C000009Ah
0x1400505fd  lea     r11, [rsp+78h+var_28]
0x140050602  mov     rbx, [r11+38h]
0x140050606  mov     rbp, [r11+40h]
0x14005060a  mov     rsp, r11
0x14005060d  pop     r15
0x14005060f  pop     r14
0x140050611  pop     r12
0x140050613  pop     rdi
0x140050614  pop     rsi
0x140050615  retn
0x140050617  mov     rcx, cs:DriverObject; DriverObject
0x14005061e  lea     rax, [rsp+78h+arg_0]
0x140050626  mov     r8, rbp; DeviceName
0x140050629  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x14005062e  call    WdmlibIoCreateDeviceSecure
0x140050633  mov     esi, eax
0x140050635  test    eax, eax
0x140050637  js      loc_14005079E
0x14005063d  mov     rdi, [rsp+78h+arg_0]
0x140050645  xor     edx, edx; Val
0x140050647  mov     [rbx], rdi
0x14005064a  mov     r8d, 328h; Size
0x140050650  lea     rbx, [rdi+158h]
0x140050657  mov     rcx, rbx; void *
0x14005065a  call    memset
0x14005065f  mov     [rbx+8], rbx
0x140050663  lea     rax, [rdi+180h]
0x14005066a  mov     [rbx], rbx
0x14005066d  lea     rcx, [rdi+3C0h]; Event
0x140050674  mov     [rax+8], rax
0x140050678  xor     r8d, r8d; State
0x14005067b  mov     [rax], rax
0x14005067e  xor     edx, edx; Type
0x140050680  lea     rax, [rdi+190h]
0x140050687  mov     [rax+8], rax
0x14005068b  mov     [rax], rax
0x14005068e  lea     rax, [rdi+1A0h]
0x140050695  mov     [rax+8], rax
0x140050699  mov     [rax], rax
0x14005069c  lea     rax, [rdi+170h]
0x1400506a3  mov     [rax+8], rax
0x1400506a7  mov     [rax], rax
0x1400506aa  mov     dword ptr [rdi+3B8h], 0
0x1400506b4  call    cs:__imp_KeInitializeEvent
0x1400506bb  nop     dword ptr [rax+rax+00h]
0x1400506c0  lea     rcx, [rdi+350h]; SpinLock
0x1400506c7  mov     dword ptr [rdi+168h], 43766544h
0x1400506d1  mov     [rdi+154h], r12d
0x1400506d8  call    cs:__imp_KeInitializeSpinLock
0x1400506df  nop     dword ptr [rax+rax+00h]
0x1400506e4  inc     dword ptr [rdi+474h]
0x1400506ea  lea     rcx, [rdi+1D8h]; DestinationString
0x1400506f1  mov     dword ptr [rdi+16Ch], 1
0x1400506fb  mov     rdx, rbp; SourceString
0x1400506fe  mov     dword ptr [rdi+438h], 1
0x140050708  mov     dword ptr [rdi+2BCh], 0FFFFFFFFh
0x140050712  movzx   eax, word ptr [rbp+2]
0x140050716  mov     [rdi+1DAh], ax
0x14005071d  mov     [rdi+1E0h], r14
0x140050724  call    cs:__imp_RtlCopyUnicodeString
0x14005072b  nop     dword ptr [rax+rax+00h]
0x140050730  movzx   eax, word ptr [r15+2]
0x140050735  lea     rcx, [rdi+1C8h]; DestinationString
0x14005073c  mov     [rdi+1CAh], ax
0x140050743  mov     rdx, r15; SourceString
0x140050746  movzx   eax, word ptr [rbp+2]
0x14005074a  add     rax, r14
0x14005074d  mov     [rdi+1D0h], rax
0x140050754  call    cs:__imp_RtlCopyUnicodeString
0x14005075b  nop     dword ptr [rax+rax+00h]
0x140050760  lea     rcx, [rdi+2A0h]; Event
0x140050767  xor     r8d, r8d; State
0x14005076a  xor     edx, edx; Type
0x14005076c  call    cs:__imp_KeInitializeEvent
0x140050773  nop     dword ptr [rax+rax+00h]
0x140050778  lea     rcx, [rdi+420h]; Event
0x14005077f  xor     r8d, r8d; State
0x140050782  xor     edx, edx; Type
0x140050784  call    cs:__imp_KeInitializeEvent
0x14005078b  nop     dword ptr [rax+rax+00h]
0x140050790  mov     byte ptr [rdi+38Ch], 0
0x140050797  mov     eax, esi
0x140050799  jmp     loc_1400505FD
0x14005079e  test    byte ptr cs:xmmword_140038420+3, 1
0x1400507a5  jz      short loc_1400507B4
0x1400507a7  mov     r9d, esi
0x1400507aa  mov     [rsp+78h+var_58], rbp
0x1400507af  call    WPP_SF_DZ
0x1400507b4  xor     edx, edx; Tag
0x1400507b6  mov     rcx, r14; P
0x1400507b9  call    cs:__imp_ExFreePoolWithTag
0x1400507c0  nop     dword ptr [rax+rax+00h]
0x1400507c5  jmp     short loc_140050797
```
