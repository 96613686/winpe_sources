# PktMonAttachProvider

- ea: `0x140166f60`
- end: `0x1401670bf`
- name: `PktMonAttachProvider`
- size: `351`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, PVOID ClientBindingContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140166efc`
- `0x140166f60`
- `0x1401677e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140167074`
- `ntoskrnl!KeWaitForSingleObject` at `0x140167074`
- `ntoskrnl!KeReleaseMutex` at `0x1401670ae`
- `ntoskrnl!KeReleaseMutex` at `0x1401670ae`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140166ff5`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140166ff5`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140167014`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140167014`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140166fab`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140166fab`
- `NETIO!NmrClientAttachProvider` at `0x14016703e`
- `NETIO!NmrClientAttachProvider` at `0x14016703e`

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
    || *((_QWORD *)&xmmword_1401A37A0 + 1) )
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
    RunRefCacheAware = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x72644D50u);
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
         (const void **)&xmmword_1401A37A0 + 1);
  if ( v7 )
  {
LABEL_5:
    if ( RunRefCacheAware )
    {
      ExFreeCacheAwareRundownProtection(RunRefCacheAware);
      RunRefCacheAware = 0;
    }
    return v7;
  }
  if ( NmrAttachSync )
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
  *(_QWORD *)&xmmword_1401A37A0 = ProviderBindingContext;
  ((void (*)(void))qword_1401A3788)();
  if ( NmrAttachSync )
    KeReleaseMutex(&PktMonCompMutex, 0);
  return v7;
}

```

## disassembly

```asm
0x140166f60  mov     [rsp+arg_0], rbx
0x140166f65  mov     [rsp+arg_8], rsi
0x140166f6a  push    rdi
0x140166f6b  sub     rsp, 30h
0x140166f6f  mov     rbx, r8
0x140166f72  mov     [rsp+38h+ProviderBindingContext], 0
0x140166f7b  mov     rdi, rdx
0x140166f7e  mov     rsi, rcx
0x140166f81  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x140166f86  test    eax, eax
0x140166f88  jz      short loc_140166FD5
0x140166f8a  mov     rax, [rbx+20h]
0x140166f8e  test    rax, rax
0x140166f91  jz      short loc_140166FD5
0x140166f93  cmp     word ptr [rax+4], 1
0x140166f98  jz      short loc_140166FD5
0x140166f9a  mov     ebx, 0C00002B9h
0x140166f9f  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140166fa6  test    rcx, rcx
0x140166fa9  jz      short loc_140166FC2
0x140166fab  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140166fb2  nop     dword ptr [rax+rax+00h]
0x140166fb7  mov     cs:RunRefCacheAware, 0
0x140166fc2  mov     rsi, [rsp+38h+arg_8]
0x140166fc7  mov     eax, ebx
0x140166fc9  mov     rbx, [rsp+38h+arg_0]
0x140166fce  add     rsp, 30h
0x140166fd2  pop     rdi
0x140166fd3  retn
0x140166fd5  cmp     qword ptr cs:xmmword_1401A37A0+8, 0
0x140166fdd  jnz     short loc_140166F9A
0x140166fdf  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140166fe6  test    rcx, rcx
0x140166fe9  jnz     short loc_140167014
0x140166feb  mov     edx, 72644D50h; PoolTag
0x140166ff0  mov     ecx, 200h; PoolType
0x140166ff5  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140166ffc  nop     dword ptr [rax+rax+00h]
0x140167001  mov     cs:RunRefCacheAware, rax
0x140167008  test    rax, rax
0x14016700b  jnz     short loc_140167020
0x14016700d  mov     ebx, 0C0000017h
0x140167012  jmp     short loc_140166F9F
0x140167014  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14016701b  nop     dword ptr [rax+rax+00h]
0x140167020  lea     rax, xmmword_1401A37A0+8
0x140167027  mov     rdx, rdi; ClientBindingContext
0x14016702a  lea     r9, [rsp+38h+ProviderBindingContext]; ProviderBindingContext
0x14016702f  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x140167034  lea     r8, PktMonClientDispatch; ClientDispatch
0x14016703b  mov     rcx, rsi; NmrBindingHandle
0x14016703e  call    cs:__imp_NmrClientAttachProvider
0x140167045  nop     dword ptr [rax+rax+00h]
0x14016704a  mov     ebx, eax
0x14016704c  test    eax, eax
0x14016704e  jnz     loc_140166F9F
0x140167054  cmp     cs:NmrAttachSync, al
0x14016705a  jz      short loc_140167080
0x14016705c  xor     r9d, r9d; Alertable
0x14016705f  mov     [rsp+38h+ProviderDispatch], 0; Timeout
0x140167068  xor     r8d, r8d; WaitMode
0x14016706b  lea     rcx, PktMonCompMutex; Object
0x140167072  xor     edx, edx; WaitReason
0x140167074  call    cs:__imp_KeWaitForSingleObject
0x14016707b  nop     dword ptr [rax+rax+00h]
0x140167080  mov     rax, [rsp+38h+ProviderBindingContext]
0x140167085  mov     qword ptr cs:xmmword_1401A37A0, rax
0x14016708c  mov     rax, cs:qword_1401A3788
0x140167093  call    _guard_dispatch_icall
0x140167098  cmp     cs:NmrAttachSync, 0
0x14016709f  jz      loc_140166FC2
0x1401670a5  xor     edx, edx; Wait
0x1401670a7  lea     rcx, PktMonCompMutex; Mutex
0x1401670ae  call    cs:__imp_KeReleaseMutex
0x1401670b5  nop     dword ptr [rax+rax+00h]
0x1401670ba  jmp     loc_140166FC2
```
