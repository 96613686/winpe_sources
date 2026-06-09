# DriverEntry

- ea: `0x14000d078`
- end: `0x14000d154`
- name: `DriverEntry`
- size: `220`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000d010`

## callees

- `0x140003770`
- `0x14000a254`
- `0x14000d078`
- `0x14000d15c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d0a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d0a2`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000d120`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000d120`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000d0fd`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000d0fd`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  CKernelFilterDriver *PoolWithTag; // rax
  CKernelFilterDriver *v5; // rbx
  NTSTATUS v6; // edi

  wil_InitializeFeatureStaging();
  PoolWithTag = (CKernelFilterDriver *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x774E434Bu);
  v5 = PoolWithTag;
  if ( PoolWithTag )
  {
    *((_QWORD *)PoolWithTag + 1) = DriverObject;
    *((_QWORD *)PoolWithTag + 2) = RegistryPath;
    *(_QWORD *)PoolWithTag = &CKSThunkDriver::`vftable';
    v6 = CKernelFilterDriver::Initialize(PoolWithTag);
    if ( v6 >= 0 )
      return v6;
    (*(void (__fastcall **)(CKernelFilterDriver *, __int64))(*(_QWORD *)v5 + 16LL))(v5, 1);
  }
  else
  {
    v6 = -1073741670;
  }
  if ( g_wil_details_featureChangeNotification )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return v6;
}

```

## disassembly

```asm
0x14000d078  mov     [rsp+arg_0], rbx
0x14000d07d  mov     [rsp+arg_8], rsi
0x14000d082  push    rdi
0x14000d083  sub     rsp, 20h
0x14000d087  mov     rdi, rdx
0x14000d08a  mov     rsi, rcx
0x14000d08d  call    wil_InitializeFeatureStaging
0x14000d092  mov     edx, 18h; NumberOfBytes
0x14000d097  mov     ecx, 200h; PoolType
0x14000d09c  mov     r8d, 774E434Bh; Tag
0x14000d0a2  call    cs:__imp_ExAllocatePoolWithTag
0x14000d0a9  nop     dword ptr [rax+rax+00h]
0x14000d0ae  mov     rbx, rax
0x14000d0b1  test    rax, rax
0x14000d0b4  jz      short loc_14000D0EC
0x14000d0b6  mov     [rax+8], rsi
0x14000d0ba  mov     rcx, rbx; this
0x14000d0bd  mov     [rax+10h], rdi
0x14000d0c1  lea     rax, ??_7CKSThunkDriver@@6B@; const CKSThunkDriver::`vftable'
0x14000d0c8  mov     [rbx], rax
0x14000d0cb  call    ?Initialize@CKernelFilterDriver@@QEAAJXZ; CKernelFilterDriver::Initialize(void)
0x14000d0d0  mov     edi, eax
0x14000d0d2  test    eax, eax
0x14000d0d4  jns     short loc_14000D141
0x14000d0d6  mov     rcx, [rbx]
0x14000d0d9  mov     edx, 1
0x14000d0de  mov     rax, [rcx+10h]
0x14000d0e2  mov     rcx, rbx
0x14000d0e5  call    _guard_dispatch_icall
0x14000d0ea  jmp     short loc_14000D0F1
0x14000d0ec  mov     edi, 0C000009Ah
0x14000d0f1  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000d0f8  test    rcx, rcx
0x14000d0fb  jz      short loc_14000D114
0x14000d0fd  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000d104  nop     dword ptr [rax+rax+00h]
0x14000d109  mov     cs:g_wil_details_featureChangeNotification, 0
0x14000d114  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000d11b  test    rcx, rcx
0x14000d11e  jz      short loc_14000D137
0x14000d120  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000d127  nop     dword ptr [rax+rax+00h]
0x14000d12c  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000d137  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000d141  mov     rbx, [rsp+28h+arg_0]
0x14000d146  mov     eax, edi
0x14000d148  mov     rsi, [rsp+28h+arg_8]
0x14000d14d  add     rsp, 20h
0x14000d151  pop     rdi
0x14000d152  retn
```
