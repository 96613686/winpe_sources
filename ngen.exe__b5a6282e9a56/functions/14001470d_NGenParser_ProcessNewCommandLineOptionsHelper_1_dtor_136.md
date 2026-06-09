# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$136

- ea: `0x14001470d`
- end: `0x140014736`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$136`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x14001470d`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_136(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x800);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x800u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x14001470d  push    rbp
0x14001470f  sub     rsp, 20h
0x140014713  mov     rbp, rdx
0x140014716  mov     eax, [rbp+40h]
0x140014719  and     eax, 800h
0x14001471e  test    eax, eax
0x140014720  jz      short loc_140014730
0x140014722  btr     dword ptr [rbp+40h], 0Bh
0x140014727  lea     rcx, [rbp+70h]
0x14001472b  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014730  add     rsp, 20h
0x140014734  pop     rbp
0x140014735  retn
```
