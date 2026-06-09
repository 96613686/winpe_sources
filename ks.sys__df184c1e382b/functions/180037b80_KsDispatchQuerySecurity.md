# KsDispatchQuerySecurity

- ea: `0x180037b80`
- end: `0x180037c6f`
- name: `KsDispatchQuerySecurity`
- size: `239`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180037b80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180037bb2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180037bb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037c2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x180037c2d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037c39`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180037c39`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037bc4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180037bc4`
- `ntoskrnl!IofCompleteRequest` at `0x180037c4d`
- `ntoskrnl!IofCompleteRequest` at `0x180037c4d`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x180037bf2`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x180037bf2`

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
0x180037b80  mov     [rsp+arg_0], rbx
0x180037b85  mov     [rsp+arg_10], rbp
0x180037b8a  push    rsi
0x180037b8b  push    rdi
0x180037b8c  push    r14
0x180037b8e  sub     rsp, 20h
0x180037b92  mov     rbp, [rdx+0B8h]
0x180037b99  mov     rsi, rdx
0x180037b9c  mov     rax, [rbp+30h]
0x180037ba0  mov     rcx, [rax+18h]
0x180037ba4  mov     rax, [rbp+28h]
0x180037ba8  mov     rdi, [rcx]
0x180037bab  mov     rcx, [rax+40h]
0x180037baf  mov     r14, [rcx]
0x180037bb2  call    cs:__imp_KeEnterCriticalRegion
0x180037bb9  nop     dword ptr [rax+rax+00h]
0x180037bbe  mov     dl, 1; Wait
0x180037bc0  lea     rcx, [r14+10h]; Resource
0x180037bc4  call    cs:__imp_ExAcquireResourceSharedLite
0x180037bcb  nop     dword ptr [rax+rax+00h]
0x180037bd0  mov     r9, [rdi+18h]
0x180037bd4  add     r9, 20h ; ' '; ObjectsSecurityDescriptor
0x180037bd8  cmp     qword ptr [r9], 0
0x180037bdc  jz      short loc_180037C24
0x180037bde  mov     eax, [rbp+10h]
0x180037be1  lea     rcx, [rbp+8]; SecurityInformation
0x180037be5  mov     rdx, [rsi+70h]; SecurityDescriptor
0x180037be9  lea     r8, [rsp+38h+Length]; Length
0x180037bee  mov     [rsp+38h+Length], eax
0x180037bf2  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x180037bf9  nop     dword ptr [rax+rax+00h]
0x180037bfe  mov     ebx, eax
0x180037c00  cmp     eax, 0C0000023h
0x180037c05  jnz     short loc_180037C16
0x180037c07  mov     eax, [rsp+38h+Length]
0x180037c0b  mov     ebx, 80000005h
0x180037c10  mov     [rsi+38h], rax
0x180037c14  jmp     short loc_180037C29
0x180037c16  test    eax, eax
0x180037c18  js      short loc_180037C29
0x180037c1a  mov     eax, [rsp+38h+Length]
0x180037c1e  mov     [rsi+38h], rax
0x180037c22  jmp     short loc_180037C29
0x180037c24  mov     ebx, 0C00000D7h
0x180037c29  lea     rcx, [r14+10h]; Resource
0x180037c2d  call    cs:__imp_ExReleaseResourceLite
0x180037c34  nop     dword ptr [rax+rax+00h]
0x180037c39  call    cs:__imp_KeLeaveCriticalRegion
0x180037c40  nop     dword ptr [rax+rax+00h]
0x180037c45  xor     edx, edx; PriorityBoost
0x180037c47  mov     [rsi+30h], ebx
0x180037c4a  mov     rcx, rsi; Irp
0x180037c4d  call    cs:__imp_IofCompleteRequest
0x180037c54  nop     dword ptr [rax+rax+00h]
0x180037c59  mov     rbp, [rsp+38h+arg_10]
0x180037c5e  mov     eax, ebx
0x180037c60  mov     rbx, [rsp+38h+arg_0]
0x180037c65  add     rsp, 20h
0x180037c69  pop     r14
0x180037c6b  pop     rdi
0x180037c6c  pop     rsi
0x180037c6d  retn
```
