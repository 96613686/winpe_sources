# CLocalizedHidTextSet::~CLocalizedHidTextSet(void)

- ea: `0x18000b7b8`
- end: `0x18000b80a`
- name: `??1CLocalizedHidTextSet@@EEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CLocalizedHidTextSet *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b9e0`

## callees

- `0x18000b68c`
- `0x18000b6b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7ee`

## pseudocode

```c
void __fastcall CLocalizedHidTextSet::~CLocalizedHidTextSet(CLocalizedHidTextSet *this)
{
  *(_QWORD *)this = &CLocalizedHidTextSet::`vftable'{for `CItem'};
  *((_QWORD *)this + 3) = &CLocalizedHidTextSet::`vftable'{for `IOOBELocalizedHidAccItem'};
  CoTaskMemFree(*((LPVOID *)this + 6));
  CoTaskMemFree(*((LPVOID *)this + 7));
  CoTaskMemFree(*((LPVOID *)this + 8));
  wil::com_ptr_t<ISpObjectToken,wil::err_returncode_policy>::~com_ptr_t<ISpObjectToken,wil::err_returncode_policy>((char *)this + 32);
  CItem::~CItem(this);
}

```

## disassembly

```asm
0x18000b7b8  push    rbx
0x18000b7ba  sub     rsp, 20h
0x18000b7be  lea     rax, ??_7CLocalizedHidTextSet@@6BCItem@@@; const CLocalizedHidTextSet::`vftable'{for `CItem'}
0x18000b7c5  mov     rbx, rcx
0x18000b7c8  mov     [rcx], rax
0x18000b7cb  lea     rax, ??_7CLocalizedHidTextSet@@6BIOOBELocalizedHidAccItem@@@; const CLocalizedHidTextSet::`vftable'{for `IOOBELocalizedHidAccItem'}
0x18000b7d2  mov     [rcx+18h], rax
0x18000b7d6  mov     rcx, [rcx+30h]; pv
0x18000b7da  call    cs:__imp_CoTaskMemFree
0x18000b7e0  mov     rcx, [rbx+38h]; pv
0x18000b7e4  call    cs:__imp_CoTaskMemFree
0x18000b7ea  mov     rcx, [rbx+40h]; pv
0x18000b7ee  call    cs:__imp_CoTaskMemFree
0x18000b7f4  lea     rcx, [rbx+20h]
0x18000b7f8  call    ??1?$com_ptr_t@UISpObjectToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISpObjectToken,wil::err_returncode_policy>::~com_ptr_t<ISpObjectToken,wil::err_returncode_policy>(void)
0x18000b7fd  mov     rcx, rbx; this
0x18000b800  add     rsp, 20h
0x18000b804  pop     rbx
0x18000b805  jmp     ??1CItem@@MEAA@XZ; CItem::~CItem(void)
```
