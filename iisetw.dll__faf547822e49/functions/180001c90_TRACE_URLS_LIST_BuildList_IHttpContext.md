# TRACE_URLS_LIST::BuildList(IHttpContext *)

- ea: `0x180001c90`
- end: `0x1800021b7`
- name: `?BuildList@TRACE_URLS_LIST@@QEAAJPEAVIHttpContext@@@Z`
- size: `1319`
- prototype: `__int64 __fastcall(TRACE_URLS_LIST *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800019a4`

## callees

- `0x180001008`
- `0x180001048`
- `0x180001c90`
- `0x180003406`
- `0x180003430`
- `0x180004010`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001e9d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001e9d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001e85`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001ff1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001e85`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001ff1`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001e10`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001e10`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d11`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d38`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001fe2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d11`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001d38`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001fe2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000209a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800020a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800020bc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002170`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000217a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000209a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800020a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800020bc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002170`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000217a`

## pseudocode

```c
__int64 __fastcall TRACE_URLS_LIST::BuildList(TRACE_URLS_LIST *this, struct IHttpContext *a2)
{
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rax
  int v5; // ebx
  const unsigned __int16 *v6; // rbx
  __int64 (__fastcall *v7)(__int64, _QWORD, const unsigned __int16 *, int *, _QWORD); // rdi
  __int64 v8; // rax
  unsigned int v9; // eax
  int v10; // eax
  const unsigned __int16 *v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, const unsigned __int16 *, int *, _QWORD); // rdi
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // esi
  char *v16; // rax
  _QWORD *v17; // rdi
  TRACE_URLS_LIST **v18; // rax
  __int64 v19; // rcx
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v23; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v29; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v31; // [rsp+A0h] [rbp-60h]
  _BYTE v32[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v33; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v34[64]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v35[264]; // [rsp+170h] [rbp+70h] BYREF

  v25 = 0;
  v28 = 0;
  v24 = 0;
  v27 = 0;
  v26 = 0;
  v21 = 0;
  v23 = 0;
  v29 = 0;
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v32, v34, 0x40u);
  memset_0(v35, 0, 0x208u);
  STRU::STRU((STRU *)v30, v35, 0x104u);
  v22 = 260;
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v5 = (**v4)(v4, &IID_INativeConfigurationSystem, &v25);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 56LL))(v25, &v21);
    if ( v5 >= 0 )
    {
      v6 = v31;
      v7 = *(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, int *, _QWORD))(*(_QWORD *)v21 + 24LL);
      v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 176LL))(v8);
      v10 = v7(v21, v9, v6, &v22, 0);
      v5 = v10;
      if ( v10 >= 0
        || v10 == -2147024774
        && (v5 = STRU::Resize((STRU *)v30, 2 * v22 + 2), v5 >= 0)
        && (v11 = v31,
            v12 = *(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, int *, _QWORD))(*(_QWORD *)v21 + 24LL),
            v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2),
            v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 176LL))(v13),
            v5 = v12(v21, v14, v11, &v22, 0),
            v5 >= 0) )
      {
        v5 = STRU::Copy((STRU *)v32, L"MACHINE/WEBROOT/APPHOST/");
        if ( v5 >= 0 )
        {
          v5 = STRU::Append((STRU *)v32, v31);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v25 + 24LL))(
                   v25,
                   L"system.webServer/httpTracing",
                   v33,
                   &v28,
                   0,
                   0);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 32LL))(
                     v28,
                     L"traceUrls",
                     &v27);
              if ( v5 >= 0 )
              {
                v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 40LL))(v27, &v24);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                v28 = 0;
                if ( v5 >= 0 )
                {
                  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v23);
                  if ( v5 >= 0 )
                  {
                    v15 = 0;
                    if ( !v23 )
                    {
LABEL_20:
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                      v24 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                      v27 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                      v21 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                      v25 = 0;
                      STRU::~STRU((STRU *)v30);
                      STRU::~STRU((STRU *)v32);
                      return 0;
                    }
                    while ( 1 )
                    {
                      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 32LL))(
                             v24,
                             v15,
                             &v26);
                      if ( v5 < 0 )
                        break;
                      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v26 + 64LL))(
                             v26,
                             L"value",
                             &v29,
                             0,
                             0);
                      if ( v5 < 0 )
                        break;
                      v16 = (char *)operator new(0xC8u);
                      v17 = v16;
                      if ( !v16 )
                      {
                        v5 = -2147024888;
                        break;
                      }
                      STRU::STRU((STRU *)(v16 + 16), (unsigned __int16 *)v16 + 36, 0x40u);
                      v5 = STRU::Copy((STRU *)(v17 + 2), v29);
                      if ( v5 < 0 )
                      {
                        STRU::~STRU((STRU *)(v17 + 2));
                        operator delete(v17);
                        break;
                      }
                      v18 = (TRACE_URLS_LIST **)*((_QWORD *)this + 1);
                      if ( *v18 != this )
                        __fastfail(3u);
                      v17[1] = v18;
                      *v17 = this;
                      *v18 = (TRACE_URLS_LIST *)v17;
                      v19 = v26;
                      *((_QWORD *)this + 1) = v17;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                      ++v15;
                      v26 = 0;
                      if ( v15 >= v23 )
                        goto LABEL_20;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  STRU::~STRU((STRU *)v30);
  STRU::~STRU((STRU *)v32);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001c90  mov     [rsp-8+arg_10], rbx
0x180001c95  mov     [rsp-8+arg_18], rsi
0x180001c9a  push    rbp
0x180001c9b  push    rdi
0x180001c9c  push    r12
0x180001c9e  push    r14
0x180001ca0  push    r15
0x180001ca2  lea     rbp, [rsp-290h]
0x180001caa  sub     rsp, 390h
0x180001cb1  mov     rax, cs:__security_cookie
0x180001cb8  xor     rax, rsp
0x180001cbb  mov     [rbp+2B0h+var_30], rax
0x180001cc2  xor     r12d, r12d
0x180001cc5  mov     rsi, rdx
0x180001cc8  mov     r14, rcx
0x180001ccb  mov     [rsp+3B0h+var_358], r12
0x180001cd0  xor     edx, edx; Val
0x180001cd2  mov     [rsp+3B0h+var_340], r12
0x180001cd7  lea     rcx, [rbp+2B0h+var_2C0]; void *
0x180001cdb  mov     [rsp+3B0h+var_360], r12
0x180001ce0  mov     r8d, 80h; Size
0x180001ce6  mov     [rsp+3B0h+var_348], r12
0x180001ceb  mov     [rsp+3B0h+var_350], r12
0x180001cf0  mov     [rsp+3B0h+var_370], r12
0x180001cf5  mov     [rsp+3B0h+var_364], r12d
0x180001cfa  mov     [rsp+3B0h+var_338], r12
0x180001cff  call    memset_0
0x180001d04  lea     r8d, [r12+40h]
0x180001d09  lea     rdx, [rbp+2B0h+var_2C0]
0x180001d0d  lea     rcx, [rbp+2B0h+var_2F8]
0x180001d11  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001d17  xor     edx, edx; Val
0x180001d19  lea     rcx, [rbp+2B0h+var_240]; void *
0x180001d1d  mov     r8d, 208h; Size
0x180001d23  call    memset_0
0x180001d28  mov     ebx, 104h
0x180001d2d  lea     rdx, [rbp+2B0h+var_240]
0x180001d31  mov     r8d, ebx
0x180001d34  lea     rcx, [rbp+2B0h+var_330]
0x180001d38  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001d3e  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180001d45  mov     [rsp+3B0h+var_368], ebx
0x180001d49  mov     rax, [rcx]
0x180001d4c  mov     rax, [rax+38h]
0x180001d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d55  mov     r9, rax
0x180001d58  lea     r8, [rsp+3B0h+var_358]
0x180001d5d  lea     rdx, IID_INativeConfigurationSystem
0x180001d64  mov     rcx, [rax]
0x180001d67  mov     rax, [rcx]
0x180001d6a  mov     rcx, r9
0x180001d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d72  mov     ebx, eax
0x180001d74  test    eax, eax
0x180001d76  js      loc_1800020CA
0x180001d7c  mov     rcx, [rsp+3B0h+var_358]
0x180001d81  lea     rdx, [rsp+3B0h+var_370]
0x180001d86  mov     rax, [rcx]
0x180001d89  mov     rax, [rax+38h]
0x180001d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d92  mov     ebx, eax
0x180001d94  test    eax, eax
0x180001d96  js      loc_1800020CA
0x180001d9c  mov     rax, [rsp+3B0h+var_370]
0x180001da1  mov     rbx, [rbp+2B0h+var_310]
0x180001da5  mov     rcx, [rax]
0x180001da8  mov     rax, [rsi]
0x180001dab  mov     rdi, [rcx+18h]
0x180001daf  mov     rcx, rsi
0x180001db2  mov     rax, [rax+18h]
0x180001db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dbb  mov     rdx, rax
0x180001dbe  mov     rcx, [rax]
0x180001dc1  mov     rax, [rcx+0B0h]
0x180001dc8  mov     rcx, rdx
0x180001dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dd0  mov     rcx, [rsp+3B0h+var_370]
0x180001dd5  lea     r9, [rsp+3B0h+var_368]
0x180001dda  mov     edx, eax
0x180001ddc  mov     [rsp+3B0h+var_390], r12
0x180001de1  mov     rax, rdi
0x180001de4  mov     r8, rbx
0x180001de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dec  mov     ebx, eax
0x180001dee  test    eax, eax
0x180001df0  jns     loc_180001E7A
0x180001df6  cmp     eax, 8007007Ah
0x180001dfb  jnz     loc_1800020CA
0x180001e01  mov     edx, [rsp+3B0h+var_368]
0x180001e05  lea     rcx, [rbp+2B0h+var_330]
0x180001e09  lea     edx, ds:2[rdx*2]
0x180001e10  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180001e16  mov     ebx, eax
0x180001e18  test    eax, eax
0x180001e1a  js      loc_1800020CA
0x180001e20  mov     rax, [rsp+3B0h+var_370]
0x180001e25  mov     rcx, rsi
0x180001e28  mov     rbx, [rbp+2B0h+var_310]
0x180001e2c  mov     rdx, [rax]
0x180001e2f  mov     rax, [rsi]
0x180001e32  mov     rdi, [rdx+18h]
0x180001e36  mov     rax, [rax+18h]
0x180001e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e3f  mov     rdx, rax
0x180001e42  mov     rcx, [rax]
0x180001e45  mov     rax, [rcx+0B0h]
0x180001e4c  mov     rcx, rdx
0x180001e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e54  mov     rcx, [rsp+3B0h+var_370]
0x180001e59  lea     r9, [rsp+3B0h+var_368]
0x180001e5e  mov     edx, eax
0x180001e60  mov     [rsp+3B0h+var_390], r12
0x180001e65  mov     rax, rdi
0x180001e68  mov     r8, rbx
0x180001e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e70  mov     ebx, eax
0x180001e72  test    eax, eax
0x180001e74  js      loc_1800020CA
0x180001e7a  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST/"
0x180001e81  lea     rcx, [rbp+2B0h+var_2F8]
0x180001e85  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001e8b  mov     ebx, eax
0x180001e8d  test    eax, eax
0x180001e8f  js      loc_1800020CA
0x180001e95  mov     rdx, [rbp+2B0h+var_310]
0x180001e99  lea     rcx, [rbp+2B0h+var_2F8]
0x180001e9d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180001ea3  mov     ebx, eax
0x180001ea5  test    eax, eax
0x180001ea7  js      loc_1800020CA
0x180001ead  mov     rcx, [rsp+3B0h+var_358]
0x180001eb2  lea     r9, [rsp+3B0h+var_340]
0x180001eb7  mov     r8, [rbp+2B0h+var_2D8]
0x180001ebb  lea     rdx, aSystemWebserve; "system.webServer/httpTracing"
0x180001ec2  mov     [rsp+3B0h+var_388], r12
0x180001ec7  mov     [rsp+3B0h+var_390], r12
0x180001ecc  mov     rax, [rcx]
0x180001ecf  mov     rax, [rax+18h]
0x180001ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ed8  mov     ebx, eax
0x180001eda  test    eax, eax
0x180001edc  js      loc_1800020CA
0x180001ee2  mov     rcx, [rsp+3B0h+var_340]
0x180001ee7  lea     r8, [rsp+3B0h+var_348]
0x180001eec  lea     rdx, aTraceurls; "traceUrls"
0x180001ef3  mov     rax, [rcx]
0x180001ef6  mov     rax, [rax+20h]
0x180001efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eff  mov     ebx, eax
0x180001f01  test    eax, eax
0x180001f03  js      loc_1800020CA
0x180001f09  mov     rcx, [rsp+3B0h+var_348]
0x180001f0e  lea     rdx, [rsp+3B0h+var_360]
0x180001f13  mov     rax, [rcx]
0x180001f16  mov     rax, [rax+28h]
0x180001f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f1f  mov     rcx, [rsp+3B0h+var_340]
0x180001f24  mov     ebx, eax
0x180001f26  mov     rax, [rcx]
0x180001f29  mov     rax, [rax+10h]
0x180001f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f32  mov     [rsp+3B0h+var_340], r12
0x180001f37  test    ebx, ebx
0x180001f39  js      loc_1800020CA
0x180001f3f  mov     rcx, [rsp+3B0h+var_360]
0x180001f44  lea     rdx, [rsp+3B0h+var_364]
0x180001f49  mov     rax, [rcx]
0x180001f4c  mov     rax, [rax+18h]
0x180001f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f55  mov     ebx, eax
0x180001f57  test    eax, eax
0x180001f59  js      loc_1800020CA
0x180001f5f  mov     esi, r12d
0x180001f62  cmp     [rsp+3B0h+var_364], r12d
0x180001f67  jbe     loc_18000203E
0x180001f6d  mov     rcx, [rsp+3B0h+var_360]
0x180001f72  lea     r8, [rsp+3B0h+var_350]
0x180001f77  mov     edx, esi
0x180001f79  mov     rax, [rcx]
0x180001f7c  mov     rax, [rax+20h]
0x180001f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f85  mov     ebx, eax
0x180001f87  test    eax, eax
0x180001f89  js      loc_1800020CA
0x180001f8f  mov     rcx, [rsp+3B0h+var_350]
0x180001f94  lea     r8, [rsp+3B0h+var_338]
0x180001f99  xor     r9d, r9d
0x180001f9c  mov     [rsp+3B0h+var_390], r12
0x180001fa1  lea     rdx, aValue; "value"
0x180001fa8  mov     rax, [rcx]
0x180001fab  mov     rax, [rax+40h]
0x180001faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fb4  mov     ebx, eax
0x180001fb6  test    eax, eax
0x180001fb8  js      loc_1800020CA
0x180001fbe  mov     ecx, 0C8h; Size
0x180001fc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001fc8  mov     rdi, rax
0x180001fcb  test    rax, rax
0x180001fce  jz      loc_1800021AD
0x180001fd4  lea     rdx, [rax+48h]
0x180001fd8  mov     r8d, 40h ; '@'
0x180001fde  lea     rcx, [rax+10h]
0x180001fe2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001fe8  mov     rdx, [rsp+3B0h+var_338]
0x180001fed  lea     rcx, [rdi+10h]
0x180001ff1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001ff7  mov     ebx, eax
0x180001ff9  test    eax, eax
0x180001ffb  js      loc_1800020B8
0x180002001  mov     rax, [r14+8]
0x180002005  cmp     [rax], r14
0x180002008  jnz     loc_1800020B1
0x18000200e  mov     [rdi+8], rax
0x180002012  mov     [rdi], r14
0x180002015  mov     [rax], rdi
0x180002018  mov     rcx, [rsp+3B0h+var_350]
0x18000201d  mov     [r14+8], rdi
0x180002021  mov     rax, [rcx]
0x180002024  mov     rax, [rax+10h]
0x180002028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000202d  inc     esi
0x18000202f  mov     [rsp+3B0h+var_350], r12
0x180002034  cmp     esi, [rsp+3B0h+var_364]
0x180002038  jb      loc_180001F6D
0x18000203e  mov     rcx, [rsp+3B0h+var_360]
0x180002043  mov     rax, [rcx]
0x180002046  mov     rax, [rax+10h]
0x18000204a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000204f  mov     rcx, [rsp+3B0h+var_348]
0x180002054  mov     [rsp+3B0h+var_360], r12
0x180002059  mov     rax, [rcx]
0x18000205c  mov     rax, [rax+10h]
0x180002060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002065  mov     rcx, [rsp+3B0h+var_370]
0x18000206a  mov     [rsp+3B0h+var_348], r12
0x18000206f  mov     rax, [rcx]
0x180002072  mov     rax, [rax+10h]
0x180002076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000207b  mov     rcx, [rsp+3B0h+var_358]
0x180002080  mov     [rsp+3B0h+var_370], r12
0x180002085  mov     rax, [rcx]
0x180002088  mov     rax, [rax+10h]
0x18000208c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002091  lea     rcx, [rbp+2B0h+var_330]
0x180002095  mov     [rsp+3B0h+var_358], r12
0x18000209a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800020a0  lea     rcx, [rbp+2B0h+var_2F8]
0x1800020a4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800020aa  xor     eax, eax
0x1800020ac  jmp     loc_180002182
0x1800020b1  mov     ecx, 3
0x1800020b6  int     29h; Win8: RtlFailFast(ecx)
0x1800020b8  lea     rcx, [rdi+10h]
0x1800020bc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800020c2  mov     rcx, rdi; Block
0x1800020c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800020ca  mov     rcx, [rsp+3B0h+var_350]
0x1800020cf  test    rcx, rcx
0x1800020d2  jz      short loc_1800020E5
0x1800020d4  mov     rax, [rcx]
0x1800020d7  mov     rax, [rax+10h]
0x1800020db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e0  mov     [rsp+3B0h+var_350], r12
0x1800020e5  mov     rcx, [rsp+3B0h+var_360]
0x1800020ea  test    rcx, rcx
0x1800020ed  jz      short loc_180002100
0x1800020ef  mov     rax, [rcx]
0x1800020f2  mov     rax, [rax+10h]
0x1800020f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020fb  mov     [rsp+3B0h+var_360], r12
0x180002100  mov     rcx, [rsp+3B0h+var_348]
0x180002105  test    rcx, rcx
0x180002108  jz      short loc_18000211B
0x18000210a  mov     rax, [rcx]
0x18000210d  mov     rax, [rax+10h]
0x180002111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002116  mov     [rsp+3B0h+var_348], r12
0x18000211b  mov     rcx, [rsp+3B0h+var_340]
0x180002120  test    rcx, rcx
0x180002123  jz      short loc_180002136
0x180002125  mov     rax, [rcx]
0x180002128  mov     rax, [rax+10h]
0x18000212c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002131  mov     [rsp+3B0h+var_340], r12
0x180002136  mov     rcx, [rsp+3B0h+var_370]
0x18000213b  test    rcx, rcx
0x18000213e  jz      short loc_180002151
0x180002140  mov     rax, [rcx]
0x180002143  mov     rax, [rax+10h]
0x180002147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000214c  mov     [rsp+3B0h+var_370], r12
0x180002151  mov     rcx, [rsp+3B0h+var_358]
0x180002156  test    rcx, rcx
0x180002159  jz      short loc_18000216C
0x18000215b  mov     rax, [rcx]
0x18000215e  mov     rax, [rax+10h]
0x180002162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002167  mov     [rsp+3B0h+var_358], r12
0x18000216c  lea     rcx, [rbp+2B0h+var_330]
  ... truncated ...
```
