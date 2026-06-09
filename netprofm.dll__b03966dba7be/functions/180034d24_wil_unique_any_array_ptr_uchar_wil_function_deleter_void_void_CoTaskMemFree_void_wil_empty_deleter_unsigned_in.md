# wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)

- ea: `0x180034d24`
- end: `0x180034d50`
- name: `??1?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003640c`
- `0x1800414fc`
- `0x180041664`

## callees

- `0x180034d24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d35`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180034d24  push    rbx
0x180034d26  sub     rsp, 20h
0x180034d2a  mov     rbx, rcx
0x180034d2d  mov     rcx, [rcx]; pv
0x180034d30  test    rcx, rcx
0x180034d33  jz      short loc_180034D4A
0x180034d35  call    cs:__imp_CoTaskMemFree
0x180034d3b  mov     qword ptr [rbx], 0
0x180034d42  mov     qword ptr [rbx+8], 0
0x180034d4a  add     rsp, 20h
0x180034d4e  pop     rbx
0x180034d4f  retn
```
