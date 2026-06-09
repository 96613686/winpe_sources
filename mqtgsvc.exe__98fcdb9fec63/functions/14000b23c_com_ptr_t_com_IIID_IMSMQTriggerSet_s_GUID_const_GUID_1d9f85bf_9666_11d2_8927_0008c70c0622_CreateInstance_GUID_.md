# _com_ptr_t<_com_IIID<IMSMQTriggerSet,&__s_GUID const _GUID_1d9f85bf_9666_11d2_8927_0008c70c0622>>::CreateInstance(_GUID const &,IUnknown *,ulong)

- ea: `0x14000b23c`
- end: `0x14000b2e8`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggerSet@@$1?_GUID_1d9f85bf_9666_11d2_8927_0008c70c0622@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `172`
- prototype: `int __fastcall(LPVOID *ppv, __int64, IUnknown *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a6dc`

## callees

- `0x140004eb4`
- `0x14000b23c`
- `0x140020010`

## import_xrefs

- `ole32!OleRun` at `0x14000b28c`
- `ole32!OleRun` at `0x14000b28c`
- `ole32!CoCreateInstance` at `0x14000b27d`
- `ole32!CoCreateInstance` at `0x14000b2d3`
- `ole32!CoCreateInstance` at `0x14000b27d`
- `ole32!CoCreateInstance` at `0x14000b2d3`

## pseudocode

```c
int __fastcall _com_ptr_t<_com_IIID<IMSMQTriggerSet,&__s_GUID const _GUID_1d9f85bf_9666_11d2_8927_0008c70c0622>>::CreateInstance(
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
             &GUID_1d9f85c0_9666_11d2_8927_0008c70c0622,
             0,
             a4,
             &GUID_1d9f85bf_9666_11d2_8927_0008c70c0622,
             ppv);
  pUnknown = 0;
  result = CoCreateInstance(
             &GUID_1d9f85c0_9666_11d2_8927_0008c70c0622,
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
           &GUID_1d9f85bf_9666_11d2_8927_0008c70c0622,
           ppv);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  return v7;
}

```

## disassembly

```asm
0x14000b23c  mov     [rsp+arg_0], rbx
0x14000b241  mov     [rsp+pUnknown], r8
0x14000b246  push    rdi
0x14000b247  sub     rsp, 30h
0x14000b24b  mov     ebx, r9d
0x14000b24e  mov     rdi, rcx
0x14000b251  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000b256  mov     r8d, ebx; dwClsContext
0x14000b259  xor     edx, edx; pUnkOuter
0x14000b25b  lea     rcx, _GUID_1d9f85c0_9666_11d2_8927_0008c70c0622; rclsid
0x14000b262  test    bl, 14h
0x14000b265  jz      short loc_14000B2C7
0x14000b267  mov     [rsp+38h+pUnknown], rdx
0x14000b26c  lea     rax, [rsp+38h+pUnknown]
0x14000b271  mov     [rsp+38h+ppv], rax; ppv
0x14000b276  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14000b27d  call    cs:__imp_CoCreateInstance
0x14000b283  test    eax, eax
0x14000b285  js      short loc_14000B2DD
0x14000b287  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x14000b28c  call    cs:__imp_OleRun
0x14000b292  mov     ebx, eax
0x14000b294  test    eax, eax
0x14000b296  js      short loc_14000B2B4
0x14000b298  mov     rcx, [rsp+38h+pUnknown]
0x14000b29d  mov     rax, [rcx]
0x14000b2a0  mov     r8, rdi
0x14000b2a3  lea     rdx, _GUID_1d9f85bf_9666_11d2_8927_0008c70c0622
0x14000b2aa  mov     rax, [rax]
0x14000b2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2b2  mov     ebx, eax
0x14000b2b4  mov     rcx, [rsp+38h+pUnknown]
0x14000b2b9  mov     rax, [rcx]
0x14000b2bc  mov     rax, [rax+10h]
0x14000b2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2c5  jmp     short loc_14000B2DB
0x14000b2c7  mov     [rsp+38h+ppv], rdi; ppv
0x14000b2cc  lea     r9, _GUID_1d9f85bf_9666_11d2_8927_0008c70c0622; riid
0x14000b2d3  call    cs:__imp_CoCreateInstance
0x14000b2d9  mov     ebx, eax
0x14000b2db  mov     eax, ebx
0x14000b2dd  mov     rbx, [rsp+38h+arg_0]
0x14000b2e2  add     rsp, 30h
0x14000b2e6  pop     rdi
0x14000b2e7  retn
```
