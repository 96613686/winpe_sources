# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x140004a80`
- end: `0x140004ad1`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `81`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x140004a80`
- `0x140019010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140004abd`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004abd`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        __int64 a1,
        char a2)
{
  __int64 v4; // rcx

  *(_DWORD *)(a1 + 44) = -1073741823;
  v4 = *(_QWORD *)(a1 + 32);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete((void *)a1);
  return a1;
}

```

## disassembly

```asm
0x140004a80  mov     [rsp+arg_0], rbx
0x140004a85  push    rdi
0x140004a86  sub     rsp, 20h
0x140004a8a  mov     edi, edx
0x140004a8c  mov     rbx, rcx
0x140004a8f  mov     dword ptr [rcx+2Ch], 0C0000001h
0x140004a96  mov     rcx, [rcx+20h]
0x140004a9a  test    rcx, rcx
0x140004a9d  jz      short loc_140004AB4
0x140004a9f  mov     qword ptr [rbx+20h], 0
0x140004aa7  mov     rax, [rcx]
0x140004aaa  mov     rax, [rax+10h]
0x140004aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ab3  nop
0x140004ab4  test    dil, 1
0x140004ab8  jz      short loc_140004AC3
0x140004aba  mov     rcx, rbx
0x140004abd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140004ac3  mov     rax, rbx
0x140004ac6  mov     rbx, [rsp+28h+arg_0]
0x140004acb  add     rsp, 20h
0x140004acf  pop     rdi
0x140004ad0  retn
```
