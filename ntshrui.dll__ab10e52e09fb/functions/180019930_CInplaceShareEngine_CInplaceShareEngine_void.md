# CInplaceShareEngine::~CInplaceShareEngine(void)

- ea: `0x180019930`
- end: `0x1800199f9`
- name: `??1CInplaceShareEngine@@EEAA@XZ`
- size: `201`
- prototype: `void __fastcall(CInplaceShareEngine *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800198f4`

## callees

- `0x180019930`
- `0x180019a00`
- `0x180019a64`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001999e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001999e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199f1`

## pseudocode

```c
void __fastcall CInplaceShareEngine::~CInplaceShareEngine(CInplaceShareEngine *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  unsigned int v4; // edx
  CDefaultAclCache *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CInplaceShareEngine::`vftable'{for `IShareEngine'};
  *((_QWORD *)this + 1) = &CInplaceShareEngine::`vftable'{for `IInplaceShareEngine'};
  *((_QWORD *)this + 2) = &CInplaceShareEngine::`vftable'{for `CFolderAclEngine'};
  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  LocalFree(*((HLOCAL *)this + 207));
  v5 = (CDefaultAclCache *)*((_QWORD *)this + 209);
  if ( v5 )
    CDefaultAclCache::`scalar deleting destructor'(v5, v4);
  _InterlockedDecrement(&g_cRefThisDll);
  v6 = (void *)*((_QWORD *)this + 205);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 204);
  if ( v7 )
    CoTaskMemFree(v7);
  CFolderAclEngine::~CFolderAclEngine((CInplaceShareEngine *)((char *)this + 16));
}

```

## disassembly

```asm
0x180019930  mov     [rsp+arg_0], rbx
0x180019935  push    rdi
0x180019936  sub     rsp, 20h
0x18001993a  mov     rbx, rcx
0x18001993d  lea     rax, ??_7CInplaceShareEngine@@6BIShareEngine@@@; const CInplaceShareEngine::`vftable'{for `IShareEngine'}
0x180019944  mov     [rcx], rax
0x180019947  lea     rax, ??_7CInplaceShareEngine@@6BIInplaceShareEngine@@@; const CInplaceShareEngine::`vftable'{for `IInplaceShareEngine'}
0x18001994e  mov     [rcx+8], rax
0x180019952  lea     rax, ??_7CInplaceShareEngine@@6BCFolderAclEngine@@@; const CInplaceShareEngine::`vftable'{for `CFolderAclEngine'}
0x180019959  mov     [rcx+10h], rax
0x18001995d  mov     rcx, [rcx+38h]
0x180019961  mov     qword ptr [rbx+38h], 0
0x180019969  test    rcx, rcx
0x18001996c  jz      short loc_18001997A
0x18001996e  mov     rax, [rcx]
0x180019971  mov     rax, [rax+10h]
0x180019975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001997a  mov     rcx, [rbx+40h]
0x18001997e  mov     qword ptr [rbx+40h], 0
0x180019986  test    rcx, rcx
0x180019989  jz      short loc_180019997
0x18001998b  mov     rax, [rcx]
0x18001998e  mov     rax, [rax+10h]
0x180019992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019997  mov     rcx, [rbx+678h]; hMem
0x18001999e  call    cs:__imp_LocalFree
0x1800199a4  mov     rcx, [rbx+688h]; this
0x1800199ab  test    rcx, rcx
0x1800199ae  jnz     short loc_1800199E2
0x1800199b0  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800199b7  mov     rcx, [rbx+668h]; pv
0x1800199be  test    rcx, rcx
0x1800199c1  jnz     short loc_1800199E9
0x1800199c3  mov     rcx, [rbx+660h]; pv
0x1800199ca  test    rcx, rcx
0x1800199cd  jnz     short loc_1800199F1
0x1800199cf  lea     rcx, [rbx+10h]; this
0x1800199d3  mov     rbx, [rsp+28h+arg_0]
0x1800199d8  add     rsp, 20h
0x1800199dc  pop     rdi
0x1800199dd  jmp     ??1CFolderAclEngine@@MEAA@XZ; CFolderAclEngine::~CFolderAclEngine(void)
0x1800199e2  call    ??_GCDefaultAclCache@@QEAAPEAXI@Z; CDefaultAclCache::`scalar deleting destructor'(uint)
0x1800199e7  jmp     short loc_1800199B0
0x1800199e9  call    cs:__imp_CoTaskMemFree
0x1800199ef  jmp     short loc_1800199C3
0x1800199f1  call    cs:__imp_CoTaskMemFree
0x1800199f7  jmp     short loc_1800199CF
```
