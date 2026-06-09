# _BaseWrapper_HKEY_____FunctionBase_HKEY_____&DoNothing_HKEY______&RegKeyRelease_2__0_&CompareDefault_HKEY______2_::operator&_::_1_::dtor$0

- ea: `0x140015944`
- end: `0x14001596a`
- name: `_BaseWrapper_HKEY_____FunctionBase_HKEY_____&DoNothing_HKEY______&RegKeyRelease_2__0_&CompareDefault_HKEY______2_::operator&_::_1_::dtor$0`
- size: `38`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140015944`

## pseudocode

```c
_QWORD *__fastcall BaseWrapper_HKEY_____FunctionBase_HKEY______DoNothing_HKEY_______RegKeyRelease_2__0__CompareDefault_HKEY______2_::operator&_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(*(_QWORD **)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x140015944  push    rbp
0x140015946  sub     rsp, 20h
0x14001594a  mov     rbp, rdx
0x14001594d  mov     eax, [rbp+20h]
0x140015950  and     eax, 1
0x140015953  test    eax, eax
0x140015955  jz      short loc_140015964
0x140015957  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14001595b  mov     rcx, [rbp+48h]
0x14001595f  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140015964  add     rsp, 20h
0x140015968  pop     rbp
0x140015969  retn
```
