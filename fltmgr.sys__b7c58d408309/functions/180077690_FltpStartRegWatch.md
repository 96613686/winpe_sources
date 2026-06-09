# FltpStartRegWatch

- ea: `0x180077690`
- end: `0x18007782c`
- name: `FltpStartRegWatch`
- size: `412`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180089078`

## callees

- `0x180009f20`
- `0x180024880`
- `0x180050fec`
- `0x180077690`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18007774e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007774e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077804`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077804`
- `ntoskrnl!ZwOpenKey` at `0x1800776d9`
- `ntoskrnl!ZwOpenKey` at `0x1800776d9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007775f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007775f`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1800777ae`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1800777ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800777f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800777f8`
- `ntoskrnl!ExInitializeResourceLite` at `0x180077718`
- `ntoskrnl!ExInitializeResourceLite` at `0x180077718`

## pseudocode

```c
__int64 FltpStartRegWatch()
{
  unsigned int v0; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF
  OBJECT_ATTRIBUTES v3; // [rsp+60h] [rbp-38h] BYREF

  *(_QWORD *)&v3.Length = 48;
  v3.ObjectName = (PUNICODE_STRING)L"|~";
  *(_QWORD *)&v3.Attributes = 576;
  v3.RootDirectory = 0;
  *(_OWORD *)&v3.SecurityDescriptor = 0;
  v0 = ZwOpenKey(&KeyHandle, 0x10u, &v3);
  if ( (int)FltpDbgStatus(v0) >= 0 )
  {
    ExInitializeResourceLite(&FltpDynamicConfigRegWatchContext);
    qword_1800404A8 = (__int64)&FltpDynamicConfigRegWatchContext;
    qword_1800404A0 = (__int64)FltpRegWatchCallback;
    qword_1800404B0 = (__int64)FltpUpdateDynamicRegistrySettings;
    *(_QWORD *)ApcRoutine = 0;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&FltpDynamicConfigRegWatchContext, 1u);
    IoStatusBlock = 0;
    v0 = ZwNotifyChangeKey(KeyHandle, 0, ApcRoutine, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
    if ( (int)FltpDbgStatus(v0) < 0 )
    {
      FltpCleanupRegWatch();
    }
    else
    {
      v0 = 0;
      dword_1800404B8 = 0;
      ((void (__fastcall *)(struct _ERESOURCE *))qword_1800404B0)(&FltpDynamicConfigRegWatchContext);
    }
    ExReleaseResourceLite(&FltpDynamicConfigRegWatchContext);
    KeLeaveCriticalRegion();
  }
  return v0;
}

```

## disassembly

```asm
0x180077690  mov     r11, rsp
0x180077693  mov     [r11+10h], rbx
0x180077697  push    rdi
0x180077698  sub     rsp, 90h
0x18007769f  lea     rax, FileSystemRegKeyName; "|~"
0x1800776a6  mov     qword ptr [r11-38h], 30h ; '0'
0x1800776ae  xorps   xmm0, xmm0
0x1800776b1  mov     [r11-28h], rax
0x1800776b5  xor     edi, edi
0x1800776b7  mov     qword ptr [r11-20h], 240h
0x1800776bf  lea     r8, [r11-38h]; ObjectAttributes
0x1800776c3  mov     [r11-30h], rdi
0x1800776c7  mov     edx, 10h; DesiredAccess
0x1800776cc  lea     rcx, KeyHandle; KeyHandle
0x1800776d3  movdqu  xmmword ptr [r11-18h], xmm0
0x1800776d9  call    cs:__imp_ZwOpenKey
0x1800776e0  nop     dword ptr [rax+rax+00h]
0x1800776e5  mov     r8d, 310Fh
0x1800776eb  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800776f2  mov     ecx, eax
0x1800776f4  xor     r9d, r9d
0x1800776f7  mov     ebx, eax
0x1800776f9  call    FltpDbgStatus
0x1800776fe  test    eax, eax
0x180077700  js      loc_180077818
0x180077706  mov     [rsp+98h+arg_0], rsi
0x18007770e  lea     rsi, FltpDynamicConfigRegWatchContext
0x180077715  mov     rcx, rsi; Resource
0x180077718  call    cs:__imp_ExInitializeResourceLite
0x18007771f  nop     dword ptr [rax+rax+00h]
0x180077724  lea     rax, FltpRegWatchCallback
0x18007772b  mov     cs:qword_1800404A8, rsi
0x180077732  mov     cs:qword_1800404A0, rax
0x180077739  lea     rax, FltpUpdateDynamicRegistrySettings
0x180077740  mov     cs:qword_1800404B0, rax
0x180077747  mov     cs:ApcRoutine, rdi
0x18007774e  call    cs:__imp_KeEnterCriticalRegion
0x180077755  nop     dword ptr [rax+rax+00h]
0x18007775a  mov     dl, 1; Wait
0x18007775c  mov     rcx, rsi; Resource
0x18007775f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180077766  nop     dword ptr [rax+rax+00h]
0x18007776b  mov     rcx, cs:KeyHandle; KeyHandle
0x180077772  lea     rax, [rsp+98h+var_48]
0x180077777  mov     [rsp+98h+Asynchronous], 1; Asynchronous
0x18007777c  lea     r8, ApcRoutine; ApcRoutine
0x180077783  mov     [rsp+98h+BufferSize], edi; BufferSize
0x180077787  xorps   xmm0, xmm0
0x18007778a  mov     [rsp+98h+Buffer], rdi; Buffer
0x18007778f  mov     r9d, 1; ApcContext
0x180077795  mov     [rsp+98h+WatchTree], 1; WatchTree
0x18007779a  xor     edx, edx; Event
0x18007779c  mov     [rsp+98h+CompletionFilter], 5; CompletionFilter
0x1800777a4  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x1800777a9  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x1800777ae  call    cs:__imp_ZwNotifyChangeKey
0x1800777b5  nop     dword ptr [rax+rax+00h]
0x1800777ba  mov     r8d, 312Ch
0x1800777c0  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800777c7  mov     ecx, eax
0x1800777c9  xor     r9d, r9d
0x1800777cc  mov     ebx, eax
0x1800777ce  call    FltpDbgStatus
0x1800777d3  test    eax, eax
0x1800777d5  js      short loc_1800777F0
0x1800777d7  mov     rax, cs:qword_1800404B0
0x1800777de  mov     rcx, rsi
0x1800777e1  mov     ebx, edi
0x1800777e3  mov     cs:dword_1800404B8, edi
0x1800777e9  call    _guard_dispatch_icall
0x1800777ee  jmp     short loc_1800777F5
0x1800777f0  call    FltpCleanupRegWatch
0x1800777f5  mov     rcx, rsi; Resource
0x1800777f8  call    cs:__imp_ExReleaseResourceLite
0x1800777ff  nop     dword ptr [rax+rax+00h]
0x180077804  call    cs:__imp_KeLeaveCriticalRegion
0x18007780b  nop     dword ptr [rax+rax+00h]
0x180077810  mov     rsi, [rsp+98h+arg_0]
0x180077818  mov     eax, ebx
0x18007781a  mov     rbx, [rsp+98h+arg_8]
0x180077822  add     rsp, 90h
0x180077829  pop     rdi
0x18007782a  retn
```
