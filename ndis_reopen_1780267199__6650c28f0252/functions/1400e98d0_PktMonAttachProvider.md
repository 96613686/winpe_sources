# PktMonAttachProvider

- ea: `0x1400e98d0`
- end: `0x1400e9a1a`
- name: `PktMonAttachProvider`
- size: `330`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, PVOID ClientBindingContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400962c4`
- `0x1400e98d0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400e9a09`
- `ntoskrnl!KeReleaseMutex` at `0x1400e9a09`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e99dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e99dc`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400e9965`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1400e9965`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400e9984`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400e9984`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400e991b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400e991b`
- `NETIO!NmrClientAttachProvider` at `0x1400e99ae`
- `NETIO!NmrClientAttachProvider` at `0x1400e99ae`

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
    || *((_QWORD *)&xmmword_140123740 + 1) )
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
         (const void **)&xmmword_140123740 + 1);
  if ( !v7 )
  {
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
    *(_QWORD *)&xmmword_140123740 = ProviderBindingContext;
    ((void (*)(void))qword_140123728)();
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
0x1400e98d0  mov     [rsp+arg_0], rbx
0x1400e98d5  mov     [rsp+arg_8], rsi
0x1400e98da  push    rdi
0x1400e98db  sub     rsp, 30h
0x1400e98df  mov     rbx, r8
0x1400e98e2  mov     [rsp+38h+ProviderBindingContext], 0
0x1400e98eb  mov     rdi, rdx
0x1400e98ee  mov     rsi, rcx
0x1400e98f1  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x1400e98f6  test    eax, eax
0x1400e98f8  jz      short loc_1400E9945
0x1400e98fa  mov     rax, [rbx+20h]
0x1400e98fe  test    rax, rax
0x1400e9901  jz      short loc_1400E9945
0x1400e9903  cmp     word ptr [rax+4], 1
0x1400e9908  jz      short loc_1400E9945
0x1400e990a  mov     ebx, 0C00002B9h
0x1400e990f  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1400e9916  test    rcx, rcx
0x1400e9919  jz      short loc_1400E9932
0x1400e991b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400e9922  nop     dword ptr [rax+rax+00h]
0x1400e9927  mov     cs:RunRefCacheAware, 0
0x1400e9932  mov     rsi, [rsp+38h+arg_8]
0x1400e9937  mov     eax, ebx
0x1400e9939  mov     rbx, [rsp+38h+arg_0]
0x1400e993e  add     rsp, 30h
0x1400e9942  pop     rdi
0x1400e9943  retn
0x1400e9945  cmp     qword ptr cs:xmmword_140123740+8, 0
0x1400e994d  jnz     short loc_1400E990A
0x1400e994f  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1400e9956  test    rcx, rcx
0x1400e9959  jnz     short loc_1400E9984
0x1400e995b  mov     edx, 72644D50h; PoolTag
0x1400e9960  mov     ecx, 200h; PoolType
0x1400e9965  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1400e996c  nop     dword ptr [rax+rax+00h]
0x1400e9971  mov     cs:RunRefCacheAware, rax
0x1400e9978  test    rax, rax
0x1400e997b  jnz     short loc_1400E9990
0x1400e997d  mov     ebx, 0C0000017h
0x1400e9982  jmp     short loc_1400E990F
0x1400e9984  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1400e998b  nop     dword ptr [rax+rax+00h]
0x1400e9990  lea     rax, xmmword_140123740+8
0x1400e9997  mov     rdx, rdi; ClientBindingContext
0x1400e999a  lea     r9, [rsp+38h+ProviderBindingContext]; ProviderBindingContext
0x1400e999f  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x1400e99a4  lea     r8, PktMonClientDispatch; ClientDispatch
0x1400e99ab  mov     rcx, rsi; NmrBindingHandle
0x1400e99ae  call    cs:__imp_NmrClientAttachProvider
0x1400e99b5  nop     dword ptr [rax+rax+00h]
0x1400e99ba  mov     ebx, eax
0x1400e99bc  test    eax, eax
0x1400e99be  jnz     loc_1400E990F
0x1400e99c4  xor     r9d, r9d; Alertable
0x1400e99c7  mov     [rsp+38h+ProviderDispatch], 0; Timeout
0x1400e99d0  xor     r8d, r8d; WaitMode
0x1400e99d3  lea     rcx, PktMonCompMutex; Object
0x1400e99da  xor     edx, edx; WaitReason
0x1400e99dc  call    cs:__imp_KeWaitForSingleObject
0x1400e99e3  nop     dword ptr [rax+rax+00h]
0x1400e99e8  mov     rdx, [rsp+38h+ProviderBindingContext]
0x1400e99ed  mov     rax, cs:qword_140123728
0x1400e99f4  mov     qword ptr cs:xmmword_140123740, rdx
0x1400e99fb  call    _guard_dispatch_icall
0x1400e9a00  xor     edx, edx; Wait
0x1400e9a02  lea     rcx, PktMonCompMutex; Mutex
0x1400e9a09  call    cs:__imp_KeReleaseMutex
0x1400e9a10  nop     dword ptr [rax+rax+00h]
0x1400e9a15  jmp     loc_1400E9932
```
