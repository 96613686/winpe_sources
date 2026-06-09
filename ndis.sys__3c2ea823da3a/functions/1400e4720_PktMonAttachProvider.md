# PktMonAttachProvider

- ea: `0x1400e4720`
- end: `0x1400e486a`
- name: `PktMonAttachProvider`
- size: `330`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, PVOID ClientBindingContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14009103c`
- `0x1400e4720`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400e4859`
- `ntoskrnl!KeReleaseMutex` at `0x1400e4859`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e482c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e482c`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400e47b5`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400e47b5`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400e47d4`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400e47d4`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400e476b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400e476b`
- `NETIO!NmrClientAttachProvider` at `0x1400e47fe`
- `NETIO!NmrClientAttachProvider` at `0x1400e47fe`

## pseudocode

```c
__int64 __fastcall PktMonAttachProvider(HANDLE NmrBindingHandle, PVOID ClientBindingContext, __int64 a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  PVOID ProviderBindingContext; // [rsp+58h] [rbp+20h] BYREF

  ProviderBindingContext = 0;
  if ( (unsigned int)Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline()
    && (v6 = *(_QWORD *)(a3 + 32)) != 0
    && *(_WORD *)(v6 + 4) != 1
    || *((_QWORD *)&xmmword_14011D750 + 1) )
  {
    v7 = -1073741127;
    goto LABEL_5;
  }
  if ( RunRefCacheAware )
  {
    ExReInitializeRundownProtectionCacheAware(RunRefCacheAware);
  }
  else
  {
    RunRefCacheAware = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x72644D50u);
    if ( !RunRefCacheAware )
    {
      v7 = -1073741801;
      goto LABEL_5;
    }
  }
  v7 = NmrClientAttachProvider(
         NmrBindingHandle,
         ClientBindingContext,
         &PktMonClientDispatch,
         &ProviderBindingContext,
         (const void **)&xmmword_14011D750 + 1);
  if ( !v7 )
  {
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
    *(_QWORD *)&xmmword_14011D750 = ProviderBindingContext;
    ((void (*)(void))qword_14011D738)();
    KeReleaseMutex(&PktMonCompMutex, 0);
    return v7;
  }
LABEL_5:
  if ( RunRefCacheAware )
  {
    ExFreeCacheAwareRundownProtection(RunRefCacheAware);
    RunRefCacheAware = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1400e4720  mov     [rsp+arg_0], rbx
0x1400e4725  mov     [rsp+arg_8], rsi
0x1400e472a  push    rdi
0x1400e472b  sub     rsp, 30h
0x1400e472f  mov     rbx, r8
0x1400e4732  mov     [rsp+38h+ProviderBindingContext], 0
0x1400e473b  mov     rdi, rdx
0x1400e473e  mov     rsi, rcx
0x1400e4741  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x1400e4746  test    eax, eax
0x1400e4748  jz      short loc_1400E4795
0x1400e474a  mov     rax, [rbx+20h]
0x1400e474e  test    rax, rax
0x1400e4751  jz      short loc_1400E4795
0x1400e4753  cmp     word ptr [rax+4], 1
0x1400e4758  jz      short loc_1400E4795
0x1400e475a  mov     ebx, 0C00002B9h
0x1400e475f  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1400e4766  test    rcx, rcx
0x1400e4769  jz      short loc_1400E4782
0x1400e476b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400e4772  nop     dword ptr [rax+rax+00h]
0x1400e4777  mov     cs:RunRefCacheAware, 0
0x1400e4782  mov     rsi, [rsp+38h+arg_8]
0x1400e4787  mov     eax, ebx
0x1400e4789  mov     rbx, [rsp+38h+arg_0]
0x1400e478e  add     rsp, 30h
0x1400e4792  pop     rdi
0x1400e4793  retn
0x1400e4795  cmp     qword ptr cs:xmmword_14011D750+8, 0
0x1400e479d  jnz     short loc_1400E475A
0x1400e479f  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1400e47a6  test    rcx, rcx
0x1400e47a9  jnz     short loc_1400E47D4
0x1400e47ab  mov     edx, 72644D50h; PoolTag
0x1400e47b0  mov     ecx, 200h; PoolType
0x1400e47b5  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1400e47bc  nop     dword ptr [rax+rax+00h]
0x1400e47c1  mov     cs:RunRefCacheAware, rax
0x1400e47c8  test    rax, rax
0x1400e47cb  jnz     short loc_1400E47E0
0x1400e47cd  mov     ebx, 0C0000017h
0x1400e47d2  jmp     short loc_1400E475F
0x1400e47d4  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1400e47db  nop     dword ptr [rax+rax+00h]
0x1400e47e0  lea     rax, xmmword_14011D750+8
0x1400e47e7  mov     rdx, rdi; ClientBindingContext
0x1400e47ea  lea     r9, [rsp+38h+ProviderBindingContext]; ProviderBindingContext
0x1400e47ef  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x1400e47f4  lea     r8, PktMonClientDispatch; ClientDispatch
0x1400e47fb  mov     rcx, rsi; NmrBindingHandle
0x1400e47fe  call    cs:__imp_NmrClientAttachProvider
0x1400e4805  nop     dword ptr [rax+rax+00h]
0x1400e480a  mov     ebx, eax
0x1400e480c  test    eax, eax
0x1400e480e  jnz     loc_1400E475F
0x1400e4814  xor     r9d, r9d; Alertable
0x1400e4817  mov     [rsp+38h+ProviderDispatch], 0; Timeout
0x1400e4820  xor     r8d, r8d; WaitMode
0x1400e4823  lea     rcx, PktMonCompMutex; Object
0x1400e482a  xor     edx, edx; WaitReason
0x1400e482c  call    cs:__imp_KeWaitForSingleObject
0x1400e4833  nop     dword ptr [rax+rax+00h]
0x1400e4838  mov     rdx, [rsp+38h+ProviderBindingContext]
0x1400e483d  mov     rax, cs:qword_14011D738
0x1400e4844  mov     qword ptr cs:xmmword_14011D750, rdx
0x1400e484b  call    _guard_dispatch_icall
0x1400e4850  xor     edx, edx; Wait
0x1400e4852  lea     rcx, PktMonCompMutex; Mutex
0x1400e4859  call    cs:__imp_KeReleaseMutex
0x1400e4860  nop     dword ptr [rax+rax+00h]
0x1400e4865  jmp     loc_1400E4782
```
