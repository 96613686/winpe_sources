# PsmpNotificationContextCreate

- ea: `0x1800242a8`
- end: `0x1800243a0`
- name: `PsmpNotificationContextCreate`
- size: `248`
- prototype: `__int64 __fastcall(int, int, void *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a3a0`

## callees

- `0x1800017b0`
- `0x18000436c`
- `0x18001c10c`
- `0x1800241e4`
- `0x1800242a8`
- `0x1800243a8`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800242fd`
- `ntdll!RtlCopySid` at `0x1800242fd`
- `ntdll!RtlInitializeSRWLock` at `0x180024307`
- `ntdll!RtlInitializeSRWLock` at `0x180024307`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024337`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024337`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002436f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002436f`

## pseudocode

```c
__int64 __fastcall PsmpNotificationContextCreate(int a1, int a2, void *a3, __int64 *a4)
{
  PVOID Heap; // rax
  __int64 v9; // rbx
  int State; // edi
  __int64 *v11; // rax

  Heap = PsmpAllocateHeap(0x90u);
  v9 = (__int64)Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0x90u);
    *(_DWORD *)(v9 + 116) = a1;
    *(_DWORD *)(v9 + 120) = a2;
    RtlCopySid(0x44u, (PSID)(v9 + 48), a3);
    RtlInitializeSRWLock(v9 + 40);
    *(_QWORD *)(v9 + 24) = v9 + 16;
    *(_QWORD *)(v9 + 16) = v9 + 16;
    *(_DWORD *)(v9 + 32) = 1;
    State = PsmpNotificationContextAllocateState(v9, a3);
    if ( State < 0 )
    {
      if ( PsmpDereferenceObjectEx((volatile signed __int32 *)(v9 + 32), 0) )
        PsmpNotificationContextDestroy(v9);
    }
    else
    {
      RtlAcquireSRWLockExclusive(&PsmpNotificationContextsListLock);
      v11 = (__int64 *)off_18003F0E8;
      if ( *off_18003F0E8 != (_UNKNOWN *)&PsmpNotificationContextsList )
        __fastfail(3u);
      *(_QWORD *)v9 = &PsmpNotificationContextsList;
      *(_QWORD *)(v9 + 8) = v11;
      *v11 = v9;
      off_18003F0E8 = (_UNKNOWN **)v9;
      RtlReleaseSRWLockExclusive(&PsmpNotificationContextsListLock);
      State = 0;
      *a4 = v9;
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)State;
}

```

## disassembly

```asm
0x1800242a8  push    rbx
0x1800242aa  push    rbp
0x1800242ab  push    rsi
0x1800242ac  push    rdi
0x1800242ad  push    r14
0x1800242af  sub     rsp, 20h
0x1800242b3  mov     r14d, ecx
0x1800242b6  mov     rsi, r9
0x1800242b9  mov     ecx, 90h
0x1800242be  mov     rdi, r8
0x1800242c1  mov     ebp, edx
0x1800242c3  call    PsmpAllocateHeap
0x1800242c8  mov     rbx, rax
0x1800242cb  test    rax, rax
0x1800242ce  jnz     short loc_1800242DA
0x1800242d0  mov     edi, 0C0000017h
0x1800242d5  jmp     loc_180024393
0x1800242da  xor     edx, edx; Val
0x1800242dc  mov     r8d, 90h; Size
0x1800242e2  mov     rcx, rbx; void *
0x1800242e5  call    memset_0
0x1800242ea  lea     rdx, [rbx+30h]; DestinationSid
0x1800242ee  mov     [rbx+74h], r14d
0x1800242f2  mov     r8, rdi; SourceSid
0x1800242f5  mov     [rbx+78h], ebp
0x1800242f8  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1800242fd  call    cs:__imp_RtlCopySid
0x180024303  lea     rcx, [rbx+28h]
0x180024307  call    cs:__imp_RtlInitializeSRWLock
0x18002430d  lea     rax, [rbx+10h]
0x180024311  mov     rdx, rdi
0x180024314  mov     [rax+8], rax
0x180024318  mov     rcx, rbx
0x18002431b  mov     [rax], rax
0x18002431e  mov     dword ptr [rbx+20h], 1
0x180024325  call    PsmpNotificationContextAllocateState
0x18002432a  mov     edi, eax
0x18002432c  test    eax, eax
0x18002432e  js      short loc_18002437C
0x180024330  lea     rcx, PsmpNotificationContextsListLock
0x180024337  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002433d  mov     rax, cs:off_18003F0E8
0x180024344  lea     rcx, PsmpNotificationContextsList
0x18002434b  cmp     [rax], rcx
0x18002434e  jz      short loc_180024357
0x180024350  mov     ecx, 3
0x180024355  int     29h; Win8: RtlFailFast(ecx)
0x180024357  mov     [rbx], rcx
0x18002435a  lea     rcx, PsmpNotificationContextsListLock
0x180024361  mov     [rbx+8], rax
0x180024365  mov     [rax], rbx
0x180024368  mov     cs:off_18003F0E8, rbx
0x18002436f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180024375  xor     edi, edi
0x180024377  mov     [rsi], rbx
0x18002437a  jmp     short loc_180024393
0x18002437c  lea     rcx, [rbx+20h]
0x180024380  xor     edx, edx
0x180024382  call    PsmpDereferenceObjectEx
0x180024387  test    al, al
0x180024389  jz      short loc_180024393
0x18002438b  mov     rcx, rbx
0x18002438e  call    PsmpNotificationContextDestroy
0x180024393  mov     eax, edi
0x180024395  add     rsp, 20h
0x180024399  pop     r14
0x18002439b  pop     rdi
0x18002439c  pop     rsi
0x18002439d  pop     rbp
0x18002439e  pop     rbx
0x18002439f  retn
```
