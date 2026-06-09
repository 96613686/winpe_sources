# W3_RESTRICTION_LIST::Create(INativeSectionException * *)

- ea: `0x180011d90`
- end: `0x180012061`
- name: `?Create@W3_RESTRICTION_LIST@@AEAAJPEAPEAVINativeSectionException@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(W3_RESTRICTION_LIST *__hidden this, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180012068`

## callees

- `0x180001020`
- `0x180011d90`
- `0x180012150`
- `0x180013010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011f8b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011f8b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011f77`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011f77`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180011fa0`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180011fa0`

## string_xrefs

- `0x180011e1b`: `system.webServer/security/isapiCgiRestriction`

## pseudocode

```c
__int64 __fastcall W3_RESTRICTION_LIST::Create(W3_RESTRICTION_LIST *this, struct INativeSectionException **a2)
{
  __int64 v4; // rax
  __int64 (__fastcall *v5)(struct IHttpServer *); // rax
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rax
  int v7; // edi
  unsigned int i; // r14d
  _DWORD *v9; // rax
  _DWORD *v10; // rsi
  const unsigned __int16 *v11; // rdx
  __int64 v12; // r8
  int inserted; // ebx
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v19; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+B0h] [rbp+40h] BYREF
  int v21; // [rsp+B8h] [rbp+48h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  v4 = *(_QWORD *)W3_RESTRICTION_LIST::sm_pGlobalInfo;
  v15 = 0;
  v20 = 0;
  v19 = 0;
  v5 = *(__int64 (__fastcall **)(struct IHttpServer *))(v4 + 56);
  v21 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v5(W3_RESTRICTION_LIST::sm_pGlobalInfo);
  v7 = (**v6)(v6, &IID_INativeConfigurationSystem, &v18);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v18 + 24LL))(
           v18,
           L"system.webServer/security/isapiCgiRestriction",
           L"MACHINE/WEBROOT/APPHOST",
           &v16,
           a2,
           0);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
             v16,
             L"notListedIsapisAllowed",
             (char *)this + 76,
             0,
             0);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
               v16,
               L"notListedCgisAllowed",
               (char *)this + 72,
               0,
               0);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 40LL))(v16, &v17);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v20);
            if ( v7 >= 0 )
            {
              for ( i = 0; i < v20; ++i )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 32LL))(v17, i, &v15);
                if ( v7 < 0 )
                  break;
                v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                       v15,
                       L"path",
                       &v19,
                       0,
                       0);
                if ( v7 < 0 )
                  break;
                v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 72LL))(
                       v15,
                       L"allowed",
                       &v21,
                       0,
                       0);
                if ( v7 < 0 )
                  break;
                v9 = operator new(0x48u);
                v10 = v9;
                if ( !v9 )
                {
                  v7 = -2147024888;
                  break;
                }
                *v9 = 1;
                STRU::STRU((STRU *)(v9 + 2));
                v11 = v19;
                v10[16] = v21;
                v7 = STRU::Copy((STRU *)(v10 + 2), v11);
                if ( v7 < 0 )
                {
                  W3_IMAGE_RECORD::DereferenceImageRecord((W3_IMAGE_RECORD *)v10);
                  break;
                }
                LOBYTE(v12) = 1;
                inserted = CLKRHashTable::InsertRecord(this, v10, v12);
                W3_IMAGE_RECORD::DereferenceImageRecord((W3_IMAGE_RECORD *)v10);
                if ( inserted )
                {
                  v7 = -2147467259;
                  break;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                v15 = 0;
              }
            }
          }
        }
      }
    }
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180011d90  mov     [rsp-28h+arg_0], rbx
0x180011d95  mov     [rsp-28h+arg_8], rsi
0x180011d9a  push    rbp
0x180011d9b  push    rdi
0x180011d9c  push    r12
0x180011d9e  push    r14
0x180011da0  push    r15
0x180011da2  mov     rbp, rsp
0x180011da5  sub     rsp, 70h
0x180011da9  xor     r12d, r12d
0x180011dac  mov     r15, rcx
0x180011daf  mov     rcx, cs:?sm_pGlobalInfo@W3_RESTRICTION_LIST@@0PEAVIHttpServer@@EA; IHttpServer * W3_RESTRICTION_LIST::sm_pGlobalInfo
0x180011db6  mov     rbx, rdx
0x180011db9  mov     [rbp+var_18], r12
0x180011dbd  mov     [rbp+var_28], r12
0x180011dc1  mov     [rbp+var_20], r12
0x180011dc5  mov     rax, [rcx]
0x180011dc8  mov     [rbp+var_30], r12
0x180011dcc  mov     [rbp+arg_10], r12d
0x180011dd0  mov     [rbp+var_10], r12
0x180011dd4  mov     rax, [rax+38h]
0x180011dd8  mov     [rbp+arg_18], r12d
0x180011ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011de1  mov     r9, rax
0x180011de4  lea     r8, [rbp+var_18]
0x180011de8  lea     rdx, IID_INativeConfigurationSystem
0x180011def  mov     rcx, [rax]
0x180011df2  mov     rax, [rcx]
0x180011df5  mov     rcx, r9
0x180011df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dfd  mov     edi, eax
0x180011dff  test    eax, eax
0x180011e01  js      loc_180011FE6
0x180011e07  mov     rcx, [rbp+var_18]
0x180011e0b  lea     r9, [rbp+var_28]
0x180011e0f  mov     [rsp+70h+var_48], r12
0x180011e14  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180011e1b  lea     rdx, aSystemWebserve; "system.webServer/security/isapiCgiRestr"...
0x180011e22  mov     [rsp+70h+var_50], rbx
0x180011e27  mov     rax, [rcx]
0x180011e2a  mov     rax, [rax+18h]
0x180011e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e33  mov     edi, eax
0x180011e35  test    eax, eax
0x180011e37  js      loc_180011FE6
0x180011e3d  mov     rcx, [rbp+var_28]
0x180011e41  lea     r8, [r15+4Ch]
0x180011e45  xor     r9d, r9d
0x180011e48  mov     [rsp+70h+var_50], r12
0x180011e4d  lea     rdx, aNotlistedisapi; "notListedIsapisAllowed"
0x180011e54  mov     rax, [rcx]
0x180011e57  mov     rax, [rax+48h]
0x180011e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e60  mov     edi, eax
0x180011e62  test    eax, eax
0x180011e64  js      loc_180011FE6
0x180011e6a  mov     rcx, [rbp+var_28]
0x180011e6e  lea     r8, [r15+48h]
0x180011e72  xor     r9d, r9d
0x180011e75  mov     [rsp+70h+var_50], r12
0x180011e7a  lea     rdx, aNotlistedcgisa; "notListedCgisAllowed"
0x180011e81  mov     rax, [rcx]
0x180011e84  mov     rax, [rax+48h]
0x180011e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e8d  mov     edi, eax
0x180011e8f  test    eax, eax
0x180011e91  js      loc_180011FE6
0x180011e97  mov     rcx, [rbp+var_28]
0x180011e9b  lea     rdx, [rbp+var_20]
0x180011e9f  mov     rax, [rcx]
0x180011ea2  mov     rax, [rax+28h]
0x180011ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eab  mov     edi, eax
0x180011ead  test    eax, eax
0x180011eaf  js      loc_180011FE6
0x180011eb5  mov     rcx, [rbp+var_20]
0x180011eb9  lea     rdx, [rbp+arg_10]
0x180011ebd  mov     rax, [rcx]
0x180011ec0  mov     rax, [rax+18h]
0x180011ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ec9  mov     edi, eax
0x180011ecb  test    eax, eax
0x180011ecd  js      loc_180011FE6
0x180011ed3  mov     r14d, r12d
0x180011ed6  cmp     r14d, [rbp+arg_10]
0x180011eda  jnb     loc_180011FE6
0x180011ee0  mov     rcx, [rbp+var_20]
0x180011ee4  lea     r8, [rbp+var_30]
0x180011ee8  mov     edx, r14d
0x180011eeb  mov     rax, [rcx]
0x180011eee  mov     rax, [rax+20h]
0x180011ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef7  mov     edi, eax
0x180011ef9  test    eax, eax
0x180011efb  js      loc_180011FE6
0x180011f01  mov     rcx, [rbp+var_30]
0x180011f05  lea     r8, [rbp+var_10]
0x180011f09  xor     r9d, r9d
0x180011f0c  mov     [rsp+70h+var_50], r12
0x180011f11  lea     rdx, aPath; "path"
0x180011f18  mov     rax, [rcx]
0x180011f1b  mov     rax, [rax+40h]
0x180011f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f24  mov     edi, eax
0x180011f26  test    eax, eax
0x180011f28  js      loc_180011FE6
0x180011f2e  mov     rcx, [rbp+var_30]
0x180011f32  lea     r8, [rbp+arg_18]
0x180011f36  xor     r9d, r9d
0x180011f39  mov     [rsp+70h+var_50], r12
0x180011f3e  lea     rdx, aAllowed; "allowed"
0x180011f45  mov     rax, [rcx]
0x180011f48  mov     rax, [rax+48h]
0x180011f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f51  mov     edi, eax
0x180011f53  test    eax, eax
0x180011f55  js      loc_180011FE6
0x180011f5b  mov     ecx, 48h ; 'H'; Size
0x180011f60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011f65  mov     rsi, rax
0x180011f68  test    rax, rax
0x180011f6b  jz      short loc_180011FE1
0x180011f6d  lea     rcx, [rax+8]
0x180011f71  mov     dword ptr [rax], 1
0x180011f77  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011f7d  mov     ecx, [rbp+arg_18]
0x180011f80  mov     rdx, [rbp+var_10]
0x180011f84  mov     [rsi+40h], ecx
0x180011f87  lea     rcx, [rsi+8]
0x180011f8b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180011f91  mov     edi, eax
0x180011f93  test    eax, eax
0x180011f95  js      short loc_180011FD7
0x180011f97  mov     r8b, 1
0x180011f9a  mov     rdx, rsi
0x180011f9d  mov     rcx, r15
0x180011fa0  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180011fa6  mov     rcx, rsi; this
0x180011fa9  mov     ebx, eax
0x180011fab  call    ?DereferenceImageRecord@W3_IMAGE_RECORD@@QEAAXXZ; W3_IMAGE_RECORD::DereferenceImageRecord(void)
0x180011fb0  test    ebx, ebx
0x180011fb2  jnz     short loc_180011FD0
0x180011fb4  mov     rcx, [rbp+var_30]
0x180011fb8  mov     rax, [rcx]
0x180011fbb  mov     rax, [rax+10h]
0x180011fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fc4  inc     r14d
0x180011fc7  mov     [rbp+var_30], r12
0x180011fcb  jmp     loc_180011ED6
0x180011fd0  mov     edi, 80004005h
0x180011fd5  jmp     short loc_180011FE6
0x180011fd7  mov     rcx, rsi; this
0x180011fda  call    ?DereferenceImageRecord@W3_IMAGE_RECORD@@QEAAXXZ; W3_IMAGE_RECORD::DereferenceImageRecord(void)
0x180011fdf  jmp     short loc_180011FE6
0x180011fe1  mov     edi, 80070008h
0x180011fe6  mov     rcx, [rbp+var_30]
0x180011fea  test    rcx, rcx
0x180011fed  jz      short loc_180011FFF
0x180011fef  mov     rax, [rcx]
0x180011ff2  mov     rax, [rax+10h]
0x180011ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ffb  mov     [rbp+var_30], r12
0x180011fff  mov     rcx, [rbp+var_20]
0x180012003  test    rcx, rcx
0x180012006  jz      short loc_180012018
0x180012008  mov     rax, [rcx]
0x18001200b  mov     rax, [rax+10h]
0x18001200f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012014  mov     [rbp+var_20], r12
0x180012018  mov     rcx, [rbp+var_28]
0x18001201c  test    rcx, rcx
0x18001201f  jz      short loc_180012031
0x180012021  mov     rax, [rcx]
0x180012024  mov     rax, [rax+10h]
0x180012028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001202d  mov     [rbp+var_28], r12
0x180012031  mov     rcx, [rbp+var_18]
0x180012035  test    rcx, rcx
0x180012038  jz      short loc_180012046
0x18001203a  mov     rax, [rcx]
0x18001203d  mov     rax, [rax+10h]
0x180012041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012046  lea     r11, [rsp+70h+var_s0]
0x18001204b  mov     eax, edi
0x18001204d  mov     rbx, [r11+30h]
0x180012051  mov     rsi, [r11+38h]
0x180012055  mov     rsp, r11
0x180012058  pop     r15
0x18001205a  pop     r14
0x18001205c  pop     r12
0x18001205e  pop     rdi
0x18001205f  pop     rbp
0x180012060  retn
```
