# _GetCorService_::_1_::dtor$13

- ea: `0x140014a77`
- end: `0x140014a9d`
- name: `_GetCorService_::_1_::dtor$13`
- size: `38`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006170`
- `0x140014a77`

## pseudocode

```c
_QWORD *__fastcall GetCorService_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 2);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~2u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 96));
  }
  return result;
}

```

## disassembly

```asm
0x140014a77  push    rbp
0x140014a79  sub     rsp, 20h
0x140014a7d  mov     rbp, rdx
0x140014a80  mov     eax, [rbp+20h]
0x140014a83  and     eax, 2
0x140014a86  test    eax, eax
0x140014a88  jz      short loc_140014A97
0x140014a8a  and     dword ptr [rbp+20h], 0FFFFFFFDh
0x140014a8e  lea     rcx, [rbp+60h]
0x140014a92  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ
0x140014a97  add     rsp, 20h
0x140014a9b  pop     rbp
0x140014a9c  retn
```
