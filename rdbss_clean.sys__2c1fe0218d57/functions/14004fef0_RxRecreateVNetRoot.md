# RxRecreateVNetRoot

- ea: `0x14004fef0`
- end: `0x14005040e`
- name: `RxRecreateVNetRoot`
- size: `1310`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x140078fe0`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x14000f4d0`
- `0x140014e40`
- `0x140014ec0`
- `0x140016e20`
- `0x140016e70`
- `0x140017a38`
- `0x14001b178`
- `0x140025d00`
- `0x14004dc60`
- `0x14004fef0`
- `0x14005c450`
- `0x1400621c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140050035`
- `ntoskrnl!ExAllocatePool2` at `0x140050035`
- `ntoskrnl!KeInitializeEvent` at `0x14005005c`
- `ntoskrnl!KeInitializeEvent` at `0x14005005c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140050003`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005025a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140050003`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005025a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ffdd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005011a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ffdd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005011a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050393`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050393`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14004ff79`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400503af`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14004ff79`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400503af`
- `ntoskrnl!KeWaitForSingleObject` at `0x140050161`
- `ntoskrnl!KeWaitForSingleObject` at `0x140050161`

## pseudocode

```c
__int64 __fastcall RxRecreateVNetRoot(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rax
  struct _RDBSS_DEVICE_OBJECT *v7; // rbp
  LARGE_INTEGER CacheWriteBytesRequested; // rbx
  struct _ERESOURCE *v9; // r12
  PRX_CONTEXT RxContext; // rax
  enum _RX_BLOCK_CONDITION *v11; // r14
  int v12; // ebx
  _DWORD *v13; // r13
  __int64 Pool2; // rax
  _DWORD *v15; // r12
  __int64 (__fastcall *v16)(enum _RX_BLOCK_CONDITION *, __int64); // rax
  struct _LIST_ENTRY *Flink; // rax
  _DWORD *v18; // rsi
  void (__fastcall *DeviceObject)(__int64, _QWORD); // rax
  __int64 v20; // r9
  struct _ERESOURCE *Resource; // [rsp+70h] [rbp+8h]
  __int64 v23; // [rsp+88h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a1 + 32);
  v23 = 0;
  v7 = *(struct _RDBSS_DEVICE_OBJECT **)(v3 + 48);
  CacheWriteBytesRequested = v7->CacheWriteBytesRequested;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      164,
      (unsigned int)&WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
      a1,
      a2,
      a2 + 224);
  }
  v9 = (struct _ERESOURCE *)(CacheWriteBytesRequested.QuadPart + 24);
  Resource = (struct _ERESOURCE *)(CacheWriteBytesRequested.QuadPart + 24);
  ExIsResourceAcquiredSharedLite((PERESOURCE)(CacheWriteBytesRequested.QuadPart + 24));
  RxContext = RxCreateRxContext(0, v7, 2u);
  v11 = (enum _RX_BLOCK_CONDITION *)RxContext;
  if ( RxContext )
  {
    LOWORD(RxContext->RealDevice) = 0;
    v13 = (_DWORD *)(a2 + 204);
    *(_QWORD *)&RxContext->TrackerHistory[0].Flags = a2;
    RxContext->TrackerHistory[0].FileName = (PSZ)a1;
    *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = *(_QWORD *)(a1 + 32);
    if ( *(_DWORD *)(a2 + 204) == 1 )
    {
      v12 = 0;
      ExReleaseResourceLite(v9);
      RxWaitForStableCondition(v11, (PLIST_ENTRY)(a2 + 204), (PRX_CONTEXT)(a2 + 360), 0);
      ExAcquireResourceExclusiveLite(v9, 1u);
      if ( (*(_DWORD *)(a2 + 56) & 0x10) != 0 )
        v12 = *(_DWORD *)(a2 + 208);
      goto LABEL_66;
    }
    Pool2 = ExAllocatePool2(64, 304, 1866692690);
    v15 = (_DWORD *)Pool2;
    if ( !Pool2 )
    {
      v12 = -1073741670;
LABEL_65:
      v9 = Resource;
LABEL_66:
      RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)v11);
      goto LABEL_67;
    }
    KeInitializeEvent((PRKEVENT)(Pool2 + 8), SynchronizationEvent, 0);
    *((_QWORD *)v15 + 4) = v11;
    *((_QWORD *)v15 + 34) = RxCreateNetRootCallBack;
    *((_QWORD *)v15 + 33) = a2;
    *(_QWORD *)v15 = v7;
    *v13 = 1;
    if ( !a3 )
    {
      v16 = *(__int64 (__fastcall **)(enum _RX_BLOCK_CONDITION *, __int64))(*(_QWORD *)&Fcb->ShareAccess.Writers + 448LL);
      if ( !v16 )
      {
        v12 = -1073741822;
LABEL_16:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_dq(
            WPP_GLOBAL_Control->AttachedDevice,
            165,
            &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
            (unsigned int)v12,
            a2);
        }
LABEL_64:
        ExFreePoolWithTag(v15, 0);
        goto LABEL_65;
      }
      v12 = v16(v11, a2);
      if ( v12 < 0 )
        goto LABEL_16;
    }
    ExReleaseResourceLite(Resource);
    Flink = v7->RDBSSDeviceObject[1].Queue.ListEntry.Flink;
    if ( Flink && ((unsigned int (__fastcall *)(_DWORD *))Flink)(v15) == 259 )
      KeWaitForSingleObject(v15 + 2, Executive, 0, 0, 0);
    v12 = v15[71];
    if ( v12 || (v12 = v15[70]) != 0 )
    {
      if ( v12 == -1073741790
        || v12 == -1073741724
        || v12 == -1073741718
        || v12 == -1073741715
        || v12 == -1073741711
        || v12 == -1073741276
        || v12 == -1073740920 )
      {
        v18 = (_DWORD *)(a2 + 56);
        *(_DWORD *)(a2 + 56) |= 0x20u;
      }
      else
      {
        v18 = (_DWORD *)(a2 + 56);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          167,
          &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
          a2,
          *v18,
          v12);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 166, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, a1 + 216);
      }
      v12 = 0;
      v18 = (_DWORD *)(a2 + 56);
    }
    ExAcquireResourceExclusiveLite(Resource, 1u);
    if ( v12 >= 0 )
    {
      if ( !(unsigned __int8)RxGetShareRights(a2, &v23)
        || (_WORD)v23
        || (unsigned __int8)RxIsUserCredentialPresent(*(_QWORD *)(a2 + 104)) )
      {
        *v18 &= ~0x10u;
        *v18 &= ~0x20u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 169, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, a2);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 168, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, a2);
        }
        DeviceObject = (void (__fastcall *)(__int64, _QWORD))v7->RDBSSDeviceObject[1].Queue.Wcb.DeviceObject;
        if ( DeviceObject )
          DeviceObject(a2, 0);
        *(_DWORD *)(a2 + 56) |= 0x20u;
        v12 = -1073741715;
      }
    }
    v20 = (unsigned int)*v13;
    if ( (_DWORD)v20 == 1 )
    {
      RxUpdateCondition(Condition_Good, (PRX_BLOCK_CONDITION)(unsigned int)v12, (PLIST_ENTRY)(a2 + 204));
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 170, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, v20);
    }
    goto LABEL_64;
  }
  v12 = -1073741670;
LABEL_67:
  ExIsResourceAcquiredSharedLite(v9);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      171,
      &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14004fef0  mov     r11, rsp
0x14004fef3  mov     [r11+18h], rbx
0x14004fef7  push    rbp
0x14004fef8  push    rsi
0x14004fef9  push    rdi
0x14004fefa  push    r12
0x14004fefc  push    r13
0x14004fefe  push    r14
0x14004ff00  push    r15
0x14004ff02  sub     rsp, 30h
0x14004ff06  mov     rax, [rcx+20h]
0x14004ff0a  mov     r15b, r8b
0x14004ff0d  mov     rdi, rdx
0x14004ff10  mov     qword ptr [r11+20h], 0
0x14004ff18  mov     rsi, rcx
0x14004ff1b  mov     rbp, [rax+30h]
0x14004ff1f  mov     rbx, [rbp+1F8h]
0x14004ff26  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ff2d  lea     rax, WPP_GLOBAL_Control
0x14004ff34  cmp     rcx, rax
0x14004ff37  jz      short loc_14004FF6D
0x14004ff39  mov     eax, [rcx+2Ch]
0x14004ff3c  test    al, al
0x14004ff3e  jns     short loc_14004FF6D
0x14004ff40  cmp     byte ptr [rcx+29h], 2
0x14004ff44  jb      short loc_14004FF6D
0x14004ff46  mov     rcx, [rcx+18h]
0x14004ff4a  lea     rax, [rdx+0E0h]
0x14004ff51  mov     [r11-40h], rax
0x14004ff55  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004ff5c  mov     edx, 0A4h
0x14004ff61  mov     [r11-48h], rdi
0x14004ff65  mov     r9, rsi
0x14004ff68  call    WPP_SF_qqZ
0x14004ff6d  lea     r12, [rbx+18h]
0x14004ff71  mov     rcx, r12; Resource
0x14004ff74  mov     [rsp+68h+Resource], r12
0x14004ff79  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14004ff80  nop     dword ptr [rax+rax+00h]
0x14004ff85  mov     r8d, 2; InitialContextFlags
0x14004ff8b  mov     rdx, rbp; RxDeviceObject
0x14004ff8e  xor     ecx, ecx; Irp
0x14004ff90  call    RxCreateRxContext
0x14004ff95  mov     r14, rax
0x14004ff98  test    rax, rax
0x14004ff9b  jnz     short loc_14004FFA7
0x14004ff9d  mov     ebx, 0C000009Ah
0x14004ffa2  jmp     loc_1400503AC
0x14004ffa7  mov     word ptr [rax+20h], 0
0x14004ffad  lea     r13, [rdi+0CCh]
0x14004ffb4  mov     [rax+290h], rdi
0x14004ffbb  mov     ebx, 1
0x14004ffc0  mov     [rax+288h], rsi
0x14004ffc7  mov     rax, [rsi+20h]
0x14004ffcb  mov     [r14+280h], rax
0x14004ffd2  cmp     [r13+0], ebx
0x14004ffd6  jnz     short loc_140050025
0x14004ffd8  mov     rcx, r12; Resource
0x14004ffdb  xor     ebx, ebx
0x14004ffdd  call    cs:__imp_ExReleaseResourceLite
0x14004ffe4  nop     dword ptr [rax+rax+00h]
0x14004ffe9  lea     r8, [rdi+168h]; RxContext
0x14004fff0  xor     r9d, r9d; AsyncStatus
0x14004fff3  mov     rdx, r13; TransitionWaitList
0x14004fff6  mov     rcx, r14; Condition
0x14004fff9  call    RxWaitForStableCondition
0x14004fffe  mov     dl, 1; Wait
0x140050000  mov     rcx, r12; Resource
0x140050003  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005000a  nop     dword ptr [rax+rax+00h]
0x14005000f  mov     eax, [rdi+38h]
0x140050012  test    al, 10h
0x140050014  jz      loc_1400503A4
0x14005001a  mov     ebx, [rdi+0D0h]
0x140050020  jmp     loc_1400503A4
0x140050025  mov     edx, 130h
0x14005002a  mov     ecx, 40h ; '@'
0x14005002f  mov     r8d, 6F437852h
0x140050035  call    cs:__imp_ExAllocatePool2
0x14005003c  nop     dword ptr [rax+rax+00h]
0x140050041  mov     r12, rax
0x140050044  test    rax, rax
0x140050047  jnz     short loc_140050053
0x140050049  mov     ebx, 0C000009Ah
0x14005004e  jmp     loc_14005039F
0x140050053  xor     r8d, r8d; State
0x140050056  lea     rcx, [rax+8]; Event
0x14005005a  mov     edx, ebx; Type
0x14005005c  call    cs:__imp_KeInitializeEvent
0x140050063  nop     dword ptr [rax+rax+00h]
0x140050068  mov     [r12+20h], r14
0x14005006d  lea     rax, RxCreateNetRootCallBack
0x140050074  mov     [r12+110h], rax
0x14005007c  mov     [r12+108h], rdi
0x140050084  mov     [r12], rbp
0x140050088  mov     [r13+0], ebx
0x14005008c  test    r15b, r15b
0x14005008f  jnz     loc_140050115
0x140050095  mov     rax, cs:Fcb
0x14005009c  mov     rcx, [rax+160h]
0x1400500a3  mov     rax, [rcx+1C0h]
0x1400500aa  test    rax, rax
0x1400500ad  jnz     short loc_1400500B6
0x1400500af  mov     ebx, 0C0000002h
0x1400500b4  jmp     short loc_1400500C7
0x1400500b6  mov     rdx, rdi
0x1400500b9  mov     rcx, r14
0x1400500bc  call    _guard_dispatch_icall
0x1400500c1  mov     ebx, eax
0x1400500c3  test    eax, eax
0x1400500c5  jns     short loc_140050115
0x1400500c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400500ce  lea     rbp, WPP_GLOBAL_Control
0x1400500d5  cmp     rcx, rbp
0x1400500d8  jz      loc_14005038E
0x1400500de  mov     edx, [rcx+2Ch]
0x1400500e1  test    dl, dl
0x1400500e3  jns     loc_14005038E
0x1400500e9  cmp     byte ptr [rcx+29h], 2
0x1400500ed  jb      loc_14005038E
0x1400500f3  mov     rcx, [rcx+18h]
0x1400500f7  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x1400500fe  mov     edx, 0A5h
0x140050103  mov     [rsp+68h+Timeout], rdi
0x140050108  mov     r9d, ebx
0x14005010b  call    WPP_SF_dq
0x140050110  jmp     loc_14005038E
0x140050115  mov     rcx, [rsp+68h+Resource]; Resource
0x14005011a  call    cs:__imp_ExReleaseResourceLite
0x140050121  nop     dword ptr [rax+rax+00h]
0x140050126  mov     rax, [rbp+160h]
0x14005012d  mov     r15, rbp
0x140050130  mov     rax, [rax+1A0h]
0x140050137  test    rax, rax
0x14005013a  jz      short loc_14005016D
0x14005013c  mov     rcx, r12
0x14005013f  call    _guard_dispatch_icall
0x140050144  cmp     eax, 103h
0x140050149  jnz     short loc_14005016D
0x14005014b  xor     r9d, r9d; Alertable
0x14005014e  mov     [rsp+68h+Timeout], 0; Timeout
0x140050157  xor     r8d, r8d; WaitMode
0x14005015a  lea     rcx, [r12+8]; Object
0x14005015f  xor     edx, edx; WaitReason
0x140050161  call    cs:__imp_KeWaitForSingleObject
0x140050168  nop     dword ptr [rax+rax+00h]
0x14005016d  mov     ebx, [r12+11Ch]
0x140050175  test    ebx, ebx
0x140050177  jnz     short loc_1400501CC
0x140050179  mov     ebx, [r12+118h]
0x140050181  test    ebx, ebx
0x140050183  jnz     short loc_1400501CC
0x140050185  mov     rcx, cs:WPP_GLOBAL_Control
0x14005018c  lea     rbp, WPP_GLOBAL_Control
0x140050193  cmp     rcx, rbp
0x140050196  jz      short loc_1400501C1
0x140050198  mov     eax, [rcx+2Ch]
0x14005019b  test    al, al
0x14005019d  jns     short loc_1400501C1
0x14005019f  cmp     byte ptr [rcx+29h], 4
0x1400501a3  jb      short loc_1400501C1
0x1400501a5  mov     rcx, [rcx+18h]
0x1400501a9  lea     r9, [rsi+0D8h]
0x1400501b0  mov     edx, 0A6h
0x1400501b5  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x1400501bc  call    WPP_SF_Z
0x1400501c1  xor     ebx, ebx
0x1400501c3  lea     rsi, [rdi+38h]
0x1400501c7  jmp     loc_140050253
0x1400501cc  cmp     ebx, 0C0000022h
0x1400501d2  jz      short loc_14005020A
0x1400501d4  cmp     ebx, 0C0000064h
0x1400501da  jz      short loc_14005020A
0x1400501dc  cmp     ebx, 0C000006Ah
0x1400501e2  jz      short loc_14005020A
0x1400501e4  cmp     ebx, 0C000006Dh
0x1400501ea  jz      short loc_14005020A
0x1400501ec  cmp     ebx, 0C0000071h
0x1400501f2  jz      short loc_14005020A
0x1400501f4  cmp     ebx, 0C0000224h
0x1400501fa  jz      short loc_14005020A
0x1400501fc  cmp     ebx, 0C0000388h
0x140050202  jz      short loc_14005020A
0x140050204  lea     rsi, [rdi+38h]
0x140050208  jmp     short loc_140050211
0x14005020a  lea     rsi, [rdi+38h]
0x14005020e  or      dword ptr [rsi], 20h
0x140050211  mov     rcx, cs:WPP_GLOBAL_Control
0x140050218  lea     rbp, WPP_GLOBAL_Control
0x14005021f  cmp     rcx, rbp
0x140050222  jz      short loc_140050253
0x140050224  mov     eax, [rcx+2Ch]
0x140050227  test    al, al
0x140050229  jns     short loc_140050253
0x14005022b  cmp     byte ptr [rcx+29h], 4
0x14005022f  jb      short loc_140050253
0x140050231  mov     eax, [rsi]
0x140050233  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14005023a  mov     rcx, [rcx+18h]
0x14005023e  mov     edx, 0A7h
0x140050243  mov     [rsp+68h+var_40], ebx
0x140050247  mov     r9, rdi
0x14005024a  mov     dword ptr [rsp+68h+Timeout], eax
0x14005024e  call    WPP_SF_qDD
0x140050253  mov     rcx, [rsp+68h+Resource]; Resource
0x140050258  mov     dl, 1; Wait
0x14005025a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140050261  nop     dword ptr [rax+rax+00h]
0x140050266  test    ebx, ebx
0x140050268  js      loc_14005032B
0x14005026e  lea     rdx, [rsp+68h+arg_18]
0x140050276  mov     rcx, rdi
0x140050279  call    RxGetShareRights
0x14005027e  test    al, al
0x140050280  jz      short loc_1400502F4
0x140050282  movzx   eax, word ptr [rsp+68h+arg_18]
0x14005028a  test    eax, eax
0x14005028c  jnz     short loc_1400502F4
0x14005028e  mov     rcx, [rdi+68h]
0x140050292  call    RxIsUserCredentialPresent
0x140050297  test    al, al
0x140050299  jnz     short loc_1400502F4
0x14005029b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400502a2  cmp     rcx, rbp
0x1400502a5  jz      short loc_1400502CC
0x1400502a7  mov     eax, [rcx+2Ch]
0x1400502aa  test    al, al
0x1400502ac  jns     short loc_1400502CC
0x1400502ae  cmp     byte ptr [rcx+29h], 2
0x1400502b2  jb      short loc_1400502CC
0x1400502b4  mov     rcx, [rcx+18h]
0x1400502b8  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x1400502bf  mov     edx, 0A8h
0x1400502c4  mov     r9, rdi
0x1400502c7  call    WPP_SF_q
0x1400502cc  mov     rax, [r15+160h]
0x1400502d3  mov     rax, [rax+1D0h]
0x1400502da  test    rax, rax
0x1400502dd  jz      short loc_1400502E9
0x1400502df  xor     edx, edx
0x1400502e1  mov     rcx, rdi
0x1400502e4  call    _guard_dispatch_icall
0x1400502e9  or      dword ptr [rdi+38h], 20h
0x1400502ed  mov     ebx, 0C000006Dh
0x1400502f2  jmp     short loc_14005032B
0x1400502f4  and     dword ptr [rsi], 0FFFFFFEFh
0x1400502f7  and     dword ptr [rsi], 0FFFFFFDFh
0x1400502fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140050301  cmp     rcx, rbp
0x140050304  jz      short loc_14005032B
0x140050306  mov     eax, [rcx+2Ch]
0x140050309  test    al, al
0x14005030b  jns     short loc_14005032B
0x14005030d  cmp     byte ptr [rcx+29h], 4
0x140050311  jb      short loc_14005032B
0x140050313  mov     rcx, [rcx+18h]
0x140050317  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14005031e  mov     edx, 0A9h
0x140050323  mov     r9, rdi
0x140050326  call    WPP_SF_q
0x14005032b  mov     r9d, [r13+0]
0x14005032f  cmp     r9d, 1
0x140050333  jnz     short loc_140050360
0x140050335  lea     rax, [rdi+168h]
0x14005033c  mov     word ptr [rsp+68h+var_40], 0EB12h
0x140050343  lea     r9, [rdi+0D0h]
0x14005034a  mov     [rsp+68h+Timeout], rax
0x14005034f  mov     r8, r13; TransitionWaitList
0x140050352  mov     edx, ebx; Condition
0x140050354  mov     ecx, 3; NewConditionValue
0x140050359  call    RxUpdateCondition
0x14005035e  jmp     short loc_14005038E
0x140050360  mov     rcx, cs:WPP_GLOBAL_Control
0x140050367  cmp     rcx, rbp
0x14005036a  jz      short loc_14005038E
0x14005036c  mov     eax, [rcx+2Ch]
0x14005036f  test    al, al
0x140050371  jns     short loc_14005038E
0x140050373  cmp     byte ptr [rcx+29h], 2
0x140050377  jb      short loc_14005038E
0x140050379  mov     rcx, [rcx+18h]
0x14005037d  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x140050384  mov     edx, 0AAh
0x140050389  call    WPP_SF_d
0x14005038e  xor     edx, edx; Tag
0x140050390  mov     rcx, r12; P
0x140050393  call    cs:__imp_ExFreePoolWithTag
0x14005039a  nop     dword ptr [rax+rax+00h]
0x14005039f  mov     r12, [rsp+68h+Resource]
0x1400503a4  mov     rcx, r14; RxContext
0x1400503a7  call    RxDereferenceAndDeleteRxContext_Real
0x1400503ac  mov     rcx, r12; Resource
0x1400503af  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400503b6  nop     dword ptr [rax+rax+00h]
0x1400503bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400503c2  lea     rax, WPP_GLOBAL_Control
0x1400503c9  cmp     rcx, rax
0x1400503cc  jz      short loc_1400503F3
0x1400503ce  mov     eax, [rcx+2Ch]
0x1400503d1  test    al, al
  ... truncated ...
```
