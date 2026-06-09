# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$150

- ea: `0x140014788`
- end: `0x1400147b1`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$150`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140014788`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_150(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x4000);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x4000u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x140014788  push    rbp
0x14001478a  sub     rsp, 20h
0x14001478e  mov     rbp, rdx
0x140014791  mov     eax, [rbp+40h]
0x140014794  and     eax, 4000h
0x140014799  test    eax, eax
0x14001479b  jz      short loc_1400147AB
0x14001479d  btr     dword ptr [rbp+40h], 0Eh
0x1400147a2  lea     rcx, [rbp+70h]
0x1400147a6  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x1400147ab  add     rsp, 20h
0x1400147af  pop     rbp
0x1400147b0  retn
```
