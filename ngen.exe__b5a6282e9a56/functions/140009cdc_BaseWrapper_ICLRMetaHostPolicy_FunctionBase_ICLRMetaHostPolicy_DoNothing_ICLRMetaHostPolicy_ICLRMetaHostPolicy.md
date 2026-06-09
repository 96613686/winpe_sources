# BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder(void)

- ea: `0x140009cdc`
- end: `0x140009ced`
- name: `??1AddressInitHolder@?$BaseWrapper@PEAUICLRMetaHostPolicy@@V?$FunctionBase@PEAUICLRMetaHostPolicy@@$1??$DoNothing@PEAUICLRMetaHostPolicy@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICLRMetaHostPolicy@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICLRMetaHostPolicy@@@@YAHPEAU1@0@Z$01@@QEAA@XZ`
- size: `17`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001441d`
- `0x140014855`
- `0x140014a47`
- `0x140014af6`
- `0x140014e74`
- `0x14001508c`
- `0x140015137`
- `0x14001564b`
- `0x14001596a`
- `0x140015ade`

## callees

- `0x140009cdc`

## pseudocode

```c
_QWORD *__fastcall BaseWrapper<ICLRMetaHostPolicy *,FunctionBase<ICLRMetaHostPolicy *,&void DoNothing<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *),&void DoTheRelease<ICLRMetaHostPolicy>(ICLRMetaHostPolicy *),2>,0,&int CompareDefault<ICLRMetaHostPolicy *>(ICLRMetaHostPolicy *,ICLRMetaHostPolicy *),2>::AddressInitHolder::~AddressInitHolder(
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
0x140009cdc  mov     rax, [rcx]
0x140009cdf  cmp     qword ptr [rax], 0
0x140009ce3  jz      short locret_140009CEC
0x140009ce5  mov     dword ptr [rax+8], 1
0x140009cec  retn
```
