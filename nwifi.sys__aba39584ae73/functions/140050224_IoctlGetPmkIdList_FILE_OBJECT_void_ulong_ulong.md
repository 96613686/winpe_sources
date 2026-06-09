# IoctlGetPmkIdList(_FILE_OBJECT *,void *,ulong,ulong *)

- ea: `0x140050224`
- end: `0x140050546`
- name: `?IoctlGetPmkIdList@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z`
- size: `802`
- prototype: `int(struct _FILE_OBJECT *, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140033a14`

## callees

- `0x140020dc0`
- `0x140020f20`
- `0x140050224`
- `0x1400547f8`
- `0x140090bd8`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140050355`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140050355`
- `ntoskrnl!ExAllocatePool2` at `0x14005036a`
- `ntoskrnl!ExAllocatePool2` at `0x14005036a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400504d7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400504d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400504eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400504eb`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400503ff`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400503ff`
- `NDIS!NdisReleaseRWLock` at `0x140050499`
- `NDIS!NdisReleaseRWLock` at `0x140050499`

## pseudocode

```c
__int64 __fastcall IoctlGetPmkIdList(struct _FILE_OBJECT *a1, unsigned int *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int *v4; // r12
  unsigned int v5; // r15d
  __int64 v7; // r13
  unsigned int PmkId; // ebx
  __int64 v9; // r9
  __int64 v10; // r8
  unsigned int v11; // ecx
  unsigned int v12; // edi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v16; // rsi
  _DWORD *v17; // rbp
  unsigned int v18; // edi
  __int64 v19; // r12
  __int64 v20; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+A0h] [rbp+8h] BYREF
  PNPAGED_LOOKASIDE_LIST *v23; // [rsp+A8h] [rbp+10h]
  unsigned int v24; // [rsp+B0h] [rbp+18h]
  unsigned int *v25; // [rsp+B8h] [rbp+20h]

  v25 = a4;
  v24 = a3;
  v4 = a4;
  v5 = a3;
  v7 = *((_QWORD *)a1->FsContext + 2);
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( a3 < 0x2C )
  {
    PmkId = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 357, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a3, 44);
    return PmkId;
  }
  v9 = *a2;
  if ( (_DWORD)v9 )
  {
    PmkId = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 358, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v9, 1);
    return PmkId;
  }
  v10 = a2[2];
  v11 = 28 * v10;
  if ( (unsigned __int64)(28 * v10) > 0xFFFFFFFF )
  {
    v12 = 0;
    v11 = -1;
LABEL_35:
    PmkId = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_dDDD(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v10, v5, v10, v11, v12);
    return PmkId;
  }
  v12 = v11 + 16;
  if ( v11 + 16 < v11 )
  {
    v12 = -1;
    goto LABEL_35;
  }
  if ( v5 < v12 )
    goto LABEL_35;
  v13 = v11 + 32;
  if ( v12 >= 0xFFFFFFF0 )
    goto LABEL_23;
  if ( v13 > 0x40 )
  {
    if ( v13 > 0x100 )
    {
      if ( v13 > 0x400 )
      {
        if ( v13 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 2053731191);
          goto LABEL_22;
        }
        p_WaitListHead = &stru_1400B31C0;
      }
      else
      {
        p_WaitListHead = &Lookaside;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    }
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_22:
  v23 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  v16 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
  {
LABEL_23:
    PmkId = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 360, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v12);
    return PmkId;
  }
  Pool2[2] = 2053731191;
  *(_QWORD *)Pool2 = p_WaitListHead;
  v17 = Pool2 + 4;
  PmkId = 0;
  memset(Pool2 + 4, 0, v12);
  *(_QWORD *)v17 = *(_QWORD *)(a2 + 1);
  *((_DWORD *)v16 + 6) = a2[3];
  *((_DWORD *)v16 + 5) = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState, 0);
  v18 = 0;
  if ( a2[2] )
  {
    do
    {
      v19 = 7LL * v18;
      PmkId = Dot11GetPmkId((struct _DOT11_PMK_CACHE *)(v7 + 8168));
      if ( !PmkId )
      {
        v20 = 7LL * *((unsigned int *)v16 + 5);
        v17[v20 + 3] = a2[v19 + 4];
        LOWORD(v17[v20 + 4]) = a2[v19 + 5];
        ++*((_DWORD *)v16 + 5);
      }
      ++v18;
    }
    while ( v18 < a2[2] );
    v16 = v23;
    v5 = v24;
    v4 = v25;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState);
  *v4 = 28 * v17[1] + 12;
  memset(a2, 0, v5);
  memmove(a2, v17, *v4);
  if ( *v16 )
    ExFreeToNPagedLookasideList(*v16, v16);
  else
    ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
  return PmkId;
}

```

## disassembly

```asm
0x140050224  mov     r11, rsp
0x140050227  mov     [r11+20h], r9
0x14005022b  mov     [r11+18h], r8d
0x14005022f  push    rbx
0x140050230  push    rbp
0x140050231  push    rsi
0x140050232  push    rdi
0x140050233  push    r12
0x140050235  push    r13
0x140050237  push    r14
0x140050239  push    r15
0x14005023b  sub     rsp, 58h
0x14005023f  mov     rax, [rcx+18h]
0x140050243  mov     r12, r9
0x140050246  mov     r15d, r8d
0x140050249  mov     r14, rdx
0x14005024c  mov     r13, [rax+10h]
0x140050250  xor     eax, eax
0x140050252  mov     [rsp+98h+var_50], r13
0x140050257  mov     byte ptr [r11+8], 0
0x14005025c  mov     [r11+9], ax
0x140050261  cmp     r8d, 2Ch ; ','
0x140050265  jnb     short loc_1400502A8
0x140050267  mov     ebx, 0C000000Dh
0x14005026c  mov     rcx, cs:WPP_GLOBAL_Control
0x140050273  lea     rax, WPP_GLOBAL_Control
0x14005027a  cmp     rcx, rax
0x14005027d  jz      loc_140050532
0x140050283  mov     edx, 165h
0x140050288  mov     [rsp+98h+var_78], 2Ch ; ','
0x140050290  mov     r9d, r8d
0x140050293  mov     rcx, [rcx+18h]
0x140050297  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14005029e  call    WPP_SF_Dd
0x1400502a3  jmp     loc_140050532
0x1400502a8  mov     r9d, [rdx]
0x1400502ab  test    r9d, r9d
0x1400502ae  jz      short loc_1400502DB
0x1400502b0  mov     ebx, 0C000000Dh
0x1400502b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400502bc  lea     rax, WPP_GLOBAL_Control
0x1400502c3  cmp     rcx, rax
0x1400502c6  jz      loc_140050532
0x1400502cc  mov     edx, 166h
0x1400502d1  mov     [rsp+98h+var_78], 1
0x1400502d9  jmp     short loc_140050293
0x1400502db  mov     r8d, [rdx+8]
0x1400502df  mov     eax, 0FFFFFFFFh
0x1400502e4  imul    rcx, r8, 1Ch
0x1400502e8  cmp     rcx, rax
0x1400502eb  ja      loc_1400504FD
0x1400502f1  lea     edi, [rcx+10h]
0x1400502f4  cmp     edi, ecx
0x1400502f6  jb      loc_1400504F9
0x1400502fc  cmp     r15d, edi
0x1400502ff  jb      loc_140050501
0x140050305  lea     eax, [rdi+10h]
0x140050308  cmp     eax, 10h
0x14005030b  jb      short loc_140050386
0x14005030d  mov     ecx, 40h ; '@'
0x140050312  mov     ebp, 7A697377h
0x140050317  cmp     eax, ecx
0x140050319  ja      short loc_140050324
0x14005031b  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140050322  jmp     short loc_140050352
0x140050324  cmp     eax, 100h
0x140050329  ja      short loc_140050334
0x14005032b  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140050332  jmp     short loc_140050352
0x140050334  cmp     eax, 400h
0x140050339  ja      short loc_140050344
0x14005033b  lea     rbx, Lookaside
0x140050342  jmp     short loc_140050352
0x140050344  cmp     eax, 800h
0x140050349  ja      short loc_140050363
0x14005034b  lea     rbx, stru_1400B31C0
0x140050352  mov     rcx, rbx; Lookaside
0x140050355  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005035c  nop     dword ptr [rax+rax+00h]
0x140050361  jmp     short loc_140050376
0x140050363  xor     ebx, ebx
0x140050365  mov     edx, eax
0x140050367  mov     r8d, ebp
0x14005036a  call    cs:__imp_ExAllocatePool2
0x140050371  nop     dword ptr [rax+rax+00h]
0x140050376  mov     [rsp+98h+arg_8], rax
0x14005037e  mov     rsi, rax
0x140050381  test    rax, rax
0x140050384  jnz     short loc_1400503BF
0x140050386  mov     ebx, 0C000009Ah
0x14005038b  mov     rcx, cs:WPP_GLOBAL_Control
0x140050392  lea     rax, WPP_GLOBAL_Control
0x140050399  cmp     rcx, rax
0x14005039c  jz      loc_140050532
0x1400503a2  mov     rcx, [rcx+18h]
0x1400503a6  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400503ad  mov     edx, 168h
0x1400503b2  mov     r9d, edi
0x1400503b5  call    WPP_SF_d
0x1400503ba  jmp     loc_140050532
0x1400503bf  mov     [rsi+8], ebp
0x1400503c2  xor     edx, edx; Val
0x1400503c4  mov     [rsi], rbx
0x1400503c7  lea     rbp, [rsi+10h]
0x1400503cb  mov     rcx, rbp; void *
0x1400503ce  mov     r8d, edi; Size
0x1400503d1  xor     ebx, ebx
0x1400503d3  call    memset
0x1400503d8  movsd   xmm0, qword ptr [r14+4]
0x1400503de  lea     rdx, [rsp+98h+LockState]; LockState
0x1400503e6  movsd   qword ptr [rbp+0], xmm0
0x1400503eb  xor     r8d, r8d; Flags
0x1400503ee  mov     eax, [r14+0Ch]
0x1400503f2  mov     [rbp+8], eax
0x1400503f5  mov     [rbp+4], ebx
0x1400503f8  mov     rcx, [r13+90h]; Lock
0x1400503ff  call    cs:__imp_NdisAcquireRWLockWrite
0x140050406  nop     dword ptr [rax+rax+00h]
0x14005040b  xor     edi, edi
0x14005040d  cmp     [r14+8], ebx
0x140050411  jbe     short loc_14005048A
0x140050413  lea     r15, [rbp+12h]
0x140050417  mov     eax, edi
0x140050419  lea     rdx, [r14+10h]
0x14005041d  imul    r12, rax, 1Ch
0x140050421  mov     eax, [rbp+4]
0x140050424  lea     r8, [r13+132Ah]
0x14005042b  imul    r9, rax, 1Ch
0x14005042f  add     rdx, r12
0x140050432  lea     rcx, [r13+1FE8h]; struct _DOT11_PMK_CACHE *
0x140050439  add     r9, r15
0x14005043c  call    Dot11GetPmkId
0x140050441  mov     ebx, eax
0x140050443  test    eax, eax
0x140050445  jnz     short loc_140050465
0x140050447  mov     ecx, [rbp+4]
0x14005044a  imul    rdx, rcx, 1Ch
0x14005044e  mov     ecx, [r12+r14+10h]
0x140050453  mov     [rdx+rbp+0Ch], ecx
0x140050457  movzx   ecx, word ptr [r12+r14+14h]
0x14005045d  mov     [rdx+rbp+10h], cx
0x140050462  inc     dword ptr [rbp+4]
0x140050465  inc     edi
0x140050467  cmp     edi, [r14+8]
0x14005046b  jb      short loc_140050417
0x14005046d  mov     rsi, [rsp+98h+arg_8]
0x140050475  mov     r15d, [rsp+98h+arg_10]
0x14005047d  mov     r13, [rsp+98h+var_50]
0x140050482  mov     r12, [rsp+98h+arg_18]
0x14005048a  mov     rcx, [r13+90h]; Lock
0x140050491  lea     rdx, [rsp+98h+LockState]; LockState
0x140050499  call    cs:__imp_NdisReleaseRWLock
0x1400504a0  nop     dword ptr [rax+rax+00h]
0x1400504a5  imul    eax, [rbp+4], 1Ch
0x1400504a9  xor     edx, edx; Val
0x1400504ab  mov     r8d, r15d; Size
0x1400504ae  mov     rcx, r14; void *
0x1400504b1  add     eax, 0Ch
0x1400504b4  mov     [r12], eax
0x1400504b8  call    memset
0x1400504bd  mov     r8d, [r12]; Size
0x1400504c1  mov     rdx, rbp; Src
0x1400504c4  mov     rcx, r14; void *
0x1400504c7  call    memmove
0x1400504cc  mov     rcx, [rsi]; Lookaside
0x1400504cf  test    rcx, rcx
0x1400504d2  jz      short loc_1400504E5
0x1400504d4  mov     rdx, rsi; Entry
0x1400504d7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400504de  nop     dword ptr [rax+rax+00h]
0x1400504e3  jmp     short loc_140050532
0x1400504e5  mov     edx, [rsi+8]; Tag
0x1400504e8  mov     rcx, rsi; P
0x1400504eb  call    cs:__imp_ExFreePoolWithTag
0x1400504f2  nop     dword ptr [rax+rax+00h]
0x1400504f7  jmp     short loc_140050532
0x1400504f9  mov     edi, eax
0x1400504fb  jmp     short loc_140050501
0x1400504fd  xor     edi, edi
0x1400504ff  mov     ecx, eax
0x140050501  mov     ebx, 0C000000Dh
0x140050506  mov     rdx, cs:WPP_GLOBAL_Control
0x14005050d  lea     rax, WPP_GLOBAL_Control
0x140050514  cmp     rdx, rax
0x140050517  jz      short loc_140050532
0x140050519  mov     [rsp+98h+var_68], edi
0x14005051d  mov     r9d, r15d
0x140050520  mov     [rsp+98h+var_70], ecx
0x140050524  mov     rcx, [rdx+18h]
0x140050528  mov     [rsp+98h+var_78], r8d
0x14005052d  call    WPP_SF_dDDD
0x140050532  mov     eax, ebx
0x140050534  add     rsp, 58h
0x140050538  pop     r15
0x14005053a  pop     r14
0x14005053c  pop     r13
0x14005053e  pop     r12
0x140050540  pop     rdi
0x140050541  pop     rsi
0x140050542  pop     rbp
0x140050543  pop     rbx
0x140050544  retn
```
