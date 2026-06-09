# ReactProcessExit(ulong)

- ea: `0x180007ecc`
- end: `0x180007f81`
- name: `?ReactProcessExit@@YAKK@Z`
- size: `181`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007b10`

## callees

- `0x180005be0`
- `0x180007ecc`
- `0x1800095e8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007f66`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f66`
- `KERNEL32!CreateMutexW` at `0x180007eea`
- `KERNEL32!CreateMutexW` at `0x180007eea`
- `KERNEL32!WaitForSingleObject` at `0x180007efd`
- `KERNEL32!WaitForSingleObject` at `0x180007efd`
- `KERNEL32!ReleaseMutex` at `0x180007f73`
- `KERNEL32!ReleaseMutex` at `0x180007f73`

## pseudocode

```c
__int64 __fastcall ReactProcessExit(unsigned int a1)
{
  HANDLE MutexW; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  CounterHelper *v5; // rbx
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = a1;
  MutexW = CounterHelper::LagCounterMajorEvent;
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  v3 = CounterHelper::ProcessesToCounter;
  v4 = *(_QWORD *)(CounterHelper::ProcessesToCounter + 8);
  while ( !*(_BYTE *)(v4 + 25) )
  {
    if ( *(_DWORD *)(v4 + 32) >= a1 )
    {
      v3 = v4;
      v4 = *(_QWORD *)v4;
    }
    else
    {
      v4 = *(_QWORD *)(v4 + 16);
    }
  }
  if ( v3 == CounterHelper::ProcessesToCounter || a1 < *(_DWORD *)(v3 + 32) )
    v3 = CounterHelper::ProcessesToCounter;
  if ( v3 != CounterHelper::ProcessesToCounter )
  {
    v5 = *(CounterHelper **)(v3 + 40);
    CounterHelper::DeleteCounter(v5, 1);
    std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::erase(
      &CounterHelper::ProcessesToCounter,
      &v7);
    if ( v5 )
      operator delete(v5);
  }
  ReleaseMutex(CounterHelper::LagCounterMajorEvent);
  return 0;
}

```

## disassembly

```asm
0x180007ecc  mov     [rsp+arg_0], ecx
0x180007ed0  push    rbx
0x180007ed1  sub     rsp, 20h
0x180007ed5  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180007edc  mov     ebx, ecx
0x180007ede  test    rax, rax
0x180007ee1  jnz     short loc_180007EF7
0x180007ee3  xor     r8d, r8d; lpName
0x180007ee6  xor     edx, edx; bInitialOwner
0x180007ee8  xor     ecx, ecx; lpMutexAttributes
0x180007eea  call    cs:__imp_CreateMutexW
0x180007ef0  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x180007ef7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007efa  mov     rcx, rax; hHandle
0x180007efd  call    cs:__imp_WaitForSingleObject
0x180007f03  mov     rdx, cs:?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180007f0a  mov     rcx, rdx
0x180007f0d  mov     rax, [rdx+8]
0x180007f11  jmp     short loc_180007F24
0x180007f13  cmp     [rax+20h], ebx
0x180007f16  jnb     short loc_180007F1E
0x180007f18  mov     rax, [rax+10h]
0x180007f1c  jmp     short loc_180007F24
0x180007f1e  mov     rcx, rax
0x180007f21  mov     rax, [rax]
0x180007f24  cmp     byte ptr [rax+19h], 0
0x180007f28  jz      short loc_180007F13
0x180007f2a  cmp     rcx, rdx
0x180007f2d  jz      short loc_180007F34
0x180007f2f  cmp     ebx, [rcx+20h]
0x180007f32  jnb     short loc_180007F37
0x180007f34  mov     rcx, rdx
0x180007f37  cmp     rcx, rdx
0x180007f3a  jz      short loc_180007F6C
0x180007f3c  mov     rbx, [rcx+28h]
0x180007f40  mov     edx, 1; int
0x180007f45  mov     rcx, rbx; this
0x180007f48  call    ?DeleteCounter@CounterHelper@@QEAAXH@Z; CounterHelper::DeleteCounter(int)
0x180007f4d  lea     rdx, [rsp+28h+arg_0]
0x180007f52  lea     rcx, ?ProcessesToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesToCounter
0x180007f59  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::erase(ulong const &)
0x180007f5e  test    rbx, rbx
0x180007f61  jz      short loc_180007F6C
0x180007f63  mov     rcx, rbx
0x180007f66  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007f6c  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x180007f73  call    cs:__imp_ReleaseMutex
0x180007f79  xor     eax, eax
0x180007f7b  add     rsp, 20h
0x180007f7f  pop     rbx
0x180007f80  retn
```
