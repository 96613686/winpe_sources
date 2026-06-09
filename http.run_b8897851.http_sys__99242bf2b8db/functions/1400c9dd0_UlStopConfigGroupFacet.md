# UlStopConfigGroupFacet

- ea: `0x1400c9dd0`
- end: `0x1400c9eed`
- name: `UlStopConfigGroupFacet`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1400c9dd0`
- `0x1400c9ef4`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400c9e3f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400c9e3f`
- `ntoskrnl!ExFreeCacheAwarePushLock` at `0x1400c9e65`
- `ntoskrnl!ExFreeCacheAwarePushLock` at `0x1400c9e65`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400c9e12`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400c9e12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9e4b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9e4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9eaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9eaf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c9dff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c9dff`

## pseudocode

```c
void __fastcall UlStopConfigGroupFacet(__int64 a1)
{
  _QWORD *i; // rdi
  _DWORD *v3; // rax

  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_q(1028, 82, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, a1);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1368));
  for ( i = (_QWORD *)(a1 + 1344); (_QWORD *)*i != i; UlpTreeDeleteReservation((PVOID)(*i - 120LL)) )
    ;
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1368));
  KeLeaveCriticalRegion();
  if ( *(_QWORD *)(a1 + 1368) )
  {
    ExFreeCacheAwarePushLock();
    *(_QWORD *)(a1 + 1368) = 0;
  }
  v3 = *(_DWORD **)(a1 + 1320);
  if ( v3 )
  {
    *v3 = 1751338101;
    ExFreePoolWithTag(*(PVOID *)(a1 + 1320), 0);
    *(_QWORD *)(a1 + 1320) = 0;
  }
  ExFreePoolWithTag(*(PVOID *)(a1 + 1360), 0);
  *(_QWORD *)(a1 + 1360) = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_(1028, 83, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids);
}

```

## disassembly

```asm
0x1400c9dd0  mov     [rsp+arg_0], rbx
0x1400c9dd5  push    rdi
0x1400c9dd6  sub     rsp, 20h
0x1400c9dda  mov     rbx, rcx
0x1400c9ddd  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400c9de4  jz      short loc_1400C9DFF
0x1400c9de6  mov     edx, 52h ; 'R'
0x1400c9deb  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400c9df2  mov     ecx, 404h
0x1400c9df7  mov     r9, rbx
0x1400c9dfa  call    WPP_SF_q
0x1400c9dff  call    cs:__imp_KeEnterCriticalRegion
0x1400c9e06  nop     dword ptr [rax+rax+00h]
0x1400c9e0b  mov     rcx, [rbx+558h]
0x1400c9e12  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400c9e19  nop     dword ptr [rax+rax+00h]
0x1400c9e1e  lea     rdi, [rbx+540h]
0x1400c9e25  mov     rcx, [rdi]
0x1400c9e28  cmp     rcx, rdi
0x1400c9e2b  jz      short loc_1400C9E38
0x1400c9e2d  add     rcx, 0FFFFFFFFFFFFFF88h; P
0x1400c9e31  call    UlpTreeDeleteReservation
0x1400c9e36  jmp     short loc_1400C9E25
0x1400c9e38  mov     rcx, [rbx+558h]
0x1400c9e3f  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400c9e46  nop     dword ptr [rax+rax+00h]
0x1400c9e4b  call    cs:__imp_KeLeaveCriticalRegion
0x1400c9e52  nop     dword ptr [rax+rax+00h]
0x1400c9e57  mov     rcx, [rbx+558h]
0x1400c9e5e  xor     edi, edi
0x1400c9e60  test    rcx, rcx
0x1400c9e63  jz      short loc_1400C9E78
0x1400c9e65  call    cs:__imp_ExFreeCacheAwarePushLock
0x1400c9e6c  nop     dword ptr [rax+rax+00h]
0x1400c9e71  mov     [rbx+558h], rdi
0x1400c9e78  mov     rax, [rbx+528h]
0x1400c9e7f  test    rax, rax
0x1400c9e82  jz      short loc_1400C9EA6
0x1400c9e84  mov     dword ptr [rax], 68634C75h
0x1400c9e8a  xor     edx, edx; Tag
0x1400c9e8c  mov     rcx, [rbx+528h]; P
0x1400c9e93  call    cs:__imp_ExFreePoolWithTag
0x1400c9e9a  nop     dword ptr [rax+rax+00h]
0x1400c9e9f  mov     [rbx+528h], rdi
0x1400c9ea6  mov     rcx, [rbx+550h]; P
0x1400c9ead  xor     edx, edx; Tag
0x1400c9eaf  call    cs:__imp_ExFreePoolWithTag
0x1400c9eb6  nop     dword ptr [rax+rax+00h]
0x1400c9ebb  mov     [rbx+550h], rdi
0x1400c9ec2  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400c9ec9  jz      short loc_1400C9EE1
0x1400c9ecb  mov     edx, 53h ; 'S'
0x1400c9ed0  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400c9ed7  mov     ecx, 404h
0x1400c9edc  call    WPP_SF_
0x1400c9ee1  mov     rbx, [rsp+28h+arg_0]
0x1400c9ee6  add     rsp, 20h
0x1400c9eea  pop     rdi
0x1400c9eeb  retn
```
