# CCOMComponentRegistrar::CheckItfHasStandardMarshalling(_GUID const &,int *)

- ea: `0x18002e100`
- end: `0x18002e326`
- name: `?CheckItfHasStandardMarshalling@CCOMComponentRegistrar@@AEAAJAEBU_GUID@@PEAH@Z`
- size: `550`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, const struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf60`

## callees

- `0x18002e100`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002e299`
- `msvcrt!_wcsicmp` at `0x18002e2ae`
- `msvcrt!_wcsicmp` at `0x18002e299`
- `msvcrt!_wcsicmp` at `0x18002e2ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e17d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e17d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e288`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e288`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCOMComponentRegistrar::CheckItfHasStandardMarshalling(
        CCOMComponentRegistrar *this,
        const struct _GUID *a2,
        int *a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // [rsp+50h] [rbp-59h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-51h] BYREF
  int v10; // [rsp+60h] [rbp-49h] BYREF
  int v11; // [rsp+64h] [rbp-45h] BYREF
  GUID *rguid; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v13[2]; // [rsp+70h] [rbp-39h] BYREF
  int v14; // [rsp+80h] [rbp-29h]
  int v15; // [rsp+84h] [rbp-25h]
  OLECHAR sz[40]; // [rsp+90h] [rbp-19h] BYREF

  *a3 = 0;
  v11 = 0;
  v10 = 0;
  rguid = 0;
  ppv = 0;
  v8 = 0;
  v5 = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
  if ( v5 < 0 )
    goto LABEL_14;
  if ( !ppv )
  {
    v5 = -2147024882;
    goto LABEL_17;
  }
  v13[0] = a2;
  v13[1] = 0;
  v14 = 72;
  v15 = 16;
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         didCOMCLASSIC,
         tidCOMCLASSIC_IIDS,
         v13,
         1,
         1,
         4,
         &v8);
  if ( v5 < 0 )
    goto LABEL_14;
  v6 = v8;
  if ( v8 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 40LL))(v8);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, GUID **))(*(_QWORD *)v8 + 64LL))(
                 v8,
                 1,
                 &v11,
                 &v10,
                 &rguid);
          if ( !v5 )
          {
            StringFromGUID2(rguid, sz, 40);
            if ( !_wcsicmp(sz, L"{00020420-0000-0000-C000-000000000046}")
              || !_wcsicmp(sz, L"{00020424-0000-0000-C000-000000000046}") )
            {
              *a3 = 1;
            }
          }
        }
      }
    }
LABEL_14:
    v6 = v8;
    goto LABEL_15;
  }
  v5 = -2147024882;
LABEL_15:
  if ( !ppv )
    goto LABEL_18;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  ppv = 0;
LABEL_17:
  v6 = v8;
LABEL_18:
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v5 )
  {
    *a3 = 0;
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002e100  mov     [rsp-8+arg_0], rbx
0x18002e105  mov     [rsp-8+arg_8], rsi
0x18002e10a  push    rbp
0x18002e10b  push    rdi
0x18002e10c  push    r15
0x18002e10e  lea     rbp, [rsp-47h]
0x18002e113  sub     rsp, 0F0h
0x18002e11a  mov     rax, cs:__security_cookie
0x18002e121  xor     rax, rsp
0x18002e124  mov     [rbp+57h+var_20], rax
0x18002e128  mov     rdi, r8
0x18002e12b  mov     dword ptr [r8], 0
0x18002e132  mov     rsi, rdx
0x18002e135  mov     [rbp+57h+var_9C], 0
0x18002e13c  lea     rax, [rbp+57h+var_A8]
0x18002e140  mov     [rbp+57h+var_A0], 0
0x18002e147  mov     r15d, 1
0x18002e14d  mov     [rbp+57h+rguid], 0
0x18002e155  mov     r8d, r15d; dwClsContext
0x18002e158  mov     [rbp+57h+var_A8], 0
0x18002e160  lea     r9, IID_ISimpleTableDispenser; riid
0x18002e167  mov     [rbp+57h+var_B0], 0
0x18002e16f  xor     edx, edx; pUnkOuter
0x18002e171  mov     [rsp+100h+ppv], rax; ppv
0x18002e176  lea     rcx, CLSID_STDispenser; rclsid
0x18002e17d  call    cs:__imp_CoCreateInstance
0x18002e183  mov     ebx, eax
0x18002e185  test    eax, eax
0x18002e187  js      loc_18002E2BB
0x18002e18d  mov     rcx, [rbp+57h+var_A8]
0x18002e191  test    rcx, rcx
0x18002e194  jnz     short loc_18002E1A0
0x18002e196  mov     ebx, 8007000Eh
0x18002e19b  jmp     loc_18002E2DF
0x18002e1a0  mov     [rbp+57h+var_90], rsi
0x18002e1a4  lea     rdx, [rbp+57h+var_B0]
0x18002e1a8  mov     [rsp+100h+var_C8], rdx
0x18002e1ad  lea     r9, [rbp+57h+var_90]
0x18002e1b1  mov     [rbp+57h+var_88], 0
0x18002e1b9  lea     r8, tidCOMCLASSIC_IIDS
0x18002e1c0  mov     [rbp+57h+var_80], 48h ; 'H'
0x18002e1c7  lea     rdx, didCOMCLASSIC
0x18002e1ce  mov     [rbp+57h+var_7C], 10h
0x18002e1d5  mov     rax, [rcx]
0x18002e1d8  mov     [rsp+100h+var_D0], 4
0x18002e1e0  mov     [rsp+100h+var_D8], r15d
0x18002e1e5  mov     [rsp+100h+ppv], r15
0x18002e1ea  mov     rax, [rax+18h]
0x18002e1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1f3  mov     ebx, eax
0x18002e1f5  test    eax, eax
0x18002e1f7  js      loc_18002E2BB
0x18002e1fd  mov     rcx, [rbp+57h+var_B0]
0x18002e201  test    rcx, rcx
0x18002e204  jnz     short loc_18002E210
0x18002e206  mov     ebx, 8007000Eh
0x18002e20b  jmp     loc_18002E2BF
0x18002e210  mov     rax, [rcx]
0x18002e213  mov     rax, [rax+18h]
0x18002e217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e21c  mov     ebx, eax
0x18002e21e  test    eax, eax
0x18002e220  js      loc_18002E2BB
0x18002e226  mov     rcx, [rbp+57h+var_B0]
0x18002e22a  mov     rax, [rcx]
0x18002e22d  mov     rax, [rax+20h]
0x18002e231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e236  mov     ebx, eax
0x18002e238  test    eax, eax
0x18002e23a  js      short loc_18002E2BB
0x18002e23c  mov     rcx, [rbp+57h+var_B0]
0x18002e240  mov     rax, [rcx]
0x18002e243  mov     rax, [rax+28h]
0x18002e247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e24c  mov     ebx, eax
0x18002e24e  test    eax, eax
0x18002e250  js      short loc_18002E2BB
0x18002e252  mov     rcx, [rbp+57h+var_B0]
0x18002e256  lea     rdx, [rbp+57h+rguid]
0x18002e25a  mov     [rsp+100h+ppv], rdx
0x18002e25f  lea     r9, [rbp+57h+var_A0]
0x18002e263  lea     r8, [rbp+57h+var_9C]
0x18002e267  mov     edx, r15d
0x18002e26a  mov     rax, [rcx]
0x18002e26d  mov     rax, [rax+40h]
0x18002e271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e276  mov     ebx, eax
0x18002e278  test    eax, eax
0x18002e27a  jnz     short loc_18002E2BB
0x18002e27c  mov     rcx, [rbp+57h+rguid]; rguid
0x18002e280  lea     r8d, [rax+28h]; cchMax
0x18002e284  lea     rdx, [rbp+57h+sz]; lpsz
0x18002e288  call    cs:__imp_StringFromGUID2
0x18002e28e  lea     rdx, a00020420000000; "{00020420-0000-0000-C000-000000000046}"
0x18002e295  lea     rcx, [rbp+57h+sz]; String1
0x18002e299  call    cs:__imp__wcsicmp
0x18002e29f  test    eax, eax
0x18002e2a1  jz      short loc_18002E2B8
0x18002e2a3  lea     rdx, a00020424000000; "{00020424-0000-0000-C000-000000000046}"
0x18002e2aa  lea     rcx, [rbp+57h+sz]; String1
0x18002e2ae  call    cs:__imp__wcsicmp
0x18002e2b4  test    eax, eax
0x18002e2b6  jnz     short loc_18002E2BB
0x18002e2b8  mov     [rdi], r15d
0x18002e2bb  mov     rcx, [rbp+57h+var_B0]
0x18002e2bf  mov     rdx, [rbp+57h+var_A8]
0x18002e2c3  test    rdx, rdx
0x18002e2c6  jz      short loc_18002E2E3
0x18002e2c8  mov     rax, [rdx]
0x18002e2cb  mov     rcx, rdx
0x18002e2ce  mov     rax, [rax+10h]
0x18002e2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2d7  mov     [rbp+57h+var_A8], 0
0x18002e2df  mov     rcx, [rbp+57h+var_B0]
0x18002e2e3  test    rcx, rcx
0x18002e2e6  jz      short loc_18002E2F4
0x18002e2e8  mov     rax, [rcx]
0x18002e2eb  mov     rax, [rax+10h]
0x18002e2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2f4  test    ebx, ebx
0x18002e2f6  jz      short loc_18002E300
0x18002e2f8  mov     dword ptr [rdi], 0
0x18002e2fe  xor     ebx, ebx
0x18002e300  mov     eax, ebx
0x18002e302  mov     rcx, [rbp+57h+var_20]
0x18002e306  xor     rcx, rsp; StackCookie
0x18002e309  call    __security_check_cookie
0x18002e30e  lea     r11, [rsp+100h+var_10]
0x18002e316  mov     rbx, [r11+20h]
0x18002e31a  mov     rsi, [r11+28h]
0x18002e31e  mov     rsp, r11
0x18002e321  pop     r15
0x18002e323  pop     rdi
0x18002e324  pop     rbp
0x18002e325  retn
```
