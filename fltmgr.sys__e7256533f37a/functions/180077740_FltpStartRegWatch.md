# FltpStartRegWatch

- ea: `0x180077740`
- end: `0x1800778dc`
- name: `FltpStartRegWatch`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18008c078`

## callees

- `0x180009f20`
- `0x1800248e0`
- `0x180050fec`
- `0x180077740`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800777fe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800777fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800778b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800778b4`
- `ntoskrnl!ZwOpenKey` at `0x180077789`
- `ntoskrnl!ZwOpenKey` at `0x180077789`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007780f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007780f`
- `ntoskrnl!ZwNotifyChangeKey` at `0x18007785e`
- `ntoskrnl!ZwNotifyChangeKey` at `0x18007785e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800778a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800778a8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800777c8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800777c8`

## pseudocode

```c
__int64 FltpStartRegWatch()
{
  __int64 v0; // rbx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF
  OBJECT_ATTRIBUTES v3; // [rsp+60h] [rbp-38h] BYREF

  *(_QWORD *)&v3.Length = 48;
  v3.ObjectName = (PUNICODE_STRING)L"|~";
  *(_QWORD *)&v3.Attributes = 576;
  v3.RootDirectory = 0;
  *(_OWORD *)&v3.SecurityDescriptor = 0;
  LODWORD(v0) = ZwOpenKey(&KeyHandle, 0x10u, &v3);
  if ( (int)FltpDbgStatus((unsigned int)v0, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 12559, 0) >= 0 )
  {
    ExInitializeResourceLite(&FltpDynamicConfigRegWatchContext);
    qword_180040A28 = (__int64)&FltpDynamicConfigRegWatchContext;
    qword_180040A20 = (__int64)FltpRegWatchCallback;
    qword_180040A30 = (__int64)FltpUpdateDynamicRegistrySettings;
    *(_QWORD *)ApcRoutine = 0;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&FltpDynamicConfigRegWatchContext, 1u);
    IoStatusBlock = 0;
    v0 = (unsigned int)ZwNotifyChangeKey(KeyHandle, 0, ApcRoutine, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
    if ( (int)FltpDbgStatus(v0, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 12588, 0) < 0 )
    {
      FltpCleanupRegWatch();
    }
    else
    {
      LODWORD(v0) = 0;
      dword_180040A38 = 0;
      ((void (__fastcall *)(struct _ERESOURCE *))qword_180040A30)(&FltpDynamicConfigRegWatchContext);
    }
    ExReleaseResourceLite(&FltpDynamicConfigRegWatchContext);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180077740  mov     r11, rsp
0x180077743  mov     [r11+10h], rbx
0x180077747  push    rdi
0x180077748  sub     rsp, 90h
0x18007774f  lea     rax, FileSystemRegKeyName; "|~"
0x180077756  mov     qword ptr [r11-38h], 30h ; '0'
0x18007775e  xorps   xmm0, xmm0
0x180077761  mov     [r11-28h], rax
0x180077765  xor     edi, edi
0x180077767  mov     qword ptr [r11-20h], 240h
0x18007776f  lea     r8, [r11-38h]; ObjectAttributes
0x180077773  mov     [r11-30h], rdi
0x180077777  mov     edx, 10h; DesiredAccess
0x18007777c  lea     rcx, KeyHandle; KeyHandle
0x180077783  movdqu  xmmword ptr [r11-18h], xmm0
0x180077789  call    cs:__imp_ZwOpenKey
0x180077790  nop     dword ptr [rax+rax+00h]
0x180077795  mov     r8d, 310Fh
0x18007779b  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800777a2  mov     ecx, eax
0x1800777a4  xor     r9d, r9d
0x1800777a7  mov     ebx, eax
0x1800777a9  call    FltpDbgStatus
0x1800777ae  test    eax, eax
0x1800777b0  js      loc_1800778C8
0x1800777b6  mov     [rsp+98h+arg_0], rsi
0x1800777be  lea     rsi, FltpDynamicConfigRegWatchContext
0x1800777c5  mov     rcx, rsi; Resource
0x1800777c8  call    cs:__imp_ExInitializeResourceLite
0x1800777cf  nop     dword ptr [rax+rax+00h]
0x1800777d4  lea     rax, FltpRegWatchCallback
0x1800777db  mov     cs:qword_180040A28, rsi
0x1800777e2  mov     cs:qword_180040A20, rax
0x1800777e9  lea     rax, FltpUpdateDynamicRegistrySettings
0x1800777f0  mov     cs:qword_180040A30, rax
0x1800777f7  mov     cs:ApcRoutine, rdi
0x1800777fe  call    cs:__imp_KeEnterCriticalRegion
0x180077805  nop     dword ptr [rax+rax+00h]
0x18007780a  mov     dl, 1; Wait
0x18007780c  mov     rcx, rsi; Resource
0x18007780f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180077816  nop     dword ptr [rax+rax+00h]
0x18007781b  mov     rcx, cs:KeyHandle; KeyHandle
0x180077822  lea     rax, [rsp+98h+var_48]
0x180077827  mov     [rsp+98h+Asynchronous], 1; Asynchronous
0x18007782c  lea     r8, ApcRoutine; ApcRoutine
0x180077833  mov     [rsp+98h+BufferSize], edi; BufferSize
0x180077837  xorps   xmm0, xmm0
0x18007783a  mov     [rsp+98h+Buffer], rdi; Buffer
0x18007783f  mov     r9d, 1; ApcContext
0x180077845  mov     [rsp+98h+WatchTree], 1; WatchTree
0x18007784a  xor     edx, edx; Event
0x18007784c  mov     [rsp+98h+CompletionFilter], 5; CompletionFilter
0x180077854  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180077859  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18007785e  call    cs:__imp_ZwNotifyChangeKey
0x180077865  nop     dword ptr [rax+rax+00h]
0x18007786a  mov     r8d, 312Ch
0x180077870  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x180077877  mov     ecx, eax
0x180077879  xor     r9d, r9d
0x18007787c  mov     ebx, eax
0x18007787e  call    FltpDbgStatus
0x180077883  test    eax, eax
0x180077885  js      short loc_1800778A0
0x180077887  mov     rax, cs:qword_180040A30
0x18007788e  mov     rcx, rsi
0x180077891  mov     ebx, edi
0x180077893  mov     cs:dword_180040A38, edi
0x180077899  call    _guard_dispatch_icall
0x18007789e  jmp     short loc_1800778A5
0x1800778a0  call    FltpCleanupRegWatch
0x1800778a5  mov     rcx, rsi; Resource
0x1800778a8  call    cs:__imp_ExReleaseResourceLite
0x1800778af  nop     dword ptr [rax+rax+00h]
0x1800778b4  call    cs:__imp_KeLeaveCriticalRegion
0x1800778bb  nop     dword ptr [rax+rax+00h]
0x1800778c0  mov     rsi, [rsp+98h+arg_0]
0x1800778c8  mov     eax, ebx
0x1800778ca  mov     rbx, [rsp+98h+arg_8]
0x1800778d2  add     rsp, 90h
0x1800778d9  pop     rdi
0x1800778da  retn
```
