# CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock::SPIN_TYPE)

- ea: `0x180027bf4`
- end: `0x180027cf3`
- name: `?_LockSpin@CTSReaderWriterLock@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CTSReaderWriterLock *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026234`
- `0x180027de4`

## callees

- `0x18001efd8`
- `0x18001f424`
- `0x180027bf4`
- `0x180027cfc`
- `0x180027d30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180027cbc`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180027cbc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027cc8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027cc8`

## pseudocode

```c
__int64 __fastcall CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock *a1, int a2)
{
  DWORD v3; // ebp
  double v5; // xmm0_8
  int v6; // ebx
  int v7; // edi
  __int64 result; // rax
  int v9; // eax
  int v10; // r8d
  unsigned int v11; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v11 = 0;
  PAL_System_ThreadGetId(&v11);
  v5 = *(double *)&`CTSReaderWriterLock::_RandomBackoffFactor'::`2'::s_aFactors[v11 % 0xD] * 4000.0;
LABEL_2:
  v6 = (int)v5;
  if ( (int)v5 <= 10000 )
  {
    if ( v6 <= 100 )
      v6 = 100;
  }
  else
  {
    v6 = 10000;
  }
  v7 = 1;
  if ( *((_DWORD *)a1 + 3) )
    v7 = v6;
  while ( 1 )
  {
    if ( a2 == 1 )
    {
      result = CTSReaderWriterLock::_TryWriteLock(a1, 0);
    }
    else if ( a2 == 2 )
    {
      result = CTSReaderWriterLock::_TryReadLock(a1);
    }
    else
    {
      result = 0;
      if ( (unsigned __int16)*(_DWORD *)a1 != 0xFFFF )
      {
        v9 = PAL_System_AtomicCompareAndExchange(a1, (unsigned int)(*(_DWORD *)a1 + 1));
        if ( v10 == v9 )
          result = 1;
      }
    }
    if ( (_DWORD)result )
      return result;
    if ( !--v7 )
    {
      if ( !SwitchToThread() )
        Sleep(v3);
      v3 ^= 1u;
      v5 = (double)v6 * 0.5;
      goto LABEL_2;
    }
  }
}

```

## disassembly

```asm
0x180027bf4  push    rbx
0x180027bf6  push    rbp
0x180027bf7  push    rsi
0x180027bf8  push    rdi
0x180027bf9  push    r13
0x180027bfb  push    r14
0x180027bfd  sub     rsp, 28h
0x180027c01  mov     rsi, rcx
0x180027c04  xor     ebp, ebp
0x180027c06  lea     rcx, [rsp+58h+arg_8]
0x180027c0b  mov     [rsp+58h+arg_8], ebp
0x180027c0f  mov     r14d, edx
0x180027c12  call    PAL_System_ThreadGetId
0x180027c17  mov     r8d, [rsp+58h+arg_8]
0x180027c1c  lea     rcx, ?s_aFactors@?1??_RandomBackoffFactor@CTSReaderWriterLock@@AEAANXZ@4QBNB; double const near * const `CTSReaderWriterLock::_RandomBackoffFactor(void)'::`2'::s_aFactors
0x180027c23  mov     eax, 4EC4EC4Fh
0x180027c28  lea     r13d, [rbp+64h]
0x180027c2c  mul     r8d
0x180027c2f  shr     edx, 2
0x180027c32  imul    eax, edx, 0Dh
0x180027c35  sub     r8d, eax
0x180027c38  movsd   xmm0, qword ptr [rcx+r8*8]
0x180027c3e  mulsd   xmm0, cs:__real@40af400000000000
0x180027c46  cvttsd2si ebx, xmm0
0x180027c4a  cmp     ebx, 2710h
0x180027c50  jle     short loc_180027C59
0x180027c52  mov     ebx, 2710h
0x180027c57  jmp     short loc_180027C60
0x180027c59  cmp     ebx, r13d
0x180027c5c  cmovle  ebx, r13d
0x180027c60  cmp     dword ptr [rsi+0Ch], 0
0x180027c64  mov     edi, 1
0x180027c69  cmovnz  edi, ebx
0x180027c6c  cmp     r14d, 1
0x180027c70  jnz     short loc_180027C7E
0x180027c72  xor     edx, edx; int
0x180027c74  mov     rcx, rsi; this
0x180027c77  call    ?_TryWriteLock@CTSReaderWriterLock@@AEAAHJ@Z; CTSReaderWriterLock::_TryWriteLock(long)
0x180027c7c  jmp     short loc_180027CB3
0x180027c7e  cmp     r14d, 2
0x180027c82  jnz     short loc_180027C8E
0x180027c84  mov     rcx, rsi; this
0x180027c87  call    ?_TryReadLock@CTSReaderWriterLock@@AEAAHXZ; CTSReaderWriterLock::_TryReadLock(void)
0x180027c8c  jmp     short loc_180027CB3
0x180027c8e  mov     r8d, [rsi]
0x180027c91  cmp     r8w, 0FFFFh
0x180027c97  jz      short loc_180027CB1
0x180027c99  lea     edx, [r8+1]
0x180027c9d  mov     rcx, rsi
0x180027ca0  call    PAL_System_AtomicCompareAndExchange
0x180027ca5  cmp     r8d, eax
0x180027ca8  jnz     short loc_180027CB1
0x180027caa  mov     eax, 1
0x180027caf  jmp     short loc_180027CB3
0x180027cb1  xor     eax, eax
0x180027cb3  test    eax, eax
0x180027cb5  jnz     short loc_180027CE6
0x180027cb7  sub     edi, 1
0x180027cba  jnz     short loc_180027C6C
0x180027cbc  call    cs:__imp_SwitchToThread
0x180027cc2  test    eax, eax
0x180027cc4  jnz     short loc_180027CCE
0x180027cc6  mov     ecx, ebp; dwMilliseconds
0x180027cc8  call    cs:__imp_Sleep
0x180027cce  movd    xmm0, ebx
0x180027cd2  xor     ebp, 1
0x180027cd5  cvtdq2pd xmm0, xmm0
0x180027cd9  mulsd   xmm0, cs:__real@3fe0000000000000
0x180027ce1  jmp     loc_180027C46
0x180027ce6  add     rsp, 28h
0x180027cea  pop     r14
0x180027cec  pop     r13
0x180027cee  pop     rdi
0x180027cef  pop     rsi
0x180027cf0  pop     rbp
0x180027cf1  pop     rbx
0x180027cf2  retn
```
