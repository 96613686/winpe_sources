# CScheduler::RemoveEntry(SCHED_LIST_HEAD *,void *)

- ea: `0x14002054c`
- end: `0x140020651`
- name: `?RemoveEntry@CScheduler@@AEAAHPEAUSCHED_LIST_HEAD@@PEAX@Z`
- size: `261`
- prototype: `int(CScheduler *__hidden this, struct SCHED_LIST_HEAD *, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400207bc`
- `0x140020894`

## callees

- `0x1400010a4`
- `0x1400033f0`
- `0x14002054c`
- `0x140020c6c`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140020636`
- `ntoskrnl!KeSetTimer` at `0x140020636`
- `ntoskrnl!KeCancelTimer` at `0x14002060a`
- `ntoskrnl!KeCancelTimer` at `0x14002060a`

## pseudocode

```c
__int64 __fastcall CScheduler::RemoveEntry(CScheduler *this, struct SCHED_LIST_HEAD *a2, void *a3)
{
  _QWORD *v5; // rax
  _QWORD **i; // rdx
  _QWORD *v7; // rcx
  __int64 v9; // rbx
  struct _KTIMER *v10; // rcx
  bool v11; // zf
  LARGE_INTEGER v12; // rdx
  void *v13; // [rsp+58h] [rbp+10h] BYREF

  v13 = a2;
  if ( *((void **)a2 + 1) == a3 )
  {
    v7 = (_QWORD *)*((_QWORD *)a2 + 2);
    if ( !v7 )
    {
      v9 = *(_QWORD *)a2;
      CAVLTree::DelNode((CScheduler *)((char *)this + 8), a2);
      operator delete(a2);
      if ( v9 == *((_QWORD *)this + 8) )
      {
        if ( CSortQ::PeekHead((CScheduler *)((char *)this + 8), &v13, 0) )
        {
          v11 = *((_DWORD *)this + 20) == 0;
          v12 = *(LARGE_INTEGER *)v13;
          *((_QWORD *)this + 8) = *(_QWORD *)v13;
          if ( v11 )
            KeSetTimer((PKTIMER)(*((_QWORD *)this + 7) + 16LL), v12, (PKDPC)(*((_QWORD *)this + 7) + 80LL));
        }
        else
        {
          v10 = (struct _KTIMER *)(*((_QWORD *)this + 7) + 16LL);
          *((_QWORD *)this + 8) = 0;
          KeCancelTimer(v10);
        }
      }
      return 1;
    }
    *((_QWORD *)a2 + 2) = v7[1];
    *((_QWORD *)a2 + 1) = *v7;
    if ( *((_QWORD **)a2 + 3) == v7 )
      *((_QWORD *)a2 + 3) = 0;
  }
  else
  {
    v5 = 0;
    for ( i = (_QWORD **)((char *)a2 + 16); ; i = (_QWORD **)(v7 + 1) )
    {
      v7 = *i;
      if ( !*i )
        return 0;
      if ( (void *)*v7 == a3 )
        break;
      v5 = *i;
    }
    if ( *((_QWORD **)a2 + 3) == v7 )
      *((_QWORD *)a2 + 3) = v5;
    *i = (_QWORD *)v7[1];
  }
  operator delete(v7);
  return 1;
}

```

## disassembly

```asm
0x14002054c  mov     [rsp+arg_8], rdx
0x140020551  push    rbx
0x140020552  push    rbp
0x140020553  push    rsi
0x140020554  push    rdi
0x140020555  sub     rsp, 28h
0x140020559  mov     rdi, rdx
0x14002055c  mov     rsi, rcx
0x14002055f  cmp     [rdx+8], r8
0x140020563  jz      short loc_1400205A3
0x140020565  xor     eax, eax
0x140020567  add     rdx, 10h
0x14002056b  mov     rcx, [rdx]; void *
0x14002056e  test    rcx, rcx
0x140020571  jz      short loc_14002059C
0x140020573  cmp     [rcx], r8
0x140020576  jz      short loc_140020581
0x140020578  mov     rax, rcx
0x14002057b  lea     rdx, [rcx+8]
0x14002057f  jmp     short loc_14002056B
0x140020581  cmp     [rdi+18h], rcx
0x140020585  jnz     short loc_14002058B
0x140020587  mov     [rdi+18h], rax
0x14002058b  mov     rax, [rcx+8]
0x14002058f  mov     [rdx], rax
0x140020592  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140020597  jmp     loc_140020642
0x14002059c  xor     eax, eax
0x14002059e  jmp     loc_140020647
0x1400205a3  mov     rcx, [rdx+10h]
0x1400205a7  test    rcx, rcx
0x1400205aa  jz      short loc_1400205CB
0x1400205ac  mov     rax, [rcx+8]
0x1400205b0  mov     [rdx+10h], rax
0x1400205b4  mov     rax, [rcx]
0x1400205b7  mov     [rdx+8], rax
0x1400205bb  cmp     [rdx+18h], rcx
0x1400205bf  jnz     short loc_140020592
0x1400205c1  mov     qword ptr [rdx+18h], 0
0x1400205c9  jmp     short loc_140020592
0x1400205cb  mov     rbx, [rdx]
0x1400205ce  lea     rcx, [rsi+8]; this
0x1400205d2  call    ?DelNode@CAVLTree@@QEAAXPEAX@Z; CAVLTree::DelNode(void *)
0x1400205d7  mov     rcx, rdi; void *
0x1400205da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400205df  cmp     rbx, [rsi+40h]
0x1400205e3  jnz     short loc_140020642
0x1400205e5  xor     r8d, r8d; struct CAVLTreeCursor *
0x1400205e8  lea     rdx, [rsp+48h+arg_8]; void **
0x1400205ed  lea     rcx, [rsi+8]; this
0x1400205f1  call    ?PeekHead@CSortQ@@QEAAHPEAPEAXPEAVCAVLTreeCursor@@@Z; CSortQ::PeekHead(void * *,CAVLTreeCursor *)
0x1400205f6  test    eax, eax
0x1400205f8  jnz     short loc_140020618
0x1400205fa  mov     rcx, [rsi+38h]
0x1400205fe  add     rcx, 10h; PKTIMER
0x140020602  mov     qword ptr [rsi+40h], 0
0x14002060a  call    cs:__imp_KeCancelTimer
0x140020611  nop     dword ptr [rax+rax+00h]
0x140020616  jmp     short loc_140020642
0x140020618  cmp     dword ptr [rsi+50h], 0
0x14002061c  mov     rax, [rsp+48h+arg_8]
0x140020621  mov     rdx, [rax]; DueTime
0x140020624  mov     [rsi+40h], rdx
0x140020628  jnz     short loc_140020642
0x14002062a  mov     rcx, [rsi+38h]
0x14002062e  lea     r8, [rcx+50h]; Dpc
0x140020632  add     rcx, 10h; Timer
0x140020636  call    cs:__imp_KeSetTimer
0x14002063d  nop     dword ptr [rax+rax+00h]
0x140020642  mov     eax, 1
0x140020647  add     rsp, 28h
0x14002064b  pop     rdi
0x14002064c  pop     rsi
0x14002064d  pop     rbp
0x14002064e  pop     rbx
0x14002064f  retn
```
