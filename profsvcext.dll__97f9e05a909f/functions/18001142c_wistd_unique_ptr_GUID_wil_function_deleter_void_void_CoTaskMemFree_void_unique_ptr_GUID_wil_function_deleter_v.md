# wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18001142c`
- end: `0x18001144e`
- name: `??1?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e894`

## callees

- `0x18001142c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011442`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x18001142c  sub     rsp, 28h
0x180011430  mov     rax, [rcx]
0x180011433  mov     qword ptr [rcx], 0
0x18001143a  test    rax, rax
0x18001143d  jz      short loc_180011449
0x18001143f  mov     rcx, rax; pv
0x180011442  call    cs:__imp_CoTaskMemFree
0x180011448  nop
0x180011449  add     rsp, 28h
0x18001144d  retn
```
