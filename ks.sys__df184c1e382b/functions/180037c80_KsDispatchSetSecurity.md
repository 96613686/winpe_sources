# KsDispatchSetSecurity

- ea: `0x180037c80`
- end: `0x180037d86`
- name: `KsDispatchSetSecurity`
- size: `262`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180037c80`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180037ce8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180037ce8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180037cb1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180037cb1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037cc4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180037cc4`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037d46`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037d46`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037d52`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037d52`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x180037d0f`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x180037d0f`
- `ntoskrnl!IofCompleteRequest` at `0x180037d66`
- `ntoskrnl!IofCompleteRequest` at `0x180037d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037d26`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037d26`

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
0x180037c80  push    rbx
0x180037c82  push    rbp
0x180037c83  push    rsi
0x180037c84  push    rdi
0x180037c85  push    r12
0x180037c87  push    r13
0x180037c89  push    r14
0x180037c8b  push    r15
0x180037c8d  sub     rsp, 38h
0x180037c91  mov     r15, [rdx+0B8h]
0x180037c98  mov     rbp, rdx
0x180037c9b  mov     rax, [r15+30h]
0x180037c9f  mov     rcx, [rax+18h]
0x180037ca3  mov     rax, [r15+28h]
0x180037ca7  mov     r14, [rcx]
0x180037caa  mov     rcx, [rax+40h]
0x180037cae  mov     r12, [rcx]
0x180037cb1  call    cs:__imp_KeEnterCriticalRegion
0x180037cb8  nop     dword ptr [rax+rax+00h]
0x180037cbd  mov     dl, 1; Wait
0x180037cbf  lea     rcx, [r12+10h]; Resource
0x180037cc4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180037ccb  nop     dword ptr [rax+rax+00h]
0x180037cd0  mov     rax, [r14+18h]
0x180037cd4  mov     r13, [rax+20h]
0x180037cd8  test    r13, r13
0x180037cdb  jz      short loc_180037D3C
0x180037cdd  mov     rdi, [r15+10h]
0x180037ce1  mov     rbx, rax
0x180037ce4  mov     rsi, [r15+30h]
0x180037ce8  call    cs:__imp_IoGetFileObjectGenericMapping
0x180037cef  nop     dword ptr [rax+rax+00h]
0x180037cf4  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x180037cf9  lea     rdx, [r15+8]; SecurityInformation
0x180037cfd  mov     r8, rdi; ModificationDescriptor
0x180037d00  mov     [rsp+78h+PoolType], 200h; PoolType
0x180037d08  lea     r9, [rbx+20h]; ObjectsSecurityDescriptor
0x180037d0c  mov     rcx, rsi; Object
0x180037d0f  call    cs:__imp_SeSetSecurityDescriptorInfo
0x180037d16  nop     dword ptr [rax+rax+00h]
0x180037d1b  mov     ebx, eax
0x180037d1d  test    eax, eax
0x180037d1f  js      short loc_180037D41
0x180037d21  xor     edx, edx; Tag
0x180037d23  mov     rcx, r13; P
0x180037d26  call    cs:__imp_ExFreePoolWithTag
0x180037d2d  nop     dword ptr [rax+rax+00h]
0x180037d32  mov     rcx, [r14+18h]
0x180037d36  or      dword ptr [rcx+28h], 1
0x180037d3a  jmp     short loc_180037D41
0x180037d3c  mov     ebx, 0C00000D7h
0x180037d41  lea     rcx, [r12+10h]; Resource
0x180037d46  call    cs:__imp_ExReleaseResourceLite
0x180037d4d  nop     dword ptr [rax+rax+00h]
0x180037d52  call    cs:__imp_KeLeaveCriticalRegion
0x180037d59  nop     dword ptr [rax+rax+00h]
0x180037d5e  xor     edx, edx; PriorityBoost
0x180037d60  mov     [rbp+30h], ebx
0x180037d63  mov     rcx, rbp; Irp
0x180037d66  call    cs:__imp_IofCompleteRequest
0x180037d6d  nop     dword ptr [rax+rax+00h]
0x180037d72  mov     eax, ebx
0x180037d74  add     rsp, 38h
0x180037d78  pop     r15
0x180037d7a  pop     r14
0x180037d7c  pop     r13
0x180037d7e  pop     r12
0x180037d80  pop     rdi
0x180037d81  pop     rsi
0x180037d82  pop     rbp
0x180037d83  pop     rbx
0x180037d84  retn
```
