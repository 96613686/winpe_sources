# RxRecreateVNetRootOnLogicalRdr

- ea: `0x140050414`
- end: `0x140050818`
- name: `RxRecreateVNetRootOnLogicalRdr`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x14004d498`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x140016e70`
- `0x140017310`
- `0x140017370`
- `0x140025d00`
- `0x140050414`
- `0x14005c450`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005056b`
- `ntoskrnl!ExAllocatePool2` at `0x14005056b`
- `ntoskrnl!KeInitializeEvent` at `0x1400505f4`
- `ntoskrnl!KeInitializeEvent` at `0x1400505f4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400504cc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400506c4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005075d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400504cc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400506c4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005075d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005054c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005054c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400507ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400507ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005065c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005065c`

## pseudocode

```c
__int64 __fastcall RxRecreateVNetRootOnLogicalRdr(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int64 v5; // rsi
  unsigned int v6; // ebx
  int v7; // r15d
  __int64 v10; // rdx
  __int64 v11; // rbp
  __int64 v12; // rcx
  __int64 v13; // rax
  struct _ERESOURCE *v14; // r12
  __int64 Pool2; // rbp
  PRX_CONTEXT v16; // rsi
  PRX_CONTEXT RxContext; // rax
  __int64 v18; // rax
  void (__fastcall *v19)(__int64); // rax
  PFCB v20; // rax
  __int64 (__fastcall *v21)(__int64, __int64); // rax

  v5 = *(_QWORD *)(a2 + 32);
  v6 = 0;
  v7 = 0;
  v10 = *(_QWORD *)(v5 + 48);
  if ( (*(_DWORD *)(v10 + 336) & 0x20) != 0 && Fcb && Fcb != (PFCB)v10 && (*(_DWORD *)(a3 + 56) & 0x10) == 0 )
  {
    v11 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 504LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 74, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids);
    }
    if ( !*a5 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(v11 + 24), 1u);
      *a5 = 2;
    }
    v12 = *(_QWORD *)(a3 + 392);
    v13 = v12;
    if ( !v12 )
      v13 = *(_QWORD *)(v5 + 48);
    if ( !*(_QWORD *)(*(_QWORD *)(v13 + 352) + 464LL) )
    {
      v6 = -1073741822;
LABEL_18:
      v7 = 4531;
      goto LABEL_44;
    }
    if ( !v12 )
      v12 = *(_QWORD *)(v5 + 48);
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v12 + 352) + 464LL))(a3, 0);
    if ( v6 )
      goto LABEL_18;
    v14 = (struct _ERESOURCE *)(v11 + 24);
    *(_DWORD *)(a3 + 204) = 1;
    ExReleaseResourceLite((PERESOURCE)(v11 + 24));
    *a5 = 0;
    Pool2 = ExAllocatePool2(64, 304, 1866692690);
    if ( Pool2 )
    {
      RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(v5 + 48), 2u);
      v16 = RxContext;
      if ( RxContext )
      {
        LOWORD(RxContext->RealDevice) = 0;
        *(_QWORD *)&RxContext->TrackerHistory[0].Flags = 0;
        RxContext->TrackerHistory[0].FileName = 0;
        *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = 0;
        v18 = *(_QWORD *)(a1 + 568);
        LODWORD(v16->RdbssDbgExtension) |= 0x100u;
        *((_QWORD *)&v16->9 + 21) = v18;
        KeInitializeEvent((PRKEVENT)(Pool2 + 8), SynchronizationEvent, 0);
        *(_QWORD *)(Pool2 + 32) = v16;
        *(_QWORD *)(Pool2 + 272) = RxCreateNetRootCallBack;
        *(_QWORD *)(Pool2 + 264) = a3;
        *(_DWORD *)(Pool2 + 284) = 0;
        *(_DWORD *)(Pool2 + 280) = -1073741715;
        v19 = *(void (__fastcall **)(__int64))(*(_QWORD *)&Fcb->ShareAccess.Writers + 416LL);
        if ( v19 )
          v19(Pool2);
        KeWaitForSingleObject((PVOID)(Pool2 + 8), Executive, 0, 0, 0);
        if ( !*(_DWORD *)(Pool2 + 284) && !*(_DWORD *)(Pool2 + 280) )
        {
          *(_DWORD *)(a3 + 56) |= 0x30u;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, a3);
          }
        }
        ExAcquireResourceExclusiveLite(v14, 1u);
        v20 = Fcb;
        *a5 = 2;
        v21 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)&v20->ShareAccess.Writers + 424LL);
        if ( v21 )
          v6 = v21(a3, a4);
        else
          v6 = -1073741822;
        *(_QWORD *)(a3 + 392) = Fcb;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 76, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids);
        }
      }
      else
      {
        v16 = 0;
        v7 = 4559;
        v6 = -1073741670;
      }
    }
    else
    {
      v16 = 0;
      v7 = 4548;
      v6 = -1073741670;
    }
    if ( !*a5 )
    {
      ExAcquireResourceExclusiveLite(v14, 1u);
      *a5 = 2;
    }
    RxUpdateCondition((RX_BLOCK_CONDITION)((v6 != 0) + 3), (PRX_BLOCK_CONDITION)v6, (PLIST_ENTRY)(a3 + 204));
    if ( Pool2 )
      ExFreePoolWithTag((PVOID)Pool2, 0);
    if ( v16 )
      RxDereferenceAndDeleteRxContext_Real(v16);
  }
LABEL_44:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 77, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, v6, v7);
  }
  return v6;
}

```

## disassembly

```asm
0x140050414  mov     [rsp+arg_18], r9
0x140050419  push    rbx
0x14005041a  push    rbp
0x14005041b  push    rsi
0x14005041c  push    rdi
0x14005041d  push    r12
0x14005041f  push    r13
0x140050421  push    r14
0x140050423  push    r15
0x140050425  sub     rsp, 38h
0x140050429  mov     rsi, [rdx+20h]
0x14005042d  xor     ebx, ebx
0x14005042f  xor     r15d, r15d
0x140050432  mov     rdi, r8
0x140050435  mov     r13, rcx
0x140050438  mov     rdx, [rsi+30h]
0x14005043c  mov     eax, [rdx+150h]
0x140050442  test    al, 20h
0x140050444  jz      loc_1400507C5
0x14005044a  mov     rax, cs:Fcb
0x140050451  test    rax, rax
0x140050454  jz      loc_1400507C5
0x14005045a  cmp     rax, rdx
0x14005045d  jz      loc_1400507C5
0x140050463  mov     r8d, [r8+38h]
0x140050467  test    r8b, 10h
0x14005046b  jnz     loc_1400507C5
0x140050471  mov     rax, [rcx+50h]
0x140050475  mov     rbp, [rax+1F8h]
0x14005047c  mov     rcx, cs:WPP_GLOBAL_Control
0x140050483  lea     rax, WPP_GLOBAL_Control
0x14005048a  cmp     rcx, rax
0x14005048d  jz      short loc_1400504B9
0x14005048f  test    dword ptr [rcx+2Ch], 400h
0x140050496  jz      short loc_1400504B9
0x140050498  cmp     byte ptr [rcx+29h], 2
0x14005049c  jb      short loc_1400504B9
0x14005049e  mov     rcx, [rcx+18h]
0x1400504a2  lea     edx, [rbx+4Ah]
0x1400504a5  mov     dword ptr [rsp+78h+Timeout], r8d
0x1400504aa  mov     r9, rdi
0x1400504ad  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x1400504b4  call    WPP_SF_qD
0x1400504b9  mov     r14, [rsp+78h+arg_20]
0x1400504c1  cmp     [r14], ebx
0x1400504c4  jnz     short loc_1400504DF
0x1400504c6  lea     rcx, [rbp+18h]; Resource
0x1400504ca  mov     dl, 1; Wait
0x1400504cc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400504d3  nop     dword ptr [rax+rax+00h]
0x1400504d8  mov     dword ptr [r14], 2
0x1400504df  mov     rcx, [rdi+188h]
0x1400504e6  mov     rax, rcx
0x1400504e9  test    rcx, rcx
0x1400504ec  jnz     short loc_1400504F2
0x1400504ee  mov     rax, [rsi+30h]
0x1400504f2  mov     rax, [rax+160h]
0x1400504f9  cmp     [rax+1D0h], rbx
0x140050500  jnz     short loc_140050509
0x140050502  mov     ebx, 0C0000002h
0x140050507  jmp     short loc_140050530
0x140050509  test    rcx, rcx
0x14005050c  jnz     short loc_140050512
0x14005050e  mov     rcx, [rsi+30h]
0x140050512  mov     rax, [rcx+160h]
0x140050519  xor     edx, edx
0x14005051b  mov     rcx, rdi
0x14005051e  mov     rax, [rax+1D0h]
0x140050525  call    _guard_dispatch_icall
0x14005052a  mov     ebx, eax
0x14005052c  test    eax, eax
0x14005052e  jz      short loc_14005053B
0x140050530  mov     r15d, 11B3h
0x140050536  jmp     loc_1400507C5
0x14005053b  lea     r12, [rbp+18h]
0x14005053f  mov     dword ptr [rdi+0CCh], 1
0x140050549  mov     rcx, r12; Resource
0x14005054c  call    cs:__imp_ExReleaseResourceLite
0x140050553  nop     dword ptr [rax+rax+00h]
0x140050558  xor     ebx, ebx
0x14005055a  mov     edx, 130h
0x14005055f  mov     r8d, 6F437852h
0x140050565  mov     [r14], ebx
0x140050568  lea     ecx, [rbx+40h]
0x14005056b  call    cs:__imp_ExAllocatePool2
0x140050572  nop     dword ptr [rax+rax+00h]
0x140050577  mov     rbp, rax
0x14005057a  test    rax, rax
0x14005057d  jnz     short loc_140050591
0x14005057f  mov     esi, ebx
0x140050581  mov     r15d, 11C4h
0x140050587  mov     ebx, 0C000009Ah
0x14005058c  jmp     loc_140050752
0x140050591  mov     rdx, [rsi+30h]; RxDeviceObject
0x140050595  mov     r8d, 2; InitialContextFlags
0x14005059b  xor     ecx, ecx; Irp
0x14005059d  call    RxCreateRxContext
0x1400505a2  mov     rsi, rax
0x1400505a5  test    rax, rax
0x1400505a8  jnz     short loc_1400505BD
0x1400505aa  mov     rsi, rbx
0x1400505ad  mov     r15d, 11CFh
0x1400505b3  mov     ebx, 0C000009Ah
0x1400505b8  jmp     loc_140050752
0x1400505bd  xor     r8d, r8d; State
0x1400505c0  mov     [rax+20h], bx
0x1400505c4  mov     [rax+290h], rbx
0x1400505cb  lea     rcx, [rbp+8]; Event
0x1400505cf  mov     [rax+288h], rbx
0x1400505d6  mov     [rax+280h], rbx
0x1400505dd  mov     rax, [r13+238h]
0x1400505e4  lea     edx, [r8+1]; Type
0x1400505e8  bts     dword ptr [rsi+78h], 8
0x1400505ed  mov     [rsi+238h], rax
0x1400505f4  call    cs:__imp_KeInitializeEvent
0x1400505fb  nop     dword ptr [rax+rax+00h]
0x140050600  mov     [rbp+20h], rsi
0x140050604  lea     rax, RxCreateNetRootCallBack
0x14005060b  mov     [rbp+110h], rax
0x140050612  mov     [rbp+108h], rdi
0x140050619  mov     [rbp+11Ch], ebx
0x14005061f  mov     dword ptr [rbp+118h], 0C000006Dh
0x140050629  mov     rax, cs:Fcb
0x140050630  mov     rcx, [rax+160h]
0x140050637  mov     rax, [rcx+1A0h]
0x14005063e  test    rax, rax
0x140050641  jz      short loc_14005064B
0x140050643  mov     rcx, rbp
0x140050646  call    _guard_dispatch_icall
0x14005064b  xor     r9d, r9d; Alertable
0x14005064e  mov     [rsp+78h+Timeout], rbx; Timeout
0x140050653  xor     r8d, r8d; WaitMode
0x140050656  lea     rcx, [rbp+8]; Object
0x14005065a  xor     edx, edx; WaitReason
0x14005065c  call    cs:__imp_KeWaitForSingleObject
0x140050663  nop     dword ptr [rax+rax+00h]
0x140050668  cmp     [rbp+11Ch], ebx
0x14005066e  jnz     short loc_1400506B8
0x140050670  cmp     [rbp+118h], ebx
0x140050676  jnz     short loc_1400506B8
0x140050678  or      dword ptr [rdi+38h], 30h
0x14005067c  mov     rcx, cs:WPP_GLOBAL_Control
0x140050683  lea     r13, WPP_GLOBAL_Control
0x14005068a  cmp     rcx, r13
0x14005068d  jz      short loc_1400506BF
0x14005068f  test    dword ptr [rcx+2Ch], 400h
0x140050696  jz      short loc_1400506BF
0x140050698  cmp     byte ptr [rcx+29h], 4
0x14005069c  jb      short loc_1400506BF
0x14005069e  mov     rcx, [rcx+18h]
0x1400506a2  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x1400506a9  mov     edx, 4Bh ; 'K'
0x1400506ae  mov     r9, rdi
0x1400506b1  call    WPP_SF_q
0x1400506b6  jmp     short loc_1400506BF
0x1400506b8  lea     r13, WPP_GLOBAL_Control
0x1400506bf  mov     dl, 1; Wait
0x1400506c1  mov     rcx, r12; Resource
0x1400506c4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400506cb  nop     dword ptr [rax+rax+00h]
0x1400506d0  mov     rax, cs:Fcb
0x1400506d7  mov     dword ptr [r14], 2
0x1400506de  mov     rcx, [rax+160h]
0x1400506e5  mov     rax, [rcx+1A8h]
0x1400506ec  test    rax, rax
0x1400506ef  jnz     short loc_1400506F8
0x1400506f1  mov     ebx, 0C0000002h
0x1400506f6  jmp     short loc_14005070A
0x1400506f8  mov     rdx, [rsp+78h+arg_18]
0x140050700  mov     rcx, rdi
0x140050703  call    _guard_dispatch_icall
0x140050708  mov     ebx, eax
0x14005070a  mov     rax, cs:Fcb
0x140050711  mov     [rdi+188h], rax
0x140050718  mov     rcx, cs:WPP_GLOBAL_Control
0x14005071f  cmp     rcx, r13
0x140050722  jz      short loc_140050752
0x140050724  test    dword ptr [rcx+2Ch], 400h
0x14005072b  jz      short loc_140050752
0x14005072d  cmp     byte ptr [rcx+29h], 2
0x140050731  jb      short loc_140050752
0x140050733  mov     eax, [rdi+38h]
0x140050736  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14005073d  mov     rcx, [rcx+18h]
0x140050741  mov     edx, 4Ch ; 'L'
0x140050746  mov     r9, rdi
0x140050749  mov     dword ptr [rsp+78h+Timeout], eax
0x14005074d  call    WPP_SF_qD
0x140050752  cmp     dword ptr [r14], 0
0x140050756  jnz     short loc_140050770
0x140050758  mov     dl, 1; Wait
0x14005075a  mov     rcx, r12; Resource
0x14005075d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140050764  nop     dword ptr [rax+rax+00h]
0x140050769  mov     dword ptr [r14], 2
0x140050770  xor     ecx, ecx
0x140050772  mov     [rsp+78h+var_50], 0EB12h
0x140050779  lea     rax, [rdi+168h]
0x140050780  test    ebx, ebx
0x140050782  lea     r9, [rdi+0D0h]
0x140050789  mov     [rsp+78h+Timeout], rax
0x14005078e  setnz   cl
0x140050791  lea     r8, [rdi+0CCh]; TransitionWaitList
0x140050798  add     ecx, 3; NewConditionValue
0x14005079b  mov     edx, ebx; Condition
0x14005079d  call    RxUpdateCondition
0x1400507a2  test    rbp, rbp
0x1400507a5  jz      short loc_1400507B8
0x1400507a7  xor     edx, edx; Tag
0x1400507a9  mov     rcx, rbp; P
0x1400507ac  call    cs:__imp_ExFreePoolWithTag
0x1400507b3  nop     dword ptr [rax+rax+00h]
0x1400507b8  test    rsi, rsi
0x1400507bb  jz      short loc_1400507C5
0x1400507bd  mov     rcx, rsi; RxContext
0x1400507c0  call    RxDereferenceAndDeleteRxContext_Real
0x1400507c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400507cc  lea     rax, WPP_GLOBAL_Control
0x1400507d3  cmp     rcx, rax
0x1400507d6  jz      short loc_140050804
0x1400507d8  test    dword ptr [rcx+2Ch], 400h
0x1400507df  jz      short loc_140050804
0x1400507e1  cmp     byte ptr [rcx+29h], 2
0x1400507e5  jb      short loc_140050804
0x1400507e7  mov     rcx, [rcx+18h]
0x1400507eb  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x1400507f2  mov     edx, 4Dh ; 'M'
0x1400507f7  mov     dword ptr [rsp+78h+Timeout], r15d
0x1400507fc  mov     r9d, ebx
0x1400507ff  call    WPP_SF_Dd
0x140050804  mov     eax, ebx
0x140050806  add     rsp, 38h
0x14005080a  pop     r15
0x14005080c  pop     r14
0x14005080e  pop     r13
0x140050810  pop     r12
0x140050812  pop     rdi
0x140050813  pop     rsi
0x140050814  pop     rbp
0x140050815  pop     rbx
0x140050816  retn
```
