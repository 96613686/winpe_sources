# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$167

- ea: `0x140014803`
- end: `0x14001482c`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$167`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140014803`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_167(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x20000);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x20000u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x140014803  push    rbp
0x140014805  sub     rsp, 20h
0x140014809  mov     rbp, rdx
0x14001480c  mov     eax, [rbp+40h]
0x14001480f  and     eax, 20000h
0x140014814  test    eax, eax
0x140014816  jz      short loc_140014826
0x140014818  btr     dword ptr [rbp+40h], 11h
0x14001481d  lea     rcx, [rbp+70h]
0x140014821  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014826  add     rsp, 20h
0x14001482a  pop     rbp
0x14001482b  retn
```
