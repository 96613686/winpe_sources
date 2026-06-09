# PcpLineSendNetBufferLists

- ea: `0x140009fe0`
- end: `0x14000a370`
- name: `PcpLineSendNetBufferLists`
- size: `912`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140005c10`
- `0x140009b80`

## callees

- `0x140008290`
- `0x140009fe0`
- `0x14000a380`
- `0x14000a790`
- `0x1400110d8`

## import_xrefs

- `NDIS!NdisFSendNetBufferLists` at `0x14000a0f9`
- `NDIS!NdisFSendNetBufferLists` at `0x14000a20e`
- `NDIS!NdisFSendNetBufferLists` at `0x14000a0f9`
- `NDIS!NdisFSendNetBufferLists` at `0x14000a20e`
- `NDIS!NdisReleaseRWLock` at `0x14000a352`
- `NDIS!NdisReleaseRWLock` at `0x14000a352`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000a332`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000a332`
- `HAL!KeQueryPerformanceCounter` at `0x14000a12b`
- `HAL!KeQueryPerformanceCounter` at `0x14000a12b`

## pseudocode

```c
void __fastcall PcpLineSendNetBufferLists(__int64 a1, unsigned int a2, struct _NET_BUFFER_LIST *a3, int a4)
{
  struct _NET_BUFFER_LIST *v5; // rsi
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned int v9; // r8d
  SLIST_HEADER *Alignment; // rcx
  ULONGLONG Region; // rax
  int i; // edx
  __int64 v13; // r10
  signed int v14; // r8d
  SLIST_HEADER *v15; // rax
  bool v16; // zf
  signed int v17; // edx
  LARGE_INTEGER v18; // rax
  union _LARGE_INTEGER v19; // r8
  LARGE_INTEGER v20; // r9
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  unsigned __int8 v23; // al
  unsigned __int8 v24; // al
  signed int v25; // ecx
  _QWORD *v26; // rax
  __int64 v27; // r8
  _QWORD *v28; // rax
  signed int v29; // ecx
  __int64 v30; // rbx
  SLIST_HEADER *v31; // rdx
  SLIST_HEADER *v32; // rdi
  __int64 v33; // r14
  int v34; // edx
  int v35; // r9d
  struct _NET_BUFFER_LIST *QuadPart; // rdx
  __int64 v37; // r8
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v39; // [rsp+70h] [rbp+18h] BYREF
  int LockState; // [rsp+78h] [rbp+20h] BYREF

  LockState = a4;
  PerformanceFrequency.QuadPart = 0;
  v5 = a3;
  v39 = 0;
  if ( a1 )
  {
    LOWORD(LockState) = 0;
    BYTE2(LockState) = 0;
    v7 = MEMORY[0xFFFFF78000000008];
    v8 = *(_QWORD *)QosgTimerTable + ((unsigned __int64)a2 << 7);
    if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v8 + 8) )
    {
      PerformanceFrequency.QuadPart = 0;
      v18 = KeQueryPerformanceCounter(&PerformanceFrequency);
      v19 = PerformanceFrequency;
      v20 = v18;
      v21 = *(unsigned __int8 *)(v8 + 112);
      v22 = ((1000000 * HIDWORD(v18.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
          + (1000000LL * v18.LowPart
           + ((1000000 * HIDWORD(v18.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
          / PerformanceFrequency.QuadPart;
      if ( (_BYTE)v21 )
        v23 = v21 - 1;
      else
        v23 = 2;
      if ( (__int64)(*(_QWORD *)(v8 + 8LL * v23 + 64) - v22) > 0 )
      {
        *(_QWORD *)(v8 + 8 * v21 + 16) = *(_QWORD *)(v8 + 8LL * v23 + 16);
        *(_QWORD *)(v8 + 8 * v21 + 40) = *(_QWORD *)(v8 + 8LL * v23 + 40);
        *(_QWORD *)(v8 + 8 * v21 + 64) = *(_QWORD *)(v8 + 8LL * v23 + 64);
        v22 = *(_QWORD *)(v8 + 8LL * v23 + 64);
      }
      else
      {
        *(LARGE_INTEGER *)(v8 + 8 * v21 + 16) = v20;
        *(union _LARGE_INTEGER *)(v8 + 8 * v21 + 40) = v19;
        *(_QWORD *)(v8 + 8 * v21 + 64) = v22;
      }
      *(_QWORD *)(v8 + 8 * v21 + 88) = v7;
      v24 = *(_BYTE *)(v8 + 112) + 1;
      *(_QWORD *)v8 = v22;
      *(_QWORD *)(v8 + 8) = v7;
      *(_BYTE *)(v8 + 112) = v24 % 3u;
    }
    if ( ((__int64)(*(_QWORD *)(a1 + 192) - *(_QWORD *)v8) <= 0 || (__int64)(*(_QWORD *)(a1 + 184) - *(_QWORD *)v8) <= 0)
      && !_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 152), 1u) )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 16), (PLOCK_STATE_EX)&LockState, 0);
      QosLineSignalExternalEvent(a1 + 24, a2);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), (PLOCK_STATE_EX)&LockState);
    }
    v9 = 0;
    Alignment = (SLIST_HEADER *)v5;
    if ( v5 )
    {
      do
      {
        Region = Alignment->Region;
        for ( i = 0; Region; Region = *(_QWORD *)Region )
          i += *(_DWORD *)(Region + 24);
        Alignment = (SLIST_HEADER *)Alignment->Alignment;
        v9 += i;
      }
      while ( Alignment );
      _InterlockedAdd((volatile signed __int32 *)(a1 + 156), v9);
      v13 = *(_QWORD *)(a1 + 256);
      v14 = 0;
      v15 = (SLIST_HEADER *)v5;
      do
      {
        v16 = v15[7].Region == *(_QWORD *)(v13 + 40);
        v17 = v14 + 1;
        v15 = (SLIST_HEADER *)v15->Alignment;
        if ( !v16 )
          v17 = v14;
        v14 = v17;
      }
      while ( v15 );
      if ( v17 > 0 )
        _InterlockedAdd((volatile signed __int32 *)(v13 + 128), v17);
      NdisFSendNetBufferLists(*(NDIS_HANDLE *)(*(_QWORD *)(a1 + 256) + 40LL), v5, 0, 0);
    }
    else
    {
      _InterlockedAdd((volatile signed __int32 *)(a1 + 156), 0);
    }
  }
  else
  {
    v31 = (SLIST_HEADER *)a3;
    v30 = *(_QWORD *)&a3->Context->ContextData[a3->Context->Offset + 32] - 24LL;
    do
    {
      v32 = (SLIST_HEADER *)v31->Alignment;
      if ( v31->Alignment )
        v33 = *(_QWORD *)(*(unsigned __int16 *)(v32[1].Alignment + 10) + v32[1].Alignment + 48) - 24LL;
      else
        v33 = 0;
      if ( v30 != v33 )
      {
        v31->Alignment = 0;
        PcpLineSignalExternalEvent(v30, a2);
        QosLineSendNetBufferLists(v30 + 24, v34, (_DWORD)v5, v35, (__int64)&PerformanceFrequency, (__int64)&v39);
        QuadPart = (struct _NET_BUFFER_LIST *)PerformanceFrequency.QuadPart;
        if ( PerformanceFrequency.QuadPart )
        {
          v37 = *(_QWORD *)(v30 + 256);
          v26 = (_QWORD *)PerformanceFrequency.QuadPart;
          v25 = 0;
          do
          {
            if ( v26[15] == *(_QWORD *)(v37 + 40) )
              ++v25;
            v26 = (_QWORD *)*v26;
          }
          while ( v26 );
          if ( v25 > 0 )
            _InterlockedAdd((volatile signed __int32 *)(v37 + 128), v25);
          NdisFSendNetBufferLists(*(NDIS_HANDLE *)(*(_QWORD *)(v30 + 256) + 40LL), QuadPart, 0, 0);
          PerformanceFrequency.QuadPart = 0;
        }
        if ( v39 )
        {
          v27 = *(_QWORD *)(v30 + 256);
          v28 = v39;
          v29 = 0;
          do
          {
            if ( v28[15] == *(_QWORD *)(v27 + 40) )
              ++v29;
            v28 = (_QWORD *)*v28;
          }
          while ( v28 );
          if ( v29 > 0 )
            _InterlockedAdd((volatile signed __int32 *)(v27 + 128), v29);
          PcpLineDropNblChain(v30);
          v39 = 0;
        }
        LODWORD(v5) = (_DWORD)v32;
      }
      v30 = v33;
      v31 = v32;
    }
    while ( v32 );
  }
}

```

## disassembly

```asm
0x140009fe0  mov     [rsp+arg_8], rbx
0x140009fe5  mov     [rsp+LockState], r9d
0x140009fea  push    rbp
0x140009feb  push    rsi
0x140009fec  push    rdi
0x140009fed  push    r14
0x140009fef  push    r15
0x140009ff1  sub     rsp, 30h
0x140009ff5  xor     r15d, r15d
0x140009ff8  mov     ebp, edx
0x140009ffa  mov     qword ptr [rsp+58h+PerformanceFrequency], r15
0x140009fff  mov     rsi, r8
0x14000a002  mov     [rsp+58h+arg_10], r15
0x14000a007  mov     rdi, rcx
0x14000a00a  test    rcx, rcx
0x14000a00d  jz      loc_14000A276
0x14000a013  xor     eax, eax
0x14000a015  mov     r14d, ebp
0x14000a018  mov     word ptr [rsp+58h+LockState], ax
0x14000a01d  mov     rbx, 0FFFFF78000000008h
0x14000a027  mov     byte ptr [rsp+58h+LockState+2], al
0x14000a02b  mov     rax, cs:QosgTimerTable
0x14000a032  shl     r14, 7
0x14000a036  mov     rbx, [rbx]
0x14000a039  add     r14, [rax]
0x14000a03c  cmp     rbx, [r14+8]
0x14000a040  jnz     loc_14000A121
0x14000a046  mov     rcx, [r14]
0x14000a049  mov     rax, [rdi+0C0h]
0x14000a050  sub     rax, rcx
0x14000a053  test    rax, rax
0x14000a056  jle     short loc_14000A067
0x14000a058  mov     rax, [rdi+0B8h]
0x14000a05f  sub     rax, rcx
0x14000a062  test    rax, rax
0x14000a065  jg      short loc_14000A07C
0x14000a067  mov     eax, 1
0x14000a06c  lock xadd [rdi+98h], eax
0x14000a074  test    eax, eax
0x14000a076  jz      loc_14000A326
0x14000a07c  mov     r8d, r15d
0x14000a07f  mov     rcx, rsi
0x14000a082  test    rsi, rsi
0x14000a085  jz      loc_14000A117
0x14000a08b  mov     rax, [rcx+8]
0x14000a08f  mov     edx, r15d
0x14000a092  test    rax, rax
0x14000a095  jz      short loc_14000A0A2
0x14000a097  add     edx, [rax+18h]
0x14000a09a  mov     rax, [rax]
0x14000a09d  test    rax, rax
0x14000a0a0  jnz     short loc_14000A097
0x14000a0a2  mov     rcx, [rcx]
0x14000a0a5  add     r8d, edx
0x14000a0a8  test    rcx, rcx
0x14000a0ab  jnz     short loc_14000A08B
0x14000a0ad  lock add [rdi+9Ch], r8d
0x14000a0b5  mov     r10, [rdi+100h]
0x14000a0bc  mov     r8d, r15d
0x14000a0bf  mov     rax, rsi
0x14000a0c2  mov     r9, [r10+28h]
0x14000a0c6  cmp     [rax+78h], r9
0x14000a0ca  lea     edx, [r8+1]
0x14000a0ce  mov     rax, [rax]
0x14000a0d1  cmovnz  edx, r8d
0x14000a0d5  mov     r8d, edx
0x14000a0d8  test    rax, rax
0x14000a0db  jnz     short loc_14000A0C6
0x14000a0dd  test    edx, edx
0x14000a0df  jg      loc_14000A363
0x14000a0e5  mov     rcx, [rdi+100h]
0x14000a0ec  xor     r9d, r9d; SendFlags
0x14000a0ef  xor     r8d, r8d; PortNumber
0x14000a0f2  mov     rdx, rsi; NetBufferList
0x14000a0f5  mov     rcx, [rcx+28h]; NdisFilterHandle
0x14000a0f9  call    cs:__imp_NdisFSendNetBufferLists
0x14000a100  nop     dword ptr [rax+rax+00h]
0x14000a105  mov     rbx, [rsp+58h+arg_8]
0x14000a10a  add     rsp, 30h
0x14000a10e  pop     r15
0x14000a110  pop     r14
0x14000a112  pop     rdi
0x14000a113  pop     rsi
0x14000a114  pop     rbp
0x14000a115  retn
0x14000a117  lock add [rdi+9Ch], r8d
0x14000a11f  jmp     short loc_14000A105
0x14000a121  lea     rcx, [rsp+58h+PerformanceFrequency]; PerformanceFrequency
0x14000a126  mov     qword ptr [rsp+58h+PerformanceFrequency], r15
0x14000a12b  call    cs:__imp_KeQueryPerformanceCounter
0x14000a132  nop     dword ptr [rax+rax+00h]
0x14000a137  mov     r8, qword ptr [rsp+58h+PerformanceFrequency]
0x14000a13c  xor     edx, edx
0x14000a13e  mov     r9, rax
0x14000a141  shr     rax, 20h
0x14000a145  imul    r10, rax, 0F4240h
0x14000a14c  mov     ecx, r9d
0x14000a14f  mov     rax, r10
0x14000a152  div     r8
0x14000a155  mov     rax, rdx
0x14000a158  shl     rax, 20h
0x14000a15c  imul    rdx, rcx, 0F4240h
0x14000a163  add     rax, rdx
0x14000a166  xor     edx, edx
0x14000a168  div     r8
0x14000a16b  xor     edx, edx
0x14000a16d  mov     rcx, rax
0x14000a170  mov     rax, r10
0x14000a173  div     r8
0x14000a176  movzx   edx, byte ptr [r14+70h]
0x14000a17b  shl     rax, 20h
0x14000a17f  add     rcx, rax
0x14000a182  test    dl, dl
0x14000a184  jz      short loc_14000A1DD
0x14000a186  lea     eax, [rdx-1]
0x14000a189  movzx   r10d, al
0x14000a18d  mov     rax, [r14+r10*8+40h]
0x14000a192  sub     rax, rcx
0x14000a195  test    rax, rax
0x14000a198  jg      loc_14000A2FE
0x14000a19e  mov     [r14+rdx*8+10h], r9
0x14000a1a3  mov     [r14+rdx*8+28h], r8
0x14000a1a8  mov     [r14+rdx*8+40h], rcx
0x14000a1ad  mov     [r14+rdx*8+58h], rbx
0x14000a1b2  movzx   eax, byte ptr [r14+70h]
0x14000a1b7  inc     al
0x14000a1b9  mov     [r14], rcx
0x14000a1bc  movzx   r8d, al
0x14000a1c0  mov     eax, 0AAAAAAABh
0x14000a1c5  mul     r8d
0x14000a1c8  mov     [r14+8], rbx
0x14000a1cc  shr     edx, 1; NetBufferList
0x14000a1ce  lea     eax, [rdx+rdx*2]
0x14000a1d1  sub     r8d, eax
0x14000a1d4  mov     [r14+70h], r8b
0x14000a1d8  jmp     loc_14000A046
0x14000a1dd  mov     al, 2
0x14000a1df  jmp     short loc_14000A189
0x14000a1e1  cmp     [rax+78h], r9
0x14000a1e5  jnz     short loc_14000A1E9
0x14000a1e7  inc     ecx
0x14000a1e9  mov     rax, [rax]
0x14000a1ec  test    rax, rax
0x14000a1ef  jnz     short loc_14000A1E1
0x14000a1f1  test    ecx, ecx
0x14000a1f3  jle     short loc_14000A1FD
0x14000a1f5  lock add [r8+80h], ecx
0x14000a1fd  mov     rcx, [rbx+100h]
0x14000a204  xor     r9d, r9d; SendFlags
0x14000a207  xor     r8d, r8d; PortNumber
0x14000a20a  mov     rcx, [rcx+28h]; NdisFilterHandle
0x14000a20e  call    cs:__imp_NdisFSendNetBufferLists
0x14000a215  nop     dword ptr [rax+rax+00h]
0x14000a21a  mov     qword ptr [rsp+58h+PerformanceFrequency], r15
0x14000a21f  mov     rdx, [rsp+58h+arg_10]
0x14000a224  test    rdx, rdx
0x14000a227  jz      short loc_14000A263
0x14000a229  mov     r8, [rbx+100h]
0x14000a230  mov     rax, rdx
0x14000a233  mov     ecx, r15d
0x14000a236  mov     r9, [r8+28h]
0x14000a23a  cmp     [rax+78h], r9
0x14000a23e  jnz     short loc_14000A242
0x14000a240  inc     ecx
0x14000a242  mov     rax, [rax]
0x14000a245  test    rax, rax
0x14000a248  jnz     short loc_14000A23A
0x14000a24a  test    ecx, ecx
0x14000a24c  jle     short loc_14000A256
0x14000a24e  lock add [r8+80h], ecx
0x14000a256  mov     rcx, rbx
0x14000a259  call    PcpLineDropNblChain
0x14000a25e  mov     [rsp+58h+arg_10], r15
0x14000a263  mov     rsi, rdi
0x14000a266  mov     rbx, r14
0x14000a269  mov     rdx, rdi
0x14000a26c  test    rdi, rdi
0x14000a26f  jnz     short loc_14000A28A
0x14000a271  jmp     loc_14000A105
0x14000a276  mov     rcx, [r8+10h]
0x14000a27a  mov     rdx, rsi
0x14000a27d  movzx   eax, word ptr [rcx+0Ah]
0x14000a281  mov     rbx, [rax+rcx+30h]
0x14000a286  sub     rbx, 18h
0x14000a28a  mov     rdi, [rdx]
0x14000a28d  test    rdi, rdi
0x14000a290  jz      short loc_14000A2A5
0x14000a292  mov     rcx, [rdi+10h]
0x14000a296  movzx   eax, word ptr [rcx+0Ah]
0x14000a29a  mov     r14, [rax+rcx+30h]
0x14000a29f  sub     r14, 18h
0x14000a2a3  jmp     short loc_14000A2A8
0x14000a2a5  mov     r14, r15
0x14000a2a8  cmp     rbx, r14
0x14000a2ab  jz      short loc_14000A266
0x14000a2ad  mov     [rdx], r15
0x14000a2b0  mov     rcx, rbx
0x14000a2b3  mov     edx, ebp
0x14000a2b5  call    PcpLineSignalExternalEvent
0x14000a2ba  lea     rax, [rsp+58h+arg_10]
0x14000a2bf  mov     r8, rsi
0x14000a2c2  mov     [rsp+58h+var_30], rax
0x14000a2c7  lea     rcx, [rbx+18h]
0x14000a2cb  lea     rax, [rsp+58h+PerformanceFrequency]
0x14000a2d0  mov     [rsp+58h+var_38], rax
0x14000a2d5  call    QosLineSendNetBufferLists
0x14000a2da  mov     rdx, qword ptr [rsp+58h+PerformanceFrequency]
0x14000a2df  test    rdx, rdx
0x14000a2e2  jz      loc_14000A21F
0x14000a2e8  mov     r8, [rbx+100h]
0x14000a2ef  mov     rax, rdx
0x14000a2f2  mov     ecx, r15d
0x14000a2f5  mov     r9, [r8+28h]
0x14000a2f9  jmp     loc_14000A1E1
0x14000a2fe  mov     rax, [r14+r10*8+10h]
0x14000a303  mov     [r14+rdx*8+10h], rax
0x14000a308  mov     rax, [r14+r10*8+28h]
0x14000a30d  mov     [r14+rdx*8+28h], rax
0x14000a312  mov     rax, [r14+r10*8+40h]
0x14000a317  mov     [r14+rdx*8+40h], rax
0x14000a31c  mov     rcx, [r14+r10*8+40h]
0x14000a321  jmp     loc_14000A1AD
0x14000a326  mov     rcx, [rdi+10h]; Lock
0x14000a32a  lea     rdx, [rsp+58h+LockState]; LockState
0x14000a32f  xor     r8d, r8d; Flags
0x14000a332  call    cs:__imp_NdisAcquireRWLockWrite
0x14000a339  nop     dword ptr [rax+rax+00h]
0x14000a33e  lea     rcx, [rdi+18h]
0x14000a342  mov     edx, ebp
0x14000a344  call    QosLineSignalExternalEvent
0x14000a349  mov     rcx, [rdi+10h]; Lock
0x14000a34d  lea     rdx, [rsp+58h+LockState]; LockState
0x14000a352  call    cs:__imp_NdisReleaseRWLock
0x14000a359  nop     dword ptr [rax+rax+00h]
0x14000a35e  jmp     loc_14000A07C
0x14000a363  lock add [r10+80h], r8d
0x14000a36b  jmp     loc_14000A0E5
```
