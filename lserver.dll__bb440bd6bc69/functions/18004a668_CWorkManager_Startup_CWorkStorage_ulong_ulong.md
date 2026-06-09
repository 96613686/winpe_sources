# CWorkManager::Startup(CWorkStorage *,ulong,ulong)

- ea: `0x18004a668`
- end: `0x18004a88d`
- name: `?Startup@CWorkManager@@QEAAKPEAVCWorkStorage@@KK@Z`
- size: `549`
- prototype: `unsigned int __fastcall(CWorkManager *__hidden this, struct CWorkStorage *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180025c1c`

## callees

- `0x18001ad74`
- `0x18004a668`
- `0x18004a894`
- `0x1800a5010`

## import_xrefs

- `msvcrt!__doserrno` at `0x18004a871`
- `msvcrt!__doserrno` at `0x18004a871`
- `msvcrt!_beginthreadex` at `0x18004a859`
- `msvcrt!_beginthreadex` at `0x18004a859`
- `KERNEL32!CreateSemaphoreW` at `0x18004a693`
- `KERNEL32!CreateSemaphoreW` at `0x18004a693`
- `KERNEL32!CreateEventW` at `0x18004a706`
- `KERNEL32!CreateEventW` at `0x18004a731`
- `KERNEL32!CreateEventW` at `0x18004a760`
- `KERNEL32!CreateEventW` at `0x18004a78f`
- `KERNEL32!CreateEventW` at `0x18004a706`
- `KERNEL32!CreateEventW` at `0x18004a731`
- `KERNEL32!CreateEventW` at `0x18004a760`
- `KERNEL32!CreateEventW` at `0x18004a78f`
- `KERNEL32!GetLastError` at `0x18004a6bd`
- `KERNEL32!GetLastError` at `0x18004a7e4`
- `KERNEL32!GetLastError` at `0x18004a80f`
- `KERNEL32!GetLastError` at `0x18004a6bd`
- `KERNEL32!GetLastError` at `0x18004a7e4`
- `KERNEL32!GetLastError` at `0x18004a80f`

## pseudocode

```c
__int64 __fastcall CWorkManager::Startup(CWorkManager *this, struct CWorkStorage *a2)
{
  DWORD v2; // ebx
  HANDLE SemaphoreW; // rax
  DWORD LastError; // eax
  unsigned int ThrdAddr; // [rsp+58h] [rbp+20h] BYREF

  v2 = 0;
  ThrdAddr = 0;
  if ( !qword_1800E9368 )
  {
    SemaphoreW = CreateSemaphoreW(0, 50, 50, 0);
    qword_1800E9370 = 0;
    qword_1800E9368 = (__int64)SemaphoreW;
    dword_1800E9378 = 50;
    if ( !SemaphoreW )
      return GetLastError();
  }
  if ( ((dword_1800E9360 = 50, qword_1800E9380 = (__int64)&g_WorkStorage, dword_1800E935C = 900000, qword_1800E9328)
     || (qword_1800E9328 = (__int64)CreateEventW(0, 1, 1, 0)) != 0)
    && ((_QWORD)xmmword_1800E9340
     || (*(_QWORD *)&xmmword_1800E9340 = CreateEventW(0, 1, 0, 0), (_QWORD)xmmword_1800E9340))
    && (*((_QWORD *)&xmmword_1800E9330 + 1) || (*((_QWORD *)&xmmword_1800E9330 + 1) = CreateEventW(0, 1, 1, 0)) != 0)
    && (*((_QWORD *)&xmmword_1800E9340 + 1) || (*((_QWORD *)&xmmword_1800E9340 + 1) = CreateEventW(0, 1, 1, 0)) != 0) )
  {
    if ( (**(unsigned int (__fastcall ***)(__int64, __int64 *))qword_1800E9380)(qword_1800E9380, &g_WorkManager) )
    {
      if ( !(unsigned int)CWorkManager::UpdateTimeToNextPersistentJob((CWorkManager *)&g_WorkManager) )
        return 1075904515;
      if ( !(_QWORD)xmmword_1800E9330 )
      {
        *(_QWORD *)&xmmword_1800E9330 = _beginthreadex(
                                          0,
                                          0,
                                          CWorkManager::WorkManagerThread,
                                          &g_WorkManager,
                                          0,
                                          &ThrdAddr);
        if ( !(_QWORD)xmmword_1800E9330 )
          return *__doserrno();
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids, LastError);
      }
      v2 = GetLastError();
      if ( !v2 )
        return 1075904515;
    }
  }
  else
  {
    return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x18004a668  mov     [rsp+arg_0], rbx
0x18004a66d  mov     [rsp+arg_18], r9d
0x18004a672  push    rsi
0x18004a673  sub     rsp, 30h
0x18004a677  xor     ebx, ebx
0x18004a679  and     [rsp+38h+arg_18], ebx
0x18004a67d  cmp     cs:qword_1800E9368, rbx
0x18004a684  lea     esi, [rbx+32h]
0x18004a687  jnz     short loc_18004A6D0
0x18004a689  xor     r9d, r9d; lpName
0x18004a68c  mov     r8d, esi; lMaximumCount
0x18004a68f  mov     edx, esi; lInitialCount
0x18004a691  xor     ecx, ecx; lpSemaphoreAttributes
0x18004a693  call    cs:__imp_CreateSemaphoreW
0x18004a69a  nop     dword ptr [rax+rax+00h]
0x18004a69f  and     dword ptr cs:qword_1800E9370, ebx
0x18004a6a5  and     dword ptr cs:qword_1800E9370+4, ebx
0x18004a6ab  mov     cs:qword_1800E9368, rax
0x18004a6b2  mov     cs:dword_1800E9378, esi
0x18004a6b8  test    rax, rax
0x18004a6bb  jnz     short loc_18004A6D0
0x18004a6bd  call    cs:__imp_GetLastError
0x18004a6c4  nop     dword ptr [rax+rax+00h]
0x18004a6c9  mov     ebx, eax
0x18004a6cb  jmp     loc_18004A87F
0x18004a6d0  cmp     cs:qword_1800E9328, rbx
0x18004a6d7  lea     rax, ?g_WorkStorage@@3VCPersistentWorkStorage@@A; CPersistentWorkStorage g_WorkStorage
0x18004a6de  mov     cs:dword_1800E9360, esi
0x18004a6e4  mov     esi, 1
0x18004a6e9  mov     cs:qword_1800E9380, rax
0x18004a6f0  mov     cs:dword_1800E935C, 0DBBA0h
0x18004a6fa  jnz     short loc_18004A71E
0x18004a6fc  xor     r9d, r9d; lpName
0x18004a6ff  mov     r8d, esi; bInitialState
0x18004a702  mov     edx, esi; bManualReset
0x18004a704  xor     ecx, ecx; lpEventAttributes
0x18004a706  call    cs:__imp_CreateEventW
0x18004a70d  nop     dword ptr [rax+rax+00h]
0x18004a712  mov     cs:qword_1800E9328, rax
0x18004a719  test    rax, rax
0x18004a71c  jz      short loc_18004A6BD
0x18004a71e  cmp     qword ptr cs:xmmword_1800E9340, rbx
0x18004a725  jnz     short loc_18004A74D
0x18004a727  xor     r9d, r9d; lpName
0x18004a72a  xor     r8d, r8d; bInitialState
0x18004a72d  mov     edx, esi; bManualReset
0x18004a72f  xor     ecx, ecx; lpEventAttributes
0x18004a731  call    cs:__imp_CreateEventW
0x18004a738  nop     dword ptr [rax+rax+00h]
0x18004a73d  mov     qword ptr cs:xmmword_1800E9340, rax
0x18004a744  test    rax, rax
0x18004a747  jz      loc_18004A6BD
0x18004a74d  cmp     qword ptr cs:xmmword_1800E9330+8, rbx
0x18004a754  jnz     short loc_18004A77C
0x18004a756  xor     r9d, r9d; lpName
0x18004a759  mov     r8d, esi; bInitialState
0x18004a75c  mov     edx, esi; bManualReset
0x18004a75e  xor     ecx, ecx; lpEventAttributes
0x18004a760  call    cs:__imp_CreateEventW
0x18004a767  nop     dword ptr [rax+rax+00h]
0x18004a76c  mov     qword ptr cs:xmmword_1800E9330+8, rax
0x18004a773  test    rax, rax
0x18004a776  jz      loc_18004A6BD
0x18004a77c  cmp     qword ptr cs:xmmword_1800E9340+8, rbx
0x18004a783  jnz     short loc_18004A7AB
0x18004a785  xor     r9d, r9d; lpName
0x18004a788  mov     r8d, esi; bInitialState
0x18004a78b  mov     edx, esi; bManualReset
0x18004a78d  xor     ecx, ecx; lpEventAttributes
0x18004a78f  call    cs:__imp_CreateEventW
0x18004a796  nop     dword ptr [rax+rax+00h]
0x18004a79b  mov     qword ptr cs:xmmword_1800E9340+8, rax
0x18004a7a2  test    rax, rax
0x18004a7a5  jz      loc_18004A6BD
0x18004a7ab  mov     rcx, cs:qword_1800E9380
0x18004a7b2  lea     rsi, ?g_WorkManager@@3VCWorkManager@@A; CWorkManager g_WorkManager
0x18004a7b9  mov     rdx, rsi
0x18004a7bc  mov     rax, [rcx]
0x18004a7bf  mov     rax, [rax]
0x18004a7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7c7  test    eax, eax
0x18004a7c9  jnz     short loc_18004A828
0x18004a7cb  mov     rax, cs:WPP_GLOBAL_Control
0x18004a7d2  lea     rcx, WPP_GLOBAL_Control
0x18004a7d9  cmp     rax, rcx
0x18004a7dc  jz      short loc_18004A80F
0x18004a7de  test    byte ptr [rax+1Ch], 40h
0x18004a7e2  jz      short loc_18004A80F
0x18004a7e4  call    cs:__imp_GetLastError
0x18004a7eb  nop     dword ptr [rax+rax+00h]
0x18004a7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a7f7  lea     r8, WPP_0ce7f016aabd318d7b95e346aacd31e1_Traceguids
0x18004a7fe  mov     edx, 21h ; '!'
0x18004a803  mov     r9d, eax
0x18004a806  mov     rcx, [rcx+10h]
0x18004a80a  call    WPP_SF_D
0x18004a80f  call    cs:__imp_GetLastError
0x18004a816  nop     dword ptr [rax+rax+00h]
0x18004a81b  mov     ebx, eax
0x18004a81d  test    eax, eax
0x18004a81f  jnz     short loc_18004A87F
0x18004a821  mov     ebx, 40210003h
0x18004a826  jmp     short loc_18004A87F
0x18004a828  mov     rcx, rsi; this
0x18004a82b  call    ?UpdateTimeToNextPersistentJob@CWorkManager@@AEAAHXZ; CWorkManager::UpdateTimeToNextPersistentJob(void)
0x18004a830  test    eax, eax
0x18004a832  jz      short loc_18004A821
0x18004a834  cmp     qword ptr cs:xmmword_1800E9330, rbx
0x18004a83b  jnz     short loc_18004A87F
0x18004a83d  lea     rax, [rsp+38h+arg_18]
0x18004a842  mov     r9, rsi; ArgList
0x18004a845  mov     [rsp+38h+ThrdAddr], rax; ThrdAddr
0x18004a84a  lea     r8, ?WorkManagerThread@CWorkManager@@CAIPEAX@Z; StartAddress
0x18004a851  and     [rsp+38h+var_18], ebx
0x18004a855  xor     edx, edx; StackSize
0x18004a857  xor     ecx, ecx; Security
0x18004a859  call    cs:__imp__beginthreadex
0x18004a860  nop     dword ptr [rax+rax+00h]
0x18004a865  mov     qword ptr cs:xmmword_1800E9330, rax
0x18004a86c  test    rax, rax
0x18004a86f  jnz     short loc_18004A87F
0x18004a871  call    cs:__imp___doserrno
0x18004a878  nop     dword ptr [rax+rax+00h]
0x18004a87d  mov     ebx, [rax]
0x18004a87f  mov     eax, ebx
0x18004a881  mov     rbx, [rsp+38h+arg_0]
0x18004a886  add     rsp, 30h
0x18004a88a  pop     rsi
0x18004a88b  retn
```
