# BaseHolder<void *,FunctionBase<void *,&StressLog::Enter(void *),&StressLog::Leave(void *),0>,0,&CompareDefault<void *>(void *,void *),0>::~BaseHolder<void *,FunctionBase<void *,&StressLog::Enter(void *),&StressLog::Leave(void *),0>,0,&CompareDefault<void *>(void *,void *),0>(void)

- ea: `0x14000faa4`
- end: `0x14000fad3`
- name: `??1?$BaseHolder@PEAXV?$FunctionBase@PEAX$1?Enter@StressLog@@SAXPEAX@Z$1?Leave@2@SAX0@Z$0A@@@$0A@$1??$CompareDefault@PEAX@@YAHPEAX0@Z$0A@@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001598e`
- `0x1400159be`

## callees

- `0x14000a218`
- `0x14000faa4`
- `0x140011bbc`
- `0x140011cf0`

## pseudocode

```c
void __fastcall BaseHolder<void *,FunctionBase<void *,&public: static void StressLog::Enter(void *),&public: static void StressLog::Leave(void *),0>,0,&int CompareDefault<void *>(void *,void *),0>::~BaseHolder<void *,FunctionBase<void *,&public: static void StressLog::Enter(void *),&public: static void StressLog::Leave(void *),0>,0,&int CompareDefault<void *>(void *,void *),0>(
        __int64 a1)
{
  if ( *(_DWORD *)(a1 + 8) )
  {
    IncCantAllocCount();
    ClrLeaveCriticalSection(qword_140027138);
    DecCantAllocCount();
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x14000faa4  push    rbx
0x14000faa6  sub     rsp, 20h
0x14000faaa  mov     rbx, rcx
0x14000faad  cmp     dword ptr [rcx+8], 0
0x14000fab1  jz      short loc_14000FACD
0x14000fab3  call    ?IncCantAllocCount@@YAXXZ; IncCantAllocCount(void)
0x14000fab8  mov     rcx, cs:qword_140027138; void *
0x14000fabf  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x14000fac4  call    ?DecCantAllocCount@@YAXXZ; DecCantAllocCount(void)
0x14000fac9  and     dword ptr [rbx+8], 0
0x14000facd  add     rsp, 20h
0x14000fad1  pop     rbx
0x14000fad2  retn
```
