# BaseHolder<void *,FunctionBase<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),2>,0,&CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),2>,0,&CompareDefault<void *>(void *,void *),2>(void)

- ea: `0x140012df4`
- end: `0x140012e15`
- name: `??1?$BaseHolder@PEAXV?$FunctionBase@PEAX$1?ClrEnterCriticalSection@@YAXPEAX@Z$1?ClrLeaveCriticalSection@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAX@@YAHPEAX0@Z$01@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140015cdc`
- `0x140015ce8`

## callees

- `0x14000a218`
- `0x140012df4`

## pseudocode

```c
void __fastcall BaseHolder<void *,FunctionBase<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>(
        __int64 a1)
{
  if ( *(_DWORD *)(a1 + 8) )
  {
    ClrLeaveCriticalSection(*(void **)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x140012df4  push    rbx
0x140012df6  sub     rsp, 20h
0x140012dfa  mov     rbx, rcx
0x140012dfd  cmp     dword ptr [rcx+8], 0
0x140012e01  jz      short loc_140012E0F
0x140012e03  mov     rcx, [rcx]; void *
0x140012e06  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x140012e0b  and     dword ptr [rbx+8], 0
0x140012e0f  add     rsp, 20h
0x140012e13  pop     rbx
0x140012e14  retn
```
