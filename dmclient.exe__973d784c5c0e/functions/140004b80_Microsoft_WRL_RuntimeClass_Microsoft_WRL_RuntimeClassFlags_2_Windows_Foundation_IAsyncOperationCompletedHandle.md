# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x140004b80`
- end: `0x140004bd8`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x140004b80`
- `0x14001a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140004bbd`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004bbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140004b80  mov     [rsp+arg_0], rbx
0x140004b85  push    rdi
0x140004b86  sub     rsp, 20h
0x140004b8a  mov     edi, edx
0x140004b8c  mov     rbx, rcx
0x140004b8f  mov     dword ptr [rcx+2Ch], 0C0000001h
0x140004b96  mov     rcx, [rcx+20h]
0x140004b9a  test    rcx, rcx
0x140004b9d  jz      short loc_140004BB4
0x140004b9f  mov     qword ptr [rbx+20h], 0
0x140004ba7  mov     rax, [rcx]
0x140004baa  mov     rax, [rax+10h]
0x140004bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bb3  nop
0x140004bb4  test    dil, 1
0x140004bb8  jz      short loc_140004BC9
0x140004bba  mov     rcx, rbx
0x140004bbd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140004bc4  nop     dword ptr [rax+rax+00h]
0x140004bc9  mov     rax, rbx
0x140004bcc  mov     rbx, [rsp+28h+arg_0]
0x140004bd1  add     rsp, 20h
0x140004bd5  pop     rdi
0x140004bd6  retn
```
