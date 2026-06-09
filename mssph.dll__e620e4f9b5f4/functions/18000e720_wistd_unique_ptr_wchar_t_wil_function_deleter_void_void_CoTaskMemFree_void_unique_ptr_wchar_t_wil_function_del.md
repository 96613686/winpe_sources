# wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18000e720`
- end: `0x18000e741`
- name: `??1?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800268c9`
- `0x1800269de`

## callees

- `0x18000e720`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e736`

## pseudocode

```c
void __fastcall wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x18000e720  sub     rsp, 28h
0x18000e724  mov     rax, [rcx]
0x18000e727  mov     qword ptr [rcx], 0
0x18000e72e  test    rax, rax
0x18000e731  jz      short loc_18000E73C
0x18000e733  mov     rcx, rax; pv
0x18000e736  call    cs:__imp_CoTaskMemFree
0x18000e73c  add     rsp, 28h
0x18000e740  retn
```
