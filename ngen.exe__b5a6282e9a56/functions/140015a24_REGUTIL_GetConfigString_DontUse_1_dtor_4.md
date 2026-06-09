# _REGUTIL::GetConfigString_DontUse__::_1_::dtor$4

- ea: `0x140015a24`
- end: `0x140015a4a`
- name: `_REGUTIL::GetConfigString_DontUse__::_1_::dtor$4`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006170`
- `0x140015a24`

## pseudocode

```c
_QWORD *__fastcall REGUTIL::GetConfigString_DontUse__::_1_::dtor_4(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 48) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x140015a24  push    rbp
0x140015a26  sub     rsp, 20h
0x140015a2a  mov     rbp, rdx
0x140015a2d  mov     eax, [rbp+30h]
0x140015a30  and     eax, 1
0x140015a33  test    eax, eax
0x140015a35  jz      short loc_140015A44
0x140015a37  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x140015a3b  lea     rcx, [rbp+38h]
0x140015a3f  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140015a44  add     rsp, 20h
0x140015a48  pop     rbp
0x140015a49  retn
```
