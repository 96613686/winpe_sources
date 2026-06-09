# CdpServerSetSecurity

- ea: `0x140009270`
- end: `0x1400093a2`
- name: `CdpServerSetSecurity`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140009270`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000932d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000932d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400092b1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400092b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000936c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000936c`
- `ntoskrnl!IofCompleteRequest` at `0x140009388`
- `ntoskrnl!IofCompleteRequest` at `0x140009388`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400092c3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400092c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009360`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009360`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140009346`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140009346`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140009319`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140009319`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1400092f9`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1400092f9`

## pseudocode

```c
__int64 __fastcall CdpServerSetSecurity(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  NTSTATUS v5; // ebx
  DWORD SecurityInformation; // [rsp+60h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+68h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR ModificationDescriptor; // [rsp+70h] [rbp+40h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  ModificationDescriptor = 0;
  SecurityInformation = 0;
  ObjectsSecurityDescriptor = 0;
  SecurityInformation = CurrentStackLocation->Parameters.Read.Length;
  ModificationDescriptor = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 40, 0);
  ObjectsSecurityDescriptor = *(PSECURITY_DESCRIPTOR *)(a1 + 56);
  v5 = SeSetSecurityDescriptorInfo(
         0,
         &SecurityInformation,
         ModificationDescriptor,
         &ObjectsSecurityDescriptor,
         PagedPool,
         &CdpGenericMapping);
  if ( v5 >= 0 )
  {
    v5 = ObLogSecurityDescriptor(ObjectsSecurityDescriptor, &ModificationDescriptor, 1);
    ExFreePoolWithTag(ObjectsSecurityDescriptor, 0);
    if ( v5 >= 0 )
    {
      ObDereferenceSecurityDescriptor(*(_QWORD *)(a1 + 56), 1);
      *(_QWORD *)(a1 + 56) = ModificationDescriptor;
    }
  }
  ExReleasePushLockExclusiveEx(a1 + 40, 0);
  KeLeaveCriticalRegion();
  a2->IoStatus.Status = v5;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140009270  push    rbp
0x140009272  push    rbx
0x140009273  push    rsi
0x140009274  push    rdi
0x140009275  push    r14
0x140009277  mov     rbp, rsp
0x14000927a  sub     rsp, 30h
0x14000927e  mov     r8, [rdx+0B8h]
0x140009285  mov     rdi, rdx
0x140009288  mov     [rbp+ModificationDescriptor], 0
0x140009290  mov     rsi, rcx
0x140009293  mov     [rbp+SecurityInformation], 0
0x14000929a  mov     [rbp+ObjectsSecurityDescriptor], 0
0x1400092a2  mov     eax, [r8+8]
0x1400092a6  mov     [rbp+SecurityInformation], eax
0x1400092a9  mov     rax, [r8+10h]
0x1400092ad  mov     [rbp+ModificationDescriptor], rax
0x1400092b1  call    cs:__imp_KeEnterCriticalRegion
0x1400092b8  nop     dword ptr [rax+rax+00h]
0x1400092bd  xor     edx, edx
0x1400092bf  lea     rcx, [rsi+28h]
0x1400092c3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400092ca  nop     dword ptr [rax+rax+00h]
0x1400092cf  mov     rax, [rsi+38h]
0x1400092d3  lea     r9, [rbp+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1400092d7  mov     r8, [rbp+ModificationDescriptor]; ModificationDescriptor
0x1400092db  lea     rdx, [rbp+SecurityInformation]; SecurityInformation
0x1400092df  mov     [rbp+ObjectsSecurityDescriptor], rax
0x1400092e3  xor     ecx, ecx; Object
0x1400092e5  lea     rax, CdpGenericMapping
0x1400092ec  mov     [rsp+30h+GenericMapping], rax; GenericMapping
0x1400092f1  mov     [rsp+30h+PoolType], 1; PoolType
0x1400092f9  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140009300  nop     dword ptr [rax+rax+00h]
0x140009305  mov     ebx, eax
0x140009307  test    eax, eax
0x140009309  js      short loc_14000935A
0x14000930b  mov     rcx, [rbp+ObjectsSecurityDescriptor]
0x14000930f  lea     rdx, [rbp+ModificationDescriptor]
0x140009313  mov     r8d, 1
0x140009319  call    cs:__imp_ObLogSecurityDescriptor
0x140009320  nop     dword ptr [rax+rax+00h]
0x140009325  mov     rcx, [rbp+ObjectsSecurityDescriptor]; P
0x140009329  xor     edx, edx; Tag
0x14000932b  mov     ebx, eax
0x14000932d  call    cs:__imp_ExFreePoolWithTag
0x140009334  nop     dword ptr [rax+rax+00h]
0x140009339  test    ebx, ebx
0x14000933b  js      short loc_14000935A
0x14000933d  mov     rcx, [rsi+38h]
0x140009341  mov     edx, 1
0x140009346  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000934d  nop     dword ptr [rax+rax+00h]
0x140009352  mov     rax, [rbp+ModificationDescriptor]
0x140009356  mov     [rsi+38h], rax
0x14000935a  xor     edx, edx
0x14000935c  lea     rcx, [rsi+28h]
0x140009360  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140009367  nop     dword ptr [rax+rax+00h]
0x14000936c  call    cs:__imp_KeLeaveCriticalRegion
0x140009373  nop     dword ptr [rax+rax+00h]
0x140009378  xor     edx, edx; PriorityBoost
0x14000937a  mov     [rdi+30h], ebx
0x14000937d  mov     rcx, rdi; Irp
0x140009380  mov     qword ptr [rdi+38h], 0
0x140009388  call    cs:__imp_IofCompleteRequest
0x14000938f  nop     dword ptr [rax+rax+00h]
0x140009394  mov     eax, ebx
0x140009396  add     rsp, 30h
0x14000939a  pop     r14
0x14000939c  pop     rdi
0x14000939d  pop     rsi
0x14000939e  pop     rbx
0x14000939f  pop     rbp
0x1400093a0  retn
```
