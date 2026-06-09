# _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::CreateInstance(_GUID const &,IUnknown *,ulong)

- ea: `0x14000e620`
- end: `0x14000e6cc`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `172`
- prototype: `int __fastcall(LPVOID *ppv, __int64, IUnknown *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e768`

## callees

- `0x140004eb4`
- `0x14000e620`
- `0x140020010`

## import_xrefs

- `ole32!OleRun` at `0x14000e670`
- `ole32!OleRun` at `0x14000e670`
- `ole32!CoCreateInstance` at `0x14000e661`
- `ole32!CoCreateInstance` at `0x14000e6b7`
- `ole32!CoCreateInstance` at `0x14000e661`
- `ole32!CoCreateInstance` at `0x14000e6b7`

## pseudocode

```c
int __fastcall _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::CreateInstance(
        LPVOID *ppv,
        __int64 a2,
        IUnknown *a3,
        DWORD a4)
{
  int result; // eax
  HRESULT v7; // ebx
  LPUNKNOWN pUnknown; // [rsp+50h] [rbp+18h] BYREF

  pUnknown = a3;
  R<IObjectContext>::~R<IObjectContext>((__int64 *)ppv);
  if ( (a4 & 0x14) == 0 )
    return CoCreateInstance(
             &GUID_7c55d6a2_f584_11d2_89b2_000000000000,
             0,
             a4,
             &GUID_7c55d6a1_f584_11d2_89b2_000000000000,
             ppv);
  pUnknown = 0;
  result = CoCreateInstance(
             &GUID_7c55d6a2_f584_11d2_89b2_000000000000,
             0,
             a4,
             &GUID_00000000_0000_0000_c000_000000000046,
             (LPVOID *)&pUnknown);
  if ( result < 0 )
    return result;
  v7 = OleRun(pUnknown);
  if ( v7 >= 0 )
    v7 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
           pUnknown,
           &GUID_7c55d6a1_f584_11d2_89b2_000000000000,
           ppv);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  return v7;
}

```

## disassembly

```asm
0x14000e620  mov     [rsp+arg_0], rbx
0x14000e625  mov     [rsp+pUnknown], r8
0x14000e62a  push    rdi
0x14000e62b  sub     rsp, 30h
0x14000e62f  mov     ebx, r9d
0x14000e632  mov     rdi, rcx
0x14000e635  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000e63a  mov     r8d, ebx; dwClsContext
0x14000e63d  xor     edx, edx; pUnkOuter
0x14000e63f  lea     rcx, _GUID_7c55d6a2_f584_11d2_89b2_000000000000; rclsid
0x14000e646  test    bl, 14h
0x14000e649  jz      short loc_14000E6AB
0x14000e64b  mov     [rsp+38h+pUnknown], rdx
0x14000e650  lea     rax, [rsp+38h+pUnknown]
0x14000e655  mov     [rsp+38h+ppv], rax; ppv
0x14000e65a  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14000e661  call    cs:__imp_CoCreateInstance
0x14000e667  test    eax, eax
0x14000e669  js      short loc_14000E6C1
0x14000e66b  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x14000e670  call    cs:__imp_OleRun
0x14000e676  mov     ebx, eax
0x14000e678  test    eax, eax
0x14000e67a  js      short loc_14000E698
0x14000e67c  mov     rcx, [rsp+38h+pUnknown]
0x14000e681  mov     rax, [rcx]
0x14000e684  mov     r8, rdi
0x14000e687  lea     rdx, _GUID_7c55d6a1_f584_11d2_89b2_000000000000
0x14000e68e  mov     rax, [rax]
0x14000e691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e696  mov     ebx, eax
0x14000e698  mov     rcx, [rsp+38h+pUnknown]
0x14000e69d  mov     rax, [rcx]
0x14000e6a0  mov     rax, [rax+10h]
0x14000e6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6a9  jmp     short loc_14000E6BF
0x14000e6ab  mov     [rsp+38h+ppv], rdi; ppv
0x14000e6b0  lea     r9, _GUID_7c55d6a1_f584_11d2_89b2_000000000000; riid
0x14000e6b7  call    cs:__imp_CoCreateInstance
0x14000e6bd  mov     ebx, eax
0x14000e6bf  mov     eax, ebx
0x14000e6c1  mov     rbx, [rsp+38h+arg_0]
0x14000e6c6  add     rsp, 30h
0x14000e6ca  pop     rdi
0x14000e6cb  retn
```
