# CdpServerQuerySecurity

- ea: `0x14000e130`
- end: `0x14000e200`
- name: `CdpServerQuerySecurity`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000e130`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e164`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e164`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e179`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e179`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e1aa`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e1aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e1b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e1b6`
- `ntoskrnl!IofCompleteRequest` at `0x14000e1da`
- `ntoskrnl!IofCompleteRequest` at `0x14000e1da`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000e197`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000e197`

## pseudocode

```c
__int64 __fastcall CdpServerQuerySecurity(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  NTSTATUS v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // esi
  ULONG Length; // [rsp+30h] [rbp+8h] BYREF
  DWORD SecurityInformation; // [rsp+38h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  SecurityInformation = 0;
  Length = 0;
  Length = CurrentStackLocation->Parameters.Create.Options;
  SecurityInformation = CurrentStackLocation->Parameters.Read.Length;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1 + 40, 0);
  v5 = SeQuerySecurityDescriptorInfo(&SecurityInformation, a2->UserBuffer, &Length, (PSECURITY_DESCRIPTOR *)(a1 + 56));
  v6 = a1 + 40;
  v7 = v5;
  ExReleasePushLockSharedEx(v6, 0);
  KeLeaveCriticalRegion();
  if ( v7 == -1073741789 )
    v7 = -2147483643;
  a2->IoStatus.Information = Length;
  a2->IoStatus.Status = v7;
  IofCompleteRequest(a2, 0);
  return v7;
}

```

## disassembly

```asm
0x14000e130  mov     [rsp+arg_10], rbx
0x14000e135  mov     [rsp+arg_18], rsi
0x14000e13a  push    rdi
0x14000e13b  sub     rsp, 20h
0x14000e13f  xor     eax, eax
0x14000e141  mov     rbx, rdx
0x14000e144  mov     rdx, [rdx+0B8h]
0x14000e14b  mov     rsi, rcx
0x14000e14e  mov     [rsp+28h+SecurityInformation], eax
0x14000e152  mov     [rsp+28h+Length], eax
0x14000e156  mov     eax, [rdx+10h]
0x14000e159  mov     [rsp+28h+Length], eax
0x14000e15d  mov     eax, [rdx+8]
0x14000e160  mov     [rsp+28h+SecurityInformation], eax
0x14000e164  call    cs:__imp_KeEnterCriticalRegion
0x14000e16b  nop     dword ptr [rax+rax+00h]
0x14000e170  lea     rdi, [rsi+28h]
0x14000e174  xor     edx, edx
0x14000e176  mov     rcx, rdi
0x14000e179  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000e180  nop     dword ptr [rax+rax+00h]
0x14000e185  mov     rdx, [rbx+70h]; SecurityDescriptor
0x14000e189  lea     r9, [rsi+38h]; ObjectsSecurityDescriptor
0x14000e18d  lea     r8, [rsp+28h+Length]; Length
0x14000e192  lea     rcx, [rsp+28h+SecurityInformation]; SecurityInformation
0x14000e197  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x14000e19e  nop     dword ptr [rax+rax+00h]
0x14000e1a3  xor     edx, edx
0x14000e1a5  mov     rcx, rdi
0x14000e1a8  mov     esi, eax
0x14000e1aa  call    cs:__imp_ExReleasePushLockSharedEx
0x14000e1b1  nop     dword ptr [rax+rax+00h]
0x14000e1b6  call    cs:__imp_KeLeaveCriticalRegion
0x14000e1bd  nop     dword ptr [rax+rax+00h]
0x14000e1c2  cmp     esi, 0C0000023h
0x14000e1c8  jz      short loc_14000E1F9
0x14000e1ca  mov     eax, [rsp+28h+Length]
0x14000e1ce  xor     edx, edx; PriorityBoost
0x14000e1d0  mov     rcx, rbx; Irp
0x14000e1d3  mov     [rbx+38h], rax
0x14000e1d7  mov     [rbx+30h], esi
0x14000e1da  call    cs:__imp_IofCompleteRequest
0x14000e1e1  nop     dword ptr [rax+rax+00h]
0x14000e1e6  mov     rbx, [rsp+28h+arg_10]
0x14000e1eb  mov     eax, esi
0x14000e1ed  mov     rsi, [rsp+28h+arg_18]
0x14000e1f2  add     rsp, 20h
0x14000e1f6  pop     rdi
0x14000e1f7  retn
0x14000e1f9  mov     esi, 80000005h
0x14000e1fe  jmp     short loc_14000E1CA
```
