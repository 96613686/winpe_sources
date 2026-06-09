# BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(void)

- ea: `0x140006170`
- end: `0x140006186`
- name: `??1TypedAddressInitHolder@?$BaseWrapper@PEAUICorSvcRepository@@V?$FunctionBase@PEAUICorSvcRepository@@$1??$DoNothing@PEAUICorSvcRepository@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcRepository@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcRepository@@@@YAHPEAU1@0@Z$01@@QEAA@XZ`
- size: `22`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `36`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400143f7`
- `0x14001444d`
- `0x14001454b`
- `0x140014595`
- `0x1400145bb`
- `0x1400145e1`
- `0x140014607`
- `0x140014651`
- `0x140014692`
- `0x1400146bb`
- `0x1400146e4`
- `0x14001470d`
- `0x140014736`
- `0x14001475f`
- `0x140014788`
- `0x1400147b1`
- `0x1400147da`
- `0x140014803`
- `0x14001482c`
- `0x140014a21`
- `0x140014a77`
- `0x140014acd`
- `0x140014b02`
- `0x140014e4b`
- `0x140014e80`
- `0x140014ed9`
- `0x140014f02`
- `0x140015063`
- `0x140015098`
- `0x1400150e5`
- `0x14001510e`
- `0x140015625`
- `0x140015944`
- `0x140015a24`
- `0x140015a4a`
- `0x140015a70`

## callees

- `0x140006170`

## pseudocode

```c
_QWORD *__fastcall BaseWrapper<ICorSvcRepository *,FunctionBase<ICorSvcRepository *,&void DoNothing<ICorSvcRepository *>(ICorSvcRepository *),&void DoTheRelease<ICorSvcRepository>(ICorSvcRepository *),2>,0,&int CompareDefault<ICorSvcRepository *>(ICorSvcRepository *,ICorSvcRepository *),2>::TypedAddressInitHolder::~TypedAddressInitHolder(
        _QWORD *a1)
{
  _QWORD *result; // rax

  result = (_QWORD *)*a1;
  if ( *(_QWORD *)*a1 )
    *((_DWORD *)result + 2) = 1;
  return result;
}

```

## disassembly

```asm
0x140006170  mov     [rsp+arg_0], rcx
0x140006175  mov     rax, [rcx]
0x140006178  cmp     qword ptr [rax], 0
0x14000617c  jz      short locret_140006185
0x14000617e  mov     dword ptr [rax+8], 1
0x140006185  retn
```
