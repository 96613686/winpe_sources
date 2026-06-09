# CInterfaceInGITBase::_Marshal(_GUID const &,IUnknown *)

- ea: `0x180006500`
- end: `0x1800065ee`
- name: `?_Marshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CInterfaceInGITBase *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008e54`
- `0x18000cc68`
- `0x180014b90`
- `0x180025400`

## callees

- `0x180006500`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000657a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000657a`

## pseudocode

```c
__int64 __fastcall CInterfaceInGITBase::_Marshal(
        CInterfaceInGITBase *this,
        const struct _GUID *a2,
        struct IUnknown *a3)
{
  _QWORD *v5; // rdx
  __int64 v6; // rax
  _DWORD *v7; // rdi
  HRESULT v8; // ebx
  __int64 result; // rax
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  v5 = (_QWORD *)*((_QWORD *)this + 1);
  v6 = *(_QWORD *)&a2->Data1 - *v5;
  if ( *(_QWORD *)&a2->Data1 == *v5 )
    v6 = *(_QWORD *)a2->Data4 - v5[1];
  if ( v6 )
    return 2147500034LL;
  v7 = (_DWORD *)((char *)this + 16);
  if ( *((_DWORD *)this + 4) )
    return 2147500037LL;
  *v7 = 0;
  ppv = 0;
  v8 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, const struct _GUID *, _DWORD *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           a3,
           a2,
           v7);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  result = (unsigned int)v8;
  if ( v8 < 0 )
    *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180006500  push    rbp
0x180006502  push    rsi
0x180006503  sub     rsp, 38h
0x180006507  mov     rbp, r8
0x18000650a  mov     rsi, rdx
0x18000650d  test    r8, r8
0x180006510  jz      loc_1800065E7
0x180006516  mov     rdx, [rcx+8]
0x18000651a  mov     rax, [rsi]
0x18000651d  sub     rax, [rdx]
0x180006520  jnz     short loc_18000652A
0x180006522  mov     rax, [rsi+8]
0x180006526  sub     rax, [rdx+8]
0x18000652a  test    rax, rax
0x18000652d  jnz     loc_1800065CF
0x180006533  cmp     [rcx+10h], eax
0x180006536  mov     [rsp+48h+arg_8], rdi
0x18000653b  lea     rdi, [rcx+10h]
0x18000653f  jnz     loc_1800065DB
0x180006545  lea     rax, [rsp+48h+arg_10]
0x18000654a  mov     [rsp+48h+arg_0], rbx
0x18000654f  mov     [rsp+48h+var_18], r14
0x180006554  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000655b  xor     r14d, r14d
0x18000655e  mov     [rsp+48h+ppv], rax; ppv
0x180006563  xor     edx, edx; pUnkOuter
0x180006565  mov     [rdi], r14d
0x180006568  mov     r8d, 1; dwClsContext
0x18000656e  mov     [rsp+48h+arg_10], r14
0x180006573  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000657a  call    cs:__imp_CoCreateInstance
0x180006580  mov     ebx, eax
0x180006582  test    eax, eax
0x180006584  js      short loc_1800065B3
0x180006586  mov     rcx, [rsp+48h+arg_10]
0x18000658b  mov     r9, rdi
0x18000658e  mov     r8, rsi
0x180006591  mov     rdx, rbp
0x180006594  mov     rax, [rcx]
0x180006597  mov     rax, [rax+18h]
0x18000659b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a0  mov     rcx, [rsp+48h+arg_10]
0x1800065a5  mov     ebx, eax
0x1800065a7  mov     rax, [rcx]
0x1800065aa  mov     rax, [rax+10h]
0x1800065ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065b3  mov     eax, ebx
0x1800065b5  test    ebx, ebx
0x1800065b7  js      short loc_1800065E2
0x1800065b9  mov     rbx, [rsp+48h+arg_0]
0x1800065be  mov     r14, [rsp+48h+var_18]
0x1800065c3  mov     rdi, [rsp+48h+arg_8]
0x1800065c8  add     rsp, 38h
0x1800065cc  pop     rsi
0x1800065cd  pop     rbp
0x1800065ce  retn
0x1800065cf  mov     eax, 80004002h
0x1800065d4  add     rsp, 38h
0x1800065d8  pop     rsi
0x1800065d9  pop     rbp
0x1800065da  retn
0x1800065db  mov     eax, 80004005h
0x1800065e0  jmp     short loc_1800065C3
0x1800065e2  mov     [rdi], r14d
0x1800065e5  jmp     short loc_1800065B9
0x1800065e7  mov     eax, 80070057h
0x1800065ec  jmp     short loc_1800065C8
```
