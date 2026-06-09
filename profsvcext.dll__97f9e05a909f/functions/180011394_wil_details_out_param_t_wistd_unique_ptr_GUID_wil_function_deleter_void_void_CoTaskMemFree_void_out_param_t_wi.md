# wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x180011394`
- end: `0x1800113bc`
- name: `??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(void ***)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007bd0`
- `0x18001e8a6`

## callees

- `0x180011394`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800113b0`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        void ***a1)
{
  void **v1; // rdx
  void **v2; // rax
  void *v3; // rcx

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = a1[1];
    v2 = *a1;
    v3 = **a1;
    *v2 = v1;
    if ( v3 )
      CoTaskMemFree(v3);
  }
}

```

## disassembly

```asm
0x180011394  sub     rsp, 28h
0x180011398  cmp     byte ptr [rcx+10h], 0
0x18001139c  jz      short loc_1800113B7
0x18001139e  mov     rdx, [rcx+8]
0x1800113a2  mov     rax, [rcx]
0x1800113a5  mov     rcx, [rax]; pv
0x1800113a8  mov     [rax], rdx
0x1800113ab  test    rcx, rcx
0x1800113ae  jz      short loc_1800113B7
0x1800113b0  call    cs:__imp_CoTaskMemFree
0x1800113b6  nop
0x1800113b7  add     rsp, 28h
0x1800113bb  retn
```
