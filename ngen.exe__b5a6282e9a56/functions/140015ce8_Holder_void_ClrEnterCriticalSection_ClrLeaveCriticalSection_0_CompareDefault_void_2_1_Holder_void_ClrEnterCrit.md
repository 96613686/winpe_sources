# _Holder_void___&ClrEnterCriticalSection_&ClrLeaveCriticalSection_0_&CompareDefault_void____2_1_::_Holder_void___&ClrEnterCriticalSection_&ClrLeaveCriticalSection_0_&CompareDefault_void____2_1__::_1_::dtor$0

- ea: `0x140015ce8`
- end: `0x140015cf4`
- name: `_Holder_void___&ClrEnterCriticalSection_&ClrLeaveCriticalSection_0_&CompareDefault_void____2_1_::_Holder_void___&ClrEnterCriticalSection_&ClrLeaveCriticalSection_0_&CompareDefault_void____2_1__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012df4`

## pseudocode

```c
void __fastcall Holder_void____ClrEnterCriticalSection__ClrLeaveCriticalSection_0__CompareDefault_void____2_1_::_Holder_void____ClrEnterCriticalSection__ClrLeaveCriticalSection_0__CompareDefault_void____2_1__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  BaseHolder<void *,FunctionBase<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&void ClrEnterCriticalSection(void *),&void ClrLeaveCriticalSection(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x140015ce8  mov     rcx, [rdx+30h]
0x140015cef  jmp     ??1?$BaseHolder@PEAXV?$FunctionBase@PEAX$1?ClrEnterCriticalSection@@YAXPEAX@Z$1?ClrLeaveCriticalSection@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAX@@YAHPEAX0@Z$01@@QEAA@XZ; BaseHolder<void *,FunctionBase<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),2>,0,&CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&ClrEnterCriticalSection(void *),&ClrLeaveCriticalSection(void *),2>,0,&CompareDefault<void *>(void *,void *),2>(void)
```
