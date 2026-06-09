# RegisterCLSIDInCategory

- ea: `0x18007f510`
- end: `0x18007f5c4`
- name: `RegisterCLSIDInCategory`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007f5cc`

## callees

- `0x18007f510`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007f559`
- `ole32!CoCreateInstance` at `0x18007f559`

## pseudocode

```c
__int64 __fastcall RegisterCLSIDInCategory(__int64 a1, __int128 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+30h] [rbp-28h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  v4 = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &v6);
  if ( v4 >= 0 )
  {
    v7 = *a2;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int128 *))(*(_QWORD *)v6 + 40LL))(v6, a1, 1, &v7);
  }
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007f510  mov     r11, rsp
0x18007f513  mov     [r11+10h], rbx
0x18007f517  mov     [r11+18h], rsi
0x18007f51b  push    rdi
0x18007f51c  sub     rsp, 50h
0x18007f520  mov     rax, cs:__security_cookie
0x18007f527  xor     rax, rsp
0x18007f52a  mov     [rsp+58h+var_10], rax
0x18007f52f  mov     rdi, rdx
0x18007f532  mov     qword ptr [r11-28h], 0
0x18007f53a  xor     edx, edx; pUnkOuter
0x18007f53c  lea     rax, [r11-28h]
0x18007f540  mov     rsi, rcx
0x18007f543  mov     [r11-38h], rax
0x18007f547  lea     r9, IID_ICatRegister; riid
0x18007f54e  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18007f555  lea     r8d, [rdx+1]; dwClsContext
0x18007f559  call    cs:__imp_CoCreateInstance
0x18007f55f  mov     ebx, eax
0x18007f561  test    eax, eax
0x18007f563  js      short loc_18007F58F
0x18007f565  mov     rcx, [rsp+58h+var_28]
0x18007f56a  lea     r9, [rsp+58h+var_20]
0x18007f56f  movaps  xmm0, xmmword ptr [rdi]
0x18007f572  mov     r8d, 1
0x18007f578  movdqu  [rsp+58h+var_20], xmm0
0x18007f57e  mov     rdx, rsi
0x18007f581  mov     rax, [rcx]
0x18007f584  mov     rax, [rax+28h]
0x18007f588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f58d  mov     ebx, eax
0x18007f58f  mov     rcx, [rsp+58h+var_28]
0x18007f594  test    rcx, rcx
0x18007f597  jz      short loc_18007F5A5
0x18007f599  mov     rax, [rcx]
0x18007f59c  mov     rax, [rax+10h]
0x18007f5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f5a5  mov     eax, ebx
0x18007f5a7  mov     rcx, [rsp+58h+var_10]
0x18007f5ac  xor     rcx, rsp; StackCookie
0x18007f5af  call    __security_check_cookie
0x18007f5b4  mov     rbx, [rsp+58h+arg_8]
0x18007f5b9  mov     rsi, [rsp+58h+arg_10]
0x18007f5be  add     rsp, 50h
0x18007f5c2  pop     rdi
0x18007f5c3  retn
```
