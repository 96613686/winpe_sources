# UlStopConfigGroupFacet

- ea: `0x1400c9cf0`
- end: `0x1400c9e0d`
- name: `UlStopConfigGroupFacet`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1400c9cf0`
- `0x1400c9e14`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400c9d5f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400c9d5f`
- `ntoskrnl!ExFreeCacheAwarePushLock` at `0x1400c9d85`
- `ntoskrnl!ExFreeCacheAwarePushLock` at `0x1400c9d85`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400c9d32`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400c9d32`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9d6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9d6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9db3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9dcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9db3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9dcf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c9d1f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c9d1f`

## pseudocode

```c
void __fastcall UlStopConfigGroupFacet(__int64 a1)
{
  _QWORD *i; // rdi
  _DWORD *v3; // rax

  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_q(1028, 82, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, a1);
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
    WPP_SF_(1028, 83, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids);
}

```

## disassembly

```asm
0x1400c9cf0  mov     [rsp+arg_0], rbx
0x1400c9cf5  push    rdi
0x1400c9cf6  sub     rsp, 20h
0x1400c9cfa  mov     rbx, rcx
0x1400c9cfd  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400c9d04  jz      short loc_1400C9D1F
0x1400c9d06  mov     edx, 52h ; 'R'
0x1400c9d0b  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400c9d12  mov     ecx, 404h
0x1400c9d17  mov     r9, rbx
0x1400c9d1a  call    WPP_SF_q
0x1400c9d1f  call    cs:__imp_KeEnterCriticalRegion
0x1400c9d26  nop     dword ptr [rax+rax+00h]
0x1400c9d2b  mov     rcx, [rbx+558h]
0x1400c9d32  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400c9d39  nop     dword ptr [rax+rax+00h]
0x1400c9d3e  lea     rdi, [rbx+540h]
0x1400c9d45  mov     rcx, [rdi]
0x1400c9d48  cmp     rcx, rdi
0x1400c9d4b  jz      short loc_1400C9D58
0x1400c9d4d  add     rcx, 0FFFFFFFFFFFFFF88h; P
0x1400c9d51  call    UlpTreeDeleteReservation
0x1400c9d56  jmp     short loc_1400C9D45
0x1400c9d58  mov     rcx, [rbx+558h]
0x1400c9d5f  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400c9d66  nop     dword ptr [rax+rax+00h]
0x1400c9d6b  call    cs:__imp_KeLeaveCriticalRegion
0x1400c9d72  nop     dword ptr [rax+rax+00h]
0x1400c9d77  mov     rcx, [rbx+558h]
0x1400c9d7e  xor     edi, edi
0x1400c9d80  test    rcx, rcx
0x1400c9d83  jz      short loc_1400C9D98
0x1400c9d85  call    cs:__imp_ExFreeCacheAwarePushLock
0x1400c9d8c  nop     dword ptr [rax+rax+00h]
0x1400c9d91  mov     [rbx+558h], rdi
0x1400c9d98  mov     rax, [rbx+528h]
0x1400c9d9f  test    rax, rax
0x1400c9da2  jz      short loc_1400C9DC6
0x1400c9da4  mov     dword ptr [rax], 68634C75h
0x1400c9daa  xor     edx, edx; Tag
0x1400c9dac  mov     rcx, [rbx+528h]; P
0x1400c9db3  call    cs:__imp_ExFreePoolWithTag
0x1400c9dba  nop     dword ptr [rax+rax+00h]
0x1400c9dbf  mov     [rbx+528h], rdi
0x1400c9dc6  mov     rcx, [rbx+550h]; P
0x1400c9dcd  xor     edx, edx; Tag
0x1400c9dcf  call    cs:__imp_ExFreePoolWithTag
0x1400c9dd6  nop     dword ptr [rax+rax+00h]
0x1400c9ddb  mov     [rbx+550h], rdi
0x1400c9de2  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400c9de9  jz      short loc_1400C9E01
0x1400c9deb  mov     edx, 53h ; 'S'
0x1400c9df0  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400c9df7  mov     ecx, 404h
0x1400c9dfc  call    WPP_SF_
0x1400c9e01  mov     rbx, [rsp+28h+arg_0]
0x1400c9e06  add     rsp, 20h
0x1400c9e0a  pop     rdi
0x1400c9e0b  retn
```
