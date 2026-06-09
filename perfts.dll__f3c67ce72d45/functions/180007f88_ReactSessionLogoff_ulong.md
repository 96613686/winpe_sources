# ReactSessionLogoff(ulong)

- ea: `0x180007f88`
- end: `0x18000806c`
- name: `?ReactSessionLogoff@@YAKK@Z`
- size: `228`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007b10`

## callees

- `0x180001008`
- `0x180005be0`
- `0x180007f88`
- `0x1800095e8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008051`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008051`
- `KERNEL32!CreateMutexW` at `0x180007fa6`
- `KERNEL32!CreateMutexW` at `0x180007fa6`
- `KERNEL32!WaitForSingleObject` at `0x180007fb9`
- `KERNEL32!WaitForSingleObject` at `0x180007fb9`
- `KERNEL32!ReleaseMutex` at `0x18000805e`
- `KERNEL32!ReleaseMutex` at `0x18000805e`

## string_xrefs

- `0x180008003`: `Failed to delete session that was logged off`

## pseudocode

```c
__int64 __fastcall ReactSessionLogoff(unsigned int a1)
{
  HANDLE MutexW; // rax
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rcx
  __int64 v6; // rax
  CounterHelper *v7; // rbx
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF
  const char *v10; // [rsp+48h] [rbp+10h] BYREF

  v9 = a1;
  MutexW = CounterHelper::LagCounterMajorEvent;
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  v5 = CounterHelper::SessionToCounter;
  v6 = *(_QWORD *)(CounterHelper::SessionToCounter + 8);
  while ( !*(_BYTE *)(v6 + 25) )
  {
    if ( *(_DWORD *)(v6 + 32) >= a1 )
    {
      v5 = v6;
      v6 = *(_QWORD *)v6;
    }
    else
    {
      v6 = *(_QWORD *)(v6 + 16);
    }
  }
  if ( v5 == CounterHelper::SessionToCounter || a1 < *(_DWORD *)(v5 + 32) )
    v5 = CounterHelper::SessionToCounter;
  if ( v5 == CounterHelper::SessionToCounter )
  {
    if ( (unsigned int)dword_180012020 > 2 )
    {
      v10 = "Failed to delete session that was logged off";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v5,
        (unsigned int)&unk_18000EF61,
        v3,
        v4,
        (__int64)&v10);
    }
  }
  else
  {
    v7 = *(CounterHelper **)(v5 + 40);
    CounterHelper::DeleteCounter(v7, 1);
    std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::erase(
      &CounterHelper::SessionToCounter,
      &v9);
    if ( v7 )
      operator delete(v7);
  }
  ReleaseMutex(CounterHelper::LagCounterMajorEvent);
  return 0;
}

```

## disassembly

```asm
0x180007f88  mov     [rsp+arg_0], ecx
0x180007f8c  push    rbx
0x180007f8d  sub     rsp, 30h
0x180007f91  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180007f98  mov     ebx, ecx
0x180007f9a  test    rax, rax
0x180007f9d  jnz     short loc_180007FB3
0x180007f9f  xor     r8d, r8d; lpName
0x180007fa2  xor     edx, edx; bInitialOwner
0x180007fa4  xor     ecx, ecx; lpMutexAttributes
0x180007fa6  call    cs:__imp_CreateMutexW
0x180007fac  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x180007fb3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007fb6  mov     rcx, rax; hHandle
0x180007fb9  call    cs:__imp_WaitForSingleObject
0x180007fbf  mov     rdx, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180007fc6  mov     rcx, rdx
0x180007fc9  mov     rax, [rdx+8]
0x180007fcd  jmp     short loc_180007FE0
0x180007fcf  cmp     [rax+20h], ebx
0x180007fd2  jnb     short loc_180007FDA
0x180007fd4  mov     rax, [rax+10h]
0x180007fd8  jmp     short loc_180007FE0
0x180007fda  mov     rcx, rax
0x180007fdd  mov     rax, [rax]
0x180007fe0  cmp     byte ptr [rax+19h], 0
0x180007fe4  jz      short loc_180007FCF
0x180007fe6  cmp     rcx, rdx
0x180007fe9  jz      short loc_180007FF0
0x180007feb  cmp     ebx, [rcx+20h]
0x180007fee  jnb     short loc_180007FF3
0x180007ff0  mov     rcx, rdx
0x180007ff3  cmp     rcx, rdx
0x180007ff6  jnz     short loc_180008027
0x180007ff8  mov     eax, cs:dword_180012020
0x180007ffe  cmp     eax, 2
0x180008001  jbe     short loc_180008057
0x180008003  lea     rax, aFailedToDelete; "Failed to delete session that was logge"...
0x18000800a  mov     [rsp+38h+arg_8], rax
0x18000800f  lea     rdx, unk_18000EF61
0x180008016  lea     rax, [rsp+38h+arg_8]
0x18000801b  mov     [rsp+38h+var_18], rax
0x180008020  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180008025  jmp     short loc_180008057
0x180008027  mov     rbx, [rcx+28h]
0x18000802b  mov     edx, 1; int
0x180008030  mov     rcx, rbx; this
0x180008033  call    ?DeleteCounter@CounterHelper@@QEAAXH@Z; CounterHelper::DeleteCounter(int)
0x180008038  lea     rdx, [rsp+38h+arg_0]
0x18000803d  lea     rcx, ?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180008044  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::erase(ulong const &)
0x180008049  test    rbx, rbx
0x18000804c  jz      short loc_180008057
0x18000804e  mov     rcx, rbx
0x180008051  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008057  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x18000805e  call    cs:__imp_ReleaseMutex
0x180008064  xor     eax, eax
0x180008066  add     rsp, 30h
0x18000806a  pop     rbx
0x18000806b  retn
```
