# _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(_GUID const &,IUnknown *,ulong)

- ea: `0x140008464`
- end: `0x140008519`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `181`
- prototype: `int __fastcall(LPVOID *ppv, IID *rclsid, IUnknown *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140008520`

## callees

- `0x140004eb4`
- `0x140008464`
- `0x140020010`

## import_xrefs

- `ole32!OleRun` at `0x1400084b8`
- `ole32!OleRun` at `0x1400084b8`
- `ole32!CoCreateInstance` at `0x1400084a9`
- `ole32!CoCreateInstance` at `0x1400084ff`
- `ole32!CoCreateInstance` at `0x1400084a9`
- `ole32!CoCreateInstance` at `0x1400084ff`

## pseudocode

```c
int __fastcall _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(
        LPVOID *ppv,
        IID *rclsid,
        IUnknown *a3,
        DWORD a4)
{
  int result; // eax
  HRESULT v8; // ebx
  LPUNKNOWN pUnknown; // [rsp+50h] [rbp+18h] BYREF

  pUnknown = a3;
  R<IObjectContext>::~R<IObjectContext>((__int64 *)ppv);
  if ( (a4 & 0x14) == 0 )
    return CoCreateInstance(rclsid, 0, a4, &GUID_b0cdbf11_9774_11d2_8929_000000000000, ppv);
  pUnknown = 0;
  result = CoCreateInstance(rclsid, 0, a4, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&pUnknown);
  if ( result < 0 )
    return result;
  v8 = OleRun(pUnknown);
  if ( v8 >= 0 )
    v8 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
           pUnknown,
           &GUID_b0cdbf11_9774_11d2_8929_000000000000,
           ppv);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  return v8;
}

```

## disassembly

```asm
0x140008464  mov     [rsp+arg_0], rbx
0x140008469  mov     [rsp+arg_8], rsi
0x14000846e  mov     [rsp+pUnknown], r8
0x140008473  push    rdi
0x140008474  sub     rsp, 30h
0x140008478  mov     ebx, r9d
0x14000847b  mov     rsi, rdx
0x14000847e  mov     rdi, rcx
0x140008481  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x140008486  mov     r8d, ebx; dwClsContext
0x140008489  xor     edx, edx; pUnkOuter
0x14000848b  mov     rcx, rsi; rclsid
0x14000848e  test    bl, 14h
0x140008491  jz      short loc_1400084F3
0x140008493  mov     [rsp+38h+pUnknown], rdx
0x140008498  lea     rax, [rsp+38h+pUnknown]
0x14000849d  mov     [rsp+38h+ppv], rax; ppv
0x1400084a2  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1400084a9  call    cs:__imp_CoCreateInstance
0x1400084af  test    eax, eax
0x1400084b1  js      short loc_140008509
0x1400084b3  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x1400084b8  call    cs:__imp_OleRun
0x1400084be  mov     ebx, eax
0x1400084c0  test    eax, eax
0x1400084c2  js      short loc_1400084E0
0x1400084c4  mov     rcx, [rsp+38h+pUnknown]
0x1400084c9  mov     rax, [rcx]
0x1400084cc  mov     r8, rdi
0x1400084cf  lea     rdx, _GUID_b0cdbf11_9774_11d2_8929_000000000000
0x1400084d6  mov     rax, [rax]
0x1400084d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084de  mov     ebx, eax
0x1400084e0  mov     rcx, [rsp+38h+pUnknown]
0x1400084e5  mov     rax, [rcx]
0x1400084e8  mov     rax, [rax+10h]
0x1400084ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084f1  jmp     short loc_140008507
0x1400084f3  mov     [rsp+38h+ppv], rdi; ppv
0x1400084f8  lea     r9, _GUID_b0cdbf11_9774_11d2_8929_000000000000; riid
0x1400084ff  call    cs:__imp_CoCreateInstance
0x140008505  mov     ebx, eax
0x140008507  mov     eax, ebx
0x140008509  mov     rbx, [rsp+38h+arg_0]
0x14000850e  mov     rsi, [rsp+38h+arg_8]
0x140008513  add     rsp, 30h
0x140008517  pop     rdi
0x140008518  retn
```
