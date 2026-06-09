# CcnDestroyPublisher

- ea: `0x180071ae0`
- end: `0x180071bb1`
- name: `CcnDestroyPublisher`
- size: `209`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180069c80`

## callees

- `0x18001bd90`
- `0x180071ae0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180071b94`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071b94`
- `ntoskrnl!ObfDereferenceObject` at `0x180071b45`
- `ntoskrnl!ObfDereferenceObject` at `0x180071b45`
- `ntoskrnl!ExDeleteResourceLite` at `0x180071b80`
- `ntoskrnl!ExDeleteResourceLite` at `0x180071b80`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180071b0c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180071b0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180071b65`
- `ntoskrnl!ExReleaseResourceLite` at `0x180071b65`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180071b71`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180071b71`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180071afb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180071afb`

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
0x180071ae0  test    rcx, rcx
0x180071ae3  jz      locret_180071BAF
0x180071ae9  mov     [rsp+arg_0], rbx
0x180071aee  mov     [rsp+arg_8], rsi
0x180071af3  push    rdi
0x180071af4  sub     rsp, 20h
0x180071af8  mov     rdi, rcx
0x180071afb  call    cs:__imp_KeEnterGuardedRegion
0x180071b02  nop     dword ptr [rax+rax+00h]
0x180071b07  mov     dl, 1; Wait
0x180071b09  mov     rcx, rdi; Resource
0x180071b0c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180071b13  nop     dword ptr [rax+rax+00h]
0x180071b18  lea     rsi, [rdi+68h]
0x180071b1c  mov     rbx, [rsi]
0x180071b1f  cmp     rbx, rsi
0x180071b22  jz      short loc_180071B62
0x180071b24  cmp     [rbx+8], rsi
0x180071b28  jnz     short loc_180071B5B
0x180071b2a  mov     rax, [rbx]
0x180071b2d  cmp     [rax+8], rbx
0x180071b31  jnz     short loc_180071B5B
0x180071b33  mov     [rsi], rax
0x180071b36  mov     [rax+8], rsi
0x180071b3a  cmp     qword ptr [rbx+10h], 0
0x180071b3f  jz      short loc_180071B51
0x180071b41  mov     rcx, [rbx+18h]; Object
0x180071b45  call    cs:__imp_ObfDereferenceObject
0x180071b4c  nop     dword ptr [rax+rax+00h]
0x180071b51  mov     rcx, rbx; P
0x180071b54  call    BCryptFree
0x180071b59  jmp     short loc_180071B1C
0x180071b5b  mov     ecx, 3
0x180071b60  int     29h; Win8: RtlFailFast(ecx)
0x180071b62  mov     rcx, rdi; Resource
0x180071b65  call    cs:__imp_ExReleaseResourceLite
0x180071b6c  nop     dword ptr [rax+rax+00h]
0x180071b71  call    cs:__imp_KeLeaveGuardedRegion
0x180071b78  nop     dword ptr [rax+rax+00h]
0x180071b7d  mov     rcx, rdi; Resource
0x180071b80  call    cs:__imp_ExDeleteResourceLite
0x180071b87  nop     dword ptr [rax+rax+00h]
0x180071b8c  mov     edx, 62676E43h; Tag
0x180071b91  mov     rcx, rdi; P
0x180071b94  call    cs:__imp_ExFreePoolWithTag
0x180071b9b  nop     dword ptr [rax+rax+00h]
0x180071ba0  mov     rbx, [rsp+28h+arg_0]
0x180071ba5  mov     rsi, [rsp+28h+arg_8]
0x180071baa  add     rsp, 20h
0x180071bae  pop     rdi
0x180071baf  retn
```
