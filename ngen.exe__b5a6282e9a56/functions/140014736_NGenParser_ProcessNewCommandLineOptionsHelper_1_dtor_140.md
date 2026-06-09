# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$140

- ea: `0x140014736`
- end: `0x14001475f`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$140`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140014736`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_140(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x1000);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x1000u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x140014736  push    rbp
0x140014738  sub     rsp, 20h
0x14001473c  mov     rbp, rdx
0x14001473f  mov     eax, [rbp+40h]
0x140014742  and     eax, 1000h
0x140014747  test    eax, eax
0x140014749  jz      short loc_140014759
0x14001474b  btr     dword ptr [rbp+40h], 0Ch
0x140014750  lea     rcx, [rbp+70h]
0x140014754  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014759  add     rsp, 20h
0x14001475d  pop     rbp
0x14001475e  retn
```
