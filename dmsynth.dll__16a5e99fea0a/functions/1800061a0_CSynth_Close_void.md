# CSynth::Close(void)

- ea: `0x1800061a0`
- end: `0x18000641a`
- name: `?Close@CSynth@@QEAAJXZ`
- size: `634`
- prototype: `__int64 __fastcall(CSynth *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800114b0`
- `0x1800117f0`

## callees

- `0x180001514`
- `0x1800031f0`
- `0x180003200`
- `0x180003210`
- `0x180006030`
- `0x1800061a0`
- `0x18000a210`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800063db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800063f4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800063db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800063f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006408`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006408`

## pseudocode

```c
__int64 __fastcall CSynth::Close(CSynth *this)
{
  unsigned int i; // r14d
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rbx
  CCutOffFreqIn *v7; // rdi
  __int64 v8; // rbx
  CCutOffFreqIn *v9; // rdi
  __int64 v10; // rbx
  CCutOffFreqIn *v11; // rdi
  __int64 v12; // rbx
  CCutOffFreqIn *v13; // rdi
  __int64 v14; // rbx
  CCutOffFreqIn *v15; // rdi
  __int64 v16; // rbx
  CCutOffFreqIn *v17; // rdi
  __int64 v18; // rbx
  CCutOffFreqIn *v19; // rdi
  __int64 v20; // rbx
  CCutOffFreqIn *v21; // rdi
  CCutOffFreqIn *v22; // rbx
  __int64 v23; // rdi
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  CSynth::AllNotesOff(this);
  for ( i = 0; i < *((_DWORD *)this + 260); ++i )
  {
    v3 = *(_QWORD *)(*((_QWORD *)this + 129) + 8LL * i);
    if ( v3 )
    {
      v4 = 16;
      v5 = v3 + 7112;
      do
      {
        v5 -= 132;
        --v4;
      }
      while ( v4 );
      v6 = 16;
      v7 = (CCutOffFreqIn *)(v3 + 5000);
      do
      {
        v7 = (CCutOffFreqIn *)((char *)v7 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v7);
        --v6;
      }
      while ( v6 );
      CWaveIn::~CWaveIn((CWaveIn *)(v3 + 4544));
      v8 = 16;
      v9 = (CCutOffFreqIn *)(v3 + 3240);
      do
      {
        v9 = (CCutOffFreqIn *)((char *)v9 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v9);
        --v8;
      }
      while ( v8 );
      v10 = 16;
      v11 = (CCutOffFreqIn *)(v3 + 2856);
      do
      {
        v11 = (CCutOffFreqIn *)((char *)v11 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v11);
        --v10;
      }
      while ( v10 );
      v12 = 16;
      v13 = (CCutOffFreqIn *)(v3 + 2472);
      do
      {
        v13 = (CCutOffFreqIn *)((char *)v13 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v13);
        --v12;
      }
      while ( v12 );
      v14 = 16;
      v15 = (CCutOffFreqIn *)(v3 + 2088);
      do
      {
        v15 = (CCutOffFreqIn *)((char *)v15 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v15);
        --v14;
      }
      while ( v14 );
      v16 = 16;
      v17 = (CCutOffFreqIn *)(v3 + 1704);
      do
      {
        v17 = (CCutOffFreqIn *)((char *)v17 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v17);
        --v16;
      }
      while ( v16 );
      v18 = 16;
      v19 = (CCutOffFreqIn *)(v3 + 1320);
      do
      {
        v19 = (CCutOffFreqIn *)((char *)v19 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v19);
        --v18;
      }
      while ( v18 );
      v20 = 16;
      v21 = (CCutOffFreqIn *)(v3 + 936);
      do
      {
        v21 = (CCutOffFreqIn *)((char *)v21 - 32);
        CCutOffFreqIn::~CCutOffFreqIn(v21);
        --v20;
      }
      while ( v20 );
      v22 = (CCutOffFreqIn *)(v3 + 424);
      v23 = 16;
      do
      {
        v22 = (CCutOffFreqIn *)((char *)v22 - 24);
        CCutOffFreqIn::~CCutOffFreqIn(v22);
        --v23;
      }
      while ( v23 );
      CMIDIRecorder::~CMIDIRecorder((CMIDIRecorder *)(v3 + 16));
      operator delete((void *)v3);
    }
  }
  v24 = (void *)*((_QWORD *)this + 129);
  *((_DWORD *)this + 260) = 0;
  if ( v24 )
  {
    operator delete(v24);
    *((_QWORD *)this + 129) = 0;
  }
  v25 = (void *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 34) = 0;
  if ( v25 )
  {
    free(v25);
    *((_QWORD *)this + 19) = 0;
  }
  v26 = (void *)*((_QWORD *)this + 18);
  if ( v26 )
  {
    free(v26);
    *((_QWORD *)this + 18) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  return 0;
}

```

## disassembly

```asm
0x1800061a0  push    rbp
0x1800061a2  push    r12
0x1800061a4  push    r13
0x1800061a6  sub     rsp, 30h
0x1800061aa  mov     rbp, rcx
0x1800061ad  mov     [rsp+48h+var_20], r14
0x1800061b2  add     rcx, 418h; lpCriticalSection
0x1800061b9  mov     [rsp+48h+var_28], r15
0x1800061be  call    cs:__imp_EnterCriticalSection
0x1800061c4  mov     rcx, rbp; this
0x1800061c7  call    ?AllNotesOff@CSynth@@QEAAJXZ; CSynth::AllNotesOff(void)
0x1800061cc  xor     r13d, r13d
0x1800061cf  mov     r14d, r13d
0x1800061d2  cmp     [rbp+410h], r13d
0x1800061d9  jbe     loc_180006397
0x1800061df  mov     [rsp+48h+arg_0], rbx
0x1800061e4  mov     [rsp+48h+arg_8], rsi
0x1800061e9  mov     [rsp+48h+arg_10], rdi
0x1800061ee  xchg    ax, ax
0x1800061f0  mov     rax, [rbp+408h]
0x1800061f7  mov     ecx, r14d
0x1800061fa  mov     rsi, [rax+rcx*8]
0x1800061fe  test    rsi, rsi
0x180006201  jz      loc_180006378
0x180006207  mov     ebx, 10h
0x18000620c  lea     rdi, [rsi+1BC8h]
0x180006213  nop     dword ptr [rax+00h]
0x180006217  nop     word ptr [rax+rax+00000000h]
0x180006220  sub     rdi, 84h
0x180006227  mov     rcx, rdi
0x18000622a  call    _guard_check_icall_nop
0x18000622f  sub     rbx, 1
0x180006233  jnz     short loc_180006220
0x180006235  mov     ebx, 10h
0x18000623a  lea     rdi, [rsi+1388h]
0x180006241  sub     rdi, 18h
0x180006245  mov     rcx, rdi; this
0x180006248  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x18000624d  sub     rbx, 1
0x180006251  jnz     short loc_180006241
0x180006253  lea     rcx, [rsi+11C0h]; this
0x18000625a  call    ??1CWaveIn@@QEAA@XZ; CWaveIn::~CWaveIn(void)
0x18000625f  mov     ebx, 10h
0x180006264  lea     rdi, [rsi+0CA8h]
0x18000626b  nop     dword ptr [rax+rax+00h]
0x180006270  sub     rdi, 18h
0x180006274  mov     rcx, rdi; this
0x180006277  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x18000627c  sub     rbx, 1
0x180006280  jnz     short loc_180006270
0x180006282  mov     ebx, 10h
0x180006287  lea     rdi, [rsi+0B28h]
0x18000628e  xchg    ax, ax
0x180006290  sub     rdi, 18h
0x180006294  mov     rcx, rdi; this
0x180006297  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x18000629c  sub     rbx, 1
0x1800062a0  jnz     short loc_180006290
0x1800062a2  mov     ebx, 10h
0x1800062a7  lea     rdi, [rsi+9A8h]
0x1800062ae  xchg    ax, ax
0x1800062b0  sub     rdi, 18h
0x1800062b4  mov     rcx, rdi; this
0x1800062b7  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x1800062bc  sub     rbx, 1
0x1800062c0  jnz     short loc_1800062B0
0x1800062c2  mov     ebx, 10h
0x1800062c7  lea     rdi, [rsi+828h]
0x1800062ce  xchg    ax, ax
0x1800062d0  sub     rdi, 18h
0x1800062d4  mov     rcx, rdi; this
0x1800062d7  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x1800062dc  sub     rbx, 1
0x1800062e0  jnz     short loc_1800062D0
0x1800062e2  mov     ebx, 10h
0x1800062e7  lea     rdi, [rsi+6A8h]
0x1800062ee  xchg    ax, ax
0x1800062f0  sub     rdi, 18h
0x1800062f4  mov     rcx, rdi; this
0x1800062f7  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x1800062fc  sub     rbx, 1
0x180006300  jnz     short loc_1800062F0
0x180006302  mov     ebx, 10h
0x180006307  lea     rdi, [rsi+528h]
0x18000630e  xchg    ax, ax
0x180006310  sub     rdi, 18h
0x180006314  mov     rcx, rdi; this
0x180006317  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x18000631c  sub     rbx, 1
0x180006320  jnz     short loc_180006310
0x180006322  mov     ebx, 10h
0x180006327  lea     rdi, [rsi+3A8h]
0x18000632e  xchg    ax, ax
0x180006330  sub     rdi, 20h ; ' '
0x180006334  mov     rcx, rdi; this
0x180006337  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x18000633c  sub     rbx, 1
0x180006340  jnz     short loc_180006330
0x180006342  lea     rbx, [rsi+1A8h]
0x180006349  mov     edi, 10h
0x18000634e  xchg    ax, ax
0x180006350  sub     rbx, 18h
0x180006354  mov     rcx, rbx; this
0x180006357  call    ??1CCutOffFreqIn@@QEAA@XZ; CCutOffFreqIn::~CCutOffFreqIn(void)
0x18000635c  sub     rdi, 1
0x180006360  jnz     short loc_180006350
0x180006362  lea     rcx, [rsi+10h]; this
0x180006366  call    ??1CMIDIRecorder@@QEAA@XZ; CMIDIRecorder::~CMIDIRecorder(void)
0x18000636b  mov     edx, 1BC8h; unsigned __int64
0x180006370  mov     rcx, rsi; void *
0x180006373  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006378  inc     r14d
0x18000637b  cmp     r14d, [rbp+410h]
0x180006382  jb      loc_1800061F0
0x180006388  mov     rdi, [rsp+48h+arg_10]
0x18000638d  mov     rsi, [rsp+48h+arg_8]
0x180006392  mov     rbx, [rsp+48h+arg_0]
0x180006397  mov     rcx, [rbp+408h]; void *
0x18000639e  mov     r14, [rsp+48h+var_20]
0x1800063a3  mov     [rbp+410h], r13d
0x1800063aa  test    rcx, rcx
0x1800063ad  jz      short loc_1800063BB
0x1800063af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800063b4  mov     [rbp+408h], r13
0x1800063bb  mov     rcx, [rbp+98h]; Block
0x1800063c2  mov     r15, [rsp+48h+var_28]
0x1800063c7  mov     [rbp+50h], r13
0x1800063cb  mov     [rbp+28h], r13
0x1800063cf  mov     [rbp+88h], r13d
0x1800063d6  test    rcx, rcx
0x1800063d9  jz      short loc_1800063E8
0x1800063db  call    cs:__imp_free
0x1800063e1  mov     [rbp+98h], r13
0x1800063e8  mov     rcx, [rbp+90h]; Block
0x1800063ef  test    rcx, rcx
0x1800063f2  jz      short loc_180006401
0x1800063f4  call    cs:__imp_free
0x1800063fa  mov     [rbp+90h], r13
0x180006401  lea     rcx, [rbp+418h]; lpCriticalSection
0x180006408  call    cs:__imp_LeaveCriticalSection
0x18000640e  xor     eax, eax
0x180006410  add     rsp, 30h
0x180006414  pop     r13
0x180006416  pop     r12
0x180006418  pop     rbp
0x180006419  retn
```
