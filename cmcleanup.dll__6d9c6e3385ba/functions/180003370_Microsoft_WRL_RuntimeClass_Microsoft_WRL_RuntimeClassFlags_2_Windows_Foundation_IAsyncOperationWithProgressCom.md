# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(uint)

- ea: `0x180003370`
- end: `0x1800033c5`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `85`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001954`
- `0x180003370`
- `0x180009010`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  Block[11] = -1073741823;
  v4 = *((_QWORD *)Block + 4);
  if ( v4 )
  {
    *((_QWORD *)Block + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003370  mov     [rsp+arg_0], rbx
0x180003375  push    rdi
0x180003376  sub     rsp, 20h
0x18000337a  mov     edi, edx
0x18000337c  mov     rbx, rcx
0x18000337f  mov     dword ptr [rcx+2Ch], 0C0000001h
0x180003386  mov     rcx, [rcx+20h]
0x18000338a  test    rcx, rcx
0x18000338d  jz      short loc_1800033A4
0x18000338f  mov     qword ptr [rbx+20h], 0
0x180003397  mov     rax, [rcx]
0x18000339a  mov     rax, [rax+10h]
0x18000339e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a3  nop
0x1800033a4  test    dil, 1
0x1800033a8  jz      short loc_1800033B7
0x1800033aa  mov     edx, 30h ; '0'
0x1800033af  mov     rcx, rbx; Block
0x1800033b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800033b7  mov     rax, rbx
0x1800033ba  mov     rbx, [rsp+28h+arg_0]
0x1800033bf  add     rsp, 20h
0x1800033c3  pop     rdi
0x1800033c4  retn
```
