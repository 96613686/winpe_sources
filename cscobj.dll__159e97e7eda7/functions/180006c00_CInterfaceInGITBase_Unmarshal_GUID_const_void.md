# CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)

- ea: `0x180006c00`
- end: `0x180006cea`
- name: `?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `234`
- prototype: `__int64 __fastcall(CInterfaceInGITBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `35`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006b00`
- `0x1800089f0`
- `0x18000d0a0`
- `0x18000d270`
- `0x18000d2e0`
- `0x18000d530`
- `0x18000d680`
- `0x18000d870`
- `0x18000d920`
- `0x18000d9c0`
- `0x18000da40`
- `0x18000dab0`
- `0x18000db30`
- `0x18000dd80`
- `0x18000de80`
- `0x18000e0a0`
- `0x18000e270`
- `0x18000e650`
- `0x18000e710`
- `0x18000e990`
- `0x18000ea60`
- `0x18000ec70`
- `0x18000f170`
- `0x18000f3c0`
- `0x180011570`
- `0x180014c20`
- `0x180014ed0`
- `0x180023c40`
- `0x180024020`
- `0x180024650`
- `0x1800249d0`
- `0x180024c80`
- `0x180024f40`
- `0x180025700`
- `0x180026470`

## callees

- `0x180006c00`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c82`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c82`

## pseudocode

```c
__int64 __fastcall CInterfaceInGITBase::_Unmarshal(CInterfaceInGITBase *this, const struct _GUID *a2, void **a3)
{
  _QWORD *v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // ebp
  HRESULT v9; // ebx
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v6 = (_QWORD *)*((_QWORD *)this + 1);
  v7 = *(_QWORD *)&a2->Data1 - *v6;
  if ( *(_QWORD *)&a2->Data1 == *v6 )
    v7 = *(_QWORD *)a2->Data4 - v6[1];
  if ( v7 )
    return 2147500034LL;
  v8 = *((_DWORD *)this + 4);
  if ( !v8 )
    return 2147500034LL;
  ppv = 0;
  v9 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *, void **))(*(_QWORD *)ppv + 40LL))(
           ppv,
           v8,
           a2,
           a3);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006c00  mov     [rsp+arg_18], rsi
0x180006c05  push    rdi
0x180006c06  sub     rsp, 30h
0x180006c0a  mov     rdi, r8
0x180006c0d  mov     rsi, rdx
0x180006c10  test    r8, r8
0x180006c13  jnz     short loc_180006C25
0x180006c15  mov     eax, 80070057h
0x180006c1a  mov     rsi, [rsp+38h+arg_18]
0x180006c1f  add     rsp, 30h
0x180006c23  pop     rdi
0x180006c24  retn
0x180006c25  xor     r8d, r8d
0x180006c28  mov     [rdi], r8
0x180006c2b  mov     rdx, [rcx+8]
0x180006c2f  mov     rax, [rsi]
0x180006c32  sub     rax, [rdx]
0x180006c35  jnz     short loc_180006C3F
0x180006c37  mov     rax, [rsi+8]
0x180006c3b  sub     rax, [rdx+8]
0x180006c3f  test    rax, rax
0x180006c42  jnz     loc_180006CCB
0x180006c48  mov     [rsp+38h+arg_8], rbp
0x180006c4d  mov     ebp, [rcx+10h]
0x180006c50  test    ebp, ebp
0x180006c52  jz      loc_180006CDB
0x180006c58  mov     [rsp+38h+arg_10], r8
0x180006c5d  lea     rax, [rsp+38h+arg_10]
0x180006c62  mov     r8d, 1; dwClsContext
0x180006c68  mov     [rsp+38h+ppv], rax; ppv
0x180006c6d  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006c74  mov     [rsp+38h+arg_0], rbx
0x180006c79  xor     edx, edx; pUnkOuter
0x180006c7b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006c82  call    cs:__imp_CoCreateInstance
0x180006c88  mov     ebx, eax
0x180006c8a  test    eax, eax
0x180006c8c  js      short loc_180006CBA
0x180006c8e  mov     rcx, [rsp+38h+arg_10]
0x180006c93  mov     r9, rdi
0x180006c96  mov     r8, rsi
0x180006c99  mov     edx, ebp
0x180006c9b  mov     rax, [rcx]
0x180006c9e  mov     rax, [rax+28h]
0x180006ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca7  mov     rcx, [rsp+38h+arg_10]
0x180006cac  mov     ebx, eax
0x180006cae  mov     rax, [rcx]
0x180006cb1  mov     rax, [rax+10h]
0x180006cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cba  mov     rbp, [rsp+38h+arg_8]
0x180006cbf  mov     eax, ebx
0x180006cc1  mov     rbx, [rsp+38h+arg_0]
0x180006cc6  jmp     loc_180006C1A
0x180006ccb  mov     rsi, [rsp+38h+arg_18]
0x180006cd0  mov     eax, 80004002h
0x180006cd5  add     rsp, 30h
0x180006cd9  pop     rdi
0x180006cda  retn
0x180006cdb  mov     rbp, [rsp+38h+arg_8]
0x180006ce0  mov     eax, 80004002h
0x180006ce5  jmp     loc_180006C1A
```
