# wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x1800253e8`
- end: `0x180025409`
- name: `??1?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002dbed`

## callees

- `0x1800253e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253fe`

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
0x1800253e8  sub     rsp, 28h
0x1800253ec  mov     rax, [rcx]
0x1800253ef  mov     qword ptr [rcx], 0
0x1800253f6  test    rax, rax
0x1800253f9  jz      short loc_180025404
0x1800253fb  mov     rcx, rax; pv
0x1800253fe  call    cs:__imp_CoTaskMemFree
0x180025404  add     rsp, 28h
0x180025408  retn
```
