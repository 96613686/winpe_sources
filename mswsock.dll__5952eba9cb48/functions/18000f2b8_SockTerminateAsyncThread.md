# SockTerminateAsyncThread

- ea: `0x18000f2b8`
- end: `0x18000f3d9`
- name: `SockTerminateAsyncThread`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x18000ca20`
- `0x18000db30`
- `0x18000f2b8`

## import_xrefs

- `ntdll!NtSetInformationObject` at `0x18000f322`
- `ntdll!NtSetInformationObject` at `0x18000f364`
- `ntdll!NtSetInformationObject` at `0x18000f322`
- `ntdll!NtSetInformationObject` at `0x18000f364`
- `ntdll!NtClose` at `0x18000f332`
- `ntdll!NtClose` at `0x18000f374`
- `ntdll!NtClose` at `0x18000f332`
- `ntdll!NtClose` at `0x18000f374`
- `ntdll!NtSetIoCompletion` at `0x18000f3c8`
- `ntdll!NtSetIoCompletion` at `0x18000f3c8`

## pseudocode

```c
__int64 SockTerminateAsyncThread()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  HANDLE v4; // rdi
  HANDLE v5; // rdi
  __int16 ObjectInformation; // [rsp+50h] [rbp+8h] BYREF

  ObjectInformation = 0;
  SockAcquireRwLockExclusive();
  v4 = SockAsyncSelectHelperHandle;
  if ( SockAsyncSelectHelperHandle )
  {
    SockAsyncSelectHelperHandle = 0;
    ObjectInformation = 0;
    NtSetInformationObject(v4, ObjectHandleFlagInformation, &ObjectInformation, 2u);
    NtClose(v4);
  }
  v5 = SockAsyncConnectHelperHandle;
  if ( SockAsyncConnectHelperHandle )
  {
    SockAsyncConnectHelperHandle = 0;
    ObjectInformation = 0;
    NtSetInformationObject(v5, ObjectHandleFlagInformation, &ObjectInformation, 2u);
    NtClose(v5);
  }
  if ( SockAsyncQueuePort )
  {
    do
    {
      v0 = (unsigned int)SockAsyncThreadReferenceCount;
      if ( SockAsyncThreadReferenceCount <= 0 )
        break;
      v1 = (unsigned int)(SockAsyncThreadReferenceCount + 1);
      if ( (_DWORD)v0 == _InterlockedCompareExchange(&SockAsyncThreadReferenceCount, v1, SockAsyncThreadReferenceCount) )
      {
        NtSetIoCompletion(SockAsyncQueuePort, (PVOID)0xFFFFFFFFFFFFFFFFLL, (PVOID)0xFFFFFFFFFFFFFFFFLL, 0, 0);
        return SockReleaseRwLockExclusive(v1, v0, v2, v3);
      }
    }
    while ( (int)v0 > 0 );
  }
  return SockReleaseRwLockExclusive(v1, v0, v2, v3);
}

```

## disassembly

```asm
0x18000f2b8  mov     [rsp+arg_8], rbx
0x18000f2bd  push    rdi
0x18000f2be  sub     rsp, 40h
0x18000f2c2  xor     ebx, ebx
0x18000f2c4  mov     [rsp+48h+ObjectInformation], bx
0x18000f2c9  call    SockAcquireRwLockExclusive
0x18000f2ce  mov     rdi, cs:SockAsyncSelectHelperHandle
0x18000f2d5  test    rdi, rdi
0x18000f2d8  jnz     short loc_18000F304
0x18000f2da  mov     rdi, cs:SockAsyncConnectHelperHandle
0x18000f2e1  test    rdi, rdi
0x18000f2e4  jnz     short loc_18000F344
0x18000f2e6  cmp     cs:SockAsyncQueuePort, rbx
0x18000f2ed  jnz     loc_18000F38C
0x18000f2f3  call    SockReleaseRwLockExclusive
0x18000f2f8  mov     rbx, [rsp+48h+arg_8]
0x18000f2fd  add     rsp, 40h
0x18000f301  pop     rdi
0x18000f302  retn
0x18000f304  mov     cs:SockAsyncSelectHelperHandle, rbx
0x18000f30b  mov     [rsp+48h+ObjectInformation], bx
0x18000f310  mov     r9d, 2; Length
0x18000f316  lea     r8, [rsp+48h+ObjectInformation]; ObjectInformation
0x18000f31b  lea     edx, [r9+2]; ObjectInformationClass
0x18000f31f  mov     rcx, rdi; ObjectHandle
0x18000f322  call    cs:__imp_NtSetInformationObject
0x18000f329  nop     dword ptr [rax+rax+00h]
0x18000f32e  nop
0x18000f32f  mov     rcx, rdi; Handle
0x18000f332  call    cs:__imp_NtClose
0x18000f339  nop     dword ptr [rax+rax+00h]
0x18000f33e  jmp     short loc_18000F2DA
0x18000f340  xor     ebx, ebx
0x18000f342  jmp     short loc_18000F2DA
0x18000f344  mov     cs:SockAsyncConnectHelperHandle, rbx
0x18000f34b  mov     [rsp+48h+ObjectInformation], 0
0x18000f352  mov     r9d, 2; Length
0x18000f358  lea     r8, [rsp+48h+ObjectInformation]; ObjectInformation
0x18000f35d  lea     edx, [r9+2]; ObjectInformationClass
0x18000f361  mov     rcx, rdi; ObjectHandle
0x18000f364  call    cs:__imp_NtSetInformationObject
0x18000f36b  nop     dword ptr [rax+rax+00h]
0x18000f370  nop
0x18000f371  mov     rcx, rdi; Handle
0x18000f374  call    cs:__imp_NtClose
0x18000f37b  nop     dword ptr [rax+rax+00h]
0x18000f380  jmp     loc_18000F2E6
0x18000f385  xor     ebx, ebx
0x18000f387  jmp     loc_18000F2E6
0x18000f38c  mov     edx, cs:SockAsyncThreadReferenceCount
0x18000f392  test    edx, edx
0x18000f394  jle     loc_18000F2F3
0x18000f39a  lea     ecx, [rdx+1]
0x18000f39d  mov     eax, edx
0x18000f39f  lock cmpxchg cs:SockAsyncThreadReferenceCount, ecx
0x18000f3a7  jz      short loc_18000F3B2
0x18000f3a9  test    edx, edx
0x18000f3ab  jg      short loc_18000F38C
0x18000f3ad  jmp     loc_18000F2F3
0x18000f3b2  mov     qword ptr [rsp+48h+CompletionInformation], rbx; CompletionInformation
0x18000f3b7  xor     r9d, r9d; CompletionStatus
0x18000f3ba  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionKey
0x18000f3be  mov     r8, rdx; CompletionContext
0x18000f3c1  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x18000f3c8  call    cs:__imp_NtSetIoCompletion
0x18000f3cf  nop     dword ptr [rax+rax+00h]
0x18000f3d4  jmp     loc_18000F2F3
```
