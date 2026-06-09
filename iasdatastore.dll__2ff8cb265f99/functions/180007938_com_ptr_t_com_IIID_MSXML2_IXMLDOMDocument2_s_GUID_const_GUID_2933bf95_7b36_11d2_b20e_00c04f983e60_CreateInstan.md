# _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(_GUID const &,IUnknown *,ulong)

- ea: `0x180007938`
- end: `0x1800079f4`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `188`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800093cc`
- `0x180009af8`

## callees

- `0x180007938`
- `0x180010010`

## import_xrefs

- `ole32!OleRun` at `0x180007998`
- `ole32!OleRun` at `0x180007998`
- `ole32!CoCreateInstance` at `0x180007989`
- `ole32!CoCreateInstance` at `0x1800079df`
- `ole32!CoCreateInstance` at `0x180007989`
- `ole32!CoCreateInstance` at `0x1800079df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(
        LPVOID *ppv,
        __int64 a2,
        IUnknown *a3,
        DWORD a4)
{
  LPVOID v6; // rcx
  int result; // eax
  HRESULT v8; // ebx
  LPUNKNOWN pUnknown; // [rsp+50h] [rbp+18h] BYREF

  pUnknown = a3;
  v6 = *ppv;
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  if ( (a4 & 0x14) == 0 )
    return CoCreateInstance(
             &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
             0,
             a4,
             &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
             ppv);
  pUnknown = 0;
  result = CoCreateInstance(
             &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
             0,
             a4,
             &GUID_00000000_0000_0000_c000_000000000046,
             (LPVOID *)&pUnknown);
  if ( result < 0 )
    return result;
  v8 = OleRun(pUnknown);
  if ( v8 >= 0 )
    v8 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
           pUnknown,
           &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           ppv);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  return v8;
}

```

## disassembly

```asm
0x180007938  mov     [rsp+arg_0], rbx
0x18000793d  mov     [rsp+pUnknown], r8
0x180007942  push    rdi
0x180007943  sub     rsp, 30h
0x180007947  mov     ebx, r9d
0x18000794a  mov     rdi, rcx
0x18000794d  mov     rcx, [rcx]
0x180007950  test    rcx, rcx
0x180007953  jz      short loc_180007962
0x180007955  mov     rax, [rcx]
0x180007958  mov     rax, [rax+10h]
0x18000795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007961  nop
0x180007962  mov     r8d, ebx; dwClsContext
0x180007965  xor     edx, edx; pUnkOuter
0x180007967  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18000796e  test    bl, 14h
0x180007971  jz      short loc_1800079D3
0x180007973  mov     [rsp+38h+pUnknown], rdx
0x180007978  lea     rax, [rsp+38h+pUnknown]
0x18000797d  mov     [rsp+38h+ppv], rax; ppv
0x180007982  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180007989  call    cs:__imp_CoCreateInstance
0x18000798f  test    eax, eax
0x180007991  js      short loc_1800079E9
0x180007993  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x180007998  call    cs:__imp_OleRun
0x18000799e  mov     ebx, eax
0x1800079a0  test    eax, eax
0x1800079a2  js      short loc_1800079C0
0x1800079a4  mov     rcx, [rsp+38h+pUnknown]
0x1800079a9  mov     rax, [rcx]
0x1800079ac  mov     r8, rdi
0x1800079af  lea     rdx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x1800079b6  mov     rax, [rax]
0x1800079b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079be  mov     ebx, eax
0x1800079c0  mov     rcx, [rsp+38h+pUnknown]
0x1800079c5  mov     rax, [rcx]
0x1800079c8  mov     rax, [rax+10h]
0x1800079cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d1  jmp     short loc_1800079E7
0x1800079d3  mov     [rsp+38h+ppv], rdi; ppv
0x1800079d8  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x1800079df  call    cs:__imp_CoCreateInstance
0x1800079e5  mov     ebx, eax
0x1800079e7  mov     eax, ebx
0x1800079e9  mov     rbx, [rsp+38h+arg_0]
0x1800079ee  add     rsp, 30h
0x1800079f2  pop     rdi
0x1800079f3  retn
```
