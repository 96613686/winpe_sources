# KsCreateFilterFactory_wrapper

- ea: `0x18006f720`
- end: `0x18006f881`
- name: `KsCreateFilterFactory_wrapper`
- size: `353`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, KSFILTER_DESCRIPTOR *Descriptor, PWSTR RefString, PSECURITY_DESCRIPTOR SecurityDescriptor, ULONG CreateItemFlags, PFNKSFILTERFACTORYPOWER SleepCallback, PFNKSFILTERFACTORYPOWER WakeCallback, PKSFILTERFACTORY *FilterFactory)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180019cb0`
- `0x180061150`
- `0x18006f720`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006f757`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006f757`

## string_xrefs

- `0x18006f76e`: `KsCreateFilterFactory should only be called at IRQL == PASSIVE_LEVEL.`
- `0x18006f7ea`: `The driver should hold the device mutex when calling KsCreateFilterFactory.`

## pseudocode

```c
NTSTATUS __fastcall KsCreateFilterFactory_wrapper(
        PDEVICE_OBJECT DeviceObject,
        KSFILTER_DESCRIPTOR *Descriptor,
        PWSTR RefString,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        ULONG CreateItemFlags,
        PFNKSFILTERFACTORYPOWER SleepCallback,
        PFNKSFILTERFACTORYPOWER WakeCallback,
        PKSFILTERFACTORY *FilterFactory)
{
  __int64 v8; // rbx
  __int64 v13; // rdi

  v8 = 0;
  v13 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)DeviceObject->DeviceExtension + 360LL) + 64LL);
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsCreateFilterFactory should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 8))(v13);
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 72))(v13);
  }
  if ( (KsXdvExtLevel & 8) != 0
    && v8
    && (!(*(_DWORD *)(v8 + 92) + *(unsigned __int8 *)(v8 + 88)) || *(struct _KTHREAD **)(v8 + 72) != KeGetCurrentThread()) )
  {
    (*(void (__fastcall **)(const char *, __int64, __int64))(KsVerifierUtilTable + 88))(
      "The driver should hold the device mutex when calling KsCreateFilterFactory.",
      528385,
      v8);
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 80))(v13);
  return KsCreateFilterFactory(
           DeviceObject,
           Descriptor,
           RefString,
           SecurityDescriptor,
           CreateItemFlags,
           SleepCallback,
           WakeCallback,
           FilterFactory);
}

```

## disassembly

```asm
0x18006f720  push    rbx
0x18006f722  push    rbp
0x18006f723  push    rsi
0x18006f724  push    rdi
0x18006f725  push    r14
0x18006f727  push    r15
0x18006f729  sub     rsp, 48h
0x18006f72d  mov     rax, [rcx+40h]
0x18006f731  xor     ebx, ebx
0x18006f733  mov     rbp, r9
0x18006f736  mov     r14, r8
0x18006f739  mov     r15, rdx
0x18006f73c  mov     rsi, rcx
0x18006f73f  mov     r10, [rax]
0x18006f742  mov     rax, [r10+168h]
0x18006f749  mov     rdi, [rax+40h]
0x18006f74d  mov     eax, cs:KsXdvExtLevel
0x18006f753  test    al, 8
0x18006f755  jz      short loc_18006F783
0x18006f757  call    cs:__imp_KeGetCurrentIrql
0x18006f75e  nop     dword ptr [rax+rax+00h]
0x18006f763  test    al, al
0x18006f765  jz      short loc_18006F783
0x18006f767  mov     rax, cs:KsVerifierUtilTable
0x18006f76e  lea     rcx, aKscreatefilter; "KsCreateFilterFactory should only be ca"...
0x18006f775  mov     edx, 81009h
0x18006f77a  mov     rax, [rax+60h]
0x18006f77e  call    _guard_dispatch_icall
0x18006f783  mov     eax, cs:KsXdvExtLevel
0x18006f789  test    al, 18h
0x18006f78b  jz      short loc_18006F7B6
0x18006f78d  mov     rax, cs:KsVerifierUtilTable
0x18006f794  mov     rcx, rdi
0x18006f797  mov     rax, [rax+8]
0x18006f79b  call    _guard_dispatch_icall
0x18006f7a0  mov     rcx, cs:KsVerifierUtilTable
0x18006f7a7  mov     rbx, rax
0x18006f7aa  mov     rax, [rcx+48h]
0x18006f7ae  mov     rcx, rdi
0x18006f7b1  call    _guard_dispatch_icall
0x18006f7b6  mov     ecx, cs:KsXdvExtLevel
0x18006f7bc  test    cl, 8
0x18006f7bf  jz      short loc_18006F813
0x18006f7c1  test    rbx, rbx
0x18006f7c4  jz      short loc_18006F813
0x18006f7c6  lea     r9, [rbx+48h]
0x18006f7ca  movzx   eax, byte ptr [r9+10h]
0x18006f7cf  add     eax, [r9+14h]
0x18006f7d3  jz      short loc_18006F7E3
0x18006f7d5  mov     rax, gs:188h
0x18006f7de  cmp     [r9], rax
0x18006f7e1  jz      short loc_18006F813
0x18006f7e3  mov     rax, cs:KsVerifierUtilTable
0x18006f7ea  lea     rcx, aTheDriverShoul_1; "The driver should hold the device mutex"...
0x18006f7f1  mov     dword ptr [rsp+78h+SleepCallback], 18h
0x18006f7f9  mov     r8, rbx
0x18006f7fc  mov     edx, 81001h
0x18006f801  mov     qword ptr [rsp+78h+CreateItemFlags], 0
0x18006f80a  mov     rax, [rax+58h]
0x18006f80e  call    _guard_dispatch_icall
0x18006f813  mov     eax, cs:KsXdvExtLevel
0x18006f819  test    al, 18h
0x18006f81b  jz      short loc_18006F830
0x18006f81d  mov     rax, cs:KsVerifierUtilTable
0x18006f824  mov     rcx, rdi
0x18006f827  mov     rax, [rax+50h]
0x18006f82b  call    _guard_dispatch_icall
0x18006f830  mov     rax, [rsp+78h+arg_38]
0x18006f838  mov     r9, rbp; SecurityDescriptor
0x18006f83b  mov     [rsp+78h+FilterFactory], rax; FilterFactory
0x18006f840  mov     r8, r14; RefString
0x18006f843  mov     rax, [rsp+78h+arg_30]
0x18006f84b  mov     rdx, r15; Descriptor
0x18006f84e  mov     [rsp+78h+WakeCallback], rax; WakeCallback
0x18006f853  mov     rcx, rsi; DeviceObject
0x18006f856  mov     rax, [rsp+78h+arg_28]
0x18006f85e  mov     [rsp+78h+SleepCallback], rax; SleepCallback
0x18006f863  mov     eax, [rsp+78h+arg_20]
0x18006f86a  mov     [rsp+78h+CreateItemFlags], eax; CreateItemFlags
0x18006f86e  call    KsCreateFilterFactory
0x18006f873  add     rsp, 48h
0x18006f877  pop     r15
0x18006f879  pop     r14
0x18006f87b  pop     rdi
0x18006f87c  pop     rsi
0x18006f87d  pop     rbp
0x18006f87e  pop     rbx
0x18006f87f  retn
```
