# PktMonAttachProvider

- ea: `0x1c005a030`
- end: `0x1c005a161`
- name: `PktMonAttachProvider`
- size: `305`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, PVOID ClientBindingContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1c001b610`
- `0x1c005a030`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1c005a115`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c005a115`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1c005a0b8`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1c005a0b8`
- `ntoskrnl!KeReleaseMutex` at `0x1c005a150`
- `ntoskrnl!KeReleaseMutex` at `0x1c005a150`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1c005a099`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1c005a099`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1c005a061`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1c005a061`
- `NETIO!NmrClientAttachProvider` at `0x1c005a0e2`
- `NETIO!NmrClientAttachProvider` at `0x1c005a0e2`

## pseudocode

```c
__int64 __fastcall PktMonAttachProvider(HANDLE NmrBindingHandle, PVOID ClientBindingContext)
{
  unsigned int v4; // ebx
  PVOID ProviderBindingContext; // [rsp+58h] [rbp+20h] BYREF

  ProviderBindingContext = 0;
  if ( *((_QWORD *)&xmmword_1C0077E88 + 1) )
  {
    v4 = -1073741127;
LABEL_3:
    if ( RunRef )
    {
      ExFreeCacheAwareRundownProtection(RunRef);
      RunRef = 0;
    }
    return v4;
  }
  if ( RunRef )
  {
    ExReInitializeRundownProtectionCacheAware(RunRef);
  }
  else
  {
    RunRef = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x72644D50u);
    if ( !RunRef )
      return (unsigned int)-1073741801;
  }
  v4 = NmrClientAttachProvider(
         NmrBindingHandle,
         ClientBindingContext,
         &PktMonClientDispatch,
         &ProviderBindingContext,
         (const void **)&xmmword_1C0077E88 + 1);
  if ( v4 )
    goto LABEL_3;
  if ( NmrAttachSync )
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
  *(_QWORD *)&xmmword_1C0077E88 = ProviderBindingContext;
  ((void (*)(void))qword_1C0077E78)();
  if ( NmrAttachSync )
    KeReleaseMutex(&PktMonCompMutex, 0);
  return v4;
}

```

## disassembly

```asm
0x1c005a030  mov     [rsp+arg_0], rbx
0x1c005a035  push    rdi
0x1c005a036  sub     rsp, 30h
0x1c005a03a  and     [rsp+38h+ProviderBindingContext], 0
0x1c005a040  mov     rbx, rdx
0x1c005a043  cmp     qword ptr cs:xmmword_1C0077E88+8, 0
0x1c005a04b  mov     rdi, rcx
0x1c005a04e  jz      short loc_1C005A083
0x1c005a050  mov     ebx, 0C00002B9h
0x1c005a055  mov     rcx, cs:RunRef; RunRefCacheAware
0x1c005a05c  test    rcx, rcx
0x1c005a05f  jz      short loc_1C005A075
0x1c005a061  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1c005a068  nop     dword ptr [rax+rax+00h]
0x1c005a06d  and     cs:RunRef, 0
0x1c005a075  mov     eax, ebx
0x1c005a077  mov     rbx, [rsp+38h+arg_0]
0x1c005a07c  add     rsp, 30h
0x1c005a080  pop     rdi
0x1c005a081  retn
0x1c005a083  mov     rcx, cs:RunRef; RunRefCacheAware
0x1c005a08a  test    rcx, rcx
0x1c005a08d  jnz     short loc_1C005A0B8
0x1c005a08f  mov     edx, 72644D50h; PoolTag
0x1c005a094  mov     ecx, 200h; PoolType
0x1c005a099  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1c005a0a0  nop     dword ptr [rax+rax+00h]
0x1c005a0a5  mov     cs:RunRef, rax
0x1c005a0ac  test    rax, rax
0x1c005a0af  jnz     short loc_1C005A0C4
0x1c005a0b1  mov     ebx, 0C0000017h
0x1c005a0b6  jmp     short loc_1C005A075
0x1c005a0b8  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1c005a0bf  nop     dword ptr [rax+rax+00h]
0x1c005a0c4  lea     rax, xmmword_1C0077E88+8
0x1c005a0cb  mov     rdx, rbx; ClientBindingContext
0x1c005a0ce  lea     r9, [rsp+38h+ProviderBindingContext]; ProviderBindingContext
0x1c005a0d3  mov     [rsp+38h+ProviderDispatch], rax; Timeout
0x1c005a0d8  lea     r8, PktMonClientDispatch; ClientDispatch
0x1c005a0df  mov     rcx, rdi; NmrBindingHandle
0x1c005a0e2  call    cs:__imp_NmrClientAttachProvider
0x1c005a0e9  nop     dword ptr [rax+rax+00h]
0x1c005a0ee  mov     ebx, eax
0x1c005a0f0  test    eax, eax
0x1c005a0f2  jnz     loc_1C005A055
0x1c005a0f8  cmp     cs:NmrAttachSync, al
0x1c005a0fe  jz      short loc_1C005A121
0x1c005a100  and     [rsp+38h+ProviderDispatch], 0
0x1c005a106  lea     rcx, PktMonCompMutex; Object
0x1c005a10d  xor     r9d, r9d; Alertable
0x1c005a110  xor     r8d, r8d; WaitMode
0x1c005a113  xor     edx, edx; WaitReason
0x1c005a115  call    cs:__imp_KeWaitForSingleObject
0x1c005a11c  nop     dword ptr [rax+rax+00h]
0x1c005a121  mov     rax, [rsp+38h+ProviderBindingContext]
0x1c005a126  mov     qword ptr cs:xmmword_1C0077E88, rax
0x1c005a12d  mov     rax, cs:qword_1C0077E78
0x1c005a134  call    cs:__guard_dispatch_icall_fptr
0x1c005a13a  cmp     cs:NmrAttachSync, 0
0x1c005a141  jz      loc_1C005A075
0x1c005a147  xor     edx, edx; Wait
0x1c005a149  lea     rcx, PktMonCompMutex; Mutex
0x1c005a150  call    cs:__imp_KeReleaseMutex
0x1c005a157  nop     dword ptr [rax+rax+00h]
0x1c005a15c  jmp     loc_1C005A075
```
