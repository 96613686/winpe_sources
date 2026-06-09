# lldpEnableTxFastMode

- ea: `0x140002180`
- end: `0x1400022b8`
- name: `lldpEnableTxFastMode`
- size: `312`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001db0`
- `0x140002050`
- `0x140002fe0`
- `0x140010150`
- `0x1400114d0`
- `0x140011aa0`

## callees

- `0x140002180`
- `0x1400025d8`
- `0x140003f20`
- `0x140005ac0`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400021f4`
- `ntoskrnl!KeCancelTimer` at `0x1400021f4`

## pseudocode

```c
void __fastcall lldpEnableTxFastMode(__int64 a1)
{
  __int32 v1; // edi
  signed __int32 v3; // eax
  signed __int32 v4; // ett
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  int v7; // ecx
  int v8; // ecx
  signed __int32 v9; // eax
  signed __int32 v10; // ett

  v1 = *(_DWORD *)(a1 + 272);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_DDD(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids,
      HIWORD(*(_QWORD *)(a1 + 120)),
      (*(_QWORD *)(a1 + 120) >> 24) & 0xFFFFFF,
      v1);
  _InterlockedExchange((volatile __int32 *)(a1 + 876), v1);
  _m_prefetchw((const void *)(a1 + 52));
  v3 = *(_DWORD *)(a1 + 52);
  do
  {
    v4 = v3;
    v3 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 52), v3, v3);
  }
  while ( v4 != v3 );
  if ( (unsigned int)(v3 - 4) > 1 )
    goto LABEL_10;
  _m_prefetchw((const void *)(a1 + 304));
  v5 = *(_DWORD *)(a1 + 304);
  do
  {
    v6 = v5;
    v5 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 304), v5, v5);
  }
  while ( v6 != v5 );
  if ( v5 || (v7 = *(_DWORD *)(a1 + 248)) == 0 || (v8 = v7 - 1) != 0 && v8 != 2 )
  {
LABEL_10:
    KeCancelTimer((PKTIMER)(a1 + 584));
    if ( _InterlockedExchange((volatile __int32 *)(a1 + 860), 0) )
      lldpTxSendShutdownPacket(a1);
  }
  else
  {
    _m_prefetchw((const void *)(a1 + 876));
    v9 = *(_DWORD *)(a1 + 876);
    do
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 876), v9, v9);
    }
    while ( v10 != v9 );
    _InterlockedExchange((volatile __int32 *)(a1 + 860), 1);
    lldpSetPeriodicTimer((PKTIMER)(a1 + 584));
  }
}

```

## disassembly

```asm
0x140002180  mov     [rsp+arg_0], rbx
0x140002185  push    rdi
0x140002186  sub     rsp, 30h
0x14000218a  mov     edi, [rcx+110h]
0x140002190  mov     rbx, rcx
0x140002193  mov     rcx, cs:WPP_GLOBAL_Control
0x14000219a  lea     rax, WPP_GLOBAL_Control
0x1400021a1  cmp     rcx, rax
0x1400021a4  jz      short loc_1400021B0
0x1400021a6  cmp     byte ptr [rcx+29h], 4
0x1400021aa  jnb     loc_140002282
0x1400021b0  xchg    edi, [rbx+36Ch]
0x1400021b6  prefetchw byte ptr [rbx+34h]
0x1400021ba  mov     eax, [rbx+34h]
0x1400021bd  mov     ecx, eax
0x1400021bf  lock cmpxchg [rbx+34h], ecx
0x1400021c4  jnz     short loc_1400021BD
0x1400021c6  sub     eax, 4
0x1400021c9  jz      short loc_1400021D0
0x1400021cb  cmp     eax, 1
0x1400021ce  jnz     short loc_1400021ED
0x1400021d0  prefetchw byte ptr [rbx+130h]
0x1400021d7  mov     eax, [rbx+130h]
0x1400021dd  mov     ecx, eax
0x1400021df  lock cmpxchg [rbx+130h], ecx
0x1400021e7  jnz     short loc_1400021DD
0x1400021e9  test    eax, eax
0x1400021eb  jz      short loc_140002218
0x1400021ed  lea     rcx, [rbx+248h]; PKTIMER
0x1400021f4  call    cs:__imp_KeCancelTimer
0x1400021fb  nop     dword ptr [rax+rax+00h]
0x140002200  xor     eax, eax
0x140002202  xchg    eax, [rbx+35Ch]
0x140002208  test    eax, eax
0x14000220a  jnz     short loc_140002278
0x14000220c  mov     rbx, [rsp+38h+arg_0]
0x140002211  add     rsp, 30h
0x140002215  pop     rdi
0x140002216  retn
0x140002218  mov     ecx, [rbx+0F8h]
0x14000221e  test    ecx, ecx
0x140002220  jz      short loc_1400021ED
0x140002222  sub     ecx, 1
0x140002225  jz      short loc_140002231
0x140002227  sub     ecx, 1
0x14000222a  jz      short loc_1400021ED
0x14000222c  cmp     ecx, 1
0x14000222f  jnz     short loc_1400021ED
0x140002231  prefetchw byte ptr [rbx+36Ch]
0x140002238  mov     eax, [rbx+36Ch]
0x14000223e  mov     ecx, eax
0x140002240  lock cmpxchg [rbx+36Ch], ecx
0x140002248  jnz     short loc_14000223E
0x14000224a  test    eax, eax
0x14000224c  mov     edx, 10Ch
0x140002251  mov     eax, 1
0x140002256  mov     ecx, 100h
0x14000225b  cmovnz  ecx, edx
0x14000225e  mov     r8b, 1
0x140002261  mov     edx, [rcx+rbx]
0x140002264  lea     rcx, [rbx+248h]; Timer
0x14000226b  xchg    eax, [rbx+35Ch]
0x140002271  call    lldpSetPeriodicTimer
0x140002276  jmp     short loc_14000220C
0x140002278  mov     rcx, rbx
0x14000227b  call    lldpTxSendShutdownPacket
0x140002280  jmp     short loc_14000220C
0x140002282  mov     r9, [rbx+78h]
0x140002286  lea     r8, WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids
0x14000228d  mov     rcx, [rcx+18h]
0x140002291  mov     rax, r9
0x140002294  shr     rax, 18h
0x140002298  mov     edx, 10h
0x14000229d  and     eax, 0FFFFFFh
0x1400022a2  shr     r9, 30h
0x1400022a6  mov     [rsp+38h+var_10], edi
0x1400022aa  mov     [rsp+38h+var_18], eax
0x1400022ae  call    WPP_SF_DDD
0x1400022b3  jmp     loc_1400021B0
```
