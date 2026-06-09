# _GetCorSvcInstaller_::_1_::dtor$27

- ea: `0x140014b02`
- end: `0x140014b2b`
- name: `_GetCorSvcInstaller_::_1_::dtor$27`
- size: `41`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006170`
- `0x140014b02`

## pseudocode

```c
_QWORD *__fastcall GetCorSvcInstaller_::_1_::dtor_27(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 2);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~2u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 144));
  }
  return result;
}

```

## disassembly

```asm
0x140014b02  push    rbp
0x140014b04  sub     rsp, 20h
0x140014b08  mov     rbp, rdx
0x140014b0b  mov     eax, [rbp+20h]
0x140014b0e  and     eax, 2
0x140014b11  test    eax, eax
0x140014b13  jz      short loc_140014B25
0x140014b15  and     dword ptr [rbp+20h], 0FFFFFFFDh
0x140014b19  lea     rcx, [rbp+90h]
0x140014b20  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014b25  add     rsp, 20h
0x140014b29  pop     rbp
0x140014b2a  retn
```
