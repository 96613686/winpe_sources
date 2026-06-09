# _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::CreateInstance(_GUID const &,IUnknown *,ulong)

- ea: `0x1400083b0`
- end: `0x14000845c`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `172`
- prototype: `int __fastcall(LPVOID *ppv, __int64, IUnknown *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000858c`

## callees

- `0x140004eb4`
- `0x1400083b0`
- `0x140020010`

## import_xrefs

- `ole32!OleRun` at `0x140008400`
- `ole32!OleRun` at `0x140008400`
- `ole32!CoCreateInstance` at `0x1400083f1`
- `ole32!CoCreateInstance` at `0x140008447`
- `ole32!CoCreateInstance` at `0x1400083f1`
- `ole32!CoCreateInstance` at `0x140008447`

## pseudocode

```c
int __fastcall _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::CreateInstance(
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
             &GUID_07f19952_ab28_11d2_8936_000000000000,
             0,
             a4,
             &GUID_07f19951_ab28_11d2_8936_000000000000,
             ppv);
  pUnknown = 0;
  result = CoCreateInstance(
             &GUID_07f19952_ab28_11d2_8936_000000000000,
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
           &GUID_07f19951_ab28_11d2_8936_000000000000,
           ppv);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  return v7;
}

```

## disassembly

```asm
0x1400083b0  mov     [rsp+arg_0], rbx
0x1400083b5  mov     [rsp+pUnknown], r8
0x1400083ba  push    rdi
0x1400083bb  sub     rsp, 30h
0x1400083bf  mov     ebx, r9d
0x1400083c2  mov     rdi, rcx
0x1400083c5  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x1400083ca  mov     r8d, ebx; dwClsContext
0x1400083cd  xor     edx, edx; pUnkOuter
0x1400083cf  lea     rcx, _GUID_07f19952_ab28_11d2_8936_000000000000; rclsid
0x1400083d6  test    bl, 14h
0x1400083d9  jz      short loc_14000843B
0x1400083db  mov     [rsp+38h+pUnknown], rdx
0x1400083e0  lea     rax, [rsp+38h+pUnknown]
0x1400083e5  mov     [rsp+38h+ppv], rax; ppv
0x1400083ea  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1400083f1  call    cs:__imp_CoCreateInstance
0x1400083f7  test    eax, eax
0x1400083f9  js      short loc_140008451
0x1400083fb  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x140008400  call    cs:__imp_OleRun
0x140008406  mov     ebx, eax
0x140008408  test    eax, eax
0x14000840a  js      short loc_140008428
0x14000840c  mov     rcx, [rsp+38h+pUnknown]
0x140008411  mov     rax, [rcx]
0x140008414  mov     r8, rdi
0x140008417  lea     rdx, _GUID_07f19951_ab28_11d2_8936_000000000000
0x14000841e  mov     rax, [rax]
0x140008421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008426  mov     ebx, eax
0x140008428  mov     rcx, [rsp+38h+pUnknown]
0x14000842d  mov     rax, [rcx]
0x140008430  mov     rax, [rax+10h]
0x140008434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008439  jmp     short loc_14000844F
0x14000843b  mov     [rsp+38h+ppv], rdi; ppv
0x140008440  lea     r9, _GUID_07f19951_ab28_11d2_8936_000000000000; riid
0x140008447  call    cs:__imp_CoCreateInstance
0x14000844d  mov     ebx, eax
0x14000844f  mov     eax, ebx
0x140008451  mov     rbx, [rsp+38h+arg_0]
0x140008456  add     rsp, 30h
0x14000845a  pop     rdi
0x14000845b  retn
```
