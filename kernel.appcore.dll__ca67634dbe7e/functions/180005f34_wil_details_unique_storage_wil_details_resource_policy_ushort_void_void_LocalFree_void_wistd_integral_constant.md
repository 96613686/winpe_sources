# wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x180005f34`
- end: `0x180005f4b`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005e44`
- `0x180005f54`

## callees

- `0x180005f34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f40`

## pseudocode

```c
HLOCAL __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( v1 )
    return LocalFree(v1);
  return result;
}

```

## disassembly

```asm
0x180005f34  sub     rsp, 28h
0x180005f38  mov     rcx, [rcx]; hMem
0x180005f3b  test    rcx, rcx
0x180005f3e  jz      short loc_180005F46
0x180005f40  call    cs:__imp_LocalFree
0x180005f46  add     rsp, 28h
0x180005f4a  retn
```
