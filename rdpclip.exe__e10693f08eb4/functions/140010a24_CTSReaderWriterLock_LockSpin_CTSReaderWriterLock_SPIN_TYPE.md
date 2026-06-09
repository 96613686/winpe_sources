# CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock::SPIN_TYPE)

- ea: `0x140010a24`
- end: `0x140010b3a`
- name: `?_LockSpin@CTSReaderWriterLock@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140010500`
- `0x140010d44`

## callees

- `0x14000ef6c`
- `0x140010a24`
- `0x140010c44`
- `0x140010c80`
- `0x140018404`
- `0x140018850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x140010af0`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x140010af0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140010afd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140010afd`

## pseudocode

```c
__int64 __fastcall CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock *a1, int a2)
{
  DWORD v3; // r14d
  double v5; // xmm0_8
  int v6; // edi
  int v7; // esi
  int Lock; // eax
  BOOL v9; // ecx
  int v10; // eax
  int v11; // r8d
  unsigned int v13; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v13 = 0;
  PAL_System_ThreadGetId(&v13);
  v5 = *(double *)&`CTSReaderWriterLock::_RandomBackoffFactor'::`2'::s_aFactors[v13 % 0xD] * 4000.0;
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
      Lock = CTSReaderWriterLock::_TryWriteLock(a1, 0);
LABEL_12:
      v9 = Lock;
      goto LABEL_17;
    }
    if ( a2 == 2 )
    {
      Lock = CTSReaderWriterLock::_TryReadLock(a1);
      goto LABEL_12;
    }
    v9 = 0;
    if ( (unsigned __int16)*(_DWORD *)a1 != 0xFFFF )
    {
      v10 = PAL_System_AtomicCompareAndExchange(a1, (unsigned int)(*(_DWORD *)a1 + 1));
      if ( v11 == v10 )
        v9 = 1;
    }
LABEL_17:
    if ( v9 )
      break;
    if ( !--v7 )
    {
      if ( !SwitchToThread() )
        Sleep(v3);
      v3 ^= 1u;
      v5 = (double)v6 * 0.5;
      goto LABEL_2;
    }
  }
  if ( a2 == 1 )
    return CTSReaderWriterLock::IsWriteLocked(a1);
  else
    return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x140010a24  push    rbx
0x140010a26  push    rbp
0x140010a27  push    rsi
0x140010a28  push    rdi
0x140010a29  push    r13
0x140010a2b  push    r14
0x140010a2d  sub     rsp, 28h
0x140010a31  mov     rbx, rcx
0x140010a34  xor     r14d, r14d
0x140010a37  lea     rcx, [rsp+58h+arg_8]
0x140010a3c  mov     [rsp+58h+arg_8], r14d
0x140010a41  mov     ebp, edx
0x140010a43  call    PAL_System_ThreadGetId
0x140010a48  mov     r8d, [rsp+58h+arg_8]
0x140010a4d  lea     rcx, ?s_aFactors@?1??_RandomBackoffFactor@CTSReaderWriterLock@@AEAANXZ@4QBNB; double const near * const `CTSReaderWriterLock::_RandomBackoffFactor(void)'::`2'::s_aFactors
0x140010a54  mov     eax, 4EC4EC4Fh
0x140010a59  lea     r13d, [r14+64h]
0x140010a5d  mul     r8d
0x140010a60  shr     edx, 2
0x140010a63  imul    eax, edx, 0Dh
0x140010a66  sub     r8d, eax
0x140010a69  movsd   xmm0, qword ptr [rcx+r8*8]
0x140010a6f  mulsd   xmm0, cs:__real@40af400000000000
0x140010a77  cvttsd2si edi, xmm0
0x140010a7b  cmp     edi, 2710h
0x140010a81  jle     short loc_140010A8A
0x140010a83  mov     edi, 2710h
0x140010a88  jmp     short loc_140010A91
0x140010a8a  cmp     edi, r13d
0x140010a8d  cmovle  edi, r13d
0x140010a91  cmp     dword ptr [rbx+0Ch], 0
0x140010a95  mov     esi, 1
0x140010a9a  cmovnz  esi, edi
0x140010a9d  cmp     ebp, 1
0x140010aa0  jnz     short loc_140010AAE
0x140010aa2  xor     edx, edx; int
0x140010aa4  mov     rcx, rbx; this
0x140010aa7  call    ?_TryWriteLock@CTSReaderWriterLock@@AEAAHJ@Z; CTSReaderWriterLock::_TryWriteLock(long)
0x140010aac  jmp     short loc_140010ABB
0x140010aae  cmp     ebp, 2
0x140010ab1  jnz     short loc_140010ABF
0x140010ab3  mov     rcx, rbx; this
0x140010ab6  call    ?_TryReadLock@CTSReaderWriterLock@@AEAAHXZ; CTSReaderWriterLock::_TryReadLock(void)
0x140010abb  mov     ecx, eax
0x140010abd  jmp     short loc_140010AE7
0x140010abf  mov     r8d, [rbx]
0x140010ac2  cmp     r8w, 0FFFFh
0x140010ac8  jz      short loc_140010AE5
0x140010aca  lea     edx, [r8+1]
0x140010ace  mov     rcx, rbx
0x140010ad1  call    PAL_System_AtomicCompareAndExchange
0x140010ad6  cmp     r8d, eax
0x140010ad9  jnz     short loc_140010AE5
0x140010adb  mov     eax, [rbx+4]
0x140010ade  mov     ecx, 1
0x140010ae3  jmp     short loc_140010AE7
0x140010ae5  xor     ecx, ecx
0x140010ae7  test    ecx, ecx
0x140010ae9  jnz     short loc_140010B1C
0x140010aeb  sub     esi, 1
0x140010aee  jnz     short loc_140010A9D
0x140010af0  call    cs:__imp_SwitchToThread
0x140010af6  test    eax, eax
0x140010af8  jnz     short loc_140010B03
0x140010afa  mov     ecx, r14d; dwMilliseconds
0x140010afd  call    cs:__imp_Sleep
0x140010b03  movd    xmm0, edi
0x140010b07  xor     r14d, 1
0x140010b0b  cvtdq2pd xmm0, xmm0
0x140010b0f  mulsd   xmm0, cs:__real@3fe0000000000000
0x140010b17  jmp     loc_140010A77
0x140010b1c  cmp     ebp, 1
0x140010b1f  jnz     short loc_140010B2B
0x140010b21  mov     rcx, rbx; this
0x140010b24  call    ?IsWriteLocked@CTSReaderWriterLock@@QEBAHXZ; CTSReaderWriterLock::IsWriteLocked(void)
0x140010b29  jmp     short loc_140010B2D
0x140010b2b  mov     eax, [rbx]
0x140010b2d  add     rsp, 28h
0x140010b31  pop     r14
0x140010b33  pop     r13
0x140010b35  pop     rdi
0x140010b36  pop     rsi
0x140010b37  pop     rbp
0x140010b38  pop     rbx
0x140010b39  retn
```
