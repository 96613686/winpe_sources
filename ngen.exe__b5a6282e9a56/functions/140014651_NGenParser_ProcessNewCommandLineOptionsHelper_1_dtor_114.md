# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$114

- ea: `0x140014651`
- end: `0x14001467a`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$114`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140014651`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_114(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x80);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x80u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x140014651  push    rbp
0x140014653  sub     rsp, 20h
0x140014657  mov     rbp, rdx
0x14001465a  mov     eax, [rbp+40h]
0x14001465d  and     eax, 80h
0x140014662  test    eax, eax
0x140014664  jz      short loc_140014674
0x140014666  btr     dword ptr [rbp+40h], 7
0x14001466b  lea     rcx, [rbp+70h]
0x14001466f  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014674  add     rsp, 20h
0x140014678  pop     rbp
0x140014679  retn
```
