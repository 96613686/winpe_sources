# wil::WaitForCompletion<Windows::ApplicationModel::AppService::AppServiceResponse *,Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceResponse>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS)

- ea: `0x140004418`
- end: `0x140004483`
- name: `??$WaitForCompletion@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@V?$ComPtr@UIAppServiceResponse@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIAppServiceResponse@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005bd4`
- `0x1400081c4`

## callees

- `0x140003f18`
- `0x140004418`
- `0x14000bff0`
- `0x14001a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::WaitForCompletion<Windows::ApplicationModel::AppService::AppServiceResponse *,Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceResponse>>(
        _QWORD *a1,
        __int64 a2,
        int a3)
{
  int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v5 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(
         a2,
         a2,
         a3);
  if ( v5 >= 0 )
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a2 + 64LL))(a2, a1);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v6, v7, (const char *)(unsigned int)v5, 2);
  return a1;
}

```

## disassembly

```asm
0x140004418  mov     rax, rsp
0x14000441b  mov     [rax+10h], rbx
0x14000441f  mov     [rax+8], rcx
0x140004423  push    rdi
0x140004424  sub     rsp, 30h
0x140004428  mov     rdi, rdx
0x14000442b  mov     rbx, rcx
0x14000442e  mov     dword ptr [rax-18h], 0
0x140004435  mov     qword ptr [rcx], 0
0x14000443c  mov     dword ptr [rax-18h], 2
0x140004443  mov     rcx, rdx
0x140004446  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x14000444b  test    eax, eax
0x14000444d  js      short loc_140004462
0x14000444f  mov     rax, [rdi]
0x140004452  mov     rdx, rbx
0x140004455  mov     rcx, rdi
0x140004458  mov     rax, [rax+40h]
0x14000445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004461  nop
0x140004462  mov     rcx, [rsp+38h]; this
0x140004467  test    eax, eax
0x140004469  js      short loc_14000447A
0x14000446b  mov     rax, rbx
0x14000446e  mov     rbx, [rsp+38h+arg_8]
0x140004473  add     rsp, 30h
0x140004477  pop     rdi
0x140004478  retn
0x14000447a  mov     r9d, eax; char *
0x14000447d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
