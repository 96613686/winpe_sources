# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$128

- ea: `0x1400146bb`
- end: `0x1400146e4`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$128`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x1400146bb`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_128(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x200);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x200u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x1400146bb  push    rbp
0x1400146bd  sub     rsp, 20h
0x1400146c1  mov     rbp, rdx
0x1400146c4  mov     eax, [rbp+40h]
0x1400146c7  and     eax, 200h
0x1400146cc  test    eax, eax
0x1400146ce  jz      short loc_1400146DE
0x1400146d0  btr     dword ptr [rbp+40h], 9
0x1400146d5  lea     rcx, [rbp+70h]
0x1400146d9  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x1400146de  add     rsp, 20h
0x1400146e2  pop     rbp
0x1400146e3  retn
```
