# LuafvInitializeUsn

- ea: `0x140024cac`
- end: `0x140024f77`
- name: `LuafvInitializeUsn`
- size: `715`
- prototype: `NTSTATUS __fastcall(char *StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140021e40`

## callees

- `0x140006000`
- `0x1400140b4`
- `0x140024cac`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140024f1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f4a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f4a`
- `ntoskrnl!PsCreateSystemThread` at `0x140024eb6`
- `ntoskrnl!PsCreateSystemThread` at `0x140024eb6`
- `ntoskrnl!ExInitializePushLock` at `0x140024cce`
- `ntoskrnl!ExInitializePushLock` at `0x140024cce`
- `ntoskrnl!ZwClose` at `0x140024ef9`
- `ntoskrnl!ZwClose` at `0x140024ef9`
- `ntoskrnl!KeInitializeEvent` at `0x140024ced`
- `ntoskrnl!KeInitializeEvent` at `0x140024d02`
- `ntoskrnl!KeInitializeEvent` at `0x140024d1e`
- `ntoskrnl!KeInitializeEvent` at `0x140024d36`
- `ntoskrnl!KeInitializeEvent` at `0x140024d4e`
- `ntoskrnl!KeInitializeEvent` at `0x140024d66`
- `ntoskrnl!KeInitializeEvent` at `0x140024ced`
- `ntoskrnl!KeInitializeEvent` at `0x140024d02`
- `ntoskrnl!KeInitializeEvent` at `0x140024d1e`
- `ntoskrnl!KeInitializeEvent` at `0x140024d36`
- `ntoskrnl!KeInitializeEvent` at `0x140024d4e`
- `ntoskrnl!KeInitializeEvent` at `0x140024d66`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140024ee8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140024ee8`
- `ntoskrnl!ObfDereferenceObject` at `0x140024f59`
- `ntoskrnl!ObfDereferenceObject` at `0x140024f59`
- `ntoskrnl!ExAllocatePool2` at `0x140024df6`
- `ntoskrnl!ExAllocatePool2` at `0x140024df6`
- `FLTMGR!FltReleasePushLockEx` at `0x140024e40`
- `FLTMGR!FltReleasePushLockEx` at `0x140024e40`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140024e21`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140024e21`

## pseudocode

```c
NTSTATUS __fastcall LuafvInitializeUsn(char *StartContext)
{
  _QWORD *v2; // r8
  unsigned int v3; // edx
  char *v4; // r9
  char *v5; // rax
  __int64 v6; // rcx
  char *v7; // rcx
  __int64 Pool2; // rax
  __int64 v9; // rdi
  void *v10; // rcx
  NTSTATUS result; // eax
  PVOID *v12; // rdi
  void *ThreadHandle; // [rsp+50h] [rbp+8h] BYREF

  ThreadHandle = 0;
  ExInitializePushLock((PULONG_PTR)StartContext + 33);
  *((_DWORD *)StartContext + 208) = 0;
  KeInitializeEvent((PRKEVENT)(StartContext + 88), NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)(StartContext + 112), NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)(StartContext + 136), SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)(StartContext + 160), NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)(StartContext + 184), SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)(StartContext + 208), NotificationEvent, 0);
  v2 = StartContext + 816;
  v3 = 0;
  v4 = StartContext + 816;
  *((_QWORD *)StartContext + 99) = StartContext + 784;
  *((_QWORD *)StartContext + 98) = StartContext + 784;
  *((_QWORD *)StartContext + 101) = StartContext + 800;
  *((_QWORD *)StartContext + 100) = StartContext + 800;
  v5 = StartContext + 816;
  *((_QWORD *)StartContext + 103) = StartContext + 816;
  *((_QWORD *)StartContext + 102) = StartContext + 816;
  while ( 1 )
  {
    if ( v5 != v4 )
      __fastfail(3u);
    v6 = v3++;
    v7 = &StartContext[32 * v6 + 272];
    *(_QWORD *)v7 = v4;
    *((_QWORD *)v7 + 1) = v2;
    *v2 = v7;
    *((_QWORD *)StartContext + 103) = v7;
    if ( v3 >= 0x10 )
      break;
    v5 = *(char **)v7;
    v2 = v7;
  }
  *((_DWORD *)StartContext + 60) = 4104;
  Pool2 = ExAllocatePool2(256, 4112, 1717663052);
  v9 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 4104;
    *(_BYTE *)(Pool2 + 4) = -1;
    FltAcquirePushLockExclusiveEx(&PoolLock, 0);
    dword_14000ECBC += 4104;
    FltReleasePushLockEx(&PoolLock, 0);
    v10 = (void *)(v9 + 8);
  }
  else
  {
    v10 = 0;
  }
  *((_QWORD *)StartContext + 29) = v10;
  if ( !v10 )
    return -1073741670;
  memset(v10, 0, *((unsigned int *)StartContext + 60));
  result = InitializeUsn((__int64)StartContext);
  if ( result >= 0 )
  {
    result = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, (PKSTART_ROUTINE)UsnThread, StartContext);
    if ( result >= 0 )
    {
      v12 = (PVOID *)(StartContext + 72);
      ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, (PVOID *)StartContext + 9, 0);
      ZwClose(ThreadHandle);
      KeWaitForSingleObject(StartContext + 88, Executive, 0, 0, 0);
      if ( *((int *)StartContext + 61) < 0 )
      {
        KeWaitForSingleObject(*v12, Executive, 0, 0, 0);
        ObfDereferenceObject(*v12);
        return *((_DWORD *)StartContext + 61);
      }
      else
      {
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140024cac  mov     [rsp+arg_8], rbx
0x140024cb1  mov     [rsp+arg_10], rsi
0x140024cb6  push    rdi
0x140024cb7  sub     rsp, 40h
0x140024cbb  mov     rbx, rcx
0x140024cbe  mov     [rsp+48h+ThreadHandle], 0
0x140024cc7  add     rcx, 108h; PushLock
0x140024cce  call    cs:__imp_ExInitializePushLock
0x140024cd5  nop     dword ptr [rax+rax+00h]
0x140024cda  xor     r8d, r8d; State
0x140024cdd  mov     dword ptr [rbx+340h], 0
0x140024ce7  xor     edx, edx; Type
0x140024ce9  lea     rcx, [rbx+58h]; Event
0x140024ced  call    cs:__imp_KeInitializeEvent
0x140024cf4  nop     dword ptr [rax+rax+00h]
0x140024cf9  lea     rcx, [rbx+70h]; Event
0x140024cfd  xor     r8d, r8d; State
0x140024d00  xor     edx, edx; Type
0x140024d02  call    cs:__imp_KeInitializeEvent
0x140024d09  nop     dword ptr [rax+rax+00h]
0x140024d0e  xor     r8d, r8d; State
0x140024d11  lea     rcx, [rbx+88h]; Event
0x140024d18  lea     edi, [r8+1]
0x140024d1c  mov     edx, edi; Type
0x140024d1e  call    cs:__imp_KeInitializeEvent
0x140024d25  nop     dword ptr [rax+rax+00h]
0x140024d2a  lea     rcx, [rbx+0A0h]; Event
0x140024d31  xor     r8d, r8d; State
0x140024d34  xor     edx, edx; Type
0x140024d36  call    cs:__imp_KeInitializeEvent
0x140024d3d  nop     dword ptr [rax+rax+00h]
0x140024d42  lea     rcx, [rbx+0B8h]; Event
0x140024d49  xor     r8d, r8d; State
0x140024d4c  mov     edx, edi; Type
0x140024d4e  call    cs:__imp_KeInitializeEvent
0x140024d55  nop     dword ptr [rax+rax+00h]
0x140024d5a  lea     rcx, [rbx+0D0h]; Event
0x140024d61  xor     r8d, r8d; State
0x140024d64  xor     edx, edx; Type
0x140024d66  call    cs:__imp_KeInitializeEvent
0x140024d6d  nop     dword ptr [rax+rax+00h]
0x140024d72  lea     r8, [rbx+330h]
0x140024d79  xor     edx, edx
0x140024d7b  lea     rax, [rbx+310h]
0x140024d82  mov     r9, r8
0x140024d85  mov     [rax+8], rax
0x140024d89  lea     r10, [r8+8]
0x140024d8d  mov     [rax], rax
0x140024d90  lea     rax, [rbx+320h]
0x140024d97  mov     [rax+8], rax
0x140024d9b  mov     [rax], rax
0x140024d9e  mov     rax, r8
0x140024da1  mov     [r10], r8
0x140024da4  mov     [r8], r8
0x140024da7  cmp     rax, r9
0x140024daa  jnz     loc_140024F70
0x140024db0  mov     ecx, edx
0x140024db2  add     edx, edi
0x140024db4  shl     rcx, 5
0x140024db8  add     rcx, 110h
0x140024dbf  add     rcx, rbx
0x140024dc2  mov     [rcx], r9
0x140024dc5  mov     [rcx+8], r8
0x140024dc9  mov     [r8], rcx
0x140024dcc  mov     [r10], rcx
0x140024dcf  cmp     edx, 10h
0x140024dd2  jnb     short loc_140024DDC
0x140024dd4  mov     rax, [rcx]
0x140024dd7  mov     r8, rcx
0x140024dda  jmp     short loc_140024DA7
0x140024ddc  mov     edx, 1010h
0x140024de1  mov     dword ptr [rbx+0F0h], 1008h
0x140024deb  mov     ecx, 100h
0x140024df0  mov     r8d, 6661754Ch
0x140024df6  call    cs:__imp_ExAllocatePool2
0x140024dfd  nop     dword ptr [rax+rax+00h]
0x140024e02  mov     rdi, rax
0x140024e05  test    rax, rax
0x140024e08  jnz     short loc_140024E0E
0x140024e0a  xor     ecx, ecx
0x140024e0c  jmp     short loc_140024E50
0x140024e0e  xor     edx, edx
0x140024e10  mov     dword ptr [rax], 1008h
0x140024e16  lea     rcx, PoolLock
0x140024e1d  mov     byte ptr [rax+4], 0FFh
0x140024e21  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140024e28  nop     dword ptr [rax+rax+00h]
0x140024e2d  add     cs:dword_14000ECBC, 1008h
0x140024e37  lea     rcx, PoolLock
0x140024e3e  xor     edx, edx
0x140024e40  call    cs:__imp_FltReleasePushLockEx
0x140024e47  nop     dword ptr [rax+rax+00h]
0x140024e4c  lea     rcx, [rdi+8]; void *
0x140024e50  mov     [rbx+0E8h], rcx
0x140024e57  test    rcx, rcx
0x140024e5a  jnz     short loc_140024E72
0x140024e5c  mov     eax, 0C000009Ah
0x140024e61  mov     rbx, [rsp+48h+arg_8]
0x140024e66  mov     rsi, [rsp+48h+arg_10]
0x140024e6b  add     rsp, 40h
0x140024e6f  pop     rdi
0x140024e70  retn
0x140024e72  mov     r8d, [rbx+0F0h]; Size
0x140024e79  xor     edx, edx; Val
0x140024e7b  call    memset
0x140024e80  mov     rcx, rbx
0x140024e83  call    InitializeUsn
0x140024e88  test    eax, eax
0x140024e8a  js      short loc_140024E61
0x140024e8c  lea     rax, UsnThread
0x140024e93  mov     [rsp+48h+StartContext], rbx; StartContext
0x140024e98  mov     [rsp+48h+StartRoutine], rax; StartRoutine
0x140024e9d  lea     rcx, [rsp+48h+ThreadHandle]; ThreadHandle
0x140024ea2  xor     r9d, r9d; ProcessHandle
0x140024ea5  mov     [rsp+48h+ClientId], 0; ClientId
0x140024eae  xor     r8d, r8d; ObjectAttributes
0x140024eb1  mov     edx, 1FFFFFh; DesiredAccess
0x140024eb6  call    cs:__imp_PsCreateSystemThread
0x140024ebd  nop     dword ptr [rax+rax+00h]
0x140024ec2  test    eax, eax
0x140024ec4  js      short loc_140024E61
0x140024ec6  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x140024ecb  lea     rdi, [rbx+48h]
0x140024ecf  mov     [rsp+48h+StartRoutine], 0; HandleInformation
0x140024ed8  xor     r9d, r9d; AccessMode
0x140024edb  xor     r8d, r8d; ObjectType
0x140024ede  mov     [rsp+48h+ClientId], rdi; Object
0x140024ee3  mov     edx, 1FFFFFh; DesiredAccess
0x140024ee8  call    cs:__imp_ObReferenceObjectByHandle
0x140024eef  nop     dword ptr [rax+rax+00h]
0x140024ef4  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x140024ef9  call    cs:__imp_ZwClose
0x140024f00  nop     dword ptr [rax+rax+00h]
0x140024f05  xor     r9d, r9d; Alertable
0x140024f08  mov     [rsp+48h+ClientId], 0; Timeout
0x140024f11  xor     r8d, r8d; WaitMode
0x140024f14  lea     rcx, [rbx+58h]; Object
0x140024f18  xor     edx, edx; WaitReason
0x140024f1a  call    cs:__imp_KeWaitForSingleObject
0x140024f21  nop     dword ptr [rax+rax+00h]
0x140024f26  cmp     dword ptr [rbx+0F4h], 0
0x140024f2d  jl      short loc_140024F36
0x140024f2f  xor     eax, eax
0x140024f31  jmp     loc_140024E61
0x140024f36  mov     rcx, [rdi]; Object
0x140024f39  xor     r9d, r9d; Alertable
0x140024f3c  xor     r8d, r8d; WaitMode
0x140024f3f  mov     [rsp+48h+ClientId], 0; Timeout
0x140024f48  xor     edx, edx; WaitReason
0x140024f4a  call    cs:__imp_KeWaitForSingleObject
0x140024f51  nop     dword ptr [rax+rax+00h]
0x140024f56  mov     rcx, [rdi]; Object
0x140024f59  call    cs:__imp_ObfDereferenceObject
0x140024f60  nop     dword ptr [rax+rax+00h]
0x140024f65  mov     eax, [rbx+0F4h]
0x140024f6b  jmp     loc_140024E61
0x140024f70  mov     ecx, 3
0x140024f75  int     29h; Win8: RtlFailFast(ecx)
```
