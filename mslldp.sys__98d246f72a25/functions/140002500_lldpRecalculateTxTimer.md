# lldpRecalculateTxTimer

- ea: `0x140002500`
- end: `0x1400025d1`
- name: `lldpRecalculateTxTimer`
- size: `209`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001f00`
- `0x1400022c0`
- `0x140003590`

## callees

- `0x140002500`
- `0x1400025d8`
- `0x140003f20`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14000254b`
- `ntoskrnl!KeCancelTimer` at `0x14000254b`

## pseudocode

```c
void __fastcall lldpRecalculateTxTimer(_DWORD *a1, char a2)
{
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  int v8; // ecx
  int v9; // ecx
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  __int64 v12; // rcx
  unsigned int v13; // edx

  _m_prefetchw(a1 + 13);
  v4 = a1[13];
  do
  {
    v5 = v4;
    v4 = _InterlockedCompareExchange(a1 + 13, v4, v4);
  }
  while ( v5 != v4 );
  if ( (unsigned int)(v4 - 4) > 1 )
    goto LABEL_7;
  _m_prefetchw(a1 + 76);
  v6 = a1[76];
  do
  {
    v7 = v6;
    v6 = _InterlockedCompareExchange(a1 + 76, v6, v6);
  }
  while ( v7 != v6 );
  if ( v6 || (v8 = a1[62]) == 0 || (v9 = v8 - 1) != 0 && v9 != 2 )
  {
LABEL_7:
    KeCancelTimer((PKTIMER)(a1 + 146));
    if ( _InterlockedExchange(a1 + 215, 0) )
      lldpTxSendShutdownPacket((__int64)a1);
  }
  else
  {
    _m_prefetchw(a1 + 219);
    v10 = a1[219];
    do
    {
      v11 = v10;
      v10 = _InterlockedCompareExchange(a1 + 219, v10, v10);
    }
    while ( v11 != v10 );
    v12 = 64;
    if ( v10 )
      v12 = 67;
    v13 = a1[v12];
    _InterlockedExchange(a1 + 215, 1);
    lldpSetPeriodicTimer((PKTIMER)(a1 + 146), v13, a2);
  }
}

```

## disassembly

```asm
0x140002500  push    rbx
0x140002502  sub     rsp, 20h
0x140002506  movzx   r8d, dl
0x14000250a  mov     rbx, rcx
0x14000250d  prefetchw byte ptr [rcx+34h]
0x140002511  mov     eax, [rcx+34h]
0x140002514  mov     ecx, eax
0x140002516  lock cmpxchg [rbx+34h], ecx
0x14000251b  jnz     short loc_140002514
0x14000251d  sub     eax, 4
0x140002520  jz      short loc_140002527
0x140002522  cmp     eax, 1
0x140002525  jnz     short loc_140002544
0x140002527  prefetchw byte ptr [rbx+130h]
0x14000252e  mov     eax, [rbx+130h]
0x140002534  mov     ecx, eax
0x140002536  lock cmpxchg [rbx+130h], ecx
0x14000253e  jnz     short loc_140002534
0x140002540  test    eax, eax
0x140002542  jz      short loc_14000256A
0x140002544  lea     rcx, [rbx+248h]; PKTIMER
0x14000254b  call    cs:__imp_KeCancelTimer
0x140002552  nop     dword ptr [rax+rax+00h]
0x140002557  xor     eax, eax
0x140002559  xchg    eax, [rbx+35Ch]
0x14000255f  test    eax, eax
0x140002561  jnz     short loc_1400025C7
0x140002563  add     rsp, 20h
0x140002567  pop     rbx
0x140002568  retn
0x14000256a  mov     ecx, [rbx+0F8h]
0x140002570  test    ecx, ecx
0x140002572  jz      short loc_140002544
0x140002574  sub     ecx, 1
0x140002577  jz      short loc_140002583
0x140002579  sub     ecx, 1
0x14000257c  jz      short loc_140002544
0x14000257e  cmp     ecx, 1
0x140002581  jnz     short loc_140002544
0x140002583  prefetchw byte ptr [rbx+36Ch]
0x14000258a  mov     eax, [rbx+36Ch]
0x140002590  mov     ecx, eax
0x140002592  lock cmpxchg [rbx+36Ch], ecx
0x14000259a  jnz     short loc_140002590
0x14000259c  test    eax, eax
0x14000259e  mov     edx, 10Ch
0x1400025a3  mov     eax, 1
0x1400025a8  mov     ecx, 100h
0x1400025ad  cmovnz  ecx, edx
0x1400025b0  mov     edx, [rcx+rbx]
0x1400025b3  lea     rcx, [rbx+248h]; Timer
0x1400025ba  xchg    eax, [rbx+35Ch]
0x1400025c0  call    lldpSetPeriodicTimer
0x1400025c5  jmp     short loc_140002563
0x1400025c7  mov     rcx, rbx
0x1400025ca  call    lldpTxSendShutdownPacket
0x1400025cf  jmp     short loc_140002563
```
