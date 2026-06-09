# CcnDestroyPublisher

- ea: `0x18007bc80`
- end: `0x18007bd51`
- name: `CcnDestroyPublisher`
- size: `209`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180073e20`

## callees

- `0x180025ec0`
- `0x18007bc80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18007bd34`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007bd34`
- `ntoskrnl!ObfDereferenceObject` at `0x18007bce5`
- `ntoskrnl!ObfDereferenceObject` at `0x18007bce5`
- `ntoskrnl!ExDeleteResourceLite` at `0x18007bd20`
- `ntoskrnl!ExDeleteResourceLite` at `0x18007bd20`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007bcac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18007bcac`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007bd05`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007bd05`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18007bd11`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18007bd11`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18007bc9b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18007bc9b`

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
0x18007bc80  test    rcx, rcx
0x18007bc83  jz      locret_18007BD4F
0x18007bc89  mov     [rsp+arg_0], rbx
0x18007bc8e  mov     [rsp+arg_8], rsi
0x18007bc93  push    rdi
0x18007bc94  sub     rsp, 20h
0x18007bc98  mov     rdi, rcx
0x18007bc9b  call    cs:__imp_KeEnterGuardedRegion
0x18007bca2  nop     dword ptr [rax+rax+00h]
0x18007bca7  mov     dl, 1; Wait
0x18007bca9  mov     rcx, rdi; Resource
0x18007bcac  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18007bcb3  nop     dword ptr [rax+rax+00h]
0x18007bcb8  lea     rsi, [rdi+68h]
0x18007bcbc  mov     rbx, [rsi]
0x18007bcbf  cmp     rbx, rsi
0x18007bcc2  jz      short loc_18007BD02
0x18007bcc4  cmp     [rbx+8], rsi
0x18007bcc8  jnz     short loc_18007BCFB
0x18007bcca  mov     rax, [rbx]
0x18007bccd  cmp     [rax+8], rbx
0x18007bcd1  jnz     short loc_18007BCFB
0x18007bcd3  mov     [rsi], rax
0x18007bcd6  mov     [rax+8], rsi
0x18007bcda  cmp     qword ptr [rbx+10h], 0
0x18007bcdf  jz      short loc_18007BCF1
0x18007bce1  mov     rcx, [rbx+18h]; Object
0x18007bce5  call    cs:__imp_ObfDereferenceObject
0x18007bcec  nop     dword ptr [rax+rax+00h]
0x18007bcf1  mov     rcx, rbx; P
0x18007bcf4  call    BCryptFree
0x18007bcf9  jmp     short loc_18007BCBC
0x18007bcfb  mov     ecx, 3
0x18007bd00  int     29h; Win8: RtlFailFast(ecx)
0x18007bd02  mov     rcx, rdi; Resource
0x18007bd05  call    cs:__imp_ExReleaseResourceLite
0x18007bd0c  nop     dword ptr [rax+rax+00h]
0x18007bd11  call    cs:__imp_KeLeaveGuardedRegion
0x18007bd18  nop     dword ptr [rax+rax+00h]
0x18007bd1d  mov     rcx, rdi; Resource
0x18007bd20  call    cs:__imp_ExDeleteResourceLite
0x18007bd27  nop     dword ptr [rax+rax+00h]
0x18007bd2c  mov     edx, 62676E43h; Tag
0x18007bd31  mov     rcx, rdi; P
0x18007bd34  call    cs:__imp_ExFreePoolWithTag
0x18007bd3b  nop     dword ptr [rax+rax+00h]
0x18007bd40  mov     rbx, [rsp+28h+arg_0]
0x18007bd45  mov     rsi, [rsp+28h+arg_8]
0x18007bd4a  add     rsp, 20h
0x18007bd4e  pop     rdi
0x18007bd4f  retn
```
