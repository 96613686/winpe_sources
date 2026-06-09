# MSnodeRegCompletion

- ea: `0x14000c570`
- end: `0x14000cbb3`
- name: `MSnodeRegCompletion`
- size: `1603`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140007ff8`
- `0x140008110`
- `0x1400089c8`
- `0x14000a7b0`
- `0x14000b7e8`
- `0x14000b810`
- `0x14000c570`
- `0x140019db4`
- `0x140025144`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c5c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c6b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c5c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c6b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c657`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c6ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c845`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c657`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c6ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c845`

## pseudocode

```c
void __fastcall MSnodeRegCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // di
  char v6; // r8
  KIRQL v7; // al
  __int16 v8; // cx
  KIRQL v9; // r12
  _WORD *v10; // rdx
  unsigned int v11; // r15d
  volatile signed __int32 *v12; // rdi
  KIRQL v13; // si
  KIRQL v14; // dl
  volatile signed __int32 *v15; // r14
  int v16; // r8d
  _WORD *v17; // r9
  volatile signed __int32 *v18; // r15
  __int64 v19; // rax
  bool v20; // zf
  volatile signed __int32 *v21; // r14
  _DWORD *v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  int v25; // [rsp+B0h] [rbp+8h] BYREF

  v3 = NodeType;
  v25 = 0;
  if ( (NodeType & 1) != 0 && (unsigned int)IsBrowserName(*(_QWORD *)(a1 + 48) + 164LL) )
    v3 = v6;
  if ( !a3 )
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 48) + 112LL) = 0;
    v15 = *(volatile signed __int32 **)(a1 + 48);
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *((_DWORD *)v15 + 5),
        81,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        (_DWORD)v15,
        *((_DWORD *)v15 + 5),
        *((_DWORD *)v15 + 5) - 1,
        100,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( _InterlockedExchangeAdd(v15 + 5, 0xFFFFFFFF) == 1 )
    {
      NbtUnlinkNameFromHashTable(v15);
      NbtFreeNameAddr((PVOID)v15);
    }
    else
    {
      NbtCheckNameAddrTimer(v15);
    }
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *(_DWORD *)(a1 + 20),
        84,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        a1,
        *(_DWORD *)(a1 + 20),
        *(_DWORD *)(a1 + 20) - 1,
        101,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( !_InterlockedDecrement((volatile signed __int32 *)(a1 + 20)) )
      FreeTracker(a1, 4);
    return;
  }
  v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v8 = *(_WORD *)(a3 + 256);
  v9 = v7;
  if ( (v8 & 0x10) != 0 )
  {
    *(_WORD *)(a3 + 256) = v8 & 0xFFEE | 1;
    v22 = *(_DWORD **)(a1 + 32);
    if ( !v22[122]
      || (v23 = *(_DWORD *)(a1 + 240), (v23 & 2) != 0) && v22[126] == 2130706432
      || (v23 & 4) != 0 && v22[127] == 2130706432 )
    {
      *(_DWORD *)(a3 + 24) = 10;
    }
    goto LABEL_60;
  }
  if ( !*(_QWORD *)(a3 + 72) )
  {
    v21 = *(volatile signed __int32 **)(a1 + 48);
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *((_DWORD *)v21 + 5),
        81,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        (_DWORD)v21,
        *((_DWORD *)v21 + 5),
        *((_DWORD *)v21 + 5) - 1,
        138,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( _InterlockedExchangeAdd(v21 + 5, 0xFFFFFFFF) == 1 )
    {
      NbtUnlinkNameFromHashTable(v21);
      NbtFreeNameAddr((PVOID)v21);
    }
    else
    {
      NbtCheckNameAddrTimer(v21);
    }
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *(_DWORD *)(a1 + 20),
        84,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        a1,
        *(_DWORD *)(a1 + 20),
        *(_DWORD *)(a1 + 20) - 1,
        139,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
      FreeTracker(a1, 4);
    goto LABEL_60;
  }
  v10 = (_WORD *)(a3 + 20);
  v20 = (*(_WORD *)(a3 + 20))-- == 1;
  v11 = 4;
  if ( !v20 )
  {
    if ( *(_WORD *)(a3 + 20) != 1 )
    {
LABEL_11:
      v12 = (volatile signed __int32 *)(a1 + 20);
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *v12,
          15,
          (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
          a1,
          *v12,
          *v12 + 1,
          4,
          (__int64)"minio\\netbt\\sys\\namesrv.c");
      _InterlockedAdd(v12, 1u);
      *(_WORD *)(a3 + 256) |= 1u;
      KeReleaseSpinLock(&SpinLock, v9);
      SendNameServiceRequest(*(_QWORD *)(a1 + 48), Str2, a1, 0, 0, 0, 0, 0, v11, 1, &v25);
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *v12,
          84,
          (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
          a1,
          *v12,
          *v12 - 1,
          18,
          (__int64)"minio\\netbt\\sys\\namesrv.c");
      v13 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
        FreeTracker(a1, 4);
      v14 = v13;
      goto LABEL_18;
    }
    if ( (*(_DWORD *)(a1 + 240) & 1) != 0 )
    {
      v11 = 5;
      goto LABEL_11;
    }
    if ( (v3 & 0xA) == 0 )
      goto LABEL_11;
    *(_DWORD *)(a3 + 24) = 5;
    *(_WORD *)(a3 + 256) = v8 | 1;
LABEL_60:
    v14 = v9;
LABEL_18:
    KeReleaseSpinLock(&SpinLock, v14);
    return;
  }
  v16 = *(_DWORD *)(a1 + 240);
  *(_DWORD *)(a1 + 240) = v16 & 0xFFFFFFFC;
  *(_DWORD *)(a3 + 24) = dword_1400395C0;
  *v10 = word_1400395D8 + 1;
  if ( (v16 & 1) != 0 )
  {
    if ( (v3 & 4) != 0 )
    {
      ++dword_140039384;
      v19 = *(_QWORD *)(a1 + 32);
      *(_DWORD *)(a1 + 240) |= 2u;
      v20 = *(_DWORD *)(v19 + 504) == 2130706432;
      goto LABEL_49;
    }
    v17 = (_WORD *)(a3 + 20);
  }
  else
  {
    v17 = (_WORD *)(a3 + 20);
  }
  if ( (v16 & 2) != 0 && (v3 & 1) == 0 )
  {
    v19 = *(_QWORD *)(a1 + 32);
    *(_DWORD *)(a1 + 240) |= 4u;
    v20 = *(_DWORD *)(v19 + 508) == 2130706432;
LABEL_49:
    if ( v20 || *(_BYTE *)(v19 + 858) )
    {
      *(_DWORD *)(a3 + 24) = 10;
      *v10 = 1;
    }
    goto LABEL_11;
  }
  if ( (v3 & 8) != 0 && (v16 & 1) == 0 )
  {
    if ( (v16 & 4) != 0 )
    {
      *(_DWORD *)(a1 + 240) |= 1u;
      ++dword_140039384;
      *(_DWORD *)(a3 + 24) = dword_1400395BC;
      *v17 = word_1400395DA + 1;
    }
    goto LABEL_11;
  }
  if ( (v3 & 1) != 0 )
    ++dword_140039384;
  if ( (v16 & 1) == 0 )
  {
    v24 = *(_QWORD *)(a1 + 32);
    if ( *(_DWORD *)(v24 + 504) != 2130706432 )
      SetWinsDownFlag(v24);
  }
  v18 = *(volatile signed __int32 **)(a1 + 48);
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *((_DWORD *)v18 + 5),
      81,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      (_DWORD)v18,
      *((_DWORD *)v18 + 5),
      *((_DWORD *)v18 + 5) - 1,
      250,
      (__int64)"minio\\netbt\\sys\\namesrv.c");
  if ( _InterlockedExchangeAdd(v18 + 5, 0xFFFFFFFF) == 1 )
  {
    NbtUnlinkNameFromHashTable(v18);
    NbtFreeNameAddr((PVOID)v18);
  }
  else
  {
    NbtCheckNameAddrTimer(v18);
  }
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *(_DWORD *)(a1 + 20),
      84,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      a1,
      *(_DWORD *)(a1 + 20),
      *(_DWORD *)(a1 + 20) - 1,
      251,
      (__int64)"minio\\netbt\\sys\\namesrv.c");
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
    FreeTracker(a1, 4);
  KeReleaseSpinLock(&SpinLock, v9);
  InterlockedCallCompletion(a3, 0);
}

```

## disassembly

```asm
0x14000c570  mov     rax, rsp
0x14000c573  push    rbx
0x14000c574  push    rbp
0x14000c575  push    rsi
0x14000c576  push    rdi
0x14000c577  push    r12
0x14000c579  push    r13
0x14000c57b  push    r14
0x14000c57d  push    r15
0x14000c57f  sub     rsp, 68h
0x14000c583  movzx   edi, cs:NodeType
0x14000c58a  xor     ebp, ebp
0x14000c58c  mov     rsi, r8
0x14000c58f  mov     [rax+8], ebp
0x14000c592  mov     r8d, edi
0x14000c595  mov     rbx, rcx
0x14000c598  lea     r13d, [rbp+1]
0x14000c59c  and     r8d, r13d
0x14000c59f  jz      short loc_14000C5B7
0x14000c5a1  mov     rcx, [rcx+30h]
0x14000c5a5  add     rcx, 0A4h
0x14000c5ac  call    IsBrowserName
0x14000c5b1  test    eax, eax
0x14000c5b3  cmovnz  edi, r8d
0x14000c5b7  test    rsi, rsi
0x14000c5ba  jz      loc_14000C708
0x14000c5c0  lea     rcx, SpinLock; SpinLock
0x14000c5c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c5ce  nop     dword ptr [rax+rax+00h]
0x14000c5d3  movzx   ecx, word ptr [rsi+100h]
0x14000c5da  mov     r12b, al
0x14000c5dd  test    cl, 10h
0x14000c5e0  jnz     loc_14000CAA3
0x14000c5e6  cmp     [rsi+48h], rbp
0x14000c5ea  jz      loc_14000C8F9
0x14000c5f0  lea     rdx, [rsi+14h]
0x14000c5f4  mov     eax, 0FFFFh
0x14000c5f9  add     [rdx], ax
0x14000c5fc  mov     r15d, 4
0x14000c602  movzx   eax, word ptr [rdx]
0x14000c605  jz      loc_14000C770
0x14000c60b  cmp     ax, r13w
0x14000c60f  jnz     short loc_14000C626
0x14000c611  mov     eax, [rbx+0F0h]
0x14000c617  test    r13b, al
0x14000c61a  jz      loc_14000C86A
0x14000c620  mov     r15d, 5
0x14000c626  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c62d  lea     rdi, [rbx+14h]
0x14000c631  lea     rbp, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x14000c638  jnz     loc_14000C892
0x14000c63e  mov     r14, rdi
0x14000c641  lock add [r14], r13d
0x14000c645  or      [rsi+100h], r13w
0x14000c64d  lea     rcx, SpinLock; SpinLock
0x14000c654  mov     dl, r12b; NewIrql
0x14000c657  call    cs:__imp_KeReleaseSpinLock
0x14000c65e  nop     dword ptr [rax+rax+00h]
0x14000c663  mov     rdx, cs:Str2
0x14000c66a  lea     rax, [rsp+0A8h+arg_0]
0x14000c672  mov     rcx, [rbx+30h]
0x14000c676  xor     r9d, r9d
0x14000c679  mov     [rsp+0A8h+var_58], rax
0x14000c67e  mov     r8, rbx
0x14000c681  mov     [rsp+0A8h+var_60], r13d
0x14000c686  xor     eax, eax
0x14000c688  mov     [rsp+0A8h+var_68], r15d
0x14000c68d  mov     dword ptr [rsp+0A8h+var_70], eax
0x14000c691  mov     [rsp+0A8h+var_78], eax
0x14000c695  mov     [rsp+0A8h+var_80], rax
0x14000c69a  mov     [rsp+0A8h+var_88], rax
0x14000c69f  call    SendNameServiceRequest
0x14000c6a4  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c6ab  jnz     loc_14000CA07
0x14000c6b1  lea     rcx, SpinLock; SpinLock
0x14000c6b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c6bf  nop     dword ptr [rax+rax+00h]
0x14000c6c4  or      edi, 0FFFFFFFFh
0x14000c6c7  mov     sil, al
0x14000c6ca  mov     ecx, edi
0x14000c6cc  lock xadd [r14], ecx
0x14000c6d1  add     ecx, edi
0x14000c6d3  jnz     short loc_14000C6E0
0x14000c6d5  lea     edx, [rdi+5]
0x14000c6d8  mov     rcx, rbx
0x14000c6db  call    FreeTracker
0x14000c6e0  mov     dl, sil; NewIrql
0x14000c6e3  lea     rcx, SpinLock; SpinLock
0x14000c6ea  call    cs:__imp_KeReleaseSpinLock
0x14000c6f1  nop     dword ptr [rax+rax+00h]
0x14000c6f6  add     rsp, 68h
0x14000c6fa  pop     r15
0x14000c6fc  pop     r14
0x14000c6fe  pop     r13
0x14000c700  pop     r12
0x14000c702  pop     rdi
0x14000c703  pop     rsi
0x14000c704  pop     rbp
0x14000c705  pop     rbx
0x14000c706  retn
0x14000c708  mov     rax, [rbx+30h]
0x14000c70c  mov     [rax+70h], rbp
0x14000c710  mov     r14, [rbx+30h]
0x14000c714  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c71b  lea     rbp, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x14000c722  jnz     loc_14000CA6E
0x14000c728  or      edi, 0FFFFFFFFh
0x14000c72b  mov     eax, edi
0x14000c72d  lock xadd [r14+14h], eax
0x14000c733  mov     rcx, r14
0x14000c736  add     eax, edi
0x14000c738  jnz     loc_14000C860
0x14000c73e  call    NbtUnlinkNameFromHashTable
0x14000c743  mov     rcx, r14; P
0x14000c746  call    NbtFreeNameAddr
0x14000c74b  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c752  jnz     loc_14000C99F
0x14000c758  mov     eax, edi
0x14000c75a  lock xadd [rbx+14h], eax
0x14000c75f  add     eax, edi
0x14000c761  jnz     short loc_14000C6F6
0x14000c763  lea     edx, [rax+4]
0x14000c766  mov     rcx, rbx
0x14000c769  call    FreeTracker
0x14000c76e  jmp     short loc_14000C6F6
0x14000c770  mov     r8d, [rbx+0F0h]
0x14000c777  mov     eax, r8d
0x14000c77a  and     eax, 0FFFFFFFCh
0x14000c77d  mov     r10d, r8d
0x14000c780  mov     [rbx+0F0h], eax
0x14000c786  mov     eax, cs:dword_1400395C0
0x14000c78c  mov     [rsi+18h], eax
0x14000c78f  movzx   eax, cs:word_1400395D8
0x14000c796  add     ax, r13w
0x14000c79a  mov     [rdx], ax
0x14000c79d  and     r10d, r13d
0x14000c7a0  jnz     loc_14000CB31
0x14000c7a6  mov     r9, rdx
0x14000c7a9  test    r8b, 2
0x14000c7ad  setnz   cl
0x14000c7b0  test    r13b, dil
0x14000c7b3  setz    al
0x14000c7b6  test    al, cl
0x14000c7b8  jnz     loc_14000C8C5
0x14000c7be  test    dil, 8
0x14000c7c2  jnz     loc_14000C95B
0x14000c7c8  test    r13b, dil
0x14000c7cb  jz      short loc_14000C7D4
0x14000c7cd  add     cs:dword_140039384, r13d
0x14000c7d4  test    r13b, r8b
0x14000c7d7  jz      loc_14000CB60
0x14000c7dd  mov     r15, [rbx+30h]
0x14000c7e1  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c7e8  lea     rbp, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x14000c7ef  jnz     loc_14000CB7E
0x14000c7f5  or      edi, 0FFFFFFFFh
0x14000c7f8  mov     eax, edi
0x14000c7fa  lock xadd [r15+14h], eax
0x14000c800  mov     rcx, r15
0x14000c803  add     eax, edi
0x14000c805  jnz     loc_14000C88B
0x14000c80b  call    NbtUnlinkNameFromHashTable
0x14000c810  mov     rcx, r15; P
0x14000c813  call    NbtFreeNameAddr
0x14000c818  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c81f  jnz     loc_14000CA3A
0x14000c825  mov     eax, edi
0x14000c827  lock xadd [rbx+14h], eax
0x14000c82c  add     eax, edi
0x14000c82e  jnz     short loc_14000C83B
0x14000c830  lea     edx, [rax+4]
0x14000c833  mov     rcx, rbx
0x14000c836  call    FreeTracker
0x14000c83b  mov     dl, r12b; NewIrql
0x14000c83e  lea     rcx, SpinLock; SpinLock
0x14000c845  call    cs:__imp_KeReleaseSpinLock
0x14000c84c  nop     dword ptr [rax+rax+00h]
0x14000c851  xor     edx, edx
0x14000c853  mov     rcx, rsi
0x14000c856  call    InterlockedCallCompletion
0x14000c85b  jmp     loc_14000C6F6
0x14000c860  call    NbtCheckNameAddrTimer
0x14000c865  jmp     loc_14000C74B
0x14000c86a  test    dil, 0Ah
0x14000c86e  jz      loc_14000C626
0x14000c874  or      cx, r13w
0x14000c878  mov     dword ptr [rsi+18h], 5
0x14000c87f  mov     [rsi+100h], cx
0x14000c886  jmp     loc_14000C953
0x14000c88b  call    NbtCheckNameAddrTimer
0x14000c890  jmp     short loc_14000C818
0x14000c892  mov     ecx, [rdi]
0x14000c894  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x14000c89b  mov     [rsp+0A8h+var_70], rbp
0x14000c8a0  mov     edx, 0Fh
0x14000c8a5  mov     [rsp+0A8h+var_78], 704h
0x14000c8ad  mov     r9, rbx
0x14000c8b0  lea     eax, [rcx+1]
0x14000c8b3  mov     dword ptr [rsp+0A8h+var_80], eax
0x14000c8b7  mov     dword ptr [rsp+0A8h+var_88], ecx
0x14000c8bb  call    WPP_SF_qddds
0x14000c8c0  jmp     loc_14000C63E
0x14000c8c5  mov     rax, [rbx+20h]
0x14000c8c9  or      [rbx+0F0h], r15d
0x14000c8d0  cmp     dword ptr [rax+1FCh], 7F000000h
0x14000c8da  jz      short loc_14000C8E9
0x14000c8dc  cmp     [rax+35Ah], bpl
0x14000c8e3  jz      loc_14000C626
0x14000c8e9  mov     dword ptr [rsi+18h], 0Ah
0x14000c8f0  mov     [rdx], r13w
0x14000c8f4  jmp     loc_14000C626
0x14000c8f9  mov     r14, [rbx+30h]
0x14000c8fd  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c904  lea     rbp, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x14000c90b  jnz     loc_14000CAFC
0x14000c911  or      edi, 0FFFFFFFFh
0x14000c914  mov     eax, edi
0x14000c916  lock xadd [r14+14h], eax
0x14000c91c  mov     rcx, r14
0x14000c91f  add     eax, edi
0x14000c921  jnz     short loc_14000C998
0x14000c923  call    NbtUnlinkNameFromHashTable
0x14000c928  mov     rcx, r14; P
0x14000c92b  call    NbtFreeNameAddr
0x14000c930  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000c937  jnz     loc_14000C9D3
0x14000c93d  mov     eax, edi
0x14000c93f  lock xadd [rbx+14h], eax
0x14000c944  add     eax, edi
0x14000c946  jnz     short loc_14000C953
0x14000c948  lea     edx, [rax+4]
0x14000c94b  mov     rcx, rbx
0x14000c94e  call    FreeTracker
0x14000c953  mov     dl, r12b
0x14000c956  jmp     loc_14000C6E3
0x14000c95b  test    r10d, r10d
0x14000c95e  jnz     loc_14000C7C8
0x14000c964  test    r15b, r8b
0x14000c967  jz      loc_14000C626
0x14000c96d  or      [rbx+0F0h], r13d
0x14000c974  add     cs:dword_140039384, r13d
0x14000c97b  mov     eax, cs:dword_1400395BC
0x14000c981  mov     [rsi+18h], eax
0x14000c984  movzx   eax, cs:word_1400395DA
0x14000c98b  add     ax, r13w
0x14000c98f  mov     [r9], ax
0x14000c993  jmp     loc_14000C626
0x14000c998  call    NbtCheckNameAddrTimer
0x14000c99d  jmp     short loc_14000C930
0x14000c99f  mov     ecx, [rbx+14h]
0x14000c9a2  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14000c9a9  mov     [rsp+0A8h+var_70], rbp
0x14000c9ae  mov     edx, 54h ; 'T'
0x14000c9b3  mov     [rsp+0A8h+var_78], 665h
0x14000c9bb  mov     r9, rbx
0x14000c9be  lea     eax, [rcx-1]
0x14000c9c1  mov     dword ptr [rsp+0A8h+var_80], eax
0x14000c9c5  mov     dword ptr [rsp+0A8h+var_88], ecx
0x14000c9c9  call    WPP_SF_qddds
0x14000c9ce  jmp     loc_14000C758
0x14000c9d3  mov     ecx, [rbx+14h]
0x14000c9d6  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14000c9dd  mov     [rsp+0A8h+var_70], rbp
0x14000c9e2  mov     edx, 54h ; 'T'
0x14000c9e7  mov     [rsp+0A8h+var_78], 68Bh
0x14000c9ef  mov     r9, rbx
0x14000c9f2  lea     eax, [rcx-1]
0x14000c9f5  mov     dword ptr [rsp+0A8h+var_80], eax
0x14000c9f9  mov     dword ptr [rsp+0A8h+var_88], ecx
0x14000c9fd  call    WPP_SF_qddds
0x14000ca02  jmp     loc_14000C93D
0x14000ca07  mov     ecx, [rdi]
0x14000ca09  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14000ca10  mov     [rsp+0A8h+var_70], rbp
0x14000ca15  mov     edx, 54h ; 'T'
0x14000ca1a  mov     [rsp+0A8h+var_78], 712h
0x14000ca22  mov     r9, rbx
0x14000ca25  lea     eax, [rcx-1]
0x14000ca28  mov     dword ptr [rsp+0A8h+var_80], eax
0x14000ca2c  mov     dword ptr [rsp+0A8h+var_88], ecx
0x14000ca30  call    WPP_SF_qddds
0x14000ca35  jmp     loc_14000C6B1
0x14000ca3a  mov     ecx, [rbx+14h]
0x14000ca3d  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14000ca44  mov     [rsp+0A8h+var_70], rbp
0x14000ca49  mov     edx, 54h ; 'T'
0x14000ca4e  mov     [rsp+0A8h+var_78], 6FBh
0x14000ca56  mov     r9, rbx
0x14000ca59  lea     eax, [rcx-1]
0x14000ca5c  mov     dword ptr [rsp+0A8h+var_80], eax
0x14000ca60  mov     dword ptr [rsp+0A8h+var_88], ecx
0x14000ca64  call    WPP_SF_qddds
0x14000ca69  jmp     loc_14000C825
0x14000ca6e  mov     ecx, [r14+14h]
0x14000ca72  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14000ca79  mov     [rsp+0A8h+var_70], rbp
0x14000ca7e  mov     edx, 51h ; 'Q'
0x14000ca83  mov     [rsp+0A8h+var_78], 664h
0x14000ca8b  mov     r9, r14
0x14000ca8e  lea     eax, [rcx-1]
  ... truncated ...
```
