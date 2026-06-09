# LagCounterManager::PerfCloseDataCallback(void)

- ea: `0x180006d0c`
- end: `0x180006f90`
- name: `?PerfCloseDataCallback@LagCounterManager@@SAKXZ`
- size: `644`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003450`
- `0x180003bd0`
- `0x180007668`

## callees

- `0x18000576c`
- `0x180006d0c`
- `0x180008f38`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006d8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006dfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006e7b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006edb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006f1d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006d8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006dfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006e7b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006edb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006f1d`
- `KERNEL32!CreateMutexW` at `0x180006d5e`
- `KERNEL32!CreateMutexW` at `0x180006d5e`
- `KERNEL32!WaitForSingleObject` at `0x180006d31`
- `KERNEL32!WaitForSingleObject` at `0x180006d71`
- `KERNEL32!WaitForSingleObject` at `0x180006d31`
- `KERNEL32!WaitForSingleObject` at `0x180006d71`
- `KERNEL32!ReleaseMutex` at `0x180006f31`
- `KERNEL32!ReleaseMutex` at `0x180006f31`
- `KERNEL32!FreeLibrary` at `0x180006f66`
- `KERNEL32!FreeLibrary` at `0x180006f66`
- `KERNEL32!CloseHandle` at `0x180006d3e`
- `KERNEL32!CloseHandle` at `0x180006f3e`
- `KERNEL32!CloseHandle` at `0x180006d3e`
- `KERNEL32!CloseHandle` at `0x180006f3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 LagCounterManager::PerfCloseDataCallback(void)
{
  HANDLE MutexW; // rax
  __int64 v1; // rdx
  _QWORD *v2; // rbx
  void *v3; // rcx
  __int64 i; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  void *v9; // rcx
  __int64 j; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rbx
  _BYTE *v15; // rdi
  __int64 v16; // rax
  _BYTE *v17; // rdi
  _BYTE *v18; // rbx
  unsigned int v19; // r8d
  const char *v20; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  LagCounterManager::Cleanup();
  if ( LagCounterManager::hEtwThread )
  {
    WaitForSingleObject(LagCounterManager::hEtwThread, 0xFFFFFFFF);
    CloseHandle(LagCounterManager::hEtwThread);
    LagCounterManager::hEtwThread = 0;
  }
  MutexW = CounterHelper::LagCounterMajorEvent;
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  v1 = CounterHelper::ProcessesToCounter;
  v2 = *(_QWORD **)CounterHelper::ProcessesToCounter;
  while ( v2 != (_QWORD *)v1 )
  {
    v3 = (void *)v2[5];
    if ( v3 )
    {
      operator delete(v3);
      v1 = CounterHelper::ProcessesToCounter;
    }
    if ( !*((_BYTE *)v2 + 25) )
    {
      i = v2[2];
      if ( *(_BYTE *)(i + 25) )
      {
        for ( i = v2[1]; !*(_BYTE *)(i + 25) && v2 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v2 = (_QWORD *)i;
LABEL_18:
        v2 = (_QWORD *)i;
      }
      else
      {
        v5 = *(_QWORD **)i;
        if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
          goto LABEL_18;
        do
        {
          v2 = v5;
          v6 = *v5;
          v5 = (_QWORD *)v6;
        }
        while ( !*(_BYTE *)(v6 + 25) );
      }
    }
  }
  v7 = CounterHelper::SessionToCounter;
  v8 = *(_QWORD **)CounterHelper::SessionToCounter;
  while ( v8 != (_QWORD *)v7 )
  {
    v9 = (void *)v8[5];
    if ( v9 )
    {
      operator delete(v9);
      v7 = CounterHelper::SessionToCounter;
    }
    if ( !*((_BYTE *)v8 + 25) )
    {
      j = v8[2];
      if ( *(_BYTE *)(j + 25) )
      {
        for ( j = v8[1]; !*(_BYTE *)(j + 25) && v8 == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
          v8 = (_QWORD *)j;
LABEL_32:
        v8 = (_QWORD *)j;
      }
      else
      {
        v11 = *(_QWORD **)j;
        if ( *(_BYTE *)(*(_QWORD *)j + 25LL) )
          goto LABEL_32;
        do
        {
          v8 = v11;
          v12 = *v11;
          v11 = (_QWORD *)v12;
        }
        while ( !*(_BYTE *)(v12 + 25) );
      }
    }
  }
  try
  {
    v13 = CounterHelper::ProcessesToCounter;
    v14 = *(_BYTE **)(CounterHelper::ProcessesToCounter + 8);
    v15 = v14;
    if ( !v14[25] )
    {
      do
      {
        std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::_Erase(
          &CounterHelper::ProcessesToCounter,
          *((_QWORD *)v15 + 2));
        v15 = *(_BYTE **)v15;
        operator delete(v14);
        v14 = v15;
      }
      while ( !v15[25] );
      v13 = CounterHelper::ProcessesToCounter;
    }
    *(_QWORD *)(v13 + 8) = v13;
    *(_QWORD *)CounterHelper::ProcessesToCounter = CounterHelper::ProcessesToCounter;
    *(_QWORD *)(CounterHelper::ProcessesToCounter + 16) = CounterHelper::ProcessesToCounter;
    qword_180012DA0 = 0;
    v16 = CounterHelper::SessionToCounter;
    v17 = *(_BYTE **)(CounterHelper::SessionToCounter + 8);
    v18 = v17;
    if ( !v17[25] )
    {
      do
      {
        std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::_Erase(
          &CounterHelper::SessionToCounter,
          *((_QWORD *)v18 + 2));
        v18 = *(_BYTE **)v18;
        operator delete(v17);
        v17 = v18;
      }
      while ( !v18[25] );
      v16 = CounterHelper::SessionToCounter;
    }
    *(_QWORD *)(v16 + 8) = v16;
    *(_QWORD *)CounterHelper::SessionToCounter = CounterHelper::SessionToCounter;
    *(_QWORD *)(CounterHelper::SessionToCounter + 16) = CounterHelper::SessionToCounter;
    qword_180012DB0 = 0;
    if ( CounterHelper::MachineCounter )
    {
      operator delete(CounterHelper::MachineCounter);
      CounterHelper::MachineCounter = 0;
    }
    ReleaseMutex(CounterHelper::LagCounterMajorEvent);
    CloseHandle(CounterHelper::LagCounterMajorEvent);
    CounterHelper::LagCounterMajorEvent = 0;
    if ( LagCounterManager::dwOpenPerfCount )
      _InterlockedDecrement((volatile signed __int32 *)&LagCounterManager::dwOpenPerfCount);
    if ( LagCounterManager::hPdhLib )
    {
      FreeLibrary(LagCounterManager::hPdhLib);
      LagCounterManager::hPdhLib = 0;
    }
    LagCounterManager::bPendingShutdown = 0;
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x4C7, v19, v20);
    ReleaseMutex(CounterHelper::LagCounterMajorEvent);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006d0c  mov     [rsp+arg_0], rbx
0x180006d11  mov     [rsp+arg_8], rsi
0x180006d16  push    rdi
0x180006d17  sub     rsp, 20h
0x180006d1b  call    ?Cleanup@LagCounterManager@@SAXXZ; LagCounterManager::Cleanup(void)
0x180006d20  mov     rcx, cs:?hEtwThread@LagCounterManager@@2PEAXEA; hHandle
0x180006d27  xor     esi, esi
0x180006d29  test    rcx, rcx
0x180006d2c  jz      short loc_180006D4B
0x180006d2e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006d31  call    cs:__imp_WaitForSingleObject
0x180006d37  mov     rcx, cs:?hEtwThread@LagCounterManager@@2PEAXEA; hObject
0x180006d3e  call    cs:__imp_CloseHandle
0x180006d44  mov     cs:?hEtwThread@LagCounterManager@@2PEAXEA, rsi; void * LagCounterManager::hEtwThread
0x180006d4b  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180006d52  test    rax, rax
0x180006d55  jnz     short loc_180006D6B
0x180006d57  xor     r8d, r8d; lpName
0x180006d5a  xor     edx, edx; bInitialOwner
0x180006d5c  xor     ecx, ecx; lpMutexAttributes
0x180006d5e  call    cs:__imp_CreateMutexW
0x180006d64  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x180006d6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006d6e  mov     rcx, rax; hHandle
0x180006d71  call    cs:__imp_WaitForSingleObject
0x180006d77  mov     rdx, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180006d7e  mov     rbx, [rdx]
0x180006d81  cmp     rbx, rdx
0x180006d84  jz      short loc_180006DE4
0x180006d86  mov     rcx, [rbx+28h]
0x180006d8a  test    rcx, rcx
0x180006d8d  jz      short loc_180006D9C
0x180006d8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006d95  mov     rdx, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180006d9c  cmp     [rbx+19h], sil
0x180006da0  jnz     short loc_180006D81
0x180006da2  mov     rax, [rbx+10h]
0x180006da6  cmp     [rax+19h], sil
0x180006daa  jnz     short loc_180006DC6
0x180006dac  mov     rcx, [rax]
0x180006daf  cmp     [rcx+19h], sil
0x180006db3  jnz     short loc_180006DDF
0x180006db5  mov     rbx, rcx
0x180006db8  mov     rax, [rcx]
0x180006dbb  mov     rcx, rax
0x180006dbe  cmp     [rax+19h], sil
0x180006dc2  jz      short loc_180006DB5
0x180006dc4  jmp     short loc_180006D81
0x180006dc6  mov     rax, [rbx+8]
0x180006dca  jmp     short loc_180006DD9
0x180006dcc  cmp     rbx, [rax+10h]
0x180006dd0  jnz     short loc_180006DDF
0x180006dd2  mov     rbx, rax
0x180006dd5  mov     rax, [rax+8]
0x180006dd9  cmp     [rax+19h], sil
0x180006ddd  jz      short loc_180006DCC
0x180006ddf  mov     rbx, rax
0x180006de2  jmp     short loc_180006D81
0x180006de4  mov     rdx, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180006deb  mov     rbx, [rdx]
0x180006dee  cmp     rbx, rdx
0x180006df1  jz      short loc_180006E51
0x180006df3  mov     rcx, [rbx+28h]
0x180006df7  test    rcx, rcx
0x180006dfa  jz      short loc_180006E09
0x180006dfc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006e02  mov     rdx, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180006e09  cmp     [rbx+19h], sil
0x180006e0d  jnz     short loc_180006DEE
0x180006e0f  mov     rax, [rbx+10h]
0x180006e13  cmp     [rax+19h], sil
0x180006e17  jnz     short loc_180006E33
0x180006e19  mov     rcx, [rax]
0x180006e1c  cmp     [rcx+19h], sil
0x180006e20  jnz     short loc_180006E4C
0x180006e22  mov     rbx, rcx
0x180006e25  mov     rax, [rcx]
0x180006e28  mov     rcx, rax
0x180006e2b  cmp     [rax+19h], sil
0x180006e2f  jz      short loc_180006E22
0x180006e31  jmp     short loc_180006DEE
0x180006e33  mov     rax, [rbx+8]
0x180006e37  jmp     short loc_180006E46
0x180006e39  cmp     rbx, [rax+10h]
0x180006e3d  jnz     short loc_180006E4C
0x180006e3f  mov     rbx, rax
0x180006e42  mov     rax, [rax+8]
0x180006e46  cmp     [rax+19h], sil
0x180006e4a  jz      short loc_180006E39
0x180006e4c  mov     rbx, rax
0x180006e4f  jmp     short loc_180006DEE
0x180006e51  mov     rax, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180006e58  mov     rbx, [rax+8]
0x180006e5c  mov     rdi, rbx
0x180006e5f  cmp     [rbx+19h], sil
0x180006e63  jnz     short loc_180006E91
0x180006e65  mov     rdx, [rdi+10h]
0x180006e69  lea     rcx, ?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180006e70  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::_Erase(std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)
0x180006e75  mov     rdi, [rdi]
0x180006e78  mov     rcx, rbx
0x180006e7b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006e81  mov     rbx, rdi
0x180006e84  cmp     [rdi+19h], sil
0x180006e88  jz      short loc_180006E65
0x180006e8a  mov     rax, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180006e91  mov     [rax+8], rax
0x180006e95  mov     rax, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180006e9c  mov     [rax], rax
0x180006e9f  mov     rax, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180006ea6  mov     [rax+10h], rax
0x180006eaa  mov     cs:qword_180012DA0, rsi
0x180006eb1  mov     rax, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180006eb8  mov     rdi, [rax+8]
0x180006ebc  mov     rbx, rdi
0x180006ebf  cmp     [rdi+19h], sil
0x180006ec3  jnz     short loc_180006EF1
0x180006ec5  mov     rdx, [rbx+10h]
0x180006ec9  lea     rcx, ?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180006ed0  call    ?_Erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::_Erase(std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)
0x180006ed5  mov     rbx, [rbx]
0x180006ed8  mov     rcx, rdi
0x180006edb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006ee1  mov     rdi, rbx
0x180006ee4  cmp     [rbx+19h], sil
0x180006ee8  jz      short loc_180006EC5
0x180006eea  mov     rax, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180006ef1  mov     [rax+8], rax
0x180006ef5  mov     rax, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180006efc  mov     [rax], rax
0x180006eff  mov     rax, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180006f06  mov     [rax+10h], rax
0x180006f0a  mov     cs:qword_180012DB0, rsi
0x180006f11  mov     rcx, cs:?MachineCounter@CounterHelper@@2PEAV1@EA; CounterHelper * CounterHelper::MachineCounter
0x180006f18  test    rcx, rcx
0x180006f1b  jz      short loc_180006F2A
0x180006f1d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006f23  mov     cs:?MachineCounter@CounterHelper@@2PEAV1@EA, rsi; CounterHelper * CounterHelper::MachineCounter
0x180006f2a  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x180006f31  call    cs:__imp_ReleaseMutex
0x180006f37  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hObject
0x180006f3e  call    cs:__imp_CloseHandle
0x180006f44  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rsi; void * CounterHelper::LagCounterMajorEvent
0x180006f4b  cmp     cs:?dwOpenPerfCount@LagCounterManager@@2KA, esi; ulong LagCounterManager::dwOpenPerfCount
0x180006f51  jbe     short loc_180006F5A
0x180006f53  lock dec cs:?dwOpenPerfCount@LagCounterManager@@2KA; ulong LagCounterManager::dwOpenPerfCount
0x180006f5a  mov     rcx, cs:?hPdhLib@LagCounterManager@@2PEAUHINSTANCE__@@EA; hLibModule
0x180006f61  test    rcx, rcx
0x180006f64  jz      short loc_180006F73
0x180006f66  call    cs:__imp_FreeLibrary
0x180006f6c  mov     cs:?hPdhLib@LagCounterManager@@2PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * LagCounterManager::hPdhLib
0x180006f73  mov     cs:?bPendingShutdown@LagCounterManager@@2HA, esi; int LagCounterManager::bPendingShutdown
0x180006f79  xor     eax, eax
0x180006f7b  jmp     short loc_180006F7F
0x180006f7d  xor     eax, eax
0x180006f7f  mov     rbx, [rsp+28h+arg_0]
0x180006f84  mov     rsi, [rsp+28h+arg_8]
0x180006f89  add     rsp, 20h
0x180006f8d  pop     rdi
0x180006f8e  retn
```
