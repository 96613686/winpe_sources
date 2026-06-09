# FveEowFreeSweepStartThread

- ea: `0x14007d648`
- end: `0x14007d8bd`
- name: `FveEowFreeSweepStartThread`
- size: `629`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140081264`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14007d648`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14007d6d7`
- `ntoskrnl!KeClearEvent` at `0x14007d6d7`
- `ntoskrnl!PsCreateSystemThread` at `0x14007d76a`
- `ntoskrnl!PsCreateSystemThread` at `0x14007d76a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007d7a5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007d7a5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007d6b5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007d7c4`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007d7fe`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007d6b5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007d7c4`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007d7fe`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007d71d`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007d85f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007d71d`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007d85f`
- `ntoskrnl!KeSetEvent` at `0x14007d850`
- `ntoskrnl!KeSetEvent` at `0x14007d850`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007d7ed`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007d7ed`
- `ntoskrnl!KeBugCheckEx` at `0x14007d70d`
- `ntoskrnl!KeBugCheckEx` at `0x14007d83a`
- `ntoskrnl!KeBugCheckEx` at `0x14007d70d`
- `ntoskrnl!KeBugCheckEx` at `0x14007d83a`
- `ntoskrnl!ZwClose` at `0x14007d7b5`
- `ntoskrnl!ZwClose` at `0x14007d7b5`

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
0x14007d648  mov     [rsp-18h+arg_10], rbx
0x14007d64d  mov     [rsp-18h+arg_18], rsi
0x14007d652  push    rbp
0x14007d653  push    rdi
0x14007d654  push    r14
0x14007d656  mov     rbp, rsp
0x14007d659  sub     rsp, 70h
0x14007d65d  xorps   xmm0, xmm0
0x14007d660  xor     esi, esi
0x14007d662  xor     eax, eax
0x14007d664  mov     rbx, rcx
0x14007d667  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14007d66b  mov     [rbp+ThreadHandle], rax
0x14007d66f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14007d673  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14007d677  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d67e  lea     rax, WPP_GLOBAL_Control
0x14007d685  cmp     rcx, rax
0x14007d688  jz      short loc_14007D6AE
0x14007d68a  test    dword ptr [rcx+2Ch], 100h
0x14007d691  jz      short loc_14007D6AE
0x14007d693  cmp     byte ptr [rcx+29h], 5
0x14007d697  jb      short loc_14007D6AE
0x14007d699  mov     rcx, [rcx+18h]
0x14007d69d  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007d6a4  mov     edx, 0E2h
0x14007d6a9  call    WPP_SF_
0x14007d6ae  lea     rdi, [rbx+18h]
0x14007d6b2  mov     rcx, rdi; Mutex
0x14007d6b5  call    cs:__imp_KeAcquireGuardedMutex
0x14007d6bc  nop     dword ptr [rax+rax+00h]
0x14007d6c1  cmp     [rbx+50h], rsi
0x14007d6c5  jnz     loc_14007D85C
0x14007d6cb  lea     rcx, [rbx+58h]; Event
0x14007d6cf  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x14007d6d7  call    cs:__imp_KeClearEvent
0x14007d6de  nop     dword ptr [rax+rax+00h]
0x14007d6e3  mov     eax, 1
0x14007d6e8  lock xadd [rbx+88h], eax
0x14007d6f0  inc     eax
0x14007d6f2  cmp     eax, 2
0x14007d6f5  jz      short loc_14007D71A
0x14007d6f7  xor     r9d, r9d; BugCheckParameter3
0x14007d6fa  cdqe
0x14007d6fc  mov     r8, rbx; BugCheckParameter2
0x14007d6ff  mov     [rsp+70h+BugCheckParameter4], rax; BugCheckParameter4
0x14007d704  mov     ecx, 120h; BugCheckCode
0x14007d709  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14007d70d  call    cs:__imp_KeBugCheckEx
0x14007d71a  mov     rcx, rdi; Mutex
0x14007d71d  call    cs:__imp_KeReleaseGuardedMutex
0x14007d724  nop     dword ptr [rax+rax+00h]
0x14007d729  lea     rax, FveEowFreeSweepWorker
0x14007d730  mov     [rsp+70h+StartContext], rbx; StartContext
0x14007d735  xorps   xmm0, xmm0
0x14007d738  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14007d73d  xor     r9d, r9d; ProcessHandle
0x14007d740  mov     [rsp+70h+BugCheckParameter4], rsi; ClientId
0x14007d745  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14007d749  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14007d750  xor     edx, edx; DesiredAccess
0x14007d752  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14007d756  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14007d75a  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14007d761  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x14007d765  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14007d76a  call    cs:__imp_PsCreateSystemThread
0x14007d771  nop     dword ptr [rax+rax+00h]
0x14007d776  mov     esi, eax
0x14007d778  test    eax, eax
0x14007d77a  js      short loc_14007D7FB
0x14007d77c  mov     rcx, [rbp+ThreadHandle]; Handle
0x14007d780  lea     rax, [rbp+Object]
0x14007d784  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x14007d78d  xor     r9d, r9d; AccessMode
0x14007d790  xor     r8d, r8d; ObjectType
0x14007d793  mov     [rsp+70h+BugCheckParameter4], rax; Object
0x14007d798  mov     edx, 1FFFFFh; DesiredAccess
0x14007d79d  mov     [rbp+Object], 0
0x14007d7a5  call    cs:__imp_ObReferenceObjectByHandle
0x14007d7ac  nop     dword ptr [rax+rax+00h]
0x14007d7b1  mov     rcx, [rbp+ThreadHandle]; Handle
0x14007d7b5  call    cs:__imp_ZwClose
0x14007d7bc  nop     dword ptr [rax+rax+00h]
0x14007d7c1  mov     rcx, rdi; Mutex
0x14007d7c4  call    cs:__imp_KeAcquireGuardedMutex
0x14007d7cb  nop     dword ptr [rax+rax+00h]
0x14007d7d0  mov     rax, [rbp+Object]
0x14007d7d4  lea     rcx, [rbx+70h]; Object
0x14007d7d8  xor     r9d, r9d; Alertable
0x14007d7db  mov     [rbx+50h], rax
0x14007d7df  xor     r8d, r8d; WaitMode
0x14007d7e2  mov     [rsp+70h+BugCheckParameter4], 0; Timeout
0x14007d7eb  xor     edx, edx; WaitReason
0x14007d7ed  call    cs:__imp_KeWaitForSingleObject
0x14007d7f4  nop     dword ptr [rax+rax+00h]
0x14007d7f9  jmp     short loc_14007D85C
0x14007d7fb  mov     rcx, rdi; Mutex
0x14007d7fe  call    cs:__imp_KeAcquireGuardedMutex
0x14007d805  nop     dword ptr [rax+rax+00h]
0x14007d80a  or      eax, 0FFFFFFFFh
0x14007d80d  mov     qword ptr [rbx+50h], 0
0x14007d815  lock xadd [rbx+88h], eax
0x14007d81d  dec     eax
0x14007d81f  cmp     eax, 1
0x14007d822  jz      short loc_14007D847
0x14007d824  xor     r9d, r9d; BugCheckParameter3
0x14007d827  cdqe
0x14007d829  mov     r8, rbx; BugCheckParameter2
0x14007d82c  mov     [rsp+70h+BugCheckParameter4], rax; BugCheckParameter4
0x14007d831  mov     ecx, 120h; BugCheckCode
0x14007d836  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14007d83a  call    cs:__imp_KeBugCheckEx
0x14007d847  xor     r8d, r8d; Wait
0x14007d84a  lea     rcx, [rbx+58h]; Event
0x14007d84e  xor     edx, edx; Increment
0x14007d850  call    cs:__imp_KeSetEvent
0x14007d857  nop     dword ptr [rax+rax+00h]
0x14007d85c  mov     rcx, rdi; Mutex
0x14007d85f  call    cs:__imp_KeReleaseGuardedMutex
0x14007d866  nop     dword ptr [rax+rax+00h]
0x14007d86b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d872  lea     rax, WPP_GLOBAL_Control
0x14007d879  cmp     rcx, rax
0x14007d87c  jz      short loc_14007D8A5
0x14007d87e  test    dword ptr [rcx+2Ch], 100h
0x14007d885  jz      short loc_14007D8A5
0x14007d887  cmp     byte ptr [rcx+29h], 5
0x14007d88b  jb      short loc_14007D8A5
0x14007d88d  mov     rcx, [rcx+18h]
0x14007d891  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007d898  mov     edx, 0E3h
0x14007d89d  mov     r9d, esi
0x14007d8a0  call    WPP_SF_d
0x14007d8a5  lea     r11, [rsp+70h+var_s0]
0x14007d8aa  mov     eax, esi
0x14007d8ac  mov     rbx, [r11+30h]
0x14007d8b0  mov     rsi, [r11+38h]
0x14007d8b4  mov     rsp, r11
0x14007d8b7  pop     r14
0x14007d8b9  pop     rdi
0x14007d8ba  pop     rbp
0x14007d8bb  retn
```
