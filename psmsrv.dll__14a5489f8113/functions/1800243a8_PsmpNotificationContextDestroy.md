# PsmpNotificationContextDestroy

- ea: `0x1800243a8`
- end: `0x18002446e`
- name: `PsmpNotificationContextDestroy`
- size: `198`
- prototype: `BOOLEAN __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000dd3c`
- `0x1800242a8`
- `0x18002a220`
- `0x18002a3a0`
- `0x18002a4a0`

## callees

- `0x180001fdc`
- `0x18001a088`
- `0x180024150`
- `0x1800243a8`
- `0x180024474`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18002444a`
- `ntdll!NtDeleteWnfStateName` at `0x18002444a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800243c2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002440c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800243c2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002440c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800243d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024432`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800243d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024432`

## pseudocode

```c
BOOLEAN __fastcall PsmpNotificationContextDestroy(_QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rdx
  __int64 NextSubscription; // rdi
  void *v4; // rcx
  _QWORD *v5; // rdx
  void **v6; // rax

  v1 = a1;
  v2 = 0;
  while ( 1 )
  {
    NextSubscription = PsmpGetNextSubscription(a1, v2);
    if ( !NextSubscription )
      break;
    RtlAcquireSRWLockExclusive(v1 + 5);
    *(_DWORD *)(NextSubscription + 8) = 1;
    RtlReleaseSRWLockExclusive(v1 + 5);
    PsmpSubcriptionDereference(NextSubscription);
    v2 = NextSubscription;
    a1 = v1;
  }
  v4 = (void *)v1[17];
  if ( v4 )
    RmpWnfCleanupPendingCallbackList(v4);
  RtlAcquireSRWLockExclusive(&PsmpNotificationContextsListLock);
  v5 = (_QWORD *)*v1;
  if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v6 = (void **)v1[1], *v6 != v1) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = v6;
  RtlReleaseSRWLockExclusive(&PsmpNotificationContextsListLock);
  if ( *((_DWORD *)v1 + 31) || *((_DWORD *)v1 + 32) )
    NtDeleteWnfStateName((char *)v1 + 124);
  return PsmpFreeHeap(v1);
}

```

## disassembly

```asm
0x1800243a8  mov     [rsp+arg_0], rbx
0x1800243ad  mov     [rsp+arg_8], rsi
0x1800243b2  push    rdi
0x1800243b3  sub     rsp, 20h
0x1800243b7  mov     rbx, rcx
0x1800243ba  xor     edx, edx
0x1800243bc  jmp     short loc_1800243E7
0x1800243be  lea     rcx, [rbx+28h]
0x1800243c2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800243c8  lea     rcx, [rbx+28h]
0x1800243cc  mov     dword ptr [rdi+8], 1
0x1800243d3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800243d9  mov     rcx, rdi
0x1800243dc  call    PsmpSubcriptionDereference
0x1800243e1  mov     rdx, rdi
0x1800243e4  mov     rcx, rbx
0x1800243e7  call    PsmpGetNextSubscription
0x1800243ec  mov     rdi, rax
0x1800243ef  test    rax, rax
0x1800243f2  jnz     short loc_1800243BE
0x1800243f4  mov     rcx, [rbx+88h]; P
0x1800243fb  test    rcx, rcx
0x1800243fe  jz      short loc_180024405
0x180024400  call    RmpWnfCleanupPendingCallbackList
0x180024405  lea     rcx, PsmpNotificationContextsListLock
0x18002440c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024412  mov     rdx, [rbx]
0x180024415  cmp     [rdx+8], rbx
0x180024419  jnz     short loc_180024467
0x18002441b  mov     rax, [rbx+8]
0x18002441f  cmp     [rax], rbx
0x180024422  jnz     short loc_180024467
0x180024424  mov     [rax], rdx
0x180024427  lea     rcx, PsmpNotificationContextsListLock
0x18002442e  mov     [rdx+8], rax
0x180024432  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180024438  lea     rcx, [rbx+7Ch]
0x18002443c  cmp     dword ptr [rcx], 0
0x18002443f  jnz     short loc_18002444A
0x180024441  cmp     dword ptr [rbx+80h], 0
0x180024448  jz      short loc_180024450
0x18002444a  call    cs:__imp_NtDeleteWnfStateName
0x180024450  mov     rcx, rbx
0x180024453  mov     rbx, [rsp+28h+arg_0]
0x180024458  mov     rsi, [rsp+28h+arg_8]
0x18002445d  add     rsp, 20h
0x180024461  pop     rdi
0x180024462  jmp     PsmpFreeHeap
0x180024467  mov     ecx, 3
0x18002446c  int     29h; Win8: RtlFailFast(ecx)
```
