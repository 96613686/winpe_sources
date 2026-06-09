# CQMInterface::TakeOpenQueueRequest(_GUID const &,CACOpenQueueRequest * *)

- ea: `0x14001b384`
- end: `0x14001b4db`
- name: `?TakeOpenQueueRequest@CQMInterface@@QEAAJAEBU_GUID@@PEAPEAVCACOpenQueueRequest@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(CQMInterface *__hidden this, const struct _GUID *, struct CACOpenQueueRequest **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004314`
- `0x140004d64`

## callees

- `0x140001c04`
- `0x140003d84`
- `0x14001b384`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b434`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b4c1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b434`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b4c1`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001b3a1`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001b3a1`

## pseudocode

```c
__int64 __fastcall CQMInterface::TakeOpenQueueRequest(
        CQMInterface *this,
        const struct _GUID *a2,
        struct CACOpenQueueRequest **a3)
{
  struct CACOpenQueueRequest **v6; // rbx
  struct CACOpenQueueRequest *i; // rcx
  struct CACOpenQueueRequest *v8; // rax
  struct CACOpenQueueRequest *v9; // r8
  __int64 v10; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  IoAcquireCancelSpinLock(&Irql);
  v6 = (struct CACOpenQueueRequest **)((char *)this + 72);
  *a3 = 0;
  for ( i = *v6; ; i = *(struct CACOpenQueueRequest **)i )
  {
    v8 = 0;
    if ( v6 != (struct CACOpenQueueRequest **)i )
      v8 = i;
    if ( !v8 )
      break;
    v9 = i;
    if ( v6 == (struct CACOpenQueueRequest **)i )
      v9 = 0;
    v10 = *((_QWORD *)v9 + 4) - *(_QWORD *)&a2->Data1;
    if ( !v10 )
      v10 = *((_QWORD *)v9 + 5) - *(_QWORD *)a2->Data4;
    if ( !v10 )
    {
      if ( v6 == (struct CACOpenQueueRequest **)i )
        i = 0;
      *a3 = i;
      break;
    }
  }
  if ( *a3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 24, &WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids, *a3);
    }
    v12 = *a3;
    v13 = *(_QWORD *)*a3;
    if ( *(struct CACOpenQueueRequest **)(v13 + 8) != *a3 || (v14 = (_QWORD *)v12[1], (_QWORD *)*v14 != v12) )
      __fastfail(3u);
    *v14 = v13;
    *(_QWORD *)(v13 + 8) = v14;
    *v12 = 0;
    v12[1] = 0;
    _InterlockedExchange64((volatile __int64 *)(*((_QWORD *)*a3 + 2) + 104LL), 0);
    IoReleaseCancelSpinLock(Irql);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 23, &WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids);
    }
    IoReleaseCancelSpinLock(Irql);
    return 3221225488LL;
  }
}

```

## disassembly

```asm
0x14001b384  mov     [rsp+arg_8], rbx
0x14001b389  mov     [rsp+arg_10], rsi
0x14001b38e  push    rdi
0x14001b38f  sub     rsp, 20h
0x14001b393  mov     rbx, rcx
0x14001b396  mov     rdi, r8
0x14001b399  lea     rcx, [rsp+28h+Irql]; Irql
0x14001b39e  mov     rsi, rdx
0x14001b3a1  call    cs:__imp_IoAcquireCancelSpinLock
0x14001b3a8  nop     dword ptr [rax+rax+00h]
0x14001b3ad  add     rbx, 48h ; 'H'
0x14001b3b1  mov     qword ptr [rdi], 0
0x14001b3b8  mov     rcx, [rbx]
0x14001b3bb  xor     eax, eax
0x14001b3bd  cmp     rbx, rcx
0x14001b3c0  cmovnz  rax, rcx
0x14001b3c4  test    rax, rax
0x14001b3c7  jz      short loc_14001B3FA
0x14001b3c9  xor     eax, eax
0x14001b3cb  mov     r8, rcx
0x14001b3ce  cmp     rbx, rcx
0x14001b3d1  cmovz   r8, rax
0x14001b3d5  mov     rdx, [r8+20h]
0x14001b3d9  sub     rdx, [rsi]
0x14001b3dc  jnz     short loc_14001B3E6
0x14001b3de  mov     rdx, [r8+28h]
0x14001b3e2  sub     rdx, [rsi+8]
0x14001b3e6  test    rdx, rdx
0x14001b3e9  jz      short loc_14001B3F0
0x14001b3eb  mov     rcx, [rcx]
0x14001b3ee  jmp     short loc_14001B3BB
0x14001b3f0  cmp     rbx, rcx
0x14001b3f3  cmovz   rcx, rax
0x14001b3f7  mov     [rdi], rcx
0x14001b3fa  mov     r9, [rdi]
0x14001b3fd  test    r9, r9
0x14001b400  jnz     short loc_14001B456
0x14001b402  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b409  lea     rax, WPP_GLOBAL_Control
0x14001b410  cmp     rcx, rax
0x14001b413  jz      short loc_14001B430
0x14001b415  mov     eax, [rcx+6Ch]
0x14001b418  test    al, 1
0x14001b41a  jz      short loc_14001B430
0x14001b41c  mov     rcx, [rcx+58h]
0x14001b420  lea     edx, [r9+17h]
0x14001b424  lea     r8, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids
0x14001b42b  call    WPP_SF_
0x14001b430  mov     cl, [rsp+28h+Irql]; Irql
0x14001b434  call    cs:__imp_IoReleaseCancelSpinLock
0x14001b43b  nop     dword ptr [rax+rax+00h]
0x14001b440  mov     eax, 0C0000010h
0x14001b445  mov     rbx, [rsp+28h+arg_8]
0x14001b44a  mov     rsi, [rsp+28h+arg_10]
0x14001b44f  add     rsp, 20h
0x14001b453  pop     rdi
0x14001b454  retn
0x14001b456  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b45d  lea     rax, WPP_GLOBAL_Control
0x14001b464  cmp     rcx, rax
0x14001b467  jz      short loc_14001B485
0x14001b469  mov     eax, [rcx+6Ch]
0x14001b46c  test    al, 4
0x14001b46e  jz      short loc_14001B485
0x14001b470  mov     rcx, [rcx+58h]
0x14001b474  lea     r8, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids
0x14001b47b  mov     edx, 18h
0x14001b480  call    WPP_SF_q
0x14001b485  mov     rax, [rdi]
0x14001b488  mov     rcx, [rax]
0x14001b48b  cmp     [rcx+8], rax
0x14001b48f  jnz     short loc_14001B4D4
0x14001b491  mov     rdx, [rax+8]
0x14001b495  cmp     [rdx], rax
0x14001b498  jnz     short loc_14001B4D4
0x14001b49a  mov     [rdx], rcx
0x14001b49d  mov     [rcx+8], rdx
0x14001b4a1  mov     qword ptr [rax], 0
0x14001b4a8  mov     qword ptr [rax+8], 0
0x14001b4b0  mov     rax, [rdi]
0x14001b4b3  mov     rcx, [rax+10h]
0x14001b4b7  xor     eax, eax
0x14001b4b9  xchg    rax, [rcx+68h]
0x14001b4bd  mov     cl, [rsp+28h+Irql]; Irql
0x14001b4c1  call    cs:__imp_IoReleaseCancelSpinLock
0x14001b4c8  nop     dword ptr [rax+rax+00h]
0x14001b4cd  xor     eax, eax
0x14001b4cf  jmp     loc_14001B445
0x14001b4d4  mov     ecx, 3
0x14001b4d9  int     29h; Win8: RtlFailFast(ecx)
```
