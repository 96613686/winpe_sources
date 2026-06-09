# LagCounterManager::PerfCollectDataCallback(ushort *,void * *,ulong *,ulong *)

- ea: `0x180006f98`
- end: `0x180007660`
- name: `?PerfCollectDataCallback@LagCounterManager@@SAKPEAGPEAPEAXPEAK2@Z`
- size: `1736`
- prototype: `unsigned int __fastcall(wchar_t *Source, void **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003bb0`

## callees

- `0x1800026b0`
- `0x180005fe0`
- `0x180006f98`
- `0x180009930`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000701c`
- `msvcrt!wcscpy_s` at `0x18000701c`
- `msvcrt!wcsstr` at `0x180007038`
- `msvcrt!wcsstr` at `0x180007075`
- `msvcrt!wcsstr` at `0x1800070a8`
- `msvcrt!wcsstr` at `0x180007038`
- `msvcrt!wcsstr` at `0x180007075`
- `msvcrt!wcsstr` at `0x1800070a8`
- `msvcrt!_wcslwr_s` at `0x180007028`
- `msvcrt!_wcslwr_s` at `0x180007028`
- `msvcrt!_ultow_s` at `0x180007067`
- `msvcrt!_ultow_s` at `0x18000709a`
- `msvcrt!_ultow_s` at `0x180007067`
- `msvcrt!_ultow_s` at `0x18000709a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800070c9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800070c9`
- `KERNEL32!CreateMutexW` at `0x1800070f9`
- `KERNEL32!CreateMutexW` at `0x18000753c`
- `KERNEL32!CreateMutexW` at `0x1800070f9`
- `KERNEL32!CreateMutexW` at `0x18000753c`
- `KERNEL32!WaitForSingleObject` at `0x18000710c`
- `KERNEL32!WaitForSingleObject` at `0x18000754f`
- `KERNEL32!WaitForSingleObject` at `0x18000710c`
- `KERNEL32!WaitForSingleObject` at `0x18000754f`
- `KERNEL32!ReleaseMutex` at `0x18000717f`
- `KERNEL32!ReleaseMutex` at `0x180007584`
- `KERNEL32!ReleaseMutex` at `0x180007629`
- `KERNEL32!ReleaseMutex` at `0x18000717f`
- `KERNEL32!ReleaseMutex` at `0x180007584`
- `KERNEL32!ReleaseMutex` at `0x180007629`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall LagCounterManager::PerfCollectDataCallback(
        wchar_t *Source,
        void **a2,
        unsigned int *a3,
        unsigned int *a4)
{
  _OWORD *v7; // rdi
  __int64 v8; // rax
  rsize_t v9; // rsi
  int v10; // r13d
  wchar_t *v11; // rbx
  int v12; // r12d
  BOOL v13; // esi
  HANDLE MutexW; // rax
  unsigned int v15; // ecx
  int v16; // eax
  __int64 *v18; // rbx
  struct _USER_INPUT_DELAY_INSTANCE *PerfInstance; // rax
  __int64 *i; // rax
  __int64 *v21; // rcx
  void **v22; // r15
  _OWORD *v23; // rdi
  __int64 *v24; // rbx
  struct _USER_INPUT_DELAY_INSTANCE *v25; // rax
  __int64 *j; // rax
  __int64 *v27; // rcx
  struct _USER_INPUT_DELAY_INSTANCE *v28; // rax
  char *v29; // rdi
  CounterHelper *v30; // rbx
  HANDLE v31; // rax
  BOOL v32; // [rsp+20h] [rbp-A8h]
  wchar_t Buffer[40]; // [rsp+30h] [rbp-98h] BYREF

  v7 = *a2;
  v32 = CounterHelper::MachineCounter != 0;
  v8 = -1;
  do
    ++v8;
  while ( Source[v8] );
  v9 = v8 + 1;
  v10 = 2;
  v11 = (wchar_t *)operator new[](saturated_mul(v8 + 1, 2u));
  wcscpy_s(v11, v9, Source);
  _wcslwr_s(v11, v9);
  if ( wcsstr(v11, L"global") )
  {
    v12 = 1;
    v13 = 1;
  }
  else
  {
    _ultow_s(*(unsigned int *)&LagCounterManager::dwFirstCounter, Buffer, 0x21u, 10);
    v13 = wcsstr(v11, Buffer) != 0;
    _ultow_s(*(_DWORD *)&LagCounterManager::dwFirstCounter + 2, Buffer, 0x21u, 10);
    if ( wcsstr(v11, Buffer) )
    {
      v12 = 1;
    }
    else
    {
      v12 = v13;
      v10 = 0;
    }
  }
  if ( v11 )
    operator delete[](v11);
  if ( !v12 || !LagCounterManager::dwOpenPerfCount )
  {
    *a3 = 0;
    *a4 = 0;
    return 0;
  }
  MutexW = CounterHelper::LagCounterMajorEvent;
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  dword_180012D30 = qword_180012DA0;
  v15 = 184 * qword_180012DA0 + 144;
  LagCounterManager::ProcessDef = v15;
  if ( v10 )
  {
    dword_180012CA0 = qword_180012DB0;
    v16 = qword_180012DB0 + 2;
    if ( v32 )
      dword_180012CA0 = qword_180012DB0 + 2;
    else
      v16 = qword_180012DB0;
    LagCounterManager::SessionDef = 184 * v16 + 144;
    v15 += LagCounterManager::SessionDef;
  }
  if ( *a3 < v15 )
  {
    *a3 = 0;
    *a4 = 0;
    ReleaseMutex(CounterHelper::LagCounterMajorEvent);
    return 234;
  }
  *a3 = v15;
  if ( v13 )
  {
    dword_180012D30 = qword_180012DA0;
    *v7 = LagCounterManager::ProcessDef;
    v7[1] = xmmword_180012D18;
    v7[2] = unk_180012D28;
    v7[3] = xmmword_180012D38;
    v7[4] = xmmword_180012D48;
    v7[5] = xmmword_180012D58;
    v7[6] = xmmword_180012D68;
    v7[7] = xmmword_180012D78;
    v7[8] = xmmword_180012D88;
    v7 += 9;
    v18 = *(__int64 **)CounterHelper::ProcessesToCounter;
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( v18 == (__int64 *)CounterHelper::ProcessesToCounter )
          {
            ++*a4;
            v22 = a2;
            *a2 = v7;
            goto LABEL_36;
          }
          PerfInstance = CounterHelper::GetPerfInstance((CounterHelper *)v18[5]);
          *v7 = *(_OWORD *)PerfInstance;
          v7[1] = *((_OWORD *)PerfInstance + 1);
          v7[2] = *((_OWORD *)PerfInstance + 2);
          v7[3] = *((_OWORD *)PerfInstance + 3);
          v7[4] = *((_OWORD *)PerfInstance + 4);
          v7[5] = *((_OWORD *)PerfInstance + 5);
          v7[6] = *((_OWORD *)PerfInstance + 6);
          v7[7] = *((_OWORD *)PerfInstance + 7);
          v7[8] = *((_OWORD *)PerfInstance + 8);
          v7[9] = *((_OWORD *)PerfInstance + 9);
          v7[10] = *((_OWORD *)PerfInstance + 10);
          *((_QWORD *)v7 + 22) = *((_QWORD *)PerfInstance + 22);
          v7 = (_OWORD *)((char *)v7 + 184);
        }
        while ( *((_BYTE *)v18 + 25) );
        i = (__int64 *)v18[2];
        if ( !*((_BYTE *)i + 25) )
          break;
        for ( i = (__int64 *)v18[1]; !*((_BYTE *)i + 25) && v18 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v18 = i;
LABEL_33:
        v18 = i;
      }
      v21 = (__int64 *)*i;
      if ( *(_BYTE *)(*i + 25) )
        goto LABEL_33;
      do
      {
        v18 = v21;
        v21 = (__int64 *)*v21;
      }
      while ( !*((_BYTE *)v21 + 25) );
    }
  }
  v22 = a2;
LABEL_36:
  if ( !v10 )
    goto LABEL_56;
  dword_180012CA0 = qword_180012DB0;
  if ( v32 )
    dword_180012CA0 = qword_180012DB0 + 2;
  *v7 = LagCounterManager::SessionDef;
  v7[1] = xmmword_180012C88;
  v7[2] = unk_180012C98;
  v7[3] = xmmword_180012CA8;
  v7[4] = xmmword_180012CB8;
  v7[5] = xmmword_180012CC8;
  v7[6] = xmmword_180012CD8;
  v7[7] = xmmword_180012CE8;
  v7[8] = xmmword_180012CF8;
  v23 = v7 + 9;
  v24 = *(__int64 **)CounterHelper::SessionToCounter;
  while ( v24 != (__int64 *)CounterHelper::SessionToCounter )
  {
    v25 = CounterHelper::GetPerfInstance((CounterHelper *)v24[5]);
    *v23 = *(_OWORD *)v25;
    v23[1] = *((_OWORD *)v25 + 1);
    v23[2] = *((_OWORD *)v25 + 2);
    v23[3] = *((_OWORD *)v25 + 3);
    v23[4] = *((_OWORD *)v25 + 4);
    v23[5] = *((_OWORD *)v25 + 5);
    v23[6] = *((_OWORD *)v25 + 6);
    v23[7] = *((_OWORD *)v25 + 7);
    v23[8] = *((_OWORD *)v25 + 8);
    v23[9] = *((_OWORD *)v25 + 9);
    v23[10] = *((_OWORD *)v25 + 10);
    *((_QWORD *)v23 + 22) = *((_QWORD *)v25 + 22);
    v23 = (_OWORD *)((char *)v23 + 184);
    if ( !*((_BYTE *)v24 + 25) )
    {
      j = (__int64 *)v24[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( j = (__int64 *)v24[1]; !*((_BYTE *)j + 25) && v24 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v24 = j;
LABEL_50:
        v24 = j;
      }
      else
      {
        v27 = (__int64 *)*j;
        if ( *(_BYTE *)(*j + 25) )
          goto LABEL_50;
        do
        {
          v24 = v27;
          v27 = (__int64 *)*v27;
        }
        while ( !*((_BYTE *)v27 + 25) );
      }
    }
  }
  if ( v32 )
  {
    v28 = CounterHelper::GetPerfInstance(CounterHelper::MachineCounter);
    *v23 = *(_OWORD *)v28;
    v23[1] = *((_OWORD *)v28 + 1);
    v23[2] = *((_OWORD *)v28 + 2);
    v23[3] = *((_OWORD *)v28 + 3);
    v23[4] = *((_OWORD *)v28 + 4);
    v23[5] = *((_OWORD *)v28 + 5);
    v23[6] = *((_OWORD *)v28 + 6);
    v23[7] = *((_OWORD *)v28 + 7);
    v23[8] = *((_OWORD *)v28 + 8);
    v23[9] = *((_OWORD *)v28 + 9);
    v23[10] = *((_OWORD *)v28 + 10);
    *((_QWORD *)v23 + 22) = *((_QWORD *)v28 + 22);
    v29 = (char *)v23 + 184;
    v30 = CounterHelper::MachineCounter;
    v31 = CounterHelper::LagCounterMajorEvent;
    if ( !CounterHelper::LagCounterMajorEvent )
    {
      v31 = CreateMutexW(0, 0, 0);
      CounterHelper::LagCounterMajorEvent = v31;
    }
    WaitForSingleObject(v31, 0xFFFFFFFF);
    *((_QWORD *)v30 + 1) += *((_QWORD *)v30 + 5);
    *((_DWORD *)v30 + 101) = *((_DWORD *)v30 + 8);
    *((_QWORD *)v30 + 51) = *((_QWORD *)v30 + 1);
    *((_QWORD *)v30 + 5) = 0;
    ReleaseMutex(CounterHelper::LagCounterMajorEvent);
    *(_OWORD *)v29 = *(_OWORD *)((char *)v30 + 232);
    *((_OWORD *)v29 + 1) = *(_OWORD *)((char *)v30 + 248);
    *((_OWORD *)v29 + 2) = *(_OWORD *)((char *)v30 + 264);
    *((_OWORD *)v29 + 3) = *(_OWORD *)((char *)v30 + 280);
    *((_OWORD *)v29 + 4) = *(_OWORD *)((char *)v30 + 296);
    *((_OWORD *)v29 + 5) = *(_OWORD *)((char *)v30 + 312);
    *((_OWORD *)v29 + 6) = *(_OWORD *)((char *)v30 + 328);
    *((_OWORD *)v29 + 7) = *(_OWORD *)((char *)v30 + 344);
    *((_OWORD *)v29 + 8) = *(_OWORD *)((char *)v30 + 360);
    *((_OWORD *)v29 + 9) = *(_OWORD *)((char *)v30 + 376);
    *((_OWORD *)v29 + 10) = *(_OWORD *)((char *)v30 + 392);
    *((_QWORD *)v29 + 22) = *((_QWORD *)v30 + 51);
    v23 = v29 + 184;
  }
  ++*a4;
  *v22 = v23;
LABEL_56:
  ReleaseMutex(CounterHelper::LagCounterMajorEvent);
  return 0;
}

```

## disassembly

```asm
0x180006f98  push    rbx
0x180006f9a  push    rsi
0x180006f9b  push    rdi
0x180006f9c  push    r12
0x180006f9e  push    r13
0x180006fa0  push    r14
0x180006fa2  push    r15
0x180006fa4  sub     rsp, 90h
0x180006fab  mov     rax, cs:__security_cookie
0x180006fb2  xor     rax, rsp
0x180006fb5  mov     [rsp+0C8h+var_48], rax
0x180006fbd  mov     r14, r9
0x180006fc0  mov     r15, r8
0x180006fc3  mov     [rsp+0C8h+var_A0], rdx
0x180006fc8  mov     r12, rcx
0x180006fcb  xor     ecx, ecx
0x180006fcd  mov     eax, ecx
0x180006fcf  mov     rdi, [rdx]
0x180006fd2  lea     edx, [rcx+1]
0x180006fd5  cmp     cs:?MachineCounter@CounterHelper@@2PEAV1@EA, rcx; CounterHelper * CounterHelper::MachineCounter
0x180006fdc  cmovnz  eax, edx
0x180006fdf  mov     [rsp+0C8h+var_A8], eax
0x180006fe3  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006fe7  mov     rax, r8
0x180006fea  inc     rax
0x180006fed  cmp     [r12+rax*2], cx
0x180006ff2  jnz     short loc_180006FEA
0x180006ff4  lea     rsi, [rax+1]
0x180006ff8  mov     r13d, 2
0x180006ffe  mov     eax, r13d
0x180007001  mul     rsi
0x180007004  cmovb   rax, r8
0x180007008  mov     rcx, rax; unsigned __int64
0x18000700b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007010  mov     rbx, rax
0x180007013  mov     r8, r12; Source
0x180007016  mov     rdx, rsi; SizeInWords
0x180007019  mov     rcx, rax; Destination
0x18000701c  call    cs:__imp_wcscpy_s
0x180007022  mov     rdx, rsi; SizeInWords
0x180007025  mov     rcx, rbx; String
0x180007028  call    cs:__imp__wcslwr_s
0x18000702e  lea     rdx, aGlobal; "global"
0x180007035  mov     rcx, rbx; Str
0x180007038  call    cs:__imp_wcsstr
0x18000703e  xor     ecx, ecx
0x180007040  test    rax, rax
0x180007043  jz      short loc_18000704F
0x180007045  lea     eax, [rcx+1]
0x180007048  mov     r12d, eax
0x18000704b  mov     esi, eax
0x18000704d  jmp     short loc_1800070C1
0x18000704f  mov     r9d, 0Ah; Radix
0x180007055  lea     r12d, [r9+17h]
0x180007059  mov     r8d, r12d; BufferCount
0x18000705c  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x180007061  mov     ecx, cs:?dwFirstCounter@LagCounterManager@@2KA; Value
0x180007067  call    cs:__imp__ultow_s
0x18000706d  lea     rdx, [rsp+0C8h+Buffer]; SubStr
0x180007072  mov     rcx, rbx; Str
0x180007075  call    cs:__imp_wcsstr
0x18000707b  xor     esi, esi
0x18000707d  test    rax, rax
0x180007080  setnz   sil
0x180007084  mov     ecx, cs:?dwFirstCounter@LagCounterManager@@2KA; ulong LagCounterManager::dwFirstCounter
0x18000708a  add     ecx, r13d; Value
0x18000708d  lea     r9d, [r12-17h]; Radix
0x180007092  mov     r8d, r12d; BufferCount
0x180007095  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x18000709a  call    cs:__imp__ultow_s
0x1800070a0  lea     rdx, [rsp+0C8h+Buffer]; SubStr
0x1800070a5  mov     rcx, rbx; Str
0x1800070a8  call    cs:__imp_wcsstr
0x1800070ae  xor     ecx, ecx
0x1800070b0  test    rax, rax
0x1800070b3  jz      short loc_1800070BB
0x1800070b5  lea     r12d, [rcx+1]
0x1800070b9  jmp     short loc_1800070C1
0x1800070bb  mov     r12d, esi
0x1800070be  mov     r13d, ecx
0x1800070c1  test    rbx, rbx
0x1800070c4  jz      short loc_1800070D1
0x1800070c6  mov     rcx, rbx
0x1800070c9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800070cf  xor     ecx, ecx
0x1800070d1  test    r12d, r12d
0x1800070d4  jz      loc_180007654
0x1800070da  cmp     cs:?dwOpenPerfCount@LagCounterManager@@2KA, ecx; ulong LagCounterManager::dwOpenPerfCount
0x1800070e0  jz      loc_180007654
0x1800070e6  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x1800070ed  test    rax, rax
0x1800070f0  jnz     short loc_180007106
0x1800070f2  xor     r8d, r8d; lpName
0x1800070f5  xor     edx, edx; bInitialOwner
0x1800070f7  xor     ecx, ecx; lpMutexAttributes
0x1800070f9  call    cs:__imp_CreateMutexW
0x1800070ff  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x180007106  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007109  mov     rcx, rax; hHandle
0x18000710c  call    cs:__imp_WaitForSingleObject
0x180007112  mov     eax, dword ptr cs:qword_180012DA0
0x180007118  mov     cs:dword_180012D30, eax
0x18000711e  imul    ecx, eax, 0B8h
0x180007124  add     ecx, 90h
0x18000712a  mov     dword ptr cs:?ProcessDef@LagCounterManager@@2U_USER_INPUT_DELAY_DEFINITION@@A, ecx; _USER_INPUT_DELAY_DEFINITION LagCounterManager::ProcessDef
0x180007130  xor     r8d, r8d
0x180007133  mov     r12d, [rsp+0C8h+var_A8]
0x180007138  test    r13d, r13d
0x18000713b  jz      short loc_18000716D
0x18000713d  mov     edx, dword ptr cs:qword_180012DB0
0x180007143  mov     cs:dword_180012CA0, edx
0x180007149  lea     eax, [rdx+2]
0x18000714c  test    r12d, r12d
0x18000714f  jz      short loc_180007157
0x180007151  mov     cs:dword_180012CA0, eax
0x180007157  cmovz   eax, edx
0x18000715a  imul    eax, 0B8h
0x180007160  add     eax, 90h
0x180007165  mov     dword ptr cs:?SessionDef@LagCounterManager@@2U_USER_INPUT_DELAY_DEFINITION@@A, eax; _USER_INPUT_DELAY_DEFINITION LagCounterManager::SessionDef
0x18000716b  add     ecx, eax
0x18000716d  cmp     [r15], ecx
0x180007170  jnb     short loc_18000718F
0x180007172  mov     [r15], r8d
0x180007175  mov     [r14], r8d
0x180007178  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x18000717f  call    cs:__imp_ReleaseMutex
0x180007185  mov     eax, 0EAh
0x18000718a  jmp     loc_180007631
0x18000718f  mov     [r15], ecx
0x180007192  test    esi, esi
0x180007194  mov     esi, 0B8h
0x180007199  jz      loc_180007312
0x18000719f  mov     eax, dword ptr cs:qword_180012DA0
0x1800071a5  mov     cs:dword_180012D30, eax
0x1800071ab  movups  xmm0, cs:?ProcessDef@LagCounterManager@@2U_USER_INPUT_DELAY_DEFINITION@@A; _USER_INPUT_DELAY_DEFINITION LagCounterManager::ProcessDef
0x1800071b2  movups  xmmword ptr [rdi], xmm0
0x1800071b5  movups  xmm1, cs:xmmword_180012D18
0x1800071bc  movups  xmmword ptr [rdi+10h], xmm1
0x1800071c0  movups  xmm0, xmmword ptr cs:unk_180012D28
0x1800071c7  movups  xmmword ptr [rdi+20h], xmm0
0x1800071cb  movups  xmm1, cs:xmmword_180012D38
0x1800071d2  movups  xmmword ptr [rdi+30h], xmm1
0x1800071d6  movups  xmm0, cs:xmmword_180012D48
0x1800071dd  movups  xmmword ptr [rdi+40h], xmm0
0x1800071e1  movups  xmm1, cs:xmmword_180012D58
0x1800071e8  movups  xmmword ptr [rdi+50h], xmm1
0x1800071ec  movups  xmm0, cs:xmmword_180012D68
0x1800071f3  movups  xmmword ptr [rdi+60h], xmm0
0x1800071f7  movups  xmm1, cs:xmmword_180012D78
0x1800071fe  movups  xmmword ptr [rdi+70h], xmm1
0x180007202  movups  xmm0, cs:xmmword_180012D88
0x180007209  movups  xmmword ptr [rdi+80h], xmm0
0x180007210  add     rdi, 90h
0x180007217  mov     rbx, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x18000721e  mov     rbx, [rbx]
0x180007221  cmp     rbx, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180007228  jz      loc_180007305
0x18000722e  mov     rcx, [rbx+28h]; this
0x180007232  call    ?GetPerfInstance@CounterHelper@@QEAAPEAU_USER_INPUT_DELAY_INSTANCE@@XZ; CounterHelper::GetPerfInstance(void)
0x180007237  movups  xmm0, xmmword ptr [rax]
0x18000723a  movups  xmmword ptr [rdi], xmm0
0x18000723d  movups  xmm1, xmmword ptr [rax+10h]
0x180007241  movups  xmmword ptr [rdi+10h], xmm1
0x180007245  movups  xmm0, xmmword ptr [rax+20h]
0x180007249  movups  xmmword ptr [rdi+20h], xmm0
0x18000724d  movups  xmm1, xmmword ptr [rax+30h]
0x180007251  movups  xmmword ptr [rdi+30h], xmm1
0x180007255  movups  xmm0, xmmword ptr [rax+40h]
0x180007259  movups  xmmword ptr [rdi+40h], xmm0
0x18000725d  movups  xmm1, xmmword ptr [rax+50h]
0x180007261  movups  xmmword ptr [rdi+50h], xmm1
0x180007265  movups  xmm0, xmmword ptr [rax+60h]
0x180007269  movups  xmmword ptr [rdi+60h], xmm0
0x18000726d  movups  xmm1, xmmword ptr [rax+70h]
0x180007271  movups  xmmword ptr [rdi+70h], xmm1
0x180007275  movups  xmm0, xmmword ptr [rax+80h]
0x18000727c  movups  xmmword ptr [rdi+80h], xmm0
0x180007283  movups  xmm1, xmmword ptr [rax+90h]
0x18000728a  movups  xmmword ptr [rdi+90h], xmm1
0x180007291  movups  xmm0, xmmword ptr [rax+0A0h]
0x180007298  movups  xmmword ptr [rdi+0A0h], xmm0
0x18000729f  mov     rax, [rax+0B0h]
0x1800072a6  mov     [rdi+0B0h], rax
0x1800072ad  add     rdi, rsi
0x1800072b0  xor     r8d, r8d
0x1800072b3  cmp     [rbx+19h], r8b
0x1800072b7  jnz     loc_180007221
0x1800072bd  mov     rax, [rbx+10h]
0x1800072c1  cmp     [rax+19h], r8b
0x1800072c5  jnz     short loc_1800072E4
0x1800072c7  mov     rcx, [rax]
0x1800072ca  cmp     [rcx+19h], r8b
0x1800072ce  jnz     short loc_1800072FD
0x1800072d0  mov     rbx, rcx
0x1800072d3  mov     rax, [rcx]
0x1800072d6  mov     rcx, rax
0x1800072d9  cmp     [rax+19h], r8b
0x1800072dd  jz      short loc_1800072D0
0x1800072df  jmp     loc_180007221
0x1800072e4  mov     rax, [rbx+8]
0x1800072e8  jmp     short loc_1800072F7
0x1800072ea  cmp     rbx, [rax+10h]
0x1800072ee  jnz     short loc_1800072FD
0x1800072f0  mov     rbx, rax
0x1800072f3  mov     rax, [rax+8]
0x1800072f7  cmp     [rax+19h], r8b
0x1800072fb  jz      short loc_1800072EA
0x1800072fd  mov     rbx, rax
0x180007300  jmp     loc_180007221
0x180007305  inc     dword ptr [r14]
0x180007308  mov     r15, [rsp+0C8h+var_A0]
0x18000730d  mov     [r15], rdi
0x180007310  jmp     short loc_180007317
0x180007312  mov     r15, [rsp+0C8h+var_A0]
0x180007317  test    r13d, r13d
0x18000731a  jz      loc_180007622
0x180007320  mov     eax, dword ptr cs:qword_180012DB0
0x180007326  mov     cs:dword_180012CA0, eax
0x18000732c  test    r12d, r12d
0x18000732f  jz      short loc_18000733A
0x180007331  add     eax, 2
0x180007334  mov     cs:dword_180012CA0, eax
0x18000733a  movups  xmm0, cs:?SessionDef@LagCounterManager@@2U_USER_INPUT_DELAY_DEFINITION@@A; _USER_INPUT_DELAY_DEFINITION LagCounterManager::SessionDef
0x180007341  movups  xmmword ptr [rdi], xmm0
0x180007344  movups  xmm1, cs:xmmword_180012C88
0x18000734b  movups  xmmword ptr [rdi+10h], xmm1
0x18000734f  movups  xmm0, xmmword ptr cs:unk_180012C98
0x180007356  movups  xmmword ptr [rdi+20h], xmm0
0x18000735a  movups  xmm1, cs:xmmword_180012CA8
0x180007361  movups  xmmword ptr [rdi+30h], xmm1
0x180007365  movups  xmm0, cs:xmmword_180012CB8
0x18000736c  movups  xmmword ptr [rdi+40h], xmm0
0x180007370  movups  xmm1, cs:xmmword_180012CC8
0x180007377  movups  xmmword ptr [rdi+50h], xmm1
0x18000737b  movups  xmm0, cs:xmmword_180012CD8
0x180007382  movups  xmmword ptr [rdi+60h], xmm0
0x180007386  movups  xmm1, cs:xmmword_180012CE8
0x18000738d  movups  xmmword ptr [rdi+70h], xmm1
0x180007391  movups  xmm0, cs:xmmword_180012CF8
0x180007398  movups  xmmword ptr [rdi+80h], xmm0
0x18000739f  add     rdi, 90h
0x1800073a6  mov     rbx, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x1800073ad  mov     rbx, [rbx]
0x1800073b0  cmp     rbx, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x1800073b7  jz      loc_180007494
0x1800073bd  mov     rcx, [rbx+28h]; this
0x1800073c1  call    ?GetPerfInstance@CounterHelper@@QEAAPEAU_USER_INPUT_DELAY_INSTANCE@@XZ; CounterHelper::GetPerfInstance(void)
0x1800073c6  movups  xmm0, xmmword ptr [rax]
0x1800073c9  movups  xmmword ptr [rdi], xmm0
0x1800073cc  movups  xmm1, xmmword ptr [rax+10h]
0x1800073d0  movups  xmmword ptr [rdi+10h], xmm1
0x1800073d4  movups  xmm0, xmmword ptr [rax+20h]
0x1800073d8  movups  xmmword ptr [rdi+20h], xmm0
0x1800073dc  movups  xmm1, xmmword ptr [rax+30h]
0x1800073e0  movups  xmmword ptr [rdi+30h], xmm1
0x1800073e4  movups  xmm0, xmmword ptr [rax+40h]
0x1800073e8  movups  xmmword ptr [rdi+40h], xmm0
0x1800073ec  movups  xmm1, xmmword ptr [rax+50h]
0x1800073f0  movups  xmmword ptr [rdi+50h], xmm1
0x1800073f4  movups  xmm0, xmmword ptr [rax+60h]
0x1800073f8  movups  xmmword ptr [rdi+60h], xmm0
0x1800073fc  movups  xmm1, xmmword ptr [rax+70h]
0x180007400  movups  xmmword ptr [rdi+70h], xmm1
0x180007404  movups  xmm0, xmmword ptr [rax+80h]
0x18000740b  movups  xmmword ptr [rdi+80h], xmm0
0x180007412  movups  xmm1, xmmword ptr [rax+90h]
0x180007419  movups  xmmword ptr [rdi+90h], xmm1
0x180007420  movups  xmm0, xmmword ptr [rax+0A0h]
0x180007427  movups  xmmword ptr [rdi+0A0h], xmm0
0x18000742e  mov     rax, [rax+0B0h]
0x180007435  mov     [rdi+0B0h], rax
0x18000743c  add     rdi, rsi
0x18000743f  xor     r8d, r8d
0x180007442  cmp     [rbx+19h], r8b
0x180007446  jnz     loc_1800073B0
0x18000744c  mov     rax, [rbx+10h]
0x180007450  cmp     [rax+19h], r8b
0x180007454  jnz     short loc_180007473
0x180007456  mov     rcx, [rax]
0x180007459  cmp     [rcx+19h], r8b
0x18000745d  jnz     short loc_18000748C
0x18000745f  mov     rbx, rcx
0x180007462  mov     rax, [rcx]
0x180007465  mov     rcx, rax
0x180007468  cmp     [rax+19h], r8b
0x18000746c  jz      short loc_18000745F
0x18000746e  jmp     loc_1800073B0
0x180007473  mov     rax, [rbx+8]
0x180007477  jmp     short loc_180007486
0x180007479  cmp     rbx, [rax+10h]
0x18000747d  jnz     short loc_18000748C
0x18000747f  mov     rbx, rax
0x180007482  mov     rax, [rax+8]
0x180007486  cmp     [rax+19h], r8b
0x18000748a  jz      short loc_180007479
0x18000748c  mov     rbx, rax
0x18000748f  jmp     loc_1800073B0
0x180007494  test    r12d, r12d
0x180007497  jz      loc_18000761C
0x18000749d  mov     rcx, cs:?MachineCounter@CounterHelper@@2PEAV1@EA; this
  ... truncated ...
```
