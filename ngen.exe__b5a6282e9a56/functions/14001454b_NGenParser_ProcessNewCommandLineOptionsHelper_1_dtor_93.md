# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$93

- ea: `0x14001454b`
- end: `0x140014571`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$93`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x14001454b`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_93(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 4);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~4u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x14001454b  push    rbp
0x14001454d  sub     rsp, 20h
0x140014551  mov     rbp, rdx
0x140014554  mov     eax, [rbp+40h]
0x140014557  and     eax, 4
0x14001455a  test    eax, eax
0x14001455c  jz      short loc_14001456B
0x14001455e  and     dword ptr [rbp+40h], 0FFFFFFFBh
0x140014562  lea     rcx, [rbp+70h]
0x140014566  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x14001456b  add     rsp, 20h
0x14001456f  pop     rbp
0x140014570  retn
```
