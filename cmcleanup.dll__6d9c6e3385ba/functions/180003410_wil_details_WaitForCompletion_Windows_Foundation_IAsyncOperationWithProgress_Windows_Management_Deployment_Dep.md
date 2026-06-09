# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`scalar deleting destructor'(uint)

- ea: `0x180003410`
- end: `0x180003488`
- name: `??_GCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `120`
- prototype: `_QWORD *__fastcall(_QWORD *Block, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001954`
- `0x180003410`
- `0x1800078c4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003428`

## pseudocode

```c
_QWORD *__fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>'::`2'::CompletionDelegate::`scalar deleting destructor'(
        _QWORD *Block,
        char a2)
{
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (void *)Block[7];
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  *((_DWORD *)Block + 11) = -1073741823;
  v7 = Block[4];
  if ( v7 )
  {
    Block[4] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003410  mov     [rsp+arg_0], rbx
0x180003415  push    rdi
0x180003416  sub     rsp, 20h
0x18000341a  mov     edi, edx
0x18000341c  mov     rbx, rcx
0x18000341f  mov     rcx, [rcx+38h]; hObject
0x180003423  test    rcx, rcx
0x180003426  jz      short loc_180003437
0x180003428  call    cs:__imp_CloseHandle
0x18000342e  mov     rcx, [rsp+28h]; this
0x180003433  test    eax, eax
0x180003435  jz      short loc_18000347D
0x180003437  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000343e  mov     rcx, [rbx+20h]
0x180003442  test    rcx, rcx
0x180003445  jz      short loc_18000345C
0x180003447  mov     qword ptr [rbx+20h], 0
0x18000344f  mov     rax, [rcx]
0x180003452  mov     rax, [rax+10h]
0x180003456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345b  nop
0x18000345c  test    dil, 1
0x180003460  jz      short loc_18000346F
0x180003462  mov     edx, 40h ; '@'
0x180003467  mov     rcx, rbx; Block
0x18000346a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000346f  mov     rax, rbx
0x180003472  mov     rbx, [rsp+28h+arg_0]
0x180003477  add     rsp, 20h
0x18000347b  pop     rdi
0x18000347c  retn
0x18000347d  mov     edx, 0A0Bh; void *
0x180003482  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
