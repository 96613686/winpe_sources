# CscOfflineLviewCachepCreateListEntry

- ea: `0x1400530fc`
- end: `0x14005326f`
- name: `CscOfflineLviewCachepCreateListEntry`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400709b0`

## callees

- `0x140010ae8`
- `0x14002f140`
- `0x14002f440`
- `0x1400530fc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005315b`
- `ntoskrnl!ExAllocatePool2` at `0x14005315b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053232`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053232`
- `ntoskrnl!KeInitializeEvent` at `0x140053203`
- `ntoskrnl!KeInitializeEvent` at `0x140053203`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005318d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005318d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005324f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005324f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400531eb`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400531eb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005312e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005312e`

## pseudocode

```c
__int64 __fastcall CscOfflineLviewCachepCreateListEntry(__int64 a1, const void **a2, _QWORD *a3, char a4)
{
  _DWORD *v8; // rbx
  __int64 v9; // r9
  NTSTATUS v10; // edi
  void *Pool2; // rsi
  __int16 v12; // cx

  *a3 = 0;
  v8 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(CscDevExtn + 256));
  if ( !v8 )
    return (unsigned int)-1073741670;
  Pool2 = (void *)ExAllocatePool2(258, *(unsigned __int16 *)a2, 1061124178, v9);
  if ( !Pool2 )
  {
    v10 = -1073741670;
LABEL_10:
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(CscDevExtn + 256), v8);
    return (unsigned int)v10;
  }
  memset(v8, 0, 0xC0u);
  v10 = ExInitializeResourceLite((PERESOURCE)(v8 + 10));
  if ( v10 < 0 )
  {
    ExFreePoolWithTag(Pool2, 0);
    goto LABEL_10;
  }
  *v8 = 191144;
  v12 = *(_WORD *)a2;
  *((_WORD *)v8 + 89) = *(_WORD *)a2;
  *((_WORD *)v8 + 88) = v12;
  *((_QWORD *)v8 + 23) = Pool2;
  memmove(Pool2, a2[1], *(unsigned __int16 *)a2);
  *((_QWORD *)v8 + 4) = a1;
  CscStoreReferenceEntry(a1);
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)v8 + 21);
  KeInitializeEvent((PRKEVENT)v8 + 6, NotificationEvent, 0);
  *((_QWORD *)v8 + 3) = v8 + 4;
  *((_QWORD *)v8 + 2) = v8 + 4;
  if ( a4 )
  {
    *((_BYTE *)v8 + 12) = 2;
    _InterlockedOr(v8 + 2, 2u);
  }
  *a3 = v8;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400530fc  push    rbx
0x1400530fe  push    rbp
0x1400530ff  push    rsi
0x140053100  push    rdi
0x140053101  push    r12
0x140053103  push    r13
0x140053105  push    r14
0x140053107  push    r15
0x140053109  sub     rsp, 28h
0x14005310d  mov     rbp, rcx
0x140053110  mov     qword ptr [r8], 0
0x140053117  mov     rcx, cs:CscDevExtn
0x14005311e  mov     r12b, r9b
0x140053121  add     rcx, 100h; Lookaside
0x140053128  mov     r14, r8
0x14005312b  mov     r15, rdx
0x14005312e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140053135  nop     dword ptr [rax+rax+00h]
0x14005313a  mov     rbx, rax
0x14005313d  test    rax, rax
0x140053140  jnz     short loc_14005314C
0x140053142  mov     edi, 0C000009Ah
0x140053147  jmp     loc_14005325B
0x14005314c  movzx   edx, word ptr [r15]
0x140053150  mov     ecx, 102h
0x140053155  mov     r8d, 3F3F7852h
0x14005315b  call    cs:__imp_ExAllocatePool2
0x140053162  nop     dword ptr [rax+rax+00h]
0x140053167  mov     rsi, rax
0x14005316a  test    rax, rax
0x14005316d  jnz     short loc_140053179
0x14005316f  mov     edi, 0C000009Ah
0x140053174  jmp     loc_14005323E
0x140053179  xor     edx, edx; Val
0x14005317b  mov     r8d, 0C0h; Size
0x140053181  mov     rcx, rbx; void *
0x140053184  call    memset
0x140053189  lea     rcx, [rbx+28h]; Resource
0x14005318d  call    cs:__imp_ExInitializeResourceLite
0x140053194  nop     dword ptr [rax+rax+00h]
0x140053199  mov     edi, eax
0x14005319b  test    eax, eax
0x14005319d  js      loc_14005322D
0x1400531a3  mov     dword ptr [rbx], 2EAA8h
0x1400531a9  mov     r13d, 2
0x1400531af  movzx   ecx, word ptr [r15]
0x1400531b3  mov     [rbx+0B2h], cx
0x1400531ba  mov     [rbx+0B0h], cx
0x1400531c1  mov     rcx, rsi; void *
0x1400531c4  mov     [rbx+0B8h], rsi
0x1400531cb  movzx   r8d, word ptr [r15]; Size
0x1400531cf  mov     rdx, [r15+8]; Src
0x1400531d3  call    memmove
0x1400531d8  mov     rcx, rbp
0x1400531db  mov     [rbx+20h], rbp
0x1400531df  call    CscStoreReferenceEntry
0x1400531e4  lea     rcx, [rbx+0A8h]; RunRef
0x1400531eb  call    cs:__imp_ExInitializeRundownProtection
0x1400531f2  nop     dword ptr [rax+rax+00h]
0x1400531f7  lea     rcx, [rbx+90h]; Event
0x1400531fe  xor     r8d, r8d; State
0x140053201  xor     edx, edx; Type
0x140053203  call    cs:__imp_KeInitializeEvent
0x14005320a  nop     dword ptr [rax+rax+00h]
0x14005320f  lea     rax, [rbx+10h]
0x140053213  mov     [rax+8], rax
0x140053217  mov     [rax], rax
0x14005321a  test    r12b, r12b
0x14005321d  jz      short loc_140053228
0x14005321f  mov     [rbx+0Ch], r13b
0x140053223  lock or [rbx+8], r13d
0x140053228  mov     [r14], rbx
0x14005322b  jmp     short loc_14005325B
0x14005322d  xor     edx, edx; Tag
0x14005322f  mov     rcx, rsi; P
0x140053232  call    cs:__imp_ExFreePoolWithTag
0x140053239  nop     dword ptr [rax+rax+00h]
0x14005323e  mov     rcx, cs:CscDevExtn
0x140053245  mov     rdx, rbx; Entry
0x140053248  add     rcx, 100h; Lookaside
0x14005324f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140053256  nop     dword ptr [rax+rax+00h]
0x14005325b  mov     eax, edi
0x14005325d  add     rsp, 28h
0x140053261  pop     r15
0x140053263  pop     r14
0x140053265  pop     r13
0x140053267  pop     r12
0x140053269  pop     rdi
0x14005326a  pop     rsi
0x14005326b  pop     rbp
0x14005326c  pop     rbx
0x14005326d  retn
```
