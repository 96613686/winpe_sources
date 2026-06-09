# SecPsCalloutAllocateWork

- ea: `0x14002f14c`
- end: `0x14002f2b4`
- name: `SecPsCalloutAllocateWork`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002e7a8`

## callees

- `0x140006684`
- `0x140011610`
- `0x14002f14c`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x14002f26b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14002f26b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f21f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f21f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002f178`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002f178`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f1e9`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f1e9`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14002f247`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14002f247`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002f25c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002f25c`

## pseudocode

```c
PSLIST_ENTRY __fastcall SecPsCalloutAllocateWork(__int64 a1)
{
  char v2; // di
  PSLIST_ENTRY v3; // rbx
  bool v4; // cf
  PSLIST_ENTRY result; // rax
  PACCESS_TOKEN v6; // rax
  struct _KPROCESS *CurrentProcess; // rax

  ++dword_14001B394;
  v2 = 0;
  v3 = ExpInterlockedPopEntrySList(&Lookaside);
  if ( !v3 )
  {
    ++dword_14001B398;
    v3 = (PSLIST_ENTRY)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))qword_14001B3B0)(
                         (unsigned int)dword_14001B3A4,
                         (unsigned int)dword_14001B3AC,
                         (unsigned int)dword_14001B3A8);
    if ( !v3 )
      return 0;
  }
  *v3 = 0;
  v3[1] = 0;
  v3[2] = 0;
  v3[3].Next = 0;
  if ( (int)SecUnicodeToNullTerminatedUnicode(a1, &v3[1].Next + 1) < 0 )
  {
    ++dword_14001B39C;
    v4 = ExQueryDepthSList(&Lookaside) < (USHORT)word_14001B390;
    _mm_lfence();
    if ( v4 )
    {
      ExpInterlockedPushEntrySList(&Lookaside, v3);
    }
    else
    {
      ++dword_14001B3A0;
      ((void (__fastcall *)(PSLIST_ENTRY))qword_14001B3B8)(v3);
    }
    return 0;
  }
  _mm_lfence();
  v6 = PsReferenceImpersonationToken(
         KeGetCurrentThread(),
         (PBOOLEAN)&v3[3].Next + 1,
         (PBOOLEAN)&v3[3].Next + 2,
         (PSECURITY_IMPERSONATION_LEVEL)&v3[3].Next + 1);
  *((_QWORD *)&v3[2].Next + 1) = v6;
  if ( v6 )
  {
    v2 = 1;
  }
  else
  {
    CurrentProcess = IoGetCurrentProcess();
    *((_QWORD *)&v3[2].Next + 1) = PsReferencePrimaryToken(CurrentProcess);
    *(_WORD *)((char *)&v3[3].Next + 1) = 0;
    HIDWORD(v3[3].Next) = 2;
  }
  LOBYTE(v3[3].Next) = v2;
  result = v3;
  LODWORD(v3->Next) = 1;
  return result;
}

```

## disassembly

```asm
0x14002f14c  mov     rax, rsp
0x14002f14f  mov     [rax+8], rbx
0x14002f153  mov     [rax+10h], rsi
0x14002f157  mov     [rax+18h], rdi
0x14002f15b  mov     [rax+20h], r14
0x14002f15f  push    r15
0x14002f161  sub     rsp, 20h
0x14002f165  inc     cs:dword_14001B394
0x14002f16b  lea     r14, Lookaside
0x14002f172  mov     rsi, rcx
0x14002f175  mov     rcx, r14; ListHead
0x14002f178  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002f17f  nop     dword ptr [rax+rax+00h]
0x14002f184  xor     edi, edi
0x14002f186  mov     rbx, rax
0x14002f189  test    rax, rax
0x14002f18c  jnz     short loc_14002F1BC
0x14002f18e  mov     edx, cs:dword_14001B3AC
0x14002f194  mov     rax, cs:qword_14001B3B0
0x14002f19b  mov     r8d, cs:dword_14001B3A8
0x14002f1a2  mov     ecx, cs:dword_14001B3A4
0x14002f1a8  inc     cs:dword_14001B398
0x14002f1ae  call    cs:__guard_dispatch_icall_fptr
0x14002f1b4  mov     rbx, rax
0x14002f1b7  test    rax, rax
0x14002f1ba  jz      short loc_14002F22B
0x14002f1bc  xorps   xmm0, xmm0
0x14002f1bf  lea     rdx, [rbx+18h]
0x14002f1c3  movups  xmmword ptr [rbx], xmm0
0x14002f1c6  xor     eax, eax
0x14002f1c8  mov     rcx, rsi
0x14002f1cb  movups  xmmword ptr [rbx+10h], xmm0
0x14002f1cf  movups  xmmword ptr [rbx+20h], xmm0
0x14002f1d3  mov     [rbx+30h], rax
0x14002f1d7  call    SecUnicodeToNullTerminatedUnicode
0x14002f1dc  test    eax, eax
0x14002f1de  jns     short loc_14002F22F
0x14002f1e0  inc     cs:dword_14001B39C
0x14002f1e6  mov     rcx, r14; SListHead
0x14002f1e9  call    cs:__imp_ExQueryDepthSList
0x14002f1f0  nop     dword ptr [rax+rax+00h]
0x14002f1f5  cmp     ax, cs:word_14001B390
0x14002f1fc  lfence
0x14002f1ff  jb      short loc_14002F219
0x14002f201  inc     cs:dword_14001B3A0
0x14002f207  mov     rcx, rbx
0x14002f20a  mov     rax, cs:qword_14001B3B8
0x14002f211  call    cs:__guard_dispatch_icall_fptr
0x14002f217  jmp     short loc_14002F22B
0x14002f219  mov     rdx, rbx; ListEntry
0x14002f21c  mov     rcx, r14; ListHead
0x14002f21f  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002f226  nop     dword ptr [rax+rax+00h]
0x14002f22b  xor     eax, eax
0x14002f22d  jmp     short loc_14002F298
0x14002f22f  lfence
0x14002f232  mov     rcx, gs:188h; Thread
0x14002f23b  lea     r9, [rbx+34h]; ImpersonationLevel
0x14002f23f  lea     r8, [rbx+32h]; EffectiveOnly
0x14002f243  lea     rdx, [rbx+31h]; CopyOnOpen
0x14002f247  call    cs:__imp_PsReferenceImpersonationToken
0x14002f24e  nop     dword ptr [rax+rax+00h]
0x14002f253  mov     [rbx+28h], rax
0x14002f257  test    rax, rax
0x14002f25a  jnz     short loc_14002F288
0x14002f25c  call    cs:__imp_IoGetCurrentProcess
0x14002f263  nop     dword ptr [rax+rax+00h]
0x14002f268  mov     rcx, rax; Process
0x14002f26b  call    cs:__imp_PsReferencePrimaryToken
0x14002f272  nop     dword ptr [rax+rax+00h]
0x14002f277  mov     [rbx+28h], rax
0x14002f27b  mov     [rbx+31h], di
0x14002f27f  mov     dword ptr [rbx+34h], 2
0x14002f286  jmp     short loc_14002F28B
0x14002f288  mov     dil, 1
0x14002f28b  mov     [rbx+30h], dil
0x14002f28f  mov     rax, rbx
0x14002f292  mov     dword ptr [rbx], 1
0x14002f298  mov     rbx, [rsp+28h+arg_0]
0x14002f29d  mov     rsi, [rsp+28h+arg_8]
0x14002f2a2  mov     rdi, [rsp+28h+arg_10]
0x14002f2a7  mov     r14, [rsp+28h+arg_18]
0x14002f2ac  add     rsp, 20h
0x14002f2b0  pop     r15
0x14002f2b2  retn
```
