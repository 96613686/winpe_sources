# TlgRegisterAggregateProviderEx

- ea: `0x180007ed8`
- end: `0x18000808a`
- name: `TlgRegisterAggregateProviderEx`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001f8c`

## callees

- `0x18000142c`
- `0x180007130`
- `0x1800073bc`
- `0x180007ed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007fe8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007fe8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008047`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008064`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008072`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008072`

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
    return TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18000D000);
  TlgAggregateSession[39].Ptr = 0;
  TlgAggregateSession[41].Ptr = &dword_18000D000;
  v6 = 0;
  TlgAggregateSession[40].Ptr = 0;
  v7 = *((_OWORD *)off_18000D008 - 1);
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
  v12 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18000D000);
  if ( v12 < 0 )
  {
    qword_18000D028 = 0;
    CancelTimerCallbacksAndDeleteTimer((__int64)v4);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    return (unsigned int)v12;
  }
  else
  {
    AcquireSRWLockExclusive(&SRWLock);
    v13 = qword_18000D728;
    if ( qword_18000D728
      || (TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18000D040), (v13 = qword_18000D728) != 0) )
    {
      while ( *(int **)(v13 + 328) != &dword_18000D000 )
      {
        v14 = (__int64 *)(v13 + 336);
        v13 = *(_QWORD *)(v13 + 336);
        if ( !v13 )
          goto LABEL_14;
      }
    }
    else
    {
      v14 = &qword_18000D728;
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
0x180007ed8  mov     [rsp+arg_0], rbx
0x180007edd  mov     [rsp+arg_8], rsi
0x180007ee2  mov     [rsp+arg_10], r8
0x180007ee7  push    rdi
0x180007ee8  sub     rsp, 30h
0x180007eec  mov     cl, 1
0x180007eee  call    CreateTlgAggregateSession
0x180007ef3  mov     rbx, rax
0x180007ef6  test    rax, rax
0x180007ef9  jnz     short loc_180007F11
0x180007efb  xor     r8d, r8d
0x180007efe  lea     rcx, dword_18000D000; CallbackContext
0x180007f05  xor     edx, edx
0x180007f07  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180007f0c  jmp     loc_18000807A
0x180007f11  mov     qword ptr [rax+138h], 0
0x180007f1c  lea     rdi, dword_18000D000
0x180007f23  mov     [rax+148h], rdi
0x180007f2a  xor     edx, edx
0x180007f2c  mov     qword ptr [rax+140h], 0
0x180007f37  mov     rax, cs:off_18000D008
0x180007f3e  movups  xmm0, xmmword ptr [rax-10h]
0x180007f42  mov     rax, rbx
0x180007f45  shr     rax, 4
0x180007f49  mov     [rsp+38h+arg_10], rax
0x180007f4e  xor     r8d, r8d
0x180007f51  movdqu  [rsp+38h+var_18], xmm0
0x180007f57  movzx   eax, byte ptr [rsp+r8+38h+var_18]
0x180007f5d  inc     r8
0x180007f60  add     eax, edx
0x180007f62  imul    ecx, eax, 401h
0x180007f68  mov     edx, ecx
0x180007f6a  shr     edx, 6
0x180007f6d  xor     edx, ecx
0x180007f6f  cmp     r8, 10h
0x180007f73  jb      short loc_180007F57
0x180007f75  xor     r8d, r8d
0x180007f78  movzx   eax, byte ptr [rsp+r8+38h+arg_10]
0x180007f7e  inc     r8
0x180007f81  add     eax, edx
0x180007f83  imul    ecx, eax, 401h
0x180007f89  mov     edx, ecx
0x180007f8b  shr     edx, 6
0x180007f8e  xor     edx, ecx
0x180007f90  cmp     r8, 8
0x180007f94  jb      short loc_180007F78
0x180007f96  lea     eax, [rdx+rdx*8]
0x180007f99  mov     ecx, eax
0x180007f9b  shr     ecx, 0Bh
0x180007f9e  xor     ecx, eax
0x180007fa0  mov     eax, 6FD91D85h
0x180007fa5  imul    r8d, ecx, 8001h
0x180007fac  mov     rcx, rdi; CallbackContext
0x180007faf  mul     r8d
0x180007fb2  shr     edx, 12h
0x180007fb5  imul    eax, edx, 927C0h
0x180007fbb  lea     rdx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180007fc2  sub     r8d, eax
0x180007fc5  add     r8d, 927C0h
0x180007fcc  mov     [rbx+160h], r8d
0x180007fd3  mov     r8, rbx
0x180007fd6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180007fdb  mov     esi, eax
0x180007fdd  test    eax, eax
0x180007fdf  js      short loc_180008051
0x180007fe1  lea     rcx, SRWLock; SRWLock
0x180007fe8  call    cs:__imp_AcquireSRWLockExclusive
0x180007fee  mov     rax, cs:qword_18000D728
0x180007ff5  test    rax, rax
0x180007ff8  jnz     short loc_18000801C
0x180007ffa  xor     r8d, r8d
0x180007ffd  lea     rdx, ?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180008004  lea     rcx, dword_18000D040; CallbackContext
0x18000800b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180008010  mov     rax, cs:qword_18000D728
0x180008017  test    rax, rax
0x18000801a  jz      short loc_180008036
0x18000801c  cmp     [rax+148h], rdi
0x180008023  jz      short loc_180008040
0x180008025  lea     rcx, [rax+150h]
0x18000802c  mov     rax, [rcx]
0x18000802f  test    rax, rax
0x180008032  jnz     short loc_18000801C
0x180008034  jmp     short loc_18000803D
0x180008036  lea     rcx, qword_18000D728
0x18000803d  mov     [rcx], rbx
0x180008040  lea     rcx, SRWLock; SRWLock
0x180008047  call    cs:__imp_ReleaseSRWLockExclusive
0x18000804d  xor     eax, eax
0x18000804f  jmp     short loc_18000807A
0x180008051  mov     rcx, rbx
0x180008054  mov     cs:qword_18000D028, 0
0x18000805f  call    CancelTimerCallbacksAndDeleteTimer
0x180008064  call    cs:__imp_GetProcessHeap
0x18000806a  mov     r8, rbx; lpMem
0x18000806d  xor     edx, edx; dwFlags
0x18000806f  mov     rcx, rax; hHeap
0x180008072  call    cs:__imp_HeapFree
0x180008078  mov     eax, esi
0x18000807a  mov     rbx, [rsp+38h+arg_0]
0x18000807f  mov     rsi, [rsp+38h+arg_8]
0x180008084  add     rsp, 30h
0x180008088  pop     rdi
0x180008089  retn
```
