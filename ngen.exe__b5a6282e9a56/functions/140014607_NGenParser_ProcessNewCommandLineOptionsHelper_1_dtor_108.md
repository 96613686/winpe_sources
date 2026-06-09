# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$108

- ea: `0x140014607`
- end: `0x14001462d`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$108`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140014607`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_108(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x40);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x40u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x140014607  push    rbp
0x140014609  sub     rsp, 20h
0x14001460d  mov     rbp, rdx
0x140014610  mov     eax, [rbp+40h]
0x140014613  and     eax, 40h
0x140014616  test    eax, eax
0x140014618  jz      short loc_140014627
0x14001461a  and     dword ptr [rbp+40h], 0FFFFFFBFh
0x14001461e  lea     rcx, [rbp+70h]
0x140014622  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014627  add     rsp, 20h
0x14001462b  pop     rbp
0x14001462c  retn
```
