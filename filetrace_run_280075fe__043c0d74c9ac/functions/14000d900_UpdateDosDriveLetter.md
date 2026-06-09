# UpdateDosDriveLetter

- ea: `0x14000d900`
- end: `0x14000da5a`
- name: `UpdateDosDriveLetter`
- size: `346`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000d900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000da2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da2b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d9e2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d9e2`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d950`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d950`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d997`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d997`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d9f5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d9f5`
- `FLTMGR!FltReleaseContext` at `0x14000da14`
- `FLTMGR!FltReleaseContext` at `0x14000da14`
- `FLTMGR!FltGetVolumeContext` at `0x14000d97d`
- `FLTMGR!FltGetVolumeContext` at `0x14000d97d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000da3a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000da3a`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d934`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d934`

## pseudocode

```c
void __fastcall UpdateDosDriveLetter(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, struct _FLT_VOLUME *Context)
{
  int v5; // edi
  WCHAR v6; // cx
  int v7; // ebx
  struct _UNICODE_STRING DosName; // [rsp+20h] [rbp-10h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+60h] [rbp+30h] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+68h] [rbp+38h] BYREF

  DiskDeviceObject = 0;
  Contexta = 0;
  DosName = 0;
  if ( FltGetDiskDeviceObject(Context, &DiskDeviceObject) >= 0
    && IoVolumeDeviceToDosName(DiskDeviceObject, &DosName) >= 0
    && DosName.Length
    && FltGetVolumeContext((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, Context, &Contexta) >= 0 )
  {
    v5 = 0;
    if ( (unsigned __int16)(RtlUpcaseUnicodeChar(*DosName.Buffer) - 65) <= 0x19u )
    {
      v6 = *DosName.Buffer;
      *((_WORD *)Contexta + 90) = *DosName.Buffer;
      v5 = 1 << (v6 - 65);
    }
    v7 = v5 | *((_DWORD *)Contexta + 120) & 0x18000000;
    ExAcquireFastMutex(&SessionLock);
    ExReleaseFastMutex(&SessionLock);
    *((_DWORD *)Contexta + 120) = v7;
  }
  if ( Contexta )
    FltReleaseContext(Contexta);
  if ( DosName.Buffer )
    ExFreePoolWithTag(DosName.Buffer, 0);
  FltFreeGenericWorkItem(FltWorkItem);
}

```

## disassembly

```asm
0x14000d900  mov     [rsp-18h+arg_0], rbx
0x14000d905  mov     [rsp-18h+arg_8], rsi
0x14000d90a  push    rbp
0x14000d90b  push    rdi
0x14000d90c  push    r14
0x14000d90e  mov     rbp, rsp
0x14000d911  sub     rsp, 30h
0x14000d915  mov     rsi, rcx
0x14000d918  lea     rdx, [rbp+DiskDeviceObject]; DiskDeviceObject
0x14000d91c  xor     r14d, r14d
0x14000d91f  xorps   xmm0, xmm0
0x14000d922  mov     rcx, r8; Volume
0x14000d925  mov     [rbp+DiskDeviceObject], r14
0x14000d929  mov     [rbp+Context], r14
0x14000d92d  mov     rbx, r8
0x14000d930  movups  xmmword ptr [rbp+DosName.Length], xmm0
0x14000d934  call    cs:__imp_FltGetDiskDeviceObject
0x14000d93b  nop     dword ptr [rax+rax+00h]
0x14000d940  test    eax, eax
0x14000d942  js      loc_14000DA0B
0x14000d948  mov     rcx, [rbp+DiskDeviceObject]; VolumeDeviceObject
0x14000d94c  lea     rdx, [rbp+DosName]; DosName
0x14000d950  call    cs:__imp_IoVolumeDeviceToDosName
0x14000d957  nop     dword ptr [rax+rax+00h]
0x14000d95c  test    eax, eax
0x14000d95e  js      loc_14000DA0B
0x14000d964  cmp     [rbp+DosName.Length], r14w
0x14000d969  jbe     loc_14000DA0B
0x14000d96f  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d976  lea     r8, [rbp+Context]; Context
0x14000d97a  mov     rdx, rbx; Volume
0x14000d97d  call    cs:__imp_FltGetVolumeContext
0x14000d984  nop     dword ptr [rax+rax+00h]
0x14000d989  test    eax, eax
0x14000d98b  js      short loc_14000DA0B
0x14000d98d  mov     rcx, [rbp+DosName.Buffer]
0x14000d991  mov     edi, r14d
0x14000d994  movzx   ecx, word ptr [rcx]; SourceCharacter
0x14000d997  call    cs:__imp_RtlUpcaseUnicodeChar
0x14000d99e  nop     dword ptr [rax+rax+00h]
0x14000d9a3  lea     edx, [r14+41h]
0x14000d9a7  sub     ax, dx
0x14000d9aa  cmp     ax, 19h
0x14000d9ae  ja      short loc_14000D9C9
0x14000d9b0  mov     rax, [rbp+DosName.Buffer]
0x14000d9b4  lea     edi, [rdx-40h]
0x14000d9b7  movzx   ecx, word ptr [rax]
0x14000d9ba  mov     rax, [rbp+Context]
0x14000d9be  mov     [rax+0B4h], cx
0x14000d9c5  sub     ecx, edx
0x14000d9c7  shl     edi, cl
0x14000d9c9  mov     rax, [rbp+Context]
0x14000d9cd  lea     rcx, SessionLock; FastMutex
0x14000d9d4  mov     ebx, [rax+1E0h]
0x14000d9da  and     ebx, 18000000h
0x14000d9e0  or      ebx, edi
0x14000d9e2  call    cs:__imp_ExAcquireFastMutex
0x14000d9e9  nop     dword ptr [rax+rax+00h]
0x14000d9ee  lea     rcx, SessionLock; FastMutex
0x14000d9f5  call    cs:__imp_ExReleaseFastMutex
0x14000d9fc  nop     dword ptr [rax+rax+00h]
0x14000da01  mov     rax, [rbp+Context]
0x14000da05  mov     [rax+1E0h], ebx
0x14000da0b  mov     rcx, [rbp+Context]; Context
0x14000da0f  test    rcx, rcx
0x14000da12  jz      short loc_14000DA20
0x14000da14  call    cs:__imp_FltReleaseContext
0x14000da1b  nop     dword ptr [rax+rax+00h]
0x14000da20  mov     rcx, [rbp+DosName.Buffer]; P
0x14000da24  test    rcx, rcx
0x14000da27  jz      short loc_14000DA37
0x14000da29  xor     edx, edx; Tag
0x14000da2b  call    cs:__imp_ExFreePoolWithTag
0x14000da32  nop     dword ptr [rax+rax+00h]
0x14000da37  mov     rcx, rsi; FltWorkItem
0x14000da3a  call    cs:__imp_FltFreeGenericWorkItem
0x14000da41  nop     dword ptr [rax+rax+00h]
0x14000da46  mov     rbx, [rsp+30h+arg_0]
0x14000da4b  mov     rsi, [rsp+30h+arg_8]
0x14000da50  add     rsp, 30h
0x14000da54  pop     r14
0x14000da56  pop     rdi
0x14000da57  pop     rbp
0x14000da58  retn
```
