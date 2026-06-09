# GetErrorTableInterceptor(_GUID const &,void * *)

- ea: `0x18000225c`
- end: `0x18000230e`
- name: `?GetErrorTableInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002970`

## callees

- `0x18000225c`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180002276`
- `ole32!CoTaskMemAlloc` at `0x180002276`

## pseudocode

```c
__int64 __fastcall GetErrorTableInterceptor(const struct _GUID *a1, void **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  int v6; // edi

  v4 = CoTaskMemAlloc(0x38u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4[4] = 0;
  *v4 = &ErrorTable::`vftable'{for `ISimpleTableInterceptor'};
  v4[1] = &ErrorTable::`vftable'{for `ISimpleTableWrite2'};
  v4[2] = &ErrorTable::`vftable'{for `ISimpleTableController'};
  v4[3] = &ErrorTable::`vftable'{for `IErrorInfo'};
  v4[5] = 0;
  v4[6] = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v4)(v4, a1, a2);
  if ( v6 < 0 )
    (*(void (__fastcall **)(_QWORD *, __int64))(*v5 + 32LL))(v5, 1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000225c  mov     [rsp+arg_0], rbx
0x180002261  mov     [rsp+arg_8], rsi
0x180002266  push    rdi
0x180002267  sub     rsp, 20h
0x18000226b  mov     rsi, rcx
0x18000226e  mov     rdi, rdx
0x180002271  mov     ecx, 38h ; '8'; cb
0x180002276  call    cs:__imp_CoTaskMemAlloc
0x18000227c  mov     rbx, rax
0x18000227f  test    rax, rax
0x180002282  jz      short loc_1800022F9
0x180002284  mov     qword ptr [rbx+20h], 0
0x18000228c  lea     rax, ??_7ErrorTable@@6BISimpleTableInterceptor@@@; const ErrorTable::`vftable'{for `ISimpleTableInterceptor'}
0x180002293  mov     [rbx], rax
0x180002296  mov     r8, rdi
0x180002299  lea     rax, ??_7ErrorTable@@6BISimpleTableWrite2@@@; const ErrorTable::`vftable'{for `ISimpleTableWrite2'}
0x1800022a0  mov     rdx, rsi
0x1800022a3  mov     [rbx+8], rax
0x1800022a7  mov     rcx, rbx
0x1800022aa  lea     rax, ??_7ErrorTable@@6BISimpleTableController@@@; const ErrorTable::`vftable'{for `ISimpleTableController'}
0x1800022b1  mov     [rbx+10h], rax
0x1800022b5  lea     rax, ??_7ErrorTable@@6BIErrorInfo@@@; const ErrorTable::`vftable'{for `IErrorInfo'}
0x1800022bc  mov     [rbx+18h], rax
0x1800022c0  mov     qword ptr [rbx+28h], 0
0x1800022c8  mov     qword ptr [rbx+30h], 0
0x1800022d0  mov     rax, [rbx]
0x1800022d3  mov     rax, [rax]
0x1800022d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022db  mov     edi, eax
0x1800022dd  test    eax, eax
0x1800022df  jns     short loc_1800022F5
0x1800022e1  mov     rcx, [rbx]
0x1800022e4  mov     edx, 1
0x1800022e9  mov     rax, [rcx+20h]
0x1800022ed  mov     rcx, rbx
0x1800022f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022f5  mov     eax, edi
0x1800022f7  jmp     short loc_1800022FE
0x1800022f9  mov     eax, 8007000Eh
0x1800022fe  mov     rbx, [rsp+28h+arg_0]
0x180002303  mov     rsi, [rsp+28h+arg_8]
0x180002308  add     rsp, 20h
0x18000230c  pop     rdi
0x18000230d  retn
```
