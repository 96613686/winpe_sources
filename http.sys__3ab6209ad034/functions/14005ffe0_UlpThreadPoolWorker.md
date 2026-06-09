# UlpThreadPoolWorker

- ea: `0x14005ffe0`
- end: `0x140060458`
- name: `UlpThreadPoolWorker`
- size: `1144`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x14000a350`
- `0x140035a50`
- `0x14005ffe0`
- `0x1400620f0`
- `0x140062bd0`
- `0x14013dfe4`
- `0x1401678f0`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401d620c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140060374`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400603e6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060426`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006043f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060374`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400603e6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140060426`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006043f`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140060048`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400601eb`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140060048`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400601eb`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140060161`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140060161`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400600ed`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400600ed`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400603b3`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400603b3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006012c`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14006012c`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140060035`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140060035`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006001d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060245`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006001d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060245`
- `ntoskrnl!KeSetEvent` at `0x1400603d5`
- `ntoskrnl!KeSetEvent` at `0x1400603d5`

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
0x14005ffe0  mov     [rsp+arg_18], rbx
0x14005ffe5  mov     [rsp+arg_0], rcx
0x14005ffea  push    rbp
0x14005ffeb  push    rsi
0x14005ffec  push    rdi
0x14005ffed  push    r12
0x14005ffef  push    r13
0x14005fff1  push    r14
0x14005fff3  push    r15
0x14005fff5  sub     rsp, 40h
0x14005fff9  mov     r14, [rcx]
0x14005fffc  mov     rsi, rcx
0x14005ffff  xor     ebp, ebp
0x140060001  add     rcx, 20h ; ' '; Object
0x140060005  xor     r9d, r9d; Alertable
0x140060008  mov     [rsp+78h+Timeout], rbp; Timeout
0x14006000d  xor     r8d, r8d; WaitMode
0x140060010  xor     edx, edx; WaitReason
0x140060012  mov     r15, [r14]
0x140060015  mov     [rsp+78h+arg_10], r15
0x14006001d  call    cs:__imp_KeWaitForSingleObject
0x140060024  nop     dword ptr [rax+rax+00h]
0x140060029  cmp     [rsi+38h], bpl
0x14006002d  jnz     loc_14006027D
0x140060033  xor     ecx, ecx; EnableHardErrors
0x140060035  call    cs:__imp_IoSetThreadHardErrorMode
0x14006003c  nop     dword ptr [rax+rax+00h]
0x140060041  lea     rdi, [r14+10h]
0x140060045  mov     rcx, rdi; ListHead
0x140060048  call    cs:__imp_ExpInterlockedFlushSList
0x14006004f  nop     dword ptr [rax+rax+00h]
0x140060054  cmp     byte ptr [rsi+38h], 0
0x140060058  mov     rbx, rax
0x14006005b  mov     [rsp+78h+arg_8], rax
0x140060063  jz      loc_14006021C
0x140060069  test    rax, rax
0x14006006c  jz      loc_1400601D1
0x140060072  mov     eax, ebp
0x140060074  xorps   xmm0, xmm0
0x140060077  xchg    eax, [r14+0Ch]
0x14006007b  cmp     cs:UxEnableIrqlEnforcement, 0
0x140060082  movups  [rsp+78h+var_48], xmm0
0x140060087  jnz     loc_140060374
0x14006008d  mov     rdi, rbp
0x140060090  test    rbx, rbx
0x140060093  jz      short loc_1400600B1
0x140060095  nop     word ptr [rax+rax+00000000h]
0x1400600a0  mov     rax, [rbx]
0x1400600a3  mov     [rbx], rdi
0x1400600a6  mov     rdi, rbx
0x1400600a9  mov     rbx, rax
0x1400600ac  test    rax, rax
0x1400600af  jnz     short loc_1400600A0
0x1400600b1  test    rdi, rdi
0x1400600b4  jz      loc_1400601BD
0x1400600ba  mov     rbx, [rdi+20h]
0x1400600be  xor     sil, sil
0x1400600c1  mov     r15, [rdi+10h]
0x1400600c5  xorps   xmm0, xmm0
0x1400600c8  mov     r13, [rdi]
0x1400600cb  movzx   r12d, byte ptr [rdi+18h]
0x1400600d0  mov     [rdi], rbp
0x1400600d3  mov     [rdi+10h], rbp
0x1400600d7  mov     [rdi+20h], rbp
0x1400600db  movups  [rsp+78h+var_48], xmm0
0x1400600e0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400600e4  jz      loc_140060273
0x1400600ea  mov     rcx, rbx
0x1400600ed  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400600f4  nop     dword ptr [rax+rax+00h]
0x1400600f9  mov     rbp, rax
0x1400600fc  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140060103  mov     sil, 1
0x140060106  jnz     loc_140060286
0x14006010c  mov     rcx, rdi
0x14006010f  mov     rax, r15
0x140060112  call    _guard_dispatch_icall
0x140060117  test    sil, sil
0x14006011a  jz      short loc_140060138
0x14006011c  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140060123  jnz     loc_14006038D
0x140060129  mov     rcx, rbp
0x14006012c  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140060133  nop     dword ptr [rax+rax+00h]
0x140060138  xorps   xmm0, xmm0
0x14006013b  movups  [rsp+78h+var_48], xmm0
0x140060140  test    r12b, r12b
0x140060143  jz      short loc_1400601A2
0x140060145  mov     edx, cs:UxPodMonitorSlot
0x14006014b  lea     r8, [rsp+78h+arg_8]
0x140060153  xor     r12d, r12d
0x140060156  mov     rcx, rbx
0x140060159  mov     [rsp+78h+arg_8], r12
0x140060161  call    cs:__imp_PsGetPermanentSiloContext
0x140060168  nop     dword ptr [rax+rax+00h]
0x14006016d  test    rbx, rbx
0x140060170  jnz     loc_1400603AB
0x140060176  mov     rdx, [rsp+78h+arg_8]
0x14006017e  mov     eax, 0FFFFFFFFh
0x140060183  add     rdx, 18h; BugCheckParameter2
0x140060187  lock xadd [rdx], eax
0x14006018b  dec     eax
0x14006018d  cmp     cs:UxDebugCheckRefcount, r12b
0x140060194  jnz     loc_140060256
0x14006019a  test    eax, eax
0x14006019c  jz      loc_1400603C4
0x1400601a2  cmp     cs:UxEnableIrqlEnforcement, 0
0x1400601a9  jnz     loc_1400603E6
0x1400601af  inc     dword ptr [r14+58h]
0x1400601b3  mov     rdi, r13
0x1400601b6  xor     ebp, ebp
0x1400601b8  jmp     loc_1400600B1
0x1400601bd  mov     rsi, [rsp+78h+arg_0]
0x1400601c5  lea     rdi, [r14+10h]
0x1400601c9  mov     r15, [rsp+78h+arg_10]
0x1400601d1  cmp     byte ptr [rsi+38h], 0
0x1400601d5  jz      loc_140060041
0x1400601db  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 1
0x1400601e2  jnz     loc_1400603FF
0x1400601e8  mov     rcx, rdi; ListHead
0x1400601eb  call    cs:__imp_ExpInterlockedFlushSList
0x1400601f2  nop     dword ptr [rax+rax+00h]
0x1400601f7  mov     rbx, rax
0x1400601fa  test    rax, rax
0x1400601fd  jnz     loc_1400602B4
0x140060203  mov     rbx, [rsp+78h+arg_18]
0x14006020b  add     rsp, 40h
0x14006020f  pop     r15
0x140060211  pop     r14
0x140060213  pop     r13
0x140060215  pop     r12
0x140060217  pop     rdi
0x140060218  pop     rsi
0x140060219  pop     rbp
0x14006021a  retn
0x14006021c  test    rax, rax
0x14006021f  jnz     short loc_14006022B
0x140060221  cmp     [r15+20h], al
0x140060225  jnz     loc_140060353
0x14006022b  test    rbx, rbx
0x14006022e  jnz     loc_140060072
0x140060234  lea     rcx, [r14+20h]; Object
0x140060238  mov     [rsp+78h+Timeout], rbp; Timeout
0x14006023d  xor     r9d, r9d; Alertable
0x140060240  xor     r8d, r8d; WaitMode
0x140060243  xor     edx, edx; WaitReason
0x140060245  call    cs:__imp_KeWaitForSingleObject
0x14006024c  nop     dword ptr [rax+rax+00h]
0x140060251  jmp     loc_1400601D1
0x140060256  cmp     eax, 0FFFFFFFFh
0x140060259  jg      loc_14006019A
0x14006025f  movsxd  r9, eax; BugCheckParameter4
0x140060262  mov     ecx, 3; BugCheckParameter1
0x140060267  mov     r8d, 0Dh; BugCheckParameter3
0x14006026d  call    UlBugCheckEx
0x140060273  mov     rbp, qword ptr [rsp+78h+var_48+8]
0x140060278  jmp     loc_14006010C
0x14006027d  lea     rdi, [r14+10h]
0x140060281  jmp     loc_1400601DB
0x140060286  mov     edx, 19h
0x14006028b  mov     [rsp+78h+Timeout], rbx
0x140060290  mov     ecx, 51Ch
0x140060295  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x14006029c  mov     r9, rax
0x14006029f  call    WPP_SF_qq
0x1400602a4  mov     rcx, rdi
0x1400602a7  mov     rax, r15
0x1400602aa  call    _guard_dispatch_icall
0x1400602af  jmp     loc_14006011C
0x1400602b4  cmp     cs:UxEnableIrqlEnforcement, 0
0x1400602bb  xorps   xmm0, xmm0
0x1400602be  movups  [rsp+78h+var_48], xmm0
0x1400602c3  jnz     loc_140060426
0x1400602c9  mov     rsi, rbp
0x1400602cc  mov     rax, [rbx]
0x1400602cf  mov     [rbx], rsi
0x1400602d2  mov     rsi, rbx
0x1400602d5  mov     rbx, rax
0x1400602d8  test    rax, rax
0x1400602db  jnz     short loc_1400602CC
0x1400602dd  xor     r12d, r12d
0x1400602e0  test    rsi, rsi
0x1400602e3  jz      loc_140060203
0x1400602e9  mov     rbp, [rsi+20h]
0x1400602ed  lea     rdx, [rsp+78h+var_48]
0x1400602f2  mov     rbx, [rsi+10h]
0x1400602f6  mov     rcx, rbp
0x1400602f9  mov     r15, [rsi]
0x1400602fc  movzx   edi, byte ptr [rsi+18h]
0x140060300  mov     [rsi], r12
0x140060303  mov     [rsi+10h], r12
0x140060307  mov     [rsi+20h], r12
0x14006030b  call    UxPodAttachThread
0x140060310  mov     rcx, rsi
0x140060313  mov     rax, rbx
0x140060316  call    _guard_dispatch_icall
0x14006031b  lea     rcx, [rsp+78h+var_48]
0x140060320  call    UxPodDetachThread
0x140060325  test    dil, dil
0x140060328  jz      short loc_14006033D
0x14006032a  mov     edx, 49576C55h; Tag
0x14006032f  mov     r8d, 0Dh; BugCheckParameter3
0x140060335  mov     rcx, rbp; Object
0x140060338  call    UxPodDereferenceSilo
0x14006033d  cmp     cs:UxEnableIrqlEnforcement, r12b
0x140060344  jnz     loc_14006043F
0x14006034a  inc     dword ptr [r14+58h]
0x14006034e  mov     rsi, r15
0x140060351  jmp     short loc_1400602E0
0x140060353  mov     edx, [r14+8]
0x140060357  lea     r8, [rsp+78h+arg_8]
0x14006035f  mov     rcx, r15
0x140060362  call    UlpStealThreadPoolWork
0x140060367  mov     rbx, [rsp+78h+arg_8]
0x14006036f  jmp     loc_14006022B
0x140060374  call    cs:__imp_KeGetCurrentIrql
0x14006037b  nop     dword ptr [rax+rax+00h]
0x140060380  test    al, al
0x140060382  jnz     loc_140177A7A
0x140060388  jmp     loc_14006008D
0x14006038d  mov     edx, 1Ah
0x140060392  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140060399  mov     ecx, 51Ch
0x14006039e  mov     r9, rbp
0x1400603a1  call    WPP_SF_q
0x1400603a6  jmp     loc_140060129
0x1400603ab  mov     edx, 49576C55h; Tag
0x1400603b0  mov     rcx, rbx; Object
0x1400603b3  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400603ba  nop     dword ptr [rax+rax+00h]
0x1400603bf  jmp     loc_140060176
0x1400603c4  mov     rcx, [rsp+78h+arg_8]
0x1400603cc  xor     r8d, r8d; Wait
0x1400603cf  add     rcx, 20h ; ' '; Event
0x1400603d3  xor     edx, edx; Increment
0x1400603d5  call    cs:__imp_KeSetEvent
0x1400603dc  nop     dword ptr [rax+rax+00h]
0x1400603e1  jmp     loc_1400601A2
0x1400603e6  call    cs:__imp_KeGetCurrentIrql
0x1400603ed  nop     dword ptr [rax+rax+00h]
0x1400603f2  test    al, al
0x1400603f4  jnz     loc_140177A94
0x1400603fa  jmp     loc_1400601AF
0x1400603ff  mov     eax, [r15]
0x140060402  mov     edx, 11h
0x140060407  mov     r9d, [rsi+8]
0x14006040b  mov     ecx, 518h
0x140060410  mov     [rsp+78h+var_50], eax
0x140060414  mov     eax, [r14+8]
0x140060418  mov     dword ptr [rsp+78h+Timeout], eax
0x14006041c  call    WPP_SF_ddL
0x140060421  jmp     loc_1400601E8
0x140060426  call    cs:__imp_KeGetCurrentIrql
0x14006042d  nop     dword ptr [rax+rax+00h]
0x140060432  test    al, al
0x140060434  jz      loc_1400602C9
0x14006043a  jmp     loc_140177A7A
0x14006043f  call    cs:__imp_KeGetCurrentIrql
0x140060446  nop     dword ptr [rax+rax+00h]
0x14006044b  test    al, al
0x14006044d  jnz     loc_140177A94
0x140060453  jmp     loc_14006034A
0x140177a7a  mov     r9d, 549h; BugCheckParameter4
0x140177a80  lea     r8, aMinioHttpSysTh; "minio\\http\\sys\\thrdpool.c"
0x140177a87  xor     edx, edx; BugCheckParameter2
0x140177a89  mov     ecx, 4; BugCheckParameter1
0x140177a8e  call    UlBugCheckEx
0x140177a94  mov     r9d, 579h; BugCheckParameter4
0x140177a9a  lea     r8, aMinioHttpSysTh; "minio\\http\\sys\\thrdpool.c"
0x140177aa1  xor     edx, edx; BugCheckParameter2
0x140177aa3  mov     ecx, 4; BugCheckParameter1
0x140177aa8  call    UlBugCheckEx
```
