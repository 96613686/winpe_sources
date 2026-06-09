# _NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$105

- ea: `0x1400145e1`
- end: `0x140014607`
- name: `_NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor$105`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140006170`
- `0x1400145e1`

## pseudocode

```c
_QWORD *__fastcall NGenParser::ProcessNewCommandLineOptionsHelper_::_1_::dtor_105(__int64 a1, __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 64) & 0x20);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~0x20u;
    return BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder((_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x1400145e1  push    rbp
0x1400145e3  sub     rsp, 20h
0x1400145e7  mov     rbp, rdx
0x1400145ea  mov     eax, [rbp+40h]
0x1400145ed  and     eax, 20h
0x1400145f0  test    eax, eax
0x1400145f2  jz      short loc_140014601
0x1400145f4  and     dword ptr [rbp+40h], 0FFFFFFDFh
0x1400145f8  lea     rcx, [rbp+70h]
0x1400145fc  call    ??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ; BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)
0x140014601  add     rsp, 20h
0x140014605  pop     rbp
0x140014606  retn
```
