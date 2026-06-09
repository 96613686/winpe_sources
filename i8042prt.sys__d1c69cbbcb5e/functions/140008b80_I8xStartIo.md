# I8xStartIo

- ea: `0x140008b80`
- end: `0x140008d70`
- name: `I8xStartIo`
- size: `496`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Tag)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x140008b80`
- `0x140009840`
- `0x140009b28`

## import_xrefs

- `ntoskrnl!IoAllocateController` at `0x140008d1e`
- `ntoskrnl!IoAllocateController` at `0x140008d1e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140008c92`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140008c92`
- `ntoskrnl!IofCompleteRequest` at `0x140008cc9`
- `ntoskrnl!IofCompleteRequest` at `0x140008cc9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140008ca9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140008ca9`
- `ntoskrnl!IoStartNextPacket` at `0x140008cda`
- `ntoskrnl!IoStartNextPacket` at `0x140008cda`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008cf3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008cf3`

## pseudocode

```c
void __fastcall I8xStartIo(PDEVICE_OBJECT DeviceObject, PVOID Tag)
{
  __int64 v4; // rsi
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  char *DeviceExtension; // rbx
  int v10; // edx
  int v11; // edx
  KIRQL Irql; // [rsp+58h] [rbp+10h] BYREF

  Irql = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Tag,
      11,
      61,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  v4 = *((_QWORD *)Tag + 23);
  v5 = *(_DWORD *)(v4 + 24);
  if ( v5 != 999423 && (v6 = v5 - 720900) != 0 && (v7 = v6 - 4) != 0 && (v8 = v7 - 16319) != 0 && v8 != 0x40000 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Tag,
        13,
        62,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    DeviceExtension = (char *)DeviceObject->DeviceExtension;
    v10 = -1073414131;
    if ( !DeviceExtension[565] )
      v10 = -1073414093;
    I8xLogError((_DWORD)DeviceObject, v10, 0, -1073741808, 0, 0);
    TraceLoggingInvalidStartIoRequest(*(unsigned int *)(v4 + 24));
    IoAcquireCancelSpinLock(&Irql);
    _InterlockedExchange64((volatile __int64 *)Tag + 13, 0);
    IoReleaseCancelSpinLock(Irql);
    *((_QWORD *)Tag + 7) = 0;
    *((_DWORD *)Tag + 12) = -1073741808;
    IofCompleteRequest((PIRP)Tag, 0);
    IoStartNextPacket(DeviceObject, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 40), Tag, 0x20u);
  }
  else
  {
    IoAllocateController(
      *(PCONTROLLER_OBJECT *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL),
      DeviceObject,
      I8xControllerRoutine,
      0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      11,
      63,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
}

```

## disassembly

```asm
0x140008b80  push    r12
0x140008b82  sub     rsp, 40h
0x140008b86  mov     [rsp+48h+arg_10], rbp
0x140008b8b  mov     rbp, rcx
0x140008b8e  mov     [rsp+48h+arg_18], rsi
0x140008b93  mov     [rsp+48h+var_10], rdi
0x140008b98  mov     rdi, rdx
0x140008b9b  mov     [rsp+48h+var_18], r15
0x140008ba0  mov     [rsp+48h+Irql], 0
0x140008ba5  lea     r15, WPP_RECORDER_INITIALIZED
0x140008bac  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008bb3  lea     r12, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x140008bba  jz      short loc_140008BDD
0x140008bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bc3  mov     r9d, 3Dh ; '='
0x140008bc9  mov     r8d, 0Bh
0x140008bcf  mov     [rsp+48h+var_28], r12
0x140008bd4  mov     rcx, [rcx+40h]
0x140008bd8  call    WPP_RECORDER_SF_
0x140008bdd  mov     rsi, [rdi+0B8h]
0x140008be4  mov     eax, [rsi+18h]
0x140008be7  cmp     eax, 0F3FFFh
0x140008bec  jz      loc_140008D06
0x140008bf2  sub     eax, 0B0004h
0x140008bf7  jz      loc_140008D06
0x140008bfd  sub     eax, 4
0x140008c00  jz      loc_140008D06
0x140008c06  sub     eax, 3FBFh
0x140008c0b  jz      loc_140008D06
0x140008c11  cmp     eax, 40000h
0x140008c16  jz      loc_140008D06
0x140008c1c  mov     [rsp+48h+arg_0], rbx
0x140008c21  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008c28  jz      short loc_140008C4B
0x140008c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c31  mov     r9d, 3Eh ; '>'
0x140008c37  mov     r8d, 0Dh
0x140008c3d  mov     [rsp+48h+var_28], r12
0x140008c42  mov     rcx, [rcx+40h]
0x140008c46  call    WPP_RECORDER_SF_
0x140008c4b  mov     rbx, [rbp+40h]
0x140008c4f  mov     edx, 0C005000Dh
0x140008c54  mov     eax, 0C0050033h
0x140008c59  mov     [rsp+48h+var_20], 0
0x140008c61  mov     r9d, 0C0000010h
0x140008c67  mov     [rsp+48h+var_28], 0
0x140008c70  mov     rcx, rbp
0x140008c73  cmp     byte ptr [rbx+235h], 0
0x140008c7a  cmovz   edx, eax
0x140008c7d  xor     r8d, r8d
0x140008c80  call    I8xLogError
0x140008c85  mov     ecx, [rsi+18h]
0x140008c88  call    TraceLoggingInvalidStartIoRequest
0x140008c8d  lea     rcx, [rsp+48h+Irql]; Irql
0x140008c92  call    cs:__imp_IoAcquireCancelSpinLock
0x140008c99  nop     dword ptr [rax+rax+00h]
0x140008c9e  xor     eax, eax
0x140008ca0  xchg    rax, [rdi+68h]
0x140008ca4  movzx   ecx, [rsp+48h+Irql]; Irql
0x140008ca9  call    cs:__imp_IoReleaseCancelSpinLock
0x140008cb0  nop     dword ptr [rax+rax+00h]
0x140008cb5  xor     edx, edx; PriorityBoost
0x140008cb7  mov     qword ptr [rdi+38h], 0
0x140008cbf  mov     rcx, rdi; Irp
0x140008cc2  mov     dword ptr [rdi+30h], 0C0000010h
0x140008cc9  call    cs:__imp_IofCompleteRequest
0x140008cd0  nop     dword ptr [rax+rax+00h]
0x140008cd5  xor     edx, edx; Cancelable
0x140008cd7  mov     rcx, rbp; DeviceObject
0x140008cda  call    cs:__imp_IoStartNextPacket
0x140008ce1  nop     dword ptr [rax+rax+00h]
0x140008ce6  lea     rcx, [rbx+28h]; RemoveLock
0x140008cea  mov     r8d, 20h ; ' '; RemlockSize
0x140008cf0  mov     rdx, rdi; Tag
0x140008cf3  call    cs:__imp_IoReleaseRemoveLockEx
0x140008cfa  nop     dword ptr [rax+rax+00h]
0x140008cff  mov     rbx, [rsp+48h+arg_0]
0x140008d04  jmp     short loc_140008D2A
0x140008d06  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140008d0d  lea     r8, I8xControllerRoutine; ExecutionRoutine
0x140008d14  xor     r9d, r9d; Context
0x140008d17  mov     rdx, rbp; DeviceObject
0x140008d1a  mov     rcx, [rcx+8]; ControllerObject
0x140008d1e  call    cs:__imp_IoAllocateController
0x140008d25  nop     dword ptr [rax+rax+00h]
0x140008d2a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008d31  mov     r15, [rsp+48h+var_18]
0x140008d36  mov     rdi, [rsp+48h+var_10]
0x140008d3b  mov     rsi, [rsp+48h+arg_18]
0x140008d40  mov     rbp, [rsp+48h+arg_10]
0x140008d45  jz      short loc_140008D68
0x140008d47  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d4e  mov     r9d, 3Fh ; '?'
0x140008d54  mov     r8d, 0Bh
0x140008d5a  mov     [rsp+48h+var_28], r12
0x140008d5f  mov     rcx, [rcx+40h]
0x140008d63  call    WPP_RECORDER_SF_
0x140008d68  add     rsp, 40h
0x140008d6c  pop     r12
0x140008d6e  retn
```
