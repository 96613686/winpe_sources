# CReaderWriterLock::_LockSpin(bool)

- ea: `0x180014fc0`
- end: `0x1800150dd`
- name: `?_LockSpin@CReaderWriterLock@@AEAAX_N@Z`
- size: `285`
- prototype: `void __fastcall(CReaderWriterLock *__hidden this, bool)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014f10`
- `0x180014f40`
- `0x180014f80`
- `0x18001ba40`
- `0x18001baa0`

## callees

- `0x180008e70`
- `0x180010b30`
- `0x180014fc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fe2`

## pseudocode

```c
void __fastcall CReaderWriterLock::_LockSpin(CReaderWriterLock *this, char a2)
{
  unsigned int v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // r8d
  bool v10; // zf
  signed __int32 v11; // edx
  char v12; // al

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      SwitchOrSleep(v3);
      v3 = SleepTime(v7);
      v8 = (int)((double)v8 * CReaderWriterLock::sm_dblDfltSpinAdjFctr);
      if ( v8 <= 10000 )
      {
        if ( v8 <= 100 )
          v8 = 100;
      }
      else
      {
        v8 = 10000;
      }
      v6 = CReaderWriterLock::sm_wDefaultSpinCount;
      ++v7;
      goto LABEL_2;
    }
    if ( a2 )
    {
      if ( !*(_DWORD *)this )
      {
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)this, -1, 0) == 0;
        goto LABEL_12;
      }
    }
    else if ( *(_DWORD *)this != -1 && !*((_DWORD *)this + 1) )
    {
      v11 = *(_DWORD *)this;
      v10 = v11 == _InterlockedCompareExchange((volatile signed __int32 *)this, v11 + 1, v11);
LABEL_12:
      v12 = 1;
      if ( v10 )
        goto LABEL_14;
    }
    v12 = 0;
LABEL_14:
    if ( v12 )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x180014fc0  mov     [rsp+arg_0], rbx
0x180014fc5  mov     [rsp+arg_10], rbp
0x180014fca  push    rsi
0x180014fcb  push    rdi
0x180014fcc  push    r13
0x180014fce  push    r14
0x180014fd0  push    r15
0x180014fd2  sub     rsp, 20h
0x180014fd6  xor     r15d, r15d
0x180014fd9  mov     r14b, dl
0x180014fdc  mov     ebp, r15d
0x180014fdf  mov     rdi, rcx
0x180014fe2  call    cs:__imp_GetCurrentThreadId
0x180014fe8  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock@@1GA; ushort CReaderWriterLock::sm_wDefaultSpinCount
0x180014fef  mov     esi, r15d
0x180014ff2  mov     r9d, eax
0x180014ff5  mov     eax, 4EC4EC4Fh
0x180014ffa  mul     r9d
0x180014ffd  movd    xmm0, ecx
0x180015001  cvtdq2pd xmm0, xmm0
0x180015005  shr     edx, 2
0x180015008  imul    r8d, edx, 0Dh
0x18001500c  lea     rdx, qword_180030E80
0x180015013  sub     r9d, r8d
0x180015016  or      r13d, 0FFFFFFFFh
0x18001501a  mulsd   xmm0, qword ptr [rdx+r9*8]
0x180015020  cvttsd2si ebx, xmm0
0x180015024  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18001502b  mov     r8d, ebx
0x18001502e  jb      short loc_180015035
0x180015030  test    cx, cx
0x180015033  jnz     short loc_18001503B
0x180015035  mov     r8d, 1
0x18001503b  sub     r8d, 1
0x18001503f  js      short loc_18001507B
0x180015041  test    r14b, r14b
0x180015044  jz      short loc_180015053
0x180015046  mov     eax, [rdi]
0x180015048  test    eax, eax
0x18001504a  jnz     short loc_180015070
0x18001504c  lock cmpxchg [rdi], r13d
0x180015051  jmp     short loc_18001506C
0x180015053  mov     edx, [rdi]
0x180015055  cmp     edx, r13d
0x180015058  jz      short loc_180015070
0x18001505a  mov     eax, [rdi+4]
0x18001505d  test    eax, eax
0x18001505f  jnz     short loc_180015070
0x180015061  lea     ecx, [rdx+1]
0x180015064  mov     eax, edx
0x180015066  lock cmpxchg [rdi], ecx
0x18001506a  cmp     edx, eax
0x18001506c  mov     al, 1
0x18001506e  jz      short loc_180015073
0x180015070  mov     al, r15b
0x180015073  test    al, al
0x180015075  jnz     short loc_1800150C6
0x180015077  pause
0x180015079  jmp     short loc_18001503B
0x18001507b  mov     ecx, ebp; unsigned int
0x18001507d  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180015082  mov     ecx, esi; unsigned int
0x180015084  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180015089  movd    xmm0, ebx
0x18001508d  mov     ebp, eax
0x18001508f  cvtdq2pd xmm0, xmm0
0x180015093  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock@@1NA; double CReaderWriterLock::sm_dblDfltSpinAdjFctr
0x18001509b  cvttsd2si ebx, xmm0
0x18001509f  cmp     ebx, 2710h
0x1800150a5  jle     short loc_1800150AE
0x1800150a7  mov     ebx, 2710h
0x1800150ac  jmp     short loc_1800150B8
0x1800150ae  mov     eax, 64h ; 'd'
0x1800150b3  cmp     ebx, eax
0x1800150b5  cmovle  ebx, eax
0x1800150b8  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock@@1GA; ushort CReaderWriterLock::sm_wDefaultSpinCount
0x1800150bf  inc     esi
0x1800150c1  jmp     loc_180015024
0x1800150c6  mov     rbx, [rsp+48h+arg_0]
0x1800150cb  mov     rbp, [rsp+48h+arg_10]
0x1800150d0  add     rsp, 20h
0x1800150d4  pop     r15
0x1800150d6  pop     r14
0x1800150d8  pop     r13
0x1800150da  pop     rdi
0x1800150db  pop     rsi
0x1800150dc  retn
```
