# OUTPUT_META_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180002a4c`
- end: `0x180002ea4`
- name: `?Initialize@OUTPUT_META_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1112`
- prototype: `__int64 __fastcall(OUTPUT_META_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001280`

## callees

- `0x180002a4c`
- `0x180007918`
- `0x180009010`

## string_xrefs

- `0x180002b6f`: `enableKernelCache`
- `0x180002c29`: `extension`
- `0x180002c83`: `kernelCachePolicy`

## pseudocode

```c
__int64 __fastcall OUTPUT_META_CONTEXT::Initialize(
        OUTPUT_META_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // rsi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // ebx
  unsigned int i; // esi
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 v15; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-9h] BYREF
  __int64 v18; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v19; // [rsp+60h] [rbp+7h] BYREF
  unsigned int v20; // [rsp+64h] [rbp+Bh] BYREF
  __int64 v21; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+70h] [rbp+17h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp+1Fh] BYREF
  unsigned __int16 *v24; // [rsp+80h] [rbp+27h] BYREF
  unsigned __int16 *v25; // [rsp+88h] [rbp+2Fh] BYREF
  unsigned int v26; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v27; // [rsp+D8h] [rbp+7Fh] BYREF

  v3 = *(_QWORD *)a2;
  v21 = 0;
  v16 = 0;
  v18 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v17 = 0;
  v15 = 0;
  v26 = 0;
  v25 = 0;
  v20 = 0;
  v19 = 0;
  v22 = 0;
  v27 = 0;
  v24 = 0;
  v23 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v21);
  if ( v10 < 0
    || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v21 + 24LL))(
                v21,
                L"system.webServer/caching",
                v8,
                &v16,
                a3,
                0),
        v10 < 0)
    || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
                v16,
                L"enabled",
                (char *)this + 8,
                0,
                0),
        v10 < 0)
    || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
                v16,
                L"enableKernelCache",
                (char *)this + 12,
                0,
                0),
        v10 < 0)
    || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 32LL))(
                v16,
                L"profiles",
                &v18),
        v10 < 0)
    || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v18 + 40LL))(v18, &v17), v10 < 0)
    || (v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v17 + 24))(v17, &v26), v10 < 0) )
  {
LABEL_21:
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
    }
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
      v17 = 0;
    }
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
    }
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v16 = 0;
    }
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    return (unsigned int)v10;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v12 = *v17;
      if ( i >= v26 )
        break;
      v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v12 + 32))(v17, i, &v15);
      if ( v10 < 0 )
        goto LABEL_21;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
              v15,
              L"extension",
              &v25,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_21;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
              v15,
              L"policy",
              &v20,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_21;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
              v15,
              L"kernelCachePolicy",
              &v19,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_21;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v15 + 80LL))(
              v15,
              L"duration",
              &v22,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_21;
      v13 = v22 / 10000000;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
              v15,
              L"location",
              &v27,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_21;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
              v15,
              L"varyByHeaders",
              &v24,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_21;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
              v15,
              L"varyByQueryString",
              &v23,
              0,
              0);
      if ( v10 < 0 )
        goto LABEL_21;
      v10 = OUTPUT_META_CONTEXT::AddProfile(this, v25, v20, v19, v13, v27, v24, v23);
      if ( v10 < 0 )
        goto LABEL_21;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
    }
    (*(void (**)(void))(v12 + 16))();
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    return 0;
  }
}

```

## disassembly

```asm
0x180002a4c  mov     [rsp-8+arg_0], rbx
0x180002a51  push    rbp
0x180002a52  push    rsi
0x180002a53  push    rdi
0x180002a54  push    r14
0x180002a56  push    r15
0x180002a58  lea     rbp, [rsp-37h]
0x180002a5d  sub     rsp, 90h
0x180002a64  mov     rax, [rdx]
0x180002a67  xor     r15d, r15d
0x180002a6a  mov     r14, rcx
0x180002a6d  mov     [rbp+57h+var_48], r15
0x180002a71  mov     rcx, rdx
0x180002a74  mov     [rbp+57h+var_68], r15
0x180002a78  mov     rdi, r8
0x180002a7b  mov     [rbp+57h+var_58], r15
0x180002a7f  mov     rax, [rax+0A0h]
0x180002a86  mov     [rbp+57h+var_60], r15
0x180002a8a  mov     [rbp+57h+var_70], r15
0x180002a8e  mov     [rbp+57h+arg_8], r15d
0x180002a92  mov     [rbp+57h+var_28], r15
0x180002a96  mov     [rbp+57h+var_4C], r15d
0x180002a9a  mov     [rbp+57h+var_50], r15d
0x180002a9e  mov     [rbp+57h+var_40], r15
0x180002aa2  mov     [rbp+57h+arg_18], r15d
0x180002aa6  mov     [rbp+57h+var_30], r15
0x180002aaa  mov     [rbp+57h+var_38], r15
0x180002aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab3  mov     rdx, rax
0x180002ab6  mov     rcx, [rax]
0x180002ab9  mov     rax, [rcx]
0x180002abc  mov     rcx, rdx
0x180002abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac4  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002acb  mov     rsi, rax
0x180002ace  mov     rdx, [rcx]
0x180002ad1  mov     rax, [rdx+38h]
0x180002ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ada  mov     r9, rax
0x180002add  lea     r8, [rbp+57h+var_48]
0x180002ae1  lea     rdx, IID_INativeConfigurationSystem
0x180002ae8  mov     rcx, [rax]
0x180002aeb  mov     rax, [rcx]
0x180002aee  mov     rcx, r9
0x180002af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af6  mov     ebx, eax
0x180002af8  test    eax, eax
0x180002afa  js      loc_180002E12
0x180002b00  mov     rcx, [rbp+57h+var_48]
0x180002b04  lea     r9, [rbp+57h+var_68]
0x180002b08  mov     qword ptr [rsp+0B0h+var_88], r15
0x180002b0d  lea     rdx, aSystemWebserve; "system.webServer/caching"
0x180002b14  mov     r8, rsi
0x180002b17  mov     qword ptr [rsp+0B0h+var_90], rdi
0x180002b1c  mov     rax, [rcx]
0x180002b1f  mov     rax, [rax+18h]
0x180002b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b28  mov     ebx, eax
0x180002b2a  test    eax, eax
0x180002b2c  js      loc_180002E12
0x180002b32  mov     rcx, [rbp+57h+var_68]
0x180002b36  lea     r8, [r14+8]
0x180002b3a  xor     r9d, r9d
0x180002b3d  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002b42  lea     rdx, aEnabled; "enabled"
0x180002b49  mov     rax, [rcx]
0x180002b4c  mov     rax, [rax+48h]
0x180002b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b55  mov     ebx, eax
0x180002b57  test    eax, eax
0x180002b59  js      loc_180002E12
0x180002b5f  mov     rcx, [rbp+57h+var_68]
0x180002b63  lea     r8, [r14+0Ch]
0x180002b67  xor     r9d, r9d
0x180002b6a  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002b6f  lea     rdx, aEnablekernelca; "enableKernelCache"
0x180002b76  mov     rax, [rcx]
0x180002b79  mov     rax, [rax+48h]
0x180002b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b82  mov     ebx, eax
0x180002b84  test    eax, eax
0x180002b86  js      loc_180002E12
0x180002b8c  mov     rcx, [rbp+57h+var_68]
0x180002b90  lea     r8, [rbp+57h+var_58]
0x180002b94  lea     rdx, aProfiles; "profiles"
0x180002b9b  mov     rax, [rcx]
0x180002b9e  mov     rax, [rax+20h]
0x180002ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba7  mov     ebx, eax
0x180002ba9  test    eax, eax
0x180002bab  js      loc_180002E12
0x180002bb1  mov     rcx, [rbp+57h+var_58]
0x180002bb5  lea     rdx, [rbp+57h+var_60]
0x180002bb9  mov     rax, [rcx]
0x180002bbc  mov     rax, [rax+28h]
0x180002bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc5  mov     ebx, eax
0x180002bc7  test    eax, eax
0x180002bc9  js      loc_180002E12
0x180002bcf  mov     rcx, [rbp+57h+var_60]
0x180002bd3  lea     rdx, [rbp+57h+arg_8]
0x180002bd7  mov     rax, [rcx]
0x180002bda  mov     rax, [rax+18h]
0x180002bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be3  mov     ebx, eax
0x180002be5  test    eax, eax
0x180002be7  js      loc_180002E12
0x180002bed  mov     esi, r15d
0x180002bf0  mov     rcx, [rbp+57h+var_60]
0x180002bf4  mov     rax, [rcx]
0x180002bf7  cmp     esi, [rbp+57h+arg_8]
0x180002bfa  jnb     loc_180002DC9
0x180002c00  mov     rax, [rax+20h]
0x180002c04  lea     r8, [rbp+57h+var_70]
0x180002c08  mov     edx, esi
0x180002c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c0f  mov     ebx, eax
0x180002c11  test    eax, eax
0x180002c13  js      loc_180002E12
0x180002c19  mov     rcx, [rbp+57h+var_70]
0x180002c1d  lea     r8, [rbp+57h+var_28]
0x180002c21  xor     r9d, r9d
0x180002c24  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002c29  lea     rdx, aExtension; "extension"
0x180002c30  mov     rax, [rcx]
0x180002c33  mov     rax, [rax+40h]
0x180002c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3c  mov     ebx, eax
0x180002c3e  test    eax, eax
0x180002c40  js      loc_180002E12
0x180002c46  mov     rcx, [rbp+57h+var_70]
0x180002c4a  lea     r8, [rbp+57h+var_4C]
0x180002c4e  xor     r9d, r9d
0x180002c51  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002c56  lea     rdx, aPolicy; "policy"
0x180002c5d  mov     rax, [rcx]
0x180002c60  mov     rax, [rax+30h]
0x180002c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c69  mov     ebx, eax
0x180002c6b  test    eax, eax
0x180002c6d  js      loc_180002E12
0x180002c73  mov     rcx, [rbp+57h+var_70]
0x180002c77  lea     r8, [rbp+57h+var_50]
0x180002c7b  xor     r9d, r9d
0x180002c7e  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002c83  lea     rdx, aKernelcachepol; "kernelCachePolicy"
0x180002c8a  mov     rax, [rcx]
0x180002c8d  mov     rax, [rax+30h]
0x180002c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c96  mov     ebx, eax
0x180002c98  test    eax, eax
0x180002c9a  js      loc_180002E12
0x180002ca0  mov     rcx, [rbp+57h+var_70]
0x180002ca4  lea     r8, [rbp+57h+var_40]
0x180002ca8  xor     r9d, r9d
0x180002cab  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002cb0  lea     rdx, aDuration; "duration"
0x180002cb7  mov     rax, [rcx]
0x180002cba  mov     rax, [rax+50h]
0x180002cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc3  mov     ebx, eax
0x180002cc5  test    eax, eax
0x180002cc7  js      loc_180002E12
0x180002ccd  mov     rcx, [rbp+57h+var_70]
0x180002cd1  lea     r8, [rbp+57h+arg_18]
0x180002cd5  mov     rax, 0D6BF94D5E57A42BDh
0x180002cdf  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002ce4  imul    [rbp+57h+var_40]
0x180002ce8  xor     r9d, r9d
0x180002ceb  mov     rdi, rdx
0x180002cee  lea     rdx, aLocation; "location"
0x180002cf5  add     rdi, [rbp+57h+var_40]
0x180002cf9  sar     rdi, 17h
0x180002cfd  mov     rax, rdi
0x180002d00  shr     rax, 3Fh
0x180002d04  add     rdi, rax
0x180002d07  mov     rax, [rcx]
0x180002d0a  mov     rax, [rax+30h]
0x180002d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d13  mov     ebx, eax
0x180002d15  test    eax, eax
0x180002d17  js      loc_180002E12
0x180002d1d  mov     rcx, [rbp+57h+var_70]
0x180002d21  lea     r8, [rbp+57h+var_30]
0x180002d25  xor     r9d, r9d
0x180002d28  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002d2d  lea     rdx, aVarybyheaders; "varyByHeaders"
0x180002d34  mov     rax, [rcx]
0x180002d37  mov     rax, [rax+40h]
0x180002d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d40  mov     ebx, eax
0x180002d42  test    eax, eax
0x180002d44  js      loc_180002E12
0x180002d4a  mov     rcx, [rbp+57h+var_70]
0x180002d4e  lea     r8, [rbp+57h+var_38]
0x180002d52  xor     r9d, r9d
0x180002d55  mov     qword ptr [rsp+0B0h+var_90], r15
0x180002d5a  lea     rdx, aVarybyquerystr; "varyByQueryString"
0x180002d61  mov     rax, [rcx]
0x180002d64  mov     rax, [rax+40h]
0x180002d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d6d  mov     ebx, eax
0x180002d6f  test    eax, eax
0x180002d71  js      loc_180002E12
0x180002d77  mov     rax, [rbp+57h+var_38]
0x180002d7b  mov     rcx, r14; this
0x180002d7e  mov     r9d, [rbp+57h+var_50]; unsigned int
0x180002d82  mov     r8d, [rbp+57h+var_4C]; unsigned int
0x180002d86  mov     rdx, [rbp+57h+var_28]; unsigned __int16 *
0x180002d8a  mov     [rsp+0B0h+var_78], rax; unsigned __int16 *
0x180002d8f  mov     rax, [rbp+57h+var_30]
0x180002d93  mov     [rsp+0B0h+var_80], rax; unsigned __int16 *
0x180002d98  mov     eax, [rbp+57h+arg_18]
0x180002d9b  mov     [rsp+0B0h+var_88], eax; unsigned int
0x180002d9f  mov     [rsp+0B0h+var_90], edi; unsigned int
0x180002da3  call    ?AddProfile@OUTPUT_META_CONTEXT@@AEAAJPEBGKKKK00@Z; OUTPUT_META_CONTEXT::AddProfile(ushort const *,ulong,ulong,ulong,ulong,ushort const *,ushort const *)
0x180002da8  mov     ebx, eax
0x180002daa  test    eax, eax
0x180002dac  js      short loc_180002E12
0x180002dae  mov     rcx, [rbp+57h+var_70]
0x180002db2  mov     rax, [rcx]
0x180002db5  mov     rax, [rax+10h]
0x180002db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbe  inc     esi
0x180002dc0  mov     [rbp+57h+var_70], r15
0x180002dc4  jmp     loc_180002BF0
0x180002dc9  mov     rax, [rax+10h]
0x180002dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd2  mov     rcx, [rbp+57h+var_58]
0x180002dd6  mov     [rbp+57h+var_60], r15
0x180002dda  mov     rax, [rcx]
0x180002ddd  mov     rax, [rax+10h]
0x180002de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de6  mov     rcx, [rbp+57h+var_68]
0x180002dea  mov     [rbp+57h+var_58], r15
0x180002dee  mov     rax, [rcx]
0x180002df1  mov     rax, [rax+10h]
0x180002df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dfa  mov     rcx, [rbp+57h+var_48]
0x180002dfe  mov     [rbp+57h+var_68], r15
0x180002e02  mov     rax, [rcx]
0x180002e05  mov     rax, [rax+10h]
0x180002e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e0e  xor     eax, eax
0x180002e10  jmp     short loc_180002E8D
0x180002e12  mov     rcx, [rbp+57h+var_70]
0x180002e16  test    rcx, rcx
0x180002e19  jz      short loc_180002E2B
0x180002e1b  mov     rax, [rcx]
0x180002e1e  mov     rax, [rax+10h]
0x180002e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e27  mov     [rbp+57h+var_70], r15
0x180002e2b  mov     rcx, [rbp+57h+var_60]
0x180002e2f  test    rcx, rcx
0x180002e32  jz      short loc_180002E44
0x180002e34  mov     rax, [rcx]
0x180002e37  mov     rax, [rax+10h]
0x180002e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e40  mov     [rbp+57h+var_60], r15
0x180002e44  mov     rcx, [rbp+57h+var_58]
0x180002e48  test    rcx, rcx
0x180002e4b  jz      short loc_180002E5D
0x180002e4d  mov     rax, [rcx]
0x180002e50  mov     rax, [rax+10h]
0x180002e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e59  mov     [rbp+57h+var_58], r15
0x180002e5d  mov     rcx, [rbp+57h+var_68]
0x180002e61  test    rcx, rcx
0x180002e64  jz      short loc_180002E76
0x180002e66  mov     rax, [rcx]
0x180002e69  mov     rax, [rax+10h]
0x180002e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e72  mov     [rbp+57h+var_68], r15
0x180002e76  mov     rcx, [rbp+57h+var_48]
0x180002e7a  test    rcx, rcx
0x180002e7d  jz      short loc_180002E8B
0x180002e7f  mov     rax, [rcx]
0x180002e82  mov     rax, [rax+10h]
0x180002e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8b  mov     eax, ebx
0x180002e8d  mov     rbx, [rsp+0B0h+arg_0]
0x180002e95  add     rsp, 90h
0x180002e9c  pop     r15
0x180002e9e  pop     r14
0x180002ea0  pop     rdi
0x180002ea1  pop     rsi
0x180002ea2  pop     rbp
0x180002ea3  retn
```
