# CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)

- ea: `0x180007f04`
- end: `0x180007f38`
- name: `??1CConfigServiceProvider2Impl@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006130`
- `0x180007f40`

## callees

- `0x180007f04`
- `0x18000e010`

## pseudocode

```c
void __fastcall CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(CConfigServiceProvider2Impl *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'};
  *((_QWORD *)this + 1) = &CProvisioningCommandsCSP::`vftable'{for `ICSPValidate'};
  v1 = *((_QWORD *)this + 2);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180007f04  sub     rsp, 28h
0x180007f08  lea     rax, ??_7CConfigServiceProvider2Impl@@6BIConfigServiceProvider2@@@; const CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'}
0x180007f0f  mov     [rcx], rax
0x180007f12  lea     rax, ??_7CProvisioningCommandsCSP@@6BICSPValidate@@@; const CProvisioningCommandsCSP::`vftable'{for `ICSPValidate'}
0x180007f19  mov     [rcx+8], rax
0x180007f1d  mov     rcx, [rcx+10h]
0x180007f21  test    rcx, rcx
0x180007f24  jz      short loc_180007F33
0x180007f26  mov     rax, [rcx]
0x180007f29  mov     rax, [rax+10h]
0x180007f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f32  nop
0x180007f33  add     rsp, 28h
0x180007f37  retn
```
