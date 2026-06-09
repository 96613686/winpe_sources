# wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)

- ea: `0x180067188`
- end: `0x1800671bb`
- name: `?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800662b0`
- `0x1800671c4`

## callees

- `0x180067188`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067199`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067199`

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
0x180067188  push    rbx
0x18006718a  sub     rsp, 20h
0x18006718e  mov     rbx, rcx
0x180067191  mov     rcx, [rcx]; pv
0x180067194  test    rcx, rcx
0x180067197  jz      short loc_1800671B4
0x180067199  call    cs:__imp_CoTaskMemFree
0x1800671a0  nop     dword ptr [rax+rax+00h]
0x1800671a5  mov     qword ptr [rbx], 0
0x1800671ac  mov     qword ptr [rbx+8], 0
0x1800671b4  add     rsp, 20h
0x1800671b8  pop     rbx
0x1800671b9  retn
```
