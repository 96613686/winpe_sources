# CcnDestroyPublisher

- ea: `0x1800724e0`
- end: `0x1800725b1`
- name: `CcnDestroyPublisher`
- size: `209`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006a680`

## callees

- `0x180018e40`
- `0x1800724e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180072594`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072594`
- `ntoskrnl!ObfDereferenceObject` at `0x180072545`
- `ntoskrnl!ObfDereferenceObject` at `0x180072545`
- `ntoskrnl!ExDeleteResourceLite` at `0x180072580`
- `ntoskrnl!ExDeleteResourceLite` at `0x180072580`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007250c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007250c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180072565`
- `ntoskrnl!ExReleaseResourceLite` at `0x180072565`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072571`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180072571`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800724fb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1800724fb`

## pseudocode

```c
void __fastcall CcnDestroyPublisher(struct _ERESOURCE *P)
{
  void **p_Flink; // rsi
  void *v3; // rbx
  void **v4; // rax

  if ( P )
  {
    KeEnterGuardedRegion();
    ExAcquireResourceExclusiveLite(P, 1u);
    p_Flink = (void **)&P[1].SystemResourcesList.Flink;
    while ( 1 )
    {
      v3 = *p_Flink;
      if ( *p_Flink == p_Flink )
        break;
      if ( *((void ***)v3 + 1) != p_Flink || (v4 = *(void ***)v3, *(void **)(*(_QWORD *)v3 + 8LL) != v3) )
        __fastfail(3u);
      *p_Flink = v4;
      v4[1] = p_Flink;
      if ( *((_QWORD *)v3 + 2) )
        ObfDereferenceObject(*((PVOID *)v3 + 3));
      BCryptFree(v3);
    }
    ExReleaseResourceLite(P);
    KeLeaveGuardedRegion();
    ExDeleteResourceLite(P);
    ExFreePoolWithTag(P, 0x62676E43u);
  }
}

```

## disassembly

```asm
0x1800724e0  test    rcx, rcx
0x1800724e3  jz      locret_1800725AF
0x1800724e9  mov     [rsp+arg_0], rbx
0x1800724ee  mov     [rsp+arg_8], rsi
0x1800724f3  push    rdi
0x1800724f4  sub     rsp, 20h
0x1800724f8  mov     rdi, rcx
0x1800724fb  call    cs:__imp_KeEnterGuardedRegion
0x180072502  nop     dword ptr [rax+rax+00h]
0x180072507  mov     dl, 1; Wait
0x180072509  mov     rcx, rdi; Resource
0x18007250c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180072513  nop     dword ptr [rax+rax+00h]
0x180072518  lea     rsi, [rdi+68h]
0x18007251c  mov     rbx, [rsi]
0x18007251f  cmp     rbx, rsi
0x180072522  jz      short loc_180072562
0x180072524  cmp     [rbx+8], rsi
0x180072528  jnz     short loc_18007255B
0x18007252a  mov     rax, [rbx]
0x18007252d  cmp     [rax+8], rbx
0x180072531  jnz     short loc_18007255B
0x180072533  mov     [rsi], rax
0x180072536  mov     [rax+8], rsi
0x18007253a  cmp     qword ptr [rbx+10h], 0
0x18007253f  jz      short loc_180072551
0x180072541  mov     rcx, [rbx+18h]; Object
0x180072545  call    cs:__imp_ObfDereferenceObject
0x18007254c  nop     dword ptr [rax+rax+00h]
0x180072551  mov     rcx, rbx; P
0x180072554  call    BCryptFree
0x180072559  jmp     short loc_18007251C
0x18007255b  mov     ecx, 3
0x180072560  int     29h; Win8: RtlFailFast(ecx)
0x180072562  mov     rcx, rdi; Resource
0x180072565  call    cs:__imp_ExReleaseResourceLite
0x18007256c  nop     dword ptr [rax+rax+00h]
0x180072571  call    cs:__imp_KeLeaveGuardedRegion
0x180072578  nop     dword ptr [rax+rax+00h]
0x18007257d  mov     rcx, rdi; Resource
0x180072580  call    cs:__imp_ExDeleteResourceLite
0x180072587  nop     dword ptr [rax+rax+00h]
0x18007258c  mov     edx, 62676E43h; Tag
0x180072591  mov     rcx, rdi; P
0x180072594  call    cs:__imp_ExFreePoolWithTag
0x18007259b  nop     dword ptr [rax+rax+00h]
0x1800725a0  mov     rbx, [rsp+28h+arg_0]
0x1800725a5  mov     rsi, [rsp+28h+arg_8]
0x1800725aa  add     rsp, 20h
0x1800725ae  pop     rdi
0x1800725af  retn
```
