# CKsFilterFactory::DispatchCreate(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180050010`
- end: `0x18005024d`
- name: `?DispatchCreate@CKsFilterFactory@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `573`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000da50`
- `0x180019c60`
- `0x180019fc0`
- `0x180050010`
- `0x180050254`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1800501c3`
- `ntoskrnl!IofCompleteRequest` at `0x1800501c3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800500c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800500c4`

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
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      (char)v3,
      (char)a1);
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
0x180050010  push    rbx
0x180050012  push    rbp
0x180050013  push    rsi
0x180050014  push    rdi
0x180050015  push    r12
0x180050017  push    r13
0x180050019  push    r14
0x18005001b  push    r15
0x18005001d  sub     rsp, 58h
0x180050021  mov     rdi, rdx
0x180050024  mov     rax, rcx
0x180050027  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005002e  xor     r14d, r14d
0x180050031  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180050038  jz      short loc_18005004C
0x18005003a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050041  cmp     [rcx+48h], r14w
0x180050046  jnz     loc_1800501FB
0x18005004c  mov     rax, [rdi+78h]
0x180050050  mov     rsi, [rax+8]
0x180050054  mov     rcx, [rsi-38h]
0x180050058  mov     rax, [rcx]
0x18005005b  mov     rax, [rax+28h]
0x18005005f  call    _guard_dispatch_icall
0x180050064  mov     rax, [rsi+78h]
0x180050068  mov     r15d, [rsi+90h]
0x18005006f  mov     r12, [rsi+88h]
0x180050076  mov     r13, [rsi+80h]
0x18005007d  mov     rbx, [rsi]
0x180050080  mov     [rsp+98h+arg_8], rax
0x180050088  lea     rax, WPP_RECORDER_INITIALIZED
0x18005008f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180050096  jz      short loc_1800500AA
0x180050098  mov     rcx, cs:WPP_GLOBAL_Control
0x18005009f  cmp     [rcx+48h], r14w
0x1800500a4  jnz     loc_180050227
0x1800500aa  cmp     [rbx+14h], r14d
0x1800500ae  jl      loc_1800501E3
0x1800500b4  mov     edx, 348h; NumberOfBytes
0x1800500b9  mov     ecx, 200h; PoolType
0x1800500be  mov     r8d, 6966534Bh; Tag
0x1800500c4  call    cs:__imp_ExAllocatePoolWithTag
0x1800500cb  nop     dword ptr [rax+rax+00h]
0x1800500d0  mov     r14, rax
0x1800500d3  test    rax, rax
0x1800500d6  jz      loc_1800501F4
0x1800500dc  xor     edx, edx; Val
0x1800500de  mov     r8d, 348h; Size
0x1800500e4  mov     rcx, rax; void *
0x1800500e7  call    memset
0x1800500ec  lea     rcx, [r14+28h]
0x1800500f0  mov     [rcx+28h], rcx
0x1800500f4  lea     rdx, ??_7CKsFilter@@6BIKsFilter@@@; const CKsFilter::`vftable'{for `IKsFilter'}
0x1800500fb  lea     rax, ??_7CKsFilter@@6BIKsProcessingObject@@@; const CKsFilter::`vftable'{for `IKsProcessingObject'}
0x180050102  mov     [r14], rdx
0x180050105  mov     [r14+8], rax
0x180050109  lea     rax, ??_7CKsFilter@@6BIKsPowerNotify@@@; const CKsFilter::`vftable'{for `IKsPowerNotify'}
0x180050110  mov     [r14+10h], rax
0x180050114  lea     rax, ??_7CKsFilter@@6BIKsControl@@@; const CKsFilter::`vftable'{for `IKsControl'}
0x18005011b  mov     [r14+18h], rax
0x18005011f  lea     rax, ??_7CKsFilter@@6BIKsThermalNotification@@@; const CKsFilter::`vftable'{for `IKsThermalNotification'}
0x180050126  mov     [r14+20h], rax
0x18005012a  lea     rax, ??_7CKsFilter@@6BINonDelegatedUnknown@@@; const CKsFilter::`vftable'{for `INonDelegatedUnknown'}
0x180050131  mov     [rcx], rax
0x180050134  lea     rax, ??_7CKsPin@@6BIIndirectedUnknown@@@; const CKsPin::`vftable'{for `IIndirectedUnknown'}
0x18005013b  mov     [r14+30h], rax
0x18005013f  mov     rcx, r14
0x180050142  mov     rax, [rdx+8]
0x180050146  mov     byte ptr [r14+300h], 0
0x18005014e  mov     qword ptr [r14+288h], 0
0x180050159  call    _guard_dispatch_icall
0x18005015e  mov     rax, [rsp+98h+arg_8]
0x180050166  lea     r9, [rsi-80h]; struct _LIST_ENTRY *
0x18005016a  mov     [rsp+98h+var_58], r15d; unsigned int
0x18005016f  lea     r8, [rsi-80h]; struct _KSFILTERFACTORY_EXT *
0x180050173  mov     [rsp+98h+var_60], r12; struct KSAUTOMATION_TABLE_ **
0x180050178  mov     rdx, rdi; struct _IRP *
0x18005017b  mov     [rsp+98h+var_68], r13; struct KSAUTOMATION_TABLE_ **
0x180050180  mov     rcx, r14; this
0x180050183  mov     [rsp+98h+var_70], rax; struct KSAUTOMATION_TABLE_ *
0x180050188  mov     [rsp+98h+var_78], rbx; struct _KSFILTER_DESCRIPTOR *
0x18005018d  call    ?Init@CKsFilter@@QEAAJPEAU_IRP@@PEAU_KSFILTERFACTORY_EXT@@PEAU_LIST_ENTRY@@PEBU_KSFILTER_DESCRIPTOR@@PEBUKSAUTOMATION_TABLE_@@PEBQEAU6@5K@Z; CKsFilter::Init(_IRP *,_KSFILTERFACTORY_EXT *,_LIST_ENTRY *,_KSFILTER_DESCRIPTOR const *,KSAUTOMATION_TABLE_ const *,KSAUTOMATION_TABLE_ * const *,KSAUTOMATION_TABLE_ * const *,ulong)
0x180050192  mov     ebx, eax
0x180050194  mov     rcx, r14
0x180050197  mov     rax, [r14]
0x18005019a  mov     rax, [rax+10h]
0x18005019e  call    _guard_dispatch_icall
0x1800501a3  mov     rcx, [rsi-38h]
0x1800501a7  mov     rdx, [rcx]
0x1800501aa  mov     rax, [rdx+30h]
0x1800501ae  call    _guard_dispatch_icall
0x1800501b3  cmp     ebx, 103h
0x1800501b9  jz      short loc_1800501CF
0x1800501bb  xor     edx, edx; PriorityBoost
0x1800501bd  mov     [rdi+30h], ebx
0x1800501c0  mov     rcx, rdi; Irp
0x1800501c3  call    cs:__imp_IofCompleteRequest
0x1800501ca  nop     dword ptr [rax+rax+00h]
0x1800501cf  mov     eax, ebx
0x1800501d1  add     rsp, 58h
0x1800501d5  pop     r15
0x1800501d7  pop     r14
0x1800501d9  pop     r13
0x1800501db  pop     r12
0x1800501dd  pop     rdi
0x1800501de  pop     rsi
0x1800501df  pop     rbp
0x1800501e0  pop     rbx
0x1800501e1  retn
0x1800501e3  cmp     [rdi+40h], r14b
0x1800501e7  jz      loc_1800500B4
0x1800501ed  mov     ebx, 0C0000010h
0x1800501f2  jmp     short loc_1800501A3
0x1800501f4  mov     ebx, 0C000009Ah
0x1800501f9  jmp     short loc_1800501A3
0x1800501fb  mov     rcx, [rcx+40h]
0x1800501ff  mov     r9d, 1Ch
0x180050205  mov     [rsp+98h+var_68], rax
0x18005020a  mov     dl, 5
0x18005020c  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180050213  mov     [rsp+98h+var_70], rdi
0x180050218  mov     [rsp+98h+var_78], rax
0x18005021d  call    WPP_RECORDER_SF_qq
0x180050222  jmp     loc_18005004C
0x180050227  mov     rcx, [rcx+40h]
0x18005022b  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180050232  mov     r9d, 0Ah
0x180050238  mov     [rsp+98h+var_78], rax
0x18005023d  mov     dl, 5
0x18005023f  lea     r8d, [r9-9]
0x180050243  call    WPP_RECORDER_SF_
0x180050248  jmp     loc_1800500AA
```
