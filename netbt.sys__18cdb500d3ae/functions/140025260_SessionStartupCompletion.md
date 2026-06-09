# SessionStartupCompletion

- ea: `0x140025260`
- end: `0x1400253d2`
- name: `SessionStartupCompletion`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140007ff8`
- `0x140008110`
- `0x1400089c8`
- `0x14000b810`
- `0x140010988`
- `0x14001f6dc`
- `0x140025260`
- `0x140030f80`
- `0x14004102c`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025285`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025285`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025346`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400253b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025346`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400253b2`

## pseudocode

```c
void __fastcall SessionStartupCompletion(__int64 a1, int a2)
{
  _QWORD *v2; // r14
  __int64 v5; // rcx
  KIRQL v6; // bp
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rsi
  int v10; // edx
  void *v11; // rcx

  v2 = *(_QWORD **)(a1 + 96);
  v6 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( (BYTE2(xmmword_140038420) & 8) != 0 )
    WPP_SF_qdqq(v5, 59, v7, a1, a2, v2, v2[3]);
  v8 = *(_DWORD *)(a1 + 136);
  if ( v8 )
  {
    *(_DWORD *)(a1 + 136) = v8 - 1;
    if ( a2 < 0 )
    {
      v11 = *(void **)(a1 + 152);
      if ( v11 )
      {
        *(_QWORD *)(a1 + 152) = 0;
        StopTimer(v11);
      }
    }
  }
  else
  {
    v9 = *(_QWORD *)(a1 + 48);
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *(_DWORD *)(v9 + 20),
        81,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        v9,
        *(_DWORD *)(v9 + 20),
        *(_DWORD *)(v9 + 20) - 1,
        49,
        (__int64)"minio\\netbt\\sys\\name.c");
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 20), 0xFFFFFFFF) == 1 )
    {
      NbtUnlinkNameFromHashTable((__int64 *)v9);
      NbtFreeNameAddr((PVOID)v9);
    }
    else
    {
      NbtCheckNameAddrTimer(v9);
    }
    FreeTracker(a1, 5);
  }
  KeReleaseSpinLock(&SpinLock, v6);
  NbtDereferenceConnection(v2, v10, 99, (__int64)"minio\\netbt\\sys\\name.c");
}

```

## disassembly

```asm
0x140025260  mov     rax, rsp
0x140025263  push    rbx
0x140025264  push    rbp
0x140025265  push    rsi
0x140025266  push    rdi
0x140025267  push    r12
0x140025269  push    r14
0x14002526b  sub     rsp, 48h
0x14002526f  mov     r14, [rcx+60h]
0x140025273  mov     rbx, rcx
0x140025276  xor     edi, edi
0x140025278  lea     rcx, SpinLock; SpinLock
0x14002527f  mov     [rax+8], rdi
0x140025283  mov     esi, edx
0x140025285  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002528c  nop     dword ptr [rax+rax+00h]
0x140025291  mov     bpl, al
0x140025294  test    byte ptr cs:xmmword_140038420+2, 8
0x14002529b  jz      short loc_1400252BA
0x14002529d  mov     rax, [r14+18h]
0x1400252a1  lea     edx, [rdi+3Bh]
0x1400252a4  mov     [rsp+78h+var_48], rax
0x1400252a9  mov     r9, rbx
0x1400252ac  mov     [rsp+78h+var_50], r14
0x1400252b1  mov     [rsp+78h+var_58], esi
0x1400252b5  call    WPP_SF_qdqq
0x1400252ba  mov     eax, [rbx+88h]
0x1400252c0  lea     r12, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x1400252c7  test    eax, eax
0x1400252c9  jnz     loc_140025371
0x1400252cf  mov     rsi, [rbx+30h]
0x1400252d3  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400252da  jz      short loc_14002530B
0x1400252dc  mov     ecx, [rsi+14h]
0x1400252df  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x1400252e6  mov     [rsp+78h+var_40], r12
0x1400252eb  mov     edx, 51h ; 'Q'
0x1400252f0  mov     dword ptr [rsp+78h+var_48], 1731h
0x1400252f8  mov     r9, rsi
0x1400252fb  lea     eax, [rcx-1]
0x1400252fe  mov     dword ptr [rsp+78h+var_50], eax
0x140025302  mov     [rsp+78h+var_58], ecx
0x140025306  call    WPP_SF_qddds
0x14002530b  or      eax, 0FFFFFFFFh
0x14002530e  lock xadd [rsi+14h], eax
0x140025313  mov     rcx, rsi
0x140025316  cmp     eax, 1
0x140025319  jz      short loc_140025322
0x14002531b  call    NbtCheckNameAddrTimer
0x140025320  jmp     short loc_14002532F
0x140025322  call    NbtUnlinkNameFromHashTable
0x140025327  mov     rcx, rsi; P
0x14002532a  call    NbtFreeNameAddr
0x14002532f  mov     edx, 5
0x140025334  mov     rcx, rbx
0x140025337  call    FreeTracker
0x14002533c  mov     dl, bpl; NewIrql
0x14002533f  lea     rcx, SpinLock; SpinLock
0x140025346  call    cs:__imp_KeReleaseSpinLock
0x14002534d  nop     dword ptr [rax+rax+00h]
0x140025352  mov     r9, r12
0x140025355  mov     r8d, 1763h
0x14002535b  mov     rcx, r14; P
0x14002535e  call    NbtDereferenceConnection
0x140025363  add     rsp, 48h
0x140025367  pop     r14
0x140025369  pop     r12
0x14002536b  pop     rdi
0x14002536c  pop     rsi
0x14002536d  pop     rbp
0x14002536e  pop     rbx
0x14002536f  retn
0x140025371  dec     eax
0x140025373  mov     [rbx+88h], eax
0x140025379  test    esi, esi
0x14002537b  jns     short loc_14002533C
0x14002537d  mov     rcx, [rbx+98h]; Entry
0x140025384  test    rcx, rcx
0x140025387  jz      short loc_1400253A8
0x140025389  xor     r8d, r8d
0x14002538c  mov     [rbx+98h], rdi
0x140025393  lea     rdx, [rsp+78h+arg_0]
0x14002539b  call    StopTimer
0x1400253a0  mov     rdi, [rsp+78h+arg_0]
0x1400253a8  mov     dl, bpl; NewIrql
0x1400253ab  lea     rcx, SpinLock; SpinLock
0x1400253b2  call    cs:__imp_KeReleaseSpinLock
0x1400253b9  nop     dword ptr [rax+rax+00h]
0x1400253be  test    rdi, rdi
0x1400253c1  jz      short loc_140025352
0x1400253c3  mov     edx, esi
0x1400253c5  mov     rcx, rbx
0x1400253c8  mov     rax, rdi
0x1400253cb  call    _guard_dispatch_icall
0x1400253d0  jmp     short loc_140025352
```
