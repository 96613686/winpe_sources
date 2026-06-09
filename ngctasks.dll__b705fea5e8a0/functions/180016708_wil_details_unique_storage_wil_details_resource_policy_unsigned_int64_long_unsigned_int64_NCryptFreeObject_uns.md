# wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)

- ea: `0x180016708`
- end: `0x180016720`
- name: `??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `24`
- prototype: `SECURITY_STATUS __fastcall(NCRYPT_HANDLE *)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800166d0`
- `0x180016850`
- `0x180016b24`
- `0x18001cff4`
- `0x18001d954`
- `0x18002097c`
- `0x1800209a0`
- `0x1800209d6`

## callees

- `0x180016708`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180016714`
- `ncrypt!NCryptFreeObject` at `0x180016714`

## pseudocode

```c
SECURITY_STATUS __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(
        NCRYPT_HANDLE *a1)
{
  NCRYPT_HANDLE v1; // rcx
  SECURITY_STATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return NCryptFreeObject(v1);
  return result;
}

```

## disassembly

```asm
0x180016708  sub     rsp, 28h
0x18001670c  mov     rcx, [rcx]; hObject
0x18001670f  test    rcx, rcx
0x180016712  jz      short loc_18001671B
0x180016714  call    cs:__imp_NCryptFreeObject
0x18001671a  nop
0x18001671b  add     rsp, 28h
0x18001671f  retn
```
