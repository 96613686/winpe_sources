# _REGUTIL::GetConfigString_DontUse__::_1_::dtor$5

- ea: `0x140015a4a`
- end: `0x140015a70`
- name: `_REGUTIL::GetConfigString_DontUse__::_1_::dtor$5`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006170`
- `0x140015a4a`

## pseudocode

```c
_QWORD *__fastcall REGUTIL::GetConfigString_DontUse__::_1_::dtor_5(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 48) & 2);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~2u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x140015a4a  push    rbp
0x140015a4c  sub     rsp, 20h
0x140015a50  mov     rbp, rdx
0x140015a53  mov     eax, [rbp+30h]
0x140015a56  and     eax, 2
0x140015a59  test    eax, eax
0x140015a5b  jz      short loc_140015A6A
0x140015a5d  and     dword ptr [rbp+30h], 0FFFFFFFDh
0x140015a61  lea     rcx, [rbp+38h]
0x140015a65  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140015a6a  add     rsp, 20h
0x140015a6e  pop     rbp
0x140015a6f  retn
```
