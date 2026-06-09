# GetRootDevNode(tagPROPVARIANT const &,tagPROPVARIANT *)

- ea: `0x18000f198`
- end: `0x18000f499`
- name: `?GetRootDevNode@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `769`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a480`
- `0x18000b5c0`
- `0x18000ed14`

## callees

- `0x18000d2a8`
- `0x18000f198`
- `0x180014010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000f3b8`
- `msvcrt!_wcsicmp` at `0x18000f3b8`
- `ole32!CoCreateInstance` at `0x18000f21e`
- `ole32!CoCreateInstance` at `0x18000f21e`
- `ole32!PropVariantClear` at `0x18000f3fa`
- `ole32!PropVariantClear` at `0x18000f43b`
- `ole32!PropVariantClear` at `0x18000f3fa`
- `ole32!PropVariantClear` at `0x18000f43b`

## pseudocode

```c
__int64 __fastcall GetRootDevNode(const struct tagPROPVARIANT *a1, PROPVARIANT *a2)
{
  int v4; // r14d
  unsigned int v5; // ebx
  unsigned int v6; // edi
  __int64 v8; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+48h] [rbp-38h] BYREF
  __int64 v10; // [rsp+50h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-28h] BYREF
  LARGE_INTEGER v12; // [rsp+60h] [rbp-20h] BYREF
  wchar_t *String2[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v14; // [rsp+78h] [rbp-8h]
  unsigned int v15; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v16; // [rsp+C8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_40bfd8e724853a2dad87543d7d02cd73_Traceguids);
  v4 = 0;
  v15 = 0;
  ppv = 0;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  v16 = 0;
  v9 = 0;
  v5 = CoCreateInstance(&GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc, 0, 3u, &IID_IFunctionDiscovery, &ppv);
  if ( !v5 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(
           ppv,
           L"Provider\\Microsoft.Base.PnP",
           &qword_1800166A0,
           1,
           0,
           0,
           &v16);
    if ( !v5 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v16 + 24LL))(
             v16,
             L"NotPresent",
             L"TRUE");
      if ( !v5 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, const struct tagPROPVARIANT *, _QWORD))(*(_QWORD *)v16 + 32LL))(
               v16,
               &PKEY_PNPX_GlobalIdentity,
               a1,
               0);
        if ( !v5 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, const struct tagPROPVARIANT *, _QWORD))(*(_QWORD *)v16 + 32LL))(
                 v16,
                 &PKEY_PNPX_ID,
                 a1,
                 0);
          if ( !v5 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 40LL))(v16, &v9);
            if ( !v5 )
              v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 24LL))(v9, &v15);
          }
        }
      }
    }
  }
  v6 = 0;
  if ( v5 )
  {
LABEL_29:
    PropVariantClear(a2);
  }
  else
  {
    while ( v6 < v15 )
    {
      if ( !v4 )
      {
        v8 = 0;
        v14 = 0;
        v10 = 0;
        *(_OWORD *)String2 = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 40LL))(v9, v6, &v8);
        if ( !v5 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 48LL))(v8, 0, &v10);
          if ( !v5 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, wchar_t **))(*(_QWORD *)v10 + 40LL))(
                   v10,
                   &PKEY_Device_EnumeratorName,
                   String2);
            if ( !v5 && LOWORD(String2[0]) == 31 && String2[1] && !_wcsicmp(L"SWD", String2[1]) )
            {
              v12.QuadPart = 0;
              v5 = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER *))(*(_QWORD *)v8 + 40LL))(v8, &v12);
              if ( !v5 )
              {
                a2[1] = (PROPVARIANT)v12.QuadPart;
                *(_WORD *)a2 = 31;
              }
              v4 = 1;
            }
          }
        }
        PropVariantClear((PROPVARIANT *)String2);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        ++v6;
        if ( !v5 )
          continue;
      }
      if ( !v5 )
        break;
      goto LABEL_29;
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v5;
}

```

## disassembly

```asm
0x18000f198  mov     [rsp-28h+arg_0], rbx
0x18000f19d  push    rbp
0x18000f19e  push    rsi
0x18000f19f  push    rdi
0x18000f1a0  push    r12
0x18000f1a2  push    r14
0x18000f1a4  mov     rbp, rsp
0x18000f1a7  sub     rsp, 80h
0x18000f1ae  mov     rsi, rdx
0x18000f1b1  mov     rdi, rcx
0x18000f1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1bb  lea     rax, WPP_GLOBAL_Control
0x18000f1c2  cmp     rcx, rax
0x18000f1c5  jz      short loc_18000F1E2
0x18000f1c7  cmp     byte ptr [rcx+19h], 4
0x18000f1cb  jb      short loc_18000F1E2
0x18000f1cd  mov     rcx, [rcx+10h]
0x18000f1d1  lea     r8, WPP_40bfd8e724853a2dad87543d7d02cd73_Traceguids
0x18000f1d8  mov     edx, 0Ch
0x18000f1dd  call    WPP_SF_s
0x18000f1e2  xor     r14d, r14d
0x18000f1e5  lea     r9, IID_IFunctionDiscovery; riid
0x18000f1ec  xor     eax, eax
0x18000f1ee  mov     [rbp+arg_10], r14d
0x18000f1f2  xorps   xmm0, xmm0
0x18000f1f5  mov     [rbp+var_28], r14
0x18000f1f9  movups  xmmword ptr [rsi], xmm0
0x18000f1fc  mov     [rsi+10h], rax
0x18000f200  lea     r8d, [r14+3]; dwClsContext
0x18000f204  lea     rax, [rbp+var_28]
0x18000f208  mov     [rbp+arg_18], r14
0x18000f20c  xor     edx, edx; pUnkOuter
0x18000f20e  mov     [rsp+80h+ppv], rax; ppv
0x18000f213  lea     rcx, _GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc; rclsid
0x18000f21a  mov     [rbp+var_38], r14
0x18000f21e  call    cs:__imp_CoCreateInstance
0x18000f224  mov     ebx, eax
0x18000f226  test    eax, eax
0x18000f228  jnz     loc_18000F307
0x18000f22e  mov     rcx, [rbp+var_28]
0x18000f232  lea     rdx, [rbp+arg_18]
0x18000f236  mov     [rsp+80h+var_50], rdx
0x18000f23b  lea     r9d, [r14+1]
0x18000f23f  mov     [rsp+80h+var_58], r14
0x18000f244  lea     r8, qword_1800166A0
0x18000f24b  lea     rdx, aProviderMicros_1; "Provider\\Microsoft.Base.PnP"
0x18000f252  mov     [rsp+80h+ppv], r14
0x18000f257  mov     rax, [rcx]
0x18000f25a  mov     rax, [rax+28h]
0x18000f25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f263  mov     ebx, eax
0x18000f265  test    eax, eax
0x18000f267  jnz     loc_18000F307
0x18000f26d  mov     rcx, [rbp+arg_18]
0x18000f271  lea     r8, aTrue; "TRUE"
0x18000f278  lea     rdx, aNotpresent; "NotPresent"
0x18000f27f  mov     rax, [rcx]
0x18000f282  mov     rax, [rax+18h]
0x18000f286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f28b  mov     ebx, eax
0x18000f28d  test    eax, eax
0x18000f28f  jnz     short loc_18000F307
0x18000f291  mov     rcx, [rbp+arg_18]
0x18000f295  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18000f29c  xor     r9d, r9d
0x18000f29f  mov     r8, rdi
0x18000f2a2  mov     rax, [rcx]
0x18000f2a5  mov     rax, [rax+20h]
0x18000f2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2ae  mov     ebx, eax
0x18000f2b0  test    eax, eax
0x18000f2b2  jnz     short loc_18000F307
0x18000f2b4  mov     rcx, [rbp+arg_18]
0x18000f2b8  lea     rdx, PKEY_PNPX_ID
0x18000f2bf  xor     r9d, r9d
0x18000f2c2  mov     r8, rdi
0x18000f2c5  mov     rax, [rcx]
0x18000f2c8  mov     rax, [rax+20h]
0x18000f2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2d1  mov     ebx, eax
0x18000f2d3  test    eax, eax
0x18000f2d5  jnz     short loc_18000F307
0x18000f2d7  mov     rcx, [rbp+arg_18]
0x18000f2db  lea     rdx, [rbp+var_38]
0x18000f2df  mov     rax, [rcx]
0x18000f2e2  mov     rax, [rax+28h]
0x18000f2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2eb  mov     ebx, eax
0x18000f2ed  test    eax, eax
0x18000f2ef  jnz     short loc_18000F307
0x18000f2f1  mov     rcx, [rbp+var_38]
0x18000f2f5  lea     rdx, [rbp+arg_10]
0x18000f2f9  mov     rax, [rcx]
0x18000f2fc  mov     rax, [rax+18h]
0x18000f300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f305  mov     ebx, eax
0x18000f307  xor     edi, edi
0x18000f309  test    ebx, ebx
0x18000f30b  jnz     loc_18000F438
0x18000f311  lea     r12d, [rdi+1Fh]
0x18000f315  cmp     edi, [rbp+arg_10]
0x18000f318  jnb     loc_18000F441
0x18000f31e  test    r14d, r14d
0x18000f321  jnz     loc_18000F434
0x18000f327  mov     rcx, [rbp+var_38]
0x18000f32b  lea     r8, [rbp+var_40]
0x18000f32f  xor     eax, eax
0x18000f331  mov     [rbp+var_40], 0
0x18000f339  mov     [rbp+var_8], rax
0x18000f33d  xorps   xmm0, xmm0
0x18000f340  mov     [rbp+var_30], 0
0x18000f348  mov     edx, edi
0x18000f34a  movups  xmmword ptr [rbp+String2], xmm0
0x18000f34e  mov     rax, [rcx]
0x18000f351  mov     rax, [rax+28h]
0x18000f355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f35a  mov     ebx, eax
0x18000f35c  test    eax, eax
0x18000f35e  jnz     loc_18000F3F6
0x18000f364  mov     rcx, [rbp+var_40]
0x18000f368  lea     r8, [rbp+var_30]
0x18000f36c  xor     edx, edx
0x18000f36e  mov     rax, [rcx]
0x18000f371  mov     rax, [rax+30h]
0x18000f375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f37a  mov     ebx, eax
0x18000f37c  test    eax, eax
0x18000f37e  jnz     short loc_18000F3F6
0x18000f380  mov     rcx, [rbp+var_30]
0x18000f384  lea     r8, [rbp+String2]
0x18000f388  lea     rdx, PKEY_Device_EnumeratorName
0x18000f38f  mov     rax, [rcx]
0x18000f392  mov     rax, [rax+28h]
0x18000f396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f39b  mov     ebx, eax
0x18000f39d  test    eax, eax
0x18000f39f  jnz     short loc_18000F3F6
0x18000f3a1  cmp     r12w, word ptr [rbp+String2]
0x18000f3a6  jnz     short loc_18000F3F6
0x18000f3a8  mov     rdx, [rbp+String2+8]; String2
0x18000f3ac  test    rdx, rdx
0x18000f3af  jz      short loc_18000F3F6
0x18000f3b1  lea     rcx, aSwd; "SWD"
0x18000f3b8  call    cs:__imp__wcsicmp
0x18000f3be  test    eax, eax
0x18000f3c0  jnz     short loc_18000F3F6
0x18000f3c2  mov     rcx, [rbp+var_40]
0x18000f3c6  lea     rdx, [rbp+var_20]
0x18000f3ca  mov     [rbp+var_20], 0
0x18000f3d2  mov     rax, [rcx]
0x18000f3d5  mov     rax, [rax+28h]
0x18000f3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3de  mov     ebx, eax
0x18000f3e0  test    eax, eax
0x18000f3e2  jnz     short loc_18000F3F0
0x18000f3e4  mov     rax, [rbp+var_20]
0x18000f3e8  mov     [rsi+8], rax
0x18000f3ec  mov     [rsi], r12w
0x18000f3f0  mov     r14d, 1
0x18000f3f6  lea     rcx, [rbp+String2]; pvar
0x18000f3fa  call    cs:__imp_PropVariantClear
0x18000f400  mov     rcx, [rbp+var_30]
0x18000f404  test    rcx, rcx
0x18000f407  jz      short loc_18000F415
0x18000f409  mov     rax, [rcx]
0x18000f40c  mov     rax, [rax+10h]
0x18000f410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f415  mov     rcx, [rbp+var_40]
0x18000f419  test    rcx, rcx
0x18000f41c  jz      short loc_18000F42A
0x18000f41e  mov     rax, [rcx]
0x18000f421  mov     rax, [rax+10h]
0x18000f425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f42a  inc     edi
0x18000f42c  test    ebx, ebx
0x18000f42e  jz      loc_18000F315
0x18000f434  test    ebx, ebx
0x18000f436  jz      short loc_18000F441
0x18000f438  mov     rcx, rsi; pvar
0x18000f43b  call    cs:__imp_PropVariantClear
0x18000f441  mov     rcx, [rbp+var_38]
0x18000f445  test    rcx, rcx
0x18000f448  jz      short loc_18000F456
0x18000f44a  mov     rax, [rcx]
0x18000f44d  mov     rax, [rax+10h]
0x18000f451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f456  mov     rcx, [rbp+arg_18]
0x18000f45a  test    rcx, rcx
0x18000f45d  jz      short loc_18000F46B
0x18000f45f  mov     rax, [rcx]
0x18000f462  mov     rax, [rax+10h]
0x18000f466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f46b  mov     rcx, [rbp+var_28]
0x18000f46f  test    rcx, rcx
0x18000f472  jz      short loc_18000F480
0x18000f474  mov     rax, [rcx]
0x18000f477  mov     rax, [rax+10h]
0x18000f47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f480  mov     eax, ebx
0x18000f482  mov     rbx, [rsp+80h+arg_0]
0x18000f48a  add     rsp, 80h
0x18000f491  pop     r14
0x18000f493  pop     r12
0x18000f495  pop     rdi
0x18000f496  pop     rsi
0x18000f497  pop     rbp
0x18000f498  retn
```
