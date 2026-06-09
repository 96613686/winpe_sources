# BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>::~BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>(void)

- ea: `0x140009f98`
- end: `0x140009fc6`
- name: `??1?$BaseHolder@PEAUICorSvcSetLegacyServiceBehavior@@V?$FunctionBase@PEAUICorSvcSetLegacyServiceBehavior@@$1??$DoNothing@PEAUICorSvcSetLegacyServiceBehavior@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcSetLegacyServiceBehavior@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcSetLegacyServiceBehavior@@@@YAHPEAU1@0@Z$01@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `19`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400143eb`
- `0x140014441`
- `0x14001448b`
- `0x1400144af`
- `0x1400144d3`
- `0x1400144f7`
- `0x14001451b`
- `0x14001453f`
- `0x140014589`
- `0x140014645`
- `0x140014a15`
- `0x140014a6b`
- `0x140014ac1`
- `0x140014cc7`
- `0x140014e1b`
- `0x140014e3f`
- `0x140015057`
- `0x1400150d9`
- `0x1400155ad`

## callees

- `0x140009f98`
- `0x140013f30`

## pseudocode

```c
__int64 __fastcall BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&void DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&void DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&int CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>::~BaseHolder<ICorSvcSetLegacyServiceBehavior *,FunctionBase<ICorSvcSetLegacyServiceBehavior *,&void DoNothing<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *),&void DoTheRelease<ICorSvcSetLegacyServiceBehavior>(ICorSvcSetLegacyServiceBehavior *),2>,0,&int CompareDefault<ICorSvcSetLegacyServiceBehavior *>(ICorSvcSetLegacyServiceBehavior *,ICorSvcSetLegacyServiceBehavior *),2>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  if ( *((_DWORD *)a1 + 2) )
  {
    v2 = *a1;
    if ( v2 )
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_DWORD *)a1 + 2) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140009f98  push    rbx
0x140009f9a  sub     rsp, 20h
0x140009f9e  mov     rbx, rcx
0x140009fa1  cmp     dword ptr [rcx+8], 0
0x140009fa5  jz      short loc_140009FC0
0x140009fa7  mov     rcx, [rcx]
0x140009faa  test    rcx, rcx
0x140009fad  jz      short loc_140009FBC
0x140009faf  mov     rax, [rcx]
0x140009fb2  mov     rax, [rax+10h]
0x140009fb6  call    cs:__guard_dispatch_icall_fptr
0x140009fbc  and     dword ptr [rbx+8], 0
0x140009fc0  add     rsp, 20h
0x140009fc4  pop     rbx
0x140009fc5  retn
```
