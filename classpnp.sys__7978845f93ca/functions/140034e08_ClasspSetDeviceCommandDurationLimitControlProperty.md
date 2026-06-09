# ClasspSetDeviceCommandDurationLimitControlProperty

- ea: `0x140034e08`
- end: `0x140035121`
- name: `ClasspSetDeviceCommandDurationLimitControlProperty`
- size: `793`
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
- `0x140034e08`
- `0x140037650`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400350b6`
- `ntoskrnl!KeReleaseMutex` at `0x1400350b6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140034f56`
- `ntoskrnl!KeWaitForSingleObject` at `0x140034f56`
- `ntoskrnl!KeGetCurrentIrql` at `0x140034ec0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140034ec0`

## pseudocode

```c
__int64 __fastcall ClasspSetDeviceCommandDurationLimitControlProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // r15
  _IRP *MasterIrp; // r14
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  char v7; // r12
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // eax

  DeviceExtension = DeviceObject->DeviceExtension;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 219, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  v8 = *(_DWORD *)(&MasterIrp->Size + 1);
  if ( v8 == 1 )
    goto LABEL_34;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        220,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v8);
    }
    v9 = -1073741637;
    goto LABEL_35;
  }
  if ( KeGetCurrentIrql() >= 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 221, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
    }
    v9 = -1073741496;
    goto LABEL_35;
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x14 )
  {
    v9 = -1073741789;
    goto LABEL_35;
  }
  if ( LODWORD(MasterIrp->MdlAddress) != 12 || HIDWORD(MasterIrp->MdlAddress) < 0xC )
  {
    v9 = -1073741811;
    goto LABEL_35;
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
        222,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v10);
    }
    goto LABEL_35;
  }
  if ( (unsigned __int8)ClasspIsCommandDurationLimitSupported(DeviceExtension) )
  {
    *(_WORD *)(DeviceExtension[143] + 112LL) = *(_WORD *)(DeviceExtension[143] + 112LL) & 0xFFFB
                                             | (4 * (MasterIrp->Flags & 1));
    *(_WORD *)(DeviceExtension[143] + 284LL) = *(_WORD *)(DeviceExtension[143] + 284LL) & 0xFFFB
                                             | (4 * (MasterIrp->Flags & 1));
LABEL_34:
    v9 = 0;
    goto LABEL_35;
  }
  v9 = -1073741637;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qdd(
      WPP_GLOBAL_Control->AttachedDevice,
      223,
      *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
      DeviceObject,
      *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
      *(_WORD *)(DeviceExtension[143] + 284LL) & 1);
  }
LABEL_35:
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
      224,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140034e08  push    rbx
0x140034e0a  push    rbp
0x140034e0b  push    rdi
0x140034e0c  push    r12
0x140034e0e  push    r14
0x140034e10  push    r15
0x140034e12  sub     rsp, 38h
0x140034e16  mov     r15, [rcx+40h]
0x140034e1a  mov     rbp, rdx
0x140034e1d  mov     r14, [rdx+18h]
0x140034e21  mov     rdi, rcx
0x140034e24  mov     rbx, [rdx+0B8h]
0x140034e2b  xor     r12b, r12b
0x140034e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e35  lea     rax, WPP_GLOBAL_Control
0x140034e3c  cmp     rcx, rax
0x140034e3f  jz      short loc_140034E6D
0x140034e41  mov     eax, [rcx+2Ch]
0x140034e44  test    al, 10h
0x140034e46  jz      short loc_140034E66
0x140034e48  cmp     byte ptr [rcx+29h], 5
0x140034e4c  jb      short loc_140034E66
0x140034e4e  mov     rcx, [rcx+18h]
0x140034e52  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034e59  mov     edx, 0DBh
0x140034e5e  mov     r9, rdi
0x140034e61  call    WPP_SF_q
0x140034e66  lea     rax, WPP_GLOBAL_Control
0x140034e6d  mov     r8d, [r14+4]
0x140034e71  cmp     r8d, 1
0x140034e75  jz      loc_140035090
0x140034e7b  test    r8d, r8d
0x140034e7e  jz      short loc_140034EC0
0x140034e80  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e87  cmp     rcx, rax
0x140034e8a  jz      short loc_140034EB6
0x140034e8c  mov     eax, [rcx+2Ch]
0x140034e8f  test    al, 10h
0x140034e91  jz      short loc_140034EB6
0x140034e93  cmp     byte ptr [rcx+29h], 2
0x140034e97  jb      short loc_140034EB6
0x140034e99  mov     rcx, [rcx+18h]
0x140034e9d  mov     edx, 0DCh
0x140034ea2  mov     dword ptr [rsp+68h+Timeout], r8d
0x140034ea7  mov     r9, rdi
0x140034eaa  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034eb1  call    WPP_SF_qD
0x140034eb6  mov     ebx, 0C00000BBh
0x140034ebb  jmp     loc_140035092
0x140034ec0  call    cs:__imp_KeGetCurrentIrql
0x140034ec7  nop     dword ptr [rax+rax+00h]
0x140034ecc  cmp     al, 2
0x140034ece  jb      short loc_140034F12
0x140034ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ed7  lea     r14, WPP_GLOBAL_Control
0x140034ede  cmp     rcx, r14
0x140034ee1  jz      short loc_140034F08
0x140034ee3  mov     eax, [rcx+2Ch]
0x140034ee6  test    al, 10h
0x140034ee8  jz      short loc_140034F08
0x140034eea  cmp     byte ptr [rcx+29h], 2
0x140034eee  jb      short loc_140034F08
0x140034ef0  mov     rcx, [rcx+18h]
0x140034ef4  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034efb  mov     edx, 0DDh
0x140034f00  mov     r9, rdi
0x140034f03  call    WPP_SF_q
0x140034f08  mov     ebx, 0C0000148h
0x140034f0d  jmp     loc_140035099
0x140034f12  cmp     dword ptr [rbx+10h], 14h
0x140034f16  jnb     short loc_140034F22
0x140034f18  mov     ebx, 0C0000023h
0x140034f1d  jmp     loc_140035092
0x140034f22  cmp     dword ptr [r14+8], 0Ch
0x140034f27  jz      short loc_140034F33
0x140034f29  mov     ebx, 0C000000Dh
0x140034f2e  jmp     loc_140035092
0x140034f33  cmp     dword ptr [r14+0Ch], 0Ch
0x140034f38  jb      short loc_140034F29
0x140034f3a  mov     rcx, [r15+478h]
0x140034f41  xor     r9d, r9d; Alertable
0x140034f44  add     rcx, 38h ; '8'; Object
0x140034f48  mov     [rsp+68h+Timeout], 0; Timeout
0x140034f51  xor     r8d, r8d; WaitMode
0x140034f54  xor     edx, edx; WaitReason
0x140034f56  call    cs:__imp_KeWaitForSingleObject
0x140034f5d  nop     dword ptr [rax+rax+00h]
0x140034f62  mov     rcx, r15
0x140034f65  mov     r12b, 1
0x140034f68  call    ClasspInitializeCommandDurationLimit
0x140034f6d  mov     ebx, eax
0x140034f6f  test    eax, eax
0x140034f71  jns     short loc_140034FC1
0x140034f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f7a  lea     r14, WPP_GLOBAL_Control
0x140034f81  cmp     rcx, r14
0x140034f84  jz      loc_140035099
0x140034f8a  mov     edx, [rcx+2Ch]
0x140034f8d  test    dl, 10h
0x140034f90  jz      loc_140035099
0x140034f96  cmp     byte ptr [rcx+29h], 2
0x140034f9a  jb      loc_140035099
0x140034fa0  mov     rcx, [rcx+18h]
0x140034fa4  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034fab  mov     edx, 0DEh
0x140034fb0  mov     dword ptr [rsp+68h+Timeout], eax
0x140034fb4  mov     r9, rdi
0x140034fb7  call    WPP_SF_qD
0x140034fbc  jmp     loc_140035099
0x140034fc1  mov     rcx, r15
0x140034fc4  call    ClasspIsCommandDurationLimitSupported
0x140034fc9  test    al, al
0x140034fcb  jnz     short loc_14003503A
0x140034fcd  mov     ebx, 0C00000BBh
0x140034fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140034fd9  lea     r14, WPP_GLOBAL_Control
0x140034fe0  cmp     rcx, r14
0x140034fe3  jz      loc_140035099
0x140034fe9  mov     eax, [rcx+2Ch]
0x140034fec  test    al, 10h
0x140034fee  jz      loc_140035099
0x140034ff4  cmp     byte ptr [rcx+29h], 2
0x140034ff8  jb      loc_140035099
0x140034ffe  mov     rax, [r15+478h]
0x140035005  mov     edx, 1
0x14003500a  mov     rcx, [rcx+18h]
0x14003500e  movzx   r9d, word ptr [rax+11Ch]
0x140035016  movzx   r8d, word ptr [rax+70h]
0x14003501b  and     r9d, edx
0x14003501e  mov     [rsp+68h+var_40], r9d
0x140035023  and     r8d, edx
0x140035026  mov     r9, rdi
0x140035029  mov     dword ptr [rsp+68h+Timeout], r8d
0x14003502e  mov     edx, 0DFh
0x140035033  call    WPP_SF_qdd
0x140035038  jmp     short loc_140035099
0x14003503a  mov     rdx, [r15+478h]
0x140035041  mov     r9d, 1
0x140035047  mov     ecx, [r14+10h]
0x14003504b  mov     r8d, 0FFFBh
0x140035051  and     cx, r9w
0x140035055  shl     cx, 2
0x140035059  movzx   eax, word ptr [rdx+70h]
0x14003505d  and     ax, r8w
0x140035061  or      cx, ax
0x140035064  mov     [rdx+70h], cx
0x140035068  mov     rdx, [r15+478h]
0x14003506f  mov     ecx, [r14+10h]
0x140035073  and     cx, r9w
0x140035077  shl     cx, 2
0x14003507b  movzx   eax, word ptr [rdx+11Ch]
0x140035082  and     ax, r8w
0x140035086  or      cx, ax
0x140035089  mov     [rdx+11Ch], cx
0x140035090  xor     ebx, ebx
0x140035092  lea     r14, WPP_GLOBAL_Control
0x140035099  mov     [rbp+30h], ebx
0x14003509c  mov     qword ptr [rbp+38h], 0
0x1400350a4  test    r12b, r12b
0x1400350a7  jz      short loc_1400350C2
0x1400350a9  mov     rcx, [r15+478h]
0x1400350b0  xor     edx, edx; Wait
0x1400350b2  add     rcx, 38h ; '8'; Mutex
0x1400350b6  call    cs:__imp_KeReleaseMutex
0x1400350bd  nop     dword ptr [rax+rax+00h]
0x1400350c2  mov     rdx, rbp; Tag
0x1400350c5  mov     rcx, rdi; DeviceObject
0x1400350c8  call    ClassReleaseRemoveLock
0x1400350cd  xor     r8d, r8d; PriorityBoost
0x1400350d0  mov     rdx, rbp; Irp
0x1400350d3  mov     rcx, rdi; DeviceObject
0x1400350d6  call    ClassCompleteRequest
0x1400350db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400350e2  cmp     rcx, r14
0x1400350e5  jz      short loc_140035110
0x1400350e7  mov     eax, [rcx+2Ch]
0x1400350ea  test    al, 10h
0x1400350ec  jz      short loc_140035110
0x1400350ee  cmp     byte ptr [rcx+29h], 5
0x1400350f2  jb      short loc_140035110
0x1400350f4  mov     rcx, [rcx+18h]
0x1400350f8  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400350ff  mov     edx, 0E0h
0x140035104  mov     dword ptr [rsp+68h+Timeout], ebx
0x140035108  mov     r9, rdi
0x14003510b  call    WPP_SF_qD
0x140035110  mov     eax, ebx
0x140035112  add     rsp, 38h
0x140035116  pop     r15
0x140035118  pop     r14
0x14003511a  pop     r12
0x14003511c  pop     rdi
0x14003511d  pop     rbp
0x14003511e  pop     rbx
0x14003511f  retn
```
