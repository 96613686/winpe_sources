# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$99

- ea: `0x140014595`
- end: `0x1400145bb`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$99`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x140014595`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_99(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 8);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~8u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x140014595  push    rbp
0x140014597  sub     rsp, 20h
0x14001459b  mov     rbp, rdx
0x14001459e  mov     eax, [rbp+40h]
0x1400145a1  and     eax, 8
0x1400145a4  test    eax, eax
0x1400145a6  jz      short loc_1400145B5
0x1400145a8  and     dword ptr [rbp+40h], 0FFFFFFF7h
0x1400145ac  lea     rcx, [rbp+70h]
0x1400145b0  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x1400145b5  add     rsp, 20h
0x1400145b9  pop     rbp
0x1400145ba  retn
```
