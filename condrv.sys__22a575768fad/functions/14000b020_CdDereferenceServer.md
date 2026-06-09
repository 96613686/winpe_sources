# CdDereferenceServer

- ea: `0x14000b020`
- end: `0x14000b167`
- name: `CdDereferenceServer`
- size: `327`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400083b0`
- `0x14000afd0`
- `0x14000b3a0`
- `0x14000bd90`
- `0x14000c2f0`
- `0x14000c370`
- `0x14000d5c0`
- `0x14000e440`

## callees

- `0x14000b020`
- `0x14000b170`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000b137`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b137`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b148`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b148`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b0a5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b0a5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b105`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b105`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b095`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b095`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b0bd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b0bd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b0f4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b0f4`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000b11f`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000b11f`

## pseudocode

```c
void __fastcall CdDereferenceServer(char *P)
{
  signed __int64 v1; // rax
  signed __int64 v3; // rdx
  unsigned __int64 v4; // r8
  char v5; // di
  char **v6; // r8
  PVOID *v7; // rdx
  __int64 v8; // rcx
  void *v9; // rcx

  v1 = *((_QWORD *)P + 3);
  do
  {
    v3 = v1;
    v4 = (v1 - 1) | 0x8000000000000000uLL;
    if ( v1 != 2 )
      v4 = v1 - 1;
    v1 = _InterlockedCompareExchange64((volatile signed __int64 *)P + 3, v4, v1);
  }
  while ( v1 != v3 );
  if ( v3 == 2 )
  {
    CdDisconnectIoPipe(P + 64);
    v3 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 3, 0x8000000000000000uLL) - 0x7FFFFFFFFFFFFFFFLL;
  }
  if ( v3 == 1 )
  {
    v5 = 0;
    if ( KeGetCurrentIrql() <= 1u )
    {
      KeEnterCriticalRegion();
      v5 = 1;
    }
    ExAcquirePushLockExclusiveEx(&CdpServerListLock, 0);
    v6 = (char **)*((_QWORD *)P + 1);
    if ( v6[1] != P + 8 || (v7 = (PVOID *)*((_QWORD *)P + 2), *v7 != P + 8) )
      __fastfail(3u);
    *v7 = v6;
    v6[1] = (char *)v7;
    ExReleasePushLockExclusiveEx(&CdpServerListLock, 0);
    if ( v5 )
      KeLeaveCriticalRegion();
    v8 = *((_QWORD *)P + 7);
    if ( v8 )
      ObDereferenceSecurityDescriptor(v8, 1);
    v9 = (void *)*((_QWORD *)P + 24);
    if ( v9 )
      ObfDereferenceObject(v9);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14000b020  mov     [rsp+arg_0], rbx
0x14000b025  push    rdi
0x14000b026  sub     rsp, 20h
0x14000b02a  mov     rax, [rcx+18h]
0x14000b02e  mov     rbx, rcx
0x14000b031  mov     rdi, 8000000000000000h
0x14000b03b  lea     r9, [rax-1]
0x14000b03f  mov     rdx, rax
0x14000b042  mov     r8, r9
0x14000b045  or      r8, rdi
0x14000b048  cmp     rax, 2
0x14000b04c  cmovnz  r8, r9
0x14000b050  lock cmpxchg [rcx+18h], r8
0x14000b056  cmp     rax, rdx
0x14000b059  jnz     short loc_14000B03B
0x14000b05b  cmp     rdx, 2
0x14000b05f  jnz     short loc_14000B080
0x14000b061  add     rcx, 40h ; '@'
0x14000b065  call    CdDisconnectIoPipe
0x14000b06a  mov     rdx, rdi
0x14000b06d  lock xadd [rbx+18h], rdx
0x14000b073  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000b07d  sub     rdx, rax
0x14000b080  cmp     rdx, 1
0x14000b084  jz      short loc_14000B092
0x14000b086  mov     rbx, [rsp+28h+arg_0]
0x14000b08b  add     rsp, 20h
0x14000b08f  pop     rdi
0x14000b090  retn
0x14000b092  xor     dil, dil
0x14000b095  call    cs:__imp_KeGetCurrentIrql
0x14000b09c  nop     dword ptr [rax+rax+00h]
0x14000b0a1  cmp     al, 1
0x14000b0a3  ja      short loc_14000B0B4
0x14000b0a5  call    cs:__imp_KeEnterCriticalRegion
0x14000b0ac  nop     dword ptr [rax+rax+00h]
0x14000b0b1  mov     dil, 1
0x14000b0b4  xor     edx, edx
0x14000b0b6  lea     rcx, CdpServerListLock
0x14000b0bd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b0c4  nop     dword ptr [rax+rax+00h]
0x14000b0c9  mov     r8, [rbx+8]
0x14000b0cd  lea     rax, [rbx+8]
0x14000b0d1  cmp     [r8+8], rax
0x14000b0d5  jnz     loc_14000B160
0x14000b0db  mov     rdx, [rax+8]
0x14000b0df  cmp     [rdx], rax
0x14000b0e2  jnz     short loc_14000B160
0x14000b0e4  mov     [rdx], r8
0x14000b0e7  lea     rcx, CdpServerListLock
0x14000b0ee  mov     [r8+8], rdx
0x14000b0f2  xor     edx, edx
0x14000b0f4  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b0fb  nop     dword ptr [rax+rax+00h]
0x14000b100  test    dil, dil
0x14000b103  jz      short loc_14000B111
0x14000b105  call    cs:__imp_KeLeaveCriticalRegion
0x14000b10c  nop     dword ptr [rax+rax+00h]
0x14000b111  mov     rcx, [rbx+38h]
0x14000b115  test    rcx, rcx
0x14000b118  jz      short loc_14000B12B
0x14000b11a  mov     edx, 1
0x14000b11f  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000b126  nop     dword ptr [rax+rax+00h]
0x14000b12b  mov     rcx, [rbx+0C0h]; Object
0x14000b132  test    rcx, rcx
0x14000b135  jz      short loc_14000B143
0x14000b137  call    cs:__imp_ObfDereferenceObject
0x14000b13e  nop     dword ptr [rax+rax+00h]
0x14000b143  xor     edx, edx; Tag
0x14000b145  mov     rcx, rbx; P
0x14000b148  call    cs:__imp_ExFreePoolWithTag
0x14000b14f  nop     dword ptr [rax+rax+00h]
0x14000b154  mov     rbx, [rsp+28h+arg_0]
0x14000b159  add     rsp, 20h
0x14000b15d  pop     rdi
0x14000b15e  retn
0x14000b160  mov     ecx, 3
0x14000b165  int     29h; Win8: RtlFailFast(ecx)
```
