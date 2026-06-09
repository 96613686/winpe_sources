# LdrpCallTlsInitializers

- ea: `0x18006d980`
- end: `0x18006dceb`
- name: `LdrpCallTlsInitializers`
- size: `875`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800503f0`
- `0x180050718`
- `0x180060080`
- `0x1800607d0`
- `0x1800ced58`
- `0x1800e6424`

## callees

- `0x18001eb80`
- `0x18006d6e8`
- `0x18006d980`
- `0x18006e6f4`
- `0x180070370`
- `0x18010a200`
- `0x18015ec80`
- `0x18015f910`

## string_xrefs

- `0x18006db04`: `Calling TLS callback %p for DLL "%wZ" at %p\n`

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
0x18006d980  push    rbx
0x18006d982  push    rsi
0x18006d983  push    rdi
0x18006d984  push    r12
0x18006d986  push    r13
0x18006d988  push    r14
0x18006d98a  push    r15
0x18006d98c  sub     rsp, 70h
0x18006d990  mov     rdi, rdx
0x18006d993  mov     r12d, ecx
0x18006d996  xor     r13d, r13d
0x18006d999  mov     r9d, r13d
0x18006d99c  mov     rax, gs:30h
0x18006d9a5  mov     r8, [rax+1850h]
0x18006d9ac  test    r8, r8
0x18006d9af  jz      short loc_18006D9CB
0x18006d9b1  mov     edx, r13d
0x18006d9b4  cmp     edx, 8
0x18006d9b7  jnb     short loc_18006D9CB
0x18006d9b9  mov     eax, edx
0x18006d9bb  lea     rcx, [r8+rax*8]
0x18006d9bf  cmp     [rcx], r9
0x18006d9c2  jz      short loc_18006D9C8
0x18006d9c4  inc     edx
0x18006d9c6  jmp     short loc_18006D9B4
0x18006d9c8  mov     r9, rcx
0x18006d9cb  lea     r14, LdrpTlsLock
0x18006d9d2  test    r9, r9
0x18006d9d5  jz      short loc_18006D9DA
0x18006d9d7  mov     [r9], r14
0x18006d9da  mov     esi, 11h
0x18006d9df  xor     eax, eax
0x18006d9e1  lock cmpxchg cs:LdrpTlsLock, rsi
0x18006d9ea  jnz     loc_18006DAD5
0x18006d9f0  mov     rbx, cs:LdrpTlsList
0x18006d9f7  lea     rax, LdrpTlsList
0x18006d9fe  xchg    ax, ax
0x18006da00  cmp     rbx, rax
0x18006da03  jz      short loc_18006DA10
0x18006da05  cmp     [rbx+38h], rdi
0x18006da09  jz      short loc_18006DA13
0x18006da0b  mov     rbx, [rbx]
0x18006da0e  jmp     short loc_18006DA00
0x18006da10  mov     rbx, r13
0x18006da13  mov     rcx, r13
0x18006da16  mov     rax, rsi
0x18006da19  lock cmpxchg cs:LdrpTlsLock, rcx
0x18006da22  jnz     loc_18006DAE8
0x18006da28  mov     rsi, r13
0x18006da2b  mov     rax, gs:30h
0x18006da34  mov     rdx, [rax+1850h]
0x18006da3b  test    rdx, rdx
0x18006da3e  jz      short loc_18006DA6D
0x18006da40  mov     r9, 7FFFFFFFFFFFFFFCh
0x18006da4a  and     r14, r9
0x18006da4d  mov     ecx, r13d
0x18006da50  cmp     ecx, 8
0x18006da53  jnb     short loc_18006DA6D
0x18006da55  mov     eax, ecx
0x18006da57  lea     r8, [rdx+rax*8]
0x18006da5b  mov     rax, [r8]
0x18006da5e  and     rax, r9
0x18006da61  cmp     rax, r14
0x18006da64  jz      short loc_18006DA6A
0x18006da66  inc     ecx
0x18006da68  jmp     short loc_18006DA50
0x18006da6a  mov     rsi, r8
0x18006da6d  test    rsi, rsi
0x18006da70  jz      short loc_18006DABF
0x18006da72  or      byte ptr [rsi], 2
0x18006da75  nop
0x18006da76  cmp     [rsi+7], r13b
0x18006da7a  jge     short loc_18006DABC
0x18006da7c  xorps   xmm0, xmm0
0x18006da7f  movups  [rsp+0A8h+var_50], xmm0
0x18006da84  mov     rax, gs:30h
0x18006da8d  mov     rcx, rsi
0x18006da90  sub     rcx, [rax+1850h]
0x18006da97  sar     rcx, 3
0x18006da9b  mov     qword ptr [rsp+0A8h+var_50], rcx
0x18006daa0  mov     r9d, 10h
0x18006daa6  lea     r8, [rsp+0A8h+var_50]
0x18006daab  mov     edx, 38h ; '8'
0x18006dab0  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18006dab7  call    NtSetInformationThread
0x18006dabc  mov     [rsi], r13
0x18006dabf  test    rbx, rbx
0x18006dac2  jnz     short loc_18006DAFB
0x18006dac4  add     rsp, 70h
0x18006dac8  pop     r15
0x18006daca  pop     r14
0x18006dacc  pop     r13
0x18006dace  pop     r12
0x18006dad0  pop     rdi
0x18006dad1  pop     rsi
0x18006dad2  pop     rbx
0x18006dad3  retn
0x18006dad5  mov     r8, rax
0x18006dad8  mov     rdx, r9
0x18006dadb  mov     rcx, r14
0x18006dade  call    RtlpAcquireSRWLockSharedContended
0x18006dae3  jmp     loc_18006D9F0
0x18006dae8  test    al, 1
0x18006daea  jnz     loc_18006DB78
0x18006daf0  mov     ecx, 0C0000264h
0x18006daf5  call    RtlRaiseStatus
0x18006dafb  mov     rbx, [rbx+28h]
0x18006daff  test    rbx, rbx
0x18006db02  jz      short loc_18006DAC4
0x18006db04  lea     r14, aCallingTlsCall; "Calling TLS callback %p for DLL \"%wZ\""...
0x18006db0b  mov     rsi, [rbx]
0x18006db0e  test    rsi, rsi
0x18006db11  jz      short loc_18006DB6E
0x18006db13  add     rbx, 8
0x18006db17  mov     [rsp+0A8h+var_58], rbx
0x18006db1c  lea     rcx, [rdi+48h]
0x18006db20  mov     rax, [rdi+30h]
0x18006db24  mov     [rsp+0A8h+var_70], rax
0x18006db29  mov     [rsp+0A8h+var_78], rcx
0x18006db2e  mov     qword ptr [rsp+0A8h+ArgList], rsi; ArgList
0x18006db33  mov     [rsp+0A8h+Format], r14; Format
0x18006db38  mov     r9d, 2; int
0x18006db3e  lea     r8, aLdrpcalltlsini; "LdrpCallTlsInitializers"
0x18006db45  mov     edx, 4A3h; int
0x18006db4a  lea     rcx, aMinkernelLdrLd_1; "minkernel\\ldr\\ldrtls.c"
0x18006db51  call    LdrpLogInternal
0x18006db56  mov     r9, rsi
0x18006db59  mov     r8d, r12d
0x18006db5c  mov     rdx, [rdi+30h]
0x18006db60  lea     rcx, ImageTlsCallbackCaller
0x18006db67  call    LdrpCallInitRoutine
0x18006db6c  jmp     short loc_18006DB0B
0x18006db6e  jmp     loc_18006DAC4
0x18006db73  jmp     loc_18006DAC4
0x18006db78  test    al, 2
0x18006db7a  jnz     short loc_18006DBA3
0x18006db7c  mov     rdx, rax
0x18006db7f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18006db83  lea     rcx, [rax-10h]
0x18006db87  mov     r8, r13
0x18006db8a  cmp     rdx, 10h
0x18006db8e  cmovnz  r8, rcx
0x18006db92  lock cmpxchg cs:LdrpTlsLock, r8
0x18006db9b  jz      loc_18006DA28
0x18006dba1  jmp     short loc_18006DB78
0x18006dba3  test    al, 8
0x18006dba5  jz      short loc_18006DBEB
0x18006dba7  mov     rcx, rax
0x18006dbaa  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18006dbae  mov     r8, [rcx+8]
0x18006dbb2  test    r8, r8
0x18006dbb5  jnz     short loc_18006DBCC
0x18006dbb7  nop     word ptr [rax+rax+00000000h]
0x18006dbc0  mov     rcx, [rcx]
0x18006dbc3  mov     r8, [rcx+8]
0x18006dbc7  test    r8, r8
0x18006dbca  jz      short loc_18006DBC0
0x18006dbcc  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18006dbd3  lock xadd [r8+20h], edx
0x18006dbd9  sub     edx, 1
0x18006dbdc  jg      loc_18006DA28
0x18006dbe2  mov     rdx, 0FFFFFFFFFFFFFFF7h
0x18006dbe9  jmp     short loc_18006DBF2
0x18006dbeb  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18006dbf2  mov     r8, rax
0x18006dbf5  and     r8d, 6
0x18006dbf9  cmp     r8, 2
0x18006dbfd  jz      loc_18006DCE2
0x18006dc03  mov     rcx, rdx
0x18006dc06  add     rcx, rax
0x18006dc09  lock cmpxchg cs:LdrpTlsLock, rcx
0x18006dc12  jnz     short loc_18006DBF2
0x18006dc14  cmp     r8, 2
0x18006dc18  jnz     loc_18006DA28
0x18006dc1e  mov     r15, r14
0x18006dc21  test    cl, 1
0x18006dc24  jnz     loc_18006DCC4
0x18006dc2a  mov     r9, rcx
0x18006dc2d  and     r9, 0FFFFFFFFFFFFFFF0h
0x18006dc31  mov     rdx, r9
0x18006dc34  mov     r8, [r9+8]
0x18006dc38  test    r8, r8
0x18006dc3b  jz      short loc_18006DC70
0x18006dc3d  cmp     rdx, r9
0x18006dc40  jz      short loc_18006DC46
0x18006dc42  mov     [r9+8], r8
0x18006dc46  mov     eax, [r8+24h]
0x18006dc4a  test    al, 1
0x18006dc4c  jz      short loc_18006DC57
0x18006dc4e  mov     rax, [r8+10h]
0x18006dc52  test    rax, rax
0x18006dc55  jnz     short loc_18006DC85
0x18006dc57  mov     r15, r13
0x18006dc5a  mov     rdx, r13
0x18006dc5d  mov     rax, rcx
0x18006dc60  lock cmpxchg cs:LdrpTlsLock, rdx
0x18006dc69  mov     rcx, rax
0x18006dc6c  jnz     short loc_18006DC21
0x18006dc6e  jmp     short loc_18006DC96
0x18006dc70  mov     rax, rdx
0x18006dc73  mov     rdx, [rdx]
0x18006dc76  mov     [rdx+10h], rax
0x18006dc7a  mov     r8, [rdx+8]
0x18006dc7e  test    r8, r8
0x18006dc81  jz      short loc_18006DC70
0x18006dc83  jmp     short loc_18006DC3D
0x18006dc85  mov     [r9+8], rax
0x18006dc89  mov     [r8+10h], r13
0x18006dc8d  lock and cs:LdrpTlsLock, 0FFFFFFFFFFFFFFFBh
0x18006dc96  mov     rsi, [r8+10h]
0x18006dc9a  mov     rcx, [r8+18h]
0x18006dc9e  lock bts dword ptr [r8+24h], 2
0x18006dca5  lock btr dword ptr [r8+24h], 1
0x18006dcac  jb      short loc_18006DCB6
0x18006dcae  mov     rdx, r15
0x18006dcb1  call    ZwAlertThreadByThreadIdEx
0x18006dcb6  mov     r8, rsi
0x18006dcb9  test    rsi, rsi
0x18006dcbc  jz      loc_18006DA28
0x18006dcc2  jmp     short loc_18006DC96
0x18006dcc4  lea     rdx, [rcx-4]
0x18006dcc8  mov     rax, rcx
0x18006dccb  lock cmpxchg cs:LdrpTlsLock, rdx
0x18006dcd4  mov     rcx, rax
0x18006dcd7  jnz     loc_18006DC21
0x18006dcdd  jmp     loc_18006DA28
0x18006dce2  lea     rcx, [rdx+4]
0x18006dce6  jmp     loc_18006DC06
0x180166f80  push    rbp
0x180166f82  sub     rsp, 40h
0x180166f86  mov     rbp, rdx
0x180166f89  mov     [rbp+48h], rcx
0x180166f8d  mov     dword ptr [rbp+40h], 0Bh
0x180166f94  mov     rax, [rbp+48h]
0x180166f98  mov     rdx, [rax+8]
0x180166f9c  mov     rax, [rbp+48h]
0x180166fa0  mov     rcx, [rax]
0x180166fa3  mov     r8d, [rbp+40h]
0x180166fa7  call    RtlReportException
0x180166fac  mov     dword ptr [rbp+44h], 1
0x180166fb3  mov     eax, [rbp+44h]
0x180166fb6  add     rsp, 40h
0x180166fba  pop     rbp
0x180166fbb  retn
```
