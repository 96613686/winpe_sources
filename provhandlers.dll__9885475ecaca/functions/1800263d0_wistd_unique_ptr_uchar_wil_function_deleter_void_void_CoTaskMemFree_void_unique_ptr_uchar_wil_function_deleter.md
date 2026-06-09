# wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x1800263d0`
- end: `0x1800263f1`
- name: `??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d077`

## callees

- `0x1800263d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800263e6`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x1800263d0  sub     rsp, 28h
0x1800263d4  mov     rax, [rcx]
0x1800263d7  mov     qword ptr [rcx], 0
0x1800263de  test    rax, rax
0x1800263e1  jz      short loc_1800263EC
0x1800263e3  mov     rcx, rax; pv
0x1800263e6  call    cs:__imp_CoTaskMemFree
0x1800263ec  add     rsp, 28h
0x1800263f0  retn
```
