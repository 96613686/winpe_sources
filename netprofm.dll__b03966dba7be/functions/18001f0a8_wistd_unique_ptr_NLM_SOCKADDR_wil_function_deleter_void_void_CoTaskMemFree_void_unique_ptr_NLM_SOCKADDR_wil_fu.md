# wistd::unique_ptr<NLM_SOCKADDR,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<NLM_SOCKADDR,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18001f0a8`
- end: `0x18001f0c9`
- name: `??1?$unique_ptr@UNLM_SOCKADDR@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800410a1`

## callees

- `0x18001f0a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f0be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f0be`

## pseudocode

```c
void __fastcall wistd::unique_ptr<NLM_SOCKADDR,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<NLM_SOCKADDR,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x18001f0a8  sub     rsp, 28h
0x18001f0ac  mov     rax, [rcx]
0x18001f0af  mov     qword ptr [rcx], 0
0x18001f0b6  test    rax, rax
0x18001f0b9  jz      short loc_18001F0C4
0x18001f0bb  mov     rcx, rax; pv
0x18001f0be  call    cs:__imp_CoTaskMemFree
0x18001f0c4  add     rsp, 28h
0x18001f0c8  retn
```
