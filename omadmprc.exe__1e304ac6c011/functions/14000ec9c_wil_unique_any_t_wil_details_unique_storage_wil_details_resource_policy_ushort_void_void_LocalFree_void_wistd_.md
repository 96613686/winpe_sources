# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x14000ec9c`
- end: `0x14000ecba`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015def`
- `0x140015e49`
- `0x140015e5b`
- `0x140015e6d`
- `0x140015e91`
- `0x140015eeb`

## callees

- `0x14000ec9c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000eca8`

## pseudocode

```c
HLOCAL __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
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
0x14000ec9c  sub     rsp, 28h
0x14000eca0  mov     rcx, [rcx]; hMem
0x14000eca3  test    rcx, rcx
0x14000eca6  jz      short loc_14000ECB4
0x14000eca8  call    cs:__imp_LocalFree
0x14000ecaf  nop     dword ptr [rax+rax+00h]
0x14000ecb4  add     rsp, 28h
0x14000ecb8  retn
```
