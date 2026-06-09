# CSynth::SetSampleRate(ulong)

- ea: `0x1800074b0`
- end: `0x1800075df`
- name: `?SetSampleRate@CSynth@@QEAAJK@Z`
- size: `303`
- prototype: `__int64 __fastcall(CSynth *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a70`
- `0x180005f60`
- `0x1800133b0`

## callees

- `0x180006030`
- `0x1800074b0`
- `0x180009890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800074e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007568`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800074e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007568`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000754a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000754a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800075cb`

## pseudocode

```c
__int64 __fastcall CSynth::SetSampleRate(CSynth *this, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v5; // rcx
  __int64 v6; // rax
  char *v7; // r14
  struct _RTL_CRITICAL_SECTION *v8; // r15
  __int64 i; // rbp
  _QWORD *j; // rdi
  _QWORD *k; // rbx
  CSourceArticulation *v12; // rcx

  v2 = a2;
  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  CSynth::AllNotesOff(this);
  v5 = *((unsigned int *)this + 52);
  v6 = *((_QWORD *)this + 5) * v2;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 52) = v2;
  *((_QWORD *)this + 5) = v6 / v5;
  *((_QWORD *)this + 24) = (unsigned int)v2 / 0x64;
  *((_QWORD *)this + 25) = ((int)v2 + 19) / 0x14u;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  v7 = (char *)this + 216;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 984);
  *((_DWORD *)this + 180) = v2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  for ( i = 0; i != 31; ++i )
  {
    for ( j = *(_QWORD **)&v7[8 * i]; j; j = (_QWORD *)*j )
    {
      for ( k = (_QWORD *)j[1]; k; k = (_QWORD *)*k )
      {
        v12 = (CSourceArticulation *)k[6];
        if ( v12 )
          CSourceArticulation::SetSampleRate(v12, v2);
      }
    }
  }
  LeaveCriticalSection(v8);
  return 0;
}

```

## disassembly

```asm
0x1800074b0  push    rsi
0x1800074b2  push    rdi
0x1800074b3  sub     rsp, 28h
0x1800074b7  mov     esi, edx
0x1800074b9  mov     rdi, rcx
0x1800074bc  test    edx, edx
0x1800074be  jnz     short loc_1800074CC
0x1800074c0  mov     eax, 80070057h
0x1800074c5  add     rsp, 28h
0x1800074c9  pop     rdi
0x1800074ca  pop     rsi
0x1800074cb  retn
0x1800074cc  mov     [rsp+38h+arg_0], rbx
0x1800074d1  add     rcx, 418h; lpCriticalSection
0x1800074d8  mov     [rsp+38h+arg_8], rbp
0x1800074dd  mov     [rsp+38h+arg_10], r14
0x1800074e2  mov     [rsp+38h+var_18], r15
0x1800074e7  call    cs:__imp_EnterCriticalSection
0x1800074ed  mov     rcx, rdi; this
0x1800074f0  call    ?AllNotesOff@CSynth@@QEAAJXZ; CSynth::AllNotesOff(void)
0x1800074f5  mov     ecx, [rdi+0D0h]
0x1800074fb  mov     rax, rsi
0x1800074fe  imul    rax, [rdi+28h]
0x180007503  mov     qword ptr [rdi+50h], 0
0x18000750b  cqo
0x18000750d  mov     [rdi+0D0h], esi
0x180007513  idiv    rcx
0x180007516  lea     rcx, [rdi+418h]; lpCriticalSection
0x18000751d  mov     [rdi+28h], rax
0x180007521  mov     eax, 51EB851Fh
0x180007526  mul     esi
0x180007528  shr     edx, 5
0x18000752b  mov     eax, edx
0x18000752d  lea     edx, [rsi+13h]
0x180007530  mov     [rdi+0C0h], rax
0x180007537  mov     eax, 0CCCCCCCDh
0x18000753c  mul     edx
0x18000753e  shr     edx, 4
0x180007541  mov     eax, edx
0x180007543  mov     [rdi+0C8h], rax
0x18000754a  call    cs:__imp_LeaveCriticalSection
0x180007550  lea     r14, [rdi+0D8h]
0x180007557  lea     r15, [r14+300h]
0x18000755e  mov     [r14+1F8h], esi
0x180007565  mov     rcx, r15; lpCriticalSection
0x180007568  call    cs:__imp_EnterCriticalSection
0x18000756e  xor     ebp, ebp
0x180007570  mov     rdi, [r14+rbp*8]
0x180007574  test    rdi, rdi
0x180007577  jz      short loc_1800075B0
0x180007579  nop     dword ptr [rax+00000000h]
0x180007580  mov     rbx, [rdi+8]
0x180007584  test    rbx, rbx
0x180007587  jz      short loc_1800075A8
0x180007589  nop     dword ptr [rax+00000000h]
0x180007590  mov     rcx, [rbx+30h]; this
0x180007594  test    rcx, rcx
0x180007597  jz      short loc_1800075A0
0x180007599  mov     edx, esi; unsigned int
0x18000759b  call    ?SetSampleRate@CSourceArticulation@@QEAAXK@Z; CSourceArticulation::SetSampleRate(ulong)
0x1800075a0  mov     rbx, [rbx]
0x1800075a3  test    rbx, rbx
0x1800075a6  jnz     short loc_180007590
0x1800075a8  mov     rdi, [rdi]
0x1800075ab  test    rdi, rdi
0x1800075ae  jnz     short loc_180007580
0x1800075b0  inc     rbp
0x1800075b3  cmp     rbp, 1Fh
0x1800075b7  jnz     short loc_180007570
0x1800075b9  mov     r14, [rsp+38h+arg_10]
0x1800075be  mov     rcx, r15; lpCriticalSection
0x1800075c1  mov     rbp, [rsp+38h+arg_8]
0x1800075c6  mov     rbx, [rsp+38h+arg_0]
0x1800075cb  call    cs:__imp_LeaveCriticalSection
0x1800075d1  mov     r15, [rsp+38h+var_18]
0x1800075d6  xor     eax, eax
0x1800075d8  add     rsp, 28h
0x1800075dc  pop     rdi
0x1800075dd  pop     rsi
0x1800075de  retn
```
