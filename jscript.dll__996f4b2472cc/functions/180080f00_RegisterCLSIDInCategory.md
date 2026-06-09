# RegisterCLSIDInCategory

- ea: `0x180080f00`
- end: `0x180080fbb`
- name: `RegisterCLSIDInCategory`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080fc4`

## callees

- `0x180080f00`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180080f49`
- `ole32!CoCreateInstance` at `0x180080f49`

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
0x180080f00  mov     r11, rsp
0x180080f03  mov     [r11+10h], rbx
0x180080f07  mov     [r11+18h], rsi
0x180080f0b  push    rdi
0x180080f0c  sub     rsp, 50h
0x180080f10  mov     rax, cs:__security_cookie
0x180080f17  xor     rax, rsp
0x180080f1a  mov     [rsp+58h+var_10], rax
0x180080f1f  mov     rdi, rdx
0x180080f22  mov     qword ptr [r11-28h], 0
0x180080f2a  xor     edx, edx; pUnkOuter
0x180080f2c  lea     rax, [r11-28h]
0x180080f30  mov     rsi, rcx
0x180080f33  mov     [r11-38h], rax
0x180080f37  lea     r9, IID_ICatRegister; riid
0x180080f3e  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180080f45  lea     r8d, [rdx+1]; dwClsContext
0x180080f49  call    cs:__imp_CoCreateInstance
0x180080f50  nop     dword ptr [rax+rax+00h]
0x180080f55  mov     ebx, eax
0x180080f57  test    eax, eax
0x180080f59  js      short loc_180080F85
0x180080f5b  mov     rcx, [rsp+58h+var_28]
0x180080f60  lea     r9, [rsp+58h+var_20]
0x180080f65  movaps  xmm0, xmmword ptr [rdi]
0x180080f68  mov     r8d, 1
0x180080f6e  movdqu  [rsp+58h+var_20], xmm0
0x180080f74  mov     rdx, rsi
0x180080f77  mov     rax, [rcx]
0x180080f7a  mov     rax, [rax+28h]
0x180080f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080f83  mov     ebx, eax
0x180080f85  mov     rcx, [rsp+58h+var_28]
0x180080f8a  test    rcx, rcx
0x180080f8d  jz      short loc_180080F9B
0x180080f8f  mov     rax, [rcx]
0x180080f92  mov     rax, [rax+10h]
0x180080f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080f9b  mov     eax, ebx
0x180080f9d  mov     rcx, [rsp+58h+var_10]
0x180080fa2  xor     rcx, rsp; StackCookie
0x180080fa5  call    __security_check_cookie
0x180080faa  mov     rbx, [rsp+58h+arg_8]
0x180080faf  mov     rsi, [rsp+58h+arg_10]
0x180080fb4  add     rsp, 50h
0x180080fb8  pop     rdi
0x180080fb9  retn
```
