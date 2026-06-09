# CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x18001971c`
- end: `0x180019846`
- name: `?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `298`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800015e0`
- `0x180001f10`
- `0x180003890`
- `0x180019a34`

## callees

- `0x1800195d4`
- `0x1800195f4`
- `0x18001971c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019734`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019734`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197b9`

## pseudocode

```c
DWORD __fastcall CReaderWriterLock3::_LockSpin(volatile signed __int32 *a1, int a2)
{
  DWORD v4; // r14d
  DWORD result; // eax
  DWORD CurrentThreadId; // kr00_4
  unsigned int v7; // ebp
  int v8; // edi
  int v9; // esi
  signed __int32 v10; // edx
  DWORD v11; // eax
  char v12; // cl
  signed __int32 v13; // edx

  v4 = 0;
  CurrentThreadId = GetCurrentThreadId();
  result = 1321528399 * CurrentThreadId;
  v7 = 0;
  v8 = (int)(*(double *)&qword_1800230D0[CurrentThreadId % 0xD] * 4000.0);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 )
    v9 = 1;
  do
  {
    if ( --v9 < 0 )
    {
      SwitchOrSleep(v4);
      result = SleepTime(v7);
      v4 = result;
      v8 = (int)((double)v8 * 0.5);
      if ( v8 <= 10000 )
      {
        result = 100;
        if ( v8 <= 100 )
          v8 = 100;
      }
      else
      {
        v8 = 10000;
      }
      ++v7;
      goto LABEL_2;
    }
    if ( a2 == 1 )
    {
      if ( !*((_DWORD *)a1 + 1) && !(unsigned __int16)*a1 )
      {
        v10 = *a1;
        if ( v10 == _InterlockedCompareExchange(a1, v10 | 0xFFFF, v10) )
        {
          v11 = GetCurrentThreadId() & 0xFFFFFFFC | 1;
LABEL_10:
          result = _InterlockedExchange(a1 + 1, v11);
LABEL_11:
          v12 = 1;
          continue;
        }
      }
      result = GetCurrentThreadId() & 0xFFFFFFFC;
      if ( (a1[1] & 0xFFFFFFFC) == result )
      {
        v11 = *((_DWORD *)a1 + 1) + 1;
        goto LABEL_10;
      }
    }
    else
    {
      v13 = *a1;
      if ( (unsigned __int16)*a1 != 0xFFFF )
      {
        result = _InterlockedCompareExchange(a1, v13 + 1, v13);
        if ( v13 == result )
          goto LABEL_11;
      }
    }
    v12 = 0;
  }
  while ( !v12 );
  return result;
}

```

## disassembly

```asm
0x18001971c  push    rbx
0x18001971e  push    rbp
0x18001971f  push    rsi
0x180019720  push    rdi
0x180019721  push    r12
0x180019723  push    r14
0x180019725  push    r15
0x180019727  sub     rsp, 20h
0x18001972b  mov     r15d, edx
0x18001972e  mov     rbx, rcx
0x180019731  xor     r14d, r14d
0x180019734  call    cs:__imp_GetCurrentThreadId
0x18001973a  mov     r9d, eax
0x18001973d  lea     rcx, qword_1800230D0
0x180019744  mov     eax, 4EC4EC4Fh
0x180019749  lea     r12d, [r14+1]
0x18001974d  mul     r9d
0x180019750  shr     edx, 2
0x180019753  imul    r8d, edx, 0Dh
0x180019757  sub     r9d, r8d
0x18001975a  xor     ebp, ebp
0x18001975c  movsd   xmm0, qword ptr [rcx+r9*8]
0x180019762  mulsd   xmm0, cs:__real@40af400000000000
0x18001976a  cvttsd2si edi, xmm0
0x18001976e  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180019775  mov     esi, edi
0x180019777  cmovb   esi, r12d
0x18001977b  sub     esi, r12d
0x18001977e  js      short loc_1800197FF
0x180019780  cmp     r15d, r12d
0x180019783  jnz     short loc_1800197D4
0x180019785  mov     eax, [rbx+4]
0x180019788  test    eax, eax
0x18001978a  jnz     short loc_1800197B9
0x18001978c  mov     edx, [rbx]
0x18001978e  test    dx, dx
0x180019791  jnz     short loc_1800197B9
0x180019793  mov     ecx, edx
0x180019795  mov     eax, edx
0x180019797  or      ecx, 0FFFFh
0x18001979d  lock cmpxchg [rbx], ecx
0x1800197a1  cmp     edx, eax
0x1800197a3  jnz     short loc_1800197B9
0x1800197a5  call    cs:__imp_GetCurrentThreadId
0x1800197ab  and     eax, 0FFFFFFFCh
0x1800197ae  or      eax, r12d
0x1800197b1  xchg    eax, [rbx+4]
0x1800197b4  mov     cl, r12b
0x1800197b7  jmp     short loc_1800197EC
0x1800197b9  call    cs:__imp_GetCurrentThreadId
0x1800197bf  mov     ecx, [rbx+4]
0x1800197c2  and     eax, 0FFFFFFFCh
0x1800197c5  and     ecx, 0FFFFFFFCh
0x1800197c8  cmp     ecx, eax
0x1800197ca  jnz     short loc_1800197EA
0x1800197cc  mov     eax, [rbx+4]
0x1800197cf  add     eax, r12d
0x1800197d2  jmp     short loc_1800197B1
0x1800197d4  mov     edx, [rbx]
0x1800197d6  cmp     dx, 0FFFFh
0x1800197db  jz      short loc_1800197EA
0x1800197dd  lea     ecx, [rdx+1]
0x1800197e0  mov     eax, edx
0x1800197e2  lock cmpxchg [rbx], ecx
0x1800197e6  cmp     edx, eax
0x1800197e8  jz      short loc_1800197B4
0x1800197ea  xor     cl, cl
0x1800197ec  test    cl, cl
0x1800197ee  jz      short loc_18001977B
0x1800197f0  add     rsp, 20h
0x1800197f4  pop     r15
0x1800197f6  pop     r14
0x1800197f8  pop     r12
0x1800197fa  pop     rdi
0x1800197fb  pop     rsi
0x1800197fc  pop     rbp
0x1800197fd  pop     rbx
0x1800197fe  retn
0x1800197ff  mov     ecx, r14d; dwMilliseconds
0x180019802  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180019807  mov     ecx, ebp; unsigned int
0x180019809  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18001980e  movd    xmm0, edi
0x180019812  mov     r14d, eax
0x180019815  cvtdq2pd xmm0, xmm0
0x180019819  mulsd   xmm0, cs:__real@3fe0000000000000
0x180019821  cvttsd2si edi, xmm0
0x180019825  cmp     edi, 2710h
0x18001982b  jle     short loc_180019834
0x18001982d  mov     edi, 2710h
0x180019832  jmp     short loc_18001983E
0x180019834  mov     eax, 64h ; 'd'
0x180019839  cmp     edi, eax
0x18001983b  cmovle  edi, eax
0x18001983e  add     ebp, r12d
0x180019841  jmp     loc_18001976E
```
