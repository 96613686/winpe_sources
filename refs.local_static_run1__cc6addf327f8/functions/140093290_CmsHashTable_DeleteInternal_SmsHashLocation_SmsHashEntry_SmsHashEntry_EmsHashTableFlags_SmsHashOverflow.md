# CmsHashTable::DeleteInternal(_SmsHashLocation *,SmsHashEntry *,SmsHashEntry *,EmsHashTableFlags,_SmsHashOverflow * *)

- ea: `0x140093290`
- end: `0x14009346e`
- name: `?DeleteInternal@CmsHashTable@@AEAAXPEAU_SmsHashLocation@@PEAUSmsHashEntry@@1W4EmsHashTableFlags@@PEAPEAU_SmsHashOverflow@@@Z`
- size: `478`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140016440`
- `0x14001e060`
- `0x1400568e0`

## callees

- `0x140093290`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400933db`
- `ntoskrnl!KeSetEvent` at `0x1400933db`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14009331b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14009331b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009335a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009335a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201af8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140201af8`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400933f8`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400933f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093441`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201b14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093441`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201b14`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14009338f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14009338f`

## pseudocode

```c
__int64 __fastcall CmsHashTable::DeleteInternal(__int64 a1, __int64 *a2, _QWORD *a3, __int64 a4, char a5, _QWORD *a6)
{
  __int64 v6; // r14
  _QWORD *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v13; // rcx
  void *v14; // rdx
  __int64 result; // rax
  __int64 v16; // rax
  __int64 v18; // rax
  __int64 *v19; // r15
  __int64 **v20; // rcx
  struct _KEVENT *v21; // rcx
  __int64 v22; // rcx

  v6 = a3[1];
  a3[1] = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( *a2 != -1 )
    {
LABEL_3:
      *a2 = 0;
      goto LABEL_4;
    }
  }
  else if ( *(_QWORD *)a4 != -1 )
  {
    goto LABEL_3;
  }
  *a3 = 0;
  v16 = *(_QWORD *)(a4 + 8);
  if ( (*(_DWORD *)(v16 + 4))-- == 1 )
  {
    v10 = *(_QWORD **)(a4 + 8);
    *(_QWORD *)(a4 + 8) = 0;
    goto LABEL_3;
  }
LABEL_4:
  v11 = _InterlockedExchange64((volatile __int64 *)a4, *a2);
  *a2 = 0;
  if ( v11 == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_14026C3C0, 0);
    v18 = qword_14026C3C8;
    if ( (__int64 *)qword_14026C3C8 != &qword_14026C3C8 )
    {
      do
      {
        v19 = *(__int64 **)v18;
        if ( *(_QWORD *)(v18 + 24) == a4 )
        {
          if ( v19[1] != v18 || (v20 = *(__int64 ***)(v18 + 8), *v20 != (__int64 *)v18) )
            __fastfail(3u);
          *v20 = v19;
          v19[1] = (__int64)v20;
          v21 = *(struct _KEVENT **)(v18 + 16);
          *(_QWORD *)v18 = 0;
          KeSetEvent(v21, 0, 0);
        }
        v18 = (__int64)v19;
      }
      while ( v19 != &qword_14026C3C8 );
    }
    ExReleasePushLockEx(&qword_14026C3C0, 0);
  }
  if ( (a5 & 1) == 0 && v6 )
  {
    v12 = *(_QWORD *)(v6 - 16);
    if ( v12 )
    {
      if ( *(_BYTE *)(v12 + 8) )
      {
        v13 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 64);
        v14 = (void *)(v6 - 16);
        if ( *(_BYTE *)(v12 + 9) )
          ExFreeToNPagedLookasideList(v13, v14);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v13, v14);
        goto LABEL_11;
      }
      v22 = *(_QWORD *)(v12 + 88);
      if ( (int)v22 < *(_DWORD *)(v12 + 80) || SHIDWORD(v22) >= (int)v22 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v12 + 64), (PSLIST_ENTRY)(v6 - 16));
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 88));
        goto LABEL_11;
      }
    }
    ExFreePoolWithTag((PVOID)(v6 - 16), 0);
  }
LABEL_11:
  if ( v10 )
  {
    if ( a6 )
    {
      *v10 = *a6;
      *a6 = v10;
    }
    else
    {
      ExFreePoolWithTag(v10, 0);
    }
  }
  result = 16LL * *((unsigned int *)a2 + 2);
  _InterlockedDecrement((volatile signed __int32 *)(result + a1 + 12));
  return result;
}

```

## disassembly

```asm
0x140093290  mov     [rsp+arg_18], rbx
0x140093295  push    rbp
0x140093296  push    rsi
0x140093297  push    rdi
0x140093298  push    r12
0x14009329a  push    r14
0x14009329c  sub     rsp, 20h
0x1400932a0  mov     r14, [r8+8]
0x1400932a4  xor     r12d, r12d
0x1400932a7  mov     [r8+8], r12
0x1400932ab  mov     rdi, r9
0x1400932ae  mov     rbx, rdx
0x1400932b1  mov     rbp, rcx
0x1400932b4  mov     esi, r12d
0x1400932b7  test    rdx, rdx
0x1400932ba  jz      loc_140093410
0x1400932c0  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x1400932c4  jz      loc_140093368
0x1400932ca  mov     [rdx], r12
0x1400932cd  mov     rax, [rdx]
0x1400932d0  xchg    rax, [r9]
0x1400932d3  mov     [rsp+48h+arg_0], r13
0x1400932d8  mov     [rsp+48h+arg_10], r15
0x1400932dd  mov     [rdx], r12
0x1400932e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400932e4  jz      loc_140093386
0x1400932ea  test    [rsp+48h+arg_20], 1
0x1400932ef  jnz     short loc_140093327
0x1400932f1  test    r14, r14
0x1400932f4  jz      short loc_140093327
0x1400932f6  mov     rdi, [r14-10h]
0x1400932fa  test    rdi, rdi
0x1400932fd  jz      loc_14009343B
0x140093303  cmp     [rdi+8], r12b
0x140093307  jz      loc_14009341F
0x14009330d  lea     rcx, [rdi+40h]; Lookaside
0x140093311  lea     rdx, [r14-10h]; Entry
0x140093315  cmp     [rdi+9], r12b
0x140093319  jz      short loc_14009335A
0x14009331b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140093322  nop     dword ptr [rax+rax+00h]
0x140093327  test    rsi, rsi
0x14009332a  jnz     loc_140093452
0x140093330  mov     eax, [rbx+8]
0x140093333  nop
0x140093334  mov     r15, [rsp+48h+arg_10]
0x140093339  mov     r13, [rsp+48h+arg_0]
0x14009333e  mov     rbx, [rsp+48h+arg_18]
0x140093343  shl     rax, 4
0x140093347  lock dec dword ptr [rax+rbp+0Ch]
0x14009334c  nop
0x14009334d  add     rsp, 20h
0x140093351  pop     r14
0x140093353  pop     r12
0x140093355  pop     rdi
0x140093356  pop     rsi
0x140093357  pop     rbp
0x140093358  retn
0x14009335a  call    cs:__imp_ExFreeToPagedLookasideList
0x140093361  nop     dword ptr [rax+rax+00h]
0x140093366  jmp     short loc_140093327
0x140093368  mov     [r8], r12
0x14009336b  mov     rax, [r9+8]
0x14009336f  add     dword ptr [rax+4], 0FFFFFFFFh
0x140093373  jnz     loc_1400932CD
0x140093379  mov     rsi, [r9+8]
0x14009337d  mov     [r9+8], r12
0x140093381  jmp     loc_1400932CA
0x140093386  xor     edx, edx
0x140093388  lea     rcx, qword_14026C3C0
0x14009338f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140093396  nop     dword ptr [rax+rax+00h]
0x14009339b  mov     rax, cs:qword_14026C3C8
0x1400933a2  lea     r13, qword_14026C3C8
0x1400933a9  cmp     rax, r13
0x1400933ac  jz      short loc_1400933EF
0x1400933ae  xchg    ax, ax
0x1400933b0  mov     r15, [rax]
0x1400933b3  cmp     [rax+18h], rdi
0x1400933b7  jnz     short loc_1400933E7
0x1400933b9  cmp     [r15+8], rax
0x1400933bd  jnz     short loc_140093409
0x1400933bf  mov     rcx, [rax+8]
0x1400933c3  cmp     [rcx], rax
0x1400933c6  jnz     short loc_140093409
0x1400933c8  mov     [rcx], r15
0x1400933cb  xor     r8d, r8d; Wait
0x1400933ce  mov     [r15+8], rcx
0x1400933d2  xor     edx, edx; Increment
0x1400933d4  mov     rcx, [rax+10h]; Event
0x1400933d8  mov     [rax], r12
0x1400933db  call    cs:__imp_KeSetEvent
0x1400933e2  nop     dword ptr [rax+rax+00h]
0x1400933e7  mov     rax, r15
0x1400933ea  cmp     r15, r13
0x1400933ed  jnz     short loc_1400933B0
0x1400933ef  xor     edx, edx
0x1400933f1  lea     rcx, qword_14026C3C0
0x1400933f8  call    cs:__imp_ExReleasePushLockEx
0x1400933ff  nop     dword ptr [rax+rax+00h]
0x140093404  jmp     loc_1400932EA
0x140093409  mov     ecx, 3
0x14009340e  int     29h; Win8: RtlFailFast(ecx)
0x140093410  cmp     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x140093414  jnz     loc_1400932CA
0x14009341a  jmp     loc_140093368
0x14009341f  mov     rcx, [rdi+58h]
0x140093423  cmp     ecx, [rdi+50h]
0x140093426  jl      loc_140201AF0
0x14009342c  mov     rax, rcx
0x14009342f  shr     rax, 20h
0x140093433  cmp     eax, ecx
0x140093435  jge     loc_140201AF0
0x14009343b  xor     edx, edx; Tag
0x14009343d  lea     rcx, [r14-10h]; P
0x140093441  call    cs:__imp_ExFreePoolWithTag
0x140093448  nop     dword ptr [rax+rax+00h]
0x14009344d  jmp     loc_140093327
0x140093452  mov     rcx, [rsp+48h+arg_28]
0x140093457  test    rcx, rcx
0x14009345a  jz      loc_140201B0F
0x140093460  mov     rax, [rcx]
0x140093463  mov     [rsi], rax
0x140093466  mov     [rcx], rsi
0x140093469  jmp     loc_140093330
0x140201af0  lea     rcx, [rdi+40h]; ListHead
0x140201af4  lea     rdx, [r14-10h]; ListEntry
0x140201af8  call    cs:__imp_ExpInterlockedPushEntrySList
0x140201aff  nop     dword ptr [rax+rax+00h]
0x140201b04  nop
0x140201b05  lock inc dword ptr [rdi+58h]
0x140201b09  nop
0x140201b0a  jmp     loc_140093327
0x140201b0f  xor     edx, edx; Tag
0x140201b11  mov     rcx, rsi; P
0x140201b14  call    cs:__imp_ExFreePoolWithTag
0x140201b1b  nop     dword ptr [rax+rax+00h]
0x140201b20  nop
0x140201b21  jmp     loc_140093330
```
