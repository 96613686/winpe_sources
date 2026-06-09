# LdrpCallTlsInitializers

- ea: `0x180050fa0`
- end: `0x18005130b`
- name: `LdrpCallTlsInitializers`
- size: `875`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043490`
- `0x180043be0`
- `0x1800cd1c8`
- `0x1800d61e0`
- `0x1800d6508`
- `0x1800e60a4`

## callees

- `0x18001eb80`
- `0x180050d08`
- `0x180050fa0`
- `0x180051d14`
- `0x180053990`
- `0x180109270`
- `0x18015e470`
- `0x18015f100`

## string_xrefs

- `0x180051124`: `Calling TLS callback %p for DLL "%wZ" at %p\n`

## pseudocode

```c
struct _TEB *__fastcall LdrpCallTlsInitializers(unsigned int a1, __int64 a2)
{
  _QWORD *v4; // r9
  _QWORD *SchedulerSharedDataSlot; // r8
  unsigned int i; // edx
  signed __int64 v7; // rax
  _UNKNOWN **j; // rbx
  signed __int64 v9; // rax
  _BYTE *v10; // rsi
  struct _TEB *result; // rax
  _QWORD *v12; // rdx
  unsigned int n; // ecx
  __int64 *v14; // rbx
  __int64 ArgList; // rsi
  signed __int64 v16; // r8
  signed __int64 v17; // rtt
  _QWORD *v18; // rcx
  __int64 k; // r8
  __int64 v20; // rdx
  signed __int64 v21; // r8
  __int64 v22; // rcx
  signed __int64 v23; // rcx
  signed __int64 v24; // rtt
  __int64 *v25; // r15
  _QWORD *v26; // rdx
  __int64 m; // r8
  __int64 v28; // rax
  bool v29; // zf
  signed __int64 v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // rsi
  __int64 v33; // rcx
  signed __int64 v34; // rax
  __int128 v35[5]; // [rsp+58h] [rbp-50h] BYREF

  v4 = 0;
  SchedulerSharedDataSlot = NtCurrentTeb()->SchedulerSharedDataSlot;
  if ( SchedulerSharedDataSlot )
  {
    for ( i = 0; i < 8; ++i )
    {
      if ( !SchedulerSharedDataSlot[i] )
      {
        v4 = &SchedulerSharedDataSlot[i];
        break;
      }
    }
  }
  if ( v4 )
    *v4 = &LdrpTlsLock;
  v7 = _InterlockedCompareExchange64(&LdrpTlsLock, 17, 0);
  if ( v7 )
    RtlpAcquireSRWLockSharedContended(&LdrpTlsLock, v4, v7);
  for ( j = (_UNKNOWN **)LdrpTlsList; j != &LdrpTlsList; j = (_UNKNOWN **)*j )
  {
    if ( j[7] == (_UNKNOWN *)a2 )
      goto LABEL_16;
  }
  j = 0;
LABEL_16:
  v9 = _InterlockedCompareExchange64(&LdrpTlsLock, 0, 17);
  if ( v9 != 17 )
  {
    if ( (v9 & 1) == 0 )
      RtlRaiseStatus(3221226084LL);
    while ( (v9 & 2) == 0 )
    {
      v16 = 0;
      if ( (v9 & 0xFFFFFFFFFFFFFFF0uLL) != 0x10 )
        v16 = v9 - 16;
      v17 = v9;
      v9 = _InterlockedCompareExchange64(&LdrpTlsLock, v16, v9);
      if ( v17 == v9 )
        goto LABEL_17;
    }
    if ( (v9 & 8) != 0 )
    {
      v18 = (_QWORD *)(v9 & 0xFFFFFFFFFFFFFFF0uLL);
      for ( k = *(_QWORD *)((v9 & 0xFFFFFFFFFFFFFFF0uLL) + 8); !k; k = v18[1] )
        v18 = (_QWORD *)*v18;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(k + 32), 0xFFFFFFFF) > 1 )
        goto LABEL_17;
      v20 = -9;
    }
    else
    {
      v20 = -1;
    }
    do
    {
      v21 = v9 & 6;
      if ( v21 == 2 )
        v22 = v20 + 4;
      else
        v22 = v20;
      v23 = v9 + v22;
      v24 = v9;
      v9 = _InterlockedCompareExchange64(&LdrpTlsLock, v23, v9);
    }
    while ( v24 != v9 );
    if ( v21 == 2 )
    {
      v25 = &LdrpTlsLock;
      while ( 1 )
      {
        while ( (v23 & 1) != 0 )
        {
          v34 = _InterlockedCompareExchange64(&LdrpTlsLock, v23 - 4, v23);
          v29 = v23 == v34;
          v23 = v34;
          if ( v29 )
            goto LABEL_17;
        }
        v26 = (_QWORD *)(v23 & 0xFFFFFFFFFFFFFFF0uLL);
        for ( m = *(_QWORD *)((v23 & 0xFFFFFFFFFFFFFFF0uLL) + 8); !m; m = v26[1] )
        {
          v31 = v26;
          v26 = (_QWORD *)*v26;
          v26[2] = v31;
        }
        if ( v26 != (_QWORD *)(v23 & 0xFFFFFFFFFFFFFFF0uLL) )
          *(_QWORD *)((v23 & 0xFFFFFFFFFFFFFFF0uLL) + 8) = m;
        if ( (*(_DWORD *)(m + 36) & 1) != 0 )
        {
          v28 = *(_QWORD *)(m + 16);
          if ( v28 )
            break;
        }
        v25 = 0;
        v30 = _InterlockedCompareExchange64(&LdrpTlsLock, 0, v23);
        v29 = v23 == v30;
        v23 = v30;
        if ( v29 )
          goto LABEL_62;
      }
      *(_QWORD *)((v23 & 0xFFFFFFFFFFFFFFF0uLL) + 8) = v28;
      *(_QWORD *)(m + 16) = 0;
      _InterlockedAnd64(&LdrpTlsLock, 0xFFFFFFFFFFFFFFFBuLL);
      do
      {
LABEL_62:
        v32 = *(_QWORD *)(m + 16);
        v33 = *(_QWORD *)(m + 24);
        _interlockedbittestandset((volatile signed __int32 *)(m + 36), 2u);
        if ( !_interlockedbittestandreset((volatile signed __int32 *)(m + 36), 1u) )
          ZwAlertThreadByThreadIdEx(v33, v25);
        m = v32;
      }
      while ( v32 );
    }
  }
LABEL_17:
  v10 = 0;
  result = NtCurrentTeb();
  v12 = result->SchedulerSharedDataSlot;
  if ( v12 )
  {
    for ( n = 0; n < 8; ++n )
    {
      result = (struct _TEB *)(v12[n] & 0x7FFFFFFFFFFFFFFCLL);
      if ( result == (struct _TEB *)((unsigned __int64)&LdrpTlsLock & 0x7FFFFFFFFFFFFFFCLL) )
      {
        v10 = &v12[n];
        break;
      }
    }
  }
  if ( v10 )
  {
    *v10 |= 2u;
    if ( (char)v10[7] < 0 )
    {
      v35[0] = 0;
      *(_QWORD *)&v35[0] = (v10 - (char *)NtCurrentTeb()->SchedulerSharedDataSlot) >> 3;
      result = (struct _TEB *)NtSetInformationThread(-2, 56, v35, 16);
    }
    *(_QWORD *)v10 = 0;
  }
  if ( j )
  {
    v14 = (__int64 *)j[5];
    if ( v14 )
    {
      while ( 1 )
      {
        ArgList = *v14;
        if ( !*v14 )
          break;
        ++v14;
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrtls.c",
          1187,
          (int)"LdrpCallTlsInitializers",
          2,
          "Calling TLS callback %p for DLL \"%wZ\" at %p\n",
          ArgList);
        result = (struct _TEB *)LdrpCallInitRoutine(ImageTlsCallbackCaller, *(_QWORD *)(a2 + 48), a1, ArgList);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180050fa0  push    rbx
0x180050fa2  push    rsi
0x180050fa3  push    rdi
0x180050fa4  push    r12
0x180050fa6  push    r13
0x180050fa8  push    r14
0x180050faa  push    r15
0x180050fac  sub     rsp, 70h
0x180050fb0  mov     rdi, rdx
0x180050fb3  mov     r12d, ecx
0x180050fb6  xor     r13d, r13d
0x180050fb9  mov     r9d, r13d
0x180050fbc  mov     rax, gs:30h
0x180050fc5  mov     r8, [rax+1850h]
0x180050fcc  test    r8, r8
0x180050fcf  jz      short loc_180050FEB
0x180050fd1  mov     edx, r13d
0x180050fd4  cmp     edx, 8
0x180050fd7  jnb     short loc_180050FEB
0x180050fd9  mov     eax, edx
0x180050fdb  lea     rcx, [r8+rax*8]
0x180050fdf  cmp     [rcx], r9
0x180050fe2  jz      short loc_180050FE8
0x180050fe4  inc     edx
0x180050fe6  jmp     short loc_180050FD4
0x180050fe8  mov     r9, rcx
0x180050feb  lea     r14, LdrpTlsLock
0x180050ff2  test    r9, r9
0x180050ff5  jz      short loc_180050FFA
0x180050ff7  mov     [r9], r14
0x180050ffa  mov     esi, 11h
0x180050fff  xor     eax, eax
0x180051001  lock cmpxchg cs:LdrpTlsLock, rsi
0x18005100a  jnz     loc_1800510F5
0x180051010  mov     rbx, cs:LdrpTlsList
0x180051017  lea     rax, LdrpTlsList
0x18005101e  xchg    ax, ax
0x180051020  cmp     rbx, rax
0x180051023  jz      short loc_180051030
0x180051025  cmp     [rbx+38h], rdi
0x180051029  jz      short loc_180051033
0x18005102b  mov     rbx, [rbx]
0x18005102e  jmp     short loc_180051020
0x180051030  mov     rbx, r13
0x180051033  mov     rcx, r13
0x180051036  mov     rax, rsi
0x180051039  lock cmpxchg cs:LdrpTlsLock, rcx
0x180051042  jnz     loc_180051108
0x180051048  mov     rsi, r13
0x18005104b  mov     rax, gs:30h
0x180051054  mov     rdx, [rax+1850h]
0x18005105b  test    rdx, rdx
0x18005105e  jz      short loc_18005108D
0x180051060  mov     r9, 7FFFFFFFFFFFFFFCh
0x18005106a  and     r14, r9
0x18005106d  mov     ecx, r13d
0x180051070  cmp     ecx, 8
0x180051073  jnb     short loc_18005108D
0x180051075  mov     eax, ecx
0x180051077  lea     r8, [rdx+rax*8]
0x18005107b  mov     rax, [r8]
0x18005107e  and     rax, r9
0x180051081  cmp     rax, r14
0x180051084  jz      short loc_18005108A
0x180051086  inc     ecx
0x180051088  jmp     short loc_180051070
0x18005108a  mov     rsi, r8
0x18005108d  test    rsi, rsi
0x180051090  jz      short loc_1800510DF
0x180051092  or      byte ptr [rsi], 2
0x180051095  nop
0x180051096  cmp     [rsi+7], r13b
0x18005109a  jge     short loc_1800510DC
0x18005109c  xorps   xmm0, xmm0
0x18005109f  movups  [rsp+0A8h+var_50], xmm0
0x1800510a4  mov     rax, gs:30h
0x1800510ad  mov     rcx, rsi
0x1800510b0  sub     rcx, [rax+1850h]
0x1800510b7  sar     rcx, 3
0x1800510bb  mov     qword ptr [rsp+0A8h+var_50], rcx
0x1800510c0  mov     r9d, 10h
0x1800510c6  lea     r8, [rsp+0A8h+var_50]
0x1800510cb  mov     edx, 38h ; '8'
0x1800510d0  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1800510d7  call    NtSetInformationThread
0x1800510dc  mov     [rsi], r13
0x1800510df  test    rbx, rbx
0x1800510e2  jnz     short loc_18005111B
0x1800510e4  add     rsp, 70h
0x1800510e8  pop     r15
0x1800510ea  pop     r14
0x1800510ec  pop     r13
0x1800510ee  pop     r12
0x1800510f0  pop     rdi
0x1800510f1  pop     rsi
0x1800510f2  pop     rbx
0x1800510f3  retn
0x1800510f5  mov     r8, rax
0x1800510f8  mov     rdx, r9
0x1800510fb  mov     rcx, r14
0x1800510fe  call    RtlpAcquireSRWLockSharedContended
0x180051103  jmp     loc_180051010
0x180051108  test    al, 1
0x18005110a  jnz     loc_180051198
0x180051110  mov     ecx, 0C0000264h
0x180051115  call    RtlRaiseStatus
0x18005111b  mov     rbx, [rbx+28h]
0x18005111f  test    rbx, rbx
0x180051122  jz      short loc_1800510E4
0x180051124  lea     r14, aCallingTlsCall; "Calling TLS callback %p for DLL \"%wZ\""...
0x18005112b  mov     rsi, [rbx]
0x18005112e  test    rsi, rsi
0x180051131  jz      short loc_18005118E
0x180051133  add     rbx, 8
0x180051137  mov     [rsp+0A8h+var_58], rbx
0x18005113c  lea     rcx, [rdi+48h]
0x180051140  mov     rax, [rdi+30h]
0x180051144  mov     [rsp+0A8h+var_70], rax
0x180051149  mov     [rsp+0A8h+var_78], rcx
0x18005114e  mov     qword ptr [rsp+0A8h+ArgList], rsi; ArgList
0x180051153  mov     [rsp+0A8h+Format], r14; Format
0x180051158  mov     r9d, 2; int
0x18005115e  lea     r8, aLdrpcalltlsini; "LdrpCallTlsInitializers"
0x180051165  mov     edx, 4A3h; int
0x18005116a  lea     rcx, aMinkernelLdrLd_1; "minkernel\\ldr\\ldrtls.c"
0x180051171  call    LdrpLogInternal
0x180051176  mov     r9, rsi
0x180051179  mov     r8d, r12d
0x18005117c  mov     rdx, [rdi+30h]
0x180051180  lea     rcx, ImageTlsCallbackCaller
0x180051187  call    LdrpCallInitRoutine
0x18005118c  jmp     short loc_18005112B
0x18005118e  jmp     loc_1800510E4
0x180051193  jmp     loc_1800510E4
0x180051198  test    al, 2
0x18005119a  jnz     short loc_1800511C3
0x18005119c  mov     rdx, rax
0x18005119f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800511a3  lea     rcx, [rax-10h]
0x1800511a7  mov     r8, r13
0x1800511aa  cmp     rdx, 10h
0x1800511ae  cmovnz  r8, rcx
0x1800511b2  lock cmpxchg cs:LdrpTlsLock, r8
0x1800511bb  jz      loc_180051048
0x1800511c1  jmp     short loc_180051198
0x1800511c3  test    al, 8
0x1800511c5  jz      short loc_18005120B
0x1800511c7  mov     rcx, rax
0x1800511ca  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800511ce  mov     r8, [rcx+8]
0x1800511d2  test    r8, r8
0x1800511d5  jnz     short loc_1800511EC
0x1800511d7  nop     word ptr [rax+rax+00000000h]
0x1800511e0  mov     rcx, [rcx]
0x1800511e3  mov     r8, [rcx+8]
0x1800511e7  test    r8, r8
0x1800511ea  jz      short loc_1800511E0
0x1800511ec  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800511f3  lock xadd [r8+20h], edx
0x1800511f9  sub     edx, 1
0x1800511fc  jg      loc_180051048
0x180051202  mov     rdx, 0FFFFFFFFFFFFFFF7h
0x180051209  jmp     short loc_180051212
0x18005120b  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180051212  mov     r8, rax
0x180051215  and     r8d, 6
0x180051219  cmp     r8, 2
0x18005121d  jz      loc_180051302
0x180051223  mov     rcx, rdx
0x180051226  add     rcx, rax
0x180051229  lock cmpxchg cs:LdrpTlsLock, rcx
0x180051232  jnz     short loc_180051212
0x180051234  cmp     r8, 2
0x180051238  jnz     loc_180051048
0x18005123e  mov     r15, r14
0x180051241  test    cl, 1
0x180051244  jnz     loc_1800512E4
0x18005124a  mov     r9, rcx
0x18005124d  and     r9, 0FFFFFFFFFFFFFFF0h
0x180051251  mov     rdx, r9
0x180051254  mov     r8, [r9+8]
0x180051258  test    r8, r8
0x18005125b  jz      short loc_180051290
0x18005125d  cmp     rdx, r9
0x180051260  jz      short loc_180051266
0x180051262  mov     [r9+8], r8
0x180051266  mov     eax, [r8+24h]
0x18005126a  test    al, 1
0x18005126c  jz      short loc_180051277
0x18005126e  mov     rax, [r8+10h]
0x180051272  test    rax, rax
0x180051275  jnz     short loc_1800512A5
0x180051277  mov     r15, r13
0x18005127a  mov     rdx, r13
0x18005127d  mov     rax, rcx
0x180051280  lock cmpxchg cs:LdrpTlsLock, rdx
0x180051289  mov     rcx, rax
0x18005128c  jnz     short loc_180051241
0x18005128e  jmp     short loc_1800512B6
0x180051290  mov     rax, rdx
0x180051293  mov     rdx, [rdx]
0x180051296  mov     [rdx+10h], rax
0x18005129a  mov     r8, [rdx+8]
0x18005129e  test    r8, r8
0x1800512a1  jz      short loc_180051290
0x1800512a3  jmp     short loc_18005125D
0x1800512a5  mov     [r9+8], rax
0x1800512a9  mov     [r8+10h], r13
0x1800512ad  lock and cs:LdrpTlsLock, 0FFFFFFFFFFFFFFFBh
0x1800512b6  mov     rsi, [r8+10h]
0x1800512ba  mov     rcx, [r8+18h]
0x1800512be  lock bts dword ptr [r8+24h], 2
0x1800512c5  lock btr dword ptr [r8+24h], 1
0x1800512cc  jb      short loc_1800512D6
0x1800512ce  mov     rdx, r15
0x1800512d1  call    ZwAlertThreadByThreadIdEx
0x1800512d6  mov     r8, rsi
0x1800512d9  test    rsi, rsi
0x1800512dc  jz      loc_180051048
0x1800512e2  jmp     short loc_1800512B6
0x1800512e4  lea     rdx, [rcx-4]
0x1800512e8  mov     rax, rcx
0x1800512eb  lock cmpxchg cs:LdrpTlsLock, rdx
0x1800512f4  mov     rcx, rax
0x1800512f7  jnz     loc_180051241
0x1800512fd  jmp     loc_180051048
0x180051302  lea     rcx, [rdx+4]
0x180051306  jmp     loc_180051226
0x180166470  push    rbp
0x180166472  sub     rsp, 40h
0x180166476  mov     rbp, rdx
0x180166479  mov     [rbp+48h], rcx
0x18016647d  mov     dword ptr [rbp+40h], 0Bh
0x180166484  mov     rax, [rbp+48h]
0x180166488  mov     rdx, [rax+8]
0x18016648c  mov     rax, [rbp+48h]
0x180166490  mov     rcx, [rax]
0x180166493  mov     r8d, [rbp+40h]
0x180166497  call    RtlReportException
0x18016649c  mov     dword ptr [rbp+44h], 1
0x1801664a3  mov     eax, [rbp+44h]
0x1801664a6  add     rsp, 40h
0x1801664aa  pop     rbp
0x1801664ab  retn
```
