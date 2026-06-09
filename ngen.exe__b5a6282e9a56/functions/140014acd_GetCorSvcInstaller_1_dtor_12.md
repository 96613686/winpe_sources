# _GetCorSvcInstaller_::_1_::dtor$12

- ea: `0x140014acd`
- end: `0x140014af6`
- name: `_GetCorSvcInstaller_::_1_::dtor$12`
- size: `41`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006170`
- `0x140014acd`

## pseudocode

```c
_QWORD *__fastcall GetCorSvcInstaller_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 144));
  }
  return result;
}

```

## disassembly

```asm
0x140014acd  push    rbp
0x140014acf  sub     rsp, 20h
0x140014ad3  mov     rbp, rdx
0x140014ad6  mov     eax, [rbp+20h]
0x140014ad9  and     eax, 1
0x140014adc  test    eax, eax
0x140014ade  jz      short loc_140014AF0
0x140014ae0  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x140014ae4  lea     rcx, [rbp+90h]
0x140014aeb  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014af0  add     rsp, 20h
0x140014af4  pop     rbp
0x140014af5  retn
```
