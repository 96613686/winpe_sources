# LdrpReleaseDllPath

- ea: `0x18002b9f0`
- end: `0x18002bc67`
- name: `LdrpReleaseDllPath`
- size: `631`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b9b0`
- `0x18002b5f0`
- `0x18002b7b0`
- `0x180050718`
- `0x18006fd70`
- `0x1800bfe70`
- `0x1800c09fc`
- `0x1800c0ca0`
- `0x1800c19c0`
- `0x1800c25c0`
- `0x1800fbd9c`
- `0x1801060b8`
- `0x180107a54`
- `0x180125e90`
- `0x18015bec8`

## callees

- `0x18001861c`
- `0x18002b9f0`
- `0x18002cde0`
- `0x18015ec80`
- `0x18015f910`

## pseudocode

```c
void __fastcall LdrpReleaseDllPath(__int64 a1)
{
  __int64 v1; // rbx
  _QWORD *SchedulerSharedDataSlot; // rdx
  unsigned int i; // eax
  bool v5; // zf
  signed __int64 v6; // rax
  char *v7; // rdx
  unsigned int j; // ecx
  char *v9; // rdi
  __int64 v10; // rdx
  signed __int64 v11; // rcx
  signed __int64 v12; // rtt
  __int64 *v13; // rbp
  _QWORD *v14; // rdx
  __int64 v15; // r8
  _QWORD *v16; // rax
  __int64 v17; // rax
  signed __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  signed __int64 v21; // rax

  if ( *(_BYTE *)(a1 + 124) )
  {
    v1 = *(_QWORD *)a1 - 128LL;
    SchedulerSharedDataSlot = NtCurrentTeb()->SchedulerSharedDataSlot;
    if ( SchedulerSharedDataSlot )
    {
      for ( i = 0; i < 8; ++i )
      {
        if ( !SchedulerSharedDataSlot[i] )
        {
          SchedulerSharedDataSlot[i] = &RtlpCachedPathLock;
          break;
        }
      }
    }
    if ( _interlockedbittestandset64((volatile signed __int32 *)&RtlpCachedPathLock, 0) )
      RtlpAcquireSRWLockExclusiveContended(&RtlpCachedPathLock);
    v5 = (*(_QWORD *)(v1 + 80))-- == 1;
    if ( !v5 )
      v1 = 0;
    v6 = _InterlockedCompareExchange64(&RtlpCachedPathLock, 0, 1);
    if ( v6 != 1 )
    {
      do
      {
        v10 = -1;
        if ( (v6 & 6) == 2 )
          v10 = 3;
        v11 = v10 + v6;
        v12 = v6;
        v6 = _InterlockedCompareExchange64(&RtlpCachedPathLock, v10 + v6, v6);
      }
      while ( v12 != v6 );
      if ( v10 == 3 )
      {
        v13 = &RtlpCachedPathLock;
        while ( 1 )
        {
          while ( (v11 & 1) != 0 )
          {
            v21 = _InterlockedCompareExchange64(&RtlpCachedPathLock, v11 - 4, v11);
            v5 = v11 == v21;
            v11 = v21;
            if ( v5 )
              goto LABEL_10;
          }
          v14 = (_QWORD *)(v11 & 0xFFFFFFFFFFFFFFF0uLL);
          v15 = *(_QWORD *)((v11 & 0xFFFFFFFFFFFFFFF0uLL) + 8);
          if ( !v15 )
          {
            do
            {
              v16 = v14;
              v14 = (_QWORD *)*v14;
              v14[2] = v16;
              v15 = v14[1];
            }
            while ( !v15 );
            if ( v14 != (_QWORD *)(v11 & 0xFFFFFFFFFFFFFFF0uLL) )
              *(_QWORD *)((v11 & 0xFFFFFFFFFFFFFFF0uLL) + 8) = v15;
          }
          if ( (*(_DWORD *)(v15 + 36) & 1) != 0 )
          {
            v17 = *(_QWORD *)(v15 + 16);
            if ( v17 )
              break;
          }
          v13 = 0;
          v18 = _InterlockedCompareExchange64(&RtlpCachedPathLock, 0, v11);
          v5 = v11 == v18;
          v11 = v18;
          if ( v5 )
            goto LABEL_39;
        }
        *(_QWORD *)((v11 & 0xFFFFFFFFFFFFFFF0uLL) + 8) = v17;
        *(_QWORD *)(v15 + 16) = 0;
        _InterlockedAnd64(&RtlpCachedPathLock, 0xFFFFFFFFFFFFFFFBuLL);
        do
        {
LABEL_39:
          v19 = *(_QWORD *)(v15 + 16);
          v20 = *(_QWORD *)(v15 + 24);
          _interlockedbittestandset((volatile signed __int32 *)(v15 + 36), 2u);
          if ( !_interlockedbittestandreset((volatile signed __int32 *)(v15 + 36), 1u) )
            ZwAlertThreadByThreadIdEx(v20, v13);
          v15 = v19;
        }
        while ( v19 );
      }
    }
LABEL_10:
    v7 = (char *)NtCurrentTeb()->SchedulerSharedDataSlot;
    if ( v7 )
    {
      for ( j = 0; j < 8; ++j )
      {
        v9 = &v7[8 * j];
        if ( (*(_QWORD *)v9 & 0x7FFFFFFFFFFFFFFCLL) == ((unsigned __int64)&RtlpCachedPathLock & 0x7FFFFFFFFFFFFFFCLL) )
        {
          *v9 |= 2u;
          if ( v9[7] < 0 )
            NtSetInformationThread();
          *(_QWORD *)v9 = 0;
          break;
        }
      }
    }
    if ( v1 )
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x18002b9f0  sub     rsp, 48h
0x18002b9f4  cmp     byte ptr [rcx+7Ch], 0
0x18002b9f8  jz      loc_18002BB2F
0x18002b9fe  mov     rax, gs:30h
0x18002ba07  mov     [rsp+48h+arg_8], rbx
0x18002ba0c  mov     rbx, [rcx]
0x18002ba0f  mov     [rsp+48h+var_8], rsi
0x18002ba14  add     rbx, 0FFFFFFFFFFFFFF80h
0x18002ba18  mov     rdx, [rax+1850h]
0x18002ba1f  lea     rsi, RtlpCachedPathLock
0x18002ba26  mov     [rsp+48h+var_18], r14
0x18002ba2b  xor     r14d, r14d
0x18002ba2e  test    rdx, rdx
0x18002ba31  jz      short loc_18002BA3F
0x18002ba33  mov     eax, r14d
0x18002ba36  cmp     eax, 8
0x18002ba39  jb      loc_18002BB35
0x18002ba3f  lock bts qword ptr [rsi], 0
0x18002ba45  jb      loc_18002BC52
0x18002ba4b  sub     qword ptr [rbx+50h], 1
0x18002ba50  jnz     loc_18002BC5F
0x18002ba56  mov     [rsp+48h+var_10], rdi
0x18002ba5b  mov     rcx, r14
0x18002ba5e  mov     eax, 1
0x18002ba63  lock cmpxchg cs:RtlpCachedPathLock, rcx
0x18002ba6c  jnz     loc_18002BB50
0x18002ba72  mov     rax, gs:30h
0x18002ba7b  mov     rdx, [rax+1850h]
0x18002ba82  test    rdx, rdx
0x18002ba85  jz      short loc_18002BAFF
0x18002ba87  mov     r8, 7FFFFFFFFFFFFFFCh
0x18002ba91  mov     ecx, r14d
0x18002ba94  and     rsi, r8
0x18002ba97  cmp     ecx, 8
0x18002ba9a  jnb     short loc_18002BAFF
0x18002ba9c  mov     eax, ecx
0x18002ba9e  lea     rdi, [rdx+rax*8]
0x18002baa2  mov     rax, [rdx+rax*8]
0x18002baa6  and     rax, r8
0x18002baa9  cmp     rax, rsi
0x18002baac  jz      short loc_18002BAB2
0x18002baae  inc     ecx
0x18002bab0  jmp     short loc_18002BA97
0x18002bab2  or      byte ptr [rdi], 2
0x18002bab5  nop
0x18002bab6  cmp     [rdi+7], r14b
0x18002baba  jge     short loc_18002BAFC
0x18002babc  xorps   xmm0, xmm0
0x18002babf  lea     r8, [rsp+48h+var_28]
0x18002bac4  movups  [rsp+48h+var_28], xmm0
0x18002bac9  mov     rax, gs:30h
0x18002bad2  mov     rcx, rdi
0x18002bad5  mov     r9d, 10h
0x18002badb  mov     edx, 38h ; '8'
0x18002bae0  sub     rcx, [rax+1850h]
0x18002bae7  sar     rcx, 3
0x18002baeb  mov     qword ptr [rsp+48h+var_28], rcx
0x18002baf0  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18002baf7  call    NtSetInformationThread
0x18002bafc  mov     [rdi], r14
0x18002baff  mov     r14, [rsp+48h+var_18]
0x18002bb04  mov     rdi, [rsp+48h+var_10]
0x18002bb09  mov     rsi, [rsp+48h+var_8]
0x18002bb0e  test    rbx, rbx
0x18002bb11  jz      short loc_18002BB2A
0x18002bb13  mov     rcx, gs:60h
0x18002bb1c  mov     r8, rbx
0x18002bb1f  xor     edx, edx
0x18002bb21  mov     rcx, [rcx+30h]
0x18002bb25  call    RtlFreeHeap_0
0x18002bb2a  mov     rbx, [rsp+48h+arg_8]
0x18002bb2f  add     rsp, 48h
0x18002bb33  retn
0x18002bb35  mov     ecx, eax
0x18002bb37  cmp     [rdx+rcx*8], r14
0x18002bb3b  lea     r8, [rdx+rcx*8]
0x18002bb3f  jz      short loc_18002BB48
0x18002bb41  inc     eax
0x18002bb43  jmp     loc_18002BA36
0x18002bb48  mov     [r8], rsi
0x18002bb4b  jmp     loc_18002BA3F
0x18002bb50  mov     r8d, 3
0x18002bb56  movzx   ecx, al
0x18002bb59  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18002bb60  and     cl, 6
0x18002bb63  cmp     cl, 2
0x18002bb66  cmovz   rdx, r8
0x18002bb6a  lea     rcx, [rdx+rax]
0x18002bb6e  lock cmpxchg cs:RtlpCachedPathLock, rcx
0x18002bb77  jnz     short loc_18002BB56
0x18002bb79  cmp     rdx, r8
0x18002bb7c  jnz     loc_18002BA72
0x18002bb82  mov     [rsp+48h+arg_10], rbp
0x18002bb87  mov     rbp, rsi
0x18002bb8a  test    cl, 1
0x18002bb8d  jnz     loc_18002BC2F
0x18002bb93  mov     r9, rcx
0x18002bb96  and     r9, 0FFFFFFFFFFFFFFF0h
0x18002bb9a  mov     rdx, r9
0x18002bb9d  mov     r8, [r9+8]
0x18002bba1  test    r8, r8
0x18002bba4  jnz     short loc_18002BBC2
0x18002bba6  mov     rax, rdx
0x18002bba9  mov     rdx, [rdx]
0x18002bbac  mov     [rdx+10h], rax
0x18002bbb0  mov     r8, [rdx+8]
0x18002bbb4  test    r8, r8
0x18002bbb7  jz      short loc_18002BBA6
0x18002bbb9  cmp     rdx, r9
0x18002bbbc  jz      short loc_18002BBC2
0x18002bbbe  mov     [r9+8], r8
0x18002bbc2  mov     eax, [r8+24h]
0x18002bbc6  test    al, 1
0x18002bbc8  jz      short loc_18002BBD3
0x18002bbca  mov     rax, [r8+10h]
0x18002bbce  test    rax, rax
0x18002bbd1  jnz     short loc_18002BBEC
0x18002bbd3  mov     rbp, r14
0x18002bbd6  mov     rdx, r14
0x18002bbd9  mov     rax, rcx
0x18002bbdc  lock cmpxchg cs:RtlpCachedPathLock, rdx
0x18002bbe5  mov     rcx, rax
0x18002bbe8  jnz     short loc_18002BB8A
0x18002bbea  jmp     short loc_18002BBFD
0x18002bbec  mov     [r9+8], rax
0x18002bbf0  mov     [r8+10h], r14
0x18002bbf4  lock and cs:RtlpCachedPathLock, 0FFFFFFFFFFFFFFFBh
0x18002bbfd  mov     rdi, [r8+10h]
0x18002bc01  mov     rcx, [r8+18h]
0x18002bc05  lock bts dword ptr [r8+24h], 2
0x18002bc0c  lock btr dword ptr [r8+24h], 1
0x18002bc13  jb      short loc_18002BC1D
0x18002bc15  mov     rdx, rbp
0x18002bc18  call    ZwAlertThreadByThreadIdEx
0x18002bc1d  mov     r8, rdi
0x18002bc20  test    rdi, rdi
0x18002bc23  jnz     short loc_18002BBFD
0x18002bc25  mov     rbp, [rsp+48h+arg_10]
0x18002bc2a  jmp     loc_18002BA72
0x18002bc2f  lea     rdx, [rcx-4]
0x18002bc33  mov     rax, rcx
0x18002bc36  lock cmpxchg cs:RtlpCachedPathLock, rdx
0x18002bc3f  mov     rcx, rax
0x18002bc42  jnz     loc_18002BB8A
0x18002bc48  mov     rbp, [rsp+48h+arg_10]
0x18002bc4d  jmp     loc_18002BA72
0x18002bc52  mov     rcx, rsi
0x18002bc55  call    RtlpAcquireSRWLockExclusiveContended
0x18002bc5a  jmp     loc_18002BA4B
0x18002bc5f  mov     rbx, r14
0x18002bc62  jmp     loc_18002BA56
```
