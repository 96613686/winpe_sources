# CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>::~CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>(void)

- ea: `0x180003260`
- end: `0x18000327e`
- name: `??1?$CAutoResource@PEAUITaskHandlerStatus@@U?$_CComObjectReleaser@UITaskHandlerStatus@@@@$0A@@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001410`
- `0x18000af70`

## callees

- `0x180003260`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>::~CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180003260  sub     rsp, 28h
0x180003264  mov     rcx, [rcx]
0x180003267  test    rcx, rcx
0x18000326a  jz      short loc_180003279
0x18000326c  mov     rax, [rcx]
0x18000326f  mov     rax, [rax+10h]
0x180003273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003278  nop
0x180003279  add     rsp, 28h
0x18000327d  retn
```
