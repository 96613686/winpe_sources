# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$125

- ea: `0x140014692`
- end: `0x1400146bb`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$125`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140014692`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_125(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x100);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x100u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x140014692  push    rbp
0x140014694  sub     rsp, 20h
0x140014698  mov     rbp, rdx
0x14001469b  mov     eax, [rbp+40h]
0x14001469e  and     eax, 100h
0x1400146a3  test    eax, eax
0x1400146a5  jz      short loc_1400146B5
0x1400146a7  btr     dword ptr [rbp+40h], 8
0x1400146ac  lea     rcx, [rbp+70h]
0x1400146b0  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x1400146b5  add     rsp, 20h
0x1400146b9  pop     rbp
0x1400146ba  retn
```
