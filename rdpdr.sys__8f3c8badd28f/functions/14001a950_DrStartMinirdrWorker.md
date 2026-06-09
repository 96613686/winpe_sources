# DrStartMinirdrWorker

- ea: `0x14001a950`
- end: `0x14001aabc`
- name: `DrStartMinirdrWorker`
- size: `364`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000327c`
- `0x140018f30`
- `0x14001a950`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a98a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a98a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a9ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a9ab`
- `ntoskrnl!KeSetEvent` at `0x14001aa91`
- `ntoskrnl!KeSetEvent` at `0x14001aa91`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001aa9f`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001aa9f`
- `rdbss!RxStartMinirdr` at `0x14001a99d`
- `rdbss!RxStartMinirdr` at `0x14001a99d`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001a9e4`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001a9e4`
- `rdbss!RxCreateRxContext` at `0x14001a96b`
- `rdbss!RxCreateRxContext` at `0x14001a96b`

## pseudocode

```c
void __fastcall DrStartMinirdrWorker(PRDBSS_DEVICE_OBJECT *StartContext)
{
  PRX_CONTEXT RxContext; // rdi
  int started; // ebx

  RxContext = RxCreateRxContext(0, StartContext[10], 0x202u);
  if ( RxContext )
  {
    KeEnterCriticalRegion();
    started = RxStartMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids,
        (unsigned int)started);
    RxDereferenceAndDeleteRxContext_Real(RxContext);
    if ( started >= 0 )
    {
      started = PurgeMupCache();
      if ( started < 0 )
      {
        _InterlockedCompareExchange((_DWORD *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink + 1, 0, 1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids,
            (unsigned int)started);
      }
      else
      {
        _InterlockedExchange((_DWORD *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink + 1, 2);
      }
      goto LABEL_16;
    }
  }
  else
  {
    started = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids,
      (unsigned int)started);
  _InterlockedCompareExchange((_DWORD *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink + 1, 0, 1);
LABEL_16:
  KeSetEvent((PRKEVENT)&WPP_MAIN_CB.DeviceExtension, 0, 0);
  PsTerminateSystemThread(started);
}

```

## disassembly

```asm
0x14001a950  mov     [rsp+arg_0], rbx
0x14001a955  mov     [rsp+arg_8], rsi
0x14001a95a  push    rdi
0x14001a95b  sub     rsp, 20h
0x14001a95f  mov     rdx, [rcx+50h]; RxDeviceObject
0x14001a963  mov     r8d, 202h; InitialContextFlags
0x14001a969  xor     ecx, ecx; Irp
0x14001a96b  call    cs:__imp_RxCreateRxContext
0x14001a972  nop     dword ptr [rax+rax+00h]
0x14001a977  lea     rsi, WPP_GLOBAL_Control
0x14001a97e  mov     rdi, rax
0x14001a981  test    rax, rax
0x14001a984  jz      loc_14001AA47
0x14001a98a  call    cs:__imp_KeEnterCriticalRegion
0x14001a991  nop     dword ptr [rax+rax+00h]
0x14001a996  lea     rdx, [rdi+23h]; PostToFsp
0x14001a99a  mov     rcx, rdi; RxContext
0x14001a99d  call    cs:__imp_RxStartMinirdr
0x14001a9a4  nop     dword ptr [rax+rax+00h]
0x14001a9a9  mov     ebx, eax
0x14001a9ab  call    cs:__imp_KeLeaveCriticalRegion
0x14001a9b2  nop     dword ptr [rax+rax+00h]
0x14001a9b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a9be  cmp     rcx, rsi
0x14001a9c1  jz      short loc_14001A9E1
0x14001a9c3  cmp     byte ptr [rcx+29h], 4
0x14001a9c7  jb      short loc_14001A9E1
0x14001a9c9  mov     rcx, [rcx+18h]
0x14001a9cd  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a9d4  mov     edx, 1Dh
0x14001a9d9  mov     r9d, ebx
0x14001a9dc  call    WPP_SF_d
0x14001a9e1  mov     rcx, rdi; RxContext
0x14001a9e4  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x14001a9eb  nop     dword ptr [rax+rax+00h]
0x14001a9f0  test    ebx, ebx
0x14001a9f2  js      short loc_14001AA4C
0x14001a9f4  call    ?PurgeMupCache@@YAJXZ; PurgeMupCache(void)
0x14001a9f9  mov     ebx, eax
0x14001a9fb  test    eax, eax
0x14001a9fd  js      short loc_14001AA0C
0x14001a9ff  mov     ecx, 2
0x14001aa04  xchg    ecx, dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+4
0x14001aa0a  jmp     short loc_14001AA85
0x14001aa0c  xor     ecx, ecx
0x14001aa0e  lea     eax, [rcx+1]
0x14001aa11  lock cmpxchg dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+4, ecx
0x14001aa19  mov     rax, cs:WPP_GLOBAL_Control
0x14001aa20  cmp     rax, rsi
0x14001aa23  jz      short loc_14001AA85
0x14001aa25  mov     ecx, 2
0x14001aa2a  cmp     [rax+29h], cl
0x14001aa2d  jb      short loc_14001AA85
0x14001aa2f  lea     edx, [rcx+1Ch]
0x14001aa32  mov     r9d, ebx
0x14001aa35  mov     rcx, [rax+18h]
0x14001aa39  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001aa40  call    WPP_SF_d
0x14001aa45  jmp     short loc_14001AA85
0x14001aa47  mov     ebx, 0C000009Ah
0x14001aa4c  mov     rax, cs:WPP_GLOBAL_Control
0x14001aa53  cmp     rax, rsi
0x14001aa56  jz      short loc_14001AA78
0x14001aa58  mov     ecx, 2
0x14001aa5d  cmp     [rax+29h], cl
0x14001aa60  jb      short loc_14001AA78
0x14001aa62  lea     edx, [rcx+1Dh]
0x14001aa65  mov     r9d, ebx
0x14001aa68  mov     rcx, [rax+18h]
0x14001aa6c  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001aa73  call    WPP_SF_d
0x14001aa78  xor     ecx, ecx
0x14001aa7a  lea     eax, [rcx+1]
0x14001aa7d  lock cmpxchg dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+4, ecx
0x14001aa85  xor     r8d, r8d; Wait
0x14001aa88  lea     rcx, WPP_MAIN_CB.DeviceExtension; Event
0x14001aa8f  xor     edx, edx; Increment
0x14001aa91  call    cs:__imp_KeSetEvent
0x14001aa98  nop     dword ptr [rax+rax+00h]
0x14001aa9d  mov     ecx, ebx; ExitStatus
0x14001aa9f  call    cs:__imp_PsTerminateSystemThread
0x14001aaa6  nop     dword ptr [rax+rax+00h]
0x14001aaab  mov     rbx, [rsp+28h+arg_0]
0x14001aab0  mov     rsi, [rsp+28h+arg_8]
0x14001aab5  add     rsp, 20h
0x14001aab9  pop     rdi
0x14001aaba  retn
```
