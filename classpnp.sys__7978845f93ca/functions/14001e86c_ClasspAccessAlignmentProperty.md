# ClasspAccessAlignmentProperty

- ea: `0x14001e86c`
- end: `0x14001ecad`
- name: `ClasspAccessAlignmentProperty`
- size: `1089`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x1400018a0`
- `0x140005190`
- `0x1400134a0`
- `0x140017010`
- `0x1400175e0`
- `0x14001e86c`
- `0x140020258`
- `0x140031868`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001e9c4`
- `ntoskrnl!KeReleaseMutex` at `0x14001eaaa`
- `ntoskrnl!KeReleaseMutex` at `0x14001e9c4`
- `ntoskrnl!KeReleaseMutex` at `0x14001eaaa`
- `ntoskrnl!IofCallDriver` at `0x14001ec79`
- `ntoskrnl!IofCallDriver` at `0x14001ec79`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e995`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ea7b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e995`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ea7b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e8fd`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e8fd`

## pseudocode

```c
NTSTATUS __fastcall ClasspAccessAlignmentProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  struct _COMMON_DEVICE_EXTENSION *DeviceExtension; // rdi
  unsigned int Information; // r14d
  _PHYSICAL_DEVICE_EXTENSION *ChildList; // rcx
  __int64 v8; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int v10; // ecx
  size_t Length; // r12
  _IRP *MasterIrp; // r15
  int PartitionZeroExtension; // edx
  int v14; // edx
  _PHYSICAL_DEVICE_EXTENSION *v15; // rcx
  __int64 v16; // r8
  _IRP *v17; // rdx
  int v18; // r8d
  int v19; // r9d
  _PHYSICAL_DEVICE_EXTENSION *v20; // rcx
  _LARGE_INTEGER PartitionLength; // rax
  __int64 v23; // [rsp+30h] [rbp-79h] BYREF
  int v24; // [rsp+38h] [rbp-71h] BYREF
  unsigned int IsRemoved; // [rsp+3Ch] [rbp-6Dh] BYREF
  int v26; // [rsp+40h] [rbp-69h] BYREF
  __int64 v27[14]; // [rsp+50h] [rbp-59h] BYREF

  DeviceExtension = (struct _COMMON_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  Information = 0;
  v23 = a3;
  ChildList = DeviceExtension[2].ChildList;
  if ( BYTE4(ChildList->CommonExtension.DriverExtension) )
    goto LABEL_2;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( DeviceObject->DeviceType == 7
    && (DeviceObject->Characteristics & 4) == 0
    && LODWORD(ChildList->CommonExtension.PartitionZeroExtension) != 1 )
  {
    v10 = *(_DWORD *)(&Irp->AssociatedIrp.MasterIrp->Size + 1);
    if ( v10 != 1 )
    {
      if ( v10 )
      {
LABEL_2:
        LODWORD(v8) = -1073741637;
LABEL_40:
        Irp->IoStatus.Information = Information;
        Irp->IoStatus.Status = v8;
        ClassReleaseRemoveLock(DeviceObject, Irp);
        ClassCompleteRequest(DeviceObject, Irp, 0);
        return v8;
      }
      if ( KeGetCurrentIrql() >= 2u )
      {
        LODWORD(v8) = -1073741496;
        goto LABEL_40;
      }
      Length = CurrentStackLocation->Parameters.Read.Length;
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      if ( (unsigned int)Length >= 0x1C )
      {
        LODWORD(v8) = -1073741823;
        PartitionZeroExtension = (int)DeviceExtension[2].ChildList->CommonExtension.PartitionZeroExtension;
        if ( PartitionZeroExtension )
        {
          v14 = PartitionZeroExtension - 1;
          if ( v14 )
          {
            if ( v14 == 1 )
            {
              if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
                KeWaitForSingleObject(DeviceExtension[2].DeviceName.Buffer, Executive, 0, 0, 0);
              LODWORD(v8) = ClassReadCapacity16(DeviceExtension, v23);
              if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
                KeReleaseMutex((PRKMUTEX)DeviceExtension[2].DeviceName.Buffer, 0);
              if ( (int)v8 >= 0 )
              {
                memset(MasterIrp, 0, Length);
                *(_DWORD *)&MasterIrp->Type = 28;
                Information = 28;
                *(_DWORD *)(&MasterIrp->Size + 1) = 28;
                MasterIrp->Flags = *((_DWORD *)&DeviceExtension[2].ChildList->CommonExtension + 26);
                *(&MasterIrp->Flags + 1) = DeviceExtension[2].ChildList->CommonExtension.IsRemoved;
                MasterIrp->AssociatedIrp.IrpCount = *(_DWORD *)&DeviceExtension[2].ChildList->CommonExtension.DeviceName.Length;
              }
            }
          }
          else
          {
            LODWORD(v8) = -1073741595;
          }
        }
        else
        {
          v8 = (unsigned int)ClassForwardIrpSynchronous(DeviceExtension, Irp);
          if ( (unsigned __int8)ClasspLowerLayerNotSupport(v8) )
          {
            if ( (unsigned __int8)ClasspIsObsoletePortDriver(DeviceExtension) )
            {
              HIDWORD(DeviceExtension[2].ChildList->CommonExtension.DriverData) = v8;
            }
            else
            {
              if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
                KeWaitForSingleObject(DeviceExtension[2].DeviceName.Buffer, Executive, 0, 0, 0);
              LODWORD(v8) = ClassReadCapacity16(DeviceExtension, v23);
              if ( (unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
                KeReleaseMutex((PRKMUTEX)DeviceExtension[2].DeviceName.Buffer, 0);
            }
            LODWORD(DeviceExtension[2].ChildList->CommonExtension.PartitionZeroExtension) = 2;
            if ( (int)v8 >= 0 )
            {
              memset(MasterIrp, 0, Length);
              *(_DWORD *)&MasterIrp->Type = 28;
              Information = 28;
              *(_DWORD *)(&MasterIrp->Size + 1) = 28;
              MasterIrp->Flags = *((_DWORD *)&DeviceExtension[2].ChildList->CommonExtension + 26);
              *(&MasterIrp->Flags + 1) = DeviceExtension[2].ChildList->CommonExtension.IsRemoved;
              v15 = (_PHYSICAL_DEVICE_EXTENSION *)*(unsigned int *)&DeviceExtension[2].ChildList->CommonExtension.DeviceName.Length;
              MasterIrp->AssociatedIrp.IrpCount = (int)v15;
            }
          }
          else
          {
            LODWORD(DeviceExtension[2].ChildList->CommonExtension.PartitionZeroExtension) = 1;
            Information = Irp->IoStatus.Information;
            if ( (int)v8 >= 0 && Irp->IoStatus.Information >= 0x1C )
            {
              v17 = Irp->AssociatedIrp.MasterIrp;
              *((_DWORD *)&DeviceExtension[2].ChildList->CommonExtension + 26) = v17->Flags;
              DeviceExtension[2].ChildList->CommonExtension.IsRemoved = *(&v17->Flags + 1);
              v15 = DeviceExtension[2].ChildList;
              *(_DWORD *)&v15->CommonExtension.DeviceName.Length = v17->AssociatedIrp.IrpCount;
            }
          }
          if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v15, 0x400000000000LL, v16) )
          {
            v20 = DeviceExtension[2].ChildList;
            PartitionLength = DeviceExtension[2].PartitionLength;
            v27[5] = 16;
            v27[4] = PartitionLength.QuadPart + 4;
            v24 = *((_DWORD *)&v20->CommonExtension + 26);
            v27[6] = (__int64)&v24;
            v27[7] = 4;
            IsRemoved = v20->CommonExtension.IsRemoved;
            v27[8] = (__int64)&IsRemoved;
            v27[9] = 4;
            v26 = *(_DWORD *)&v20->CommonExtension.DeviceName.Length;
            v27[10] = (__int64)&v26;
            LODWORD(v23) = HIDWORD(DeviceExtension[1].RemoveEvent.Header.WaitListHead.Flink);
            v27[12] = (__int64)&v23;
            v27[11] = 4;
            v27[13] = 4;
            tlgWriteTransfer_EtwWriteTransfer((int)v20, (int)&byte_140048CFB, v18, v19, 7u, (__int64)v27);
          }
        }
        goto LABEL_40;
      }
      if ( (unsigned int)Length < 8 )
      {
        LODWORD(v8) = -1073741789;
        goto LABEL_40;
      }
      Information = 8;
      *(_DWORD *)&MasterIrp->Type = 28;
      *(_DWORD *)(&MasterIrp->Size + 1) = 28;
    }
    LODWORD(v8) = 0;
    goto LABEL_40;
  }
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  ClassReleaseRemoveLock(DeviceObject, Irp);
  return IofCallDriver(DeviceExtension->LowerDeviceObject, Irp);
}

```

## disassembly

```asm
0x14001e86c  mov     [rsp-8+arg_18], rbx
0x14001e871  push    rbp
0x14001e872  push    rsi
0x14001e873  push    rdi
0x14001e874  push    r12
0x14001e876  push    r13
0x14001e878  push    r14
0x14001e87a  push    r15
0x14001e87c  lea     rbp, [rsp-27h]
0x14001e881  sub     rsp, 0D0h
0x14001e888  mov     rax, cs:__security_cookie
0x14001e88f  xor     rax, rsp
0x14001e892  mov     [rbp+57h+var_40], rax
0x14001e896  mov     rdi, [rcx+40h]
0x14001e89a  mov     r13, rcx
0x14001e89d  xor     r14d, r14d
0x14001e8a0  mov     [rbp+57h+var_D0], r8
0x14001e8a4  mov     rsi, rdx
0x14001e8a7  mov     rcx, [rdi+480h]
0x14001e8ae  cmp     [rcx+24h], r14b
0x14001e8b2  jz      short loc_14001E8BE
0x14001e8b4  mov     ebx, 0C00000BBh
0x14001e8b9  jmp     loc_14001EC1E
0x14001e8be  cmp     dword ptr [r13+48h], 7
0x14001e8c3  mov     rbx, [rdx+0B8h]
0x14001e8ca  jnz     loc_14001EC45
0x14001e8d0  mov     eax, [r13+34h]
0x14001e8d4  test    al, 4
0x14001e8d6  jnz     loc_14001EC45
0x14001e8dc  cmp     dword ptr [rcx+18h], 1
0x14001e8e0  jz      loc_14001EC45
0x14001e8e6  mov     rax, [rdx+18h]
0x14001e8ea  mov     ecx, [rax+4]
0x14001e8ed  cmp     ecx, 1
0x14001e8f0  jnz     short loc_14001E8F9
0x14001e8f2  xor     ebx, ebx
0x14001e8f4  jmp     loc_14001EC1E
0x14001e8f9  test    ecx, ecx
0x14001e8fb  jnz     short loc_14001E8B4
0x14001e8fd  call    cs:__imp_KeGetCurrentIrql
0x14001e904  nop     dword ptr [rax+rax+00h]
0x14001e909  cmp     al, 2
0x14001e90b  jb      short loc_14001E917
0x14001e90d  mov     ebx, 0C0000148h
0x14001e912  jmp     loc_14001EC1E
0x14001e917  mov     r12d, [rbx+8]
0x14001e91b  mov     r15, [rsi+18h]
0x14001e91f  cmp     r12d, 1Ch
0x14001e923  jnb     short loc_14001E94C
0x14001e925  cmp     r12d, 8
0x14001e929  jb      short loc_14001E942
0x14001e92b  mov     r14d, 8
0x14001e931  mov     dword ptr [r15], 1Ch
0x14001e938  mov     dword ptr [r15+4], 1Ch
0x14001e940  jmp     short loc_14001E8F2
0x14001e942  mov     ebx, 0C0000023h
0x14001e947  jmp     loc_14001EC1E
0x14001e94c  mov     rcx, [rdi+480h]
0x14001e953  mov     ebx, 0C0000001h
0x14001e958  mov     edx, [rcx+18h]
0x14001e95b  test    edx, edx
0x14001e95d  jz      loc_14001EA33
0x14001e963  sub     edx, 1
0x14001e966  jz      loc_14001EA29
0x14001e96c  cmp     edx, 1
0x14001e96f  jnz     loc_14001EC1E
0x14001e975  mov     rcx, r13
0x14001e978  call    ClasspIsManagedZonedDevice
0x14001e97d  test    al, al
0x14001e97f  jz      short loc_14001E9A1
0x14001e981  mov     rcx, [rdi+478h]; Object
0x14001e988  xor     r9d, r9d; Alertable
0x14001e98b  xor     r8d, r8d; WaitMode
0x14001e98e  mov     [rsp+100h+Timeout], r14; Timeout
0x14001e993  xor     edx, edx; WaitReason
0x14001e995  call    cs:__imp_KeWaitForSingleObject
0x14001e99c  nop     dword ptr [rax+rax+00h]
0x14001e9a1  mov     rdx, [rbp+57h+var_D0]
0x14001e9a5  mov     rcx, rdi
0x14001e9a8  call    ClassReadCapacity16
0x14001e9ad  mov     rcx, r13
0x14001e9b0  mov     ebx, eax
0x14001e9b2  call    ClasspIsManagedZonedDevice
0x14001e9b7  test    al, al
0x14001e9b9  jz      short loc_14001E9D0
0x14001e9bb  mov     rcx, [rdi+478h]; Mutex
0x14001e9c2  xor     edx, edx; Wait
0x14001e9c4  call    cs:__imp_KeReleaseMutex
0x14001e9cb  nop     dword ptr [rax+rax+00h]
0x14001e9d0  test    ebx, ebx
0x14001e9d2  js      loc_14001EC1E
0x14001e9d8  mov     r8, r12; Size
0x14001e9db  xor     edx, edx; Val
0x14001e9dd  mov     rcx, r15; void *
0x14001e9e0  call    memset
0x14001e9e5  mov     dword ptr [r15], 1Ch
0x14001e9ec  mov     r14d, 1Ch
0x14001e9f2  mov     dword ptr [r15+4], 1Ch
0x14001e9fa  mov     rax, [rdi+480h]
0x14001ea01  mov     ecx, [rax+68h]
0x14001ea04  mov     [r15+10h], ecx
0x14001ea08  mov     rax, [rdi+480h]
0x14001ea0f  mov     ecx, [rax+6Ch]
0x14001ea12  mov     [r15+14h], ecx
0x14001ea16  mov     rax, [rdi+480h]
0x14001ea1d  mov     ecx, [rax+70h]
0x14001ea20  mov     [r15+18h], ecx
0x14001ea24  jmp     loc_14001EC1E
0x14001ea29  mov     ebx, 0C00000E5h
0x14001ea2e  jmp     loc_14001EC1E
0x14001ea33  mov     rdx, rsi; Irp
0x14001ea36  mov     rcx, rdi; CommonExtension
0x14001ea39  call    ClassForwardIrpSynchronous
0x14001ea3e  mov     ecx, eax
0x14001ea40  mov     ebx, eax
0x14001ea42  call    ClasspLowerLayerNotSupport
0x14001ea47  test    al, al
0x14001ea49  jz      loc_14001EB26
0x14001ea4f  mov     rcx, rdi
0x14001ea52  call    ClasspIsObsoletePortDriver
0x14001ea57  test    al, al
0x14001ea59  jnz     short loc_14001EAB8
0x14001ea5b  mov     rcx, r13
0x14001ea5e  call    ClasspIsManagedZonedDevice
0x14001ea63  test    al, al
0x14001ea65  jz      short loc_14001EA87
0x14001ea67  mov     rcx, [rdi+478h]; Object
0x14001ea6e  xor     r9d, r9d; Alertable
0x14001ea71  xor     r8d, r8d; WaitMode
0x14001ea74  mov     [rsp+100h+Timeout], r14; Timeout
0x14001ea79  xor     edx, edx; WaitReason
0x14001ea7b  call    cs:__imp_KeWaitForSingleObject
0x14001ea82  nop     dword ptr [rax+rax+00h]
0x14001ea87  mov     rdx, [rbp+57h+var_D0]
0x14001ea8b  mov     rcx, rdi
0x14001ea8e  call    ClassReadCapacity16
0x14001ea93  mov     rcx, r13
0x14001ea96  mov     ebx, eax
0x14001ea98  call    ClasspIsManagedZonedDevice
0x14001ea9d  test    al, al
0x14001ea9f  jz      short loc_14001EAC2
0x14001eaa1  mov     rcx, [rdi+478h]; Mutex
0x14001eaa8  xor     edx, edx; Wait
0x14001eaaa  call    cs:__imp_KeReleaseMutex
0x14001eab1  nop     dword ptr [rax+rax+00h]
0x14001eab6  jmp     short loc_14001EAC2
0x14001eab8  mov     rax, [rdi+480h]
0x14001eabf  mov     [rax+64h], ebx
0x14001eac2  mov     rax, [rdi+480h]
0x14001eac9  mov     dword ptr [rax+18h], 2
0x14001ead0  test    ebx, ebx
0x14001ead2  js      loc_14001EB6E
0x14001ead8  mov     r8, r12; Size
0x14001eadb  xor     edx, edx; Val
0x14001eadd  mov     rcx, r15; void *
0x14001eae0  call    memset
0x14001eae5  mov     dword ptr [r15], 1Ch
0x14001eaec  mov     r14d, 1Ch
0x14001eaf2  mov     dword ptr [r15+4], 1Ch
0x14001eafa  mov     rax, [rdi+480h]
0x14001eb01  mov     ecx, [rax+68h]
0x14001eb04  mov     [r15+10h], ecx
0x14001eb08  mov     rax, [rdi+480h]
0x14001eb0f  mov     ecx, [rax+6Ch]
0x14001eb12  mov     [r15+14h], ecx
0x14001eb16  mov     rax, [rdi+480h]
0x14001eb1d  mov     ecx, [rax+70h]
0x14001eb20  mov     [r15+18h], ecx
0x14001eb24  jmp     short loc_14001EB6E
0x14001eb26  mov     rax, [rdi+480h]
0x14001eb2d  mov     dword ptr [rax+18h], 1
0x14001eb34  mov     r14d, [rsi+38h]
0x14001eb38  test    ebx, ebx
0x14001eb3a  js      short loc_14001EB6E
0x14001eb3c  cmp     qword ptr [rsi+38h], 1Ch
0x14001eb41  jb      short loc_14001EB6E
0x14001eb43  mov     rdx, [rsi+18h]
0x14001eb47  mov     rcx, [rdi+480h]
0x14001eb4e  mov     eax, [rdx+10h]
0x14001eb51  mov     [rcx+68h], eax
0x14001eb54  mov     rcx, [rdi+480h]
0x14001eb5b  mov     eax, [rdx+14h]
0x14001eb5e  mov     [rcx+6Ch], eax
0x14001eb61  mov     rcx, [rdi+480h]
0x14001eb68  mov     eax, [rdx+18h]
0x14001eb6b  mov     [rcx+70h], eax
0x14001eb6e  mov     eax, cs:dword_14004D060
0x14001eb74  cmp     eax, 5
0x14001eb77  jbe     loc_14001EC1E
0x14001eb7d  mov     rdx, 400000000000h
0x14001eb87  call    _tlgKeywordOn
0x14001eb8c  test    al, al
0x14001eb8e  jz      loc_14001EC1E
0x14001eb94  mov     rcx, [rdi+480h]; int
0x14001eb9b  mov     edx, 4
0x14001eba0  mov     rax, [rdi+490h]
0x14001eba7  add     rax, rdx
0x14001ebaa  mov     [rbp+57h+var_88], 10h
0x14001ebb2  mov     [rbp+57h+var_90], rax
0x14001ebb6  mov     eax, [rcx+68h]
0x14001ebb9  mov     [rbp+57h+var_C8], eax
0x14001ebbc  lea     rax, [rbp+57h+var_C8]
0x14001ebc0  mov     [rbp+57h+var_80], rax
0x14001ebc4  mov     [rbp+57h+var_78], rdx
0x14001ebc8  mov     eax, [rcx+6Ch]
0x14001ebcb  mov     [rbp+57h+var_C4], eax
0x14001ebce  lea     rax, [rbp+57h+var_C4]
0x14001ebd2  mov     [rbp+57h+var_70], rax
0x14001ebd6  mov     [rbp+57h+var_68], rdx
0x14001ebda  mov     eax, [rcx+70h]
0x14001ebdd  mov     [rbp+57h+var_C0], eax
0x14001ebe0  lea     rax, [rbp+57h+var_C0]
0x14001ebe4  mov     [rbp+57h+var_60], rax
0x14001ebe8  mov     eax, [rdi+23Ch]
0x14001ebee  mov     dword ptr [rbp+57h+var_D0], eax
0x14001ebf1  lea     rax, [rbp+57h+var_D0]
0x14001ebf5  mov     [rbp+57h+var_50], rax
0x14001ebf9  lea     rax, [rbp+57h+var_B0]
0x14001ebfd  mov     [rbp+57h+var_58], rdx
0x14001ec01  mov     [rbp+57h+var_48], rdx
0x14001ec05  lea     rdx, byte_140048CFB; int
0x14001ec0c  mov     [rsp+100h+var_D8], rax; __int64
0x14001ec11  mov     dword ptr [rsp+100h+Timeout], 7; ULONG
0x14001ec19  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001ec1e  mov     eax, r14d
0x14001ec21  mov     rdx, rsi; Tag
0x14001ec24  mov     rcx, r13; DeviceObject
0x14001ec27  mov     [rsi+38h], rax
0x14001ec2b  mov     [rsi+30h], ebx
0x14001ec2e  call    ClassReleaseRemoveLock
0x14001ec33  xor     r8d, r8d; PriorityBoost
0x14001ec36  mov     rdx, rsi; Irp
0x14001ec39  mov     rcx, r13; DeviceObject
0x14001ec3c  call    ClassCompleteRequest
0x14001ec41  mov     eax, ebx
0x14001ec43  jmp     short loc_14001EC85
0x14001ec45  movups  xmm0, xmmword ptr [rbx]
0x14001ec48  mov     rcx, r13; DeviceObject
0x14001ec4b  movups  xmmword ptr [rbx-48h], xmm0
0x14001ec4f  movups  xmm1, xmmword ptr [rbx+10h]
0x14001ec53  movups  xmmword ptr [rbx-38h], xmm1
0x14001ec57  movups  xmm0, xmmword ptr [rbx+20h]
0x14001ec5b  movups  xmmword ptr [rbx-28h], xmm0
0x14001ec5f  movsd   xmm1, qword ptr [rbx+30h]
0x14001ec64  movsd   qword ptr [rbx-18h], xmm1
0x14001ec69  mov     [rbx-45h], r14b
0x14001ec6d  call    ClassReleaseRemoveLock
0x14001ec72  mov     rcx, [rdi+10h]; DeviceObject
0x14001ec76  mov     rdx, rsi; Irp
0x14001ec79  call    cs:__imp_IofCallDriver
0x14001ec80  nop     dword ptr [rax+rax+00h]
0x14001ec85  mov     rcx, [rbp+57h+var_40]
0x14001ec89  xor     rcx, rsp; StackCookie
0x14001ec8c  call    __security_check_cookie
0x14001ec91  mov     rbx, [rsp+100h+arg_18]
0x14001ec99  add     rsp, 0D0h
0x14001eca0  pop     r15
0x14001eca2  pop     r14
0x14001eca4  pop     r13
0x14001eca6  pop     r12
0x14001eca8  pop     rdi
0x14001eca9  pop     rsi
0x14001ecaa  pop     rbp
0x14001ecab  retn
```
