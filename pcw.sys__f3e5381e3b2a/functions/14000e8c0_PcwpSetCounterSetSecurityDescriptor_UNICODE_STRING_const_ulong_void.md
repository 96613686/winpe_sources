# PcwpSetCounterSetSecurityDescriptor(_UNICODE_STRING const *,ulong,void *)

- ea: `0x14000e8c0`
- end: `0x14000eb21`
- name: `?PcwpSetCounterSetSecurityDescriptor@@YAJPEBU_UNICODE_STRING@@KPEAX@Z`
- size: `609`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, DWORD, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a9b0`

## callees

- `0x14000cf6c`
- `0x14000dcf0`
- `0x14000dd2c`
- `0x14000e648`
- `0x14000e8c0`
- `0x14000ed84`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e9a3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e9a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e98a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ea5c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e98a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ea5c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ea08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eadd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ea08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000eadd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e9fc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e9fc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ea6d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ea6d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ead1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ead1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea48`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000ea7d`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000ea7d`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000ea2f`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000ea2f`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14000e9e9`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14000e9e9`
- `ntoskrnl!ZwSetValueKey` at `0x14000eaaa`
- `ntoskrnl!ZwSetValueKey` at `0x14000eaaa`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e90e`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e96e`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000eaf4`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e90e`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e96e`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000eaf4`

## pseudocode

```c
__int64 __fastcall PcwpSetCounterSetSecurityDescriptor(const struct _UNICODE_STRING *a1, DWORD a2, void *a3)
{
  int v4; // ebx
  int v6; // edx
  unsigned int v7; // edi
  PSECURITY_DESCRIPTOR v8; // rcx
  struct PCW_SILO_NEUTRAL_COUNTERSET *v9; // rbx
  char *v10; // r14
  NTSTATUS v11; // esi
  __int64 v12; // rax
  ULONG v13; // eax
  void *v14; // r8
  PSECURITY_DESCRIPTOR v15; // rcx
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+30h] [rbp-10h] BYREF
  struct PCW_SILO_NEUTRAL_COUNTERSET *v17; // [rsp+38h] [rbp-8h] BYREF
  DWORD SecurityInformation; // [rsp+78h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+48h] BYREF

  SecurityInformation = a2;
  v17 = 0;
  ObjectsSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  v4 = PcwpOpenSecurityKey();
  if ( v4 < 0 )
  {
    if ( SecurityDescriptor )
      ObDereferenceSecurityDescriptor(SecurityDescriptor, 1);
    return (unsigned int)v4;
  }
  v6 = ((SecurityInformation & 3) != 0 ? 0x80000 : 0) | 0x40000;
  if ( (SecurityInformation & 4) == 0 )
    v6 = (SecurityInformation & 3) != 0 ? 0x80000 : 0;
  v7 = v6 | 0x1000000;
  if ( (SecurityInformation & 8) == 0 )
    v7 = v6;
  v4 = PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(&v17);
  if ( v4 < 0 )
  {
    v8 = SecurityDescriptor;
    if ( SecurityDescriptor )
      ObDereferenceSecurityDescriptor(SecurityDescriptor, 1);
    if ( v17 )
      ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v8, v17);
    return (unsigned int)v4;
  }
  KeEnterCriticalRegion();
  v9 = v17;
  v10 = (char *)v17 + 88;
  ExAcquirePushLockSharedEx((char *)v17 + 88, 0);
  ObjectsSecurityDescriptor = (PSECURITY_DESCRIPTOR)*((_QWORD *)v9 + 12);
  v11 = PcwpAccessCheck(v9, v7);
  if ( v11 >= 0 )
    v11 = SeSetSecurityDescriptorInfo(
            0,
            &SecurityInformation,
            a3,
            &ObjectsSecurityDescriptor,
            PagedPool,
            &PcwCounterSetGenericMap);
  ExReleasePushLockSharedEx(v10, 0);
  KeLeaveCriticalRegion();
  if ( v11 >= 0 )
  {
    v12 = utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(&SecurityDescriptor);
    v11 = ObLogSecurityDescriptor(ObjectsSecurityDescriptor, v12, 1);
    if ( ObjectsSecurityDescriptor )
      ExFreePoolWithTag(ObjectsSecurityDescriptor, 0);
    if ( v11 >= 0 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v10, 0);
      v13 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      v11 = ZwSetValueKey(PcwSecurityKey, (PUNICODE_STRING)((char *)v9 + 24), 0, 3u, SecurityDescriptor, v13);
      if ( v11 >= 0 )
      {
        v14 = (void *)*((_QWORD *)v9 + 12);
        *((_QWORD *)v9 + 12) = SecurityDescriptor;
        SecurityDescriptor = v14;
      }
      ExReleasePushLockExclusiveEx(v10, 0);
      KeLeaveCriticalRegion();
    }
  }
  v15 = SecurityDescriptor;
  if ( SecurityDescriptor )
    ObDereferenceSecurityDescriptor(SecurityDescriptor, 1);
  if ( v9 )
    ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v15, v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000e8c0  mov     [rsp-28h+arg_0], rbx
0x14000e8c5  mov     [rsp-28h+SecurityInformation], edx
0x14000e8c9  push    rbp
0x14000e8ca  push    rsi
0x14000e8cb  push    rdi
0x14000e8cc  push    r14
0x14000e8ce  push    r15
0x14000e8d0  mov     rbp, rsp
0x14000e8d3  sub     rsp, 40h
0x14000e8d7  mov     r15, r8
0x14000e8da  mov     [rbp+var_8], 0
0x14000e8e2  mov     rsi, rcx
0x14000e8e5  mov     [rbp+ObjectsSecurityDescriptor], 0
0x14000e8ed  mov     [rbp+SecurityDescriptor], 0
0x14000e8f5  call    ?PcwpOpenSecurityKey@@YAJXZ; PcwpOpenSecurityKey(void)
0x14000e8fa  mov     ebx, eax
0x14000e8fc  test    eax, eax
0x14000e8fe  jns     short loc_14000E921
0x14000e900  mov     rcx, [rbp+SecurityDescriptor]
0x14000e904  test    rcx, rcx
0x14000e907  jz      short loc_14000E91A
0x14000e909  mov     edx, 1
0x14000e90e  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000e915  nop     dword ptr [rax+rax+00h]
0x14000e91a  mov     eax, ebx
0x14000e91c  jmp     loc_14000EB0F
0x14000e921  mov     r8d, [rbp+SecurityInformation]
0x14000e925  mov     eax, r8d
0x14000e928  and     al, 3
0x14000e92a  neg     al
0x14000e92c  sbb     ecx, ecx
0x14000e92e  and     ecx, 80000h
0x14000e934  mov     edx, ecx
0x14000e936  bts     edx, 12h
0x14000e93a  test    r8b, 4
0x14000e93e  cmovz   edx, ecx
0x14000e941  lea     rcx, [rbp+var_8]
0x14000e945  mov     edi, edx
0x14000e947  bts     edi, 18h
0x14000e94b  test    r8b, 8
0x14000e94f  cmovz   edi, edx
0x14000e952  mov     rdx, rsi
0x14000e955  call    ?FindOrCreate@PCW_SILO_NEUTRAL_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z; PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> *,_UNICODE_STRING const *)
0x14000e95a  mov     ebx, eax
0x14000e95c  test    eax, eax
0x14000e95e  jns     short loc_14000E98A
0x14000e960  mov     rcx, [rbp+SecurityDescriptor]
0x14000e964  test    rcx, rcx
0x14000e967  jz      short loc_14000E97A
0x14000e969  mov     edx, 1
0x14000e96e  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000e975  nop     dword ptr [rax+rax+00h]
0x14000e97a  mov     rdx, [rbp+var_8]
0x14000e97e  test    rdx, rdx
0x14000e981  jz      short loc_14000E91A
0x14000e983  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000e988  jmp     short loc_14000E91A
0x14000e98a  call    cs:__imp_KeEnterCriticalRegion
0x14000e991  nop     dword ptr [rax+rax+00h]
0x14000e996  mov     rbx, [rbp+var_8]
0x14000e99a  xor     edx, edx
0x14000e99c  lea     r14, [rbx+58h]
0x14000e9a0  mov     rcx, r14
0x14000e9a3  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000e9aa  nop     dword ptr [rax+rax+00h]
0x14000e9af  mov     rax, [rbx+60h]
0x14000e9b3  mov     edx, edi; unsigned int
0x14000e9b5  mov     rcx, rbx; struct PCW_SILO_NEUTRAL_COUNTERSET *
0x14000e9b8  mov     [rbp+ObjectsSecurityDescriptor], rax
0x14000e9bc  call    ?PcwpAccessCheck@@YAJPEBVPCW_SILO_NEUTRAL_COUNTERSET@@K@Z; PcwpAccessCheck(PCW_SILO_NEUTRAL_COUNTERSET const *,ulong)
0x14000e9c1  mov     esi, eax
0x14000e9c3  mov     edi, 1
0x14000e9c8  test    eax, eax
0x14000e9ca  js      short loc_14000E9F7
0x14000e9cc  lea     rax, ?PcwCounterSetGenericMap@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING PcwCounterSetGenericMap
0x14000e9d3  mov     r8, r15; ModificationDescriptor
0x14000e9d6  mov     [rsp+40h+GenericMapping], rax; GenericMapping
0x14000e9db  lea     r9, [rbp+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x14000e9df  lea     rdx, [rbp+SecurityInformation]; SecurityInformation
0x14000e9e3  mov     [rsp+40h+PoolType], edi; PoolType
0x14000e9e7  xor     ecx, ecx; Object
0x14000e9e9  call    cs:__imp_SeSetSecurityDescriptorInfo
0x14000e9f0  nop     dword ptr [rax+rax+00h]
0x14000e9f5  mov     esi, eax
0x14000e9f7  xor     edx, edx
0x14000e9f9  mov     rcx, r14
0x14000e9fc  call    cs:__imp_ExReleasePushLockSharedEx
0x14000ea03  nop     dword ptr [rax+rax+00h]
0x14000ea08  call    cs:__imp_KeLeaveCriticalRegion
0x14000ea0f  nop     dword ptr [rax+rax+00h]
0x14000ea14  test    esi, esi
0x14000ea16  js      loc_14000EAE9
0x14000ea1c  lea     rcx, [rbp+SecurityDescriptor]
0x14000ea20  call    ??$replace@XUObDereferenceSecurityDescriptorDeleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@0@@Z; utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> &)
0x14000ea25  mov     rcx, [rbp+ObjectsSecurityDescriptor]
0x14000ea29  mov     r8d, edi
0x14000ea2c  mov     rdx, rax
0x14000ea2f  call    cs:__imp_ObLogSecurityDescriptor
0x14000ea36  nop     dword ptr [rax+rax+00h]
0x14000ea3b  mov     rcx, [rbp+ObjectsSecurityDescriptor]; P
0x14000ea3f  mov     esi, eax
0x14000ea41  test    rcx, rcx
0x14000ea44  jz      short loc_14000EA54
0x14000ea46  xor     edx, edx; Tag
0x14000ea48  call    cs:__imp_ExFreePoolWithTag
0x14000ea4f  nop     dword ptr [rax+rax+00h]
0x14000ea54  test    esi, esi
0x14000ea56  js      loc_14000EAE9
0x14000ea5c  call    cs:__imp_KeEnterCriticalRegion
0x14000ea63  nop     dword ptr [rax+rax+00h]
0x14000ea68  xor     edx, edx
0x14000ea6a  mov     rcx, r14
0x14000ea6d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ea74  nop     dword ptr [rax+rax+00h]
0x14000ea79  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000ea7d  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000ea84  nop     dword ptr [rax+rax+00h]
0x14000ea89  mov     r8, [rbp+SecurityDescriptor]
0x14000ea8d  lea     rdx, [rbx+18h]; ValueName
0x14000ea91  mov     rcx, cs:?PcwSecurityKey@@3PEAXEA; KeyHandle
0x14000ea98  mov     r9d, 3; Type
0x14000ea9e  mov     dword ptr [rsp+40h+GenericMapping], eax; DataSize
0x14000eaa2  mov     qword ptr [rsp+40h+PoolType], r8; Data
0x14000eaa7  xor     r8d, r8d; TitleIndex
0x14000eaaa  call    cs:__imp_ZwSetValueKey
0x14000eab1  nop     dword ptr [rax+rax+00h]
0x14000eab6  mov     esi, eax
0x14000eab8  test    eax, eax
0x14000eaba  js      short loc_14000EACC
0x14000eabc  mov     rdx, [rbp+SecurityDescriptor]
0x14000eac0  mov     r8, [rbx+60h]
0x14000eac4  mov     [rbx+60h], rdx
0x14000eac8  mov     [rbp+SecurityDescriptor], r8
0x14000eacc  xor     edx, edx
0x14000eace  mov     rcx, r14
0x14000ead1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ead8  nop     dword ptr [rax+rax+00h]
0x14000eadd  call    cs:__imp_KeLeaveCriticalRegion
0x14000eae4  nop     dword ptr [rax+rax+00h]
0x14000eae9  mov     rcx, [rbp+SecurityDescriptor]
0x14000eaed  test    rcx, rcx
0x14000eaf0  jz      short loc_14000EB00
0x14000eaf2  mov     edx, edi
0x14000eaf4  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000eafb  nop     dword ptr [rax+rax+00h]
0x14000eb00  test    rbx, rbx
0x14000eb03  jz      short loc_14000EB0D
0x14000eb05  mov     rdx, rbx
0x14000eb08  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000eb0d  mov     eax, esi
0x14000eb0f  mov     rbx, [rsp+40h+arg_0]
0x14000eb14  add     rsp, 40h
0x14000eb18  pop     r15
0x14000eb1a  pop     r14
0x14000eb1c  pop     rdi
0x14000eb1d  pop     rsi
0x14000eb1e  pop     rbp
0x14000eb1f  retn
```
