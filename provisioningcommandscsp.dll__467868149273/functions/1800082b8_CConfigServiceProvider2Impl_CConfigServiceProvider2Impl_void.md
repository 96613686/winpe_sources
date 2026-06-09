# CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)

- ea: `0x1800082b8`
- end: `0x1800082ed`
- name: `??1CConfigServiceProvider2Impl@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006420`
- `0x180008300`

## callees

- `0x1800082b8`
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
0x1800082b8  sub     rsp, 28h
0x1800082bc  lea     rax, ??_7CConfigServiceProvider2Impl@@6BIConfigServiceProvider2@@@; const CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'}
0x1800082c3  mov     [rcx], rax
0x1800082c6  lea     rax, ??_7CProvisioningCommandsCSP@@6BICSPValidate@@@; const CProvisioningCommandsCSP::`vftable'{for `ICSPValidate'}
0x1800082cd  mov     [rcx+8], rax
0x1800082d1  mov     rcx, [rcx+10h]
0x1800082d5  test    rcx, rcx
0x1800082d8  jz      short loc_1800082E7
0x1800082da  mov     rax, [rcx]
0x1800082dd  mov     rax, [rax+10h]
0x1800082e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e6  nop
0x1800082e7  add     rsp, 28h
0x1800082eb  retn
```
