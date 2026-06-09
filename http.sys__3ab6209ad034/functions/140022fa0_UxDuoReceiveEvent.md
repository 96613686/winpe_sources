# UxDuoReceiveEvent

- ea: `0x140022fa0`
- end: `0x1400234a5`
- name: `UxDuoReceiveEvent`
- size: `1285`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140022fa0`
- `0x140049d08`
- `0x1400513f0`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x1400b3a14`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3d94`
- `0x1401da550`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002302f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400230ba`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002302f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400230ba`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140023373`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400233a7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140023373`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400233a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400231ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400231ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002318d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002318d`

## pseudocode

```c
__int64 __fastcall UxDuoReceiveEvent(__int64 a1, int a2, _QWORD *a3, unsigned int a4, unsigned int *a5)
{
  unsigned int LockArray_high; // ebp
  unsigned __int64 v9; // rbx
  unsigned int *v10; // rax
  volatile signed __int32 *v11; // rdi
  int v12; // ebp
  unsigned __int64 v13; // rbx
  char *v14; // rax
  char *v15; // rbx
  int v16; // eax
  unsigned int v17; // ebp
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 v20; // rdi
  KIRQL v21; // al
  char v22; // si
  _QWORD *v23; // rdx
  _QWORD *v24; // rbx
  __int64 v25; // r9
  ULONG_PTR v26; // rdx
  unsigned int v27; // ebx
  int v29; // eax
  bool v30; // zf
  __int64 v31; // rbx
  USHORT CurrentNodeNumber; // ax
  __int64 v33; // rbx
  USHORT v34; // ax
  __int64 v35; // [rsp+28h] [rbp-C0h]
  _DWORD v36[24]; // [rsp+40h] [rbp-A8h] BYREF

  *a5 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqPq(1041, 57, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, a1, a2, a3, a4, a5);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  if ( UxDebugDisableLookaside )
  {
    v10 = (unsigned int *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A07E0)(
                            (unsigned int)dword_1401A07C8,
                            qword_1401A07D0,
                            (unsigned int)dword_1401A07D8,
                            0);
  }
  else if ( UxCompactMode )
  {
    v31 = qword_1401A07C0;
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    v10 = (unsigned int *)PplAllocateFromLookasideListProcessor(v31, CurrentNodeNumber);
  }
  else
  {
    v9 = qword_1401A07C0 + ((unsigned __int64)(LockArray_high + 1) << 7);
    if ( !*(_BYTE *)(v9 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A07C0, v9 + 64);
    v10 = (unsigned int *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v9 + 64));
  }
  v11 = (volatile signed __int32 *)v10;
  if ( !v10 )
    goto LABEL_40;
  *(_QWORD *)(v10 + 1) = 0;
  v10[3] = 0;
  *((_QWORD *)v10 + 3) = 0;
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 5) = 0;
  *v10 = LockArray_high;
  v10[4] = 1482258517;
  v10[5] = 1;
  v12 = HIDWORD(KeGetPcr()[1].LockArray);
  if ( UxDebugDisableLookaside )
  {
    v14 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A07B0)(
                    (unsigned int)dword_1401A0798,
                    qword_1401A07A0,
                    (unsigned int)dword_1401A07A8,
                    0);
  }
  else if ( UxCompactMode )
  {
    v33 = qword_1401A0790;
    v34 = KeGetCurrentNodeNumber();
    v14 = (char *)PplAllocateFromLookasideListProcessor(v33, v34);
  }
  else
  {
    v13 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(v12 + 1) << 7);
    if ( !*(_BYTE *)(v13 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A0790, v13 + 64);
    v14 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 64));
  }
  v15 = v14;
  if ( !v14 )
  {
    v29 = _InterlockedDecrement(v11 + 5);
    if ( UxDebugCheckRefcount && v29 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v11 + 5), 1u, v29);
    if ( !v29 )
    {
      if ( *((_QWORD *)v11 + 3) )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 16) + 128LL))(*(_QWORD *)(a1 + 8));
        *((_QWORD *)v11 + 3) = 0;
      }
      v30 = UxDebugDisableLookaside == 0;
      *((_DWORD *)v11 + 4) = 2021218421;
      if ( v30 )
      {
        if ( UxCompactMode )
          PnlFreeToLookasideList(qword_1401A07C0, v11);
        else
          PplFreeToLookasideListProcessor(qword_1401A07C0, v11, *(unsigned int *)v11);
      }
      else
      {
        memset(v36, 0, sizeof(v36));
        v36[10] = dword_1401A07D8;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A07E8)(v11, v36);
      }
    }
LABEL_40:
    v27 = -1073741670;
    UxDuoKillConnection(a1, 1000, 3221225626LL);
    goto LABEL_37;
  }
  memset(v14, 0, 0x90u);
  *(_DWORD *)v15 = v12;
  *((_DWORD *)v15 + 4) = 1230600277;
  *((_QWORD *)v15 + 4) = v15 + 24;
  *((_QWORD *)v15 + 3) = v15 + 24;
  *((_QWORD *)v15 + 5) = UxDuoExecuteReceiver;
  *((_DWORD *)v15 + 16) = 9;
  if ( a1 )
  {
    v16 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
    if ( UxDebugCheckRefcount && v16 <= -1 )
      UlBugCheckEx(3u, a1 + 4, 0x2Cu, v16);
    *((_QWORD *)v15 + 7) = a1;
  }
  v17 = a4;
  if ( a4 > *(_DWORD *)(a1 + 17468) - *(_DWORD *)(a1 + 17464) )
    v17 = *(_DWORD *)(a1 + 17468) - *(_DWORD *)(a1 + 17464);
  _InterlockedAdd((volatile signed __int32 *)(a1 + 17464), v17);
  *((_DWORD *)v11 + 8) = v17;
  *((_QWORD *)v11 + 3) = *a3;
  *a3 = 0;
  *((_QWORD *)v15 + 9) = v11;
  if ( v17 < a4 )
    _InterlockedExchange((volatile __int32 *)(a1 + 17436), 1);
  v18 = *((_QWORD *)v15 + 7);
  if ( !v18 )
    v18 = *(_QWORD *)(*((_QWORD *)v15 + 6) + 48LL);
  v19 = *(_QWORD *)(v18 + 17272);
  v20 = v18 + 17072;
  v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v18 + 17072));
  v22 = *(_BYTE *)(v20 + 24);
  *(_BYTE *)(v20 + 24) = 1;
  v23 = *(_QWORD **)(v20 + 16);
  if ( *v23 != v20 + 8 )
    __fastfail(3u);
  v24 = v15 + 24;
  *v24 = v20 + 8;
  v24[1] = v23;
  *v23 = v24;
  *(_QWORD *)(v20 + 16) = v24;
  KeReleaseSpinLock((PKSPIN_LOCK)v20, v21);
  if ( !v22 )
  {
    v26 = v20 + 32;
    if ( *(_QWORD *)(v20 + 32) || *(_QWORD *)(v20 + 48) || *(_QWORD *)(v20 + 64) )
      UlBugCheckEx(1u, v26, (ULONG_PTR)"minio\\http\\sys\\duo.c", 0x6B9u);
    LODWORD(v35) = -1;
    LOBYTE(v25) = 1;
    UlThreadPoolEnqueueWorkItem(0, v26, UxDuoTaskWorker, v25, v19, v35);
  }
  *a5 = v17;
  v27 = 0;
LABEL_37:
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qqD(1051, 58, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, *a3, *a5, v27);
  return v27;
}

```

## disassembly

```asm
0x140022fa0  push    rbx
0x140022fa2  push    rbp
0x140022fa3  push    rsi
0x140022fa4  push    rdi
0x140022fa5  push    r12
0x140022fa7  push    r13
0x140022fa9  push    r15
0x140022fab  sub     rsp, 0B0h
0x140022fb2  mov     rax, cs:__security_cookie
0x140022fb9  xor     rax, rsp
0x140022fbc  mov     [rsp+0E8h+var_48], rax
0x140022fc4  mov     r13, [rsp+0E8h+arg_20]
0x140022fcc  xor     ebx, ebx
0x140022fce  mov     r12, r8
0x140022fd1  mov     r15d, r9d
0x140022fd4  mov     r8d, edx
0x140022fd7  mov     rsi, rcx
0x140022fda  mov     [r13+0], ebx
0x140022fde  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140022fe5  jnz     loc_140023402
0x140022feb  mov     ebp, gs:1A4h
0x140022ff3  cmp     cs:UxDebugDisableLookaside, bl
0x140022ff9  jnz     loc_140023230
0x140022fff  cmp     cs:UxCompactMode, bl
0x140023005  jnz     loc_14002336C
0x14002300b  mov     r8, cs:qword_1401A07C0
0x140023012  lea     ebx, [rbp+1]
0x140023015  shl     rbx, 7
0x140023019  add     rbx, r8
0x14002301c  movzx   eax, byte ptr [rbx+0B0h]
0x140023023  test    al, al
0x140023025  jz      loc_14002338F
0x14002302b  lea     rcx, [rbx+40h]; Lookaside
0x14002302f  call    cs:__imp_ExAllocateFromLookasideListEx
0x140023036  nop     dword ptr [rax+rax+00h]
0x14002303b  xor     ebx, ebx
0x14002303d  mov     [rsp+0E8h+arg_8], r14
0x140023045  mov     rdi, rax
0x140023048  test    rax, rax
0x14002304b  jz      loc_1400232DE
0x140023051  mov     [rax+4], rbx
0x140023055  mov     [rax+0Ch], ebx
0x140023058  mov     [rax+18h], rbx
0x14002305c  mov     [rax+20h], rbx
0x140023060  mov     [rax+28h], rbx
0x140023064  mov     [rax], ebp
0x140023066  mov     dword ptr [rax+10h], 58597855h
0x14002306d  mov     dword ptr [rax+14h], 1
0x140023074  mov     ebp, gs:1A4h
0x14002307c  cmp     cs:UxDebugDisableLookaside, 0
0x140023083  jnz     loc_140023258
0x140023089  cmp     cs:UxCompactMode, 0
0x140023090  jnz     loc_1400233A0
0x140023096  mov     r8, cs:qword_1401A0790
0x14002309d  lea     ebx, [rbp+1]
0x1400230a0  shl     rbx, 7
0x1400230a4  add     rbx, r8
0x1400230a7  movzx   eax, byte ptr [rbx+0B0h]
0x1400230ae  test    al, al
0x1400230b0  jz      loc_1400233C3
0x1400230b6  lea     rcx, [rbx+40h]; Lookaside
0x1400230ba  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400230c1  nop     dword ptr [rax+rax+00h]
0x1400230c6  mov     rbx, rax
0x1400230c9  test    rax, rax
0x1400230cc  jz      loc_1400232F5
0x1400230d2  xor     edx, edx; Val
0x1400230d4  mov     r8d, 90h; Size
0x1400230da  mov     rcx, rax; void *
0x1400230dd  call    memset
0x1400230e2  mov     [rbx], ebp
0x1400230e4  mov     dword ptr [rbx+10h], 49597855h
0x1400230eb  lea     rax, [rbx+18h]
0x1400230ef  mov     [rax+8], rax
0x1400230f3  mov     [rax], rax
0x1400230f6  lea     rax, UxDuoExecuteReceiver
0x1400230fd  mov     [rbx+28h], rax
0x140023101  mov     dword ptr [rbx+40h], 9
0x140023108  test    rsi, rsi
0x14002310b  jz      short loc_14002312D
0x14002310d  lea     rdx, [rsi+4]; BugCheckParameter2
0x140023111  mov     eax, 1
0x140023116  lock xadd [rdx], eax
0x14002311a  inc     eax
0x14002311c  cmp     cs:UxDebugCheckRefcount, 0
0x140023123  jnz     loc_1400231B5
0x140023129  mov     [rbx+38h], rsi
0x14002312d  mov     ecx, [rsi+443Ch]
0x140023133  mov     ebp, r15d
0x140023136  mov     eax, [rsi+4438h]
0x14002313c  sub     ecx, eax
0x14002313e  cmp     r15d, ecx
0x140023141  cmova   ebp, ecx
0x140023144  lock add [rsi+4438h], ebp
0x14002314b  mov     [rdi+20h], ebp
0x14002314e  mov     rax, [r12]
0x140023152  mov     [rdi+18h], rax
0x140023156  mov     qword ptr [r12], 0
0x14002315e  mov     [rbx+48h], rdi
0x140023162  cmp     ebp, r15d
0x140023165  jb      loc_140023434
0x14002316b  mov     rax, [rbx+38h]
0x14002316f  test    rax, rax
0x140023172  jnz     short loc_14002317C
0x140023174  mov     rax, [rbx+30h]
0x140023178  mov     rax, [rax+30h]
0x14002317c  mov     r14, [rax+4378h]
0x140023183  lea     rdi, [rax+42B0h]
0x14002318a  mov     rcx, rdi; SpinLock
0x14002318d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140023194  nop     dword ptr [rax+rax+00h]
0x140023199  movzx   esi, byte ptr [rdi+18h]
0x14002319d  lea     rcx, [rdi+8]
0x1400231a1  mov     byte ptr [rdi+18h], 1
0x1400231a5  mov     rdx, [rcx+8]
0x1400231a9  cmp     [rdx], rcx
0x1400231ac  jz      short loc_1400231D2
0x1400231ae  mov     ecx, 3
0x1400231b3  int     29h; Win8: RtlFailFast(ecx)
0x1400231b5  cmp     eax, 0FFFFFFFFh
0x1400231b8  jg      loc_140023129
0x1400231be  movsxd  r9, eax; BugCheckParameter4
0x1400231c1  mov     ecx, 3; BugCheckParameter1
0x1400231c6  mov     r8d, 2Ch ; ','; BugCheckParameter3
0x1400231cc  call    UlBugCheckEx
0x1400231d2  add     rbx, 18h
0x1400231d6  mov     [rbx], rcx
0x1400231d9  mov     [rbx+8], rdx
0x1400231dd  mov     [rdx], rbx
0x1400231e0  movzx   edx, al; NewIrql
0x1400231e3  mov     [rcx+8], rbx
0x1400231e7  mov     rcx, rdi; SpinLock
0x1400231ea  call    cs:__imp_KeReleaseSpinLock
0x1400231f1  nop     dword ptr [rax+rax+00h]
0x1400231f6  test    sil, sil
0x1400231f9  jnz     loc_14002329E
0x1400231ff  cmp     qword ptr [rdi+20h], 0
0x140023204  lea     rdx, [rdi+20h]; BugCheckParameter2
0x140023208  jnz     short loc_140023218
0x14002320a  cmp     qword ptr [rdx+10h], 0
0x14002320f  jnz     short loc_140023218
0x140023211  cmp     qword ptr [rdx+20h], 0
0x140023216  jz      short loc_140023280
0x140023218  mov     r9d, 6B9h; BugCheckParameter4
0x14002321e  lea     r8, BugCheckParameter3; "minio\\http\\sys\\duo.c"
0x140023225  mov     ecx, 1; BugCheckParameter1
0x14002322a  call    UlBugCheckEx
0x140023230  mov     rax, cs:off_1401A07E0
0x140023237  xor     r9d, r9d
0x14002323a  mov     r8d, cs:dword_1401A07D8
0x140023241  mov     rdx, cs:qword_1401A07D0
0x140023248  mov     ecx, cs:dword_1401A07C8
0x14002324e  call    _guard_dispatch_icall
0x140023253  jmp     loc_14002303D
0x140023258  mov     rax, cs:off_1401A07B0
0x14002325f  xor     r9d, r9d
0x140023262  mov     r8d, cs:dword_1401A07A8
0x140023269  mov     rdx, cs:qword_1401A07A0
0x140023270  mov     ecx, cs:dword_1401A0798
0x140023276  call    _guard_dispatch_icall
0x14002327b  jmp     loc_1400230C6
0x140023280  mov     dword ptr [rsp+0E8h+var_C0], 0FFFFFFFFh
0x140023288  lea     r8, UxDuoTaskWorker
0x14002328f  mov     r9b, 1
0x140023292  mov     [rsp+0E8h+var_C8], r14
0x140023297  xor     ecx, ecx
0x140023299  call    UlThreadPoolEnqueueWorkItem
0x14002329e  mov     [r13+0], ebp
0x1400232a2  xor     ebx, ebx
0x1400232a4  test    byte ptr cs:xmmword_1401A2CA0+3, 8
0x1400232ab  jnz     loc_140023479
0x1400232b1  mov     r14, [rsp+0E8h+arg_8]
0x1400232b9  mov     eax, ebx
0x1400232bb  mov     rcx, [rsp+0E8h+var_48]
0x1400232c3  xor     rcx, rsp; StackCookie
0x1400232c6  call    __security_check_cookie
0x1400232cb  add     rsp, 0B0h
0x1400232d2  pop     r15
0x1400232d4  pop     r13
0x1400232d6  pop     r12
0x1400232d8  pop     rdi
0x1400232d9  pop     rsi
0x1400232da  pop     rbp
0x1400232db  pop     rbx
0x1400232dc  retn
0x1400232de  mov     ebx, 0C000009Ah
0x1400232e3  mov     edx, 3E8h
0x1400232e8  mov     r8d, ebx
0x1400232eb  mov     rcx, rsi
0x1400232ee  call    UxDuoKillConnection
0x1400232f3  jmp     short loc_1400232A4
0x1400232f5  mov     eax, 0FFFFFFFFh
0x1400232fa  lock xadd [rdi+14h], eax
0x1400232ff  dec     eax
0x140023301  cmp     cs:UxDebugCheckRefcount, 0
0x140023308  jnz     loc_1400233D4
0x14002330e  test    eax, eax
0x140023310  jnz     short loc_1400232DE
0x140023312  mov     rdx, [rdi+18h]
0x140023316  test    rdx, rdx
0x140023319  jz      short loc_140023337
0x14002331b  mov     rax, [rsi+10h]
0x14002331f  mov     rcx, [rsi+8]
0x140023323  mov     rax, [rax+80h]
0x14002332a  call    _guard_dispatch_icall
0x14002332f  mov     qword ptr [rdi+18h], 0
0x140023337  cmp     cs:UxDebugDisableLookaside, 0
0x14002333e  mov     dword ptr [rdi+10h], 78795875h
0x140023345  jnz     loc_140023444
0x14002334b  cmp     cs:UxCompactMode, 0
0x140023352  mov     rdx, rdi
0x140023355  mov     rcx, cs:qword_1401A07C0
0x14002335c  jz      loc_1400233F5
0x140023362  call    PnlFreeToLookasideList
0x140023367  jmp     loc_1400232DE
0x14002336c  mov     rbx, cs:qword_1401A07C0
0x140023373  call    cs:__imp_KeGetCurrentNodeNumber
0x14002337a  nop     dword ptr [rax+rax+00h]
0x14002337f  movzx   edx, ax
0x140023382  mov     rcx, rbx
0x140023385  call    PplAllocateFromLookasideListProcessor
0x14002338a  jmp     loc_14002303B
0x14002338f  lea     rdx, [rbx+40h]
0x140023393  mov     rcx, r8
0x140023396  call    PplpLazyInitializeLookasideList
0x14002339b  jmp     loc_14002302B
0x1400233a0  mov     rbx, cs:qword_1401A0790
0x1400233a7  call    cs:__imp_KeGetCurrentNodeNumber
0x1400233ae  nop     dword ptr [rax+rax+00h]
0x1400233b3  movzx   edx, ax
0x1400233b6  mov     rcx, rbx
0x1400233b9  call    PplAllocateFromLookasideListProcessor
0x1400233be  jmp     loc_1400230C6
0x1400233c3  lea     rdx, [rbx+40h]
0x1400233c7  mov     rcx, r8
0x1400233ca  call    PplpLazyInitializeLookasideList
0x1400233cf  jmp     loc_1400230B6
0x1400233d4  cmp     eax, 0FFFFFFFFh
0x1400233d7  jg      loc_14002330E
0x1400233dd  movsxd  r9, eax; BugCheckParameter4
0x1400233e0  lea     rdx, [rdi+14h]; BugCheckParameter2
0x1400233e4  mov     r8d, 1; BugCheckParameter3
0x1400233ea  mov     ecx, 3; BugCheckParameter1
0x1400233ef  call    UlBugCheckEx
0x1400233f5  mov     r8d, [rdi]
0x1400233f8  call    PplFreeToLookasideListProcessor
0x1400233fd  jmp     loc_1400232DE
0x140023402  mov     [rsp+0E8h+var_B0], r13
0x140023407  mov     edx, 39h ; '9'
0x14002340c  mov     [rsp+0E8h+var_B8], r15
0x140023411  mov     ecx, 411h
0x140023416  mov     [rsp+0E8h+var_C0], r12
0x14002341b  mov     r9, rsi
0x14002341e  mov     dword ptr [rsp+0E8h+var_C8], r8d
0x140023423  lea     r8, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids
0x14002342a  call    WPP_SF_qLqPq
0x14002342f  jmp     loc_140022FEB
0x140023434  mov     eax, 1
0x140023439  xchg    eax, [rsi+441Ch]
0x14002343f  jmp     loc_14002316B
0x140023444  xor     edx, edx; Val
0x140023446  lea     rcx, [rsp+0E8h+var_A8]; void *
0x14002344b  mov     r8d, 60h ; '`'; Size
0x140023451  call    memset
0x140023456  mov     eax, cs:dword_1401A07D8
0x14002345c  lea     rdx, [rsp+0E8h+var_A8]
0x140023461  mov     [rsp+0E8h+var_80], eax
0x140023465  mov     rcx, rdi
0x140023468  mov     rax, cs:off_1401A07E8
0x14002346f  call    _guard_dispatch_icall
0x140023474  jmp     loc_1400232DE
0x140023479  mov     r10d, [r13+0]
0x14002347d  lea     r8, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids
0x140023484  mov     r9, [r12]
0x140023488  mov     edx, 3Ah ; ':'
0x14002348d  mov     ecx, 41Bh
0x140023492  mov     dword ptr [rsp+0E8h+var_C0], ebx
0x140023496  mov     [rsp+0E8h+var_C8], r10
0x14002349b  call    WPP_SF_qqD
0x1400234a0  jmp     loc_1400232B1
```
