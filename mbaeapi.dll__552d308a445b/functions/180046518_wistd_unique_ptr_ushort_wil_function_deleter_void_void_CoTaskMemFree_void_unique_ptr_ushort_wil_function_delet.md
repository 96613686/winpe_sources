# wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x180046518`
- end: `0x180046539`
- name: `??1?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b2bd`

## callees

- `0x180046518`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004652e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004652e`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x180046518  sub     rsp, 28h
0x18004651c  mov     rax, [rcx]
0x18004651f  mov     qword ptr [rcx], 0
0x180046526  test    rax, rax
0x180046529  jz      short loc_180046534
0x18004652b  mov     rcx, rax; pv
0x18004652e  call    cs:__imp_CoTaskMemFree
0x180046534  add     rsp, 28h
0x180046538  retn
```
