# DriverEntry

- ea: `0x14000e078`
- end: `0x14000e154`
- name: `DriverEntry`
- size: `220`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e010`

## callees

- `0x1400041f0`
- `0x14000b254`
- `0x14000e078`
- `0x14000e15c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e0a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e0a2`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000e120`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000e120`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000e0fd`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000e0fd`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  _QWORD *PoolWithTag; // rax
  _QWORD *v5; // rbx
  NTSTATUS v6; // edi

  wil_InitializeFeatureStaging();
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x774E434Bu);
  v5 = PoolWithTag;
  if ( PoolWithTag )
  {
    PoolWithTag[1] = DriverObject;
    PoolWithTag[2] = RegistryPath;
    *PoolWithTag = &CKSThunkDriver::`vftable';
    v6 = CKernelFilterDriver::Initialize((PDRIVER_OBJECT *)PoolWithTag);
    if ( v6 >= 0 )
      return v6;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v5 + 16LL))(v5, 1);
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
0x14000e078  mov     [rsp+arg_0], rbx
0x14000e07d  mov     [rsp+arg_8], rsi
0x14000e082  push    rdi
0x14000e083  sub     rsp, 20h
0x14000e087  mov     rdi, rdx
0x14000e08a  mov     rsi, rcx
0x14000e08d  call    wil_InitializeFeatureStaging
0x14000e092  mov     edx, 18h; NumberOfBytes
0x14000e097  mov     ecx, 200h; PoolType
0x14000e09c  mov     r8d, 774E434Bh; Tag
0x14000e0a2  call    cs:__imp_ExAllocatePoolWithTag
0x14000e0a9  nop     dword ptr [rax+rax+00h]
0x14000e0ae  mov     rbx, rax
0x14000e0b1  test    rax, rax
0x14000e0b4  jz      short loc_14000E0EC
0x14000e0b6  mov     [rax+8], rsi
0x14000e0ba  mov     rcx, rbx; this
0x14000e0bd  mov     [rax+10h], rdi
0x14000e0c1  lea     rax, ??_7CKSThunkDriver@@6B@; const CKSThunkDriver::`vftable'
0x14000e0c8  mov     [rbx], rax
0x14000e0cb  call    ?Initialize@CKernelFilterDriver@@QEAAJXZ; CKernelFilterDriver::Initialize(void)
0x14000e0d0  mov     edi, eax
0x14000e0d2  test    eax, eax
0x14000e0d4  jns     short loc_14000E141
0x14000e0d6  mov     rcx, [rbx]
0x14000e0d9  mov     edx, 1
0x14000e0de  mov     rax, [rcx+10h]
0x14000e0e2  mov     rcx, rbx
0x14000e0e5  call    _guard_dispatch_icall
0x14000e0ea  jmp     short loc_14000E0F1
0x14000e0ec  mov     edi, 0C000009Ah
0x14000e0f1  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000e0f8  test    rcx, rcx
0x14000e0fb  jz      short loc_14000E114
0x14000e0fd  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000e104  nop     dword ptr [rax+rax+00h]
0x14000e109  mov     cs:g_wil_details_featureChangeNotification, 0
0x14000e114  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000e11b  test    rcx, rcx
0x14000e11e  jz      short loc_14000E137
0x14000e120  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000e127  nop     dword ptr [rax+rax+00h]
0x14000e12c  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000e137  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000e141  mov     rbx, [rsp+28h+arg_0]
0x14000e146  mov     eax, edi
0x14000e148  mov     rsi, [rsp+28h+arg_8]
0x14000e14d  add     rsp, 20h
0x14000e151  pop     rdi
0x14000e152  retn
```
