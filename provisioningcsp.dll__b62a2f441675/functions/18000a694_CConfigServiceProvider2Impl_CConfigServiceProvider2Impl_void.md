# CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)

- ea: `0x18000a694`
- end: `0x18000a6c9`
- name: `??1CConfigServiceProvider2Impl@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800048d4`
- `0x180007b18`
- `0x18000a6d0`

## callees

- `0x18000a694`
- `0x180038010`

## pseudocode

```c
void __fastcall CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(CConfigServiceProvider2Impl *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'};
  *((_QWORD *)this + 1) = &TenantLockdownCsp::`vftable'{for `ICSPValidate'};
  v1 = *((_QWORD *)this + 2);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000a694  sub     rsp, 28h
0x18000a698  lea     rax, ??_7CConfigServiceProvider2Impl@@6BIConfigServiceProvider2@@@; const CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'}
0x18000a69f  mov     [rcx], rax
0x18000a6a2  lea     rax, ??_7TenantLockdownCsp@@6BICSPValidate@@@; const TenantLockdownCsp::`vftable'{for `ICSPValidate'}
0x18000a6a9  mov     [rcx+8], rax
0x18000a6ad  mov     rcx, [rcx+10h]
0x18000a6b1  test    rcx, rcx
0x18000a6b4  jz      short loc_18000A6C3
0x18000a6b6  mov     rax, [rcx]
0x18000a6b9  mov     rax, [rax+10h]
0x18000a6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c2  nop
0x18000a6c3  add     rsp, 28h
0x18000a6c7  retn
```
