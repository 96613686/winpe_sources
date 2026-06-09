# PsmpFindOrCreateManagerContext

- ea: `0x18000b1d0`
- end: `0x18000b3d2`
- name: `PsmpFindOrCreateManagerContext`
- size: `514`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001230`
- `0x1800043d8`
- `0x18000abf0`
- `0x18000cb7c`

## callees

- `0x18000b1d0`
- `0x18000c740`
- `0x180017f60`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b2ca`
- `ntdll!RtlFreeHeap` at `0x18000b2ca`
- `ntdll!NtCreateEvent` at `0x18000b2a2`
- `ntdll!NtCreateEvent` at `0x18000b2a2`
- `ntdll!NtClose` at `0x18000b32f`
- `ntdll!NtClose` at `0x18000b32f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b221`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b221`
- `ntdll!RtlInitializeSRWLock` at `0x18000b379`
- `ntdll!RtlInitializeSRWLock` at `0x18000b379`
- `ntdll!RtlAllocateHeap` at `0x18000b24f`
- `ntdll!RtlAllocateHeap` at `0x18000b24f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b3a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b3a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b320`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b320`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b206`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b206`

## pseudocode

```c
__int64 __fastcall PsmpFindOrCreateManagerContext(unsigned int a1, unsigned int a2)
{
  __int64 ManagerContext; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  char *Heap; // rax
  char *v10; // rbx
  char *v11; // rsi
  _QWORD *v12; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  void *EventHandle; // [rsp+B0h] [rbp+48h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlAcquireSRWLockShared(&PsmpManagerLock);
  ManagerContext = PsmpFindManagerContext(a1, a2);
  RtlReleaseSRWLockShared(&PsmpManagerLock, v5, v6, v7);
  if ( ManagerContext )
    return ManagerContext;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
  v10 = Heap;
  if ( Heap )
  {
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = Heap;
    if ( NtCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0) < 0 )
    {
      EventHandle = 0;
LABEL_6:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
      return ManagerContext;
    }
    *(_DWORD *)v10 = 1;
    RtlInitializeSRWLock(v10 + 8);
    *((_QWORD *)v10 + 4) = v10 + 24;
    *((_QWORD *)v10 + 3) = v10 + 24;
    *((_DWORD *)v10 + 5) = a2;
    *((_DWORD *)v10 + 4) = a1;
    *((_QWORD *)v10 + 8) = 0;
    *((_QWORD *)v10 + 7) = EventHandle;
    RtlAcquireSRWLockExclusive(&PsmpManagerLock);
    ManagerContext = PsmpFindManagerContext(a1, a2);
    if ( !ManagerContext )
    {
      v12 = off_18003F0D8[0];
      EventHandle = 0;
      if ( *(_UNKNOWN ***)off_18003F0D8[0] != &PsmpManagerList )
        __fastfail(3u);
      ManagerContext = (__int64)v10;
      *((_QWORD *)v10 + 5) = &PsmpManagerList;
      v11 = 0;
      *((_QWORD *)v10 + 6) = v12;
      *v12 = v10 + 40;
      off_18003F0D8[0] = (_UNKNOWN **)(v10 + 40);
    }
    RtlReleaseSRWLockExclusive(&PsmpManagerLock);
    if ( EventHandle )
      NtClose(EventHandle);
    if ( v11 )
      goto LABEL_6;
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_b5485372ff90327e3674091dc1985471_Traceguids, a2);
  }
  return ManagerContext;
}

```

## disassembly

```asm
0x18000b1d0  push    rbp
0x18000b1d2  push    rbx
0x18000b1d3  push    rsi
0x18000b1d4  push    rdi
0x18000b1d5  push    r14
0x18000b1d7  push    r15
0x18000b1d9  mov     rbp, rsp
0x18000b1dc  sub     rsp, 68h
0x18000b1e0  xorps   xmm0, xmm0
0x18000b1e3  mov     [rbp+EventHandle], 0
0x18000b1eb  mov     r15d, ecx
0x18000b1ee  xor     eax, eax
0x18000b1f0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000b1f4  lea     rcx, PsmpManagerLock
0x18000b1fb  mov     r14d, edx
0x18000b1fe  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000b202  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000b206  call    cs:__imp_RtlAcquireSRWLockShared
0x18000b20c  mov     edx, r14d
0x18000b20f  mov     ecx, r15d
0x18000b212  call    PsmpFindManagerContext
0x18000b217  lea     rcx, PsmpManagerLock
0x18000b21e  mov     rdi, rax
0x18000b221  call    cs:__imp_RtlReleaseSRWLockShared
0x18000b227  test    rdi, rdi
0x18000b22a  jz      short loc_18000B23C
0x18000b22c  mov     rax, rdi
0x18000b22f  add     rsp, 68h
0x18000b233  pop     r15
0x18000b235  pop     r14
0x18000b237  pop     rdi
0x18000b238  pop     rsi
0x18000b239  pop     rbx
0x18000b23a  pop     rbp
0x18000b23b  retn
0x18000b23c  mov     rcx, gs:60h
0x18000b245  xor     edx, edx; Flags
0x18000b247  mov     rcx, [rcx+30h]; HeapHandle
0x18000b24b  lea     r8d, [rdx+48h]; Size
0x18000b24f  call    cs:__imp_RtlAllocateHeap
0x18000b255  mov     rbx, rax
0x18000b258  test    rax, rax
0x18000b25b  jz      loc_18000B337
0x18000b261  xorps   xmm0, xmm0
0x18000b264  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000b26b  mov     r9d, 1; EventType
0x18000b271  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000b279  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000b27d  mov     [rbp+ObjectAttributes.Attributes], 0
0x18000b284  mov     edx, 1F0003h; DesiredAccess
0x18000b289  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18000b291  lea     rcx, [rbp+EventHandle]; EventHandle
0x18000b295  mov     [rsp+68h+InitialState], 0; InitialState
0x18000b29a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b29f  mov     rsi, rax
0x18000b2a2  call    cs:__imp_NtCreateEvent
0x18000b2a8  test    eax, eax
0x18000b2aa  jns     loc_18000B36F
0x18000b2b0  mov     [rbp+EventHandle], 0
0x18000b2b8  mov     rcx, gs:60h
0x18000b2c1  mov     r8, rsi; P
0x18000b2c4  xor     edx, edx; Flags
0x18000b2c6  mov     rcx, [rcx+30h]; HeapHandle
0x18000b2ca  call    cs:__imp_RtlFreeHeap
0x18000b2d0  jmp     loc_18000B22C
0x18000b2d5  test    rsi, rsi
0x18000b2d8  jz      loc_18000B22C
0x18000b2de  jmp     short loc_18000B2B8
0x18000b2e0  mov     rcx, cs:off_18003F0D8
0x18000b2e7  lea     rdx, PsmpManagerList
0x18000b2ee  mov     [rbp+EventHandle], 0
0x18000b2f6  cmp     [rcx], rdx
0x18000b2f9  jnz     loc_18000B3CB
0x18000b2ff  lea     rax, [rbx+28h]
0x18000b303  mov     rdi, rbx
0x18000b306  mov     [rax], rdx
0x18000b309  xor     esi, esi
0x18000b30b  mov     [rax+8], rcx
0x18000b30f  mov     [rcx], rax
0x18000b312  mov     cs:off_18003F0D8, rax
0x18000b319  lea     rcx, PsmpManagerLock
0x18000b320  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b326  mov     rcx, [rbp+EventHandle]; Handle
0x18000b32a  test    rcx, rcx
0x18000b32d  jz      short loc_18000B2D5
0x18000b32f  call    cs:__imp_NtClose
0x18000b335  jmp     short loc_18000B2D5
0x18000b337  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b33e  test    byte ptr [rcx+1Ch], 2
0x18000b342  jz      loc_18000B22C
0x18000b348  cmp     byte ptr [rcx+19h], 2
0x18000b34c  jb      loc_18000B22C
0x18000b352  mov     rcx, [rcx+10h]
0x18000b356  lea     r8, WPP_b5485372ff90327e3674091dc1985471_Traceguids
0x18000b35d  mov     edx, 10h
0x18000b362  mov     r9d, r14d
0x18000b365  call    WPP_SF_d
0x18000b36a  jmp     loc_18000B22C
0x18000b36f  lea     rcx, [rbx+8]
0x18000b373  mov     dword ptr [rbx], 1
0x18000b379  call    cs:__imp_RtlInitializeSRWLock
0x18000b37f  lea     rax, [rbx+18h]
0x18000b383  mov     [rax+8], rax
0x18000b387  lea     rcx, PsmpManagerLock
0x18000b38e  mov     [rax], rax
0x18000b391  mov     [rbx+14h], r14d
0x18000b395  mov     [rbx+10h], r15d
0x18000b399  mov     qword ptr [rbx+40h], 0
0x18000b3a1  mov     rax, [rbp+EventHandle]
0x18000b3a5  mov     [rbx+38h], rax
0x18000b3a9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b3af  mov     edx, r14d
0x18000b3b2  mov     ecx, r15d
0x18000b3b5  call    PsmpFindManagerContext
0x18000b3ba  mov     rdi, rax
0x18000b3bd  test    rax, rax
0x18000b3c0  jnz     loc_18000B319
0x18000b3c6  jmp     loc_18000B2E0
0x18000b3cb  mov     ecx, 3
0x18000b3d0  int     29h; Win8: RtlFailFast(ecx)
```
