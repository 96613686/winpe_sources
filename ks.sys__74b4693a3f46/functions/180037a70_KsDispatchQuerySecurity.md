# KsDispatchQuerySecurity

- ea: `0x180037a70`
- end: `0x180037b5f`
- name: `KsDispatchQuerySecurity`
- size: `239`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180037a70`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180037aa2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180037aa2`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037b1d`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037b1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037b29`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037b29`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037ab4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037ab4`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x180037ae2`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x180037ae2`
- `ntoskrnl!IofCompleteRequest` at `0x180037b3d`
- `ntoskrnl!IofCompleteRequest` at `0x180037b3d`

## pseudocode

```c
NTSTATUS __stdcall KsDispatchQuerySecurity(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 v4; // rdi
  __int64 v5; // r14
  PSECURITY_DESCRIPTOR *v6; // r9
  PVOID UserBuffer; // rdx
  NTSTATUS v8; // eax
  NTSTATUS v9; // ebx
  ULONG Length; // [rsp+48h] [rbp+10h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = *(_QWORD *)CurrentStackLocation->FileObject->FsContext;
  v5 = *(_QWORD *)CurrentStackLocation->DeviceObject->DeviceExtension;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(v5 + 16), 1u);
  v6 = (PSECURITY_DESCRIPTOR *)(*(_QWORD *)(v4 + 24) + 32LL);
  if ( *v6 )
  {
    UserBuffer = Irp->UserBuffer;
    Length = CurrentStackLocation->Parameters.Create.Options;
    v8 = SeQuerySecurityDescriptorInfo(
           (PSECURITY_INFORMATION)&CurrentStackLocation->Parameters,
           UserBuffer,
           &Length,
           v6);
    v9 = v8;
    if ( v8 == -1073741789 )
    {
      v9 = -2147483643;
      Irp->IoStatus.Information = Length;
    }
    else if ( v8 >= 0 )
    {
      Irp->IoStatus.Information = Length;
    }
  }
  else
  {
    v9 = -1073741609;
  }
  ExReleaseResourceLite((PERESOURCE)(v5 + 16));
  KeLeaveCriticalRegion();
  Irp->IoStatus.Status = v9;
  IofCompleteRequest(Irp, 0);
  return v9;
}

```

## disassembly

```asm
0x180037a70  mov     [rsp+arg_0], rbx
0x180037a75  mov     [rsp+arg_10], rbp
0x180037a7a  push    rsi
0x180037a7b  push    rdi
0x180037a7c  push    r14
0x180037a7e  sub     rsp, 20h
0x180037a82  mov     rbp, [rdx+0B8h]
0x180037a89  mov     rsi, rdx
0x180037a8c  mov     rax, [rbp+30h]
0x180037a90  mov     rcx, [rax+18h]
0x180037a94  mov     rax, [rbp+28h]
0x180037a98  mov     rdi, [rcx]
0x180037a9b  mov     rcx, [rax+40h]
0x180037a9f  mov     r14, [rcx]
0x180037aa2  call    cs:__imp_KeEnterCriticalRegion
0x180037aa9  nop     dword ptr [rax+rax+00h]
0x180037aae  mov     dl, 1; Wait
0x180037ab0  lea     rcx, [r14+10h]; Resource
0x180037ab4  call    cs:__imp_ExAcquireResourceSharedLite
0x180037abb  nop     dword ptr [rax+rax+00h]
0x180037ac0  mov     r9, [rdi+18h]
0x180037ac4  add     r9, 20h ; ' '; ObjectsSecurityDescriptor
0x180037ac8  cmp     qword ptr [r9], 0
0x180037acc  jz      short loc_180037B14
0x180037ace  mov     eax, [rbp+10h]
0x180037ad1  lea     rcx, [rbp+8]; SecurityInformation
0x180037ad5  mov     rdx, [rsi+70h]; SecurityDescriptor
0x180037ad9  lea     r8, [rsp+38h+Length]; Length
0x180037ade  mov     [rsp+38h+Length], eax
0x180037ae2  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x180037ae9  nop     dword ptr [rax+rax+00h]
0x180037aee  mov     ebx, eax
0x180037af0  cmp     eax, 0C0000023h
0x180037af5  jnz     short loc_180037B06
0x180037af7  mov     eax, [rsp+38h+Length]
0x180037afb  mov     ebx, 80000005h
0x180037b00  mov     [rsi+38h], rax
0x180037b04  jmp     short loc_180037B19
0x180037b06  test    eax, eax
0x180037b08  js      short loc_180037B19
0x180037b0a  mov     eax, [rsp+38h+Length]
0x180037b0e  mov     [rsi+38h], rax
0x180037b12  jmp     short loc_180037B19
0x180037b14  mov     ebx, 0C00000D7h
0x180037b19  lea     rcx, [r14+10h]; Resource
0x180037b1d  call    cs:__imp_ExReleaseResourceLite
0x180037b24  nop     dword ptr [rax+rax+00h]
0x180037b29  call    cs:__imp_KeLeaveCriticalRegion
0x180037b30  nop     dword ptr [rax+rax+00h]
0x180037b35  xor     edx, edx; PriorityBoost
0x180037b37  mov     [rsi+30h], ebx
0x180037b3a  mov     rcx, rsi; Irp
0x180037b3d  call    cs:__imp_IofCompleteRequest
0x180037b44  nop     dword ptr [rax+rax+00h]
0x180037b49  mov     rbp, [rsp+38h+arg_10]
0x180037b4e  mov     eax, ebx
0x180037b50  mov     rbx, [rsp+38h+arg_0]
0x180037b55  add     rsp, 20h
0x180037b59  pop     r14
0x180037b5b  pop     rdi
0x180037b5c  pop     rsi
0x180037b5d  retn
```
