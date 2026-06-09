# PcpSchedulerBatchAndSendOrDropNblChain

- ea: `0x140009b80`
- end: `0x140009fd4`
- name: `PcpSchedulerBatchAndSendOrDropNblChain`
- size: `1108`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferList)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x140003ab0`
- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x14000cce0`

## callees

- `0x140008290`
- `0x140009b80`
- `0x140009fe0`
- `0x14000a380`
- `0x14000a790`
- `0x14000b9d4`
- `0x1400110d8`

## import_xrefs

- `NDIS!NdisFSendNetBufferLists` at `0x140009cc5`
- `NDIS!NdisFSendNetBufferLists` at `0x140009e2b`
- `NDIS!NdisFSendNetBufferLists` at `0x140009cc5`
- `NDIS!NdisFSendNetBufferLists` at `0x140009e2b`
- `NDIS!NdisReleaseRWLock` at `0x140009fb6`
- `NDIS!NdisReleaseRWLock` at `0x140009fb6`
- `NDIS!NdisAcquireRWLockWrite` at `0x140009f93`
- `NDIS!NdisAcquireRWLockWrite` at `0x140009f93`
- `HAL!KeQueryPerformanceCounter` at `0x140009d45`
- `HAL!KeQueryPerformanceCounter` at `0x140009d45`

## pseudocode

```c
void __fastcall PcpSchedulerBatchAndSendOrDropNblChain(
        PNET_BUFFER_LIST NetBufferList,
        unsigned int a2,
        unsigned int a3,
        char a4)
{
  struct _NET_BUFFER_LIST *Alignment; // r14
  char *v5; // rsi
  __int64 v7; // r15
  PNET_BUFFER_LIST v9; // rdi
  PNET_BUFFER_LIST v10; // rax
  char *v11; // rbp
  __int64 v12; // rbx
  __int64 v13; // r14
  unsigned int v14; // r8d
  SLIST_HEADER *v15; // rcx
  ULONGLONG Region; // rax
  int i; // edx
  __int64 v18; // r10
  signed int v19; // r8d
  SLIST_HEADER *v20; // rax
  bool v21; // zf
  signed int v22; // edx
  struct _NET_BUFFER_LIST *v23; // rbp
  LARGE_INTEGER v24; // rax
  union _LARGE_INTEGER v25; // r8
  LARGE_INTEGER v26; // r9
  __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  unsigned __int8 v29; // al
  unsigned __int8 v30; // al
  signed int v31; // ecx
  _QWORD *v32; // rax
  __int64 v33; // r8
  _QWORD *v34; // rax
  signed int v35; // ecx
  __int64 v36; // rbx
  SLIST_HEADER *v37; // rdx
  SLIST_HEADER *v38; // rsi
  __int64 v39; // rbp
  int v40; // edx
  int v41; // r9d
  struct _NET_BUFFER_LIST *QuadPart; // rdx
  __int64 v43; // r8
  _QWORD *v44; // [rsp+30h] [rbp-48h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+80h] [rbp+8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+98h] [rbp+20h] BYREF

  Alignment = (struct _NET_BUFFER_LIST *)NetBufferList->Link.Alignment;
  v5 = (char *)NetBufferList->MiniportReserved[0];
  v7 = a2;
  v9 = NetBufferList;
  v10 = NetBufferList;
  if ( NetBufferList->Link.Alignment )
  {
    do
    {
      v23 = Alignment;
      if ( Alignment->MiniportReserved[0] != v5 )
      {
        v10->Link.Alignment = 0;
        if ( a4 )
          PcpLineSendNetBufferLists(v5 - 24, (unsigned int)v7, v9);
        else
          PcpSchedulerDropNblChain(v9->NetBufferListInfo[3], v5 - 24, v9, a3);
        v5 = (char *)Alignment->MiniportReserved[0];
        v9 = Alignment;
      }
      Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
      v10 = v23;
    }
    while ( Alignment );
  }
  v11 = v5 - 24;
  if ( a4 )
  {
    PerformanceFrequency.QuadPart = 0;
    v44 = 0;
    if ( v5 == (char *)24 )
    {
      v37 = (SLIST_HEADER *)v9;
      v36 = *(_QWORD *)&v9->Context->ContextData[v9->Context->Offset + 32] - 24LL;
      do
      {
        v38 = (SLIST_HEADER *)v37->Alignment;
        if ( v37->Alignment )
          v39 = *(_QWORD *)(*(unsigned __int16 *)(v38[1].Alignment + 10) + v38[1].Alignment + 48) - 24LL;
        else
          v39 = 0;
        if ( v36 != v39 )
        {
          v37->Alignment = 0;
          PcpLineSignalExternalEvent(v36, (unsigned int)v7);
          QosLineSendNetBufferLists(v36 + 24, v40, (_DWORD)v9, v41, (__int64)&PerformanceFrequency, (__int64)&v44);
          QuadPart = (struct _NET_BUFFER_LIST *)PerformanceFrequency.QuadPart;
          if ( PerformanceFrequency.QuadPart )
          {
            v43 = *(_QWORD *)(v36 + 256);
            v32 = (_QWORD *)PerformanceFrequency.QuadPart;
            v31 = 0;
            do
            {
              if ( v32[15] == *(_QWORD *)(v43 + 40) )
                ++v31;
              v32 = (_QWORD *)*v32;
            }
            while ( v32 );
            if ( v31 > 0 )
              _InterlockedAdd((volatile signed __int32 *)(v43 + 128), v31);
            NdisFSendNetBufferLists(*(NDIS_HANDLE *)(*(_QWORD *)(v36 + 256) + 40LL), QuadPart, 0, 0);
            PerformanceFrequency.QuadPart = 0;
          }
          if ( v44 )
          {
            v33 = *(_QWORD *)(v36 + 256);
            v34 = v44;
            v35 = 0;
            do
            {
              if ( v34[15] == *(_QWORD *)(v33 + 40) )
                ++v35;
              v34 = (_QWORD *)*v34;
            }
            while ( v34 );
            if ( v35 > 0 )
              _InterlockedAdd((volatile signed __int32 *)(v33 + 128), v35);
            PcpLineDropNblChain(v36);
            v44 = 0;
          }
          LODWORD(v9) = (_DWORD)v38;
        }
        v36 = v39;
        v37 = v38;
      }
      while ( v38 );
    }
    else
    {
      *(_WORD *)&LockState.OldIrql = 0;
      LockState.Flags = 0;
      v12 = MEMORY[0xFFFFF78000000008];
      v13 = *(_QWORD *)QosgTimerTable + (v7 << 7);
      if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v13 + 8) )
      {
        PerformanceFrequency.QuadPart = 0;
        v24 = KeQueryPerformanceCounter(&PerformanceFrequency);
        v25 = PerformanceFrequency;
        v26 = v24;
        v27 = *(unsigned __int8 *)(v13 + 112);
        v28 = ((1000000 * HIDWORD(v24.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
            + (1000000LL * v24.LowPart
             + ((1000000 * HIDWORD(v24.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
            / PerformanceFrequency.QuadPart;
        if ( (_BYTE)v27 )
          v29 = v27 - 1;
        else
          v29 = 2;
        if ( (__int64)(*(_QWORD *)(v13 + 8LL * v29 + 64) - v28) > 0 )
        {
          *(_QWORD *)(v13 + 8 * v27 + 16) = *(_QWORD *)(v13 + 8LL * v29 + 16);
          *(_QWORD *)(v13 + 8 * v27 + 40) = *(_QWORD *)(v13 + 8LL * v29 + 40);
          *(_QWORD *)(v13 + 8 * v27 + 64) = *(_QWORD *)(v13 + 8LL * v29 + 64);
          v28 = *(_QWORD *)(v13 + 8LL * v29 + 64);
        }
        else
        {
          *(LARGE_INTEGER *)(v13 + 8 * v27 + 16) = v26;
          *(union _LARGE_INTEGER *)(v13 + 8 * v27 + 40) = v25;
          *(_QWORD *)(v13 + 8 * v27 + 64) = v28;
        }
        *(_QWORD *)(v13 + 8 * v27 + 88) = v12;
        v30 = *(_BYTE *)(v13 + 112) + 1;
        *(_QWORD *)v13 = v28;
        *(_QWORD *)(v13 + 8) = v12;
        *(_BYTE *)(v13 + 112) = v30 % 3u;
      }
      if ( ((__int64)(*((_QWORD *)v5 + 21) - *(_QWORD *)v13) <= 0
         || (__int64)(*((_QWORD *)v5 + 20) - *(_QWORD *)v13) <= 0)
        && !_InterlockedExchangeAdd((volatile signed __int32 *)v5 + 32, 1u) )
      {
        NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)v11 + 2), &LockState, 0);
        QosLineSignalExternalEvent(v5, (unsigned int)v7);
        NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v11 + 2), &LockState);
      }
      v14 = 0;
      v15 = (SLIST_HEADER *)v9;
      if ( v9 )
      {
        do
        {
          Region = v15->Region;
          for ( i = 0; Region; Region = *(_QWORD *)Region )
            i += *(_DWORD *)(Region + 24);
          v15 = (SLIST_HEADER *)v15->Alignment;
          v14 += i;
        }
        while ( v15 );
        _InterlockedAdd((volatile signed __int32 *)v11 + 39, v14);
        v18 = *((_QWORD *)v11 + 32);
        v19 = 0;
        v20 = (SLIST_HEADER *)v9;
        do
        {
          v21 = v20[7].Region == *(_QWORD *)(v18 + 40);
          v22 = v19 + 1;
          v20 = (SLIST_HEADER *)v20->Alignment;
          if ( !v21 )
            v22 = v19;
          v19 = v22;
        }
        while ( v20 );
        if ( v22 > 0 )
          _InterlockedAdd((volatile signed __int32 *)(v18 + 128), v22);
        NdisFSendNetBufferLists(*(NDIS_HANDLE *)(*((_QWORD *)v11 + 32) + 40LL), v9, 0, 0);
      }
      else
      {
        _InterlockedAdd((volatile signed __int32 *)v11 + 39, 0);
      }
    }
  }
  else
  {
    PcpSchedulerDropNblChain(v9->NetBufferListInfo[3], v5 - 24, v9, a3);
  }
}

```

## disassembly

```asm
0x140009b80  mov     [rsp+arg_8], rbx
0x140009b85  push    rbp
0x140009b86  push    rsi
0x140009b87  push    rdi
0x140009b88  push    r12
0x140009b8a  push    r13
0x140009b8c  push    r14
0x140009b8e  push    r15
0x140009b90  sub     rsp, 40h
0x140009b94  mov     r14, [rcx]
0x140009b97  xor     r13d, r13d
0x140009b9a  mov     rsi, [rcx+60h]
0x140009b9e  movzx   ebx, r9b
0x140009ba2  mov     r15d, edx
0x140009ba5  mov     r12d, r8d
0x140009ba8  mov     rdi, rcx
0x140009bab  mov     rax, rcx
0x140009bae  test    r14, r14
0x140009bb1  jnz     loc_140009D00
0x140009bb7  lea     rbp, [rsi-18h]
0x140009bbb  test    bl, bl
0x140009bbd  jz      loc_140009D1E
0x140009bc3  mov     qword ptr [rsp+78h+PerformanceFrequency], r13
0x140009bcb  mov     [rsp+78h+var_48], r13
0x140009bd0  test    rbp, rbp
0x140009bd3  jz      loc_140009ECD
0x140009bd9  xor     eax, eax
0x140009bdb  mov     r14, r15
0x140009bde  mov     word ptr [rsp+78h+LockState.OldIrql], ax
0x140009be6  mov     rbx, 0FFFFF78000000008h
0x140009bf0  mov     [rsp+78h+LockState.Flags], al
0x140009bf7  mov     rax, cs:QosgTimerTable
0x140009bfe  shl     r14, 7
0x140009c02  mov     rbx, [rbx]
0x140009c05  add     r14, [rax]
0x140009c08  cmp     rbx, [r14+8]
0x140009c0c  jnz     loc_140009D35
0x140009c12  mov     rcx, [r14]
0x140009c15  mov     rax, [rsi+0A8h]
0x140009c1c  sub     rax, rcx
0x140009c1f  test    rax, rax
0x140009c22  jle     short loc_140009C33
0x140009c24  mov     rax, [rsi+0A0h]
0x140009c2b  sub     rax, rcx
0x140009c2e  test    rax, rax
0x140009c31  jg      short loc_140009C48
0x140009c33  mov     eax, 1
0x140009c38  lock xadd [rsi+80h], eax
0x140009c40  test    eax, eax
0x140009c42  jz      loc_140009F84
0x140009c48  mov     r8d, r13d
0x140009c4b  mov     rcx, rdi
0x140009c4e  test    rdi, rdi
0x140009c51  jz      loc_140009CEA
0x140009c57  mov     rax, [rcx+8]
0x140009c5b  mov     edx, r13d
0x140009c5e  test    rax, rax
0x140009c61  jz      short loc_140009C6E
0x140009c63  add     edx, [rax+18h]
0x140009c66  mov     rax, [rax]
0x140009c69  test    rax, rax
0x140009c6c  jnz     short loc_140009C63
0x140009c6e  mov     rcx, [rcx]
0x140009c71  add     r8d, edx
0x140009c74  test    rcx, rcx
0x140009c77  jnz     short loc_140009C57
0x140009c79  lock add [rbp+9Ch], r8d
0x140009c81  mov     r10, [rbp+100h]
0x140009c88  mov     r8d, r13d
0x140009c8b  mov     rax, rdi
0x140009c8e  mov     r9, [r10+28h]
0x140009c92  cmp     [rax+78h], r9
0x140009c96  lea     edx, [r8+1]
0x140009c9a  mov     rax, [rax]
0x140009c9d  cmovnz  edx, r8d
0x140009ca1  mov     r8d, edx
0x140009ca4  test    rax, rax
0x140009ca7  jnz     short loc_140009C92
0x140009ca9  test    edx, edx
0x140009cab  jg      loc_140009FC7
0x140009cb1  mov     rcx, [rbp+100h]
0x140009cb8  xor     r9d, r9d; SendFlags
0x140009cbb  xor     r8d, r8d; PortNumber
0x140009cbe  mov     rdx, rdi; NetBufferList
0x140009cc1  mov     rcx, [rcx+28h]; NdisFilterHandle
0x140009cc5  call    cs:__imp_NdisFSendNetBufferLists
0x140009ccc  nop     dword ptr [rax+rax+00h]
0x140009cd1  mov     rbx, [rsp+78h+arg_8]
0x140009cd9  add     rsp, 40h
0x140009cdd  pop     r15
0x140009cdf  pop     r14
0x140009ce1  pop     r13
0x140009ce3  pop     r12
0x140009ce5  pop     rdi
0x140009ce6  pop     rsi
0x140009ce7  pop     rbp
0x140009ce8  retn
0x140009cea  lock add [rbp+9Ch], r8d
0x140009cf2  jmp     short loc_140009CD1
0x140009d00  mov     rbp, r14
0x140009d03  cmp     [r14+60h], rsi
0x140009d07  jnz     loc_140009E96
0x140009d0d  mov     r14, [r14]
0x140009d10  mov     rax, rbp
0x140009d13  test    r14, r14
0x140009d16  jz      loc_140009BB7
0x140009d1c  jmp     short loc_140009D00
0x140009d1e  mov     rcx, [rdi+0A8h]
0x140009d25  mov     r9d, r12d
0x140009d28  mov     r8, rdi
0x140009d2b  mov     rdx, rbp
0x140009d2e  call    PcpSchedulerDropNblChain
0x140009d33  jmp     short loc_140009CD1
0x140009d35  lea     rcx, [rsp+78h+PerformanceFrequency]; PerformanceFrequency
0x140009d3d  mov     qword ptr [rsp+78h+PerformanceFrequency], r13
0x140009d45  call    cs:__imp_KeQueryPerformanceCounter
0x140009d4c  nop     dword ptr [rax+rax+00h]
0x140009d51  mov     r8, qword ptr [rsp+78h+PerformanceFrequency]
0x140009d59  xor     edx, edx
0x140009d5b  mov     r9, rax
0x140009d5e  shr     rax, 20h
0x140009d62  imul    r10, rax, 0F4240h
0x140009d69  mov     ecx, r9d
0x140009d6c  mov     rax, r10
0x140009d6f  div     r8
0x140009d72  mov     rax, rdx
0x140009d75  shl     rax, 20h
0x140009d79  imul    rdx, rcx, 0F4240h
0x140009d80  add     rax, rdx
0x140009d83  xor     edx, edx
0x140009d85  div     r8
0x140009d88  xor     edx, edx
0x140009d8a  mov     rcx, rax
0x140009d8d  mov     rax, r10
0x140009d90  div     r8
0x140009d93  movzx   edx, byte ptr [r14+70h]
0x140009d98  shl     rax, 20h
0x140009d9c  add     rcx, rax
0x140009d9f  test    dl, dl
0x140009da1  jz      short loc_140009DFA
0x140009da3  lea     eax, [rdx-1]
0x140009da6  movzx   r10d, al
0x140009daa  mov     rax, [r14+r10*8+40h]
0x140009daf  sub     rax, rcx
0x140009db2  test    rax, rax
0x140009db5  jg      loc_140009F5C
0x140009dbb  mov     [r14+rdx*8+10h], r9
0x140009dc0  mov     [r14+rdx*8+28h], r8
0x140009dc5  mov     [r14+rdx*8+40h], rcx
0x140009dca  mov     [r14+rdx*8+58h], rbx
0x140009dcf  movzx   eax, byte ptr [r14+70h]
0x140009dd4  inc     al
0x140009dd6  mov     [r14], rcx
0x140009dd9  movzx   r8d, al
0x140009ddd  mov     eax, 0AAAAAAABh
0x140009de2  mul     r8d
0x140009de5  mov     [r14+8], rbx
0x140009de9  shr     edx, 1; NetBufferList
0x140009deb  lea     eax, [rdx+rdx*2]
0x140009dee  sub     r8d, eax
0x140009df1  mov     [r14+70h], r8b
0x140009df5  jmp     loc_140009C12
0x140009dfa  mov     al, 2
0x140009dfc  jmp     short loc_140009DA6
0x140009dfe  cmp     [rax+78h], r9
0x140009e02  jnz     short loc_140009E06
0x140009e04  inc     ecx
0x140009e06  mov     rax, [rax]
0x140009e09  test    rax, rax
0x140009e0c  jnz     short loc_140009DFE
0x140009e0e  test    ecx, ecx
0x140009e10  jle     short loc_140009E1A
0x140009e12  lock add [r8+80h], ecx
0x140009e1a  mov     rcx, [rbx+100h]
0x140009e21  xor     r9d, r9d; SendFlags
0x140009e24  xor     r8d, r8d; PortNumber
0x140009e27  mov     rcx, [rcx+28h]; NdisFilterHandle
0x140009e2b  call    cs:__imp_NdisFSendNetBufferLists
0x140009e32  nop     dword ptr [rax+rax+00h]
0x140009e37  mov     qword ptr [rsp+78h+PerformanceFrequency], r13
0x140009e3f  mov     rdx, [rsp+78h+var_48]
0x140009e44  test    rdx, rdx
0x140009e47  jz      short loc_140009E83
0x140009e49  mov     r8, [rbx+100h]
0x140009e50  mov     rax, rdx
0x140009e53  mov     ecx, r13d
0x140009e56  mov     r9, [r8+28h]
0x140009e5a  cmp     [rax+78h], r9
0x140009e5e  jnz     short loc_140009E62
0x140009e60  inc     ecx
0x140009e62  mov     rax, [rax]
0x140009e65  test    rax, rax
0x140009e68  jnz     short loc_140009E5A
0x140009e6a  test    ecx, ecx
0x140009e6c  jle     short loc_140009E76
0x140009e6e  lock add [r8+80h], ecx
0x140009e76  mov     rcx, rbx
0x140009e79  call    PcpLineDropNblChain
0x140009e7e  mov     [rsp+78h+var_48], r13
0x140009e83  mov     rdi, rsi
0x140009e86  mov     rbx, rbp
0x140009e89  mov     rdx, rsi
0x140009e8c  test    rsi, rsi
0x140009e8f  jnz     short loc_140009EE1
0x140009e91  jmp     loc_140009CD1
0x140009e96  mov     [rax], r13
0x140009e99  mov     r8, rdi
0x140009e9c  test    bl, bl
0x140009e9e  jz      short loc_140009EAE
0x140009ea0  mov     edx, r15d
0x140009ea3  lea     rcx, [rsi-18h]
0x140009ea7  call    PcpLineSendNetBufferLists
0x140009eac  jmp     short loc_140009EC1
0x140009eae  mov     rcx, [rdi+0A8h]
0x140009eb5  lea     rdx, [rsi-18h]
0x140009eb9  mov     r9d, r12d
0x140009ebc  call    PcpSchedulerDropNblChain
0x140009ec1  mov     rsi, [r14+60h]
0x140009ec5  mov     rdi, r14
0x140009ec8  jmp     loc_140009D0D
0x140009ecd  mov     rcx, [rdi+10h]
0x140009ed1  mov     rdx, rdi
0x140009ed4  movzx   eax, word ptr [rcx+0Ah]
0x140009ed8  mov     rbx, [rax+rcx+30h]
0x140009edd  sub     rbx, 18h
0x140009ee1  mov     rsi, [rdx]
0x140009ee4  test    rsi, rsi
0x140009ee7  jz      short loc_140009EFC
0x140009ee9  mov     rcx, [rsi+10h]
0x140009eed  movzx   eax, word ptr [rcx+0Ah]
0x140009ef1  mov     rbp, [rax+rcx+30h]
0x140009ef6  sub     rbp, 18h
0x140009efa  jmp     short loc_140009EFF
0x140009efc  mov     rbp, r13
0x140009eff  cmp     rbx, rbp
0x140009f02  jz      short loc_140009E86
0x140009f04  mov     [rdx], r13
0x140009f07  mov     rcx, rbx
0x140009f0a  mov     edx, r15d
0x140009f0d  call    PcpLineSignalExternalEvent
0x140009f12  lea     rax, [rsp+78h+var_48]
0x140009f17  mov     r8, rdi
0x140009f1a  mov     [rsp+78h+var_50], rax
0x140009f1f  lea     rcx, [rbx+18h]
0x140009f23  lea     rax, [rsp+78h+PerformanceFrequency]
0x140009f2b  mov     [rsp+78h+var_58], rax
0x140009f30  call    QosLineSendNetBufferLists
0x140009f35  mov     rdx, qword ptr [rsp+78h+PerformanceFrequency]
0x140009f3d  test    rdx, rdx
0x140009f40  jz      loc_140009E3F
0x140009f46  mov     r8, [rbx+100h]
0x140009f4d  mov     rax, rdx
0x140009f50  mov     ecx, r13d
0x140009f53  mov     r9, [r8+28h]
0x140009f57  jmp     loc_140009DFE
0x140009f5c  mov     rax, [r14+r10*8+10h]
0x140009f61  mov     [r14+rdx*8+10h], rax
0x140009f66  mov     rax, [r14+r10*8+28h]
0x140009f6b  mov     [r14+rdx*8+28h], rax
0x140009f70  mov     rax, [r14+r10*8+40h]
0x140009f75  mov     [r14+rdx*8+40h], rax
0x140009f7a  mov     rcx, [r14+r10*8+40h]
0x140009f7f  jmp     loc_140009DCA
0x140009f84  mov     rcx, [rbp+10h]; Lock
0x140009f88  lea     rdx, [rsp+78h+LockState]; LockState
0x140009f90  xor     r8d, r8d; Flags
0x140009f93  call    cs:__imp_NdisAcquireRWLockWrite
0x140009f9a  nop     dword ptr [rax+rax+00h]
0x140009f9f  mov     edx, r15d
0x140009fa2  mov     rcx, rsi
0x140009fa5  call    QosLineSignalExternalEvent
0x140009faa  mov     rcx, [rbp+10h]; Lock
0x140009fae  lea     rdx, [rsp+78h+LockState]; LockState
0x140009fb6  call    cs:__imp_NdisReleaseRWLock
0x140009fbd  nop     dword ptr [rax+rax+00h]
0x140009fc2  jmp     loc_140009C48
0x140009fc7  lock add [r10+80h], r8d
0x140009fcf  jmp     loc_140009CB1
```
