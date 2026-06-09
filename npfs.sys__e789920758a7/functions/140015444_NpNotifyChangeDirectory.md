# NpNotifyChangeDirectory

- ea: `0x140015444`
- end: `0x140015609`
- name: `NpNotifyChangeDirectory`
- size: `453`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014e30`

## callees

- `0x140015444`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140015536`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015536`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001554e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001554e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400155a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400155ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400155a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400155ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155f6`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400154f9`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400154f9`
- `ntoskrnl!IoAllocateMdl` at `0x1400154c6`
- `ntoskrnl!IoAllocateMdl` at `0x1400154c6`
- `ntoskrnl!ProbeForWrite` at `0x1400154a8`
- `ntoskrnl!ProbeForWrite` at `0x1400154a8`
- `ntoskrnl!IoFreeMdl` at `0x140015523`
- `ntoskrnl!IoFreeMdl` at `0x140015523`
- `ntoskrnl!ExRaiseStatus` at `0x1400154e1`
- `ntoskrnl!ExRaiseStatus` at `0x1400154e1`

## pseudocode

```c
__int64 __fastcall NpNotifyChangeDirectory(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdi
  unsigned int v7; // eax
  volatile void *v8; // rcx
  struct _MDL *Mdl; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  _QWORD *v12; // rdx

  v6 = *(_QWORD *)(a3 + 184);
  v7 = *(_DWORD *)(v6 + 8);
  if ( v7 && !*(_QWORD *)(a3 + 8) && !*(_QWORD *)(a3 + 24) )
  {
    v8 = *(volatile void **)(a3 + 112);
    if ( !v8 )
      return 3221225485LL;
    if ( *(_BYTE *)(a3 + 64) == 1 )
      ProbeForWrite(v8, v7, 4u);
    Mdl = IoAllocateMdl(*(PVOID *)(a3 + 112), *(_DWORD *)(v6 + 8), 0, 0, (PIRP)a3);
    if ( !Mdl )
      ExRaiseStatus(-1073741670);
    MmProbeAndLockPages(Mdl, *(_BYTE *)(a3 + 64), IoWriteAccess);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 168, 0, v10, v11);
  _InterlockedExchange64((volatile __int64 *)(a3 + 104), (__int64)&NpCancelChangeNotifyIrp);
  if ( *(_BYTE *)(a3 + 68) && _InterlockedExchange64((volatile __int64 *)(a3 + 104), 0) )
  {
    ExReleasePushLockExclusiveEx(a1 + 168, 0);
    KeLeaveCriticalRegion();
    return 3221225760LL;
  }
  else
  {
    *(_BYTE *)(*(_QWORD *)(a3 + 184) + 3LL) |= 1u;
    *(_QWORD *)(a3 + 120) = a2;
    v12 = *(_QWORD **)(a1 + 184);
    if ( *v12 != a1 + 176 )
      __fastfail(3u);
    *(_QWORD *)(a3 + 168) = a1 + 176;
    *(_QWORD *)(a3 + 176) = v12;
    *v12 = a3 + 168;
    *(_QWORD *)(a1 + 184) = a3 + 168;
    ExReleasePushLockExclusiveEx(a1 + 168, 0);
    KeLeaveCriticalRegion();
    return 259;
  }
}

```

## disassembly

```asm
0x140015444  mov     [rsp+arg_10], r8
0x140015449  push    rbx
0x14001544a  push    rsi
0x14001544b  push    rdi
0x14001544c  push    r14
0x14001544e  sub     rsp, 48h
0x140015452  mov     rbx, r8
0x140015455  mov     r14, rdx
0x140015458  mov     rsi, rcx
0x14001545b  mov     rdi, [r8+0B8h]
0x140015462  mov     eax, [rdi+8]
0x140015465  test    eax, eax
0x140015467  jz      loc_140015536
0x14001546d  cmp     qword ptr [r8+8], 0
0x140015472  jnz     loc_140015536
0x140015478  cmp     qword ptr [r8+18h], 0
0x14001547d  jnz     loc_140015536
0x140015483  mov     [rsp+68h+Mdl], 0
0x14001548c  mov     rcx, [r8+70h]; Address
0x140015490  test    rcx, rcx
0x140015493  jz      loc_1400155D3
0x140015499  cmp     byte ptr [r8+40h], 1
0x14001549e  jnz     short loc_1400154B4
0x1400154a0  mov     edx, eax; Length
0x1400154a2  mov     r8d, 4; Alignment
0x1400154a8  call    cs:__imp_ProbeForWrite
0x1400154af  nop     dword ptr [rax+rax+00h]
0x1400154b4  mov     [rsp+68h+Irp], rbx; Irp
0x1400154b9  xor     r9d, r9d; ChargeQuota
0x1400154bc  xor     r8d, r8d; SecondaryBuffer
0x1400154bf  mov     edx, [rdi+8]; Length
0x1400154c2  mov     rcx, [rbx+70h]; VirtualAddress
0x1400154c6  call    cs:__imp_IoAllocateMdl
0x1400154cd  nop     dword ptr [rax+rax+00h]
0x1400154d2  mov     [rsp+68h+Mdl], rax
0x1400154d7  test    rax, rax
0x1400154da  jnz     short loc_1400154ED
0x1400154dc  mov     ecx, 0C000009Ah; Status
0x1400154e1  call    cs:__imp_ExRaiseStatus
0x1400154ed  mov     r8d, 1; Operation
0x1400154f3  mov     dl, [rbx+40h]; AccessMode
0x1400154f6  mov     rcx, rax; MemoryDescriptorList
0x1400154f9  call    cs:__imp_MmProbeAndLockPages
0x140015500  nop     dword ptr [rax+rax+00h]
0x140015505  jmp     short loc_140015536
0x140015507  mov     ebx, eax
0x140015509  mov     rcx, [rsp+68h+Mdl]; Mdl
0x14001550e  test    rcx, rcx
0x140015511  jz      short loc_14001552F
0x140015513  mov     rdx, [rsp+68h+arg_10]
0x14001551b  mov     qword ptr [rdx+8], 0
0x140015523  call    cs:__imp_IoFreeMdl
0x14001552a  nop     dword ptr [rax+rax+00h]
0x14001552f  mov     eax, ebx
0x140015531  jmp     loc_1400155C1
0x140015536  call    cs:__imp_KeEnterCriticalRegion
0x14001553d  nop     dword ptr [rax+rax+00h]
0x140015542  lea     rdi, [rsi+0A8h]
0x140015549  xor     edx, edx
0x14001554b  mov     rcx, rdi
0x14001554e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140015555  nop     dword ptr [rax+rax+00h]
0x14001555a  lea     rax, NpCancelChangeNotifyIrp
0x140015561  xchg    rax, [rbx+68h]
0x140015565  cmp     byte ptr [rbx+44h], 0
0x140015569  jnz     short loc_1400155DA
0x14001556b  mov     rax, [rbx+0B8h]
0x140015572  or      byte ptr [rax+3], 1
0x140015576  mov     [rbx+78h], r14
0x14001557a  lea     rcx, [rsi+0B0h]
0x140015581  mov     rdx, [rcx+8]
0x140015585  cmp     [rdx], rcx
0x140015588  jnz     short loc_1400155CC
0x14001558a  lea     rax, [rbx+0A8h]
0x140015591  mov     [rax], rcx
0x140015594  mov     [rax+8], rdx
0x140015598  mov     [rdx], rax
0x14001559b  mov     [rcx+8], rax
0x14001559f  xor     edx, edx
0x1400155a1  mov     rcx, rdi
0x1400155a4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400155ab  nop     dword ptr [rax+rax+00h]
0x1400155b0  call    cs:__imp_KeLeaveCriticalRegion
0x1400155b7  nop     dword ptr [rax+rax+00h]
0x1400155bc  mov     eax, 103h
0x1400155c1  add     rsp, 48h
0x1400155c5  pop     r14
0x1400155c7  pop     rdi
0x1400155c8  pop     rsi
0x1400155c9  pop     rbx
0x1400155ca  retn
0x1400155cc  mov     ecx, 3
0x1400155d1  int     29h; Win8: RtlFailFast(ecx)
0x1400155d3  mov     eax, 0C000000Dh
0x1400155d8  jmp     short loc_1400155C1
0x1400155da  xor     eax, eax
0x1400155dc  xchg    rax, [rbx+68h]
0x1400155e0  test    rax, rax
0x1400155e3  jz      short loc_14001556B
0x1400155e5  xor     edx, edx
0x1400155e7  mov     rcx, rdi
0x1400155ea  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400155f1  nop     dword ptr [rax+rax+00h]
0x1400155f6  call    cs:__imp_KeLeaveCriticalRegion
0x1400155fd  nop     dword ptr [rax+rax+00h]
0x140015602  mov     eax, 0C0000120h
0x140015607  jmp     short loc_1400155C1
```
