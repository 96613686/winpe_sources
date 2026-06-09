# Holder<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),0,&CompareDefault<void *>(void *,void *),2,1>::~Holder<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),0,&CompareDefault<void *>(void *,void *),2,1>(void)

- ea: `0x14001278c`
- end: `0x1400127b1`
- name: `??1?$Holder@PEAX$1?ClrEnterCriticalSection@@YAXPEAX@Z$1?ClrLeaveCriticalSection@@YAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$01$00@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140015cd0`

## callees

- `0x14000a218`
- `0x14001278c`

## pseudocode

```c
void __fastcall Holder<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),0,&int CompareDefault<void *>(void *,void *),2,1>::~Holder<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),0,&int CompareDefault<void *>(void *,void *),2,1>(
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
0x14001278c  mov     [rsp+arg_0], rcx
0x140012791  push    rbx
0x140012792  sub     rsp, 20h
0x140012796  mov     rbx, rcx
0x140012799  cmp     dword ptr [rcx+8], 0
0x14001279d  jz      short loc_1400127AB
0x14001279f  mov     rcx, [rcx]; void *
0x1400127a2  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x1400127a7  and     dword ptr [rbx+8], 0
0x1400127ab  add     rsp, 20h
0x1400127af  pop     rbx
0x1400127b0  retn
```
