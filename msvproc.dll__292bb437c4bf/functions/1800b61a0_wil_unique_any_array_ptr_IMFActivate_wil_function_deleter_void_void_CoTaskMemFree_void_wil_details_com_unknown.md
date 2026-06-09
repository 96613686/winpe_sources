# wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)

- ea: `0x1800b61a0`
- end: `0x1800b6209`
- name: `?reset@?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b32ac`
- `0x1800b344c`

## callees

- `0x1800b61a0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b61e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b61e4`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(
        __int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *v3; // rsi

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
    {
      if ( *v1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v1 + 16LL))(*v1);
      ++v1;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800b61a0  mov     [rsp+arg_0], rbx
0x1800b61a5  mov     [rsp+arg_8], rsi
0x1800b61aa  push    rdi
0x1800b61ab  sub     rsp, 20h
0x1800b61af  mov     rbx, [rcx]
0x1800b61b2  mov     rdi, rcx
0x1800b61b5  test    rbx, rbx
0x1800b61b8  jz      short loc_1800B61F9
0x1800b61ba  mov     rax, [rcx+8]
0x1800b61be  lea     rsi, [rbx+rax*8]
0x1800b61c2  jmp     short loc_1800B61DC
0x1800b61c4  mov     rcx, [rbx]
0x1800b61c7  test    rcx, rcx
0x1800b61ca  jz      short loc_1800B61D8
0x1800b61cc  mov     rax, [rcx]
0x1800b61cf  mov     rax, [rax+10h]
0x1800b61d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b61d8  add     rbx, 8
0x1800b61dc  cmp     rbx, rsi
0x1800b61df  jnz     short loc_1800B61C4
0x1800b61e1  mov     rcx, [rdi]; pv
0x1800b61e4  call    cs:__imp_CoTaskMemFree
0x1800b61ea  mov     qword ptr [rdi], 0
0x1800b61f1  mov     qword ptr [rdi+8], 0
0x1800b61f9  mov     rbx, [rsp+28h+arg_0]
0x1800b61fe  mov     rsi, [rsp+28h+arg_8]
0x1800b6203  add     rsp, 20h
0x1800b6207  pop     rdi
0x1800b6208  retn
```
