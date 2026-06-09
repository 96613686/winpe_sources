# _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::CreateInstance(_GUID const &,IUnknown *,ulong)

- ea: `0x14000cf50`
- end: `0x14000d005`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQQueueInfo4@@$1?_GUID_eba96b21_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `181`
- prototype: `int __fastcall(LPVOID *ppv, IID *rclsid, IUnknown *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d4a8`

## callees

- `0x140004eb4`
- `0x14000cf50`
- `0x140020010`

## import_xrefs

- `ole32!OleRun` at `0x14000cfa4`
- `ole32!OleRun` at `0x14000cfa4`
- `ole32!CoCreateInstance` at `0x14000cf95`
- `ole32!CoCreateInstance` at `0x14000cfeb`
- `ole32!CoCreateInstance` at `0x14000cf95`
- `ole32!CoCreateInstance` at `0x14000cfeb`

## pseudocode

```c
int __fastcall _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::CreateInstance(
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
    return CoCreateInstance(rclsid, 0, a4, &GUID_eba96b21_2168_11d3_898c_00e02c074f6b, ppv);
  pUnknown = 0;
  result = CoCreateInstance(rclsid, 0, a4, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&pUnknown);
  if ( result < 0 )
    return result;
  v8 = OleRun(pUnknown);
  if ( v8 >= 0 )
    v8 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
           pUnknown,
           &GUID_eba96b21_2168_11d3_898c_00e02c074f6b,
           ppv);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  return v8;
}

```

## disassembly

```asm
0x14000cf50  mov     [rsp+arg_0], rbx
0x14000cf55  mov     [rsp+arg_8], rsi
0x14000cf5a  mov     [rsp+pUnknown], r8
0x14000cf5f  push    rdi
0x14000cf60  sub     rsp, 30h
0x14000cf64  mov     ebx, r9d
0x14000cf67  mov     rsi, rdx
0x14000cf6a  mov     rdi, rcx
0x14000cf6d  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000cf72  mov     r8d, ebx; dwClsContext
0x14000cf75  xor     edx, edx; pUnkOuter
0x14000cf77  mov     rcx, rsi; rclsid
0x14000cf7a  test    bl, 14h
0x14000cf7d  jz      short loc_14000CFDF
0x14000cf7f  mov     [rsp+38h+pUnknown], rdx
0x14000cf84  lea     rax, [rsp+38h+pUnknown]
0x14000cf89  mov     [rsp+38h+ppv], rax; ppv
0x14000cf8e  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14000cf95  call    cs:__imp_CoCreateInstance
0x14000cf9b  test    eax, eax
0x14000cf9d  js      short loc_14000CFF5
0x14000cf9f  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x14000cfa4  call    cs:__imp_OleRun
0x14000cfaa  mov     ebx, eax
0x14000cfac  test    eax, eax
0x14000cfae  js      short loc_14000CFCC
0x14000cfb0  mov     rcx, [rsp+38h+pUnknown]
0x14000cfb5  mov     rax, [rcx]
0x14000cfb8  mov     r8, rdi
0x14000cfbb  lea     rdx, _GUID_eba96b21_2168_11d3_898c_00e02c074f6b
0x14000cfc2  mov     rax, [rax]
0x14000cfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cfca  mov     ebx, eax
0x14000cfcc  mov     rcx, [rsp+38h+pUnknown]
0x14000cfd1  mov     rax, [rcx]
0x14000cfd4  mov     rax, [rax+10h]
0x14000cfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cfdd  jmp     short loc_14000CFF3
0x14000cfdf  mov     [rsp+38h+ppv], rdi; ppv
0x14000cfe4  lea     r9, _GUID_eba96b21_2168_11d3_898c_00e02c074f6b; riid
0x14000cfeb  call    cs:__imp_CoCreateInstance
0x14000cff1  mov     ebx, eax
0x14000cff3  mov     eax, ebx
0x14000cff5  mov     rbx, [rsp+38h+arg_0]
0x14000cffa  mov     rsi, [rsp+38h+arg_8]
0x14000cfff  add     rsp, 30h
0x14000d003  pop     rdi
0x14000d004  retn
```
