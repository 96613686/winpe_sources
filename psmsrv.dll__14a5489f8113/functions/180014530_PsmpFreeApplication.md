# PsmpFreeApplication

- ea: `0x180014530`
- end: `0x180014656`
- name: `PsmpFreeApplication`
- size: `294`
- prototype: `BOOLEAN __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800144a0`

## callees

- `0x1800092b4`
- `0x180014530`
- `0x180019c30`
- `0x18001c5fc`
- `0x18001c768`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001462a`
- `ntdll!RtlFreeHeap` at `0x1800145ed`
- `ntdll!RtlFreeHeap` at `0x18001462a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001459b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001459b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800145ba`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800145ba`
- `ext-ms-win-core-storelicensing-l1-2-0!PackageRundownNotificationForStoreLicense2` at `0x180014579`
- `ext-ms-win-core-storelicensing-l1-2-0!PackageRundownNotificationForStoreLicense2` at `0x180014579`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18001464b`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18001464b`

## pseudocode

```c
BOOLEAN __fastcall PsmpFreeApplication(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rdi
  __int64 v4; // rsi
  signed __int32 v5; // eax
  __int64 v7; // rcx
  _QWORD *v8; // rdx

  if ( *(_DWORD *)(*(_QWORD *)(a1 + 320) + 16LL) != 8 )
  {
    v2 = *(_QWORD *)(a1 + 8);
    if ( (unsigned __int8)IsPackageRundownNotificationForStoreLicensePresent() && (*(_DWORD *)(a1 + 132) & 0x1000) == 0 )
      PackageRundownNotificationForStoreLicense2(
        v2,
        *(unsigned int *)(*(_QWORD *)(a1 + 312) + 4LL),
        *(_QWORD *)(*(_QWORD *)(a1 + 312) + 40LL));
    if ( IsUnmountVolumeForAppPackagePresent() )
      UnmountVolumeForAppPackage(
        v2,
        *(_QWORD *)(*(_QWORD *)(a1 + 312) + 40LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 312) + 4LL));
  }
  v3 = *(_QWORD *)(a1 + 312);
  v4 = *(_QWORD *)(v3 + 56);
  RtlAcquireSRWLockExclusive(v4 + 8);
  v5 = _InterlockedDecrement((volatile signed __int32 *)v3);
  if ( v5 == -1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else if ( (v5 & 0x7FFFFFFF) == 0 )
  {
    v7 = *(_QWORD *)(v3 + 8);
    if ( *(_QWORD *)(v7 + 8) != v3 + 8 || (v8 = *(_QWORD **)(v3 + 16), *v8 != v3 + 8) )
      __fastfail(3u);
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v3);
  }
  RtlReleaseSRWLockExclusive(v4 + 8);
  PsmpDereferenceManagerContext(*(char **)(a1 + 320));
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a1);
}

```

## disassembly

```asm
0x180014530  mov     [rsp+arg_0], rbx
0x180014535  mov     [rsp+arg_8], rsi
0x18001453a  push    rdi
0x18001453b  sub     rsp, 20h
0x18001453f  mov     rax, [rcx+140h]
0x180014546  mov     rbx, rcx
0x180014549  cmp     dword ptr [rax+10h], 8
0x18001454d  jz      short loc_18001458C
0x18001454f  mov     rdi, [rcx+8]
0x180014553  call    IsPackageRundownNotificationForStoreLicensePresent
0x180014558  test    al, al
0x18001455a  jz      short loc_18001457F
0x18001455c  test    dword ptr [rbx+84h], 1000h
0x180014566  jnz     short loc_18001457F
0x180014568  mov     rdx, [rbx+138h]
0x18001456f  mov     rcx, rdi
0x180014572  mov     r8, [rdx+28h]
0x180014576  mov     edx, [rdx+4]
0x180014579  call    cs:__imp_PackageRundownNotificationForStoreLicense2
0x18001457f  call    IsUnmountVolumeForAppPackagePresent
0x180014584  test    al, al
0x180014586  jnz     loc_180014639
0x18001458c  mov     rdi, [rbx+138h]
0x180014593  mov     rsi, [rdi+38h]
0x180014597  lea     rcx, [rsi+8]
0x18001459b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800145a1  or      eax, 0FFFFFFFFh
0x1800145a4  lock xadd [rdi], eax
0x1800145a8  dec     eax
0x1800145aa  cmp     eax, 0FFFFFFFFh
0x1800145ad  jz      short loc_1800145F4
0x1800145af  test    eax, 7FFFFFFFh
0x1800145b4  jz      short loc_1800145FB
0x1800145b6  lea     rcx, [rsi+8]
0x1800145ba  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800145c0  mov     rcx, [rbx+140h]; P
0x1800145c7  call    PsmpDereferenceManagerContext
0x1800145cc  mov     rcx, gs:60h
0x1800145d5  mov     r8, rbx
0x1800145d8  xor     edx, edx
0x1800145da  mov     rcx, [rcx+30h]
0x1800145de  mov     rbx, [rsp+28h+arg_0]
0x1800145e3  mov     rsi, [rsp+28h+arg_8]
0x1800145e8  add     rsp, 20h
0x1800145ec  pop     rdi
0x1800145ed  jmp     cs:__imp_RtlFreeHeap
0x1800145f4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800145f9  jmp     short loc_1800145B6
0x1800145fb  lea     rax, [rdi+8]
0x1800145ff  mov     rcx, [rax]
0x180014602  cmp     [rcx+8], rax
0x180014606  jnz     short loc_180014632
0x180014608  mov     rdx, [rax+8]
0x18001460c  cmp     [rdx], rax
0x18001460f  jnz     short loc_180014632
0x180014611  mov     [rdx], rcx
0x180014614  mov     r8, rdi; P
0x180014617  mov     [rcx+8], rdx
0x18001461b  xor     edx, edx; Flags
0x18001461d  mov     rcx, gs:60h
0x180014626  mov     rcx, [rcx+30h]; HeapHandle
0x18001462a  call    cs:__imp_RtlFreeHeap
0x180014630  jmp     short loc_1800145B6
0x180014632  mov     ecx, 3
0x180014637  int     29h; Win8: RtlFailFast(ecx)
0x180014639  mov     rdx, [rbx+138h]
0x180014640  mov     rcx, rdi
0x180014643  mov     r8d, [rdx+4]
0x180014647  mov     rdx, [rdx+28h]
0x18001464b  call    cs:__imp_UnmountVolumeForAppPackage
0x180014651  jmp     loc_18001458C
```
