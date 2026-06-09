# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`scalar deleting destructor'(uint)

- ea: `0x140004be0`
- end: `0x140004c61`
- name: `??_GCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140004be0`
- `0x14000bfd4`
- `0x14001a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140004c3b`
- `msvcrt!??3@YAXPEAX@Z` at `0x140004c3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004bf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004bf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140004be0  mov     [rsp+arg_0], rbx
0x140004be5  push    rdi
0x140004be6  sub     rsp, 20h
0x140004bea  mov     edi, edx
0x140004bec  mov     rbx, rcx
0x140004bef  mov     rcx, [rcx+38h]; hObject
0x140004bf3  test    rcx, rcx
0x140004bf6  jz      short loc_140004C0D
0x140004bf8  call    cs:__imp_CloseHandle
0x140004bff  nop     dword ptr [rax+rax+00h]
0x140004c04  mov     rcx, [rsp+28h]; this
0x140004c09  test    eax, eax
0x140004c0b  jz      short loc_140004C56
0x140004c0d  mov     dword ptr [rbx+2Ch], 0C0000001h
0x140004c14  mov     rcx, [rbx+20h]
0x140004c18  test    rcx, rcx
0x140004c1b  jz      short loc_140004C32
0x140004c1d  mov     qword ptr [rbx+20h], 0
0x140004c25  mov     rax, [rcx]
0x140004c28  mov     rax, [rax+10h]
0x140004c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c31  nop
0x140004c32  test    dil, 1
0x140004c36  jz      short loc_140004C47
0x140004c38  mov     rcx, rbx
0x140004c3b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140004c42  nop     dword ptr [rax+rax+00h]
0x140004c47  mov     rax, rbx
0x140004c4a  mov     rbx, [rsp+28h+arg_0]
0x140004c4f  add     rsp, 20h
0x140004c53  pop     rdi
0x140004c54  retn
0x140004c56  mov     edx, 0A0Bh; void *
0x140004c5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
