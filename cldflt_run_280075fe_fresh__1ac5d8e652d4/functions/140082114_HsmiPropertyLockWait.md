# HsmiPropertyLockWait

- ea: `0x140082114`
- end: `0x1400822a2`
- name: `HsmiPropertyLockWait`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14006e778`

## callees

- `0x140003c50`
- `0x140082114`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14008215d`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14008215d`
- `ntoskrnl!KeReadStateEvent` at `0x140082200`
- `ntoskrnl!KeReadStateEvent` at `0x140082200`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400821a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140082261`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400821a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140082261`
- `ntoskrnl!KeClearEvent` at `0x140082185`
- `ntoskrnl!KeClearEvent` at `0x140082185`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008219c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140082255`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008219c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140082255`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400821ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400821ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400821dc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400821dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400821cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400821cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082275`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082275`

## pseudocode

```c
__int64 __fastcall HsmiPropertyLockWait(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rdx
  __int64 v4; // rbp
  signed __int64 UnbiasedInterruptTime; // rax
  signed __int64 v6; // rcx
  char v7; // si
  unsigned int v8; // edi
  __int64 **v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // rdx
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  v3 = *(_QWORD **)(a1 + 104);
  if ( *v3 != a1 + 96 )
    goto LABEL_13;
  v4 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a2 + 64) = a1 + 96;
  *(_QWORD *)(a2 + 72) = v3;
  *v3 = a2 + 64;
  *(_QWORD *)(a1 + 104) = a2 + 64;
  while ( 1 )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v6 = *(_QWORD *)(a2 + 56);
    if ( UnbiasedInterruptTime >= v6 )
      break;
    Timeout.QuadPart = UnbiasedInterruptTime - v6;
    KeClearEvent((PRKEVENT)(a2 + 24));
    *(_DWORD *)(a2 + 48) = 259;
    ExReleaseResourceLite((PERESOURCE)(v4 + 120));
    KeLeaveCriticalRegion();
    v7 = 0;
    if ( KeWaitForSingleObject((PVOID)(a2 + 24), Executive, 0, 1u, &Timeout) )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 120), 1u);
      v7 = 1;
      if ( !KeReadStateEvent((PRKEVENT)(a2 + 24)) )
        continue;
    }
    v8 = *(_DWORD *)(a2 + 48);
    goto LABEL_10;
  }
  v9 = *(__int64 ***)(a2 + 72);
  v10 = *v9;
  if ( (__int64 **)(*v9)[1] != v9 || (v11 = (__int64 *)*v10, *(__int64 **)(*v10 + 8) != v10) )
LABEL_13:
    __fastfail(3u);
  *v9 = v11;
  v7 = 1;
  v11[1] = (__int64)v9;
  *(_QWORD *)(a2 + 72) = a2 + 64;
  *(_QWORD *)(a2 + 64) = a2 + 64;
  v8 = -1073688806;
LABEL_10:
  HsmDbgBreakOnStatus(v8);
  if ( v7 )
  {
    ExReleaseResourceLite((PERESOURCE)(v4 + 120));
    KeLeaveCriticalRegion();
  }
  ExFreePoolWithTag((PVOID)a2, 0x72507348u);
  return v8;
}

```

## disassembly

```asm
0x140082114  mov     [rsp+arg_8], rbx
0x140082119  mov     [rsp+arg_10], rbp
0x14008211e  push    rsi
0x14008211f  push    rdi
0x140082120  push    r12
0x140082122  push    r14
0x140082124  push    r15
0x140082126  sub     rsp, 30h
0x14008212a  lea     rax, [rcx+60h]
0x14008212e  mov     qword ptr [rsp+58h+arg_0], 0
0x140082137  mov     rbx, rdx
0x14008213a  mov     rdx, [rax+8]
0x14008213e  cmp     [rdx], rax
0x140082141  jnz     loc_14008229B
0x140082147  mov     rbp, [rcx+8]
0x14008214b  lea     rdi, [rbx+40h]
0x14008214f  mov     [rdi], rax
0x140082152  mov     [rdi+8], rdx
0x140082156  mov     [rdx], rdi
0x140082159  mov     [rax+8], rdi
0x14008215d  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140082164  nop     dword ptr [rax+rax+00h]
0x140082169  mov     rcx, [rbx+38h]
0x14008216d  cmp     rax, rcx
0x140082170  jge     loc_140082219
0x140082176  sub     rax, rcx
0x140082179  lea     r15, [rbx+18h]
0x14008217d  mov     rcx, r15; Event
0x140082180  mov     qword ptr [rsp+58h+arg_0], rax
0x140082185  call    cs:__imp_KeClearEvent
0x14008218c  nop     dword ptr [rax+rax+00h]
0x140082191  lea     rcx, [rbp+78h]; Resource
0x140082195  mov     dword ptr [rbx+30h], 103h
0x14008219c  call    cs:__imp_ExReleaseResourceLite
0x1400821a3  nop     dword ptr [rax+rax+00h]
0x1400821a8  call    cs:__imp_KeLeaveCriticalRegion
0x1400821af  nop     dword ptr [rax+rax+00h]
0x1400821b4  lea     rax, [rsp+58h+arg_0]
0x1400821b9  mov     r9b, 1; Alertable
0x1400821bc  xor     r8d, r8d; WaitMode
0x1400821bf  mov     [rsp+58h+Timeout], rax; Timeout
0x1400821c4  xor     edx, edx; WaitReason
0x1400821c6  mov     rcx, r15; Object
0x1400821c9  xor     sil, sil
0x1400821cc  call    cs:__imp_KeWaitForSingleObject
0x1400821d3  nop     dword ptr [rax+rax+00h]
0x1400821d8  test    eax, eax
0x1400821da  jz      short loc_140082214
0x1400821dc  call    cs:__imp_KeEnterCriticalRegion
0x1400821e3  nop     dword ptr [rax+rax+00h]
0x1400821e8  mov     dl, 1; Wait
0x1400821ea  lea     rcx, [rbp+78h]; Resource
0x1400821ee  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400821f5  nop     dword ptr [rax+rax+00h]
0x1400821fa  mov     rcx, r15; Event
0x1400821fd  mov     sil, 1
0x140082200  call    cs:__imp_KeReadStateEvent
0x140082207  nop     dword ptr [rax+rax+00h]
0x14008220c  test    eax, eax
0x14008220e  jz      loc_14008215D
0x140082214  mov     edi, [rbx+30h]
0x140082217  jmp     short loc_140082245
0x140082219  mov     rax, [rbx+48h]
0x14008221d  mov     rcx, [rax]
0x140082220  cmp     [rcx+8], rax
0x140082224  jnz     short loc_14008229B
0x140082226  mov     rdx, [rcx]
0x140082229  cmp     [rdx+8], rcx
0x14008222d  jnz     short loc_14008229B
0x14008222f  mov     [rax], rdx
0x140082232  mov     sil, 1
0x140082235  mov     [rdx+8], rax
0x140082239  mov     [rdi+8], rdi
0x14008223d  mov     [rdi], rdi
0x140082240  mov     edi, 0C000CF1Ah
0x140082245  mov     ecx, edi
0x140082247  call    HsmDbgBreakOnStatus
0x14008224c  test    sil, sil
0x14008224f  jz      short loc_14008226D
0x140082251  lea     rcx, [rbp+78h]; Resource
0x140082255  call    cs:__imp_ExReleaseResourceLite
0x14008225c  nop     dword ptr [rax+rax+00h]
0x140082261  call    cs:__imp_KeLeaveCriticalRegion
0x140082268  nop     dword ptr [rax+rax+00h]
0x14008226d  mov     edx, 72507348h; Tag
0x140082272  mov     rcx, rbx; P
0x140082275  call    cs:__imp_ExFreePoolWithTag
0x14008227c  nop     dword ptr [rax+rax+00h]
0x140082281  mov     rbx, [rsp+58h+arg_8]
0x140082286  mov     eax, edi
0x140082288  mov     rbp, [rsp+58h+arg_10]
0x14008228d  add     rsp, 30h
0x140082291  pop     r15
0x140082293  pop     r14
0x140082295  pop     r12
0x140082297  pop     rdi
0x140082298  pop     rsi
0x140082299  retn
0x14008229b  mov     ecx, 3
0x1400822a0  int     29h; Win8: RtlFailFast(ecx)
```
