# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$102

- ea: `0x1400145bb`
- end: `0x1400145e1`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$102`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x1400145bb`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_102(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x10);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x10u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x1400145bb  push    rbp
0x1400145bd  sub     rsp, 20h
0x1400145c1  mov     rbp, rdx
0x1400145c4  mov     eax, [rbp+40h]
0x1400145c7  and     eax, 10h
0x1400145ca  test    eax, eax
0x1400145cc  jz      short loc_1400145DB
0x1400145ce  and     dword ptr [rbp+40h], 0FFFFFFEFh
0x1400145d2  lea     rcx, [rbp+70h]
0x1400145d6  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x1400145db  add     rsp, 20h
0x1400145df  pop     rbp
0x1400145e0  retn
```
