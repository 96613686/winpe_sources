# LdrpReleaseDllPath

- ea: `0x18002c6f0`
- end: `0x18002c967`
- name: `LdrpReleaseDllPath`
- size: `631`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b9b0`
- `0x18002c2f0`
- `0x18002c4b0`
- `0x180053390`
- `0x1800bbb90`
- `0x1800bc71c`
- `0x1800bc9c0`
- `0x1800bd6e0`
- `0x1800be2e0`
- `0x1800d6508`
- `0x1800fb05c`
- `0x180105288`
- `0x180106c24`
- `0x1801253a0`
- `0x18015b538`

## callees

- `0x18001861c`
- `0x18002c6f0`
- `0x18002dae0`
- `0x18015e470`
- `0x18015f100`

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
      RtlpAcquireSRWLockExclusiveContended(&RtlpCachedPathLock, SchedulerSharedDataSlot);
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
0x18002c6f0  sub     rsp, 48h
0x18002c6f4  cmp     byte ptr [rcx+7Ch], 0
0x18002c6f8  jz      loc_18002C82F
0x18002c6fe  mov     rax, gs:30h
0x18002c707  mov     [rsp+48h+arg_8], rbx
0x18002c70c  mov     rbx, [rcx]
0x18002c70f  mov     [rsp+48h+var_8], rsi
0x18002c714  add     rbx, 0FFFFFFFFFFFFFF80h
0x18002c718  mov     rdx, [rax+1850h]
0x18002c71f  lea     rsi, RtlpCachedPathLock
0x18002c726  mov     [rsp+48h+var_18], r14
0x18002c72b  xor     r14d, r14d
0x18002c72e  test    rdx, rdx
0x18002c731  jz      short loc_18002C73F
0x18002c733  mov     eax, r14d
0x18002c736  cmp     eax, 8
0x18002c739  jb      loc_18002C835
0x18002c73f  lock bts qword ptr [rsi], 0
0x18002c745  jb      loc_18002C952
0x18002c74b  sub     qword ptr [rbx+50h], 1
0x18002c750  jnz     loc_18002C95F
0x18002c756  mov     [rsp+48h+var_10], rdi
0x18002c75b  mov     rcx, r14
0x18002c75e  mov     eax, 1
0x18002c763  lock cmpxchg cs:RtlpCachedPathLock, rcx
0x18002c76c  jnz     loc_18002C850
0x18002c772  mov     rax, gs:30h
0x18002c77b  mov     rdx, [rax+1850h]
0x18002c782  test    rdx, rdx
0x18002c785  jz      short loc_18002C7FF
0x18002c787  mov     r8, 7FFFFFFFFFFFFFFCh
0x18002c791  mov     ecx, r14d
0x18002c794  and     rsi, r8
0x18002c797  cmp     ecx, 8
0x18002c79a  jnb     short loc_18002C7FF
0x18002c79c  mov     eax, ecx
0x18002c79e  lea     rdi, [rdx+rax*8]
0x18002c7a2  mov     rax, [rdx+rax*8]
0x18002c7a6  and     rax, r8
0x18002c7a9  cmp     rax, rsi
0x18002c7ac  jz      short loc_18002C7B2
0x18002c7ae  inc     ecx
0x18002c7b0  jmp     short loc_18002C797
0x18002c7b2  or      byte ptr [rdi], 2
0x18002c7b5  nop
0x18002c7b6  cmp     [rdi+7], r14b
0x18002c7ba  jge     short loc_18002C7FC
0x18002c7bc  xorps   xmm0, xmm0
0x18002c7bf  lea     r8, [rsp+48h+var_28]
0x18002c7c4  movups  [rsp+48h+var_28], xmm0
0x18002c7c9  mov     rax, gs:30h
0x18002c7d2  mov     rcx, rdi
0x18002c7d5  mov     r9d, 10h
0x18002c7db  mov     edx, 38h ; '8'
0x18002c7e0  sub     rcx, [rax+1850h]
0x18002c7e7  sar     rcx, 3
0x18002c7eb  mov     qword ptr [rsp+48h+var_28], rcx
0x18002c7f0  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18002c7f7  call    NtSetInformationThread
0x18002c7fc  mov     [rdi], r14
0x18002c7ff  mov     r14, [rsp+48h+var_18]
0x18002c804  mov     rdi, [rsp+48h+var_10]
0x18002c809  mov     rsi, [rsp+48h+var_8]
0x18002c80e  test    rbx, rbx
0x18002c811  jz      short loc_18002C82A
0x18002c813  mov     rcx, gs:60h
0x18002c81c  mov     r8, rbx
0x18002c81f  xor     edx, edx
0x18002c821  mov     rcx, [rcx+30h]
0x18002c825  call    RtlFreeHeap_0
0x18002c82a  mov     rbx, [rsp+48h+arg_8]
0x18002c82f  add     rsp, 48h
0x18002c833  retn
0x18002c835  mov     ecx, eax
0x18002c837  cmp     [rdx+rcx*8], r14
0x18002c83b  lea     r8, [rdx+rcx*8]
0x18002c83f  jz      short loc_18002C848
0x18002c841  inc     eax
0x18002c843  jmp     loc_18002C736
0x18002c848  mov     [r8], rsi
0x18002c84b  jmp     loc_18002C73F
0x18002c850  mov     r8d, 3
0x18002c856  movzx   ecx, al
0x18002c859  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18002c860  and     cl, 6
0x18002c863  cmp     cl, 2
0x18002c866  cmovz   rdx, r8
0x18002c86a  lea     rcx, [rdx+rax]
0x18002c86e  lock cmpxchg cs:RtlpCachedPathLock, rcx
0x18002c877  jnz     short loc_18002C856
0x18002c879  cmp     rdx, r8
0x18002c87c  jnz     loc_18002C772
0x18002c882  mov     [rsp+48h+arg_10], rbp
0x18002c887  mov     rbp, rsi
0x18002c88a  test    cl, 1
0x18002c88d  jnz     loc_18002C92F
0x18002c893  mov     r9, rcx
0x18002c896  and     r9, 0FFFFFFFFFFFFFFF0h
0x18002c89a  mov     rdx, r9
0x18002c89d  mov     r8, [r9+8]
0x18002c8a1  test    r8, r8
0x18002c8a4  jnz     short loc_18002C8C2
0x18002c8a6  mov     rax, rdx
0x18002c8a9  mov     rdx, [rdx]
0x18002c8ac  mov     [rdx+10h], rax
0x18002c8b0  mov     r8, [rdx+8]
0x18002c8b4  test    r8, r8
0x18002c8b7  jz      short loc_18002C8A6
0x18002c8b9  cmp     rdx, r9
0x18002c8bc  jz      short loc_18002C8C2
0x18002c8be  mov     [r9+8], r8
0x18002c8c2  mov     eax, [r8+24h]
0x18002c8c6  test    al, 1
0x18002c8c8  jz      short loc_18002C8D3
0x18002c8ca  mov     rax, [r8+10h]
0x18002c8ce  test    rax, rax
0x18002c8d1  jnz     short loc_18002C8EC
0x18002c8d3  mov     rbp, r14
0x18002c8d6  mov     rdx, r14
0x18002c8d9  mov     rax, rcx
0x18002c8dc  lock cmpxchg cs:RtlpCachedPathLock, rdx
0x18002c8e5  mov     rcx, rax
0x18002c8e8  jnz     short loc_18002C88A
0x18002c8ea  jmp     short loc_18002C8FD
0x18002c8ec  mov     [r9+8], rax
0x18002c8f0  mov     [r8+10h], r14
0x18002c8f4  lock and cs:RtlpCachedPathLock, 0FFFFFFFFFFFFFFFBh
0x18002c8fd  mov     rdi, [r8+10h]
0x18002c901  mov     rcx, [r8+18h]
0x18002c905  lock bts dword ptr [r8+24h], 2
0x18002c90c  lock btr dword ptr [r8+24h], 1
0x18002c913  jb      short loc_18002C91D
0x18002c915  mov     rdx, rbp
0x18002c918  call    ZwAlertThreadByThreadIdEx
0x18002c91d  mov     r8, rdi
0x18002c920  test    rdi, rdi
0x18002c923  jnz     short loc_18002C8FD
0x18002c925  mov     rbp, [rsp+48h+arg_10]
0x18002c92a  jmp     loc_18002C772
0x18002c92f  lea     rdx, [rcx-4]
0x18002c933  mov     rax, rcx
0x18002c936  lock cmpxchg cs:RtlpCachedPathLock, rdx
0x18002c93f  mov     rcx, rax
0x18002c942  jnz     loc_18002C88A
0x18002c948  mov     rbp, [rsp+48h+arg_10]
0x18002c94d  jmp     loc_18002C772
0x18002c952  mov     rcx, rsi
0x18002c955  call    RtlpAcquireSRWLockExclusiveContended
0x18002c95a  jmp     loc_18002C74B
0x18002c95f  mov     rbx, r14
0x18002c962  jmp     loc_18002C756
```
