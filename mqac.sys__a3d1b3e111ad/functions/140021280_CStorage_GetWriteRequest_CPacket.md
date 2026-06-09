# CStorage::GetWriteRequest(CPacket *)

- ea: `0x140021280`
- end: `0x1400213f1`
- name: `?GetWriteRequest@CStorage@@QEAAPEAU_IRP@@PEAVCPacket@@@Z`
- size: `369`
- prototype: `struct _IRP *__fastcall(CStorage *__hidden this, struct CPacket *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140014c48`

## callees

- `0x140001c04`
- `0x140003d84`
- `0x1400126bc`
- `0x140021280`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400213ca`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400213ca`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400212a1`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400212a1`

## pseudocode

```c
struct _IRP *__fastcall CStorage::GetWriteRequest(CStorage **this, struct CPacket *a2)
{
  PDEVICE_OBJECT v4; // rcx
  CStorage *i; // rsi
  char *v6; // rbx
  struct _DEVICE_OBJECT **v7; // r14
  struct _DEVICE_OBJECT *j; // rdi
  struct _DEVICE_OBJECT *v9; // rax
  struct _DEVICE_OBJECT *v10; // r9
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  IoAcquireCancelSpinLock(&Irql);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 11, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids, a2);
  }
  for ( i = *this; ; i = *(CStorage **)i )
  {
    v6 = 0;
    if ( this != (CStorage **)i )
      v6 = (char *)i - 168;
    if ( !v6 )
      break;
    if ( (*((_DWORD *)v6 + 36) & 0x80) != 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 12, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids);
      }
      v7 = (struct _DEVICE_OBJECT **)*((_QWORD *)v6 + 7);
      for ( j = *v7; ; j = *(struct _DEVICE_OBJECT **)&j->Type )
      {
        v9 = 0;
        if ( v7 != (struct _DEVICE_OBJECT **)j )
          v9 = j;
        if ( !v9 )
          break;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
        {
          v10 = j;
          if ( v7 == (struct _DEVICE_OBJECT **)j )
            v10 = 0;
          WPP_SF_q(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            13,
            WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids,
            v10->NextDevice);
        }
        v4 = j;
        if ( v7 == (struct _DEVICE_OBJECT **)j )
          v4 = 0;
        if ( (struct CPacket *)v4->NextDevice == a2 )
        {
          _InterlockedExchange64((volatile __int64 *)v6 + 13, 0);
          XList<_IRP,168>::remove(v4, v6);
          *(_BYTE *)(*((_QWORD *)v6 + 7) + 24LL) = 0;
          goto LABEL_29;
        }
      }
    }
    else if ( *((struct CPacket **)v6 + 7) == a2 )
    {
      _InterlockedExchange64((volatile __int64 *)v6 + 13, 0);
      XList<_IRP,168>::remove(v4, v6);
      break;
    }
  }
LABEL_29:
  IoReleaseCancelSpinLock(Irql);
  return (struct _IRP *)v6;
}

```

## disassembly

```asm
0x140021280  mov     [rsp+arg_8], rbx
0x140021285  mov     [rsp+arg_10], rbp
0x14002128a  push    rsi
0x14002128b  push    rdi
0x14002128c  push    r13
0x14002128e  push    r14
0x140021290  push    r15
0x140021292  sub     rsp, 20h
0x140021296  mov     r15, rcx
0x140021299  mov     rbp, rdx
0x14002129c  lea     rcx, [rsp+48h+Irql]; Irql
0x1400212a1  call    cs:__imp_IoAcquireCancelSpinLock
0x1400212a8  nop     dword ptr [rax+rax+00h]
0x1400212ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212b4  lea     r13, WPP_GLOBAL_Control
0x1400212bb  cmp     rcx, r13
0x1400212be  jz      short loc_1400212DF
0x1400212c0  mov     eax, [rcx+6Ch]
0x1400212c3  test    al, 4
0x1400212c5  jz      short loc_1400212DF
0x1400212c7  mov     rcx, [rcx+58h]
0x1400212cb  lea     r8, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids
0x1400212d2  mov     edx, 0Bh
0x1400212d7  mov     r9, rbp
0x1400212da  call    WPP_SF_q
0x1400212df  mov     rsi, [r15]
0x1400212e2  xor     ebx, ebx
0x1400212e4  lea     rax, [rsi-0A8h]
0x1400212eb  cmp     r15, rsi
0x1400212ee  cmovnz  rbx, rax
0x1400212f2  test    rbx, rbx
0x1400212f5  jz      loc_1400213C6
0x1400212fb  mov     eax, [rbx+90h]
0x140021301  shr     eax, 7
0x140021304  test    al, 1
0x140021306  jnz     short loc_140021317
0x140021308  cmp     [rbx+38h], rbp
0x14002130c  jz      loc_1400213A1
0x140021312  mov     rsi, [rsi]
0x140021315  jmp     short loc_1400212E2
0x140021317  mov     rcx, cs:WPP_GLOBAL_Control
0x14002131e  cmp     rcx, r13
0x140021321  jz      short loc_14002133F
0x140021323  mov     eax, [rcx+6Ch]
0x140021326  test    al, 4
0x140021328  jz      short loc_14002133F
0x14002132a  mov     rcx, [rcx+58h]
0x14002132e  lea     r8, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids
0x140021335  mov     edx, 0Ch
0x14002133a  call    WPP_SF_
0x14002133f  mov     r14, [rbx+38h]
0x140021343  mov     rdi, [r14]
0x140021346  xor     eax, eax
0x140021348  cmp     r14, rdi
0x14002134b  cmovnz  rax, rdi
0x14002134f  test    rax, rax
0x140021352  jz      short loc_140021312
0x140021354  mov     rcx, cs:WPP_GLOBAL_Control
0x14002135b  cmp     rcx, r13
0x14002135e  jz      short loc_14002138A
0x140021360  mov     eax, [rcx+6Ch]
0x140021363  test    al, 4
0x140021365  jz      short loc_14002138A
0x140021367  mov     rcx, [rcx+58h]
0x14002136b  lea     r8, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids
0x140021372  xor     eax, eax
0x140021374  mov     r9, rdi
0x140021377  cmp     r14, rdi
0x14002137a  cmovz   r9, rax
0x14002137e  lea     edx, [rax+0Dh]
0x140021381  mov     r9, [r9+10h]
0x140021385  call    WPP_SF_q
0x14002138a  xor     eax, eax
0x14002138c  mov     rcx, rdi
0x14002138f  cmp     r14, rdi
0x140021392  cmovz   rcx, rax
0x140021396  cmp     [rcx+10h], rbp
0x14002139a  jz      short loc_1400213B1
0x14002139c  mov     rdi, [rdi]
0x14002139f  jmp     short loc_140021346
0x1400213a1  xor     eax, eax
0x1400213a3  mov     rdx, rbx
0x1400213a6  xchg    rax, [rbx+68h]
0x1400213aa  call    ?remove@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::remove(_IRP *)
0x1400213af  jmp     short loc_1400213C6
0x1400213b1  xchg    rax, [rbx+68h]
0x1400213b5  mov     rdx, rbx
0x1400213b8  call    ?remove@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::remove(_IRP *)
0x1400213bd  mov     r8, [rbx+38h]
0x1400213c1  mov     byte ptr [r8+18h], 0
0x1400213c6  mov     cl, [rsp+48h+Irql]; Irql
0x1400213ca  call    cs:__imp_IoReleaseCancelSpinLock
0x1400213d1  nop     dword ptr [rax+rax+00h]
0x1400213d6  mov     rbp, [rsp+48h+arg_10]
0x1400213db  mov     rax, rbx
0x1400213de  mov     rbx, [rsp+48h+arg_8]
0x1400213e3  add     rsp, 20h
0x1400213e7  pop     r15
0x1400213e9  pop     r14
0x1400213eb  pop     r13
0x1400213ed  pop     rdi
0x1400213ee  pop     rsi
0x1400213ef  retn
```
