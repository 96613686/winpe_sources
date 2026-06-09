# InitThreading

- ea: `0x14001a300`
- end: `0x14001a3f7`
- name: `InitThreading`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001af90`

## callees

- `0x14001a300`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001a35f`
- `ntoskrnl!KeInitializeEvent` at `0x14001a37a`
- `ntoskrnl!KeInitializeEvent` at `0x14001a35f`
- `ntoskrnl!KeInitializeEvent` at `0x14001a37a`
- `ntoskrnl!PsCreateSystemThread` at `0x14001a3d0`
- `ntoskrnl!PsCreateSystemThread` at `0x14001a3d0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a344`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a344`

## pseudocode

```c
__int64 InitThreading()
{
  __int64 result; // rax
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  result = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !ThreadingInitialized )
  {
    WorkItemList.Blink = &WorkItemList;
    WorkItemList.Flink = &WorkItemList;
    KeInitializeSpinLock(&GlobalThreadLock);
    KeInitializeEvent(&EventPassiveThread, SynchronizationEvent, 0);
    KeInitializeEvent(&EventKillThread, SynchronizationEvent, 0);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( PsCreateSystemThread(&hPassiveThread, 0, &ObjectAttributes, 0, 0, (PKSTART_ROUTINE)MainPassiveLevelThread, 0) )
    {
      return 3221225473LL;
    }
    else
    {
      ThreadingInitialized = 1;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a300  push    rbx
0x14001a302  sub     rsp, 70h
0x14001a306  xorps   xmm0, xmm0
0x14001a309  xor     ebx, ebx
0x14001a30b  xor     eax, eax
0x14001a30d  cmp     cs:ThreadingInitialized, al
0x14001a313  movups  xmmword ptr [rsp+78h+ObjectAttributes.ObjectName], xmm0
0x14001a318  movups  xmmword ptr [rsp+78h+ObjectAttributes+1Ch], xmm0
0x14001a31d  movups  xmmword ptr [rsp+78h+ObjectAttributes.Length], xmm0
0x14001a322  jnz     loc_14001A3F0
0x14001a328  lea     rax, WorkItemList
0x14001a32f  lea     rcx, GlobalThreadLock; SpinLock
0x14001a336  mov     cs:WorkItemList.Blink, rax
0x14001a33d  mov     cs:WorkItemList.Flink, rax
0x14001a344  call    cs:__imp_KeInitializeSpinLock
0x14001a34b  nop     dword ptr [rax+rax+00h]
0x14001a350  xor     r8d, r8d; State
0x14001a353  lea     rcx, EventPassiveThread; Event
0x14001a35a  mov     edx, 1; Type
0x14001a35f  call    cs:__imp_KeInitializeEvent
0x14001a366  nop     dword ptr [rax+rax+00h]
0x14001a36b  xor     r8d, r8d; State
0x14001a36e  lea     rcx, EventKillThread; Event
0x14001a375  mov     edx, 1; Type
0x14001a37a  call    cs:__imp_KeInitializeEvent
0x14001a381  nop     dword ptr [rax+rax+00h]
0x14001a386  lea     rax, MainPassiveLevelThread
0x14001a38d  mov     [rsp+78h+StartContext], rbx; StartContext
0x14001a392  xorps   xmm0, xmm0
0x14001a395  mov     [rsp+78h+StartRoutine], rax; StartRoutine
0x14001a39a  xor     r9d, r9d; ProcessHandle
0x14001a39d  mov     [rsp+78h+ClientId], rbx; ClientId
0x14001a3a2  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x14001a3a7  mov     [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x14001a3af  xor     edx, edx; DesiredAccess
0x14001a3b1  mov     [rsp+78h+ObjectAttributes.RootDirectory], rbx
0x14001a3b6  lea     rcx, hPassiveThread; ThreadHandle
0x14001a3bd  mov     [rsp+78h+ObjectAttributes.Attributes], 200h
0x14001a3c5  mov     [rsp+78h+ObjectAttributes.ObjectName], rbx
0x14001a3ca  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001a3d0  call    cs:__imp_PsCreateSystemThread
0x14001a3d7  nop     dword ptr [rax+rax+00h]
0x14001a3dc  test    eax, eax
0x14001a3de  jnz     short loc_14001A3EB
0x14001a3e0  mov     cs:ThreadingInitialized, 1
0x14001a3e7  mov     eax, ebx
0x14001a3e9  jmp     short loc_14001A3F0
0x14001a3eb  mov     eax, 0C0000001h
0x14001a3f0  add     rsp, 70h
0x14001a3f4  pop     rbx
0x14001a3f5  retn
```
