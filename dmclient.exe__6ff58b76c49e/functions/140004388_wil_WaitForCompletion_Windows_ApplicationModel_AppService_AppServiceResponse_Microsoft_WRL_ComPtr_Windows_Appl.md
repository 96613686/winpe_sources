# wil::WaitForCompletion<Windows::ApplicationModel::AppService::AppServiceResponse *,Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceResponse>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS)

- ea: `0x140004388`
- end: `0x1400043f2`
- name: `??$WaitForCompletion@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@V?$ComPtr@UIAppServiceResponse@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIAppServiceResponse@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z`
- size: `106`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005b34`
- `0x140007ff8`

## callees

- `0x140003e98`
- `0x140004388`
- `0x14000bc48`
- `0x140019010`

## pseudocode

```c
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
0x140004388  mov     rax, rsp
0x14000438b  mov     [rax+10h], rbx
0x14000438f  mov     [rax+8], rcx
0x140004393  push    rdi
0x140004394  sub     rsp, 30h
0x140004398  mov     rdi, rdx
0x14000439b  mov     rbx, rcx
0x14000439e  mov     dword ptr [rax-18h], 0
0x1400043a5  mov     qword ptr [rcx], 0
0x1400043ac  mov     dword ptr [rax-18h], 2
0x1400043b3  mov     rcx, rdx
0x1400043b6  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x1400043bb  test    eax, eax
0x1400043bd  js      short loc_1400043D2
0x1400043bf  mov     rax, [rdi]
0x1400043c2  mov     rdx, rbx
0x1400043c5  mov     rcx, rdi
0x1400043c8  mov     rax, [rax+40h]
0x1400043cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043d1  nop
0x1400043d2  mov     rcx, [rsp+38h]; this
0x1400043d7  test    eax, eax
0x1400043d9  js      short loc_1400043E9
0x1400043db  mov     rax, rbx
0x1400043de  mov     rbx, [rsp+38h+arg_8]
0x1400043e3  add     rsp, 30h
0x1400043e7  pop     rdi
0x1400043e8  retn
0x1400043e9  mov     r9d, eax; char *
0x1400043ec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
