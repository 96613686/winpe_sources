# ClasspSetDeviceCommandDurationLimitMappingProperty

- ea: `0x140035764`
- end: `0x140035a62`
- name: `ClasspSetDeviceCommandDurationLimitMappingProperty`
- size: `766`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x14001fc38`
- `0x14002001c`
- `0x140031634`
- `0x1400317b4`
- `0x140035764`
- `0x140037650`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400359f7`
- `ntoskrnl!KeReleaseMutex` at `0x1400359f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400358b0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400358b0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003581c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003581c`

## pseudocode

```c
__int64 __fastcall ClasspSetDeviceCommandDurationLimitMappingProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // r15
  _IRP *MasterIrp; // rbp
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  char v7; // r12
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // eax
  __int64 i; // rdx
  char v12; // cl
  char v13; // cl

  DeviceExtension = DeviceObject->DeviceExtension;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 213, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  v8 = *(_DWORD *)(&MasterIrp->Size + 1);
  if ( v8 == 1 )
    goto LABEL_39;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        214,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v8);
    }
    v9 = -1073741637;
    goto LABEL_40;
  }
  if ( KeGetCurrentIrql() >= 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 215, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
    }
    v9 = -1073741496;
    goto LABEL_40;
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x20 )
  {
    v9 = -1073741789;
    goto LABEL_40;
  }
  if ( LODWORD(MasterIrp->MdlAddress) != 24 || HIDWORD(MasterIrp->MdlAddress) != 24 )
  {
    v9 = -1073741811;
    goto LABEL_40;
  }
  KeWaitForSingleObject((PVOID)(DeviceExtension[143] + 56LL), Executive, 0, 0, 0);
  v7 = 1;
  v10 = ClasspInitializeCommandDurationLimit(DeviceExtension);
  v9 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        216,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v10);
    }
    goto LABEL_40;
  }
  if ( (unsigned __int8)ClasspIsCommandDurationLimitSupported(DeviceExtension) )
  {
    for ( i = 0; i != 7; ++i )
    {
      v12 = *((_BYTE *)&MasterIrp->Flags + i);
      if ( (unsigned __int8)v12 >= 7u )
        v12 = 7;
      *(_BYTE *)(DeviceExtension[143] + i + 114) = v12;
      v13 = *((_BYTE *)&MasterIrp->Flags + i + 7);
      if ( (unsigned __int8)v13 >= 7u )
        v13 = 7;
      *(_BYTE *)(DeviceExtension[143] + i + 286) = v13;
    }
LABEL_39:
    v9 = 0;
    goto LABEL_40;
  }
  v9 = -1073741637;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qdd(
      WPP_GLOBAL_Control->AttachedDevice,
      217,
      *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
      DeviceObject,
      *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
      *(_WORD *)(DeviceExtension[143] + 284LL) & 1);
  }
LABEL_40:
  Irp->IoStatus.Status = v9;
  Irp->IoStatus.Information = 0;
  if ( v7 )
    KeReleaseMutex((PRKMUTEX)(DeviceExtension[143] + 56LL), 0);
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      218,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140035764  push    rbx
0x140035766  push    rbp
0x140035767  push    rsi
0x140035768  push    r12
0x14003576a  push    r14
0x14003576c  push    r15
0x14003576e  sub     rsp, 38h
0x140035772  mov     r15, [rcx+40h]
0x140035776  mov     r14, rdx
0x140035779  mov     rbp, [rdx+18h]
0x14003577d  mov     rsi, rcx
0x140035780  mov     rbx, [rdx+0B8h]
0x140035787  xor     r12b, r12b
0x14003578a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035791  lea     rax, WPP_GLOBAL_Control
0x140035798  cmp     rcx, rax
0x14003579b  jz      short loc_1400357C9
0x14003579d  mov     eax, [rcx+2Ch]
0x1400357a0  test    al, 10h
0x1400357a2  jz      short loc_1400357C2
0x1400357a4  cmp     byte ptr [rcx+29h], 5
0x1400357a8  jb      short loc_1400357C2
0x1400357aa  mov     rcx, [rcx+18h]
0x1400357ae  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400357b5  mov     edx, 0D5h
0x1400357ba  mov     r9, rsi
0x1400357bd  call    WPP_SF_q
0x1400357c2  lea     rax, WPP_GLOBAL_Control
0x1400357c9  mov     r8d, [rbp+4]
0x1400357cd  cmp     r8d, 1
0x1400357d1  jz      loc_1400359D0
0x1400357d7  test    r8d, r8d
0x1400357da  jz      short loc_14003581C
0x1400357dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400357e3  cmp     rcx, rax
0x1400357e6  jz      short loc_140035812
0x1400357e8  mov     eax, [rcx+2Ch]
0x1400357eb  test    al, 10h
0x1400357ed  jz      short loc_140035812
0x1400357ef  cmp     byte ptr [rcx+29h], 2
0x1400357f3  jb      short loc_140035812
0x1400357f5  mov     rcx, [rcx+18h]
0x1400357f9  mov     edx, 0D6h
0x1400357fe  mov     dword ptr [rsp+68h+Timeout], r8d
0x140035803  mov     r9, rsi
0x140035806  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003580d  call    WPP_SF_qD
0x140035812  mov     ebx, 0C00000BBh
0x140035817  jmp     loc_1400359D2
0x14003581c  call    cs:__imp_KeGetCurrentIrql
0x140035823  nop     dword ptr [rax+rax+00h]
0x140035828  cmp     al, 2
0x14003582a  jb      short loc_14003586E
0x14003582c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035833  lea     rbp, WPP_GLOBAL_Control
0x14003583a  cmp     rcx, rbp
0x14003583d  jz      short loc_140035864
0x14003583f  mov     eax, [rcx+2Ch]
0x140035842  test    al, 10h
0x140035844  jz      short loc_140035864
0x140035846  cmp     byte ptr [rcx+29h], 2
0x14003584a  jb      short loc_140035864
0x14003584c  mov     rcx, [rcx+18h]
0x140035850  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140035857  mov     edx, 0D7h
0x14003585c  mov     r9, rsi
0x14003585f  call    WPP_SF_q
0x140035864  mov     ebx, 0C0000148h
0x140035869  jmp     loc_1400359D9
0x14003586e  cmp     dword ptr [rbx+10h], 20h ; ' '
0x140035872  jnb     short loc_14003587E
0x140035874  mov     ebx, 0C0000023h
0x140035879  jmp     loc_1400359D2
0x14003587e  cmp     dword ptr [rbp+8], 18h
0x140035882  jz      short loc_14003588E
0x140035884  mov     ebx, 0C000000Dh
0x140035889  jmp     loc_1400359D2
0x14003588e  cmp     dword ptr [rbp+0Ch], 18h
0x140035892  jnz     short loc_140035884
0x140035894  mov     rcx, [r15+478h]
0x14003589b  xor     r9d, r9d; Alertable
0x14003589e  add     rcx, 38h ; '8'; Object
0x1400358a2  mov     [rsp+68h+Timeout], 0; Timeout
0x1400358ab  xor     r8d, r8d; WaitMode
0x1400358ae  xor     edx, edx; WaitReason
0x1400358b0  call    cs:__imp_KeWaitForSingleObject
0x1400358b7  nop     dword ptr [rax+rax+00h]
0x1400358bc  mov     rcx, r15
0x1400358bf  mov     r12b, 1
0x1400358c2  call    ClasspInitializeCommandDurationLimit
0x1400358c7  mov     ebx, eax
0x1400358c9  test    eax, eax
0x1400358cb  jns     short loc_14003591B
0x1400358cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400358d4  lea     rbp, WPP_GLOBAL_Control
0x1400358db  cmp     rcx, rbp
0x1400358de  jz      loc_1400359D9
0x1400358e4  mov     edx, [rcx+2Ch]
0x1400358e7  test    dl, 10h
0x1400358ea  jz      loc_1400359D9
0x1400358f0  cmp     byte ptr [rcx+29h], 2
0x1400358f4  jb      loc_1400359D9
0x1400358fa  mov     rcx, [rcx+18h]
0x1400358fe  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140035905  mov     edx, 0D8h
0x14003590a  mov     dword ptr [rsp+68h+Timeout], eax
0x14003590e  mov     r9, rsi
0x140035911  call    WPP_SF_qD
0x140035916  jmp     loc_1400359D9
0x14003591b  mov     rcx, r15
0x14003591e  call    ClasspIsCommandDurationLimitSupported
0x140035923  test    al, al
0x140035925  jnz     short loc_140035991
0x140035927  mov     ebx, 0C00000BBh
0x14003592c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035933  lea     rbp, WPP_GLOBAL_Control
0x14003593a  cmp     rcx, rbp
0x14003593d  jz      loc_1400359D9
0x140035943  mov     eax, [rcx+2Ch]
0x140035946  test    al, 10h
0x140035948  jz      loc_1400359D9
0x14003594e  cmp     byte ptr [rcx+29h], 2
0x140035952  jb      loc_1400359D9
0x140035958  mov     rax, [r15+478h]
0x14003595f  mov     edx, 0D9h
0x140035964  mov     rcx, [rcx+18h]
0x140035968  movzx   r9d, word ptr [rax+11Ch]
0x140035970  movzx   r8d, word ptr [rax+70h]
0x140035975  and     r9d, 1
0x140035979  mov     [rsp+68h+var_40], r9d
0x14003597e  and     r8d, 1
0x140035982  mov     r9, rsi
0x140035985  mov     dword ptr [rsp+68h+Timeout], r8d
0x14003598a  call    WPP_SF_qdd
0x14003598f  jmp     short loc_1400359D9
0x140035991  xor     edx, edx
0x140035993  lea     r8d, [rdx+7]
0x140035997  movzx   ecx, byte ptr [rdx+rbp+10h]
0x14003599c  mov     rax, [r15+478h]
0x1400359a3  cmp     cl, r8b
0x1400359a6  cmovnb  ecx, r8d
0x1400359aa  mov     [rax+rdx+72h], cl
0x1400359ae  movzx   ecx, byte ptr [rdx+rbp+17h]
0x1400359b3  mov     rax, [r15+478h]
0x1400359ba  cmp     cl, r8b
0x1400359bd  cmovnb  ecx, r8d
0x1400359c1  mov     [rax+rdx+11Eh], cl
0x1400359c8  inc     rdx
0x1400359cb  cmp     rdx, r8
0x1400359ce  jnz     short loc_140035997
0x1400359d0  xor     ebx, ebx
0x1400359d2  lea     rbp, WPP_GLOBAL_Control
0x1400359d9  mov     [r14+30h], ebx
0x1400359dd  mov     qword ptr [r14+38h], 0
0x1400359e5  test    r12b, r12b
0x1400359e8  jz      short loc_140035A03
0x1400359ea  mov     rcx, [r15+478h]
0x1400359f1  xor     edx, edx; Wait
0x1400359f3  add     rcx, 38h ; '8'; Mutex
0x1400359f7  call    cs:__imp_KeReleaseMutex
0x1400359fe  nop     dword ptr [rax+rax+00h]
0x140035a03  mov     rdx, r14; Tag
0x140035a06  mov     rcx, rsi; DeviceObject
0x140035a09  call    ClassReleaseRemoveLock
0x140035a0e  xor     r8d, r8d; PriorityBoost
0x140035a11  mov     rdx, r14; Irp
0x140035a14  mov     rcx, rsi; DeviceObject
0x140035a17  call    ClassCompleteRequest
0x140035a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035a23  cmp     rcx, rbp
0x140035a26  jz      short loc_140035A51
0x140035a28  mov     eax, [rcx+2Ch]
0x140035a2b  test    al, 10h
0x140035a2d  jz      short loc_140035A51
0x140035a2f  cmp     byte ptr [rcx+29h], 5
0x140035a33  jb      short loc_140035A51
0x140035a35  mov     rcx, [rcx+18h]
0x140035a39  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140035a40  mov     edx, 0DAh
0x140035a45  mov     dword ptr [rsp+68h+Timeout], ebx
0x140035a49  mov     r9, rsi
0x140035a4c  call    WPP_SF_qD
0x140035a51  mov     eax, ebx
0x140035a53  add     rsp, 38h
0x140035a57  pop     r15
0x140035a59  pop     r14
0x140035a5b  pop     r12
0x140035a5d  pop     rsi
0x140035a5e  pop     rbp
0x140035a5f  pop     rbx
0x140035a60  retn
```
