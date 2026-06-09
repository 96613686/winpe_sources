# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$143

- ea: `0x14001475f`
- end: `0x140014788`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$143`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x14001475f`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_143(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x2000);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x2000u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x14001475f  push    rbp
0x140014761  sub     rsp, 20h
0x140014765  mov     rbp, rdx
0x140014768  mov     eax, [rbp+40h]
0x14001476b  and     eax, 2000h
0x140014770  test    eax, eax
0x140014772  jz      short loc_140014782
0x140014774  btr     dword ptr [rbp+40h], 0Dh
0x140014779  lea     rcx, [rbp+70h]
0x14001477d  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014782  add     rsp, 20h
0x140014786  pop     rbp
0x140014787  retn
```
