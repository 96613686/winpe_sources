# wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18000cfa4`
- end: `0x18000cfc5`
- name: `??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180059767`

## callees

- `0x18000cfa4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfba`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18000cfa4  sub     rsp, 28h
0x18000cfa8  mov     rax, [rcx]
0x18000cfab  mov     qword ptr [rcx], 0
0x18000cfb2  test    rax, rax
0x18000cfb5  jz      short loc_18000CFC0
0x18000cfb7  mov     rcx, rax; pv
0x18000cfba  call    cs:__imp_CoTaskMemFree
0x18000cfc0  add     rsp, 28h
0x18000cfc4  retn
```
