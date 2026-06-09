# InsertEventEntryInLookUpTable

- ea: `0x180004120`
- end: `0x180004443`
- name: `InsertEventEntryInLookUpTable`
- size: `803`
- prototype: `__int64 __fastcall(__int64, __int128 *, unsigned __int8, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004c94`

## callees

- `0x180003c38`
- `0x180003f54`
- `0x180004120`
- `0x180004ed6`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000442a`
- `KERNEL32!HeapFree` at `0x18000442a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000440d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000440d`
- `KERNEL32!AcquireSRWLockShared` at `0x1800041fd`
- `KERNEL32!AcquireSRWLockShared` at `0x1800041fd`
- `KERNEL32!GetProcessHeap` at `0x18000441c`
- `KERNEL32!GetProcessHeap` at `0x18000441c`

## pseudocode

```c
__int64 __fastcall InsertEventEntryInLookUpTable(__int64 a1, __int128 *a2, unsigned __int8 a3, __int64 a4, char a5)
{
  __int64 v5; // rbx
  char *v6; // rsi
  unsigned int v7; // r10d
  unsigned __int64 v8; // r11
  __int64 v9; // r13
  unsigned __int8 v10; // r14
  int v11; // eax
  unsigned __int8 v12; // bp
  unsigned __int8 v13; // r12
  unsigned __int8 v14; // dl
  unsigned __int64 i; // r8
  int v16; // eax
  int v17; // r15d
  volatile signed __int64 *v18; // rdi
  unsigned int v19; // eax
  volatile signed __int64 v20; // r14
  int v21; // eax
  __int64 v22; // r13
  unsigned int j; // edi
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
  int v37; // [rsp+30h] [rbp-68h]
  char *v38; // [rsp+38h] [rbp-60h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-58h]
  unsigned int v40; // [rsp+A0h] [rbp+8h]

  v5 = *(_QWORD *)(a1 + 48);
  v6 = 0;
  v38 = 0;
  v7 = 0;
  v40 = 0;
  v8 = 0;
  v9 = a4;
  v10 = a3;
  do
  {
    v11 = *(unsigned __int8 *)(v8 + a4 + 16);
    ++v8;
    v7 = (1025 * (v7 + v11)) ^ ((1025 * (v7 + v11)) >> 6);
  }
  while ( v8 < 8 );
  v12 = 2;
  v13 = a5 + 2;
  v14 = a5 + 2;
  if ( (unsigned __int8)(a5 + 2) < a3 )
  {
    do
    {
      for ( i = 0; i < *(unsigned int *)(a4 + 16LL * v14 + 8); v7 = (1025 * (v7 + v16)) ^ ((1025 * (v7 + v16)) >> 6) )
        v16 = *(unsigned __int8 *)(*(_QWORD *)(a4 + 16LL * v14) + i++);
      ++v14;
    }
    while ( v14 < v10 );
  }
  v17 = 32769 * ((9 * v7) ^ ((9 * v7) >> 11));
  SRWLock = (PSRWLOCK)(v5 + 264);
  v37 = v17;
  AcquireSRWLockShared((PSRWLOCK)(v5 + 264));
  v18 = (volatile signed __int64 *)(v5 + 8LL * (v17 & 0x1F));
  while ( 1 )
  {
    if ( !*v18 )
    {
      if ( *(_DWORD *)(v5 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v5 + 300);
        v25 = 234;
        goto LABEL_48;
      }
      if ( !v6 )
      {
        v19 = CreateNewEventEntry(a2, v10, v9, a5, v17, &v38);
        v6 = v38;
        v40 = v19;
        if ( !v38 )
        {
          v25 = v19;
          if ( v19 == 8 )
            ++*(_DWORD *)(v5 + 304);
          else
            ++*(_DWORD *)(v5 + 308);
          goto LABEL_48;
        }
      }
      if ( !_InterlockedCompareExchange64(v18, (signed __int64)v6, 0) )
      {
        v6 = 0;
        if ( _InterlockedIncrement((volatile signed __int32 *)(v5 + 256)) == 1 )
          EnableFlushTimer(*(struct _TP_TIMER **)(v5 + 344), *(_DWORD *)(v5 + 352));
        v26 = *(_DWORD *)(v5 + 256);
        v25 = v40;
        if ( *(_DWORD *)(v5 + 288) < v26 )
          *(_DWORD *)(v5 + 288) = v26;
        goto LABEL_48;
      }
    }
    v20 = *v18;
    if ( v17 == *(_DWORD *)(*v18 + 40) )
    {
      v22 = *(_QWORD *)(v20 + 16);
      v21 = memcmp_0((const void *)(a4 + 16), (const void *)(v22 + 16), 8u);
      if ( !v21 )
      {
        for ( j = *(unsigned __int8 *)(v20 + 45) + 2; j < a3; ++j )
        {
          v24 = 16LL * j;
          v21 = *(_DWORD *)(v24 + a4 + 8) - *(_DWORD *)(v24 + v22 + 8);
          if ( v21 )
            goto LABEL_22;
          v21 = memcmp_0(*(const void **)(v24 + a4), *(const void **)(v24 + v22), *(unsigned int *)(v24 + a4 + 8));
          if ( v21 )
            goto LABEL_22;
        }
        v21 = 0;
LABEL_22:
        v17 = v37;
      }
      v9 = a4;
    }
    else
    {
      v21 = v17 - *(_DWORD *)(v20 + 40);
    }
    if ( !v21 )
      break;
    v18 = (volatile signed __int64 *)(v20 + (((__int64)v21 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32);
    v10 = a3;
  }
  if ( v20 && v13 > 2u )
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
      ++v12;
      ++v27;
    }
    while ( v12 < v13 );
  }
  v25 = v40;
LABEL_48:
  ReleaseSRWLockShared(SRWLock);
  if ( v6 )
  {
    v34 = (void *)*((_QWORD *)v6 + 2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v34);
  }
  return v25;
}

```

## disassembly

```asm
0x180004120  mov     rax, rsp
0x180004123  mov     [rax+20h], r9
0x180004127  mov     [rax+18h], r8b
0x18000412b  mov     [rax+10h], rdx
0x18000412f  push    rbx
0x180004130  push    rbp
0x180004131  push    rsi
0x180004132  push    rdi
0x180004133  push    r12
0x180004135  push    r13
0x180004137  push    r14
0x180004139  push    r15
0x18000413b  sub     rsp, 58h
0x18000413f  mov     rbx, [rcx+30h]
0x180004143  xor     esi, esi
0x180004145  xor     edi, edi
0x180004147  mov     [rax-60h], rsi
0x18000414b  xor     r10d, r10d
0x18000414e  mov     [rsp+98h+arg_0], edi
0x180004155  xor     r11d, r11d
0x180004158  mov     r13, r9
0x18000415b  mov     r14b, r8b
0x18000415e  movzx   eax, byte ptr [r11+r9+10h]
0x180004164  inc     r11
0x180004167  add     eax, r10d
0x18000416a  imul    ecx, eax, 401h
0x180004170  mov     r10d, ecx
0x180004173  shr     r10d, 6
0x180004177  xor     r10d, ecx
0x18000417a  cmp     r11, 8
0x18000417e  jb      short loc_18000415E
0x180004180  mov     r12b, [rsp+98h+arg_20]
0x180004188  mov     ebp, 2
0x18000418d  add     r12b, bpl
0x180004190  mov     dl, r12b
0x180004193  cmp     r12b, r14b
0x180004196  jnb     short loc_1800041D7
0x180004198  movzx   eax, dl
0x18000419b  xor     r8d, r8d
0x18000419e  add     rax, rax
0x1800041a1  mov     r9d, [r13+rax*8+8]
0x1800041a6  mov     r11, [r13+rax*8+0]
0x1800041ab  test    r9, r9
0x1800041ae  jz      short loc_1800041D0
0x1800041b0  movzx   eax, byte ptr [r11+r8]
0x1800041b5  inc     r8
0x1800041b8  add     eax, r10d
0x1800041bb  imul    ecx, eax, 401h
0x1800041c1  mov     r10d, ecx
0x1800041c4  shr     r10d, 6
0x1800041c8  xor     r10d, ecx
0x1800041cb  cmp     r8, r9
0x1800041ce  jb      short loc_1800041B0
0x1800041d0  inc     dl
0x1800041d2  cmp     dl, r14b
0x1800041d5  jb      short loc_180004198
0x1800041d7  lea     eax, [r10+r10*8]
0x1800041db  mov     ecx, eax
0x1800041dd  shr     ecx, 0Bh
0x1800041e0  xor     ecx, eax
0x1800041e2  lea     rax, [rbx+108h]
0x1800041e9  imul    r15d, ecx, 8001h
0x1800041f0  mov     rcx, rax; SRWLock
0x1800041f3  mov     [rsp+98h+SRWLock], rax
0x1800041f8  mov     [rsp+98h+var_68], r15d
0x1800041fd  call    cs:__imp_AcquireSRWLockShared
0x180004203  mov     eax, r15d
0x180004206  and     eax, 1Fh
0x180004209  lea     rdi, [rbx+rax*8]
0x18000420d  cmp     qword ptr [rdi], 0
0x180004211  jnz     short loc_180004274
0x180004213  cmp     dword ptr [rbx+100h], 400h
0x18000421d  jnb     loc_18000438C
0x180004223  test    rsi, rsi
0x180004226  jnz     short loc_180004267
0x180004228  mov     r9b, [rsp+98h+arg_20]
0x180004230  lea     rax, [rsp+98h+var_60]
0x180004235  mov     rcx, [rsp+98h+arg_8]
0x18000423d  mov     r8, r13
0x180004240  mov     [rsp+98h+var_70], rax
0x180004245  mov     dl, r14b
0x180004248  mov     [rsp+98h+var_78], r15d
0x18000424d  call    CreateNewEventEntry
0x180004252  mov     rsi, [rsp+98h+var_60]
0x180004257  mov     [rsp+98h+arg_0], eax
0x18000425e  test    rsi, rsi
0x180004261  jz      loc_180004328
0x180004267  xor     eax, eax
0x180004269  lock cmpxchg [rdi], rsi
0x18000426e  jz      loc_180004345
0x180004274  mov     r14, [rdi]
0x180004277  cmp     r15d, [r14+28h]
0x18000427b  jz      short loc_180004286
0x18000427d  mov     eax, r15d
0x180004280  sub     eax, [r14+28h]
0x180004284  jmp     short loc_180004301
0x180004286  mov     r13, [r14+10h]
0x18000428a  mov     r8d, 8; Size
0x180004290  mov     rcx, [rsp+98h+arg_18]
0x180004298  add     rcx, 10h; Buf1
0x18000429c  lea     rdx, [r13+10h]; Buf2
0x1800042a0  call    memcmp_0
0x1800042a5  test    eax, eax
0x1800042a7  jnz     short loc_1800042F9
0x1800042a9  movzx   edi, byte ptr [r14+2Dh]
0x1800042ae  movzx   r15d, [rsp+98h+arg_10]
0x1800042b7  add     edi, ebp
0x1800042b9  jmp     short loc_1800042ED
0x1800042bb  mov     r9, [rsp+98h+arg_18]
0x1800042c3  mov     ecx, edi
0x1800042c5  shl     rcx, 4
0x1800042c9  mov     eax, [rcx+r9+8]
0x1800042ce  sub     eax, [rcx+r13+8]
0x1800042d3  jnz     short loc_1800042F4
0x1800042d5  mov     r8d, [rcx+r9+8]; Size
0x1800042da  mov     rdx, [rcx+r13]; Buf2
0x1800042de  mov     rcx, [rcx+r9]; Buf1
0x1800042e2  call    memcmp_0
0x1800042e7  test    eax, eax
0x1800042e9  jnz     short loc_1800042F4
0x1800042eb  inc     edi
0x1800042ed  cmp     edi, r15d
0x1800042f0  jb      short loc_1800042BB
0x1800042f2  xor     eax, eax
0x1800042f4  mov     r15d, [rsp+98h+var_68]
0x1800042f9  mov     r13, [rsp+98h+arg_18]
0x180004301  test    eax, eax
0x180004303  jz      loc_180004399
0x180004309  movsxd  rdi, eax
0x18000430c  sar     rdi, 3Fh
0x180004310  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180004314  add     rdi, 20h ; ' '
0x180004318  add     rdi, r14
0x18000431b  mov     r14b, [rsp+98h+arg_10]
0x180004323  jmp     loc_18000420D
0x180004328  mov     edi, eax
0x18000432a  cmp     eax, 8
0x18000432d  jnz     short loc_18000433A
0x18000432f  inc     dword ptr [rbx+130h]
0x180004335  jmp     loc_180004408
0x18000433a  inc     dword ptr [rbx+134h]
0x180004340  jmp     loc_180004408
0x180004345  xor     esi, esi
0x180004347  lea     eax, [rsi+1]
0x18000434a  lock xadd [rbx+100h], eax
0x180004352  inc     eax
0x180004354  cmp     eax, 1
0x180004357  jnz     short loc_18000436B
0x180004359  mov     edx, [rbx+160h]
0x18000435f  mov     rcx, [rbx+158h]
0x180004366  call    EnableFlushTimer
0x18000436b  mov     eax, [rbx+100h]
0x180004371  mov     edi, [rsp+98h+arg_0]
0x180004378  cmp     [rbx+120h], eax
0x18000437e  jnb     loc_180004408
0x180004384  mov     [rbx+120h], eax
0x18000438a  jmp     short loc_180004408
0x18000438c  inc     dword ptr [rbx+12Ch]
0x180004392  mov     edi, 0EAh
0x180004397  jmp     short loc_180004408
0x180004399  test    r14, r14
0x18000439c  jz      short loc_180004401
0x18000439e  cmp     r12b, bpl
0x1800043a1  jbe     short loc_180004401
0x1800043a3  mov     r9, rbp
0x1800043a6  mov     rcx, r9
0x1800043a9  add     rcx, rcx
0x1800043ac  mov     rax, [r13+rcx*8+0]
0x1800043b1  mov     r8, [rax]
0x1800043b4  mov     rax, [r14+10h]
0x1800043b8  movzx   r10d, byte ptr [rax+rcx*8+0Dh]
0x1800043be  mov     rdx, [rax+rcx*8]
0x1800043c2  mov     ecx, r10d
0x1800043c5  sub     ecx, 71h ; 'q'
0x1800043c8  jz      short loc_1800043F2
0x1800043ca  sub     ecx, 1
0x1800043cd  jz      short loc_1800043D4
0x1800043cf  cmp     ecx, 1
0x1800043d2  jnz     short loc_1800043F6
0x1800043d4  mov     rax, [rdx]
0x1800043d7  cmp     r10d, 72h ; 'r'
0x1800043db  jnz     short loc_1800043E4
0x1800043dd  cmp     r8, rax
0x1800043e0  jge     short loc_1800043F6
0x1800043e2  jmp     short loc_1800043E9
0x1800043e4  cmp     r8, rax
0x1800043e7  jle     short loc_1800043F6
0x1800043e9  lock cmpxchg [rdx], r8
0x1800043ee  jnz     short loc_1800043D4
0x1800043f0  jmp     short loc_1800043F6
0x1800043f2  lock add [rdx], r8
0x1800043f6  inc     bpl
0x1800043f9  inc     r9
0x1800043fc  cmp     bpl, r12b
0x1800043ff  jb      short loc_1800043A6
0x180004401  mov     edi, [rsp+98h+arg_0]
0x180004408  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x18000440d  call    cs:__imp_ReleaseSRWLockShared
0x180004413  test    rsi, rsi
0x180004416  jz      short loc_180004430
0x180004418  mov     rbx, [rsi+10h]
0x18000441c  call    cs:__imp_GetProcessHeap
0x180004422  mov     r8, rbx; lpMem
0x180004425  xor     edx, edx; dwFlags
0x180004427  mov     rcx, rax; hHeap
0x18000442a  call    cs:__imp_HeapFree
0x180004430  mov     eax, edi
0x180004432  add     rsp, 58h
0x180004436  pop     r15
0x180004438  pop     r14
0x18000443a  pop     r13
0x18000443c  pop     r12
0x18000443e  pop     rdi
0x18000443f  pop     rsi
0x180004440  pop     rbp
0x180004441  pop     rbx
0x180004442  retn
```
