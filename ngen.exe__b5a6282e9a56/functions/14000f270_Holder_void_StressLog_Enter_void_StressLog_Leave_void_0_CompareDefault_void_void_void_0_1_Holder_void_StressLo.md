# Holder<void *,&StressLog::Enter(void *),&StressLog::Leave(void *),0,&CompareDefault<void *>(void *,void *),0,1>::~Holder<void *,&StressLog::Enter(void *),&StressLog::Leave(void *),0,&CompareDefault<void *>(void *,void *),0,1>(void)

- ea: `0x14000f270`
- end: `0x14000f2a3`
- name: `??1?$Holder@PEAX$1?Enter@StressLog@@SAXPEAX@Z$1?Leave@2@SAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$0A@$00@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400159a6`

## callees

- `0x14000a218`
- `0x14000f270`
- `0x140011bbc`
- `0x140011cf0`

## pseudocode

```c
void __fastcall Holder<void *,&public: static void StressLog::Enter(void *),&public: static void StressLog::Leave(void *),0,&int CompareDefault<void *>(void *,void *),0,1>::~Holder<void *,&public: static void StressLog::Enter(void *),&public: static void StressLog::Leave(void *),0,&int CompareDefault<void *>(void *,void *),0,1>(
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
0x14000f270  mov     [rsp+arg_0], rcx
0x14000f275  push    rbx
0x14000f276  sub     rsp, 20h
0x14000f27a  mov     rbx, rcx
0x14000f27d  cmp     dword ptr [rcx+8], 0
0x14000f281  jz      short loc_14000F29D
0x14000f283  call    ?IncCantAllocCount@@YAXXZ; IncCantAllocCount(void)
0x14000f288  mov     rcx, cs:qword_140027138; void *
0x14000f28f  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x14000f294  call    ?DecCantAllocCount@@YAXXZ; DecCantAllocCount(void)
0x14000f299  and     dword ptr [rbx+8], 0
0x14000f29d  add     rsp, 20h
0x14000f2a1  pop     rbx
0x14000f2a2  retn
```
