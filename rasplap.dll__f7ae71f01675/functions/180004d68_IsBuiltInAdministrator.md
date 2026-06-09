# _IsBuiltInAdministrator

- ea: `0x180004d68`
- end: `0x180004e6c`
- name: `_IsBuiltInAdministrator`
- size: `260`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800054ac`

## callees

- `0x180004d68`
- `0x18000c010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180004e23`
- `KERNEL32!CompareStringW` at `0x180004e23`
- `ole32!CoCreateInstance` at `0x180004da2`
- `ole32!CoCreateInstance` at `0x180004da2`
- `ole32!PropVariantClear` at `0x180004e35`
- `ole32!PropVariantClear` at `0x180004e35`

## pseudocode

```c
__int64 __fastcall IsBuiltInAdministrator(PCNZWCH lpString1, bool *a2)
{
  HRESULT v4; // ebx
  PCNZWCH lpString2[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v7; // [rsp+40h] [rbp-10h]
  __int64 v8; // [rsp+80h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 1u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv);
  if ( v4 >= 0 )
  {
    v8 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 80LL))(ppv, 500, &v8);
    if ( v4 >= 0 )
    {
      v7 = 0;
      *(_OWORD *)lpString2 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *, PCNZWCH *))(*(_QWORD *)v8 + 40LL))(
             v8,
             PKEY_SAM_Name,
             lpString2);
      if ( v4 >= 0 )
      {
        *a2 = CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2[1], -1) == 2;
        PropVariantClear((PROPVARIANT *)lpString2);
        v4 = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004d68  mov     [rsp-18h+arg_0], rbx
0x180004d6d  push    rbp
0x180004d6e  push    rsi
0x180004d6f  push    rdi
0x180004d70  mov     rbp, rsp
0x180004d73  sub     rsp, 50h
0x180004d77  mov     rdi, rdx
0x180004d7a  mov     [rbp+arg_18], 0
0x180004d82  xor     edx, edx; pUnkOuter
0x180004d84  lea     rax, [rbp+arg_18]
0x180004d88  mov     rsi, rcx
0x180004d8b  mov     [rsp+50h+ppv], rax; ppv
0x180004d90  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180004d97  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x180004d9e  lea     r8d, [rdx+1]; dwClsContext
0x180004da2  call    cs:__imp_CoCreateInstance
0x180004da8  mov     ebx, eax
0x180004daa  test    eax, eax
0x180004dac  js      loc_180004E5D
0x180004db2  mov     rcx, [rbp+arg_18]
0x180004db6  lea     r8, [rbp+arg_10]
0x180004dba  mov     [rbp+arg_10], 0
0x180004dc2  mov     edx, 1F4h
0x180004dc7  mov     rax, [rcx]
0x180004dca  mov     rax, [rax+50h]
0x180004dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd3  mov     ebx, eax
0x180004dd5  test    eax, eax
0x180004dd7  js      short loc_180004E4D
0x180004dd9  mov     rcx, [rbp+arg_10]
0x180004ddd  lea     r8, [rbp+lpString2]
0x180004de1  xor     eax, eax
0x180004de3  lea     rdx, PKEY_SAM_Name
0x180004dea  mov     [rbp+var_10], rax
0x180004dee  xorps   xmm0, xmm0
0x180004df1  movups  xmmword ptr [rbp+lpString2], xmm0
0x180004df5  mov     rax, [rcx]
0x180004df8  mov     rax, [rax+28h]
0x180004dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e01  mov     ebx, eax
0x180004e03  test    eax, eax
0x180004e05  js      short loc_180004E3D
0x180004e07  mov     rax, [rbp+lpString2+8]
0x180004e0b  or      r9d, 0FFFFFFFFh; cchCount1
0x180004e0f  mov     [rsp+50h+cchCount2], r9d; cchCount2
0x180004e14  mov     r8, rsi; lpString1
0x180004e17  mov     [rsp+50h+ppv], rax; lpString2
0x180004e1c  lea     edx, [r9+2]; dwCmpFlags
0x180004e20  lea     ecx, [rdx+7Eh]; Locale
0x180004e23  call    cs:__imp_CompareStringW
0x180004e29  cmp     eax, 2
0x180004e2c  lea     rcx, [rbp+lpString2]; pvar
0x180004e30  setz    al
0x180004e33  mov     [rdi], al
0x180004e35  call    cs:__imp_PropVariantClear
0x180004e3b  xor     ebx, ebx
0x180004e3d  mov     rcx, [rbp+arg_10]
0x180004e41  mov     rax, [rcx]
0x180004e44  mov     rax, [rax+10h]
0x180004e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4d  mov     rcx, [rbp+arg_18]
0x180004e51  mov     rax, [rcx]
0x180004e54  mov     rax, [rax+10h]
0x180004e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5d  mov     eax, ebx
0x180004e5f  mov     rbx, [rsp+50h+arg_0]
0x180004e64  add     rsp, 50h
0x180004e68  pop     rdi
0x180004e69  pop     rsi
0x180004e6a  pop     rbp
0x180004e6b  retn
```
