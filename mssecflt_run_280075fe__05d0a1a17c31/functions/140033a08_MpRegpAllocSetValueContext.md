# MpRegpAllocSetValueContext

- ea: `0x140033a08`
- end: `0x140033a8b`
- name: `MpRegpAllocSetValueContext`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003958c`

## callees

- `0x140011610`
- `0x1400119c0`
- `0x140033a08`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033a26`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033a26`

## pseudocode

```c
PSLIST_ENTRY MpRegpAllocSetValueContext()
{
  char *v0; // rdi
  union _SLIST_HEADER *v1; // rcx
  PSLIST_ENTRY v2; // rbx
  __int64 v3; // rdx
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rax
  __int64 v5; // r8
  __int64 v6; // rcx

  v0 = (char *)RegData + 256;
  v1 = (union _SLIST_HEADER *)((char *)RegData + 256);
  ++*((_DWORD *)RegData + 69);
  v2 = ExpInterlockedPopEntrySList(v1);
  if ( v2
    || (v3 = *((unsigned int *)v0 + 11),
        v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v0 + 6),
        v5 = *((unsigned int *)v0 + 10),
        v6 = *((unsigned int *)v0 + 9),
        ++*((_DWORD *)v0 + 6),
        (v2 = (PSLIST_ENTRY)v4(v6, v3, v5)) != 0) )
  {
    memset(v2, 0, 0x58u);
    LODWORD(v2->Next) = 5827329;
    *((_QWORD *)&v2->Next + 1) = MpRegpFreeSetValueContext;
    LOBYTE(v2[5].Next) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x140033a08  mov     [rsp+arg_0], rbx
0x140033a0d  push    rdi
0x140033a0e  sub     rsp, 20h
0x140033a12  mov     rdi, cs:RegData
0x140033a19  add     rdi, 100h
0x140033a20  mov     rcx, rdi; ListHead
0x140033a23  inc     dword ptr [rdi+14h]
0x140033a26  call    cs:__imp_ExpInterlockedPopEntrySList
0x140033a2d  nop     dword ptr [rax+rax+00h]
0x140033a32  mov     rbx, rax
0x140033a35  test    rax, rax
0x140033a38  jnz     short loc_140033A59
0x140033a3a  mov     edx, [rdi+2Ch]
0x140033a3d  mov     rax, [rdi+30h]
0x140033a41  mov     r8d, [rdi+28h]
0x140033a45  mov     ecx, [rdi+24h]
0x140033a48  inc     dword ptr [rdi+18h]
0x140033a4b  call    cs:__guard_dispatch_icall_fptr
0x140033a51  mov     rbx, rax
0x140033a54  test    rax, rax
0x140033a57  jz      short loc_140033A7C
0x140033a59  xor     edx, edx; Val
0x140033a5b  mov     rcx, rbx; void *
0x140033a5e  lea     r8d, [rdx+58h]; Size
0x140033a62  call    memset
0x140033a67  lea     rax, MpRegpFreeSetValueContext
0x140033a6e  mov     dword ptr [rbx], 58EB01h
0x140033a74  mov     [rbx+8], rax
0x140033a78  mov     byte ptr [rbx+50h], 0
0x140033a7c  mov     rax, rbx
0x140033a7f  mov     rbx, [rsp+28h+arg_0]
0x140033a84  add     rsp, 20h
0x140033a88  pop     rdi
0x140033a89  retn
```
