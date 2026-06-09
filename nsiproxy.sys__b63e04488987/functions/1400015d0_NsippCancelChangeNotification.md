# NsippCancelChangeNotification

- ea: `0x1400015d0`
- end: `0x140001873`
- name: `NsippCancelChangeNotification`
- size: `675`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x1400015d0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001697`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001697`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000170c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000170c`
- `ntoskrnl!IoIs32bitProcess` at `0x1400015f9`
- `ntoskrnl!IoIs32bitProcess` at `0x1400015f9`
- `ntoskrnl!IofCompleteRequest` at `0x14000178f`
- `ntoskrnl!IofCompleteRequest` at `0x14000178f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000174e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001777`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000174e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001777`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000173a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001763`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000173a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001763`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001665`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001665`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001652`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140001652`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001830`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001830`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x14000181d`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x14000181d`

## pseudocode

```c
__int64 __fastcall NsippCancelChangeNotification(unsigned int *a1, unsigned int a2)
{
  BOOLEAN v4; // al
  __int64 v5; // rsi
  KSPIN_LOCK *v6; // rbp
  _QWORD *v7; // rdi
  char v8; // r12
  KSPIN_LOCK *i; // r15
  _QWORD *v10; // r14
  KIRQL v11; // al
  _QWORD *v12; // rbx
  KIRQL v13; // cl
  _QWORD *v14; // rdx
  _QWORD *v15; // rax
  unsigned int v16; // ebx
  _QWORD *v18; // rax
  PVOID *v19; // rdx
  __int128 v20; // [rsp+20h] [rbp-58h] BYREF
  __int128 v21; // [rsp+30h] [rbp-48h]
  int v22; // [rsp+40h] [rbp-38h]
  KIRQL Irql; // [rsp+90h] [rbp+18h] BYREF

  Irql = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  v4 = IoIs32bitProcess(0);
  if ( !a1 )
    return 3221225485LL;
  if ( v4 )
  {
    if ( a2 >= 4 )
    {
      v5 = *a1;
      goto LABEL_5;
    }
    return 3221225485LL;
  }
  if ( a2 < 8 )
    return 3221225485LL;
  v5 = *(_QWORD *)a1;
LABEL_5:
  v6 = 0;
  v7 = 0;
  v8 = 0;
  IoAcquireCancelSpinLock(&Irql);
  KeAcquireSpinLockAtDpcLevel(&NsippNotificationHandleListLock);
  for ( i = (KSPIN_LOCK *)NsippNotificationHandleList; ; i = (KSPIN_LOCK *)*i )
  {
    if ( i == (KSPIN_LOCK *)&NsippNotificationHandleList )
      goto LABEL_20;
    v7 = 0;
    v10 = i + 12;
    v11 = KeAcquireSpinLockRaiseToDpc(i + 11);
    v12 = (_QWORD *)i[12];
    v13 = v11;
    while ( 1 )
    {
      if ( v12 == v10 )
        goto LABEL_15;
      v7 = v12 - 21;
      if ( v5 )
      {
        if ( v7[12] == v5 )
          break;
      }
      v12 = (_QWORD *)*v12;
    }
    *((_DWORD *)v7 + 12) = -1073741536;
    v7[7] = 0;
    _InterlockedExchange64(v7 + 13, 0);
    v14 = (_QWORD *)*v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 )
      goto LABEL_34;
    v15 = (_QWORD *)v12[1];
    if ( (_QWORD *)*v15 != v12 )
      goto LABEL_34;
    *v15 = v14;
    v14[1] = v15;
LABEL_15:
    v6 = i;
    KeReleaseSpinLock(i + 11, v13);
    if ( v12 == v10 )
      v7 = 0;
    if ( v7 )
      break;
  }
  if ( (_QWORD *)*v10 != v10 )
    goto LABEL_19;
  if ( !*((_DWORD *)i + 4) )
  {
    v18 = (_QWORD *)*i;
    if ( *(KSPIN_LOCK **)(*i + 8) != i || (v19 = (PVOID *)i[1], *v19 != i) )
LABEL_34:
      __fastfail(3u);
    *v19 = v18;
    v8 = 1;
    v18[1] = v19;
LABEL_19:
    KeReleaseSpinLockFromDpcLevel(&NsippNotificationHandleListLock);
    IoReleaseCancelSpinLock(Irql);
LABEL_21:
    v16 = 0;
    IofCompleteRequest((PIRP)v7, 0);
    goto LABEL_22;
  }
LABEL_20:
  KeReleaseSpinLockFromDpcLevel(&NsippNotificationHandleListLock);
  IoReleaseCancelSpinLock(Irql);
  if ( v7 )
    goto LABEL_21;
  v16 = -1073741275;
LABEL_22:
  if ( v8 == 1 )
  {
    v20 = *(_OWORD *)(v6 + 3);
    v21 = *(_OWORD *)(v6 + 5);
    v16 = NsiDeregisterChangeNotificationEx(&v20);
    ExFreePoolWithTag(v6, 0);
  }
  return v16;
}

```

## disassembly

```asm
0x1400015d0  push    rbx
0x1400015d2  push    rsi
0x1400015d3  sub     rsp, 68h
0x1400015d7  xorps   xmm0, xmm0
0x1400015da  mov     [rsp+78h+Irql], 0
0x1400015e2  mov     rsi, rcx
0x1400015e5  xor     eax, eax
0x1400015e7  xor     ecx, ecx; Irp
0x1400015e9  mov     [rsp+78h+var_38], eax
0x1400015ed  movups  [rsp+78h+var_58], xmm0
0x1400015f2  mov     ebx, edx
0x1400015f4  movups  [rsp+78h+var_48], xmm0
0x1400015f9  call    cs:__imp_IoIs32bitProcess
0x140001600  nop     dword ptr [rax+rax+00h]
0x140001605  test    rsi, rsi
0x140001608  jz      loc_1400017DA
0x14000160e  test    al, al
0x140001610  jz      loc_1400017E7
0x140001616  cmp     ebx, 4
0x140001619  jb      loc_1400017DA
0x14000161f  mov     esi, [rsi]
0x140001621  mov     [rsp+78h+arg_0], rbp
0x140001629  lea     rcx, [rsp+78h+Irql]; Irql
0x140001631  mov     [rsp+78h+arg_8], rdi
0x140001639  xor     ebp, ebp
0x14000163b  mov     [rsp+78h+arg_18], r12
0x140001643  xor     edi, edi
0x140001645  mov     [rsp+78h+var_20], r14
0x14000164a  xor     r12b, r12b
0x14000164d  mov     [rsp+78h+var_28], r15
0x140001652  call    cs:__imp_IoAcquireCancelSpinLock
0x140001659  nop     dword ptr [rax+rax+00h]
0x14000165e  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x140001665  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000166c  nop     dword ptr [rax+rax+00h]
0x140001671  mov     r15, cs:NsippNotificationHandleList
0x140001678  mov     [rsp+78h+var_18], r13
0x14000167d  lea     rax, NsippNotificationHandleList
0x140001684  cmp     r15, rax
0x140001687  jz      loc_14000175C
0x14000168d  xor     edi, edi
0x14000168f  lea     rcx, [r15+58h]; SpinLock
0x140001693  lea     r14, [r15+60h]
0x140001697  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000169e  nop     dword ptr [rax+rax+00h]
0x1400016a3  mov     rbx, [r14]
0x1400016a6  movzx   ecx, al
0x1400016a9  nop     dword ptr [rax+00000000h]
0x1400016b0  cmp     rbx, r14
0x1400016b3  jz      short loc_140001702
0x1400016b5  lea     rdi, [rbx-0A8h]
0x1400016bc  test    rsi, rsi
0x1400016bf  jz      short loc_1400016C7
0x1400016c1  cmp     [rdi+60h], rsi
0x1400016c5  jz      short loc_1400016CC
0x1400016c7  mov     rbx, [rbx]
0x1400016ca  jmp     short loc_1400016B0
0x1400016cc  mov     dword ptr [rdi+30h], 0C0000120h
0x1400016d3  xor     eax, eax
0x1400016d5  mov     qword ptr [rdi+38h], 0
0x1400016dd  xchg    rax, [rdi+68h]
0x1400016e1  mov     rdx, [rbx]
0x1400016e4  cmp     [rdx+8], rbx
0x1400016e8  jnz     loc_14000186C
0x1400016ee  mov     rax, [rbx+8]
0x1400016f2  cmp     [rax], rbx
0x1400016f5  jnz     loc_14000186C
0x1400016fb  mov     [rax], rdx
0x1400016fe  mov     [rdx+8], rax
0x140001702  movzx   edx, cl; NewIrql
0x140001705  mov     rbp, r15
0x140001708  lea     rcx, [r15+58h]; SpinLock
0x14000170c  call    cs:__imp_KeReleaseSpinLock
0x140001713  nop     dword ptr [rax+rax+00h]
0x140001718  xor     eax, eax
0x14000171a  cmp     rbx, r14
0x14000171d  cmovz   rdi, rax
0x140001721  test    rdi, rdi
0x140001724  jz      loc_1400017D2
0x14000172a  cmp     [r14], r14
0x14000172d  jz      loc_140001841
0x140001733  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x14000173a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140001741  nop     dword ptr [rax+rax+00h]
0x140001746  movzx   ecx, [rsp+78h+Irql]; Irql
0x14000174e  call    cs:__imp_IoReleaseCancelSpinLock
0x140001755  nop     dword ptr [rax+rax+00h]
0x14000175a  jmp     short loc_140001788
0x14000175c  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x140001763  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000176a  nop     dword ptr [rax+rax+00h]
0x14000176f  movzx   ecx, [rsp+78h+Irql]; Irql
0x140001777  call    cs:__imp_IoReleaseCancelSpinLock
0x14000177e  nop     dword ptr [rax+rax+00h]
0x140001783  test    rdi, rdi
0x140001786  jz      short loc_1400017F4
0x140001788  xor     ebx, ebx
0x14000178a  xor     edx, edx; PriorityBoost
0x14000178c  mov     rcx, rdi; Irp
0x14000178f  call    cs:__imp_IofCompleteRequest
0x140001796  nop     dword ptr [rax+rax+00h]
0x14000179b  cmp     r12b, 1
0x14000179f  jz      short loc_1400017FB
0x1400017a1  mov     r13, [rsp+78h+var_18]
0x1400017a6  mov     eax, ebx
0x1400017a8  mov     r14, [rsp+78h+var_20]
0x1400017ad  mov     r12, [rsp+78h+arg_18]
0x1400017b5  mov     rdi, [rsp+78h+arg_8]
0x1400017bd  mov     rbp, [rsp+78h+arg_0]
0x1400017c5  mov     r15, [rsp+78h+var_28]
0x1400017ca  add     rsp, 68h
0x1400017ce  pop     rsi
0x1400017cf  pop     rbx
0x1400017d0  retn
0x1400017d2  mov     r15, [r15]
0x1400017d5  jmp     loc_14000167D
0x1400017da  mov     eax, 0C000000Dh
0x1400017df  add     rsp, 68h
0x1400017e3  pop     rsi
0x1400017e4  pop     rbx
0x1400017e5  retn
0x1400017e7  cmp     ebx, 8
0x1400017ea  jb      short loc_1400017DA
0x1400017ec  mov     rsi, [rsi]
0x1400017ef  jmp     loc_140001621
0x1400017f4  mov     ebx, 0C0000225h
0x1400017f9  jmp     short loc_14000179B
0x1400017fb  movups  xmm0, xmmword ptr [rbp+18h]
0x1400017ff  lea     rcx, [rsp+78h+var_58]
0x140001804  movups  [rsp+78h+var_58], xmm0
0x140001809  movsd   xmm1, qword ptr [rbp+28h]
0x14000180e  movsd   qword ptr [rsp+78h+var_48], xmm1
0x140001814  mov     rax, [rbp+30h]
0x140001818  mov     qword ptr [rsp+78h+var_48+8], rax
0x14000181d  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x140001824  nop     dword ptr [rax+rax+00h]
0x140001829  xor     edx, edx; Tag
0x14000182b  mov     rcx, rbp; P
0x14000182e  mov     ebx, eax
0x140001830  call    cs:__imp_ExFreePoolWithTag
0x140001837  nop     dword ptr [rax+rax+00h]
0x14000183c  jmp     loc_1400017A1
0x140001841  cmp     [r15+10h], eax
0x140001845  jnz     loc_14000175C
0x14000184b  mov     rax, [r15]
0x14000184e  cmp     [rax+8], r15
0x140001852  jnz     short loc_14000186C
0x140001854  mov     rdx, [r15+8]
0x140001858  cmp     [rdx], r15
0x14000185b  jnz     short loc_14000186C
0x14000185d  mov     [rdx], rax
0x140001860  mov     r12b, 1
0x140001863  mov     [rax+8], rdx
0x140001867  jmp     loc_140001733
0x14000186c  mov     ecx, 3
0x140001871  int     29h; Win8: RtlFailFast(ecx)
```
