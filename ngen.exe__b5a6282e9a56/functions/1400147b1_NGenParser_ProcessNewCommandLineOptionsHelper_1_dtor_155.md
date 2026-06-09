# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$155

- ea: `0x1400147b1`
- end: `0x1400147da`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$155`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x1400147b1`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_155(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x8000);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x8000u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x1400147b1  push    rbp
0x1400147b3  sub     rsp, 20h
0x1400147b7  mov     rbp, rdx
0x1400147ba  mov     eax, [rbp+40h]
0x1400147bd  and     eax, 8000h
0x1400147c2  test    eax, eax
0x1400147c4  jz      short loc_1400147D4
0x1400147c6  btr     dword ptr [rbp+40h], 0Fh
0x1400147cb  lea     rcx, [rbp+70h]
0x1400147cf  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x1400147d4  add     rsp, 20h
0x1400147d8  pop     rbp
0x1400147d9  retn
```
