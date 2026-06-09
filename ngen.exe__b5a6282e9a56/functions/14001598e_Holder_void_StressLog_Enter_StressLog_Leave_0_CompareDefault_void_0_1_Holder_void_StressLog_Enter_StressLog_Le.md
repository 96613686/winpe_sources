# _Holder_void___&StressLog::Enter_&StressLog::Leave_0_&CompareDefault_void____0_1_::_Holder_void___&StressLog::Enter_&StressLog::Leave_0_&CompareDefault_void____0_1__::_1_::dtor$0

- ea: `0x14001598e`
- end: `0x14001599a`
- name: `_Holder_void___&StressLog::Enter_&StressLog::Leave_0_&CompareDefault_void____0_1_::_Holder_void___&StressLog::Enter_&StressLog::Leave_0_&CompareDefault_void____0_1__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000faa4`

## pseudocode

```c
void __fastcall Holder_void____StressLog::Enter__StressLog::Leave_0__CompareDefault_void____0_1_::_Holder_void____StressLog::Enter__StressLog::Leave_0__CompareDefault_void____0_1__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  BaseHolder<void *,FunctionBase<void *,&public: static void StressLog::Enter(void *),&public: static void StressLog::Leave(void *),0>,0,&int CompareDefault<void *>(void *,void *),0>::~BaseHolder<void *,FunctionBase<void *,&public: static void StressLog::Enter(void *),&public: static void StressLog::Leave(void *),0>,0,&int CompareDefault<void *>(void *,void *),0>(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x14001598e  mov     rcx, [rdx+30h]
0x140015995  jmp     ??1?$BaseHolder@PEAXV?$FunctionBase@PEAX$1?Enter@StressLog@@SAXPEAX@Z$1?Leave@2@SAX0@Z$0A@@@$0A@$1??$CompareDefault@PEAX@@YAHPEAX0@Z$0A@@@QEAA@XZ; BaseHolder<void *,FunctionBase<void *,&StressLog::Enter(void *),&StressLog::Leave(void *),0>,0,&CompareDefault<void *>(void *,void *),0>::~BaseHolder<void *,FunctionBase<void *,&StressLog::Enter(void *),&StressLog::Leave(void *),0>,0,&CompareDefault<void *>(void *,void *),0>(void)
```
