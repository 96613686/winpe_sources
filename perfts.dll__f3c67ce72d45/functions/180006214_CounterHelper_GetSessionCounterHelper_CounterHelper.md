# CounterHelper::GetSessionCounterHelper(CounterHelper *)

- ea: `0x180006214`
- end: `0x1800062e1`
- name: `?GetSessionCounterHelper@CounterHelper@@QEAAPEAV1@PEAV1@@Z`
- size: `205`
- prototype: `struct CounterHelper *__fastcall(CounterHelper *__hidden this, struct CounterHelper *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004cb8`

## callees

- `0x180004be0`
- `0x180006214`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180006293`
- `KERNEL32!CreateMutexW` at `0x180006293`
- `KERNEL32!WaitForSingleObject` at `0x1800062a6`
- `KERNEL32!WaitForSingleObject` at `0x1800062a6`
- `KERNEL32!ReleaseMutex` at `0x1800062c9`
- `KERNEL32!ReleaseMutex` at `0x1800062c9`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180006224`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180006224`

## pseudocode

```c
struct CounterHelper *__fastcall CounterHelper::GetSessionCounterHelper(CounterHelper *this, struct CounterHelper *a2)
{
  int v4; // eax
  unsigned int v5; // r9d
  __int64 v6; // rcx
  __int64 v7; // rax
  HANDLE MutexW; // rax
  __int64 v9; // rbx
  _QWORD *v10; // rax
  HANDLE v11; // rcx

  v4 = WTSGetServiceSessionId();
  v5 = *((_DWORD *)this + 105);
  if ( v5 == v4 && !CounterHelper::LagCounterShowUnknown )
    return 0;
  v6 = CounterHelper::SessionToCounter;
  v7 = *(_QWORD *)(CounterHelper::SessionToCounter + 8);
  while ( !*(_BYTE *)(v7 + 25) )
  {
    if ( *(_DWORD *)(v7 + 32) >= v5 )
    {
      v6 = v7;
      v7 = *(_QWORD *)v7;
    }
    else
    {
      v7 = *(_QWORD *)(v7 + 16);
    }
  }
  if ( v6 == CounterHelper::SessionToCounter || v5 < *(_DWORD *)(v6 + 32) )
    v6 = CounterHelper::SessionToCounter;
  if ( v6 == CounterHelper::SessionToCounter )
    return 0;
  MutexW = CounterHelper::LagCounterMajorEvent;
  v9 = *(_QWORD *)(v6 + 40);
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  v10 = (_QWORD *)std::map<unsigned long,CounterHelper *>::operator[](
                    &CounterHelper::ProcessesInSession,
                    (char *)a2 + 424);
  v11 = CounterHelper::LagCounterMajorEvent;
  *v10 = a2;
  ReleaseMutex(v11);
  return (struct CounterHelper *)v9;
}

```

## disassembly

```asm
0x180006214  mov     [rsp+arg_0], rbx
0x180006219  push    rdi
0x18000621a  sub     rsp, 20h
0x18000621e  mov     rdi, rdx
0x180006221  mov     rbx, rcx
0x180006224  call    cs:__imp_WTSGetServiceSessionId
0x18000622a  mov     r9d, [rbx+1A4h]
0x180006231  xor     edx, edx; bInitialOwner
0x180006233  cmp     r9d, eax
0x180006236  jnz     short loc_180006244
0x180006238  cmp     cs:?LagCounterShowUnknown@CounterHelper@@2HA, edx; int CounterHelper::LagCounterShowUnknown
0x18000623e  jz      loc_1800062D4
0x180006244  mov     r8, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x18000624b  mov     rcx, r8
0x18000624e  mov     rax, [r8+8]
0x180006252  jmp     short loc_180006266
0x180006254  cmp     [rax+20h], r9d
0x180006258  jnb     short loc_180006260
0x18000625a  mov     rax, [rax+10h]
0x18000625e  jmp     short loc_180006266
0x180006260  mov     rcx, rax
0x180006263  mov     rax, [rax]
0x180006266  cmp     [rax+19h], dl
0x180006269  jz      short loc_180006254
0x18000626b  cmp     rcx, r8
0x18000626e  jz      short loc_180006276
0x180006270  cmp     r9d, [rcx+20h]
0x180006274  jnb     short loc_180006279
0x180006276  mov     rcx, r8
0x180006279  cmp     rcx, r8
0x18000627c  jz      short loc_1800062D4
0x18000627e  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180006285  mov     rbx, [rcx+28h]
0x180006289  test    rax, rax
0x18000628c  jnz     short loc_1800062A0
0x18000628e  xor     r8d, r8d; lpName
0x180006291  xor     ecx, ecx; lpMutexAttributes
0x180006293  call    cs:__imp_CreateMutexW
0x180006299  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x1800062a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800062a3  mov     rcx, rax; hHandle
0x1800062a6  call    cs:__imp_WaitForSingleObject
0x1800062ac  lea     rdx, [rdi+1A8h]
0x1800062b3  lea     rcx, ?ProcessesInSession@CounterHelper@@0V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesInSession
0x1800062ba  call    ??A?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@QEAAAEAPEAVCounterHelper@@AEBK@Z; std::map<ulong,CounterHelper *>::operator[](ulong const &)
0x1800062bf  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x1800062c6  mov     [rax], rdi
0x1800062c9  call    cs:__imp_ReleaseMutex
0x1800062cf  mov     rax, rbx
0x1800062d2  jmp     short loc_1800062D6
0x1800062d4  xor     eax, eax
0x1800062d6  mov     rbx, [rsp+28h+arg_0]
0x1800062db  add     rsp, 20h
0x1800062df  pop     rdi
0x1800062e0  retn
```
