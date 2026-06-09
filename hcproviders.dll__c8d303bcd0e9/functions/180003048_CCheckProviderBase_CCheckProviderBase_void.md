# CCheckProviderBase::~CCheckProviderBase(void)

- ea: `0x180003048`
- end: `0x18000307e`
- name: `??1CCheckProviderBase@@MEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CCheckProviderBase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003010`

## callees

- `0x180003090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003064`

## pseudocode

```c
void __fastcall CCheckProviderBase::~CCheckProviderBase(LPVOID *this)
{
  *this = &CCheckProviderBase::`vftable';
  CCheckProviderBase::_ReleaseCheckCollection((CCheckProviderBase *)this);
  CoTaskMemFree(this[2]);
  _InterlockedDecrement(&g_cLocks);
}

```

## disassembly

```asm
0x180003048  push    rbx
0x18000304a  sub     rsp, 20h
0x18000304e  lea     rax, ??_7CCheckProviderBase@@6B@; const CCheckProviderBase::`vftable'
0x180003055  mov     rbx, rcx
0x180003058  mov     [rcx], rax
0x18000305b  call    ?_ReleaseCheckCollection@CCheckProviderBase@@IEAAXXZ; CCheckProviderBase::_ReleaseCheckCollection(void)
0x180003060  mov     rcx, [rbx+10h]; pv
0x180003064  call    cs:__imp_CoTaskMemFree
0x18000306b  nop     dword ptr [rax+rax+00h]
0x180003070  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180003077  add     rsp, 20h
0x18000307b  pop     rbx
0x18000307c  retn
```
