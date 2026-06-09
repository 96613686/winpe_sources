# LuafvInitializeUsn

- ea: `0x140024cfc`
- end: `0x140024fc7`
- name: `LuafvInitializeUsn`
- size: `715`
- prototype: `int __fastcall(char *StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140021e90`

## callees

- `0x140006380`
- `0x1400140b4`
- `0x140024cfc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140024f6a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f9a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f6a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f9a`
- `ntoskrnl!PsCreateSystemThread` at `0x140024f06`
- `ntoskrnl!PsCreateSystemThread` at `0x140024f06`
- `ntoskrnl!ExInitializePushLock` at `0x140024d1e`
- `ntoskrnl!ExInitializePushLock` at `0x140024d1e`
- `ntoskrnl!ZwClose` at `0x140024f49`
- `ntoskrnl!ZwClose` at `0x140024f49`
- `ntoskrnl!KeInitializeEvent` at `0x140024d3d`
- `ntoskrnl!KeInitializeEvent` at `0x140024d52`
- `ntoskrnl!KeInitializeEvent` at `0x140024d6e`
- `ntoskrnl!KeInitializeEvent` at `0x140024d86`
- `ntoskrnl!KeInitializeEvent` at `0x140024d9e`
- `ntoskrnl!KeInitializeEvent` at `0x140024db6`
- `ntoskrnl!KeInitializeEvent` at `0x140024d3d`
- `ntoskrnl!KeInitializeEvent` at `0x140024d52`
- `ntoskrnl!KeInitializeEvent` at `0x140024d6e`
- `ntoskrnl!KeInitializeEvent` at `0x140024d86`
- `ntoskrnl!KeInitializeEvent` at `0x140024d9e`
- `ntoskrnl!KeInitializeEvent` at `0x140024db6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140024f38`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140024f38`
- `ntoskrnl!ObfDereferenceObject` at `0x140024fa9`
- `ntoskrnl!ObfDereferenceObject` at `0x140024fa9`
- `ntoskrnl!ExAllocatePool2` at `0x140024e46`
- `ntoskrnl!ExAllocatePool2` at `0x140024e46`
- `FLTMGR!FltReleasePushLockEx` at `0x140024e90`
- `FLTMGR!FltReleasePushLockEx` at `0x140024e90`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140024e71`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140024e71`

## pseudocode

```c
int __fastcall LuafvInitializeUsn(char *StartContext)
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
  int result; // eax
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
    dword_14000F2FC += 4104;
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
    result = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, UsnThread, StartContext);
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
0x140024cfc  mov     [rsp+arg_8], rbx
0x140024d01  mov     [rsp+arg_10], rsi
0x140024d06  push    rdi
0x140024d07  sub     rsp, 40h
0x140024d0b  mov     rbx, rcx
0x140024d0e  mov     [rsp+48h+ThreadHandle], 0
0x140024d17  add     rcx, 108h; PushLock
0x140024d1e  call    cs:__imp_ExInitializePushLock
0x140024d25  nop     dword ptr [rax+rax+00h]
0x140024d2a  xor     r8d, r8d; State
0x140024d2d  mov     dword ptr [rbx+340h], 0
0x140024d37  xor     edx, edx; Type
0x140024d39  lea     rcx, [rbx+58h]; Event
0x140024d3d  call    cs:__imp_KeInitializeEvent
0x140024d44  nop     dword ptr [rax+rax+00h]
0x140024d49  lea     rcx, [rbx+70h]; Event
0x140024d4d  xor     r8d, r8d; State
0x140024d50  xor     edx, edx; Type
0x140024d52  call    cs:__imp_KeInitializeEvent
0x140024d59  nop     dword ptr [rax+rax+00h]
0x140024d5e  xor     r8d, r8d; State
0x140024d61  lea     rcx, [rbx+88h]; Event
0x140024d68  lea     edi, [r8+1]
0x140024d6c  mov     edx, edi; Type
0x140024d6e  call    cs:__imp_KeInitializeEvent
0x140024d75  nop     dword ptr [rax+rax+00h]
0x140024d7a  lea     rcx, [rbx+0A0h]; Event
0x140024d81  xor     r8d, r8d; State
0x140024d84  xor     edx, edx; Type
0x140024d86  call    cs:__imp_KeInitializeEvent
0x140024d8d  nop     dword ptr [rax+rax+00h]
0x140024d92  lea     rcx, [rbx+0B8h]; Event
0x140024d99  xor     r8d, r8d; State
0x140024d9c  mov     edx, edi; Type
0x140024d9e  call    cs:__imp_KeInitializeEvent
0x140024da5  nop     dword ptr [rax+rax+00h]
0x140024daa  lea     rcx, [rbx+0D0h]; Event
0x140024db1  xor     r8d, r8d; State
0x140024db4  xor     edx, edx; Type
0x140024db6  call    cs:__imp_KeInitializeEvent
0x140024dbd  nop     dword ptr [rax+rax+00h]
0x140024dc2  lea     r8, [rbx+330h]
0x140024dc9  xor     edx, edx
0x140024dcb  lea     rax, [rbx+310h]
0x140024dd2  mov     r9, r8
0x140024dd5  mov     [rax+8], rax
0x140024dd9  lea     r10, [r8+8]
0x140024ddd  mov     [rax], rax
0x140024de0  lea     rax, [rbx+320h]
0x140024de7  mov     [rax+8], rax
0x140024deb  mov     [rax], rax
0x140024dee  mov     rax, r8
0x140024df1  mov     [r10], r8
0x140024df4  mov     [r8], r8
0x140024df7  cmp     rax, r9
0x140024dfa  jnz     loc_140024FC0
0x140024e00  mov     ecx, edx
0x140024e02  add     edx, edi
0x140024e04  shl     rcx, 5
0x140024e08  add     rcx, 110h
0x140024e0f  add     rcx, rbx
0x140024e12  mov     [rcx], r9
0x140024e15  mov     [rcx+8], r8
0x140024e19  mov     [r8], rcx
0x140024e1c  mov     [r10], rcx
0x140024e1f  cmp     edx, 10h
0x140024e22  jnb     short loc_140024E2C
0x140024e24  mov     rax, [rcx]
0x140024e27  mov     r8, rcx
0x140024e2a  jmp     short loc_140024DF7
0x140024e2c  mov     edx, 1010h
0x140024e31  mov     dword ptr [rbx+0F0h], 1008h
0x140024e3b  mov     ecx, 100h
0x140024e40  mov     r8d, 6661754Ch
0x140024e46  call    cs:__imp_ExAllocatePool2
0x140024e4d  nop     dword ptr [rax+rax+00h]
0x140024e52  mov     rdi, rax
0x140024e55  test    rax, rax
0x140024e58  jnz     short loc_140024E5E
0x140024e5a  xor     ecx, ecx
0x140024e5c  jmp     short loc_140024EA0
0x140024e5e  xor     edx, edx
0x140024e60  mov     dword ptr [rax], 1008h
0x140024e66  lea     rcx, PoolLock
0x140024e6d  mov     byte ptr [rax+4], 0FFh
0x140024e71  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140024e78  nop     dword ptr [rax+rax+00h]
0x140024e7d  add     cs:dword_14000F2FC, 1008h
0x140024e87  lea     rcx, PoolLock
0x140024e8e  xor     edx, edx
0x140024e90  call    cs:__imp_FltReleasePushLockEx
0x140024e97  nop     dword ptr [rax+rax+00h]
0x140024e9c  lea     rcx, [rdi+8]; void *
0x140024ea0  mov     [rbx+0E8h], rcx
0x140024ea7  test    rcx, rcx
0x140024eaa  jnz     short loc_140024EC2
0x140024eac  mov     eax, 0C000009Ah
0x140024eb1  mov     rbx, [rsp+48h+arg_8]
0x140024eb6  mov     rsi, [rsp+48h+arg_10]
0x140024ebb  add     rsp, 40h
0x140024ebf  pop     rdi
0x140024ec0  retn
0x140024ec2  mov     r8d, [rbx+0F0h]; Size
0x140024ec9  xor     edx, edx; Val
0x140024ecb  call    memset
0x140024ed0  mov     rcx, rbx
0x140024ed3  call    InitializeUsn
0x140024ed8  test    eax, eax
0x140024eda  js      short loc_140024EB1
0x140024edc  lea     rax, UsnThread
0x140024ee3  mov     [rsp+48h+StartContext], rbx; StartContext
0x140024ee8  mov     [rsp+48h+StartRoutine], rax; StartRoutine
0x140024eed  lea     rcx, [rsp+48h+ThreadHandle]; ThreadHandle
0x140024ef2  xor     r9d, r9d; ProcessHandle
0x140024ef5  mov     [rsp+48h+ClientId], 0; ClientId
0x140024efe  xor     r8d, r8d; ObjectAttributes
0x140024f01  mov     edx, 1FFFFFh; DesiredAccess
0x140024f06  call    cs:__imp_PsCreateSystemThread
0x140024f0d  nop     dword ptr [rax+rax+00h]
0x140024f12  test    eax, eax
0x140024f14  js      short loc_140024EB1
0x140024f16  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x140024f1b  lea     rdi, [rbx+48h]
0x140024f1f  mov     [rsp+48h+StartRoutine], 0; HandleInformation
0x140024f28  xor     r9d, r9d; AccessMode
0x140024f2b  xor     r8d, r8d; ObjectType
0x140024f2e  mov     [rsp+48h+ClientId], rdi; Object
0x140024f33  mov     edx, 1FFFFFh; DesiredAccess
0x140024f38  call    cs:__imp_ObReferenceObjectByHandle
0x140024f3f  nop     dword ptr [rax+rax+00h]
0x140024f44  mov     rcx, [rsp+48h+ThreadHandle]; Handle
0x140024f49  call    cs:__imp_ZwClose
0x140024f50  nop     dword ptr [rax+rax+00h]
0x140024f55  xor     r9d, r9d; Alertable
0x140024f58  mov     [rsp+48h+ClientId], 0; Timeout
0x140024f61  xor     r8d, r8d; WaitMode
0x140024f64  lea     rcx, [rbx+58h]; Object
0x140024f68  xor     edx, edx; WaitReason
0x140024f6a  call    cs:__imp_KeWaitForSingleObject
0x140024f71  nop     dword ptr [rax+rax+00h]
0x140024f76  cmp     dword ptr [rbx+0F4h], 0
0x140024f7d  jl      short loc_140024F86
0x140024f7f  xor     eax, eax
0x140024f81  jmp     loc_140024EB1
0x140024f86  mov     rcx, [rdi]; Object
0x140024f89  xor     r9d, r9d; Alertable
0x140024f8c  xor     r8d, r8d; WaitMode
0x140024f8f  mov     [rsp+48h+ClientId], 0; Timeout
0x140024f98  xor     edx, edx; WaitReason
0x140024f9a  call    cs:__imp_KeWaitForSingleObject
0x140024fa1  nop     dword ptr [rax+rax+00h]
0x140024fa6  mov     rcx, [rdi]; Object
0x140024fa9  call    cs:__imp_ObfDereferenceObject
0x140024fb0  nop     dword ptr [rax+rax+00h]
0x140024fb5  mov     eax, [rbx+0F4h]
0x140024fbb  jmp     loc_140024EB1
0x140024fc0  mov     ecx, 3
0x140024fc5  int     29h; Win8: RtlFailFast(ecx)
```
