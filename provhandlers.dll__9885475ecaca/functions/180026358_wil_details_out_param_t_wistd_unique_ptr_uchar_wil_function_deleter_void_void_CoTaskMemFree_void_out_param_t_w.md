# wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x180026358`
- end: `0x180026382`
- name: `??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d089`
- `0x18003d0ff`

## callees

- `0x180026358`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026377`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x180026358  sub     rsp, 28h
0x18002635c  cmp     byte ptr [rcx+10h], 0
0x180026360  jz      short loc_18002637D
0x180026362  mov     rdx, [rcx]
0x180026365  mov     rax, [rcx+8]
0x180026369  mov     r8, [rdx]
0x18002636c  mov     [rdx], rax
0x18002636f  test    r8, r8
0x180026372  jz      short loc_18002637D
0x180026374  mov     rcx, r8; pv
0x180026377  call    cs:__imp_CoTaskMemFree
0x18002637d  add     rsp, 28h
0x180026381  retn
```
