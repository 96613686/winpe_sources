# ACCESS_META_STORED_CONTEXT::InitializeIpRestrictionList(IHttpContext *,INativeSectionException * *)

- ea: `0x1800030a0`
- end: `0x1800034b2`
- name: `?InitializeIpRestrictionList@ACCESS_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1042`
- prototype: `__int64 __fastcall(ACCESS_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002f68`

## callees

- `0x180001088`
- `0x1800030a0`
- `0x1800034b8`
- `0x1800034fc`
- `0x180005010`

## string_xrefs

- `0x180003159`: `system.webServer/security/ipSecurity`

## pseudocode

```c
__int64 __fastcall ACCESS_META_STORED_CONTEXT::InitializeIpRestrictionList(
        ACCESS_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // r14
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // ebx
  __int64 v11; // rcx
  unsigned int v12; // r15d
  IP_RESTRICTION_LIST *v13; // r14
  unsigned __int64 v14; // rax
  __int64 v15; // rbx
  bool v16; // cf
  size_t v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rdi
  IP_RESTRICTION_LIST_ENTRY *v20; // rsi
  unsigned int v21; // edi
  int v23; // [rsp+40h] [rbp-40h] BYREF
  __int64 v24; // [rsp+48h] [rbp-38h] BYREF
  __int64 v25; // [rsp+50h] [rbp-30h] BYREF
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  __int64 v27; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v29; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int16 *v30; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v31; // [rsp+B8h] [rbp+38h] BYREF
  int v32; // [rsp+C8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v27 = 0;
  v24 = 0;
  v26 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v25 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v23 = 0;
  v32 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v27);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v27 + 24LL))(
            v27,
            L"system.webServer/security/ipSecurity",
            v8,
            &v24,
            a3,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v24 + 72LL))(
              v24,
              L"enableReverseDns",
              (char *)this + 40,
              0,
              0);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v24 + 72LL))(
                v24,
                L"allowUnlisted",
                &v32,
                0,
                0);
        if ( v10 >= 0 )
        {
          v11 = v24;
          *((_DWORD *)this + 8) = v32;
          v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v11 + 72LL))(
                  v11,
                  L"enableProxyMode",
                  (char *)this + 44,
                  0,
                  0);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v24 + 48LL))(
                    v24,
                    L"denyAction",
                    (char *)this + 48,
                    0,
                    0);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 40LL))(v24, &v26);
              if ( v10 >= 0 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                v24 = 0;
                v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 24LL))(v26, &v31);
                if ( v10 >= 0 )
                {
                  v12 = v31;
                  v13 = (ACCESS_META_STORED_CONTEXT *)((char *)this + 16);
                  v14 = (unsigned __int64)v31 << 8;
                  v15 = v31;
                  if ( !is_mul_ok(v31, 0x100u) )
                    v14 = -1;
                  v16 = __CFADD__(v14, 8);
                  v17 = v14 + 8;
                  if ( v16 )
                    v17 = -1;
                  v18 = operator new(v17);
                  if ( v18 )
                  {
                    *v18 = v15;
                    v19 = v18 + 1;
                    v20 = (IP_RESTRICTION_LIST_ENTRY *)(v18 + 1);
                    if ( v12 )
                    {
                      do
                      {
                        IP_RESTRICTION_LIST_ENTRY::IP_RESTRICTION_LIST_ENTRY(v20);
                        v20 = (IP_RESTRICTION_LIST_ENTRY *)((char *)v20 + 256);
                        --v15;
                      }
                      while ( v15 );
                    }
                  }
                  else
                  {
                    v19 = 0;
                  }
                  *((_QWORD *)v13 + 1) = v19;
                  if ( v19 )
                    *(_DWORD *)v13 = v12;
                  v21 = 0;
                  if ( !v31 )
                  {
LABEL_28:
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                    v26 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                    return 0;
                  }
                  while ( 1 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 32LL))(
                            v26,
                            v21,
                            &v25);
                    if ( v10 < 0 )
                      break;
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v25 + 72LL))(
                            v25,
                            L"allowed",
                            &v23,
                            0,
                            0);
                    if ( v10 < 0 )
                      break;
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
                            v25,
                            L"ipAddress",
                            &v30,
                            0,
                            0);
                    if ( v10 < 0 )
                      break;
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
                            v25,
                            L"subnetMask",
                            &v29,
                            0,
                            0);
                    if ( v10 < 0 )
                      break;
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
                            v25,
                            L"domainName",
                            &v28,
                            0,
                            0);
                    if ( v10 < 0 )
                      break;
                    v10 = IP_RESTRICTION_LIST::AddEntry(v13, v23, v30, v29, v28);
                    if ( v10 < 0 )
                      break;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                    ++v21;
                    v25 = 0;
                    if ( v21 >= v31 )
                      goto LABEL_28;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800030a0  mov     [rsp-28h+arg_0], rbx
0x1800030a5  mov     [rsp-28h+arg_10], rsi
0x1800030aa  push    rbp
0x1800030ab  push    rdi
0x1800030ac  push    r12
0x1800030ae  push    r14
0x1800030b0  push    r15
0x1800030b2  mov     rbp, rsp
0x1800030b5  sub     rsp, 80h
0x1800030bc  mov     rax, [rdx]
0x1800030bf  xor     r12d, r12d
0x1800030c2  mov     rdi, rcx
0x1800030c5  mov     [rbp+var_20], r12
0x1800030c9  mov     rcx, rdx
0x1800030cc  mov     [rbp+var_38], r12
0x1800030d0  mov     rsi, r8
0x1800030d3  mov     [rbp+var_28], r12
0x1800030d7  mov     rax, [rax+0A0h]
0x1800030de  mov     [rbp+var_30], r12
0x1800030e2  mov     [rbp+arg_8], r12d
0x1800030e6  mov     [rbp+var_8], r12
0x1800030ea  mov     [rbp+var_10], r12
0x1800030ee  mov     [rbp+var_18], r12
0x1800030f2  mov     [rbp+var_40], r12d
0x1800030f6  mov     [rbp+arg_18], r12d
0x1800030fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ff  mov     rdx, rax
0x180003102  mov     rcx, [rax]
0x180003105  mov     rax, [rcx]
0x180003108  mov     rcx, rdx
0x18000310b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003110  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180003117  mov     r14, rax
0x18000311a  mov     rdx, [rcx]
0x18000311d  mov     rax, [rdx+38h]
0x180003121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003126  mov     r9, rax
0x180003129  lea     r8, [rbp+var_20]
0x18000312d  lea     rdx, IID_INativeConfigurationSystem
0x180003134  mov     rcx, [rax]
0x180003137  mov     rax, [rcx]
0x18000313a  mov     rcx, r9
0x18000313d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003142  mov     ebx, eax
0x180003144  test    eax, eax
0x180003146  js      loc_180003434
0x18000314c  mov     rcx, [rbp+var_20]
0x180003150  lea     r9, [rbp+var_38]
0x180003154  mov     [rsp+80h+var_58], r12
0x180003159  lea     rdx, aSystemWebserve; "system.webServer/security/ipSecurity"
0x180003160  mov     r8, r14
0x180003163  mov     [rsp+80h+var_60], rsi
0x180003168  mov     rax, [rcx]
0x18000316b  mov     rax, [rax+18h]
0x18000316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003174  mov     ebx, eax
0x180003176  test    eax, eax
0x180003178  js      loc_180003434
0x18000317e  mov     rcx, [rbp+var_38]
0x180003182  lea     r8, [rdi+28h]
0x180003186  xor     r9d, r9d
0x180003189  mov     [rsp+80h+var_60], r12
0x18000318e  lea     rdx, aEnablereversed; "enableReverseDns"
0x180003195  mov     rax, [rcx]
0x180003198  mov     rax, [rax+48h]
0x18000319c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a1  mov     ebx, eax
0x1800031a3  test    eax, eax
0x1800031a5  js      loc_180003434
0x1800031ab  mov     rcx, [rbp+var_38]
0x1800031af  lea     r8, [rbp+arg_18]
0x1800031b3  xor     r9d, r9d
0x1800031b6  mov     [rsp+80h+var_60], r12
0x1800031bb  lea     rdx, aAllowunlisted; "allowUnlisted"
0x1800031c2  mov     rax, [rcx]
0x1800031c5  mov     rax, [rax+48h]
0x1800031c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ce  mov     ebx, eax
0x1800031d0  test    eax, eax
0x1800031d2  js      loc_180003434
0x1800031d8  mov     eax, [rbp+arg_18]
0x1800031db  lea     r8, [rdi+2Ch]
0x1800031df  mov     rcx, [rbp+var_38]
0x1800031e3  lea     rdx, aEnableproxymod; "enableProxyMode"
0x1800031ea  mov     [rdi+20h], eax
0x1800031ed  xor     r9d, r9d
0x1800031f0  mov     [rsp+80h+var_60], r12
0x1800031f5  mov     rax, [rcx]
0x1800031f8  mov     rax, [rax+48h]
0x1800031fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003201  mov     ebx, eax
0x180003203  test    eax, eax
0x180003205  js      loc_180003434
0x18000320b  mov     rcx, [rbp+var_38]
0x18000320f  lea     r8, [rdi+30h]
0x180003213  xor     r9d, r9d
0x180003216  mov     [rsp+80h+var_60], r12
0x18000321b  lea     rdx, aDenyaction; "denyAction"
0x180003222  mov     rax, [rcx]
0x180003225  mov     rax, [rax+30h]
0x180003229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000322e  mov     ebx, eax
0x180003230  test    eax, eax
0x180003232  js      loc_180003434
0x180003238  mov     rcx, [rbp+var_38]
0x18000323c  lea     rdx, [rbp+var_28]
0x180003240  mov     rax, [rcx]
0x180003243  mov     rax, [rax+28h]
0x180003247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000324c  mov     ebx, eax
0x18000324e  test    eax, eax
0x180003250  js      loc_180003434
0x180003256  mov     rcx, [rbp+var_38]
0x18000325a  mov     rax, [rcx]
0x18000325d  mov     rax, [rax+10h]
0x180003261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003266  mov     rcx, [rbp+var_28]
0x18000326a  lea     rdx, [rbp+arg_8]
0x18000326e  mov     [rbp+var_38], r12
0x180003272  mov     rax, [rcx]
0x180003275  mov     rax, [rax+18h]
0x180003279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000327e  mov     ebx, eax
0x180003280  test    eax, eax
0x180003282  js      loc_180003434
0x180003288  mov     r15d, [rbp+arg_8]
0x18000328c  lea     rcx, [r12-1]
0x180003291  mov     eax, 100h
0x180003296  lea     r14, [rdi+10h]
0x18000329a  mul     r15
0x18000329d  mov     ebx, r15d
0x1800032a0  cmovb   rax, rcx
0x1800032a4  add     rax, 8
0x1800032a8  cmovb   rax, rcx
0x1800032ac  mov     rcx, rax; Size
0x1800032af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800032b4  test    rax, rax
0x1800032b7  jz      short loc_1800032DF
0x1800032b9  mov     [rax], rbx
0x1800032bc  lea     rdi, [rax+8]
0x1800032c0  mov     rsi, rdi
0x1800032c3  test    r15d, r15d
0x1800032c6  jz      short loc_1800032E2
0x1800032c8  mov     rcx, rsi; this
0x1800032cb  call    ??0IP_RESTRICTION_LIST_ENTRY@@QEAA@XZ; IP_RESTRICTION_LIST_ENTRY::IP_RESTRICTION_LIST_ENTRY(void)
0x1800032d0  add     rsi, 100h
0x1800032d7  sub     rbx, 1
0x1800032db  jnz     short loc_1800032C8
0x1800032dd  jmp     short loc_1800032E2
0x1800032df  mov     rdi, r12
0x1800032e2  mov     [r14+8], rdi
0x1800032e6  test    rdi, rdi
0x1800032e9  jz      short loc_1800032EE
0x1800032eb  mov     [r14], r15d
0x1800032ee  mov     edi, r12d
0x1800032f1  cmp     [rbp+arg_8], r12d
0x1800032f5  jbe     loc_18000340C
0x1800032fb  mov     rcx, [rbp+var_28]
0x1800032ff  lea     r8, [rbp+var_30]
0x180003303  mov     edx, edi
0x180003305  mov     rax, [rcx]
0x180003308  mov     rax, [rax+20h]
0x18000330c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003311  mov     ebx, eax
0x180003313  test    eax, eax
0x180003315  js      loc_180003434
0x18000331b  mov     rcx, [rbp+var_30]
0x18000331f  lea     r8, [rbp+var_40]
0x180003323  xor     r9d, r9d
0x180003326  mov     [rsp+80h+var_60], r12
0x18000332b  lea     rdx, aAllowed; "allowed"
0x180003332  mov     rax, [rcx]
0x180003335  mov     rax, [rax+48h]
0x180003339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333e  mov     ebx, eax
0x180003340  test    eax, eax
0x180003342  js      loc_180003434
0x180003348  mov     rcx, [rbp+var_30]
0x18000334c  lea     r8, [rbp+var_8]
0x180003350  xor     r9d, r9d
0x180003353  mov     [rsp+80h+var_60], r12
0x180003358  lea     rdx, aIpaddress_0; "ipAddress"
0x18000335f  mov     rax, [rcx]
0x180003362  mov     rax, [rax+40h]
0x180003366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000336b  mov     ebx, eax
0x18000336d  test    eax, eax
0x18000336f  js      loc_180003434
0x180003375  mov     rcx, [rbp+var_30]
0x180003379  lea     r8, [rbp+var_10]
0x18000337d  xor     r9d, r9d
0x180003380  mov     [rsp+80h+var_60], r12
0x180003385  lea     rdx, aSubnetmask; "subnetMask"
0x18000338c  mov     rax, [rcx]
0x18000338f  mov     rax, [rax+40h]
0x180003393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003398  mov     ebx, eax
0x18000339a  test    eax, eax
0x18000339c  js      loc_180003434
0x1800033a2  mov     rcx, [rbp+var_30]
0x1800033a6  lea     r8, [rbp+var_18]
0x1800033aa  xor     r9d, r9d
0x1800033ad  mov     [rsp+80h+var_60], r12
0x1800033b2  lea     rdx, aDomainname; "domainName"
0x1800033b9  mov     rax, [rcx]
0x1800033bc  mov     rax, [rax+40h]
0x1800033c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c5  mov     ebx, eax
0x1800033c7  test    eax, eax
0x1800033c9  js      short loc_180003434
0x1800033cb  mov     rax, [rbp+var_18]
0x1800033cf  mov     rcx, r14; this
0x1800033d2  mov     r9, [rbp+var_10]; unsigned __int16 *
0x1800033d6  mov     r8, [rbp+var_8]; unsigned __int16 *
0x1800033da  mov     edx, [rbp+var_40]; int
0x1800033dd  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800033e2  call    ?AddEntry@IP_RESTRICTION_LIST@@QEAAJHPEBG00@Z; IP_RESTRICTION_LIST::AddEntry(int,ushort const *,ushort const *,ushort const *)
0x1800033e7  mov     ebx, eax
0x1800033e9  test    eax, eax
0x1800033eb  js      short loc_180003434
0x1800033ed  mov     rcx, [rbp+var_30]
0x1800033f1  mov     rax, [rcx]
0x1800033f4  mov     rax, [rax+10h]
0x1800033f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fd  inc     edi
0x1800033ff  mov     [rbp+var_30], r12
0x180003403  cmp     edi, [rbp+arg_8]
0x180003406  jb      loc_1800032FB
0x18000340c  mov     rcx, [rbp+var_28]
0x180003410  mov     rax, [rcx]
0x180003413  mov     rax, [rax+10h]
0x180003417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341c  mov     rcx, [rbp+var_20]
0x180003420  mov     [rbp+var_28], r12
0x180003424  mov     rax, [rcx]
0x180003427  mov     rax, [rax+10h]
0x18000342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003430  xor     eax, eax
0x180003432  jmp     short loc_180003496
0x180003434  mov     rcx, [rbp+var_30]
0x180003438  test    rcx, rcx
0x18000343b  jz      short loc_18000344D
0x18000343d  mov     rax, [rcx]
0x180003440  mov     rax, [rax+10h]
0x180003444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003449  mov     [rbp+var_30], r12
0x18000344d  mov     rcx, [rbp+var_28]
0x180003451  test    rcx, rcx
0x180003454  jz      short loc_180003466
0x180003456  mov     rax, [rcx]
0x180003459  mov     rax, [rax+10h]
0x18000345d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003462  mov     [rbp+var_28], r12
0x180003466  mov     rcx, [rbp+var_38]
0x18000346a  test    rcx, rcx
0x18000346d  jz      short loc_18000347F
0x18000346f  mov     rax, [rcx]
0x180003472  mov     rax, [rax+10h]
0x180003476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347b  mov     [rbp+var_38], r12
0x18000347f  mov     rcx, [rbp+var_20]
0x180003483  test    rcx, rcx
0x180003486  jz      short loc_180003494
0x180003488  mov     rax, [rcx]
0x18000348b  mov     rax, [rax+10h]
0x18000348f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003494  mov     eax, ebx
0x180003496  lea     r11, [rsp+80h+var_s0]
0x18000349e  mov     rbx, [r11+30h]
0x1800034a2  mov     rsi, [r11+40h]
0x1800034a6  mov     rsp, r11
0x1800034a9  pop     r15
0x1800034ab  pop     r14
0x1800034ad  pop     r12
0x1800034af  pop     rdi
0x1800034b0  pop     rbp
0x1800034b1  retn
```
