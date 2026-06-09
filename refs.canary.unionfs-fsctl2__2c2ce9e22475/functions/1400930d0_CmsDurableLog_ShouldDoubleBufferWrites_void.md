# CmsDurableLog::ShouldDoubleBufferWrites(void)

- ea: `0x1400930d0`
- end: `0x140093356`
- name: `?ShouldDoubleBufferWrites@CmsDurableLog@@AEAAPEAU_SmsMergeState@@XZ`
- size: `646`
- prototype: `struct _SmsMergeState *__fastcall(CmsDurableLog *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400602cc`

## callees

- `0x140062510`
- `0x1400930d0`
- `0x1400c8574`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400932eb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093327`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400932eb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093327`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400930e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400930e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140093132`
- `ntoskrnl!KeReleaseSpinLock` at `0x140093132`
- `ntoskrnl!ExAllocatePool2` at `0x140093199`
- `ntoskrnl!ExAllocatePool2` at `0x140093243`
- `ntoskrnl!ExAllocatePool2` at `0x140093199`
- `ntoskrnl!ExAllocatePool2` at `0x140093243`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093159`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093208`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093159`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093208`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f97f2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9804`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f97f2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9804`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093308`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093345`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093308`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093345`

## string_xrefs

- `0x1401f9816`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
struct _SmsMergeState *__fastcall CmsDurableLog::ShouldDoubleBufferWrites(KSPIN_LOCK *this)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  KIRQL v4; // al
  KSPIN_LOCK v5; // rdx
  unsigned int v6; // r8d
  struct _SmsMergeState *result; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 Pool2; // rax
  int v11; // ecx
  _DWORD *v12; // rbx
  unsigned int *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // r14d
  struct _NPAGED_LOOKASIDE_LIST *v17; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx

  v2 = 0;
  v3 = 0;
  v4 = KeAcquireSpinLockRaiseToDpc(this + 5);
  v5 = this[11];
  for ( *((_BYTE *)this + 48) = v4; v5; v2 = v6 )
  {
    v6 = v2 + *(_DWORD *)(v5 + 36);
    if ( v6 > 0x40000 )
      break;
    if ( v3 >= MsPerfParams )
      break;
    v5 = *(_QWORD *)(v5 + 48);
    ++v3;
  }
  KeReleaseSpinLock(this + 5, v4);
  if ( v3 < dword_14026214C )
    return 0;
  v8 = qword_140262450 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v8 < 0x20u )
  {
    v8 = 0;
    v9 = 48;
    goto LABEL_9;
  }
  if ( *(_BYTE *)(v8 + 8) )
  {
    v17 = (struct _NPAGED_LOOKASIDE_LIST *)(v8 + 64);
    if ( *(_BYTE *)(v8 + 9) )
      Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v17);
    else
      Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v17);
LABEL_17:
    if ( Pool2 )
      goto LABEL_18;
    goto LABEL_16;
  }
  if ( (int)*(_QWORD *)(v8 + 88) > (int)HIDWORD(*(_QWORD *)(v8 + 88)) )
  {
    v11 = _InterlockedDecrement((volatile signed __int32 *)(v8 + 88));
    if ( v11 >= *(_DWORD *)(v8 + 92) && v11 >= 0 )
    {
      Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v8 + 64));
      goto LABEL_17;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 88));
  }
LABEL_16:
  v9 = *(unsigned int *)(v8 + 4);
LABEL_9:
  Pool2 = ExAllocatePool2(66, v9, 1766871885);
  if ( (Pool2 & 0xF) != 0 )
    goto LABEL_44;
  if ( !Pool2 )
    return 0;
LABEL_18:
  *(_QWORD *)Pool2 = v8;
  v12 = (_DWORD *)(Pool2 + 16);
  if ( Pool2 == -16 )
    return 0;
  v13 = (unsigned int *)(qword_140262448 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v2 > (unsigned __int64)*v13 )
  {
    v13 = 0;
    v14 = v2 + 16LL;
    goto LABEL_21;
  }
  if ( !*((_BYTE *)v13 + 8) )
  {
    if ( (int)*((_QWORD *)v13 + 11) > (int)HIDWORD(*((_QWORD *)v13 + 11)) )
    {
      v16 = _InterlockedDecrement((volatile signed __int32 *)v13 + 22);
      if ( v16 >= (int)v13[23] && v16 >= 0 )
      {
        v15 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)v13 + 4);
        goto LABEL_29;
      }
      _InterlockedIncrement((volatile signed __int32 *)v13 + 22);
    }
LABEL_28:
    v14 = v13[1];
LABEL_21:
    v15 = ExAllocatePool2(66, v14, 1766871885);
    if ( (v15 & 0xF) == 0 )
    {
      if ( !v15 )
        goto LABEL_31;
      goto LABEL_30;
    }
LABEL_44:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
  v18 = (struct _NPAGED_LOOKASIDE_LIST *)(v13 + 16);
  if ( *((_BYTE *)v13 + 9) )
    v15 = (__int64)ExAllocateFromNPagedLookasideList(v18);
  else
    v15 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v18);
LABEL_29:
  if ( !v15 )
    goto LABEL_28;
LABEL_30:
  *(_QWORD *)v15 = v13;
  v15 += 16;
LABEL_31:
  *(_QWORD *)v12 = v15;
  if ( !v15 )
  {
    CmsLookasides::Free(v12);
    return 0;
  }
  result = (struct _SmsMergeState *)v12;
  v12[2] = v2;
  v12[6] = 0;
  v12[3] = 0;
  return result;
}

```

## disassembly

```asm
0x1400930d0  push    rbx
0x1400930d2  push    rbp
0x1400930d3  push    rsi
0x1400930d4  push    rdi
0x1400930d5  sub     rsp, 28h
0x1400930d9  mov     rbx, rcx
0x1400930dc  xor     esi, esi
0x1400930de  add     rcx, 28h ; '('; SpinLock
0x1400930e2  xor     edi, edi
0x1400930e4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400930eb  nop     dword ptr [rax+rax+00h]
0x1400930f0  mov     rdx, [rbx+58h]
0x1400930f4  mov     [rbx+30h], al
0x1400930f7  test    rdx, rdx
0x1400930fa  jz      short loc_140093126
0x1400930fc  nop     dword ptr [rax+00h]
0x140093100  mov     r8d, [rdx+24h]
0x140093104  add     r8d, esi
0x140093107  cmp     r8d, 40000h
0x14009310e  ja      short loc_140093126
0x140093110  cmp     edi, cs:MsPerfParams
0x140093116  jnb     short loc_140093126
0x140093118  mov     rdx, [rdx+30h]
0x14009311c  inc     edi
0x14009311e  mov     esi, r8d
0x140093121  test    rdx, rdx
0x140093124  jnz     short loc_140093100
0x140093126  movzx   edx, al; NewIrql
0x140093129  mov     [rsp+48h+arg_0], r14
0x14009312e  lea     rcx, [rbx+28h]; SpinLock
0x140093132  call    cs:__imp_KeReleaseSpinLock
0x140093139  nop     dword ptr [rax+rax+00h]
0x14009313e  cmp     edi, cs:dword_14026214C
0x140093144  jnb     short loc_140093157
0x140093146  xor     eax, eax
0x140093148  mov     r14, [rsp+48h+arg_0]
0x14009314d  add     rsp, 28h
0x140093151  pop     rdi
0x140093152  pop     rsi
0x140093153  pop     rbp
0x140093154  pop     rbx
0x140093155  retn
0x140093157  xor     ecx, ecx; ProcNumber
0x140093159  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140093160  nop     dword ptr [rax+rax+00h]
0x140093165  xor     edx, edx
0x140093167  mov     r14d, 0FFFFFFFFh
0x14009316d  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140093173  lea     rbx, [rdx+rdx*2]
0x140093177  shl     rbx, 6
0x14009317b  add     rbx, cs:qword_140262450
0x140093182  cmp     dword ptr [rbx], 20h ; ' '
0x140093185  jnb     short loc_1400931B4
0x140093187  xor     ebx, ebx
0x140093189  mov     edx, 30h ; '0'
0x14009318e  mov     ecx, 42h ; 'B'
0x140093193  mov     r8d, 6950534Dh
0x140093199  call    cs:__imp_ExAllocatePool2
0x1400931a0  nop     dword ptr [rax+rax+00h]
0x1400931a5  test    al, 0Fh
0x1400931a7  jnz     loc_1401F9816
0x1400931ad  test    rax, rax
0x1400931b0  jz      short loc_140093146
0x1400931b2  jmp     short loc_1400931F4
0x1400931b4  cmp     byte ptr [rbx+8], 0
0x1400931b8  jnz     loc_1400932DD
0x1400931be  mov     rcx, [rbx+58h]
0x1400931c2  mov     rax, rcx
0x1400931c5  shr     rax, 20h
0x1400931c9  cmp     ecx, eax
0x1400931cb  jle     short loc_1400931EA
0x1400931cd  nop
0x1400931ce  mov     ecx, r14d
0x1400931d1  lock xadd [rbx+58h], ecx
0x1400931d6  nop
0x1400931d7  dec     ecx
0x1400931d9  mov     eax, [rbx+5Ch]
0x1400931dc  cmp     ecx, eax
0x1400931de  jge     loc_1400932FC
0x1400931e4  nop
0x1400931e5  lock inc dword ptr [rbx+58h]
0x1400931e9  nop
0x1400931ea  mov     edx, [rbx+4]
0x1400931ed  jmp     short loc_14009318E
0x1400931ef  test    rax, rax
0x1400931f2  jz      short loc_1400931EA
0x1400931f4  mov     [rax], rbx
0x1400931f7  lea     rbx, [rax+10h]
0x1400931fb  test    rbx, rbx
0x1400931fe  jz      loc_140093146
0x140093204  xor     ecx, ecx; ProcNumber
0x140093206  mov     ebp, esi
0x140093208  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009320f  nop     dword ptr [rax+rax+00h]
0x140093214  xor     edx, edx
0x140093216  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14009321c  lea     rdi, [rdx+rdx*2]
0x140093220  shl     rdi, 6
0x140093224  add     rdi, cs:qword_140262448
0x14009322b  mov     eax, [rdi]
0x14009322d  cmp     rbp, rax
0x140093230  jbe     short loc_14009325E
0x140093232  xor     edi, edi
0x140093234  lea     rdx, [rbp+10h]
0x140093238  mov     ecx, 42h ; 'B'
0x14009323d  mov     r8d, 6950534Dh
0x140093243  call    cs:__imp_ExAllocatePool2
0x14009324a  nop     dword ptr [rax+rax+00h]
0x14009324f  test    al, 0Fh
0x140093251  jnz     loc_1401F9816
0x140093257  test    rax, rax
0x14009325a  jz      short loc_1400932A5
0x14009325c  jmp     short loc_14009329E
0x14009325e  cmp     byte ptr [rdi+8], 0
0x140093262  jnz     loc_140093319
0x140093268  mov     rcx, [rdi+58h]
0x14009326c  mov     rax, rcx
0x14009326f  shr     rax, 20h
0x140093273  cmp     ecx, eax
0x140093275  jle     short loc_140093294
0x140093277  nop
0x140093278  lock xadd [rdi+58h], r14d
0x14009327e  nop
0x14009327f  dec     r14d
0x140093282  mov     eax, [rdi+5Ch]
0x140093285  cmp     r14d, eax
0x140093288  jge     loc_140093338
0x14009328e  nop
0x14009328f  lock inc dword ptr [rdi+58h]
0x140093293  nop
0x140093294  mov     edx, [rdi+4]
0x140093297  jmp     short loc_140093238
0x140093299  test    rax, rax
0x14009329c  jz      short loc_140093294
0x14009329e  mov     [rax], rdi
0x1400932a1  add     rax, 10h
0x1400932a5  mov     [rbx], rax
0x1400932a8  test    rax, rax
0x1400932ab  jz      short loc_1400932D0
0x1400932ad  mov     r14, [rsp+48h+arg_0]
0x1400932b2  mov     rax, rbx
0x1400932b5  mov     [rbx+8], esi
0x1400932b8  mov     dword ptr [rbx+18h], 0
0x1400932bf  mov     dword ptr [rbx+0Ch], 0
0x1400932c6  add     rsp, 28h
0x1400932ca  pop     rdi
0x1400932cb  pop     rsi
0x1400932cc  pop     rbp
0x1400932cd  pop     rbx
0x1400932ce  retn
0x1400932d0  mov     rcx, rbx; void *
0x1400932d3  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1400932d8  jmp     loc_140093146
0x1400932dd  cmp     byte ptr [rbx+9], 0
0x1400932e1  lea     rcx, [rbx+40h]; Lookaside
0x1400932e5  jz      loc_1401F97F2
0x1400932eb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400932f2  nop     dword ptr [rax+rax+00h]
0x1400932f7  jmp     loc_1400931EF
0x1400932fc  test    ecx, ecx
0x1400932fe  js      loc_1400931E4
0x140093304  lea     rcx, [rbx+40h]; ListHead
0x140093308  call    cs:__imp_ExpInterlockedPopEntrySList
0x14009330f  nop     dword ptr [rax+rax+00h]
0x140093314  jmp     loc_1400931EF
0x140093319  cmp     byte ptr [rdi+9], 0
0x14009331d  lea     rcx, [rdi+40h]; Lookaside
0x140093321  jz      loc_1401F9804
0x140093327  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14009332e  nop     dword ptr [rax+rax+00h]
0x140093333  jmp     loc_140093299
0x140093338  test    r14d, r14d
0x14009333b  js      loc_14009328E
0x140093341  lea     rcx, [rdi+40h]; ListHead
0x140093345  call    cs:__imp_ExpInterlockedPopEntrySList
0x14009334c  nop     dword ptr [rax+rax+00h]
0x140093351  jmp     loc_140093299
0x1401f97f2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f97f9  nop     dword ptr [rax+rax+00h]
0x1401f97fe  nop
0x1401f97ff  jmp     loc_1400931EF
0x1401f9804  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f980b  nop     dword ptr [rax+rax+00h]
0x1401f9810  nop
0x1401f9811  jmp     loc_140093299
0x1401f9816  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1401f981d  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
