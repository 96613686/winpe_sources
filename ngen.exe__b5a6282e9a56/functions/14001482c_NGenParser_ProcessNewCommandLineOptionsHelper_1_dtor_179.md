# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$179

- ea: `0x14001482c`
- end: `0x140014855`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$179`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x14001482c`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_179(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x40000);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x40000u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x14001482c  push    rbp
0x14001482e  sub     rsp, 20h
0x140014832  mov     rbp, rdx
0x140014835  mov     eax, [rbp+40h]
0x140014838  and     eax, 40000h
0x14001483d  test    eax, eax
0x14001483f  jz      short loc_14001484F
0x140014841  btr     dword ptr [rbp+40h], 12h
0x140014846  lea     rcx, [rbp+70h]
0x14001484a  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x14001484f  add     rsp, 20h
0x140014853  pop     rbp
0x140014854  retn
```
