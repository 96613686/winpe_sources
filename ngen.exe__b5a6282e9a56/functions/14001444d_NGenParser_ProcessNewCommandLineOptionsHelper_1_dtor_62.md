# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$62

- ea: `0x14001444d`
- end: `0x140014473`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$62`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x14001444d`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_62(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 2);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~2u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x14001444d  push    rbp
0x14001444f  sub     rsp, 20h
0x140014453  mov     rbp, rdx
0x140014456  mov     eax, [rbp+40h]
0x140014459  and     eax, 2
0x14001445c  test    eax, eax
0x14001445e  jz      short loc_14001446D
0x140014460  and     dword ptr [rbp+40h], 0FFFFFFFDh
0x140014464  lea     rcx, [rbp+70h]
0x140014468  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x14001446d  add     rsp, 20h
0x140014471  pop     rbp
0x140014472  retn
```
