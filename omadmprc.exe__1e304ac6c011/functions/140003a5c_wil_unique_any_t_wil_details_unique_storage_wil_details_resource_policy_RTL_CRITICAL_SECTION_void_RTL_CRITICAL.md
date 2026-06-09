# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)

- ea: `0x140003a5c`
- end: `0x140003a7a`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015d57`
- `0x140015e13`
- `0x140016023`
- `0x14001606a`
- `0x14001607c`

## callees

- `0x140003a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003a68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003a68`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  v1 = *a1;
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x140003a5c  sub     rsp, 28h
0x140003a60  mov     rcx, [rcx]; lpCriticalSection
0x140003a63  test    rcx, rcx
0x140003a66  jz      short loc_140003A74
0x140003a68  call    cs:__imp_LeaveCriticalSection
0x140003a6f  nop     dword ptr [rax+rax+00h]
0x140003a74  add     rsp, 28h
0x140003a78  retn
```
