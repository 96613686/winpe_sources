# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$133

- ea: `0x1400146e4`
- end: `0x14001470d`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$133`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x1400146e4`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_133(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x400);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x400u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x1400146e4  push    rbp
0x1400146e6  sub     rsp, 20h
0x1400146ea  mov     rbp, rdx
0x1400146ed  mov     eax, [rbp+40h]
0x1400146f0  and     eax, 400h
0x1400146f5  test    eax, eax
0x1400146f7  jz      short loc_140014707
0x1400146f9  btr     dword ptr [rbp+40h], 0Ah
0x1400146fe  lea     rcx, [rbp+70h]
0x140014702  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014707  add     rsp, 20h
0x14001470b  pop     rbp
0x14001470c  retn
```
