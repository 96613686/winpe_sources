# MupInitPrefixCache

- ea: `0x140010774`
- end: `0x1400108e7`
- name: `MupInitPrefixCache`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140010f18`

## callees

- `0x140010774`
- `0x140010c94`
- `0x140010d68`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x14001081d`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001081d`
- `ntoskrnl!KeInitializeDpc` at `0x14001080e`
- `ntoskrnl!KeInitializeDpc` at `0x14001080e`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400107f1`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400107f1`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x1400107b3`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x1400107b3`
- `ntoskrnl!ZwOpenKey` at `0x14001087e`
- `ntoskrnl!ZwOpenKey` at `0x14001087e`

## pseudocode

```c
__int64 MupInitPrefixCache()
{
  struct _DEVICE_OBJECT *v0; // rbx
  bool v1; // di
  int PrefixCacheTimeoutFromRegistry; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF

  v0 = (struct _DEVICE_OBJECT *)MupDeviceObject;
  WPP_MAIN_CB.Reserved = (PVOID)0x100507102LL;
  memset(&ObjectAttributes, 0, 44);
  v1 = 1;
  RtlInitializeUnicodePrefix((PUNICODE_PREFIX_TABLE)(&WPP_MAIN_CB.Reserved + 1));
  dword_14000A9FC = 0;
  qword_14000A9E8 = (__int64)&qword_14000A9E0;
  qword_14000A9E0 = (__int64)&qword_14000A9E0;
  dword_14000AA08 = 0;
  KeInitializeTimerEx(&MupiPrefixGarbageCollectionTimer, NotificationTimer);
  KeInitializeDpc(&MupiPrefixGarbageCollectionDpc, MupiPrefixGarbageCollectionDpcHandler, 0);
  pMupiPrefixGarbageCollectionWorkItem = IoAllocateWorkItem(v0);
  if ( !pMupiPrefixGarbageCollectionWorkItem )
    return 3221225495LL;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&WPP_MAIN_CB.Dpc.DeferredRoutine;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey((PHANDLE)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, 0x20019u, &ObjectAttributes) < 0
    || (MupiMupServicesKeyHandleValid = 1,
        PrefixCacheTimeoutFromRegistry = MupiReadPrefixCacheTimeoutFromRegistry(&qword_14000A9F0),
        v1 = (unsigned int)MupiReadPrefixCacheMaxSizeFromRegistry(&dword_14000A9F8) != 0,
        PrefixCacheTimeoutFromRegistry) )
  {
    qword_14000A9F0 = 9000000000LL;
  }
  if ( v1 )
    dword_14000A9F8 = 0x4000;
  return 0;
}

```

## disassembly

```asm
0x140010774  mov     [rsp+arg_0], rbx
0x140010779  push    rdi
0x14001077a  sub     rsp, 50h
0x14001077e  mov     rbx, cs:MupDeviceObject
0x140010785  lea     rcx, WPP_MAIN_CB+148h; PrefixTable
0x14001078c  xorps   xmm0, xmm0
0x14001078f  mov     dword ptr cs:WPP_MAIN_CB.Reserved, 507102h
0x140010799  xor     eax, eax
0x14001079b  movups  xmmword ptr [rsp+58h+ObjectAttributes.ObjectName], xmm0
0x1400107a0  movups  xmmword ptr [rsp+58h+ObjectAttributes.Length], xmm0
0x1400107a5  lea     edi, [rax+1]
0x1400107a8  mov     dword ptr cs:WPP_MAIN_CB.Reserved+4, edi
0x1400107ae  movups  xmmword ptr [rsp+58h+ObjectAttributes+1Ch], xmm0
0x1400107b3  call    cs:__imp_RtlInitializeUnicodePrefix
0x1400107ba  nop     dword ptr [rax+rax+00h]
0x1400107bf  lea     rax, qword_14000A9E0
0x1400107c6  mov     cs:dword_14000A9FC, 0
0x1400107d0  xor     edx, edx; Type
0x1400107d2  mov     cs:qword_14000A9E8, rax
0x1400107d9  lea     rcx, MupiPrefixGarbageCollectionTimer; Timer
0x1400107e0  mov     cs:qword_14000A9E0, rax
0x1400107e7  mov     cs:dword_14000AA08, 0
0x1400107f1  call    cs:__imp_KeInitializeTimerEx
0x1400107f8  nop     dword ptr [rax+rax+00h]
0x1400107fd  xor     r8d, r8d; DeferredContext
0x140010800  lea     rdx, MupiPrefixGarbageCollectionDpcHandler; DeferredRoutine
0x140010807  lea     rcx, MupiPrefixGarbageCollectionDpc; Dpc
0x14001080e  call    cs:__imp_KeInitializeDpc
0x140010815  nop     dword ptr [rax+rax+00h]
0x14001081a  mov     rcx, rbx; DeviceObject
0x14001081d  call    cs:__imp_IoAllocateWorkItem
0x140010824  nop     dword ptr [rax+rax+00h]
0x140010829  mov     cs:pMupiPrefixGarbageCollectionWorkItem, rax
0x140010830  test    rax, rax
0x140010833  jnz     short loc_14001083F
0x140010835  mov     eax, 0C0000017h
0x14001083a  jmp     loc_1400108DB
0x14001083f  lea     rax, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140010846  mov     [rsp+58h+ObjectAttributes.Length], 30h ; '0'
0x14001084e  xorps   xmm0, xmm0
0x140010851  mov     [rsp+58h+ObjectAttributes.ObjectName], rax
0x140010856  lea     r8, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x14001085b  mov     [rsp+58h+ObjectAttributes.RootDirectory], 0
0x140010864  mov     edx, 20019h; DesiredAccess
0x140010869  mov     [rsp+58h+ObjectAttributes.Attributes], 240h
0x140010871  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; KeyHandle
0x140010878  movdqu  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001087e  call    cs:__imp_ZwOpenKey
0x140010885  nop     dword ptr [rax+rax+00h]
0x14001088a  test    eax, eax
0x14001088c  js      short loc_1400108B9
0x14001088e  lea     rcx, qword_14000A9F0
0x140010895  mov     cs:MupiMupServicesKeyHandleValid, dil
0x14001089c  call    MupiReadPrefixCacheTimeoutFromRegistry
0x1400108a1  lea     rcx, dword_14000A9F8
0x1400108a8  mov     ebx, eax
0x1400108aa  call    MupiReadPrefixCacheMaxSizeFromRegistry
0x1400108af  test    eax, eax
0x1400108b1  setnz   dil
0x1400108b5  test    ebx, ebx
0x1400108b7  jz      short loc_1400108CA
0x1400108b9  mov     rax, 218711A00h
0x1400108c3  mov     cs:qword_14000A9F0, rax
0x1400108ca  test    dil, dil
0x1400108cd  jz      short loc_1400108D9
0x1400108cf  mov     cs:dword_14000A9F8, 4000h
0x1400108d9  xor     eax, eax
0x1400108db  mov     rbx, [rsp+58h+arg_0]
0x1400108e0  add     rsp, 50h
0x1400108e4  pop     rdi
0x1400108e5  retn
```
