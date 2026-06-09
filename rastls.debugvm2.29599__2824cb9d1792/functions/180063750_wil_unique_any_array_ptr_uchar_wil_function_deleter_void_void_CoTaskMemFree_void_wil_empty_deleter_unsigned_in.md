# wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)

- ea: `0x180063750`
- end: `0x18006377c`
- name: `?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062908`
- `0x180063784`

## callees

- `0x180063750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063761`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(
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
0x180063750  push    rbx
0x180063752  sub     rsp, 20h
0x180063756  mov     rbx, rcx
0x180063759  mov     rcx, [rcx]; pv
0x18006375c  test    rcx, rcx
0x18006375f  jz      short loc_180063776
0x180063761  call    cs:__imp_CoTaskMemFree
0x180063767  mov     qword ptr [rbx], 0
0x18006376e  mov     qword ptr [rbx+8], 0
0x180063776  add     rsp, 20h
0x18006377a  pop     rbx
0x18006377b  retn
```
