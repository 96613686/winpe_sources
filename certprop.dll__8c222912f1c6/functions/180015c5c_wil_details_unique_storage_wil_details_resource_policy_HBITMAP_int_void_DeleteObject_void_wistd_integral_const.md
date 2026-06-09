# wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(void)

- ea: `0x180015c5c`
- end: `0x180015c73`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015c50`

## callees

- `0x180015c5c`

## import_xrefs

- `GDI32!DeleteObject` at `0x180015c68`
- `GDI32!DeleteObject` at `0x180015c68`

## pseudocode

```c
BOOL __fastcall wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return DeleteObject(v1);
  return result;
}

```

## disassembly

```asm
0x180015c5c  sub     rsp, 28h
0x180015c60  mov     rcx, [rcx]; ho
0x180015c63  test    rcx, rcx
0x180015c66  jz      short loc_180015C6E
0x180015c68  call    cs:__imp_DeleteObject
0x180015c6e  add     rsp, 28h
0x180015c72  retn
```
