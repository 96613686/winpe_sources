# _REGUTIL::GetConfigString_DontUse__::_1_::dtor$6

- ea: `0x140015a70`
- end: `0x140015a96`
- name: `_REGUTIL::GetConfigString_DontUse__::_1_::dtor$6`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006170`
- `0x140015a70`

## pseudocode

```c
_QWORD *__fastcall REGUTIL::GetConfigString_DontUse__::_1_::dtor_6(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 48) & 4);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~4u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x140015a70  push    rbp
0x140015a72  sub     rsp, 20h
0x140015a76  mov     rbp, rdx
0x140015a79  mov     eax, [rbp+30h]
0x140015a7c  and     eax, 4
0x140015a7f  test    eax, eax
0x140015a81  jz      short loc_140015A90
0x140015a83  and     dword ptr [rbp+30h], 0FFFFFFFBh
0x140015a87  lea     rcx, [rbp+38h]
0x140015a8b  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140015a90  add     rsp, 20h
0x140015a94  pop     rbp
0x140015a95  retn
```
