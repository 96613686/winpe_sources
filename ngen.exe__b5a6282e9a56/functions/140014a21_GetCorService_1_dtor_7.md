# _GetCorService_::_1_::dtor$7

- ea: `0x140014a21`
- end: `0x140014a47`
- name: `_GetCorService_::_1_::dtor$7`
- size: `38`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006170`
- `0x140014a21`

## pseudocode

```c
_QWORD *__fastcall GetCorService_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 96));
  }
  return result;
}

```

## disassembly

```asm
0x140014a21  push    rbp
0x140014a23  sub     rsp, 20h
0x140014a27  mov     rbp, rdx
0x140014a2a  mov     eax, [rbp+20h]
0x140014a2d  and     eax, 1
0x140014a30  test    eax, eax
0x140014a32  jz      short loc_140014A41
0x140014a34  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x140014a38  lea     rcx, [rbp+60h]
0x140014a3c  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ
0x140014a41  add     rsp, 20h
0x140014a45  pop     rbp
0x140014a46  retn
```
