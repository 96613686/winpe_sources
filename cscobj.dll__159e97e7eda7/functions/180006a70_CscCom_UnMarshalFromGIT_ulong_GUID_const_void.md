# CscCom_UnMarshalFromGIT(ulong,_GUID const &,void * *)

- ea: `0x180006a70`
- end: `0x180006af9`
- name: `?CscCom_UnMarshalFromGIT@@YAJKAEBU_GUID@@PEAPEAX@Z`
- size: `137`
- prototype: `__int64 __fastcall(unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009160`
- `0x180009280`

## callees

- `0x180006a70`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ab1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ab1`

## pseudocode

```c
HRESULT __fastcall CscCom_UnMarshalFromGIT(unsigned int a1, const struct _GUID *a2, void **a3)
{
  HRESULT result; // eax
  int v7; // ebx
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  ppv = 0;
  result = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  if ( result >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *, void **))(*(_QWORD *)ppv + 40LL))(
           ppv,
           a1,
           a2,
           a3);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180006a70  mov     [rsp+arg_0], rbx
0x180006a75  mov     [rsp+arg_8], rsi
0x180006a7a  push    rdi
0x180006a7b  sub     rsp, 30h
0x180006a7f  xor     eax, eax
0x180006a81  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006a88  mov     [r8], rax
0x180006a8b  mov     rbx, r8
0x180006a8e  mov     [rsp+38h+arg_10], rax
0x180006a93  mov     rdi, rdx
0x180006a96  lea     rax, [rsp+38h+arg_10]
0x180006a9b  mov     esi, ecx
0x180006a9d  xor     edx, edx; pUnkOuter
0x180006a9f  mov     [rsp+38h+ppv], rax; ppv
0x180006aa4  mov     r8d, 1; dwClsContext
0x180006aaa  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006ab1  call    cs:__imp_CoCreateInstance
0x180006ab7  test    eax, eax
0x180006ab9  js      short loc_180006AE9
0x180006abb  mov     rcx, [rsp+38h+arg_10]
0x180006ac0  mov     r9, rbx
0x180006ac3  mov     r8, rdi
0x180006ac6  mov     edx, esi
0x180006ac8  mov     rax, [rcx]
0x180006acb  mov     rax, [rax+28h]
0x180006acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad4  mov     rcx, [rsp+38h+arg_10]
0x180006ad9  mov     ebx, eax
0x180006adb  mov     rdx, [rcx]
0x180006ade  mov     rax, [rdx+10h]
0x180006ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae7  mov     eax, ebx
0x180006ae9  mov     rbx, [rsp+38h+arg_0]
0x180006aee  mov     rsi, [rsp+38h+arg_8]
0x180006af3  add     rsp, 30h
0x180006af7  pop     rdi
0x180006af8  retn
```
