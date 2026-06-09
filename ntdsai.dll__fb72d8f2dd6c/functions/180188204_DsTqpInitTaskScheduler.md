# DsTqpInitTaskScheduler

- ea: `0x180188204`
- end: `0x1801884c5`
- name: `DsTqpInitTaskScheduler`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a504c`

## callees

- `0x18000bb20`
- `0x18000ff94`
- `0x180030b60`
- `0x180181db0`
- `0x180188204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18018845d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18018845d`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18018842e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18018842e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180188440`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180188375`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180188375`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18018835a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18018835a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801884aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801884aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018849d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018849d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180188322`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180188322`

## pseudocode

```c
__int64 __fastcall DsTqpInitTaskScheduler(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // edx
  int v13; // esi
  HANDLE EventA; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned int v17; // r9d
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  DWORD LastError; // eax
  unsigned int *v22; // rax

  if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) )
  {
    v8 = CheckWPPLevelFlagsEnabledForProvider(0, v7, 3);
    WPP_SF__ATTRTYP_LOG_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      234881388,
      4,
      3,
      v8,
      0,
      11,
      (__int64)&WPP_3d9c1e2b694232a5d7bc16b921e7a205_Traceguids);
  }
  if ( dword_180E57328 )
    return (unsigned int)dword_180E57328;
  if ( a2 < 0x3F )
  {
    v13 = 0;
    RtlInitializeGenericTableAvl(&stru_180E57350, DsTqpCompareTime, DsTqpAlloc, DsTqpFree, 0);
    qword_180E57348 = 0;
    qword_180E57340 = 0;
    hEvent = 0;
    hThread = 0;
    qword_180E577C8 = a4;
    if ( InitializeCriticalSectionAndSpinCount(&gDsTaskQueue, 0x190u) )
    {
      v13 = 1;
      EventA = CreateEventA(0, 0, 1, 0);
      hEvent = EventA;
    }
    else
    {
      EventA = hEvent;
    }
    if ( EventA )
    {
      qword_180E575B8 = (__int64)EventA;
      v17 = 0;
      v18 = 1;
      dword_180E577B8 = 1;
      qword_180E573B8 = 0;
      if ( a2 )
      {
        v19 = 0;
        do
        {
          if ( *(_QWORD *)(a3 + 16 * v19) )
          {
            v20 = *(_QWORD *)(a3 + 16 * v19 + 8);
            if ( v20 )
            {
              *((_QWORD *)&gDsTaskQueue + v18 + 23) = v20;
              *((_QWORD *)&gDsTaskQueue + (unsigned int)dword_180E577B8 + 87) = *(_QWORD *)(a3 + 16 * v19);
              v18 = (unsigned int)++dword_180E577B8;
            }
          }
          ++v17;
          ++v19;
        }
        while ( v17 < a2 );
      }
      hThread = (HANDLE)_o__beginthreadex(0, 0, DsTqpTaskScheduler, &gDsTaskQueue, 4, (char *)&qword_180E57348 + 4);
      if ( hThread )
      {
        dword_180E57328 = 1;
        dword_180E5732C = 1;
LABEL_24:
        if ( !dword_180E57328 )
        {
          if ( hEvent )
            CloseHandle(hEvent);
          if ( v13 )
            DeleteCriticalSection(&gDsTaskQueue);
        }
        return (unsigned int)dword_180E57328;
      }
      LastError = GetLastError();
      DoLogUnhandledError2(234881471, &word_18049B11A, LastError, 1);
      v22 = (unsigned int *)_o__errno();
      v16 = 234881472;
      v15 = *v22;
    }
    else
    {
      v15 = GetLastError();
      v16 = 234881441;
    }
    DoLogUnhandledError2(v16, &word_18049B11A, v15, 1);
    goto LABEL_24;
  }
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(2) || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, v9, 3) )
  {
    v10 = CheckWPPLevelFlagsEnabledForProvider(0, v9, 3);
    WPP_SF__ATTRTYP_LOG_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      234881399,
      v11,
      3,
      v10,
      0,
      12,
      (__int64)&WPP_3d9c1e2b694232a5d7bc16b921e7a205_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180188204  push    rbx
0x180188206  push    rbp
0x180188207  push    rsi
0x180188208  push    rdi
0x180188209  push    r13
0x18018820b  push    r14
0x18018820d  push    r15
0x18018820f  sub     rsp, 50h
0x180188213  mov     rbp, r9
0x180188216  mov     rdi, r8
0x180188219  mov     ebx, edx
0x18018821b  mov     r15d, 3
0x180188221  xor     ecx, ecx
0x180188223  mov     r8d, r15d
0x180188226  lea     edx, [r15+1]
0x18018822a  call    CheckWPPLevelFlagsEnabledForProvider
0x18018822f  xor     r14d, r14d
0x180188232  lea     r13, WPP_3d9c1e2b694232a5d7bc16b921e7a205_Traceguids
0x180188239  test    eax, eax
0x18018823b  jz      short loc_180188281
0x18018823d  mov     r8d, r15d
0x180188240  xor     ecx, ecx
0x180188242  call    CheckWPPLevelFlagsEnabledForProvider
0x180188247  mov     rcx, cs:WPP_GLOBAL_Control
0x18018824e  lea     r8d, [r15+1]
0x180188252  mov     [rsp+88h+var_40], r14d
0x180188257  mov     r9d, r15d
0x18018825a  mov     [rsp+88h+var_48], ebx
0x18018825e  mov     edx, 0E00016Ch
0x180188263  mov     [rsp+88h+var_50], r13
0x180188268  mov     rcx, [rcx+10h]
0x18018826c  mov     [rsp+88h+var_58], 0Bh
0x180188273  mov     dword ptr [rsp+88h+var_60], r14d
0x180188278  mov     dword ptr [rsp+88h+TableContext], eax
0x18018827c  call    WPP_SF__ATTRTYP_LOG_d
0x180188281  cmp     cs:dword_180E57328, r14d
0x180188288  jnz     loc_1801884B0
0x18018828e  cmp     ebx, 3Fh ; '?'
0x180188291  jb      short loc_1801882FE
0x180188293  mov     edx, 2
0x180188298  mov     ecx, edx
0x18018829a  call    IncrementWPPPerfCountersForLevel
0x18018829f  test    eax, eax
0x1801882a1  jnz     short loc_1801882B1
0x1801882a3  mov     r8d, r15d
0x1801882a6  xor     ecx, ecx
0x1801882a8  call    CheckWPPLevelFlagsEnabledForProvider
0x1801882ad  test    eax, eax
0x1801882af  jz      short loc_1801882F7
0x1801882b1  mov     r8d, r15d
0x1801882b4  xor     ecx, ecx
0x1801882b6  call    CheckWPPLevelFlagsEnabledForProvider
0x1801882bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801882c2  mov     r8d, edx
0x1801882c5  mov     [rsp+88h+var_40], 3Eh ; '>'
0x1801882cd  mov     r9d, r15d
0x1801882d0  mov     [rsp+88h+var_48], ebx
0x1801882d4  mov     edx, 0E000177h
0x1801882d9  mov     [rsp+88h+var_50], r13
0x1801882de  mov     rcx, [rcx+10h]
0x1801882e2  mov     [rsp+88h+var_58], 0Ch
0x1801882e9  mov     dword ptr [rsp+88h+var_60], r14d
0x1801882ee  mov     dword ptr [rsp+88h+TableContext], eax
0x1801882f2  call    WPP_SF__ATTRTYP_LOG_d
0x1801882f7  xor     eax, eax
0x1801882f9  jmp     loc_1801884B6
0x1801882fe  lea     r9, DsTqpFree; FreeRoutine
0x180188305  mov     [rsp+88h+TableContext], r14; TableContext
0x18018830a  lea     r8, DsTqpAlloc; AllocateRoutine
0x180188311  mov     esi, r14d
0x180188314  lea     rdx, DsTqpCompareTime; CompareRoutine
0x18018831b  lea     rcx, stru_180E57350; Table
0x180188322  call    cs:__imp_RtlInitializeGenericTableAvl
0x180188328  lea     r15, gDsTaskQueue
0x18018832f  mov     cs:qword_180E57348, r14
0x180188336  mov     rcx, r15; lpCriticalSection
0x180188339  mov     cs:qword_180E57340, r14
0x180188340  mov     edx, 190h; dwSpinCount
0x180188345  mov     cs:hEvent, r14
0x18018834c  mov     cs:hThread, r14
0x180188353  mov     cs:qword_180E577C8, rbp
0x18018835a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180188360  mov     ebp, 1
0x180188365  test    eax, eax
0x180188367  jz      short loc_180188384
0x180188369  xor     r9d, r9d; lpName
0x18018836c  mov     r8d, ebp; bInitialState
0x18018836f  xor     edx, edx; bManualReset
0x180188371  xor     ecx, ecx; lpEventAttributes
0x180188373  mov     esi, ebp
0x180188375  call    cs:__imp_CreateEventA
0x18018837b  mov     cs:hEvent, rax
0x180188382  jmp     short loc_18018838B
0x180188384  mov     rax, cs:hEvent
0x18018838b  test    rax, rax
0x18018838e  jnz     short loc_1801883A3
0x180188390  call    cs:__imp_GetLastError
0x180188396  mov     r8d, eax
0x180188399  mov     ecx, 0E0001A1h
0x18018839e  jmp     loc_18018846B
0x1801883a3  mov     cs:qword_180E575B8, rax
0x1801883aa  mov     r9d, r14d
0x1801883ad  mov     eax, ebp
0x1801883af  mov     cs:dword_180E577B8, eax
0x1801883b5  mov     cs:qword_180E573B8, r14
0x1801883bc  test    ebx, ebx
0x1801883be  jz      short loc_18018840C
0x1801883c0  mov     r8, r14
0x1801883c3  mov     rdx, r8
0x1801883c6  add     rdx, rdx
0x1801883c9  cmp     [rdi+rdx*8], r14
0x1801883cd  jz      short loc_180188401
0x1801883cf  mov     rcx, [rdi+rdx*8+8]
0x1801883d4  test    rcx, rcx
0x1801883d7  jz      short loc_180188401
0x1801883d9  mov     [r15+rax*8+0B8h], rcx
0x1801883e1  mov     rax, [rdi+rdx*8]
0x1801883e5  mov     ecx, cs:dword_180E577B8
0x1801883eb  mov     [r15+rcx*8+2B8h], rax
0x1801883f3  mov     eax, cs:dword_180E577B8
0x1801883f9  add     eax, ebp
0x1801883fb  mov     cs:dword_180E577B8, eax
0x180188401  add     r9d, ebp
0x180188404  add     r8, rbp
0x180188407  cmp     r9d, ebx
0x18018840a  jb      short loc_1801883C3
0x18018840c  lea     rax, qword_180E57348+4
0x180188413  mov     r9, r15
0x180188416  mov     [rsp+88h+var_60], rax
0x18018841b  lea     r8, DsTqpTaskScheduler
0x180188422  xor     edx, edx
0x180188424  mov     dword ptr [rsp+88h+TableContext], 4
0x18018842c  xor     ecx, ecx
0x18018842e  call    cs:__imp__o__beginthreadex
0x180188434  mov     cs:hThread, rax
0x18018843b  test    rax, rax
0x18018843e  jnz     short loc_18018847C
0x180188440  call    cs:__imp_GetLastError
0x180188446  mov     r9d, ebp
0x180188449  lea     rdx, word_18049B11A
0x180188450  mov     r8d, eax
0x180188453  mov     ecx, 0E0001BFh
0x180188458  call    DoLogUnhandledError2
0x18018845d  call    cs:__imp__o__errno
0x180188463  mov     ecx, 0E0001C0h
0x180188468  mov     r8d, [rax]
0x18018846b  lea     rdx, word_18049B11A
0x180188472  mov     r9d, ebp
0x180188475  call    DoLogUnhandledError2
0x18018847a  jmp     short loc_180188488
0x18018847c  mov     cs:dword_180E57328, ebp
0x180188482  mov     cs:dword_180E5732C, ebp
0x180188488  cmp     cs:dword_180E57328, r14d
0x18018848f  jnz     short loc_1801884B0
0x180188491  mov     rcx, cs:hEvent; hObject
0x180188498  test    rcx, rcx
0x18018849b  jz      short loc_1801884A3
0x18018849d  call    cs:__imp_CloseHandle
0x1801884a3  test    esi, esi
0x1801884a5  jz      short loc_1801884B0
0x1801884a7  mov     rcx, r15; lpCriticalSection
0x1801884aa  call    cs:__imp_DeleteCriticalSection
0x1801884b0  mov     eax, cs:dword_180E57328
0x1801884b6  add     rsp, 50h
0x1801884ba  pop     r15
0x1801884bc  pop     r14
0x1801884be  pop     r13
0x1801884c0  pop     rdi
0x1801884c1  pop     rsi
0x1801884c2  pop     rbp
0x1801884c3  pop     rbx
0x1801884c4  retn
```
