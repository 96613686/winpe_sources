# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$161

- ea: `0x1400147da`
- end: `0x140014803`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$161`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x1400147da`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_161(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x10000);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x10000u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x1400147da  push    rbp
0x1400147dc  sub     rsp, 20h
0x1400147e0  mov     rbp, rdx
0x1400147e3  mov     eax, [rbp+40h]
0x1400147e6  and     eax, 10000h
0x1400147eb  test    eax, eax
0x1400147ed  jz      short loc_1400147FD
0x1400147ef  btr     dword ptr [rbp+40h], 10h
0x1400147f4  lea     rcx, [rbp+70h]
0x1400147f8  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x1400147fd  add     rsp, 20h
0x140014801  pop     rbp
0x140014802  retn
```
