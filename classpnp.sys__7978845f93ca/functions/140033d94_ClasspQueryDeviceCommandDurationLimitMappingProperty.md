# ClasspQueryDeviceCommandDurationLimitMappingProperty

- ea: `0x140033d94`
- end: `0x1400340ae`
- name: `ClasspQueryDeviceCommandDurationLimitMappingProperty`
- size: `794`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
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
- `0x140033d94`
- `0x140037650`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140034041`
- `ntoskrnl!KeReleaseMutex` at `0x140034041`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033ef3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033ef3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033e51`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033e51`

## pseudocode

```c
__int64 __fastcall ClasspQueryDeviceCommandDurationLimitMappingProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // r15
  unsigned int v3; // r12d
  _IRP *MasterIrp; // r14
  char v5; // r13
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int v9; // r8d
  unsigned int v10; // ebx
  size_t Length; // rbx
  int v12; // eax
  __int64 i; // rdx
  char v14; // cl
  char v15; // cl

  DeviceExtension = DeviceObject->DeviceExtension;
  v3 = 0;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  v5 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 184, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  v9 = *(_DWORD *)(&MasterIrp->Size + 1);
  if ( v9 == 1 )
    goto LABEL_39;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        185,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v9);
    }
    v10 = -1073741637;
    goto LABEL_40;
  }
  if ( KeGetCurrentIrql() >= 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
    }
    v10 = -1073741496;
    goto LABEL_40;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (unsigned int)Length < 8 )
  {
    v10 = -1073741789;
    goto LABEL_40;
  }
  memset(MasterIrp, 0, Length);
  *(_DWORD *)&MasterIrp->Type = 24;
  *(_DWORD *)(&MasterIrp->Size + 1) = 24;
  if ( (unsigned int)Length < 0x18 )
  {
    v3 = 8;
LABEL_39:
    v10 = 0;
    goto LABEL_40;
  }
  KeWaitForSingleObject((PVOID)(DeviceExtension[143] + 56LL), Executive, 0, 0, 0);
  v5 = 1;
  v12 = ClasspInitializeCommandDurationLimit(DeviceExtension);
  v10 = v12;
  if ( v12 >= 0 )
  {
    if ( (unsigned __int8)ClasspIsCommandDurationLimitSupported(DeviceExtension) )
    {
      for ( i = 0; i != 7; ++i )
      {
        v14 = *(_BYTE *)(DeviceExtension[143] + i + 114);
        if ( (unsigned __int8)v14 >= 7u )
          v14 = -1;
        *((_BYTE *)&MasterIrp->MdlAddress + i) = v14;
        v15 = *(_BYTE *)(i + DeviceExtension[143] + 286);
        if ( (unsigned __int8)v15 >= 7u )
          v15 = -1;
        *((_BYTE *)&MasterIrp->MdlAddress + i + 7) = v15;
      }
      v3 = *(_DWORD *)(&MasterIrp->Size + 1);
      goto LABEL_39;
    }
    v10 = -1073741637;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qdd(
        WPP_GLOBAL_Control->AttachedDevice,
        188,
        *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
        DeviceObject,
        *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
        *(_WORD *)(DeviceExtension[143] + 284LL) & 1);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      187,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      v12);
  }
LABEL_40:
  Irp->IoStatus.Information = v3;
  Irp->IoStatus.Status = v10;
  if ( v5 )
    KeReleaseMutex((PRKMUTEX)(DeviceExtension[143] + 56LL), 0);
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      189,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x140033d94  push    rbx
0x140033d96  push    rbp
0x140033d97  push    rdi
0x140033d98  push    r12
0x140033d9a  push    r13
0x140033d9c  push    r14
0x140033d9e  push    r15
0x140033da0  sub     rsp, 30h
0x140033da4  mov     r15, [rcx+40h]
0x140033da8  xor     r12d, r12d
0x140033dab  mov     r14, [rdx+18h]
0x140033daf  xor     r13b, r13b
0x140033db2  mov     rbx, [rdx+0B8h]
0x140033db9  mov     rbp, rdx
0x140033dbc  mov     rdi, rcx
0x140033dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140033dc6  lea     rax, WPP_GLOBAL_Control
0x140033dcd  cmp     rcx, rax
0x140033dd0  jz      short loc_140033DFE
0x140033dd2  mov     eax, [rcx+2Ch]
0x140033dd5  test    al, 10h
0x140033dd7  jz      short loc_140033DF7
0x140033dd9  cmp     byte ptr [rcx+29h], 5
0x140033ddd  jb      short loc_140033DF7
0x140033ddf  mov     rcx, [rcx+18h]
0x140033de3  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033dea  mov     edx, 0B8h
0x140033def  mov     r9, rdi
0x140033df2  call    WPP_SF_q
0x140033df7  lea     rax, WPP_GLOBAL_Control
0x140033dfe  mov     r8d, [r14+4]
0x140033e02  cmp     r8d, 1
0x140033e06  jz      loc_14003401C
0x140033e0c  test    r8d, r8d
0x140033e0f  jz      short loc_140033E51
0x140033e11  mov     rcx, cs:WPP_GLOBAL_Control
0x140033e18  cmp     rcx, rax
0x140033e1b  jz      short loc_140033E47
0x140033e1d  mov     eax, [rcx+2Ch]
0x140033e20  test    al, 10h
0x140033e22  jz      short loc_140033E47
0x140033e24  cmp     byte ptr [rcx+29h], 2
0x140033e28  jb      short loc_140033E47
0x140033e2a  mov     rcx, [rcx+18h]
0x140033e2e  mov     edx, 0B9h
0x140033e33  mov     dword ptr [rsp+68h+Timeout], r8d
0x140033e38  mov     r9, rdi
0x140033e3b  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033e42  call    WPP_SF_qD
0x140033e47  mov     ebx, 0C00000BBh
0x140033e4c  jmp     loc_14003401E
0x140033e51  call    cs:__imp_KeGetCurrentIrql
0x140033e58  nop     dword ptr [rax+rax+00h]
0x140033e5d  cmp     al, 2
0x140033e5f  jb      short loc_140033EA3
0x140033e61  mov     rcx, cs:WPP_GLOBAL_Control
0x140033e68  lea     r14, WPP_GLOBAL_Control
0x140033e6f  cmp     rcx, r14
0x140033e72  jz      short loc_140033E99
0x140033e74  mov     eax, [rcx+2Ch]
0x140033e77  test    al, 10h
0x140033e79  jz      short loc_140033E99
0x140033e7b  cmp     byte ptr [rcx+29h], 2
0x140033e7f  jb      short loc_140033E99
0x140033e81  mov     rcx, [rcx+18h]
0x140033e85  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033e8c  mov     edx, 0BAh
0x140033e91  mov     r9, rdi
0x140033e94  call    WPP_SF_q
0x140033e99  mov     ebx, 0C0000148h
0x140033e9e  jmp     loc_140034025
0x140033ea3  mov     ebx, [rbx+8]
0x140033ea6  cmp     ebx, 8
0x140033ea9  jnb     short loc_140033EB5
0x140033eab  mov     ebx, 0C0000023h
0x140033eb0  jmp     loc_14003401E
0x140033eb5  mov     r8, rbx; Size
0x140033eb8  xor     edx, edx; Val
0x140033eba  mov     rcx, r14; void *
0x140033ebd  call    memset
0x140033ec2  mov     eax, 18h
0x140033ec7  mov     [r14], eax
0x140033eca  mov     [r14+4], eax
0x140033ece  cmp     ebx, eax
0x140033ed0  jnb     short loc_140033EDB
0x140033ed2  lea     r12d, [rax-10h]
0x140033ed6  jmp     loc_14003401C
0x140033edb  mov     rcx, [r15+478h]
0x140033ee2  xor     r9d, r9d; Alertable
0x140033ee5  add     rcx, 38h ; '8'; Object
0x140033ee9  mov     [rsp+68h+Timeout], r12; Timeout
0x140033eee  xor     r8d, r8d; WaitMode
0x140033ef1  xor     edx, edx; WaitReason
0x140033ef3  call    cs:__imp_KeWaitForSingleObject
0x140033efa  nop     dword ptr [rax+rax+00h]
0x140033eff  mov     rcx, r15
0x140033f02  mov     r13b, 1
0x140033f05  call    ClasspInitializeCommandDurationLimit
0x140033f0a  mov     ebx, eax
0x140033f0c  test    eax, eax
0x140033f0e  jns     short loc_140033F5E
0x140033f10  mov     rcx, cs:WPP_GLOBAL_Control
0x140033f17  lea     r14, WPP_GLOBAL_Control
0x140033f1e  cmp     rcx, r14
0x140033f21  jz      loc_140034025
0x140033f27  mov     edx, [rcx+2Ch]
0x140033f2a  test    dl, 10h
0x140033f2d  jz      loc_140034025
0x140033f33  cmp     byte ptr [rcx+29h], 2
0x140033f37  jb      loc_140034025
0x140033f3d  mov     rcx, [rcx+18h]
0x140033f41  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033f48  mov     edx, 0BBh
0x140033f4d  mov     dword ptr [rsp+68h+Timeout], eax
0x140033f51  mov     r9, rdi
0x140033f54  call    WPP_SF_qD
0x140033f59  jmp     loc_140034025
0x140033f5e  mov     rcx, r15
0x140033f61  call    ClasspIsCommandDurationLimitSupported
0x140033f66  test    al, al
0x140033f68  jnz     short loc_140033FD4
0x140033f6a  mov     ebx, 0C00000BBh
0x140033f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033f76  lea     r14, WPP_GLOBAL_Control
0x140033f7d  cmp     rcx, r14
0x140033f80  jz      loc_140034025
0x140033f86  mov     eax, [rcx+2Ch]
0x140033f89  test    al, 10h
0x140033f8b  jz      loc_140034025
0x140033f91  cmp     byte ptr [rcx+29h], 2
0x140033f95  jb      loc_140034025
0x140033f9b  mov     rax, [r15+478h]
0x140033fa2  mov     edx, 0BCh
0x140033fa7  mov     rcx, [rcx+18h]
0x140033fab  movzx   r9d, word ptr [rax+11Ch]
0x140033fb3  movzx   r8d, word ptr [rax+70h]
0x140033fb8  and     r9d, 1
0x140033fbc  mov     [rsp+68h+var_40], r9d
0x140033fc1  and     r8d, 1
0x140033fc5  mov     r9, rdi
0x140033fc8  mov     dword ptr [rsp+68h+Timeout], r8d
0x140033fcd  call    WPP_SF_qdd
0x140033fd2  jmp     short loc_140034025
0x140033fd4  xor     edx, edx
0x140033fd6  mov     r8d, 0FFh
0x140033fdc  mov     rax, [r15+478h]
0x140033fe3  movzx   ecx, byte ptr [rax+rdx+72h]
0x140033fe8  cmp     cl, 7
0x140033feb  cmovnb  ecx, r8d
0x140033fef  mov     [r14+rdx+8], cl
0x140033ff4  mov     rax, [r15+478h]
0x140033ffb  movzx   ecx, byte ptr [rdx+rax+11Eh]
0x140034003  cmp     cl, 7
0x140034006  cmovnb  ecx, r8d
0x14003400a  mov     [r14+rdx+0Fh], cl
0x14003400f  inc     rdx
0x140034012  cmp     rdx, 7
0x140034016  jnz     short loc_140033FDC
0x140034018  mov     r12d, [r14+4]
0x14003401c  xor     ebx, ebx
0x14003401e  lea     r14, WPP_GLOBAL_Control
0x140034025  mov     eax, r12d
0x140034028  mov     [rbp+38h], rax
0x14003402c  mov     [rbp+30h], ebx
0x14003402f  test    r13b, r13b
0x140034032  jz      short loc_14003404D
0x140034034  mov     rcx, [r15+478h]
0x14003403b  xor     edx, edx; Wait
0x14003403d  add     rcx, 38h ; '8'; Mutex
0x140034041  call    cs:__imp_KeReleaseMutex
0x140034048  nop     dword ptr [rax+rax+00h]
0x14003404d  mov     rdx, rbp; Tag
0x140034050  mov     rcx, rdi; DeviceObject
0x140034053  call    ClassReleaseRemoveLock
0x140034058  xor     r8d, r8d; PriorityBoost
0x14003405b  mov     rdx, rbp; Irp
0x14003405e  mov     rcx, rdi; DeviceObject
0x140034061  call    ClassCompleteRequest
0x140034066  mov     rcx, cs:WPP_GLOBAL_Control
0x14003406d  cmp     rcx, r14
0x140034070  jz      short loc_14003409B
0x140034072  mov     eax, [rcx+2Ch]
0x140034075  test    al, 10h
0x140034077  jz      short loc_14003409B
0x140034079  cmp     byte ptr [rcx+29h], 5
0x14003407d  jb      short loc_14003409B
0x14003407f  mov     rcx, [rcx+18h]
0x140034083  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003408a  mov     edx, 0BDh
0x14003408f  mov     dword ptr [rsp+68h+Timeout], ebx
0x140034093  mov     r9, rdi
0x140034096  call    WPP_SF_qD
0x14003409b  mov     eax, ebx
0x14003409d  add     rsp, 30h
0x1400340a1  pop     r15
0x1400340a3  pop     r14
0x1400340a5  pop     r13
0x1400340a7  pop     r12
0x1400340a9  pop     rdi
0x1400340aa  pop     rbp
0x1400340ab  pop     rbx
0x1400340ac  retn
```
