# FatFsdRead

- ea: `0x140006030`
- end: `0x14000627b`
- name: `FatFsdRead`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400023c0`
- `0x140005288`
- `0x140006030`
- `0x140023d4c`
- `0x140039550`
- `0x14003960c`
- `0x14004573c`
- `0x1400463f8`
- `0x140047d24`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140006113`
- `ntoskrnl!KeInitializeEvent` at `0x140006113`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006152`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006152`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006054`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006054`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000624b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000624b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000616b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006257`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000616b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006257`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140006193`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140006193`
- `ntoskrnl!IoGetStackLimits` at `0x1400060cf`
- `ntoskrnl!IoGetStackLimits` at `0x1400061e6`
- `ntoskrnl!IoGetStackLimits` at `0x1400060cf`
- `ntoskrnl!IoGetStackLimits` at `0x1400061e6`
- `ntoskrnl!FsRtlPostPagingFileStackOverflow` at `0x140006130`
- `ntoskrnl!FsRtlPostPagingFileStackOverflow` at `0x140006130`

## pseudocode

```c
__int64 __fastcall FatFsdRead(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  PDEVICE_OBJECT DeviceObject; // rdx
  __int64 FsContext; // rsi
  char IsIrpTopLevel; // r15
  BOOLEAN IsOperationSynchronous; // al
  unsigned __int8 *IrpContext; // rax
  unsigned __int8 *v10; // r14
  unsigned int v11; // eax
  unsigned int v12; // edi
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v14; // [rsp+48h] [rbp-50h] BYREF
  _QWORD Context[2]; // [rsp+50h] [rbp-48h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-38h] BYREF
  unsigned __int64 LowLimit; // [rsp+A8h] [rbp+10h] BYREF
  unsigned __int64 v18; // [rsp+B0h] [rbp+18h] BYREF

  LowLimit = (unsigned __int64)a2;
  KeEnterCriticalRegion();
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  if ( DeviceObject == (PDEVICE_OBJECT)qword_140017CC8
    || DeviceObject == (PDEVICE_OBJECT)qword_140017CD0
    || (FsContext = (__int64)CurrentStackLocation->FileObject->FsContext, *(_WORD *)FsContext != 1282)
    || (*(_DWORD *)(FsContext + 192) & 4) == 0 )
  {
    IsIrpTopLevel = FatIsIrpTopLevel(a2);
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
    IrpContext = (unsigned __int8 *)FatCreateIrpContext(a2, IsOperationSynchronous);
    v10 = IrpContext;
    if ( (IrpContext[65] & 4) != 0 )
    {
      v11 = FatCompleteMdl(IrpContext, a2);
    }
    else
    {
      v14 = 0;
      v18 = 0;
      IoGetStackLimits(&v18, &v14);
      if ( (unsigned __int64)&Context[-1] - v18 >= 0x1000 )
        v11 = FatCommonRead((__int64)v10, a2);
      else
        v11 = FatPostStackOverflowRead(v10, a2);
    }
    v12 = v11;
    if ( IsIrpTopLevel )
      IoSetTopLevelIrp(0);
    KeLeaveCriticalRegion();
    return v12;
  }
  else
  {
    CurrentStackLocation->Control |= 1u;
    HighLimit = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit >= 0x1000 )
    {
      FatPagingFileIo(a2, FsContext);
    }
    else
    {
      memset(&Event, 0, sizeof(Event));
      Context[0] = a2;
      Context[1] = FsContext;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      FsRtlPostPagingFileStackOverflow(Context, &Event, FatOverflowPagingFileRead);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
    KeLeaveCriticalRegion();
    return 259;
  }
}

```

## disassembly

```asm
0x140006030  mov     rax, rsp
0x140006033  mov     [rax+8], rsi
0x140006037  mov     [rax+10h], rdx
0x14000603b  push    rdi; int
0x14000603c  push    r14; int
0x14000603e  push    r15; int
0x140006040  sub     rsp, 80h
0x140006047  mov     rdi, rdx
0x14000604a  xor     esi, esi
0x14000604c  mov     [rax-60h], rsi
0x140006050  mov     [rax-68h], sil
0x140006054  call    cs:__imp_KeEnterCriticalRegion
0x14000605b  nop     dword ptr [rax+rax+00h]
0x140006060  mov     rcx, [rdi+0B8h]
0x140006067  mov     rdx, [rcx+28h]
0x14000606b  cmp     rdx, cs:qword_140017CC8
0x140006072  jz      loc_140006181
0x140006078  cmp     rdx, cs:qword_140017CD0
0x14000607f  jz      loc_140006181
0x140006085  mov     rax, [rcx+30h]
0x140006089  mov     rsi, [rax+18h]
0x14000608d  mov     eax, 502h
0x140006092  cmp     [rsi], ax
0x140006095  jnz     loc_140006181
0x14000609b  mov     eax, [rsi+0C0h]
0x1400060a1  test    al, 4
0x1400060a3  jz      loc_140006181
0x1400060a9  or      byte ptr [rcx+3], 1
0x1400060ad  mov     [rsp+98h+HighLimit], 0
0x1400060b6  mov     [rsp+98h+LowLimit], 0
0x1400060c2  lea     rdx, [rsp+98h+HighLimit]; HighLimit
0x1400060c7  lea     rcx, [rsp+98h+LowLimit]; LowLimit
0x1400060cf  call    cs:__imp_IoGetStackLimits
0x1400060d6  nop     dword ptr [rax+rax+00h]
0x1400060db  lea     rax, [rsp+98h+HighLimit]
0x1400060e0  sub     rax, [rsp+98h+LowLimit]
0x1400060e8  cmp     rax, 1000h
0x1400060ee  jnb     short loc_140006160
0x1400060f0  xorps   xmm0, xmm0
0x1400060f3  xor     eax, eax
0x1400060f5  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x1400060fa  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x1400060ff  mov     [rsp+98h+Context], rdi
0x140006104  mov     [rsp+98h+var_40], rsi
0x140006109  xor     r8d, r8d; State
0x14000610c  xor     edx, edx; Type
0x14000610e  lea     rcx, [rsp+98h+Event]; Event
0x140006113  call    cs:__imp_KeInitializeEvent
0x14000611a  nop     dword ptr [rax+rax+00h]
0x14000611f  lea     r8, FatOverflowPagingFileRead; StackOverflowRoutine
0x140006126  lea     rdx, [rsp+98h+Event]; Event
0x14000612b  lea     rcx, [rsp+98h+Context]; Context
0x140006130  call    cs:__imp_FsRtlPostPagingFileStackOverflow
0x140006137  nop     dword ptr [rax+rax+00h]
0x14000613c  mov     [rsp+98h+Timeout], 0; Timeout
0x140006145  xor     r9d, r9d; Alertable
0x140006148  xor     r8d, r8d; WaitMode
0x14000614b  xor     edx, edx; WaitReason
0x14000614d  lea     rcx, [rsp+98h+Event]; Object
0x140006152  call    cs:__imp_KeWaitForSingleObject
0x140006159  nop     dword ptr [rax+rax+00h]
0x14000615e  jmp     short loc_14000616B
0x140006160  mov     rdx, rsi
0x140006163  mov     rcx, rdi; Irp
0x140006166  call    FatPagingFileIo
0x14000616b  call    cs:__imp_KeLeaveCriticalRegion
0x140006172  nop     dword ptr [rax+rax+00h]
0x140006177  mov     eax, 103h
0x14000617c  jmp     loc_140006265
0x140006181  mov     rcx, rdi; Irp
0x140006184  call    FatIsIrpTopLevel
0x140006189  mov     r15b, al
0x14000618c  mov     byte ptr [rsp+98h+var_68], al; int
0x140006190  mov     rcx, rdi; Irp
0x140006193  call    cs:__imp_IoIsOperationSynchronous
0x14000619a  nop     dword ptr [rax+rax+00h]
0x14000619f  mov     dl, al
0x1400061a1  mov     rcx, rdi
0x1400061a4  call    FatCreateIrpContext
0x1400061a9  mov     r14, rax
0x1400061ac  mov     [rsp+98h+Entry], rax; int
0x1400061b1  test    byte ptr [rax+41h], 4
0x1400061b5  jz      short loc_1400061C4
0x1400061b7  mov     rdx, rdi; Irp
0x1400061ba  mov     rcx, rax; Entry
0x1400061bd  call    FatCompleteMdl
0x1400061c2  jmp     short loc_14000621C
0x1400061c4  mov     [rsp+98h+var_50], 0; int
0x1400061cd  mov     [rsp+98h+arg_10], 0; int
0x1400061d9  lea     rdx, [rsp+98h+var_50]; HighLimit
0x1400061de  lea     rcx, [rsp+98h+arg_10]; LowLimit
0x1400061e6  call    cs:__imp_IoGetStackLimits
0x1400061ed  nop     dword ptr [rax+rax+00h]
0x1400061f2  lea     rax, [rsp+98h+var_50]
0x1400061f7  sub     rax, [rsp+98h+arg_10]
0x1400061ff  mov     rdx, rdi; int
0x140006202  mov     rcx, r14; int
0x140006205  cmp     rax, 1000h
0x14000620b  jnb     short loc_140006217
0x14000620d  mov     r8, rsi
0x140006210  call    FatPostStackOverflowRead
0x140006215  jmp     short loc_14000621C
0x140006217  call    FatCommonRead
0x14000621c  mov     edi, eax
0x14000621e  mov     [rsp+98h+var_64], eax
0x140006222  jmp     short loc_140006244
0x140006224  mov     r8d, eax
0x140006227  mov     rdx, [rsp+98h+LowLimit]; Irp
0x14000622f  mov     rcx, [rsp+98h+Entry]; Entry
0x140006234  call    FatProcessException
0x140006239  mov     edi, eax
0x14000623b  mov     [rsp+98h+var_64], eax
0x14000623f  mov     r15b, byte ptr [rsp+98h+var_68]
0x140006244  test    r15b, r15b
0x140006247  jz      short loc_140006257
0x140006249  xor     ecx, ecx; Irp
0x14000624b  call    cs:__imp_IoSetTopLevelIrp
0x140006252  nop     dword ptr [rax+rax+00h]
0x140006257  call    cs:__imp_KeLeaveCriticalRegion
0x14000625e  nop     dword ptr [rax+rax+00h]
0x140006263  mov     eax, edi
0x140006265  mov     rsi, [rsp+98h+arg_0]
0x14000626d  add     rsp, 80h
0x140006274  pop     r15
0x140006276  pop     r14
0x140006278  pop     rdi
0x140006279  retn
0x14000d2f8  push    rbp
0x14000d2fa  sub     rsp, 30h
0x14000d2fe  mov     rbp, rdx
0x14000d301  mov     rdx, rcx
0x14000d304  mov     rcx, [rbp+38h]
0x14000d308  call    FatExceptionFilter
0x14000d30d  nop
0x14000d30e  add     rsp, 30h
0x14000d312  pop     rbp
0x14000d313  retn
```
