# RxCeSubmitTdiRequest

- ea: `0x140020f50`
- end: `0x14002111f`
- name: `RxCeSubmitTdiRequest`
- size: `463`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140023e20`
- `0x140057024`
- `0x1400573b4`
- `0x140057ba8`
- `0x140057d30`
- `0x140057eac`
- `0x140058024`
- `0x140058240`

## callees

- `0x140020f50`
- `0x140028960`
- `0x14003838c`
- `0x1400383d0`
- `0x140039fa8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140020f7e`
- `ntoskrnl!KeInitializeEvent` at `0x140020f7e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005ebfa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005ebfa`
- `ntoskrnl!IofCallDriver` at `0x140020fc2`
- `ntoskrnl!IofCallDriver` at `0x140020fc2`
- `ntoskrnl!KeReadStateEvent` at `0x140020fe2`
- `ntoskrnl!KeReadStateEvent` at `0x140020fe2`

## pseudocode

```c
__int64 __fastcall RxCeSubmitTdiRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  NTSTATUS v5; // eax
  unsigned int Status; // ebx
  NTSTATUS v8; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&RxTdiRequestCompletion;
  CurrentStackLocation[-1].Context = &Event;
  CurrentStackLocation[-1].Control = -32;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids, DeviceObject);
  }
  v5 = IofCallDriver(DeviceObject, Irp);
  if ( v5 != 259 )
  {
    if ( v5 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids,
        DeviceObject,
        Irp,
        v5);
    }
    if ( !KeReadStateEvent(&Event) )
      __debugbreak();
LABEL_6:
    Status = Irp->IoStatus.Status;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids, Status);
    }
    if ( Status == -1073741816 )
    {
      Status = -1073741300;
      Irp->IoStatus.Status = -1073741300;
    }
    return Status;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids);
  }
  v8 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  Status = v8;
  if ( v8 >= 0 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids, (unsigned int)v8);
  }
  return Status;
}

```

## disassembly

```asm
0x140020f50  mov     [rsp+arg_0], rbx
0x140020f55  mov     [rsp+arg_8], rsi
0x140020f5a  push    rdi
0x140020f5b  sub     rsp, 50h
0x140020f5f  mov     rdi, rdx
0x140020f62  mov     rbx, rcx
0x140020f65  xorps   xmm0, xmm0
0x140020f68  lea     rcx, [rsp+58h+Event]; Event
0x140020f6d  xor     eax, eax
0x140020f6f  xor     edx, edx; Type
0x140020f71  xor     r8d, r8d; State
0x140020f74  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x140020f79  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x140020f7e  call    cs:__imp_KeInitializeEvent
0x140020f85  nop     dword ptr [rax+rax+00h]
0x140020f8a  mov     rax, [rdi+0B8h]
0x140020f91  lea     rcx, RxTdiRequestCompletion
0x140020f98  mov     [rax-10h], rcx
0x140020f9c  lea     rcx, [rsp+58h+Event]
0x140020fa1  mov     [rax-8], rcx
0x140020fa5  mov     byte ptr [rax-45h], 0E0h
0x140020fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140020fb0  lea     rsi, WPP_GLOBAL_Control
0x140020fb7  cmp     rcx, rsi
0x140020fba  jnz     short loc_14002102F
0x140020fbc  mov     rdx, rdi; Irp
0x140020fbf  mov     rcx, rbx; DeviceObject
0x140020fc2  call    cs:__imp_IofCallDriver
0x140020fc9  nop     dword ptr [rax+rax+00h]
0x140020fce  cmp     eax, 103h
0x140020fd3  jz      loc_1400210AB
0x140020fd9  test    eax, eax
0x140020fdb  js      short loc_140021059
0x140020fdd  lea     rcx, [rsp+58h+Event]; Event
0x140020fe2  call    cs:__imp_KeReadStateEvent
0x140020fe9  nop     dword ptr [rax+rax+00h]
0x140020fee  test    eax, eax
0x140020ff0  jz      loc_1400210A5
0x140020ff6  mov     ebx, [rdi+30h]
0x140020ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140021000  cmp     rcx, rsi
0x140021003  jz      short loc_140021010
0x140021005  mov     eax, [rcx+2Ch]
0x140021008  test    al, 4
0x14002100a  jnz     loc_1400210EB
0x140021010  cmp     ebx, 0C0000008h
0x140021016  jz      loc_140021112
0x14002101c  mov     rsi, [rsp+58h+arg_8]
0x140021021  mov     eax, ebx
0x140021023  mov     rbx, [rsp+58h+arg_0]
0x140021028  add     rsp, 50h
0x14002102c  pop     rdi
0x14002102d  retn
0x14002102f  mov     eax, [rcx+2Ch]
0x140021032  test    al, 4
0x140021034  jz      short loc_140020FBC
0x140021036  cmp     byte ptr [rcx+29h], 1
0x14002103a  jb      short loc_140020FBC
0x14002103c  mov     rcx, [rcx+18h]
0x140021040  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140021047  mov     edx, 18h
0x14002104c  mov     r9, rbx
0x14002104f  call    WPP_SF_q
0x140021054  jmp     loc_140020FBC
0x140021059  mov     rcx, cs:WPP_GLOBAL_Control
0x140021060  cmp     rcx, rsi
0x140021063  jz      loc_140020FDD
0x140021069  mov     edx, [rcx+2Ch]
0x14002106c  test    dl, 1
0x14002106f  jz      loc_140020FDD
0x140021075  cmp     byte ptr [rcx+29h], 1
0x140021079  jb      loc_140020FDD
0x14002107f  mov     rcx, [rcx+18h]
0x140021083  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x14002108a  mov     [rsp+58h+var_30], eax
0x14002108e  mov     edx, 19h
0x140021093  mov     r9, rbx
0x140021096  mov     [rsp+58h+Timeout], rdi
0x14002109b  call    WPP_SF_qqD
0x1400210a0  jmp     loc_140020FDD
0x1400210a5  int     3; Trap to Debugger
0x1400210a6  jmp     loc_140020FF6
0x1400210ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400210b2  cmp     rcx, rsi
0x1400210b5  jz      loc_14005EBE4
0x1400210bb  mov     eax, [rcx+2Ch]
0x1400210be  test    al, 4
0x1400210c0  jz      loc_14005EBE4
0x1400210c6  cmp     byte ptr [rcx+29h], 1
0x1400210ca  jb      loc_14005EBE4
0x1400210d0  mov     rcx, [rcx+18h]
0x1400210d4  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x1400210db  mov     edx, 1Ah
0x1400210e0  call    WPP_SF_
0x1400210e5  nop
0x1400210e6  jmp     loc_14005EBE4
0x1400210eb  cmp     byte ptr [rcx+29h], 1
0x1400210ef  jb      loc_140021010
0x1400210f5  mov     rcx, [rcx+18h]
0x1400210f9  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140021100  mov     edx, 1Ch
0x140021105  mov     r9d, ebx
0x140021108  call    WPP_SF_d
0x14002110d  jmp     loc_140021010
0x140021112  mov     ebx, 0C000020Ch
0x140021117  mov     [rdi+30h], ebx
0x14002111a  jmp     loc_14002101C
0x14005ebe4  xor     r9d, r9d; Alertable
0x14005ebe7  mov     [rsp+58h+Timeout], 0; Timeout
0x14005ebf0  xor     r8d, r8d; WaitMode
0x14005ebf3  lea     rcx, [rsp+58h+Event]; Object
0x14005ebf8  xor     edx, edx; WaitReason
0x14005ebfa  call    cs:__imp_KeWaitForSingleObject
0x14005ec01  nop     dword ptr [rax+rax+00h]
0x14005ec06  mov     ebx, eax
0x14005ec08  test    eax, eax
0x14005ec0a  jns     loc_140020FF6
0x14005ec10  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ec17  cmp     rcx, rsi
0x14005ec1a  jz      loc_14002101C
0x14005ec20  mov     edx, [rcx+2Ch]
0x14005ec23  test    dl, 1
0x14005ec26  jz      loc_14002101C
0x14005ec2c  cmp     byte ptr [rcx+29h], 1
0x14005ec30  jb      loc_14002101C
0x14005ec36  mov     rcx, [rcx+18h]
0x14005ec3a  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x14005ec41  mov     edx, 1Bh
0x14005ec46  mov     r9d, eax
0x14005ec49  call    WPP_SF_d
0x14005ec4e  nop
0x14005ec4f  jmp     loc_14002101C
```
