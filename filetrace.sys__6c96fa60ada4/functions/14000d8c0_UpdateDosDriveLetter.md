# UpdateDosDriveLetter

- ea: `0x14000d8c0`
- end: `0x14000da1a`
- name: `UpdateDosDriveLetter`
- size: `346`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000d8c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9eb`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d9a2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d9a2`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d910`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d910`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d957`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d957`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d9b5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d9b5`
- `FLTMGR!FltReleaseContext` at `0x14000d9d4`
- `FLTMGR!FltReleaseContext` at `0x14000d9d4`
- `FLTMGR!FltGetVolumeContext` at `0x14000d93d`
- `FLTMGR!FltGetVolumeContext` at `0x14000d93d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000d9fa`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000d9fa`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d8f4`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d8f4`

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
0x14000d8c0  mov     [rsp-18h+arg_0], rbx
0x14000d8c5  mov     [rsp-18h+arg_8], rsi
0x14000d8ca  push    rbp
0x14000d8cb  push    rdi
0x14000d8cc  push    r14
0x14000d8ce  mov     rbp, rsp
0x14000d8d1  sub     rsp, 30h
0x14000d8d5  mov     rsi, rcx
0x14000d8d8  lea     rdx, [rbp+DiskDeviceObject]; DiskDeviceObject
0x14000d8dc  xor     r14d, r14d
0x14000d8df  xorps   xmm0, xmm0
0x14000d8e2  mov     rcx, r8; Volume
0x14000d8e5  mov     [rbp+DiskDeviceObject], r14
0x14000d8e9  mov     [rbp+Context], r14
0x14000d8ed  mov     rbx, r8
0x14000d8f0  movups  xmmword ptr [rbp+DosName.Length], xmm0
0x14000d8f4  call    cs:__imp_FltGetDiskDeviceObject
0x14000d8fb  nop     dword ptr [rax+rax+00h]
0x14000d900  test    eax, eax
0x14000d902  js      loc_14000D9CB
0x14000d908  mov     rcx, [rbp+DiskDeviceObject]; VolumeDeviceObject
0x14000d90c  lea     rdx, [rbp+DosName]; DosName
0x14000d910  call    cs:__imp_IoVolumeDeviceToDosName
0x14000d917  nop     dword ptr [rax+rax+00h]
0x14000d91c  test    eax, eax
0x14000d91e  js      loc_14000D9CB
0x14000d924  cmp     [rbp+DosName.Length], r14w
0x14000d929  jbe     loc_14000D9CB
0x14000d92f  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d936  lea     r8, [rbp+Context]; Context
0x14000d93a  mov     rdx, rbx; Volume
0x14000d93d  call    cs:__imp_FltGetVolumeContext
0x14000d944  nop     dword ptr [rax+rax+00h]
0x14000d949  test    eax, eax
0x14000d94b  js      short loc_14000D9CB
0x14000d94d  mov     rcx, [rbp+DosName.Buffer]
0x14000d951  mov     edi, r14d
0x14000d954  movzx   ecx, word ptr [rcx]; SourceCharacter
0x14000d957  call    cs:__imp_RtlUpcaseUnicodeChar
0x14000d95e  nop     dword ptr [rax+rax+00h]
0x14000d963  lea     edx, [r14+41h]
0x14000d967  sub     ax, dx
0x14000d96a  cmp     ax, 19h
0x14000d96e  ja      short loc_14000D989
0x14000d970  mov     rax, [rbp+DosName.Buffer]
0x14000d974  lea     edi, [rdx-40h]
0x14000d977  movzx   ecx, word ptr [rax]
0x14000d97a  mov     rax, [rbp+Context]
0x14000d97e  mov     [rax+0B4h], cx
0x14000d985  sub     ecx, edx
0x14000d987  shl     edi, cl
0x14000d989  mov     rax, [rbp+Context]
0x14000d98d  lea     rcx, SessionLock; FastMutex
0x14000d994  mov     ebx, [rax+1E0h]
0x14000d99a  and     ebx, 18000000h
0x14000d9a0  or      ebx, edi
0x14000d9a2  call    cs:__imp_ExAcquireFastMutex
0x14000d9a9  nop     dword ptr [rax+rax+00h]
0x14000d9ae  lea     rcx, SessionLock; FastMutex
0x14000d9b5  call    cs:__imp_ExReleaseFastMutex
0x14000d9bc  nop     dword ptr [rax+rax+00h]
0x14000d9c1  mov     rax, [rbp+Context]
0x14000d9c5  mov     [rax+1E0h], ebx
0x14000d9cb  mov     rcx, [rbp+Context]; Context
0x14000d9cf  test    rcx, rcx
0x14000d9d2  jz      short loc_14000D9E0
0x14000d9d4  call    cs:__imp_FltReleaseContext
0x14000d9db  nop     dword ptr [rax+rax+00h]
0x14000d9e0  mov     rcx, [rbp+DosName.Buffer]; P
0x14000d9e4  test    rcx, rcx
0x14000d9e7  jz      short loc_14000D9F7
0x14000d9e9  xor     edx, edx; Tag
0x14000d9eb  call    cs:__imp_ExFreePoolWithTag
0x14000d9f2  nop     dword ptr [rax+rax+00h]
0x14000d9f7  mov     rcx, rsi; FltWorkItem
0x14000d9fa  call    cs:__imp_FltFreeGenericWorkItem
0x14000da01  nop     dword ptr [rax+rax+00h]
0x14000da06  mov     rbx, [rsp+30h+arg_0]
0x14000da0b  mov     rsi, [rsp+30h+arg_8]
0x14000da10  add     rsp, 30h
0x14000da14  pop     r14
0x14000da16  pop     rdi
0x14000da17  pop     rbp
0x14000da18  retn
```
