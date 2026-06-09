# KsDispatchSetSecurity

- ea: `0x180037b70`
- end: `0x180037c76`
- name: `KsDispatchSetSecurity`
- size: `262`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180037b70`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180037ba1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180037ba1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037bb4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037bb4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037c36`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037c36`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037c42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037c42`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180037bd8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180037bd8`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x180037bff`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x180037bff`
- `ntoskrnl!IofCompleteRequest` at `0x180037c56`
- `ntoskrnl!IofCompleteRequest` at `0x180037c56`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037c16`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037c16`

## pseudocode

```c
NTSTATUS __stdcall KsDispatchSetSecurity(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  __int64 v4; // r14
  __int64 v5; // r12
  void *v6; // r13
  PUNICODE_STRING FileName; // rdi
  __int64 v8; // rbx
  PFILE_OBJECT FileObject; // rsi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  int v11; // ebx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = *(_QWORD *)CurrentStackLocation->FileObject->FsContext;
  v5 = *(_QWORD *)CurrentStackLocation->DeviceObject->DeviceExtension;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v5 + 16), 1u);
  v6 = *(void **)(*(_QWORD *)(v4 + 24) + 32LL);
  if ( v6 )
  {
    FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
    v8 = *(_QWORD *)(v4 + 24);
    FileObject = CurrentStackLocation->FileObject;
    GenericMapping = IoGetFileObjectGenericMapping();
    v11 = SeSetSecurityDescriptorInfo(
            FileObject,
            (PSECURITY_INFORMATION)&CurrentStackLocation->Parameters,
            FileName,
            (PSECURITY_DESCRIPTOR *)(v8 + 32),
            NonPagedPoolNx,
            GenericMapping);
    if ( v11 >= 0 )
    {
      ExFreePoolWithTag(v6, 0);
      *(_DWORD *)(*(_QWORD *)(v4 + 24) + 40LL) |= 1u;
    }
  }
  else
  {
    v11 = -1073741609;
  }
  ExReleaseResourceLite((PERESOURCE)(v5 + 16));
  KeLeaveCriticalRegion();
  Irp->IoStatus.Status = v11;
  IofCompleteRequest(Irp, 0);
  return v11;
}

```

## disassembly

```asm
0x180037b70  push    rbx
0x180037b72  push    rbp
0x180037b73  push    rsi
0x180037b74  push    rdi
0x180037b75  push    r12
0x180037b77  push    r13
0x180037b79  push    r14
0x180037b7b  push    r15
0x180037b7d  sub     rsp, 38h
0x180037b81  mov     r15, [rdx+0B8h]
0x180037b88  mov     rbp, rdx
0x180037b8b  mov     rax, [r15+30h]
0x180037b8f  mov     rcx, [rax+18h]
0x180037b93  mov     rax, [r15+28h]
0x180037b97  mov     r14, [rcx]
0x180037b9a  mov     rcx, [rax+40h]
0x180037b9e  mov     r12, [rcx]
0x180037ba1  call    cs:__imp_KeEnterCriticalRegion
0x180037ba8  nop     dword ptr [rax+rax+00h]
0x180037bad  mov     dl, 1; Wait
0x180037baf  lea     rcx, [r12+10h]; Resource
0x180037bb4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180037bbb  nop     dword ptr [rax+rax+00h]
0x180037bc0  mov     rax, [r14+18h]
0x180037bc4  mov     r13, [rax+20h]
0x180037bc8  test    r13, r13
0x180037bcb  jz      short loc_180037C2C
0x180037bcd  mov     rdi, [r15+10h]
0x180037bd1  mov     rbx, rax
0x180037bd4  mov     rsi, [r15+30h]
0x180037bd8  call    cs:__imp_IoGetFileObjectGenericMapping
0x180037bdf  nop     dword ptr [rax+rax+00h]
0x180037be4  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x180037be9  lea     rdx, [r15+8]; SecurityInformation
0x180037bed  mov     r8, rdi; ModificationDescriptor
0x180037bf0  mov     [rsp+78h+PoolType], 200h; PoolType
0x180037bf8  lea     r9, [rbx+20h]; ObjectsSecurityDescriptor
0x180037bfc  mov     rcx, rsi; Object
0x180037bff  call    cs:__imp_SeSetSecurityDescriptorInfo
0x180037c06  nop     dword ptr [rax+rax+00h]
0x180037c0b  mov     ebx, eax
0x180037c0d  test    eax, eax
0x180037c0f  js      short loc_180037C31
0x180037c11  xor     edx, edx; Tag
0x180037c13  mov     rcx, r13; P
0x180037c16  call    cs:__imp_ExFreePoolWithTag
0x180037c1d  nop     dword ptr [rax+rax+00h]
0x180037c22  mov     rcx, [r14+18h]
0x180037c26  or      dword ptr [rcx+28h], 1
0x180037c2a  jmp     short loc_180037C31
0x180037c2c  mov     ebx, 0C00000D7h
0x180037c31  lea     rcx, [r12+10h]; Resource
0x180037c36  call    cs:__imp_ExReleaseResourceLite
0x180037c3d  nop     dword ptr [rax+rax+00h]
0x180037c42  call    cs:__imp_KeLeaveCriticalRegion
0x180037c49  nop     dword ptr [rax+rax+00h]
0x180037c4e  xor     edx, edx; PriorityBoost
0x180037c50  mov     [rbp+30h], ebx
0x180037c53  mov     rcx, rbp; Irp
0x180037c56  call    cs:__imp_IofCompleteRequest
0x180037c5d  nop     dword ptr [rax+rax+00h]
0x180037c62  mov     eax, ebx
0x180037c64  add     rsp, 38h
0x180037c68  pop     r15
0x180037c6a  pop     r14
0x180037c6c  pop     r13
0x180037c6e  pop     r12
0x180037c70  pop     rdi
0x180037c71  pop     rsi
0x180037c72  pop     rbp
0x180037c73  pop     rbx
0x180037c74  retn
```
