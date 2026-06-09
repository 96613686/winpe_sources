# CKsFilterFactory::DispatchCreate(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1800501b0`
- end: `0x1800503ed`
- name: `?DispatchCreate@CKsFilterFactory@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000da50`
- `0x180019cb0`
- `0x18001a000`
- `0x1800501b0`
- `0x1800503f4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180050363`
- `ntoskrnl!IofCompleteRequest` at `0x180050363`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050264`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050264`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::DispatchCreate(struct _DEVICE_OBJECT *a1, struct _IRP *a2, int a3)
{
  struct _IRP *v3; // rdi
  struct _LIST_ENTRY *Blink; // rsi
  int v5; // edx
  unsigned int Flink; // r15d
  struct KSAUTOMATION_TABLE_ *const *v7; // r12
  struct KSAUTOMATION_TABLE_ *const *v8; // r13
  const struct _KSFILTER_DESCRIPTOR *v9; // rbx
  CKsFilter *PoolWithTag; // rax
  CKsFilter *v11; // r14
  unsigned int v12; // ebx
  struct KSAUTOMATION_TABLE_ *v14; // [rsp+A8h] [rbp+10h]

  v3 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      28,
      (char)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      (char)v3);
  }
  Blink = v3->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink->Blink;
  ((void (__fastcall *)(struct _LIST_ENTRY *))Blink[-4].Blink->Flink[2].Blink)(Blink[-4].Blink);
  Flink = (unsigned int)Blink[9].Flink;
  v7 = (struct KSAUTOMATION_TABLE_ *const *)Blink[8].Blink;
  v8 = (struct KSAUTOMATION_TABLE_ *const *)Blink[8].Flink;
  v9 = (const struct _KSFILTER_DESCRIPTOR *)Blink->Flink;
  v14 = (struct KSAUTOMATION_TABLE_ *)Blink[7].Blink;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      10,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  if ( (v9->Flags & 0x80000000) != 0 && v3->RequestorMode )
  {
    v12 = -1073741808;
  }
  else
  {
    PoolWithTag = (CKsFilter *)ExAllocatePoolWithTag(NonPagedPoolNx, 0x348u, 0x6966534Bu);
    v11 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, sizeof(CKsFilter));
      v11->m_UnknownOuter = (IUnknown *)&v11->CBaseUnknown;
      v11->IKsFilter::IUnknown::__vftable = (CKsFilter_vtbl *)&CKsFilter::`vftable'{for `IKsFilter'};
      v11->IKsProcessingObject::IUnknown::__vftable = (IKsProcessingObject_vtbl *)&CKsFilter::`vftable'{for `IKsProcessingObject'};
      v11->IKsPowerNotify::IUnknown::__vftable = (IKsPowerNotify_vtbl *)&CKsFilter::`vftable'{for `IKsPowerNotify'};
      v11->IKsControl::IUnknown::__vftable = (IKsControl_vtbl *)&CKsFilter::`vftable'{for `IKsControl'};
      v11->IKsThermalNotification::IUnknown::__vftable = (IKsThermalNotification_vtbl *)&CKsFilter::`vftable'{for `IKsThermalNotification'};
      v11->CBaseUnknown::INonDelegatedUnknown::__vftable = (CBaseUnknown_vtbl *)&CKsFilter::`vftable'{for `INonDelegatedUnknown'};
      v11->CBaseUnknown::IIndirectedUnknown::__vftable = (IIndirectedUnknown_vtbl *)&CKsPin::`vftable'{for `IIndirectedUnknown'};
      v11->m_IsVideoCameraFilter = 0;
      v11->m_DefaultConnections = 0;
      CKsFilter::AddRef(v11);
      v12 = CKsFilter::Init(v11, v3, (struct _KSFILTERFACTORY_EXT *)&Blink[-8], Blink - 8, v9, v14, v8, v7, Flink);
      v11->Release(v11);
    }
    else
    {
      v12 = -1073741670;
    }
  }
  ((void (__fastcall *)(struct _LIST_ENTRY *))Blink[-4].Blink->Flink[3].Flink)(Blink[-4].Blink);
  if ( v12 != 259 )
  {
    v3->IoStatus.Status = v12;
    IofCompleteRequest(v3, 0);
  }
  return v12;
}

```

## disassembly

```asm
0x1800501b0  push    rbx
0x1800501b2  push    rbp
0x1800501b3  push    rsi
0x1800501b4  push    rdi
0x1800501b5  push    r12
0x1800501b7  push    r13
0x1800501b9  push    r14
0x1800501bb  push    r15
0x1800501bd  sub     rsp, 58h
0x1800501c1  mov     rdi, rdx
0x1800501c4  mov     rax, rcx
0x1800501c7  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800501ce  xor     r14d, r14d
0x1800501d1  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800501d8  jz      short loc_1800501EC
0x1800501da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800501e1  cmp     [rcx+48h], r14w
0x1800501e6  jnz     loc_18005039B
0x1800501ec  mov     rax, [rdi+78h]
0x1800501f0  mov     rsi, [rax+8]
0x1800501f4  mov     rcx, [rsi-38h]
0x1800501f8  mov     rax, [rcx]
0x1800501fb  mov     rax, [rax+28h]
0x1800501ff  call    _guard_dispatch_icall
0x180050204  mov     rax, [rsi+78h]
0x180050208  mov     r15d, [rsi+90h]
0x18005020f  mov     r12, [rsi+88h]
0x180050216  mov     r13, [rsi+80h]
0x18005021d  mov     rbx, [rsi]
0x180050220  mov     [rsp+98h+arg_8], rax
0x180050228  lea     rax, WPP_RECORDER_INITIALIZED
0x18005022f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180050236  jz      short loc_18005024A
0x180050238  mov     rcx, cs:WPP_GLOBAL_Control
0x18005023f  cmp     [rcx+48h], r14w
0x180050244  jnz     loc_1800503C7
0x18005024a  cmp     [rbx+14h], r14d
0x18005024e  jl      loc_180050383
0x180050254  mov     edx, 348h; NumberOfBytes
0x180050259  mov     ecx, 200h; PoolType
0x18005025e  mov     r8d, 6966534Bh; Tag
0x180050264  call    cs:__imp_ExAllocatePoolWithTag
0x18005026b  nop     dword ptr [rax+rax+00h]
0x180050270  mov     r14, rax
0x180050273  test    rax, rax
0x180050276  jz      loc_180050394
0x18005027c  xor     edx, edx; Val
0x18005027e  mov     r8d, 348h; Size
0x180050284  mov     rcx, rax; void *
0x180050287  call    memset
0x18005028c  lea     rcx, [r14+28h]
0x180050290  mov     [rcx+28h], rcx
0x180050294  lea     rdx, ??_7CKsFilter@@6BIKsFilter@@@; const CKsFilter::`vftable'{for `IKsFilter'}
0x18005029b  lea     rax, ??_7CKsFilter@@6BIKsProcessingObject@@@; const CKsFilter::`vftable'{for `IKsProcessingObject'}
0x1800502a2  mov     [r14], rdx
0x1800502a5  mov     [r14+8], rax
0x1800502a9  lea     rax, ??_7CKsFilter@@6BIKsPowerNotify@@@; const CKsFilter::`vftable'{for `IKsPowerNotify'}
0x1800502b0  mov     [r14+10h], rax
0x1800502b4  lea     rax, ??_7CKsFilter@@6BIKsControl@@@; const CKsFilter::`vftable'{for `IKsControl'}
0x1800502bb  mov     [r14+18h], rax
0x1800502bf  lea     rax, ??_7CKsFilter@@6BIKsThermalNotification@@@; const CKsFilter::`vftable'{for `IKsThermalNotification'}
0x1800502c6  mov     [r14+20h], rax
0x1800502ca  lea     rax, ??_7CKsFilter@@6BINonDelegatedUnknown@@@; const CKsFilter::`vftable'{for `INonDelegatedUnknown'}
0x1800502d1  mov     [rcx], rax
0x1800502d4  lea     rax, ??_7CKsPin@@6BIIndirectedUnknown@@@; const CKsPin::`vftable'{for `IIndirectedUnknown'}
0x1800502db  mov     [r14+30h], rax
0x1800502df  mov     rcx, r14
0x1800502e2  mov     rax, [rdx+8]
0x1800502e6  mov     byte ptr [r14+300h], 0
0x1800502ee  mov     qword ptr [r14+288h], 0
0x1800502f9  call    _guard_dispatch_icall
0x1800502fe  mov     rax, [rsp+98h+arg_8]
0x180050306  lea     r9, [rsi-80h]; struct _LIST_ENTRY *
0x18005030a  mov     [rsp+98h+var_58], r15d; unsigned int
0x18005030f  lea     r8, [rsi-80h]; struct _KSFILTERFACTORY_EXT *
0x180050313  mov     [rsp+98h+var_60], r12; struct KSAUTOMATION_TABLE_ **
0x180050318  mov     rdx, rdi; struct _IRP *
0x18005031b  mov     [rsp+98h+var_68], r13; struct KSAUTOMATION_TABLE_ **
0x180050320  mov     rcx, r14; this
0x180050323  mov     [rsp+98h+var_70], rax; struct KSAUTOMATION_TABLE_ *
0x180050328  mov     [rsp+98h+var_78], rbx; struct _KSFILTER_DESCRIPTOR *
0x18005032d  call    ?Init@CKsFilter@@QEAAJPEAU_IRP@@PEAU_KSFILTERFACTORY_EXT@@PEAU_LIST_ENTRY@@PEBU_KSFILTER_DESCRIPTOR@@PEBUKSAUTOMATION_TABLE_@@PEBQEAU6@5K@Z; CKsFilter::Init(_IRP *,_KSFILTERFACTORY_EXT *,_LIST_ENTRY *,_KSFILTER_DESCRIPTOR const *,KSAUTOMATION_TABLE_ const *,KSAUTOMATION_TABLE_ * const *,KSAUTOMATION_TABLE_ * const *,ulong)
0x180050332  mov     ebx, eax
0x180050334  mov     rcx, r14
0x180050337  mov     rax, [r14]
0x18005033a  mov     rax, [rax+10h]
0x18005033e  call    _guard_dispatch_icall
0x180050343  mov     rcx, [rsi-38h]
0x180050347  mov     rdx, [rcx]
0x18005034a  mov     rax, [rdx+30h]
0x18005034e  call    _guard_dispatch_icall
0x180050353  cmp     ebx, 103h
0x180050359  jz      short loc_18005036F
0x18005035b  xor     edx, edx; PriorityBoost
0x18005035d  mov     [rdi+30h], ebx
0x180050360  mov     rcx, rdi; Irp
0x180050363  call    cs:__imp_IofCompleteRequest
0x18005036a  nop     dword ptr [rax+rax+00h]
0x18005036f  mov     eax, ebx
0x180050371  add     rsp, 58h
0x180050375  pop     r15
0x180050377  pop     r14
0x180050379  pop     r13
0x18005037b  pop     r12
0x18005037d  pop     rdi
0x18005037e  pop     rsi
0x18005037f  pop     rbp
0x180050380  pop     rbx
0x180050381  retn
0x180050383  cmp     [rdi+40h], r14b
0x180050387  jz      loc_180050254
0x18005038d  mov     ebx, 0C0000010h
0x180050392  jmp     short loc_180050343
0x180050394  mov     ebx, 0C000009Ah
0x180050399  jmp     short loc_180050343
0x18005039b  mov     rcx, [rcx+40h]
0x18005039f  mov     r9d, 1Ch
0x1800503a5  mov     [rsp+98h+var_68], rax
0x1800503aa  mov     dl, 5
0x1800503ac  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x1800503b3  mov     [rsp+98h+var_70], rdi
0x1800503b8  mov     [rsp+98h+var_78], rax
0x1800503bd  call    WPP_RECORDER_SF_qq
0x1800503c2  jmp     loc_1800501EC
0x1800503c7  mov     rcx, [rcx+40h]
0x1800503cb  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x1800503d2  mov     r9d, 0Ah
0x1800503d8  mov     [rsp+98h+var_78], rax
0x1800503dd  mov     dl, 5
0x1800503df  lea     r8d, [r9-9]
0x1800503e3  call    WPP_RECORDER_SF_
0x1800503e8  jmp     loc_18005024A
```
