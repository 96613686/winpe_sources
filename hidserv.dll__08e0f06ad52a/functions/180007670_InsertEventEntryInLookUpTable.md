# InsertEventEntryInLookUpTable

- ea: `0x180007670`
- end: `0x180007980`
- name: `InsertEventEntryInLookUpTable`
- size: `784`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800081d4`

## callees

- `0x18000718c`
- `0x180007498`
- `0x180007670`
- `0x180008406`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000794a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000794a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000774e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000774e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007959`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007967`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007967`

## pseudocode

```c
__int64 __fastcall InsertEventEntryInLookUpTable(__int64 a1, __int128 *a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v5; // rbx
  signed __int64 v6; // rsi
  unsigned int v7; // r8d
  unsigned __int64 v8; // r10
  __int64 v9; // r15
  int v10; // eax
  unsigned __int8 v11; // bp
  unsigned __int8 v12; // r12
  unsigned __int8 i; // dl
  unsigned __int64 j; // r9
  int v15; // eax
  int v16; // r13d
  __int64 v17; // rdx
  volatile signed __int64 *k; // rdi
  unsigned int v19; // eax
  volatile signed __int64 v20; // r14
  int v21; // eax
  __int64 v22; // r15
  unsigned int m; // edi
  __int64 v24; // rcx
  unsigned int v25; // edi
  unsigned int v26; // eax
  __int64 v27; // r9
  signed __int64 v28; // r8
  __int64 v29; // rax
  int v30; // r10d
  volatile signed __int64 *v31; // rdx
  signed __int64 v32; // rax
  volatile signed __int64 v33; // rtt
  void *v34; // rbx
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *SRWLock; // [rsp+30h] [rbp-58h]
  signed __int64 v38; // [rsp+90h] [rbp+8h] BYREF
  __int128 *v39; // [rsp+98h] [rbp+10h]
  unsigned int v40; // [rsp+A0h] [rbp+18h]
  __int64 v41; // [rsp+A8h] [rbp+20h]

  v41 = a4;
  v39 = a2;
  v5 = qword_18000D030;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  v40 = 0;
  v8 = 0;
  v9 = a4;
  do
  {
    v10 = *(unsigned __int8 *)(a4 + v8++ + 16);
    v7 = (1025 * (v7 + v10)) ^ ((1025 * (v7 + v10)) >> 6);
  }
  while ( v8 < 8 );
  v11 = 2;
  v12 = a5 + 2;
  for ( i = a5 + 2; i < 7u; ++i )
  {
    for ( j = 0; j < *(unsigned int *)(v9 + 16LL * i + 8); v7 = (1025 * (v7 + v15)) ^ ((1025 * (v7 + v15)) >> 6) )
      v15 = *(unsigned __int8 *)(*(_QWORD *)(v9 + 16LL * i) + j++);
  }
  v16 = 32769 * ((9 * v7) ^ ((9 * v7) >> 11));
  SRWLock = (RTL_SRWLOCK *)(qword_18000D030 + 264);
  AcquireSRWLockShared((PSRWLOCK)(qword_18000D030 + 264));
  for ( k = (volatile signed __int64 *)(v5 + 8LL * (v16 & 0x1F));
        ;
        k = (volatile signed __int64 *)(v20 + (((__int64)v21 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32) )
  {
    if ( !*k )
    {
      if ( *(_DWORD *)(v5 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v5 + 300);
        v25 = 234;
        goto LABEL_47;
      }
      if ( !v6 )
      {
        v19 = CreateNewEventEntry(v39, v17, v9, a5, v16, &v38);
        v6 = v38;
        v40 = v19;
        if ( !v38 )
        {
          v25 = v19;
          if ( v19 == 8 )
            ++*(_DWORD *)(v5 + 304);
          else
            ++*(_DWORD *)(v5 + 308);
          goto LABEL_47;
        }
      }
      if ( !_InterlockedCompareExchange64(k, v6, 0) )
      {
        v6 = 0;
        if ( _InterlockedIncrement((volatile signed __int32 *)(v5 + 256)) == 1 )
          EnableFlushTimer(*(struct _TP_TIMER **)(v5 + 344), *(_DWORD *)(v5 + 352));
        v26 = *(_DWORD *)(v5 + 256);
        v25 = v40;
        if ( *(_DWORD *)(v5 + 288) < v26 )
          *(_DWORD *)(v5 + 288) = v26;
        goto LABEL_47;
      }
    }
    v20 = *k;
    if ( v16 == *(_DWORD *)(*k + 40) )
    {
      v22 = *(_QWORD *)(v20 + 16);
      v21 = memcmp_0((const void *)(v41 + 16), (const void *)(v22 + 16), 8u);
      if ( !v21 )
      {
        for ( m = *(unsigned __int8 *)(v20 + 45) + 2; m < 7; ++m )
        {
          v24 = 16LL * m;
          v21 = *(_DWORD *)(v24 + v41 + 8) - *(_DWORD *)(v24 + v22 + 8);
          if ( v21 )
            goto LABEL_22;
          v21 = memcmp_0(*(const void **)(v24 + v41), *(const void **)(v24 + v22), *(unsigned int *)(v24 + v41 + 8));
          if ( v21 )
            goto LABEL_22;
        }
        v21 = 0;
      }
LABEL_22:
      v9 = v41;
    }
    else
    {
      v21 = v16 - *(_DWORD *)(v20 + 40);
    }
    if ( !v21 )
      break;
  }
  if ( v20 && v12 > 2u )
  {
    v27 = 2;
    do
    {
      v28 = **(_QWORD **)(v9 + 16 * v27);
      v29 = *(_QWORD *)(v20 + 16);
      v30 = *(unsigned __int8 *)(v29 + 16 * v27 + 13);
      v31 = *(volatile signed __int64 **)(v29 + 16 * v27);
      if ( v30 == 113 )
      {
        _InterlockedAdd64(v31, v28);
      }
      else if ( (unsigned int)*(unsigned __int8 *)(v29 + 16 * v27 + 13) - 114 <= 1 )
      {
        do
        {
          v32 = *v31;
          if ( v30 == 114 )
          {
            if ( v28 >= v32 )
              break;
          }
          else if ( v28 <= v32 )
          {
            break;
          }
          v33 = *v31;
        }
        while ( v33 != _InterlockedCompareExchange64(v31, v28, v32) );
      }
      ++v11;
      ++v27;
    }
    while ( v11 < v12 );
  }
  v25 = v40;
LABEL_47:
  ReleaseSRWLockShared(SRWLock);
  if ( v6 )
  {
    v34 = *(void **)(v6 + 16);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v34);
  }
  return v25;
}

```

## disassembly

```asm
0x180007670  mov     rax, rsp
0x180007673  mov     [rax+20h], r9
0x180007677  mov     [rax+18h], r8b
0x18000767b  mov     [rax+10h], rdx
0x18000767f  mov     [rax+8], rcx
0x180007683  push    rbx
0x180007684  push    rbp
0x180007685  push    rsi
0x180007686  push    rdi
0x180007687  push    r12
0x180007689  push    r13
0x18000768b  push    r14
0x18000768d  push    r15
0x18000768f  sub     rsp, 48h
0x180007693  mov     rbx, cs:qword_18000D030
0x18000769a  xor     esi, esi
0x18000769c  xor     r14d, r14d
0x18000769f  mov     [rax+8], rsi
0x1800076a3  xor     r8d, r8d
0x1800076a6  mov     [rsp+88h+arg_10], r14d
0x1800076ae  xor     r10d, r10d
0x1800076b1  mov     r15, r9
0x1800076b4  movzx   eax, byte ptr [r9+r10+10h]
0x1800076ba  inc     r10
0x1800076bd  add     eax, r8d
0x1800076c0  imul    ecx, eax, 401h
0x1800076c6  mov     r8d, ecx
0x1800076c9  shr     r8d, 6
0x1800076cd  xor     r8d, ecx
0x1800076d0  cmp     r10, 8
0x1800076d4  jb      short loc_1800076B4
0x1800076d6  mov     r12b, [rsp+88h+arg_20]
0x1800076de  mov     ebp, 2
0x1800076e3  add     r12b, bpl
0x1800076e6  mov     dl, r12b
0x1800076e9  cmp     r12b, 7
0x1800076ed  jnb     short loc_18000772D
0x1800076ef  movzx   eax, dl
0x1800076f2  xor     r9d, r9d
0x1800076f5  add     rax, rax
0x1800076f8  mov     r10d, [r15+rax*8+8]
0x1800076fd  mov     r11, [r15+rax*8]
0x180007701  test    r10, r10
0x180007704  jz      short loc_180007726
0x180007706  movzx   eax, byte ptr [r11+r9]
0x18000770b  inc     r9
0x18000770e  add     eax, r8d
0x180007711  imul    ecx, eax, 401h
0x180007717  mov     r8d, ecx
0x18000771a  shr     r8d, 6
0x18000771e  xor     r8d, ecx
0x180007721  cmp     r9, r10
0x180007724  jb      short loc_180007706
0x180007726  inc     dl
0x180007728  cmp     dl, 7
0x18000772b  jb      short loc_1800076EF
0x18000772d  lea     eax, [r8+r8*8]
0x180007731  mov     ecx, eax
0x180007733  shr     ecx, 0Bh
0x180007736  xor     ecx, eax
0x180007738  lea     rax, [rbx+108h]
0x18000773f  imul    r13d, ecx, 8001h
0x180007746  mov     rcx, rax; SRWLock
0x180007749  mov     [rsp+88h+SRWLock], rax
0x18000774e  call    cs:__imp_AcquireSRWLockShared
0x180007754  mov     eax, r13d
0x180007757  and     eax, 1Fh
0x18000775a  lea     rdi, [rbx+rax*8]
0x18000775e  cmp     qword ptr [rdi], 0
0x180007762  jnz     short loc_1800077C8
0x180007764  cmp     dword ptr [rbx+100h], 400h
0x18000776e  jnb     loc_1800078CA
0x180007774  test    rsi, rsi
0x180007777  jnz     short loc_1800077BB
0x180007779  mov     r9b, [rsp+88h+arg_20]
0x180007781  lea     rax, [rsp+88h+arg_0]
0x180007789  mov     rcx, [rsp+88h+arg_8]
0x180007791  mov     r8, r15
0x180007794  mov     [rsp+88h+var_60], rax
0x180007799  mov     [rsp+88h+var_68], r13d
0x18000779e  call    CreateNewEventEntry
0x1800077a3  mov     rsi, [rsp+88h+arg_0]
0x1800077ab  mov     [rsp+88h+arg_10], eax
0x1800077b2  test    rsi, rsi
0x1800077b5  jz      loc_180007866
0x1800077bb  xor     eax, eax
0x1800077bd  lock cmpxchg [rdi], rsi
0x1800077c2  jz      loc_180007883
0x1800077c8  mov     r14, [rdi]
0x1800077cb  cmp     r13d, [r14+28h]
0x1800077cf  jz      short loc_1800077DA
0x1800077d1  mov     eax, r13d
0x1800077d4  sub     eax, [r14+28h]
0x1800077d8  jmp     short loc_180007847
0x1800077da  mov     r15, [r14+10h]
0x1800077de  mov     r8d, 8; Size
0x1800077e4  mov     rcx, [rsp+88h+arg_18]
0x1800077ec  add     rcx, 10h; Buf1
0x1800077f0  lea     rdx, [r15+10h]; Buf2
0x1800077f4  call    memcmp_0
0x1800077f9  test    eax, eax
0x1800077fb  jnz     short loc_18000783F
0x1800077fd  movzx   edi, byte ptr [r14+2Dh]
0x180007802  add     edi, ebp
0x180007804  jmp     short loc_180007838
0x180007806  mov     r9, [rsp+88h+arg_18]
0x18000780e  mov     ecx, edi
0x180007810  shl     rcx, 4
0x180007814  mov     eax, [rcx+r9+8]
0x180007819  sub     eax, [rcx+r15+8]
0x18000781e  jnz     short loc_18000783F
0x180007820  mov     r8d, [rcx+r9+8]; Size
0x180007825  mov     rdx, [rcx+r15]; Buf2
0x180007829  mov     rcx, [rcx+r9]; Buf1
0x18000782d  call    memcmp_0
0x180007832  test    eax, eax
0x180007834  jnz     short loc_18000783F
0x180007836  inc     edi
0x180007838  cmp     edi, 7
0x18000783b  jb      short loc_180007806
0x18000783d  xor     eax, eax
0x18000783f  mov     r15, [rsp+88h+arg_18]
0x180007847  test    eax, eax
0x180007849  jz      loc_1800078D7
0x18000784f  movsxd  rdi, eax
0x180007852  sar     rdi, 3Fh
0x180007856  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18000785a  add     rdi, 20h ; ' '
0x18000785e  add     rdi, r14
0x180007861  jmp     loc_18000775E
0x180007866  mov     edi, eax
0x180007868  cmp     eax, 8
0x18000786b  jnz     short loc_180007878
0x18000786d  inc     dword ptr [rbx+130h]
0x180007873  jmp     loc_180007945
0x180007878  inc     dword ptr [rbx+134h]
0x18000787e  jmp     loc_180007945
0x180007883  xor     esi, esi
0x180007885  lea     eax, [rsi+1]
0x180007888  lock xadd [rbx+100h], eax
0x180007890  inc     eax
0x180007892  cmp     eax, 1
0x180007895  jnz     short loc_1800078A9
0x180007897  mov     edx, [rbx+160h]
0x18000789d  mov     rcx, [rbx+158h]
0x1800078a4  call    EnableFlushTimer
0x1800078a9  mov     eax, [rbx+100h]
0x1800078af  mov     edi, [rsp+88h+arg_10]
0x1800078b6  cmp     [rbx+120h], eax
0x1800078bc  jnb     loc_180007945
0x1800078c2  mov     [rbx+120h], eax
0x1800078c8  jmp     short loc_180007945
0x1800078ca  inc     dword ptr [rbx+12Ch]
0x1800078d0  mov     edi, 0EAh
0x1800078d5  jmp     short loc_180007945
0x1800078d7  test    r14, r14
0x1800078da  jz      short loc_18000793E
0x1800078dc  cmp     r12b, bpl
0x1800078df  jbe     short loc_18000793E
0x1800078e1  mov     r9, rbp
0x1800078e4  mov     rcx, r9
0x1800078e7  add     rcx, rcx
0x1800078ea  mov     rax, [r15+rcx*8]
0x1800078ee  mov     r8, [rax]
0x1800078f1  mov     rax, [r14+10h]
0x1800078f5  movzx   r10d, byte ptr [rax+rcx*8+0Dh]
0x1800078fb  mov     rdx, [rax+rcx*8]
0x1800078ff  mov     ecx, r10d
0x180007902  sub     ecx, 71h ; 'q'
0x180007905  jz      short loc_18000792F
0x180007907  sub     ecx, 1
0x18000790a  jz      short loc_180007911
0x18000790c  cmp     ecx, 1
0x18000790f  jnz     short loc_180007933
0x180007911  mov     rax, [rdx]
0x180007914  cmp     r10d, 72h ; 'r'
0x180007918  jnz     short loc_180007921
0x18000791a  cmp     r8, rax
0x18000791d  jge     short loc_180007933
0x18000791f  jmp     short loc_180007926
0x180007921  cmp     r8, rax
0x180007924  jle     short loc_180007933
0x180007926  lock cmpxchg [rdx], r8
0x18000792b  jnz     short loc_180007911
0x18000792d  jmp     short loc_180007933
0x18000792f  lock add [rdx], r8
0x180007933  inc     bpl
0x180007936  inc     r9
0x180007939  cmp     bpl, r12b
0x18000793c  jb      short loc_1800078E4
0x18000793e  mov     edi, [rsp+88h+arg_10]
0x180007945  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x18000794a  call    cs:__imp_ReleaseSRWLockShared
0x180007950  test    rsi, rsi
0x180007953  jz      short loc_18000796D
0x180007955  mov     rbx, [rsi+10h]
0x180007959  call    cs:__imp_GetProcessHeap
0x18000795f  mov     r8, rbx; lpMem
0x180007962  xor     edx, edx; dwFlags
0x180007964  mov     rcx, rax; hHeap
0x180007967  call    cs:__imp_HeapFree
0x18000796d  mov     eax, edi
0x18000796f  add     rsp, 48h
0x180007973  pop     r15
0x180007975  pop     r14
0x180007977  pop     r13
0x180007979  pop     r12
0x18000797b  pop     rdi
0x18000797c  pop     rsi
0x18000797d  pop     rbp
0x18000797e  pop     rbx
0x18000797f  retn
```
