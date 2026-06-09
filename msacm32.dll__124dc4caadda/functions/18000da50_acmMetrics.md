# acmMetrics

- ea: `0x18000da50`
- end: `0x18000ddda`
- name: `acmMetrics`
- size: `906`
- prototype: `MMRESULT __stdcall(HACMOBJ hao, UINT uMetric, LPVOID pMetric)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x180001940`
- `0x180001a40`
- `0x180001ad0`
- `0x1800023c0`
- `0x180002a80`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x180007470`
- `0x180007720`
- `0x180008dd8`
- `0x18000ad3c`
- `0x18000ae04`
- `0x18000ca28`
- `0x18000da50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dc25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dc25`

## pseudocode

```c
MMRESULT __stdcall acmMetrics(HACMOBJ hao, UINT uMetric, LPVOID pMetric)
{
  __int64 v6; // rbp
  unsigned int v8; // edi
  __int64 v9; // r8
  bool v10; // zf
  unsigned int v11; // eax
  bool v12; // zf
  __int64 CurrentThreadId; // r14

  v6 = pagFindAndBoot();
  if ( !v6 )
    return 1;
  if ( hao && !(unsigned int)ValidateHandle(hao, 0) )
    return 5;
  if ( uMetric <= 0x16 )
  {
    switch ( uMetric )
    {
      case 0x16u:
        goto LABEL_27;
      case 1u:
LABEL_21:
        if ( !(unsigned int)ValidateWritePointer(pMetric, 4) )
          return 11;
        if ( !hao )
        {
          v11 = 0;
          v9 = 0x40000000;
          v12 = uMetric == 20;
          goto LABEL_24;
        }
        goto LABEL_65;
      case 2u:
        goto LABEL_15;
      case 3u:
LABEL_27:
        if ( !(unsigned int)ValidateWritePointer(pMetric, 4) )
          return 11;
        if ( !hao )
        {
          v11 = 2;
          v9 = 1073741826;
          v12 = uMetric == 22;
LABEL_24:
          if ( !v12 )
            v9 = v11;
          return IDriverCount(v6, pMetric, v9);
        }
LABEL_65:
        *(_DWORD *)pMetric = 0;
        return 5;
    }
    if ( uMetric != 4 )
    {
      if ( uMetric != 5 )
      {
        if ( uMetric == 6 )
        {
          if ( !(unsigned int)ValidateWritePointer(pMetric, 4) )
            return 11;
          if ( !hao )
          {
            v9 = 8;
            return IDriverCount(v6, pMetric, v9);
          }
          goto LABEL_65;
        }
        if ( uMetric != 20 )
        {
          if ( uMetric == 21 )
          {
LABEL_15:
            if ( (unsigned int)ValidateWritePointer(pMetric, 4) )
            {
              if ( !hao )
              {
                v8 = 1;
                v9 = 1073741825;
                v10 = uMetric == 21;
                goto LABEL_68;
              }
              goto LABEL_65;
            }
            return 11;
          }
          return 8;
        }
        goto LABEL_21;
      }
LABEL_57:
      if ( !(unsigned int)ValidateWritePointer(pMetric, 4) )
        return 11;
      if ( !hao )
      {
        v9 = 3221225472LL;
        if ( uMetric != 24 )
          v9 = 0x80000000LL;
        return IDriverCount(v6, pMetric, v9);
      }
      goto LABEL_65;
    }
LABEL_62:
    v8 = 4;
    if ( (unsigned int)ValidateWritePointer(pMetric, 4) )
    {
      if ( !hao )
      {
        v9 = 1073741828;
        v10 = uMetric == 23;
LABEL_68:
        if ( !v10 )
          v9 = v8;
        return IDriverCount(v6, pMetric, v9);
      }
      goto LABEL_65;
    }
    return 11;
  }
  switch ( uMetric )
  {
    case 0x17u:
      goto LABEL_62;
    case 0x18u:
      goto LABEL_57;
    case 0x1Eu:
    case 0x1Fu:
      if ( (unsigned int)ValidateWritePointer(pMetric, 4) )
      {
        *(_DWORD *)pMetric = -1;
        if ( (unsigned int)ValidateHandle(hao, 1) )
          return IDriverGetWaveIdentifier(hao, pMetric, uMetric == 30);
        return 5;
      }
      return 11;
    case 0x32u:
      if ( (unsigned int)ValidateWritePointer(pMetric, 4) )
        return IMetricsMaxSizeFormat(v6, hao, pMetric);
      return 11;
    case 0x33u:
      if ( (unsigned int)ValidateWritePointer(pMetric, 4) )
        return IMetricsMaxSizeFilter(v6, hao, pMetric);
      return 11;
    case 0x64u:
      if ( (unsigned int)ValidateWritePointer(pMetric, 4) )
      {
        *(_DWORD *)pMetric = 0;
        if ( (unsigned int)ValidateHandle(hao, 1) )
          return IDriverSupport(hao, pMetric);
        return 5;
      }
      return 11;
  }
  if ( uMetric != 101 )
    return 8;
  if ( !(unsigned int)ValidateWritePointer(pMetric, 4) )
    return 11;
  *(_DWORD *)pMetric = 0;
  if ( !(unsigned int)ValidateHandle(hao, 1) )
    return 5;
  if ( !(unsigned int)threadQueryInListShared(v6) )
  {
    CurrentThreadId = GetCurrentThreadId();
    if ( (unsigned int)IDriverLockPriority(v6, CurrentThreadId, 1) )
    {
      AcquireLockExclusive((LPCRITICAL_SECTION)(v6 + 128));
      if ( (unsigned int)IDriverPrioritiesRestore(gplag) )
        IDriverBroadcastNotify(v6);
      ReleaseLock(v6 + 128);
      IDriverLockPriority(v6, CurrentThreadId, 2);
    }
  }
  *(_DWORD *)(struct HACMOBJ__ *)pMetric = hao[4];
  return 0;
}

```

## disassembly

```asm
0x18000da50  push    rbx
0x18000da52  push    rbp
0x18000da53  push    rsi
0x18000da54  push    rdi
0x18000da55  push    r14
0x18000da57  sub     rsp, 20h
0x18000da5b  mov     rbx, r8
0x18000da5e  mov     r14d, edx
0x18000da61  mov     rsi, rcx
0x18000da64  call    pagFindAndBoot
0x18000da69  mov     rbp, rax
0x18000da6c  test    rax, rax
0x18000da6f  jnz     short loc_18000DA79
0x18000da71  lea     eax, [rbp+1]
0x18000da74  jmp     loc_18000DDCF
0x18000da79  test    rsi, rsi
0x18000da7c  jz      short loc_18000DA90
0x18000da7e  xor     edx, edx
0x18000da80  mov     rcx, rsi
0x18000da83  call    ValidateHandle
0x18000da88  test    eax, eax
0x18000da8a  jz      loc_18000DDAC
0x18000da90  cmp     r14d, 16h
0x18000da94  ja      loc_18000DB96
0x18000da9a  jz      loc_18000DB69
0x18000daa0  mov     eax, r14d
0x18000daa3  sub     eax, 1
0x18000daa6  jz      loc_18000DB36
0x18000daac  sub     eax, 1
0x18000daaf  jz      short loc_18000DADF
0x18000dab1  sub     eax, 1
0x18000dab4  jz      loc_18000DB69
0x18000daba  sub     eax, 1
0x18000dabd  jz      loc_18000DD87
0x18000dac3  sub     eax, 1
0x18000dac6  jz      loc_18000DD5B
0x18000dacc  sub     eax, 1
0x18000dacf  jz      short loc_18000DB0F
0x18000dad1  sub     eax, 0Eh
0x18000dad4  jz      short loc_18000DB36
0x18000dad6  cmp     eax, 1
0x18000dad9  jnz     loc_18000DBDD
0x18000dadf  mov     edx, 4
0x18000dae4  mov     rcx, rbx
0x18000dae7  call    ValidateWritePointer
0x18000daec  test    eax, eax
0x18000daee  jz      loc_18000DD9A
0x18000daf4  test    rsi, rsi
0x18000daf7  jnz     loc_18000DDA6
0x18000dafd  lea     edi, [rsi+1]
0x18000db00  mov     r8d, 40000001h
0x18000db06  cmp     r14d, 15h
0x18000db0a  jmp     loc_18000DDBD
0x18000db0f  mov     edx, 4
0x18000db14  mov     rcx, rbx
0x18000db17  call    ValidateWritePointer
0x18000db1c  test    eax, eax
0x18000db1e  jz      loc_18000DD9A
0x18000db24  test    rsi, rsi
0x18000db27  jnz     loc_18000DDA6
0x18000db2d  lea     r8d, [rsi+8]
0x18000db31  jmp     loc_18000DDC1
0x18000db36  mov     edx, 4
0x18000db3b  mov     rcx, rbx
0x18000db3e  call    ValidateWritePointer
0x18000db43  test    eax, eax
0x18000db45  jz      loc_18000DD9A
0x18000db4b  test    rsi, rsi
0x18000db4e  jnz     loc_18000DDA6
0x18000db54  xor     eax, eax
0x18000db56  mov     r8d, 40000000h
0x18000db5c  cmp     r14d, 14h
0x18000db60  cmovnz  r8d, eax
0x18000db64  jmp     loc_18000DDC1
0x18000db69  mov     edx, 4
0x18000db6e  mov     rcx, rbx
0x18000db71  call    ValidateWritePointer
0x18000db76  test    eax, eax
0x18000db78  jz      loc_18000DD9A
0x18000db7e  test    rsi, rsi
0x18000db81  jnz     loc_18000DDA6
0x18000db87  lea     eax, [rsi+2]
0x18000db8a  mov     r8d, 40000002h
0x18000db90  cmp     r14d, 16h
0x18000db94  jmp     short loc_18000DB60
0x18000db96  mov     eax, r14d
0x18000db99  sub     eax, 17h
0x18000db9c  jz      loc_18000DD87
0x18000dba2  sub     eax, 1
0x18000dba5  jz      loc_18000DD5B
0x18000dbab  sub     eax, 6
0x18000dbae  jz      loc_18000DD1B
0x18000dbb4  sub     eax, 1
0x18000dbb7  jz      loc_18000DD1B
0x18000dbbd  sub     eax, 13h
0x18000dbc0  jz      loc_18000DCF3
0x18000dbc6  sub     eax, 1
0x18000dbc9  jz      loc_18000DCCB
0x18000dbcf  sub     eax, 31h ; '1'
0x18000dbd2  jz      loc_18000DC8B
0x18000dbd8  cmp     eax, 1
0x18000dbdb  jz      short loc_18000DBE7
0x18000dbdd  mov     eax, 8
0x18000dbe2  jmp     loc_18000DDCF
0x18000dbe7  mov     edx, 4
0x18000dbec  mov     rcx, rbx
0x18000dbef  call    ValidateWritePointer
0x18000dbf4  test    eax, eax
0x18000dbf6  jz      loc_18000DD9A
0x18000dbfc  mov     edi, 1
0x18000dc01  mov     dword ptr [rbx], 0
0x18000dc07  mov     edx, edi
0x18000dc09  mov     rcx, rsi
0x18000dc0c  call    ValidateHandle
0x18000dc11  test    eax, eax
0x18000dc13  jz      loc_18000DDAC
0x18000dc19  mov     rcx, rbp
0x18000dc1c  call    threadQueryInListShared
0x18000dc21  test    eax, eax
0x18000dc23  jnz     short loc_18000DC7F
0x18000dc25  call    cs:__imp_GetCurrentThreadId
0x18000dc2b  mov     edx, eax
0x18000dc2d  mov     r8d, edi
0x18000dc30  mov     rcx, rbp
0x18000dc33  mov     r14d, eax
0x18000dc36  call    IDriverLockPriority
0x18000dc3b  test    eax, eax
0x18000dc3d  jz      short loc_18000DC7F
0x18000dc3f  lea     rdi, [rbp+80h]
0x18000dc46  mov     rcx, rdi; lpCriticalSection
0x18000dc49  call    AcquireLockExclusive
0x18000dc4e  mov     rcx, cs:gplag
0x18000dc55  call    IDriverPrioritiesRestore
0x18000dc5a  test    eax, eax
0x18000dc5c  jz      short loc_18000DC66
0x18000dc5e  mov     rcx, rbp
0x18000dc61  call    IDriverBroadcastNotify
0x18000dc66  mov     rcx, rdi
0x18000dc69  call    ReleaseLock
0x18000dc6e  mov     r8d, 2
0x18000dc74  mov     rdx, r14
0x18000dc77  mov     rcx, rbp
0x18000dc7a  call    IDriverLockPriority
0x18000dc7f  mov     eax, [rsi+10h]
0x18000dc82  mov     [rbx], eax
0x18000dc84  xor     eax, eax
0x18000dc86  jmp     loc_18000DDCF
0x18000dc8b  mov     edx, 4
0x18000dc90  mov     rcx, rbx
0x18000dc93  call    ValidateWritePointer
0x18000dc98  test    eax, eax
0x18000dc9a  jz      loc_18000DD9A
0x18000dca0  mov     edx, 1
0x18000dca5  mov     dword ptr [rbx], 0
0x18000dcab  mov     rcx, rsi
0x18000dcae  call    ValidateHandle
0x18000dcb3  test    eax, eax
0x18000dcb5  jz      loc_18000DDAC
0x18000dcbb  mov     rdx, rbx
0x18000dcbe  mov     rcx, rsi
0x18000dcc1  call    IDriverSupport
0x18000dcc6  jmp     loc_18000DDCF
0x18000dccb  mov     edx, 4
0x18000dcd0  mov     rcx, rbx
0x18000dcd3  call    ValidateWritePointer
0x18000dcd8  test    eax, eax
0x18000dcda  jz      loc_18000DD9A
0x18000dce0  mov     r8, rbx
0x18000dce3  mov     rdx, rsi
0x18000dce6  mov     rcx, rbp
0x18000dce9  call    IMetricsMaxSizeFilter
0x18000dcee  jmp     loc_18000DDCF
0x18000dcf3  mov     edx, 4
0x18000dcf8  mov     rcx, rbx
0x18000dcfb  call    ValidateWritePointer
0x18000dd00  test    eax, eax
0x18000dd02  jz      loc_18000DD9A
0x18000dd08  mov     r8, rbx
0x18000dd0b  mov     rdx, rsi
0x18000dd0e  mov     rcx, rbp
0x18000dd11  call    IMetricsMaxSizeFormat
0x18000dd16  jmp     loc_18000DDCF
0x18000dd1b  mov     edx, 4
0x18000dd20  mov     rcx, rbx
0x18000dd23  call    ValidateWritePointer
0x18000dd28  test    eax, eax
0x18000dd2a  jz      short loc_18000DD9A
0x18000dd2c  mov     edx, 1
0x18000dd31  mov     dword ptr [rbx], 0FFFFFFFFh
0x18000dd37  mov     rcx, rsi
0x18000dd3a  call    ValidateHandle
0x18000dd3f  test    eax, eax
0x18000dd41  jz      short loc_18000DDAC
0x18000dd43  xor     r8d, r8d
0x18000dd46  mov     rdx, rbx
0x18000dd49  cmp     r14d, 1Eh
0x18000dd4d  mov     rcx, rsi
0x18000dd50  setz    r8b
0x18000dd54  call    IDriverGetWaveIdentifier
0x18000dd59  jmp     short loc_18000DDCF
0x18000dd5b  mov     edx, 4
0x18000dd60  mov     rcx, rbx
0x18000dd63  call    ValidateWritePointer
0x18000dd68  test    eax, eax
0x18000dd6a  jz      short loc_18000DD9A
0x18000dd6c  test    rsi, rsi
0x18000dd6f  jnz     short loc_18000DDA6
0x18000dd71  cmp     r14d, 18h
0x18000dd75  mov     r8d, 0C0000000h
0x18000dd7b  mov     r9d, 80000000h
0x18000dd81  cmovnz  r8d, r9d
0x18000dd85  jmp     short loc_18000DDC4
0x18000dd87  mov     edi, 4
0x18000dd8c  mov     rcx, rbx
0x18000dd8f  mov     edx, edi
0x18000dd91  call    ValidateWritePointer
0x18000dd96  test    eax, eax
0x18000dd98  jnz     short loc_18000DDA1
0x18000dd9a  mov     eax, 0Bh
0x18000dd9f  jmp     short loc_18000DDCF
0x18000dda1  test    rsi, rsi
0x18000dda4  jz      short loc_18000DDB3
0x18000dda6  mov     dword ptr [rbx], 0
0x18000ddac  mov     eax, 5
0x18000ddb1  jmp     short loc_18000DDCF
0x18000ddb3  mov     r8d, 40000004h
0x18000ddb9  cmp     r14d, 17h
0x18000ddbd  cmovnz  r8d, edi
0x18000ddc1  xor     r9d, r9d
0x18000ddc4  mov     rdx, rbx
0x18000ddc7  mov     rcx, rbp
0x18000ddca  call    IDriverCount
0x18000ddcf  add     rsp, 20h
0x18000ddd3  pop     r14
0x18000ddd5  pop     rdi
0x18000ddd6  pop     rsi
0x18000ddd7  pop     rbp
0x18000ddd8  pop     rbx
0x18000ddd9  retn
```
