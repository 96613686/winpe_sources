# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`scalar deleting destructor'(uint)

- ea: `0x140004ae0`
- end: `0x140004b54`
- name: `??_GCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140004ae0`
- `0x14000bc2c`
- `0x140019010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140004b35`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004b35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004af8`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>'::`2'::CompletionDelegate::`scalar deleting destructor'(
        __int64 a1,
        char a2)
{
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *(void **)(a1 + 56);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  *(_DWORD *)(a1 + 44) = -1073741823;
  v7 = *(_QWORD *)(a1 + 32);
  if ( v7 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( (a2 & 1) != 0 )
    operator delete((void *)a1);
  return a1;
}

```

## disassembly

```asm
0x140004ae0  mov     [rsp+arg_0], rbx
0x140004ae5  push    rdi
0x140004ae6  sub     rsp, 20h
0x140004aea  mov     edi, edx
0x140004aec  mov     rbx, rcx
0x140004aef  mov     rcx, [rcx+38h]; hObject
0x140004af3  test    rcx, rcx
0x140004af6  jz      short loc_140004B07
0x140004af8  call    cs:__imp_CloseHandle
0x140004afe  mov     rcx, [rsp+28h]; this
0x140004b03  test    eax, eax
0x140004b05  jz      short loc_140004B49
0x140004b07  mov     dword ptr [rbx+2Ch], 0C0000001h
0x140004b0e  mov     rcx, [rbx+20h]
0x140004b12  test    rcx, rcx
0x140004b15  jz      short loc_140004B2C
0x140004b17  mov     qword ptr [rbx+20h], 0
0x140004b1f  mov     rax, [rcx]
0x140004b22  mov     rax, [rax+10h]
0x140004b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b2b  nop
0x140004b2c  test    dil, 1
0x140004b30  jz      short loc_140004B3B
0x140004b32  mov     rcx, rbx
0x140004b35  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140004b3b  mov     rax, rbx
0x140004b3e  mov     rbx, [rsp+28h+arg_0]
0x140004b43  add     rsp, 20h
0x140004b47  pop     rdi
0x140004b48  retn
0x140004b49  mov     edx, 0A0Bh; void *
0x140004b4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
