# CdpCompleteServerKernelConnection

- ea: `0x140008890`
- end: `0x14000897e`
- name: `CdpCompleteServerKernelConnection`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140008890`
- `0x140008984`
- `0x140008a54`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000894b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000894b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400088d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400088d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000893a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000893a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400088c7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400088c7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400088f2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400088f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008929`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140008929`

## pseudocode

```c
__int64 __fastcall CdpCompleteServerKernelConnection(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v3; // r12d
  char v4; // si
  _QWORD *v5; // rbx
  __int64 v6; // r15
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = a2;
  v3 = *(_DWORD *)(a2 + 48);
  v4 = 0;
  v5 = (_QWORD *)*a3;
  v6 = 0;
  if ( v3 >= 0 )
    v6 = a3[1];
  if ( KeGetCurrentIrql() <= 1u )
  {
    KeEnterCriticalRegion();
    v4 = 1;
  }
  ExAcquirePushLockExclusiveEx(v5 + 27, 0);
  if ( v5[29] == a2 )
  {
    v5[28] = v6;
    v5[29] = 0;
    CdpCompleteServerKernelConnectionQueue(v5, v3);
  }
  ExReleasePushLockExclusiveEx(v5 + 27, 0);
  if ( v4 )
    KeLeaveCriticalRegion();
  ExFreePoolWithTag(a3, 0);
  CdpFreeKernelConnectionIrp(&v10);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140008890  mov     [rsp+arg_0], rbx
0x140008895  mov     [rsp+arg_10], rbp
0x14000889a  mov     [rsp+arg_8], rdx
0x14000889f  push    rsi
0x1400088a0  push    rdi
0x1400088a1  push    r12
0x1400088a3  push    r14
0x1400088a5  push    r15
0x1400088a7  sub     rsp, 20h
0x1400088ab  mov     r12d, [rdx+30h]
0x1400088af  xor     sil, sil
0x1400088b2  mov     rbx, [r8]
0x1400088b5  xor     r15d, r15d
0x1400088b8  mov     rdi, r8
0x1400088bb  mov     rbp, rdx
0x1400088be  test    r12d, r12d
0x1400088c1  js      short loc_1400088C7
0x1400088c3  mov     r15, [r8+8]
0x1400088c7  call    cs:__imp_KeGetCurrentIrql
0x1400088ce  nop     dword ptr [rax+rax+00h]
0x1400088d3  cmp     al, 1
0x1400088d5  ja      short loc_1400088E6
0x1400088d7  call    cs:__imp_KeEnterCriticalRegion
0x1400088de  nop     dword ptr [rax+rax+00h]
0x1400088e3  mov     sil, 1
0x1400088e6  lea     r14, [rbx+0D8h]
0x1400088ed  xor     edx, edx
0x1400088ef  mov     rcx, r14
0x1400088f2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400088f9  nop     dword ptr [rax+rax+00h]
0x1400088fe  cmp     [rbx+0E8h], rbp
0x140008905  jnz     short loc_140008924
0x140008907  mov     edx, r12d
0x14000890a  mov     [rbx+0E0h], r15
0x140008911  mov     rcx, rbx
0x140008914  mov     qword ptr [rbx+0E8h], 0
0x14000891f  call    CdpCompleteServerKernelConnectionQueue
0x140008924  xor     edx, edx
0x140008926  mov     rcx, r14
0x140008929  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140008930  nop     dword ptr [rax+rax+00h]
0x140008935  test    sil, sil
0x140008938  jz      short loc_140008946
0x14000893a  call    cs:__imp_KeLeaveCriticalRegion
0x140008941  nop     dword ptr [rax+rax+00h]
0x140008946  xor     edx, edx; Tag
0x140008948  mov     rcx, rdi; P
0x14000894b  call    cs:__imp_ExFreePoolWithTag
0x140008952  nop     dword ptr [rax+rax+00h]
0x140008957  lea     rcx, [rsp+48h+arg_8]
0x14000895c  call    CdpFreeKernelConnectionIrp
0x140008961  mov     rbx, [rsp+48h+arg_0]
0x140008966  mov     eax, 0C0000016h
0x14000896b  mov     rbp, [rsp+48h+arg_10]
0x140008970  add     rsp, 20h
0x140008974  pop     r15
0x140008976  pop     r14
0x140008978  pop     r12
0x14000897a  pop     rdi
0x14000897b  pop     rsi
0x14000897c  retn
```
