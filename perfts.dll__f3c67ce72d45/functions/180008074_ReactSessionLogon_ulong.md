# ReactSessionLogon(ulong)

- ea: `0x180008074`
- end: `0x180008183`
- name: `?ReactSessionLogon@@YAKK@Z`
- size: `271`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007b10`

## callees

- `0x180001da8`
- `0x1800047c4`
- `0x1800047fc`
- `0x180004be0`
- `0x180008074`
- `0x180009930`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x1800080e5`
- `KERNEL32!CreateMutexW` at `0x1800080e5`
- `KERNEL32!WaitForSingleObject` at `0x1800080f8`
- `KERNEL32!WaitForSingleObject` at `0x1800080f8`
- `KERNEL32!ReleaseMutex` at `0x180008162`
- `KERNEL32!ReleaseMutex` at `0x180008162`

## pseudocode

```c
__int64 __fastcall ReactSessionLogon(unsigned int a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  HANDLE MutexW; // rax
  void *v5; // rax
  __int64 v6; // rbx
  __int64 *v7; // rax
  HANDLE v8; // rcx
  unsigned int v10; // [rsp+30h] [rbp-238h] BYREF
  void *v11; // [rsp+38h] [rbp-230h]
  _BYTE v12[528]; // [rsp+40h] [rbp-228h] BYREF

  v10 = a1;
  v2 = CounterHelper::SessionToCounter;
  v3 = *(_QWORD *)(CounterHelper::SessionToCounter + 8);
  while ( !*(_BYTE *)(v3 + 25) )
  {
    if ( *(_DWORD *)(v3 + 32) >= a1 )
    {
      v2 = v3;
      v3 = *(_QWORD *)v3;
    }
    else
    {
      v3 = *(_QWORD *)(v3 + 16);
    }
  }
  if ( v2 == CounterHelper::SessionToCounter || a1 < *(_DWORD *)(v2 + 32) )
    v2 = CounterHelper::SessionToCounter;
  if ( v2 == CounterHelper::SessionToCounter )
  {
    MutexW = CounterHelper::LagCounterMajorEvent;
    if ( !CounterHelper::LagCounterMajorEvent )
    {
      MutexW = CreateMutexW(0, 0, 0);
      CounterHelper::LagCounterMajorEvent = MutexW;
    }
    WaitForSingleObject(MutexW, 0xFFFFFFFF);
    swprintf_s<260>(v12, L"%u", a1);
    v5 = operator new(0x1B0u);
    v11 = v5;
    if ( v5 )
      v6 = CounterHelper::CounterHelper(v5, v12, 1);
    else
      v6 = 0;
    v7 = (__int64 *)std::map<unsigned long,CounterHelper *>::operator[](&CounterHelper::SessionToCounter, &v10);
    v8 = CounterHelper::LagCounterMajorEvent;
    *v7 = v6;
    ReleaseMutex(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180008074  push    rbx
0x180008076  sub     rsp, 260h
0x18000807d  mov     rax, cs:__security_cookie
0x180008084  xor     rax, rsp
0x180008087  mov     [rsp+268h+var_18], rax
0x18000808f  mov     rdx, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180008096  mov     ebx, ecx
0x180008098  mov     [rsp+268h+var_238], ecx
0x18000809c  mov     rax, rdx
0x18000809f  mov     rcx, [rdx+8]
0x1800080a3  jmp     short loc_1800080B6
0x1800080a5  cmp     [rcx+20h], ebx
0x1800080a8  jnb     short loc_1800080B0
0x1800080aa  mov     rcx, [rcx+10h]
0x1800080ae  jmp     short loc_1800080B6
0x1800080b0  mov     rax, rcx
0x1800080b3  mov     rcx, [rcx]
0x1800080b6  cmp     byte ptr [rcx+19h], 0
0x1800080ba  jz      short loc_1800080A5
0x1800080bc  cmp     rax, rdx
0x1800080bf  jz      short loc_1800080C6
0x1800080c1  cmp     ebx, [rax+20h]
0x1800080c4  jnb     short loc_1800080C9
0x1800080c6  mov     rax, rdx
0x1800080c9  cmp     rax, rdx
0x1800080cc  jnz     loc_180008168
0x1800080d2  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x1800080d9  test    rax, rax
0x1800080dc  jnz     short loc_1800080F2
0x1800080de  xor     r8d, r8d; lpName
0x1800080e1  xor     edx, edx; bInitialOwner
0x1800080e3  xor     ecx, ecx; lpMutexAttributes
0x1800080e5  call    cs:__imp_CreateMutexW
0x1800080eb  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x1800080f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800080f5  mov     rcx, rax; hHandle
0x1800080f8  call    cs:__imp_WaitForSingleObject
0x1800080fe  mov     r8d, ebx
0x180008101  lea     rdx, aU; "%u"
0x180008108  lea     rcx, [rsp+268h+var_228]
0x18000810d  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x180008112  mov     ecx, 1B0h; Size
0x180008117  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000811c  mov     [rsp+268h+var_230], rax
0x180008121  test    rax, rax
0x180008124  jz      short loc_180008145
0x180008126  mov     r9d, ebx
0x180008129  mov     [rsp+268h+var_248], ebx
0x18000812d  mov     r8d, 1
0x180008133  lea     rdx, [rsp+268h+var_228]
0x180008138  mov     rcx, rax
0x18000813b  call    ??0CounterHelper@@QEAA@PEAGW4COUNTER_HELPER_TYPE@@KK@Z; CounterHelper::CounterHelper(ushort *,COUNTER_HELPER_TYPE,ulong,ulong)
0x180008140  mov     rbx, rax
0x180008143  jmp     short loc_180008147
0x180008145  xor     ebx, ebx
0x180008147  lea     rdx, [rsp+268h+var_238]
0x18000814c  lea     rcx, ?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180008153  call    ??A?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@QEAAAEAPEAVCounterHelper@@AEBK@Z; std::map<ulong,CounterHelper *>::operator[](ulong const &)
0x180008158  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x18000815f  mov     [rax], rbx
0x180008162  call    cs:__imp_ReleaseMutex
0x180008168  xor     eax, eax
0x18000816a  mov     rcx, [rsp+268h+var_18]
0x180008172  xor     rcx, rsp; StackCookie
0x180008175  call    __security_check_cookie
0x18000817a  add     rsp, 260h
0x180008181  pop     rbx
0x180008182  retn
```
