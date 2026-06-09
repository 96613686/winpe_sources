# BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>::~BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>(void)

- ea: `0x140009f0c`
- end: `0x140009f3e`
- name: `??1?$BaseWrapper@PEAUICorSvcOptimizer@@V?$FunctionBase@PEAUICorSvcOptimizer@@$1??$DoNothing@PEAUICorSvcOptimizer@@@@YAXPEAU1@@Z$1??$DoTheRelease@UICorSvcOptimizer@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUICorSvcOptimizer@@@@YAHPEAU1@0@Z$01@@QEAA@XZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400143df`
- `0x140014435`
- `0x14001447f`
- `0x1400144a3`
- `0x1400144c7`
- `0x1400144eb`
- `0x14001450f`
- `0x140014533`
- `0x14001457d`
- `0x140014639`
- `0x140014a09`
- `0x140014a5f`
- `0x140014ab5`
- `0x140014cbb`
- `0x140014e0f`
- `0x140014e33`
- `0x14001504b`
- `0x1400150cd`
- `0x1400155a1`

## callees

- `0x140009f0c`
- `0x140013f30`

## pseudocode

```c
__int64 __fastcall BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&void DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&void DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&int CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>::~BaseWrapper<ICorSvcOptimizer *,FunctionBase<ICorSvcOptimizer *,&void DoNothing<ICorSvcOptimizer *>(ICorSvcOptimizer *),&void DoTheRelease<ICorSvcOptimizer>(ICorSvcOptimizer *),2>,0,&int CompareDefault<ICorSvcOptimizer *>(ICorSvcOptimizer *,ICorSvcOptimizer *),2>(
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
0x140009f0c  mov     [rsp+arg_0], rcx
0x140009f11  push    rbx
0x140009f12  sub     rsp, 20h
0x140009f16  mov     rbx, rcx
0x140009f19  cmp     dword ptr [rcx+8], 0
0x140009f1d  jz      short loc_140009F38
0x140009f1f  mov     rcx, [rcx]
0x140009f22  test    rcx, rcx
0x140009f25  jz      short loc_140009F34
0x140009f27  mov     rax, [rcx]
0x140009f2a  mov     rax, [rax+10h]
0x140009f2e  call    cs:__guard_dispatch_icall_fptr
0x140009f34  and     dword ptr [rbx+8], 0
0x140009f38  add     rsp, 20h
0x140009f3c  pop     rbx
0x140009f3d  retn
```
