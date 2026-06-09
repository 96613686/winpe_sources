# TlgRegisterAggregateProviderEx

- ea: `0x180004998`
- end: `0x180004b4a`
- name: `TlgRegisterAggregateProviderEx`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800020c0`

## callees

- `0x18000142c`
- `0x180003bdc`
- `0x180003e78`
- `0x180004998`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004b32`
- `KERNEL32!HeapFree` at `0x180004b32`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004b07`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004b07`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004aa8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004aa8`
- `KERNEL32!GetProcessHeap` at `0x180004b24`
- `KERNEL32!GetProcessHeap` at `0x180004b24`

## pseudocode

```c
__int64 __fastcall TlgRegisterAggregateProviderEx(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  RTL_SRWLOCK *TlgAggregateSession; // rax
  _DWORD *v4; // rbx
  unsigned int v6; // edx
  __int128 v7; // xmm0
  unsigned __int64 v8; // r8
  int v9; // eax
  unsigned __int64 i; // r8
  int v11; // eax
  int v12; // esi
  __int64 v13; // rax
  __int64 *v14; // rcx
  HANDLE ProcessHeap; // rax
  __int128 v16; // [rsp+20h] [rbp-18h]
  unsigned __int64 v17; // [rsp+50h] [rbp+18h]

  v17 = a3;
  TlgAggregateSession = CreateTlgAggregateSession(1);
  v4 = TlgAggregateSession;
  if ( !TlgAggregateSession )
    return TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18000A008);
  TlgAggregateSession[39].Ptr = 0;
  TlgAggregateSession[41].Ptr = &dword_18000A008;
  v6 = 0;
  TlgAggregateSession[40].Ptr = 0;
  v7 = *(_OWORD *)&(*off_18000A010)[-16];
  v17 = (unsigned __int64)TlgAggregateSession >> 4;
  v8 = 0;
  v16 = v7;
  do
  {
    v9 = *((unsigned __int8 *)&v16 + v8++);
    v6 = (1025 * (v6 + v9)) ^ ((1025 * (v6 + v9)) >> 6);
  }
  while ( v8 < 0x10 );
  for ( i = 0; i < 8; ++i )
  {
    v11 = *((unsigned __int8 *)&v17 + i);
    v6 = (1025 * (v6 + v11)) ^ ((1025 * (v6 + v11)) >> 6);
  }
  v4[88] = 32769 * ((9 * v6) ^ ((9 * v6) >> 11)) % 0x927C0 + 600000;
  v12 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18000A008);
  if ( v12 < 0 )
  {
    qword_18000A030 = 0;
    CancelTimerCallbacksAndDeleteTimer((__int64)v4);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    return (unsigned int)v12;
  }
  else
  {
    AcquireSRWLockExclusive(&SRWLock);
    v13 = qword_18000A730;
    if ( qword_18000A730
      || (TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18000A040), (v13 = qword_18000A730) != 0) )
    {
      while ( *(int **)(v13 + 328) != &dword_18000A008 )
      {
        v14 = (__int64 *)(v13 + 336);
        v13 = *(_QWORD *)(v13 + 336);
        if ( !v13 )
          goto LABEL_14;
      }
    }
    else
    {
      v14 = &qword_18000A730;
LABEL_14:
      *v14 = (__int64)v4;
    }
    ReleaseSRWLockExclusive(&SRWLock);
    return 0;
  }
}

```

## disassembly

```asm
0x180004998  mov     [rsp+arg_0], rbx
0x18000499d  mov     [rsp+arg_8], rsi
0x1800049a2  mov     [rsp+arg_10], r8
0x1800049a7  push    rdi
0x1800049a8  sub     rsp, 30h
0x1800049ac  mov     cl, 1
0x1800049ae  call    CreateTlgAggregateSession
0x1800049b3  mov     rbx, rax
0x1800049b6  test    rax, rax
0x1800049b9  jnz     short loc_1800049D1
0x1800049bb  xor     r8d, r8d
0x1800049be  lea     rcx, dword_18000A008; CallbackContext
0x1800049c5  xor     edx, edx
0x1800049c7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800049cc  jmp     loc_180004B3A
0x1800049d1  mov     qword ptr [rax+138h], 0
0x1800049dc  lea     rdi, dword_18000A008
0x1800049e3  mov     [rax+148h], rdi
0x1800049ea  xor     edx, edx
0x1800049ec  mov     qword ptr [rax+140h], 0
0x1800049f7  mov     rax, cs:off_18000A010
0x1800049fe  movups  xmm0, xmmword ptr [rax-10h]
0x180004a02  mov     rax, rbx
0x180004a05  shr     rax, 4
0x180004a09  mov     [rsp+38h+arg_10], rax
0x180004a0e  xor     r8d, r8d
0x180004a11  movdqu  [rsp+38h+var_18], xmm0
0x180004a17  movzx   eax, byte ptr [rsp+r8+38h+var_18]
0x180004a1d  inc     r8
0x180004a20  add     eax, edx
0x180004a22  imul    ecx, eax, 401h
0x180004a28  mov     edx, ecx
0x180004a2a  shr     edx, 6
0x180004a2d  xor     edx, ecx
0x180004a2f  cmp     r8, 10h
0x180004a33  jb      short loc_180004A17
0x180004a35  xor     r8d, r8d
0x180004a38  movzx   eax, byte ptr [rsp+r8+38h+arg_10]
0x180004a3e  inc     r8
0x180004a41  add     eax, edx
0x180004a43  imul    ecx, eax, 401h
0x180004a49  mov     edx, ecx
0x180004a4b  shr     edx, 6
0x180004a4e  xor     edx, ecx
0x180004a50  cmp     r8, 8
0x180004a54  jb      short loc_180004A38
0x180004a56  lea     eax, [rdx+rdx*8]
0x180004a59  mov     ecx, eax
0x180004a5b  shr     ecx, 0Bh
0x180004a5e  xor     ecx, eax
0x180004a60  mov     eax, 6FD91D85h
0x180004a65  imul    r8d, ecx, 8001h
0x180004a6c  mov     rcx, rdi; CallbackContext
0x180004a6f  mul     r8d
0x180004a72  shr     edx, 12h
0x180004a75  imul    eax, edx, 927C0h
0x180004a7b  lea     rdx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180004a82  sub     r8d, eax
0x180004a85  add     r8d, 927C0h
0x180004a8c  mov     [rbx+160h], r8d
0x180004a93  mov     r8, rbx
0x180004a96  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180004a9b  mov     esi, eax
0x180004a9d  test    eax, eax
0x180004a9f  js      short loc_180004B11
0x180004aa1  lea     rcx, SRWLock; SRWLock
0x180004aa8  call    cs:__imp_AcquireSRWLockExclusive
0x180004aae  mov     rax, cs:qword_18000A730
0x180004ab5  test    rax, rax
0x180004ab8  jnz     short loc_180004ADC
0x180004aba  xor     r8d, r8d
0x180004abd  lea     rdx, ?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180004ac4  lea     rcx, dword_18000A040; CallbackContext
0x180004acb  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180004ad0  mov     rax, cs:qword_18000A730
0x180004ad7  test    rax, rax
0x180004ada  jz      short loc_180004AF6
0x180004adc  cmp     [rax+148h], rdi
0x180004ae3  jz      short loc_180004B00
0x180004ae5  lea     rcx, [rax+150h]
0x180004aec  mov     rax, [rcx]
0x180004aef  test    rax, rax
0x180004af2  jnz     short loc_180004ADC
0x180004af4  jmp     short loc_180004AFD
0x180004af6  lea     rcx, qword_18000A730
0x180004afd  mov     [rcx], rbx
0x180004b00  lea     rcx, SRWLock; SRWLock
0x180004b07  call    cs:__imp_ReleaseSRWLockExclusive
0x180004b0d  xor     eax, eax
0x180004b0f  jmp     short loc_180004B3A
0x180004b11  mov     rcx, rbx
0x180004b14  mov     cs:qword_18000A030, 0
0x180004b1f  call    CancelTimerCallbacksAndDeleteTimer
0x180004b24  call    cs:__imp_GetProcessHeap
0x180004b2a  mov     r8, rbx; lpMem
0x180004b2d  xor     edx, edx; dwFlags
0x180004b2f  mov     rcx, rax; hHeap
0x180004b32  call    cs:__imp_HeapFree
0x180004b38  mov     eax, esi
0x180004b3a  mov     rbx, [rsp+38h+arg_0]
0x180004b3f  mov     rsi, [rsp+38h+arg_8]
0x180004b44  add     rsp, 30h
0x180004b48  pop     rdi
0x180004b49  retn
```
