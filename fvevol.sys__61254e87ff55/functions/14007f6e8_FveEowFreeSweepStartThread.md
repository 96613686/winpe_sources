# FveEowFreeSweepStartThread

- ea: `0x14007f6e8`
- end: `0x14007f95d`
- name: `FveEowFreeSweepStartThread`
- size: `629`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140083304`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14007f6e8`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14007f777`
- `ntoskrnl!KeClearEvent` at `0x14007f777`
- `ntoskrnl!PsCreateSystemThread` at `0x14007f80a`
- `ntoskrnl!PsCreateSystemThread` at `0x14007f80a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007f845`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007f845`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007f755`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007f864`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007f89e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007f755`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007f864`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007f89e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007f7bd`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007f8ff`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007f7bd`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007f8ff`
- `ntoskrnl!KeSetEvent` at `0x14007f8f0`
- `ntoskrnl!KeSetEvent` at `0x14007f8f0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007f88d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007f88d`
- `ntoskrnl!KeBugCheckEx` at `0x14007f7ad`
- `ntoskrnl!KeBugCheckEx` at `0x14007f8da`
- `ntoskrnl!KeBugCheckEx` at `0x14007f7ad`
- `ntoskrnl!KeBugCheckEx` at `0x14007f8da`
- `ntoskrnl!ZwClose` at `0x14007f855`
- `ntoskrnl!ZwClose` at `0x14007f855`

## pseudocode

```c
__int64 __fastcall FveEowFreeSweepStartThread(ULONG_PTR BugCheckParameter2)
{
  NTSTATUS v1; // esi
  signed __int32 v3; // eax
  signed __int32 v4; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+90h] [rbp+20h] BYREF
  PVOID Object; // [rsp+98h] [rbp+28h] BYREF

  v1 = 0;
  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 226, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
  }
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(BugCheckParameter2 + 24));
  if ( !*(_QWORD *)(BugCheckParameter2 + 80) )
  {
    *(_QWORD *)(BugCheckParameter2 + 80) = -1;
    KeClearEvent((PRKEVENT)(BugCheckParameter2 + 88));
    v3 = _InterlockedIncrement((volatile signed __int32 *)(BugCheckParameter2 + 136));
    if ( v3 != 2 )
      KeBugCheckEx(0x120u, 0xBu, BugCheckParameter2, 0, v3);
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(BugCheckParameter2 + 24));
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v1 = PsCreateSystemThread(
           &ThreadHandle,
           0,
           &ObjectAttributes,
           0,
           0,
           FveEowFreeSweepWorker,
           (PVOID)BugCheckParameter2);
    if ( v1 < 0 )
    {
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(BugCheckParameter2 + 24));
      *(_QWORD *)(BugCheckParameter2 + 80) = 0;
      v4 = _InterlockedDecrement((volatile signed __int32 *)(BugCheckParameter2 + 136));
      if ( v4 != 1 )
        KeBugCheckEx(0x120u, 0xBu, BugCheckParameter2, 0, v4);
      KeSetEvent((PRKEVENT)(BugCheckParameter2 + 88), 0, 0);
    }
    else
    {
      Object = 0;
      ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
      ZwClose(ThreadHandle);
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(BugCheckParameter2 + 24));
      *(_QWORD *)(BugCheckParameter2 + 80) = Object;
      KeWaitForSingleObject((PVOID)(BugCheckParameter2 + 112), Executive, 0, 0, 0);
    }
  }
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(BugCheckParameter2 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 227, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids, (unsigned int)v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14007f6e8  mov     [rsp-18h+arg_10], rbx
0x14007f6ed  mov     [rsp-18h+arg_18], rsi
0x14007f6f2  push    rbp
0x14007f6f3  push    rdi
0x14007f6f4  push    r14
0x14007f6f6  mov     rbp, rsp
0x14007f6f9  sub     rsp, 70h
0x14007f6fd  xorps   xmm0, xmm0
0x14007f700  xor     esi, esi
0x14007f702  xor     eax, eax
0x14007f704  mov     rbx, rcx
0x14007f707  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14007f70b  mov     [rbp+ThreadHandle], rax
0x14007f70f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14007f713  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14007f717  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f71e  lea     rax, WPP_GLOBAL_Control
0x14007f725  cmp     rcx, rax
0x14007f728  jz      short loc_14007F74E
0x14007f72a  test    dword ptr [rcx+2Ch], 100h
0x14007f731  jz      short loc_14007F74E
0x14007f733  cmp     byte ptr [rcx+29h], 5
0x14007f737  jb      short loc_14007F74E
0x14007f739  mov     rcx, [rcx+18h]
0x14007f73d  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007f744  mov     edx, 0E2h
0x14007f749  call    WPP_SF_
0x14007f74e  lea     rdi, [rbx+18h]
0x14007f752  mov     rcx, rdi; Mutex
0x14007f755  call    cs:__imp_KeAcquireGuardedMutex
0x14007f75c  nop     dword ptr [rax+rax+00h]
0x14007f761  cmp     [rbx+50h], rsi
0x14007f765  jnz     loc_14007F8FC
0x14007f76b  lea     rcx, [rbx+58h]; Event
0x14007f76f  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x14007f777  call    cs:__imp_KeClearEvent
0x14007f77e  nop     dword ptr [rax+rax+00h]
0x14007f783  mov     eax, 1
0x14007f788  lock xadd [rbx+88h], eax
0x14007f790  inc     eax
0x14007f792  cmp     eax, 2
0x14007f795  jz      short loc_14007F7BA
0x14007f797  xor     r9d, r9d; BugCheckParameter3
0x14007f79a  cdqe
0x14007f79c  mov     r8, rbx; BugCheckParameter2
0x14007f79f  mov     [rsp+70h+BugCheckParameter4], rax; BugCheckParameter4
0x14007f7a4  mov     ecx, 120h; BugCheckCode
0x14007f7a9  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14007f7ad  call    cs:__imp_KeBugCheckEx
0x14007f7ba  mov     rcx, rdi; Mutex
0x14007f7bd  call    cs:__imp_KeReleaseGuardedMutex
0x14007f7c4  nop     dword ptr [rax+rax+00h]
0x14007f7c9  lea     rax, FveEowFreeSweepWorker
0x14007f7d0  mov     [rsp+70h+StartContext], rbx; StartContext
0x14007f7d5  xorps   xmm0, xmm0
0x14007f7d8  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14007f7dd  xor     r9d, r9d; ProcessHandle
0x14007f7e0  mov     [rsp+70h+BugCheckParameter4], rsi; ClientId
0x14007f7e5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14007f7e9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14007f7f0  xor     edx, edx; DesiredAccess
0x14007f7f2  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14007f7f6  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14007f7fa  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14007f801  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x14007f805  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14007f80a  call    cs:__imp_PsCreateSystemThread
0x14007f811  nop     dword ptr [rax+rax+00h]
0x14007f816  mov     esi, eax
0x14007f818  test    eax, eax
0x14007f81a  js      short loc_14007F89B
0x14007f81c  mov     rcx, [rbp+ThreadHandle]; Handle
0x14007f820  lea     rax, [rbp+Object]
0x14007f824  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x14007f82d  xor     r9d, r9d; AccessMode
0x14007f830  xor     r8d, r8d; ObjectType
0x14007f833  mov     [rsp+70h+BugCheckParameter4], rax; Object
0x14007f838  mov     edx, 1FFFFFh; DesiredAccess
0x14007f83d  mov     [rbp+Object], 0
0x14007f845  call    cs:__imp_ObReferenceObjectByHandle
0x14007f84c  nop     dword ptr [rax+rax+00h]
0x14007f851  mov     rcx, [rbp+ThreadHandle]; Handle
0x14007f855  call    cs:__imp_ZwClose
0x14007f85c  nop     dword ptr [rax+rax+00h]
0x14007f861  mov     rcx, rdi; Mutex
0x14007f864  call    cs:__imp_KeAcquireGuardedMutex
0x14007f86b  nop     dword ptr [rax+rax+00h]
0x14007f870  mov     rax, [rbp+Object]
0x14007f874  lea     rcx, [rbx+70h]; Object
0x14007f878  xor     r9d, r9d; Alertable
0x14007f87b  mov     [rbx+50h], rax
0x14007f87f  xor     r8d, r8d; WaitMode
0x14007f882  mov     [rsp+70h+BugCheckParameter4], 0; Timeout
0x14007f88b  xor     edx, edx; WaitReason
0x14007f88d  call    cs:__imp_KeWaitForSingleObject
0x14007f894  nop     dword ptr [rax+rax+00h]
0x14007f899  jmp     short loc_14007F8FC
0x14007f89b  mov     rcx, rdi; Mutex
0x14007f89e  call    cs:__imp_KeAcquireGuardedMutex
0x14007f8a5  nop     dword ptr [rax+rax+00h]
0x14007f8aa  or      eax, 0FFFFFFFFh
0x14007f8ad  mov     qword ptr [rbx+50h], 0
0x14007f8b5  lock xadd [rbx+88h], eax
0x14007f8bd  dec     eax
0x14007f8bf  cmp     eax, 1
0x14007f8c2  jz      short loc_14007F8E7
0x14007f8c4  xor     r9d, r9d; BugCheckParameter3
0x14007f8c7  cdqe
0x14007f8c9  mov     r8, rbx; BugCheckParameter2
0x14007f8cc  mov     [rsp+70h+BugCheckParameter4], rax; BugCheckParameter4
0x14007f8d1  mov     ecx, 120h; BugCheckCode
0x14007f8d6  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14007f8da  call    cs:__imp_KeBugCheckEx
0x14007f8e7  xor     r8d, r8d; Wait
0x14007f8ea  lea     rcx, [rbx+58h]; Event
0x14007f8ee  xor     edx, edx; Increment
0x14007f8f0  call    cs:__imp_KeSetEvent
0x14007f8f7  nop     dword ptr [rax+rax+00h]
0x14007f8fc  mov     rcx, rdi; Mutex
0x14007f8ff  call    cs:__imp_KeReleaseGuardedMutex
0x14007f906  nop     dword ptr [rax+rax+00h]
0x14007f90b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f912  lea     rax, WPP_GLOBAL_Control
0x14007f919  cmp     rcx, rax
0x14007f91c  jz      short loc_14007F945
0x14007f91e  test    dword ptr [rcx+2Ch], 100h
0x14007f925  jz      short loc_14007F945
0x14007f927  cmp     byte ptr [rcx+29h], 5
0x14007f92b  jb      short loc_14007F945
0x14007f92d  mov     rcx, [rcx+18h]
0x14007f931  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007f938  mov     edx, 0E3h
0x14007f93d  mov     r9d, esi
0x14007f940  call    WPP_SF_d
0x14007f945  lea     r11, [rsp+70h+var_s0]
0x14007f94a  mov     eax, esi
0x14007f94c  mov     rbx, [r11+30h]
0x14007f950  mov     rsi, [r11+38h]
0x14007f954  mov     rsp, r11
0x14007f957  pop     r14
0x14007f959  pop     rdi
0x14007f95a  pop     rbp
0x14007f95b  retn
```
