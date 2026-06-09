# UlpThreadPoolWorker

- ea: `0x140060000`
- end: `0x140060478`
- name: `UlpThreadPoolWorker`
- size: `1144`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x14000a350`
- `0x140035a70`
- `0x140060000`
- `0x140062110`
- `0x140062bf0`
- `0x14013def4`
- `0x1401677e0`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401d620c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140060394`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060406`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060446`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006045f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060394`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060406`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060446`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006045f`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140060068`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14006020b`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140060068`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14006020b`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140060181`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140060181`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006010d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006010d`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400603d3`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400603d3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006014c`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006014c`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140060055`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140060055`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006003d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060265`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006003d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060265`
- `ntoskrnl!KeSetEvent` at `0x1400603f5`
- `ntoskrnl!KeSetEvent` at `0x1400603f5`

## pseudocode

```c
void __fastcall UlpThreadPoolWorker(__int64 **StartContext)
{
  __int64 *v1; // r14
  __int64 **v2; // rsi
  __int64 v3; // r15
  __int64 v4; // r8
  union _SLIST_HEADER *v5; // rdi
  PSLIST_ENTRY v6; // rax
  bool v7; // zf
  _QWORD *p_Next; // rbx
  _QWORD *v9; // rdi
  _QWORD *v10; // rax
  void *v11; // rbx
  char v12; // si
  void (__fastcall *v13)(_QWORD *); // r15
  _QWORD *v14; // r13
  char v15; // r12
  __int64 v16; // rax
  __int64 v17; // rbp
  ULONG_PTR v18; // rdx
  int v19; // eax
  PSLIST_ENTRY v20; // rbx
  PSLIST_ENTRY v21; // rsi
  struct _SLIST_ENTRY *Next; // rax
  struct _SLIST_ENTRY *v23; // rbp
  struct _SLIST_ENTRY *v24; // rbx
  struct _SLIST_ENTRY *v25; // r15
  char v26; // di
  _OWORD v27[4]; // [rsp+30h] [rbp-48h] BYREF
  PSLIST_ENTRY v29; // [rsp+88h] [rbp+10h] BYREF
  __int64 v30; // [rsp+90h] [rbp+18h]

  v1 = *StartContext;
  v2 = StartContext;
  v3 = **StartContext;
  v30 = v3;
  KeWaitForSingleObject(StartContext + 4, Executive, 0, 0, 0);
  if ( !*((_BYTE *)v2 + 56) )
  {
    IoSetThreadHardErrorMode(0);
    while ( 1 )
    {
      v5 = (union _SLIST_HEADER *)(v1 + 2);
      v6 = ExpInterlockedFlushSList((PSLIST_HEADER)v1 + 1);
      v7 = *((_BYTE *)v2 + 56) == 0;
      p_Next = &v6->Next;
      v29 = v6;
      if ( !v7 )
        break;
      if ( !v6 && *(_BYTE *)(v3 + 32) )
      {
        UlpStealThreadPoolWork(v3, *((unsigned int *)v1 + 2), &v29);
        p_Next = &v29->Next;
      }
      if ( p_Next )
        goto LABEL_5;
      KeWaitForSingleObject(v1 + 4, Executive, 0, 0, 0);
LABEL_24:
      if ( *((_BYTE *)v2 + 56) )
        goto LABEL_25;
    }
    if ( !v6 )
      goto LABEL_24;
LABEL_5:
    _InterlockedExchange((volatile __int32 *)v1 + 3, 0);
    v27[0] = 0;
    if ( !UxEnableIrqlEnforcement || !KeGetCurrentIrql() )
    {
      v9 = 0;
      if ( p_Next )
      {
        do
        {
          v10 = (_QWORD *)*p_Next;
          *p_Next = v9;
          v9 = p_Next;
          p_Next = v10;
        }
        while ( v10 );
      }
      while ( 1 )
      {
        if ( !v9 )
        {
          v2 = StartContext;
          v5 = (union _SLIST_HEADER *)(v1 + 2);
          v3 = v30;
          goto LABEL_24;
        }
        v11 = (void *)v9[4];
        v12 = 0;
        v13 = (void (__fastcall *)(_QWORD *))v9[2];
        v14 = (_QWORD *)*v9;
        v15 = *((_BYTE *)v9 + 24);
        *v9 = 0;
        v9[2] = 0;
        v9[4] = 0;
        v27[0] = 0;
        if ( v11 == (void *)-1LL )
          break;
        v16 = PsAttachSiloToCurrentThread(v11);
        v17 = v16;
        v12 = 1;
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) == 0 )
          goto LABEL_11;
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v16, v11);
        v13(v9);
LABEL_12:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v17);
        PsDetachSiloFromCurrentThread(v17);
LABEL_15:
        v27[0] = 0;
        if ( v15 )
        {
          v29 = 0;
          PsGetPermanentSiloContext(v11, (unsigned int)UxPodMonitorSlot, &v29);
          if ( v11 )
            ObfDereferenceObjectWithTag(v11, 0x49576C55u);
          v18 = (ULONG_PTR)(&v29[1].Next + 1);
          v19 = _InterlockedDecrement((volatile signed __int32 *)&v29[1].Next + 2);
          if ( UxDebugCheckRefcount && v19 <= -1 )
            UlBugCheckEx(3u, v18, 0xDu, v19);
          if ( !v19 )
            KeSetEvent((PRKEVENT)&v29[2], 0, 0);
        }
        if ( UxEnableIrqlEnforcement && KeGetCurrentIrql() )
LABEL_56:
          UlBugCheckEx(4u, 0, (ULONG_PTR)"minio\\http\\sys\\thrdpool.c", 0x579u);
        ++*((_DWORD *)v1 + 22);
        v9 = v14;
      }
      v17 = *((_QWORD *)&v27[0] + 1);
LABEL_11:
      v13(v9);
      if ( !v12 )
        goto LABEL_15;
      goto LABEL_12;
    }
LABEL_55:
    UlBugCheckEx(4u, 0, (ULONG_PTR)"minio\\http\\sys\\thrdpool.c", 0x549u);
  }
  v5 = (union _SLIST_HEADER *)(v1 + 2);
LABEL_25:
  if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_ddL(1304, 17, v4, *((unsigned int *)v2 + 2), *((_DWORD *)v1 + 2), *(_DWORD *)v3);
  v20 = ExpInterlockedFlushSList(v5);
  if ( v20 )
  {
    v27[0] = 0;
    if ( UxEnableIrqlEnforcement && KeGetCurrentIrql() )
      goto LABEL_55;
    v21 = 0;
    do
    {
      Next = v20->Next;
      v20->Next = v21;
      v21 = v20;
      v20 = Next;
    }
    while ( Next );
    while ( v21 )
    {
      v23 = v21[2].Next;
      v24 = v21[1].Next;
      v25 = v21->Next;
      v26 = *((_BYTE *)&v21[1].Next + 8);
      v21->Next = 0;
      v21[1].Next = 0;
      v21[2].Next = 0;
      UxPodAttachThread(v23, v27);
      ((void (__fastcall *)(PSLIST_ENTRY))v24)(v21);
      UxPodDetachThread(v27);
      if ( v26 )
        UxPodDereferenceSilo(v23, 0x49576C55u, 0xDu);
      if ( UxEnableIrqlEnforcement && KeGetCurrentIrql() )
        goto LABEL_56;
      ++*((_DWORD *)v1 + 22);
      v21 = v25;
    }
  }
}

```

## disassembly

```asm
0x140060000  mov     [rsp+arg_18], rbx
0x140060005  mov     [rsp+arg_0], rcx
0x14006000a  push    rbp
0x14006000b  push    rsi
0x14006000c  push    rdi
0x14006000d  push    r12
0x14006000f  push    r13
0x140060011  push    r14
0x140060013  push    r15
0x140060015  sub     rsp, 40h
0x140060019  mov     r14, [rcx]
0x14006001c  mov     rsi, rcx
0x14006001f  xor     ebp, ebp
0x140060021  add     rcx, 20h ; ' '; Object
0x140060025  xor     r9d, r9d; Alertable
0x140060028  mov     [rsp+78h+Timeout], rbp; Timeout
0x14006002d  xor     r8d, r8d; WaitMode
0x140060030  xor     edx, edx; WaitReason
0x140060032  mov     r15, [r14]
0x140060035  mov     [rsp+78h+arg_10], r15
0x14006003d  call    cs:__imp_KeWaitForSingleObject
0x140060044  nop     dword ptr [rax+rax+00h]
0x140060049  cmp     [rsi+38h], bpl
0x14006004d  jnz     loc_14006029D
0x140060053  xor     ecx, ecx; EnableHardErrors
0x140060055  call    cs:__imp_IoSetThreadHardErrorMode
0x14006005c  nop     dword ptr [rax+rax+00h]
0x140060061  lea     rdi, [r14+10h]
0x140060065  mov     rcx, rdi; ListHead
0x140060068  call    cs:__imp_ExpInterlockedFlushSList
0x14006006f  nop     dword ptr [rax+rax+00h]
0x140060074  cmp     byte ptr [rsi+38h], 0
0x140060078  mov     rbx, rax
0x14006007b  mov     [rsp+78h+arg_8], rax
0x140060083  jz      loc_14006023C
0x140060089  test    rax, rax
0x14006008c  jz      loc_1400601F1
0x140060092  mov     eax, ebp
0x140060094  xorps   xmm0, xmm0
0x140060097  xchg    eax, [r14+0Ch]
0x14006009b  cmp     cs:UxEnableIrqlEnforcement, 0
0x1400600a2  movups  [rsp+78h+var_48], xmm0
0x1400600a7  jnz     loc_140060394
0x1400600ad  mov     rdi, rbp
0x1400600b0  test    rbx, rbx
0x1400600b3  jz      short loc_1400600D1
0x1400600b5  nop     word ptr [rax+rax+00000000h]
0x1400600c0  mov     rax, [rbx]
0x1400600c3  mov     [rbx], rdi
0x1400600c6  mov     rdi, rbx
0x1400600c9  mov     rbx, rax
0x1400600cc  test    rax, rax
0x1400600cf  jnz     short loc_1400600C0
0x1400600d1  test    rdi, rdi
0x1400600d4  jz      loc_1400601DD
0x1400600da  mov     rbx, [rdi+20h]
0x1400600de  xor     sil, sil
0x1400600e1  mov     r15, [rdi+10h]
0x1400600e5  xorps   xmm0, xmm0
0x1400600e8  mov     r13, [rdi]
0x1400600eb  movzx   r12d, byte ptr [rdi+18h]
0x1400600f0  mov     [rdi], rbp
0x1400600f3  mov     [rdi+10h], rbp
0x1400600f7  mov     [rdi+20h], rbp
0x1400600fb  movups  [rsp+78h+var_48], xmm0
0x140060100  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140060104  jz      loc_140060293
0x14006010a  mov     rcx, rbx
0x14006010d  call    cs:__imp_PsAttachSiloToCurrentThread
0x140060114  nop     dword ptr [rax+rax+00h]
0x140060119  mov     rbp, rax
0x14006011c  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140060123  mov     sil, 1
0x140060126  jnz     loc_1400602A6
0x14006012c  mov     rcx, rdi
0x14006012f  mov     rax, r15
0x140060132  call    _guard_dispatch_icall
0x140060137  test    sil, sil
0x14006013a  jz      short loc_140060158
0x14006013c  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140060143  jnz     loc_1400603AD
0x140060149  mov     rcx, rbp
0x14006014c  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140060153  nop     dword ptr [rax+rax+00h]
0x140060158  xorps   xmm0, xmm0
0x14006015b  movups  [rsp+78h+var_48], xmm0
0x140060160  test    r12b, r12b
0x140060163  jz      short loc_1400601C2
0x140060165  mov     edx, cs:UxPodMonitorSlot
0x14006016b  lea     r8, [rsp+78h+arg_8]
0x140060173  xor     r12d, r12d
0x140060176  mov     rcx, rbx
0x140060179  mov     [rsp+78h+arg_8], r12
0x140060181  call    cs:__imp_PsGetPermanentSiloContext
0x140060188  nop     dword ptr [rax+rax+00h]
0x14006018d  test    rbx, rbx
0x140060190  jnz     loc_1400603CB
0x140060196  mov     rdx, [rsp+78h+arg_8]
0x14006019e  mov     eax, 0FFFFFFFFh
0x1400601a3  add     rdx, 18h; BugCheckParameter2
0x1400601a7  lock xadd [rdx], eax
0x1400601ab  dec     eax
0x1400601ad  cmp     cs:UxDebugCheckRefcount, r12b
0x1400601b4  jnz     loc_140060276
0x1400601ba  test    eax, eax
0x1400601bc  jz      loc_1400603E4
0x1400601c2  cmp     cs:UxEnableIrqlEnforcement, 0
0x1400601c9  jnz     loc_140060406
0x1400601cf  inc     dword ptr [r14+58h]
0x1400601d3  mov     rdi, r13
0x1400601d6  xor     ebp, ebp
0x1400601d8  jmp     loc_1400600D1
0x1400601dd  mov     rsi, [rsp+78h+arg_0]
0x1400601e5  lea     rdi, [r14+10h]
0x1400601e9  mov     r15, [rsp+78h+arg_10]
0x1400601f1  cmp     byte ptr [rsi+38h], 0
0x1400601f5  jz      loc_140060061
0x1400601fb  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 1
0x140060202  jnz     loc_14006041F
0x140060208  mov     rcx, rdi; ListHead
0x14006020b  call    cs:__imp_ExpInterlockedFlushSList
0x140060212  nop     dword ptr [rax+rax+00h]
0x140060217  mov     rbx, rax
0x14006021a  test    rax, rax
0x14006021d  jnz     loc_1400602D4
0x140060223  mov     rbx, [rsp+78h+arg_18]
0x14006022b  add     rsp, 40h
0x14006022f  pop     r15
0x140060231  pop     r14
0x140060233  pop     r13
0x140060235  pop     r12
0x140060237  pop     rdi
0x140060238  pop     rsi
0x140060239  pop     rbp
0x14006023a  retn
0x14006023c  test    rax, rax
0x14006023f  jnz     short loc_14006024B
0x140060241  cmp     [r15+20h], al
0x140060245  jnz     loc_140060373
0x14006024b  test    rbx, rbx
0x14006024e  jnz     loc_140060092
0x140060254  lea     rcx, [r14+20h]; Object
0x140060258  mov     [rsp+78h+Timeout], rbp; Timeout
0x14006025d  xor     r9d, r9d; Alertable
0x140060260  xor     r8d, r8d; WaitMode
0x140060263  xor     edx, edx; WaitReason
0x140060265  call    cs:__imp_KeWaitForSingleObject
0x14006026c  nop     dword ptr [rax+rax+00h]
0x140060271  jmp     loc_1400601F1
0x140060276  cmp     eax, 0FFFFFFFFh
0x140060279  jg      loc_1400601BA
0x14006027f  movsxd  r9, eax; BugCheckParameter4
0x140060282  mov     ecx, 3; BugCheckParameter1
0x140060287  mov     r8d, 0Dh; BugCheckParameter3
0x14006028d  call    UlBugCheckEx
0x140060293  mov     rbp, qword ptr [rsp+78h+var_48+8]
0x140060298  jmp     loc_14006012C
0x14006029d  lea     rdi, [r14+10h]
0x1400602a1  jmp     loc_1400601FB
0x1400602a6  mov     edx, 19h
0x1400602ab  mov     [rsp+78h+Timeout], rbx
0x1400602b0  mov     ecx, 51Ch
0x1400602b5  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x1400602bc  mov     r9, rax
0x1400602bf  call    WPP_SF_qq
0x1400602c4  mov     rcx, rdi
0x1400602c7  mov     rax, r15
0x1400602ca  call    _guard_dispatch_icall
0x1400602cf  jmp     loc_14006013C
0x1400602d4  cmp     cs:UxEnableIrqlEnforcement, 0
0x1400602db  xorps   xmm0, xmm0
0x1400602de  movups  [rsp+78h+var_48], xmm0
0x1400602e3  jnz     loc_140060446
0x1400602e9  mov     rsi, rbp
0x1400602ec  mov     rax, [rbx]
0x1400602ef  mov     [rbx], rsi
0x1400602f2  mov     rsi, rbx
0x1400602f5  mov     rbx, rax
0x1400602f8  test    rax, rax
0x1400602fb  jnz     short loc_1400602EC
0x1400602fd  xor     r12d, r12d
0x140060300  test    rsi, rsi
0x140060303  jz      loc_140060223
0x140060309  mov     rbp, [rsi+20h]
0x14006030d  lea     rdx, [rsp+78h+var_48]
0x140060312  mov     rbx, [rsi+10h]
0x140060316  mov     rcx, rbp
0x140060319  mov     r15, [rsi]
0x14006031c  movzx   edi, byte ptr [rsi+18h]
0x140060320  mov     [rsi], r12
0x140060323  mov     [rsi+10h], r12
0x140060327  mov     [rsi+20h], r12
0x14006032b  call    UxPodAttachThread
0x140060330  mov     rcx, rsi
0x140060333  mov     rax, rbx
0x140060336  call    _guard_dispatch_icall
0x14006033b  lea     rcx, [rsp+78h+var_48]
0x140060340  call    UxPodDetachThread
0x140060345  test    dil, dil
0x140060348  jz      short loc_14006035D
0x14006034a  mov     edx, 49576C55h; Tag
0x14006034f  mov     r8d, 0Dh; BugCheckParameter3
0x140060355  mov     rcx, rbp; Object
0x140060358  call    UxPodDereferenceSilo
0x14006035d  cmp     cs:UxEnableIrqlEnforcement, r12b
0x140060364  jnz     loc_14006045F
0x14006036a  inc     dword ptr [r14+58h]
0x14006036e  mov     rsi, r15
0x140060371  jmp     short loc_140060300
0x140060373  mov     edx, [r14+8]
0x140060377  lea     r8, [rsp+78h+arg_8]
0x14006037f  mov     rcx, r15
0x140060382  call    UlpStealThreadPoolWork
0x140060387  mov     rbx, [rsp+78h+arg_8]
0x14006038f  jmp     loc_14006024B
0x140060394  call    cs:__imp_KeGetCurrentIrql
0x14006039b  nop     dword ptr [rax+rax+00h]
0x1400603a0  test    al, al
0x1400603a2  jnz     loc_14017797A
0x1400603a8  jmp     loc_1400600AD
0x1400603ad  mov     edx, 1Ah
0x1400603b2  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x1400603b9  mov     ecx, 51Ch
0x1400603be  mov     r9, rbp
0x1400603c1  call    WPP_SF_q
0x1400603c6  jmp     loc_140060149
0x1400603cb  mov     edx, 49576C55h; Tag
0x1400603d0  mov     rcx, rbx; Object
0x1400603d3  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400603da  nop     dword ptr [rax+rax+00h]
0x1400603df  jmp     loc_140060196
0x1400603e4  mov     rcx, [rsp+78h+arg_8]
0x1400603ec  xor     r8d, r8d; Wait
0x1400603ef  add     rcx, 20h ; ' '; Event
0x1400603f3  xor     edx, edx; Increment
0x1400603f5  call    cs:__imp_KeSetEvent
0x1400603fc  nop     dword ptr [rax+rax+00h]
0x140060401  jmp     loc_1400601C2
0x140060406  call    cs:__imp_KeGetCurrentIrql
0x14006040d  nop     dword ptr [rax+rax+00h]
0x140060412  test    al, al
0x140060414  jnz     loc_140177994
0x14006041a  jmp     loc_1400601CF
0x14006041f  mov     eax, [r15]
0x140060422  mov     edx, 11h
0x140060427  mov     r9d, [rsi+8]
0x14006042b  mov     ecx, 518h
0x140060430  mov     [rsp+78h+var_50], eax
0x140060434  mov     eax, [r14+8]
0x140060438  mov     dword ptr [rsp+78h+Timeout], eax
0x14006043c  call    WPP_SF_ddL
0x140060441  jmp     loc_140060208
0x140060446  call    cs:__imp_KeGetCurrentIrql
0x14006044d  nop     dword ptr [rax+rax+00h]
0x140060452  test    al, al
0x140060454  jz      loc_1400602E9
0x14006045a  jmp     loc_14017797A
0x14006045f  call    cs:__imp_KeGetCurrentIrql
0x140060466  nop     dword ptr [rax+rax+00h]
0x14006046b  test    al, al
0x14006046d  jnz     loc_140177994
0x140060473  jmp     loc_14006036A
0x14017797a  mov     r9d, 549h; BugCheckParameter4
0x140177980  lea     r8, aMinioHttpSysTh; "minio\\http\\sys\\thrdpool.c"
0x140177987  xor     edx, edx; BugCheckParameter2
0x140177989  mov     ecx, 4; BugCheckParameter1
0x14017798e  call    UlBugCheckEx
0x140177994  mov     r9d, 579h; BugCheckParameter4
0x14017799a  lea     r8, aMinioHttpSysTh; "minio\\http\\sys\\thrdpool.c"
0x1401779a1  xor     edx, edx; BugCheckParameter2
0x1401779a3  mov     ecx, 4; BugCheckParameter1
0x1401779a8  call    UlBugCheckEx
```
