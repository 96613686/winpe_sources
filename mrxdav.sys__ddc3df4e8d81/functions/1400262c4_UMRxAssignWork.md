# UMRxAssignWork

- ea: `0x1400262c4`
- end: `0x1400269d0`
- name: `UMRxAssignWork`
- size: `1804`
- prototype: `void __fastcall(__int64, __int64, unsigned int, _DWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f120`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140006c00`
- `0x1400262c4`
- `0x140026f54`
- `0x140027f1c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002631f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002635b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002639c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400263d9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026416`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026486`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400264d2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002652d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002656b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400265d4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026608`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026673`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026747`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026819`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026893`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400268ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026959`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026997`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002631f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002635b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002639c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400263d9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026416`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026486`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400264d2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002652d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002656b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400265d4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026608`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026673`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026747`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026819`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026893`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400268ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026959`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140026997`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026637`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400267c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026637`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400267c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026696`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400266a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026856`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026869`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026696`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400266a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026856`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026869`
- `ntoskrnl!KeSetEvent` at `0x140026934`
- `ntoskrnl!KeSetEvent` at `0x140026934`
- `ntoskrnl!PsIsThreadTerminating` at `0x140026792`
- `ntoskrnl!PsIsThreadTerminating` at `0x140026792`
- `ntoskrnl!KeRemoveQueueEx` at `0x1400266f4`
- `ntoskrnl!KeRemoveQueueEx` at `0x1400266f4`
- `ntoskrnl!PsRevertToSelf` at `0x140026588`
- `ntoskrnl!PsRevertToSelf` at `0x140026627`
- `ntoskrnl!PsRevertToSelf` at `0x140026588`
- `ntoskrnl!PsRevertToSelf` at `0x140026627`
- `ntoskrnl!KeInsertQueue` at `0x1400268c1`
- `ntoskrnl!KeInsertQueue` at `0x1400268c1`

## pseudocode

```c
void __fastcall UMRxAssignWork(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, unsigned int a5, __int64 a6)
{
  struct _KTHREAD *CurrentThread; // rdi
  unsigned __int64 v9; // r15
  __int64 v11; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax
  unsigned int *v21; // rdi
  unsigned __int64 v22; // rcx
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned __int64 v27; // rdx
  __int64 v28; // rbx
  HANDLE v29; // rax
  unsigned int v30; // eax
  __int64 v31; // rbx
  HANDLE v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // ebp
  __int64 v35; // rbx
  HANDLE v36; // rax
  unsigned int i; // ebp
  struct _LIST_ENTRY *v38; // rdx
  __int64 v39; // rbx
  HANDLE v40; // rax
  int v41; // r15d
  __int64 v42; // rbx
  HANDLE v43; // rax
  unsigned int v44; // ebx
  __int64 v45; // rbx
  HANDLE v46; // rax
  __int64 v47; // rbx
  HANDLE v48; // rax
  __int64 v49; // rbx
  HANDLE v50; // rax
  unsigned int v51; // ebx
  __int64 v52; // rdi
  HANDLE v53; // rax
  PLIST_ENTRY Entry; // [rsp+80h] [rbp+8h] BYREF

  CurrentThread = KeGetCurrentThread();
  Entry = 0;
  v9 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v11, 81, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
      {
        v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v14 = PsGetCurrentThreadId();
        WPP_SF_qq(v13, 82, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v14, a1);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
        {
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v16 = PsGetCurrentThreadId();
          WPP_SF_qq(v15, 83, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v16, CurrentThread);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
          {
            v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v18 = PsGetCurrentThreadId();
            WPP_SF_qq(v17, 84, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v18, a2);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
          {
            v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v20 = PsGetCurrentThreadId();
            WPP_SF_qq(v19, 85, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v20, a4);
          }
        }
      }
    }
  }
  v21 = (unsigned int *)a6;
  v22 = 48;
  *(_QWORD *)(a6 + 8) = 0;
  *v21 = -1073741555;
  if ( a2 )
  {
    if ( !a4 )
    {
LABEL_39:
      v30 = *(_DWORD *)(a1 + 1620);
      if ( v30 >= 0x30 )
        v22 = v30;
      if ( v9 < v22 )
      {
        *v21 = -1073741789;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0 )
        {
          return;
        }
        v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v24 = PsGetCurrentThreadId();
        v25 = 89;
LABEL_21:
        WPP_SF_q(v23, v25, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v24);
        return;
      }
      if ( (*(_DWORD *)(a2 + 20) & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xAu) )
        {
          v31 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v32 = PsGetCurrentThreadId();
          WPP_SF_q(v31, 90, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v32);
        }
        PsRevertToSelf();
        *(_DWORD *)(a2 + 20) &= ~1u;
      }
      KeEnterCriticalRegion();
      v33 = UMRxCompleteUserModeRequest(a1, a2, (unsigned int)v9, v21);
      v34 = v33;
      if ( v33 )
      {
        *v21 = v33;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
        {
          v35 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v36 = PsGetCurrentThreadId();
          WPP_SF_qD(v35, 91, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v36, v34);
        }
        KeLeaveCriticalRegion();
        return;
      }
      KeLeaveCriticalRegion();
      goto LABEL_56;
    }
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 1616) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0 )
        return;
      v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v24 = PsGetCurrentThreadId();
      v25 = 86;
      goto LABEL_21;
    }
    if ( !a4 )
    {
      *v21 = -1073741811;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0 )
        return;
      v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v24 = PsGetCurrentThreadId();
      v25 = 87;
      goto LABEL_21;
    }
  }
  v26 = *(_DWORD *)(a1 + 1620);
  v27 = 48;
  if ( v26 >= 0x30 )
    v27 = v26;
  if ( a5 < v27 )
  {
    *v21 = -1073741789;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0 )
      return;
    v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v24 = PsGetCurrentThreadId();
    v25 = 88;
    goto LABEL_21;
  }
  if ( a2 )
    goto LABEL_39;
  if ( (a4[5] & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xAu) )
    {
      v28 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v29 = PsGetCurrentThreadId();
      WPP_SF_q(v28, 92, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v29);
    }
    PsRevertToSelf();
    a4[5] &= ~1u;
  }
LABEL_56:
  if ( !a4 )
  {
    *v21 = 0;
    return;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 1608));
  for ( i = 1; ; ++i )
  {
    KeRemoveQueueEx((PKQUEUE)(a1 + 1392), 1, 1u, 0, &Entry, 1u);
    v38 = Entry;
    if ( Entry == (PLIST_ENTRY)258 )
    {
      if ( i == 5 * (i / 5)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
      {
        v39 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v40 = PsGetCurrentThreadId();
        WPP_SF_qD(v39, 93, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v40, i);
      }
      continue;
    }
    if ( Entry == (PLIST_ENTRY)192 )
      break;
    if ( Entry == (PLIST_ENTRY)257 )
    {
      if ( PsIsThreadTerminating(KeGetCurrentThread()) )
      {
        *v21 = -1073741536;
        goto LABEL_83;
      }
    }
    else
    {
      if ( Entry == (PLIST_ENTRY)(a1 + 1568) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
        {
          v45 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v46 = PsGetCurrentThreadId();
          WPP_SF_q(v45, 95, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v46);
          v38 = Entry;
        }
        KeInsertQueue((PRKQUEUE)(a1 + 1392), v38);
        goto LABEL_83;
      }
      KeEnterCriticalRegion();
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 1612));
      v41 = UMRxPrepareUserModeRequestBuffer(&Entry[-23].Blink, a1, (__int64)a4, a5, v21);
      if ( !v41 )
      {
        KeLeaveCriticalRegion();
        goto LABEL_83;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v42 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v43 = PsGetCurrentThreadId();
        WPP_SF_qD(v42, 96, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v43, v41);
      }
      v44 = a4[4];
      memset(a4, 0, v44);
      a4[4] = v44;
      KeLeaveCriticalRegion();
    }
  }
  *v21 = 192;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
  {
    v47 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v48 = PsGetCurrentThreadId();
    WPP_SF_q(v47, 94, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v48);
  }
LABEL_83:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1608), 0xFFFFFFFF) != 1 || *(_BYTE *)(a1 + 1616) )
  {
LABEL_88:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v51 = *v21;
      v52 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v53 = PsGetCurrentThreadId();
      WPP_SF_qD(v52, 98, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v53, v51);
    }
  }
  else
  {
    KeSetEvent((PRKEVENT)(a1 + 1584), 0, 0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
      {
        v49 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v50 = PsGetCurrentThreadId();
        WPP_SF_q(v49, 97, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v50);
      }
      goto LABEL_88;
    }
  }
}

```

## disassembly

```asm
0x1400262c4  mov     rax, rsp
0x1400262c7  push    rbx
0x1400262c8  push    rbp
0x1400262c9  push    rsi
0x1400262ca  push    rdi
0x1400262cb  push    r12
0x1400262cd  push    r13
0x1400262cf  push    r14
0x1400262d1  push    r15
0x1400262d3  sub     rsp, 38h
0x1400262d7  mov     rdi, gs:188h
0x1400262e0  mov     r14, r9
0x1400262e3  mov     qword ptr [rax+8], 0
0x1400262eb  mov     rbp, rdx
0x1400262ee  mov     r15d, r8d
0x1400262f1  mov     rsi, rcx
0x1400262f4  mov     rbx, cs:WPP_GLOBAL_Control
0x1400262fb  lea     r13, WPP_GLOBAL_Control
0x140026302  lea     r12, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026309  cmp     rbx, r13
0x14002630c  jz      loc_14002643A
0x140026312  test    dword ptr [rbx+2Ch], 800h
0x140026319  jz      short loc_14002633E
0x14002631b  mov     rbx, [rbx+18h]
0x14002631f  call    cs:__imp_PsGetCurrentThreadId
0x140026326  nop     dword ptr [rax+rax+00h]
0x14002632b  mov     edx, 51h ; 'Q'
0x140026330  mov     r8, r12
0x140026333  mov     r9, rax
0x140026336  mov     rcx, rbx
0x140026339  call    WPP_SF_q
0x14002633e  mov     rbx, cs:WPP_GLOBAL_Control
0x140026345  cmp     rbx, r13
0x140026348  jz      loc_14002643A
0x14002634e  test    dword ptr [rbx+2Ch], 200h
0x140026355  jz      short loc_14002637F
0x140026357  mov     rbx, [rbx+18h]
0x14002635b  call    cs:__imp_PsGetCurrentThreadId
0x140026362  nop     dword ptr [rax+rax+00h]
0x140026367  mov     edx, 52h ; 'R'
0x14002636c  mov     [rsp+78h+EntryArray], rsi
0x140026371  mov     r9, rax
0x140026374  mov     r8, r12
0x140026377  mov     rcx, rbx
0x14002637a  call    WPP_SF_qq
0x14002637f  mov     rbx, cs:WPP_GLOBAL_Control
0x140026386  cmp     rbx, r13
0x140026389  jz      loc_14002643A
0x14002638f  test    dword ptr [rbx+2Ch], 200h
0x140026396  jz      short loc_1400263C0
0x140026398  mov     rbx, [rbx+18h]
0x14002639c  call    cs:__imp_PsGetCurrentThreadId
0x1400263a3  nop     dword ptr [rax+rax+00h]
0x1400263a8  mov     edx, 53h ; 'S'
0x1400263ad  mov     [rsp+78h+EntryArray], rdi
0x1400263b2  mov     r9, rax
0x1400263b5  mov     r8, r12
0x1400263b8  mov     rcx, rbx
0x1400263bb  call    WPP_SF_qq
0x1400263c0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400263c7  cmp     rbx, r13
0x1400263ca  jz      short loc_14002643A
0x1400263cc  test    dword ptr [rbx+2Ch], 200h
0x1400263d3  jz      short loc_1400263FD
0x1400263d5  mov     rbx, [rbx+18h]
0x1400263d9  call    cs:__imp_PsGetCurrentThreadId
0x1400263e0  nop     dword ptr [rax+rax+00h]
0x1400263e5  mov     edx, 54h ; 'T'
0x1400263ea  mov     [rsp+78h+EntryArray], rbp
0x1400263ef  mov     r9, rax
0x1400263f2  mov     r8, r12
0x1400263f5  mov     rcx, rbx
0x1400263f8  call    WPP_SF_qq
0x1400263fd  mov     rbx, cs:WPP_GLOBAL_Control
0x140026404  cmp     rbx, r13
0x140026407  jz      short loc_14002643A
0x140026409  test    dword ptr [rbx+2Ch], 200h
0x140026410  jz      short loc_14002643A
0x140026412  mov     rbx, [rbx+18h]
0x140026416  call    cs:__imp_PsGetCurrentThreadId
0x14002641d  nop     dword ptr [rax+rax+00h]
0x140026422  mov     edx, 55h ; 'U'
0x140026427  mov     [rsp+78h+EntryArray], r14
0x14002642c  mov     r9, rax
0x14002642f  mov     r8, r12
0x140026432  mov     rcx, rbx
0x140026435  call    WPP_SF_qq
0x14002643a  mov     rdi, [rsp+78h+arg_28]
0x140026442  mov     ecx, 30h ; '0'
0x140026447  mov     qword ptr [rdi+8], 0
0x14002644f  mov     dword ptr [rdi], 0C000010Dh
0x140026455  test    rbp, rbp
0x140026458  jnz     loc_1400264E4
0x14002645e  cmp     [rsi+650h], bpl
0x140026465  jnz     short loc_1400264A8
0x140026467  mov     rbx, cs:WPP_GLOBAL_Control
0x14002646e  cmp     rbx, r13
0x140026471  jz      loc_1400269BE
0x140026477  mov     eax, [rbx+2Ch]
0x14002647a  test    al, al
0x14002647c  jns     loc_1400269BE
0x140026482  mov     rbx, [rbx+18h]
0x140026486  call    cs:__imp_PsGetCurrentThreadId
0x14002648d  nop     dword ptr [rax+rax+00h]
0x140026492  lea     edx, [rbp+56h]
0x140026495  mov     r9, rax
0x140026498  mov     r8, r12
0x14002649b  mov     rcx, rbx
0x14002649e  call    WPP_SF_q
0x1400264a3  jmp     loc_1400269BE
0x1400264a8  test    r14, r14
0x1400264ab  jnz     short loc_1400264ED
0x1400264ad  mov     dword ptr [rdi], 0C000000Dh
0x1400264b3  mov     rbx, cs:WPP_GLOBAL_Control
0x1400264ba  cmp     rbx, r13
0x1400264bd  jz      loc_1400269BE
0x1400264c3  mov     eax, [rbx+2Ch]
0x1400264c6  test    al, al
0x1400264c8  jns     loc_1400269BE
0x1400264ce  mov     rbx, [rbx+18h]
0x1400264d2  call    cs:__imp_PsGetCurrentThreadId
0x1400264d9  nop     dword ptr [rax+rax+00h]
0x1400264de  lea     edx, [r14+57h]
0x1400264e2  jmp     short loc_140026495
0x1400264e4  test    r14, r14
0x1400264e7  jz      loc_14002659E
0x1400264ed  mov     eax, [rsi+654h]
0x1400264f3  mov     rdx, rcx
0x1400264f6  cmp     eax, ecx
0x1400264f8  jb      short loc_1400264FC
0x1400264fa  mov     edx, eax
0x1400264fc  mov     eax, [rsp+78h+arg_20]
0x140026503  cmp     rax, rdx
0x140026506  jnb     short loc_140026543
0x140026508  mov     dword ptr [rdi], 0C0000023h
0x14002650e  mov     rbx, cs:WPP_GLOBAL_Control
0x140026515  cmp     rbx, r13
0x140026518  jz      loc_1400269BE
0x14002651e  mov     eax, [rbx+2Ch]
0x140026521  test    al, al
0x140026523  jns     loc_1400269BE
0x140026529  mov     rbx, [rbx+18h]
0x14002652d  call    cs:__imp_PsGetCurrentThreadId
0x140026534  nop     dword ptr [rax+rax+00h]
0x140026539  mov     edx, 58h ; 'X'
0x14002653e  jmp     loc_140026495
0x140026543  test    rbp, rbp
0x140026546  jnz     short loc_14002659E
0x140026548  mov     eax, [r14+14h]
0x14002654c  test    al, 1
0x14002654e  jz      loc_1400266B3
0x140026554  mov     rbx, cs:WPP_GLOBAL_Control
0x14002655b  cmp     rbx, r13
0x14002655e  jz      short loc_140026588
0x140026560  bt      dword ptr [rbx+2Ch], 0Ah
0x140026565  jnb     short loc_140026588
0x140026567  mov     rbx, [rbx+18h]
0x14002656b  call    cs:__imp_PsGetCurrentThreadId
0x140026572  nop     dword ptr [rax+rax+00h]
0x140026577  lea     edx, [rbp+5Ch]
0x14002657a  mov     r8, r12
0x14002657d  mov     r9, rax
0x140026580  mov     rcx, rbx
0x140026583  call    WPP_SF_q
0x140026588  call    cs:__imp_PsRevertToSelf
0x14002658f  nop     dword ptr [rax+rax+00h]
0x140026594  and     dword ptr [r14+14h], 0FFFFFFFEh
0x140026599  jmp     loc_1400266B3
0x14002659e  mov     eax, [rsi+654h]
0x1400265a4  cmp     eax, ecx
0x1400265a6  jb      short loc_1400265AA
0x1400265a8  mov     ecx, eax
0x1400265aa  cmp     r15, rcx
0x1400265ad  jnb     short loc_1400265EA
0x1400265af  mov     dword ptr [rdi], 0C0000023h
0x1400265b5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400265bc  cmp     rbx, r13
0x1400265bf  jz      loc_1400269BE
0x1400265c5  mov     eax, [rbx+2Ch]
0x1400265c8  test    al, al
0x1400265ca  jns     loc_1400269BE
0x1400265d0  mov     rbx, [rbx+18h]
0x1400265d4  call    cs:__imp_PsGetCurrentThreadId
0x1400265db  nop     dword ptr [rax+rax+00h]
0x1400265e0  mov     edx, 59h ; 'Y'
0x1400265e5  jmp     loc_140026495
0x1400265ea  mov     eax, [rbp+14h]
0x1400265ed  test    al, 1
0x1400265ef  jz      short loc_140026637
0x1400265f1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400265f8  cmp     rbx, r13
0x1400265fb  jz      short loc_140026627
0x1400265fd  bt      dword ptr [rbx+2Ch], 0Ah
0x140026602  jnb     short loc_140026627
0x140026604  mov     rbx, [rbx+18h]
0x140026608  call    cs:__imp_PsGetCurrentThreadId
0x14002660f  nop     dword ptr [rax+rax+00h]
0x140026614  mov     edx, 5Ah ; 'Z'
0x140026619  mov     r8, r12
0x14002661c  mov     r9, rax
0x14002661f  mov     rcx, rbx
0x140026622  call    WPP_SF_q
0x140026627  call    cs:__imp_PsRevertToSelf
0x14002662e  nop     dword ptr [rax+rax+00h]
0x140026633  and     dword ptr [rbp+14h], 0FFFFFFFEh
0x140026637  call    cs:__imp_KeEnterCriticalRegion
0x14002663e  nop     dword ptr [rax+rax+00h]
0x140026643  mov     r9, rdi
0x140026646  mov     r8d, r15d
0x140026649  mov     rdx, rbp
0x14002664c  mov     rcx, rsi
0x14002664f  call    UMRxCompleteUserModeRequest
0x140026654  mov     ebp, eax
0x140026656  test    eax, eax
0x140026658  jz      short loc_1400266A7
0x14002665a  mov     [rdi], eax
0x14002665c  mov     rbx, cs:WPP_GLOBAL_Control
0x140026663  cmp     rbx, r13
0x140026666  jz      short loc_140026696
0x140026668  mov     ecx, [rbx+2Ch]
0x14002666b  test    cl, cl
0x14002666d  jns     short loc_140026696
0x14002666f  mov     rbx, [rbx+18h]
0x140026673  call    cs:__imp_PsGetCurrentThreadId
0x14002667a  nop     dword ptr [rax+rax+00h]
0x14002667f  mov     edx, 5Bh ; '['
0x140026684  mov     dword ptr [rsp+78h+EntryArray], ebp
0x140026688  mov     r9, rax
0x14002668b  mov     r8, r12
0x14002668e  mov     rcx, rbx
0x140026691  call    WPP_SF_qD
0x140026696  call    cs:__imp_KeLeaveCriticalRegion
0x14002669d  nop     dword ptr [rax+rax+00h]
0x1400266a2  jmp     loc_1400269BE
0x1400266a7  call    cs:__imp_KeLeaveCriticalRegion
0x1400266ae  nop     dword ptr [rax+rax+00h]
0x1400266b3  test    r14, r14
0x1400266b6  jnz     short loc_1400266C0
0x1400266b8  mov     [rdi], r14d
0x1400266bb  jmp     loc_1400269BE
0x1400266c0  lock inc dword ptr [rsi+648h]
0x1400266c7  mov     ebp, 1
0x1400266cc  lea     r12, [rsi+570h]
0x1400266d3  mov     r8b, 1; Alertable
0x1400266d6  mov     [rsp+78h+Count], 1; Count
0x1400266de  lea     rax, [rsp+78h+Entry]
0x1400266e6  mov     dl, r8b; WaitMode
0x1400266e9  xor     r9d, r9d; Timeout
0x1400266ec  mov     [rsp+78h+EntryArray], rax; EntryArray
0x1400266f1  mov     rcx, r12; Queue
0x1400266f4  call    cs:__imp_KeRemoveQueueEx
0x1400266fb  nop     dword ptr [rax+rax+00h]
0x140026700  mov     rdx, [rsp+78h+Entry]
0x140026708  cmp     rdx, 102h
0x14002670f  jnz     short loc_140026773
0x140026711  mov     eax, 0CCCCCCCDh
0x140026716  mul     ebp
0x140026718  shr     edx, 2
0x14002671b  lea     ecx, [rdx+rdx*4]
0x14002671e  cmp     ebp, ecx
0x140026720  jnz     loc_140026862
0x140026726  mov     rbx, cs:WPP_GLOBAL_Control
0x14002672d  cmp     rbx, r13
0x140026730  jz      loc_140026862
0x140026736  test    dword ptr [rbx+2Ch], 400h
0x14002673d  jz      loc_140026862
0x140026743  mov     rbx, [rbx+18h]
0x140026747  call    cs:__imp_PsGetCurrentThreadId
0x14002674e  nop     dword ptr [rax+rax+00h]
0x140026753  mov     edx, 5Dh ; ']'
0x140026758  mov     dword ptr [rsp+78h+EntryArray], ebp
0x14002675c  mov     r9, rax
0x14002675f  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140026766  mov     rcx, rbx
0x140026769  call    WPP_SF_qD
0x14002676e  jmp     loc_140026862
0x140026773  cmp     rdx, 0C0h
0x14002677a  jz      loc_1400268CF
0x140026780  cmp     rdx, 101h
0x140026787  jnz     short loc_1400267B1
0x140026789  mov     rcx, gs:188h; Thread
0x140026792  call    cs:__imp_PsIsThreadTerminating
0x140026799  nop     dword ptr [rax+rax+00h]
0x14002679e  test    al, al
0x1400267a0  jz      loc_140026862
0x1400267a6  mov     dword ptr [rdi], 0C0000120h
0x1400267ac  jmp     loc_14002690F
0x1400267b1  lea     rax, [rsi+620h]
0x1400267b8  cmp     rdx, rax
0x1400267bb  jz      loc_14002687A
0x1400267c1  call    cs:__imp_KeEnterCriticalRegion
0x1400267c8  nop     dword ptr [rax+rax+00h]
0x1400267cd  lock dec dword ptr [rsi+64Ch]
0x1400267d4  mov     r8, r14
0x1400267d7  mov     rcx, [rsp+78h+Entry]
0x1400267df  mov     rdx, rsi
0x1400267e2  mov     r9d, [rsp+78h+arg_20]
0x1400267ea  add     rcx, 0FFFFFFFFFFFFFE98h; Context
0x1400267f1  mov     [rsp+78h+EntryArray], rdi; __int64
0x1400267f6  call    UMRxPrepareUserModeRequestBuffer
  ... truncated ...
```
