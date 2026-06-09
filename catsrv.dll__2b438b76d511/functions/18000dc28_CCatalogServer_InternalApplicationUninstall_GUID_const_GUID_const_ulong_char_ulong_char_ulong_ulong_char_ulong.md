# CCatalogServer::InternalApplicationUninstall(_GUID const &,_GUID const &,ulong,char *,ulong,char *,ulong,ulong,char * *,ulong *,char * *,ulong *,char * *,ulong *,char * *,ulong *,char * *,ulong *,int *)

- ea: `0x18000dc28`
- end: `0x18000e460`
- name: `?InternalApplicationUninstall@CCatalogServer@@AEAAJAEBU_GUID@@0KPEADK1KKPEAPEADPEAK23232323PEAH@Z`
- size: `2104`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int, struct __MIDL___MIDL_itf_stable_0000_0000_0002 *Src, size_t Size, char *, unsigned int, unsigned int, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d8c0`

## callees

- `0x180006cd0`
- `0x180008f2c`
- `0x18000dc28`
- `0x1800134d0`
- `0x18001381c`
- `0x18001388c`
- `0x18001ece0`
- `0x18002f158`
- `0x180031b4c`
- `0x180031cdc`
- `0x18005488c`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18000df4e`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18000df4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3bf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e375`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800559b8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000e375`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800559b8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e2c5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000e2c5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e2b3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e2b3`
- `msi!__imp_MsiConfigureProductW` at `0x18000e31a`
- `msi!__imp_MsiConfigureProductW` at `0x18000e31a`
- `msi!__imp_MsiSetInternalUI` at `0x18000e306`
- `msi!__imp_MsiSetInternalUI` at `0x18000e306`
- `msi!__imp_MsiEnumRelatedProductsW` at `0x18000e2f7`
- `msi!__imp_MsiEnumRelatedProductsW` at `0x18000e2f7`

## pseudocode

```c
__int64 __fastcall CCatalogServer::InternalApplicationUninstall(
        CCatalogServer *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        unsigned int a4,
        struct __MIDL___MIDL_itf_stable_0000_0000_0002 *Src,
        size_t Size,
        char *a7,
        unsigned int a8,
        unsigned int a9,
        char **a10,
        unsigned int *a11,
        char **a12,
        unsigned int *a13,
        char **a14,
        unsigned int *a15,
        char **a16,
        unsigned int *a17,
        char **a18,
        unsigned int *a19,
        int *a20)
{
  __int64 v23; // rbx
  int SimpleTableDispenser; // edi
  unsigned int *v25; // r12
  char **v26; // r15
  int v27; // esi
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 result; // rax
  int v33; // edi
  int v34; // [rsp+70h] [rbp-1C8h]
  unsigned int v35; // [rsp+74h] [rbp-1C4h] BYREF
  __int64 v36; // [rsp+78h] [rbp-1C0h] BYREF
  int v37; // [rsp+80h] [rbp-1B8h]
  int v38; // [rsp+84h] [rbp-1B4h] BYREF
  int v39; // [rsp+88h] [rbp-1B0h] BYREF
  __int64 v40; // [rsp+90h] [rbp-1A8h] BYREF
  __int64 v41; // [rsp+98h] [rbp-1A0h] BYREF
  _QWORD *v42; // [rsp+A0h] [rbp-198h] BYREF
  char **v43; // [rsp+A8h] [rbp-190h]
  unsigned int *v44; // [rsp+B0h] [rbp-188h]
  char **v45; // [rsp+B8h] [rbp-180h]
  unsigned int *v46; // [rsp+C0h] [rbp-178h]
  char **v47; // [rsp+C8h] [rbp-170h]
  unsigned int *v48; // [rsp+D0h] [rbp-168h]
  char **v49; // [rsp+D8h] [rbp-160h]
  unsigned int *v50; // [rsp+E0h] [rbp-158h]
  int *v51; // [rsp+E8h] [rbp-150h]
  LPVOID pv; // [rsp+F0h] [rbp-148h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-140h] BYREF
  unsigned int *v54; // [rsp+100h] [rbp-138h]
  char **v55; // [rsp+108h] [rbp-130h]
  unsigned int v56; // [rsp+110h] [rbp-128h] BYREF
  const struct _GUID *v57; // [rsp+118h] [rbp-120h]
  const struct _GUID *v58; // [rsp+120h] [rbp-118h]
  char **v59; // [rsp+128h] [rbp-110h]
  unsigned int *v60; // [rsp+130h] [rbp-108h]
  __int128 v61; // [rsp+138h] [rbp-100h] BYREF
  OLECHAR sz[40]; // [rsp+150h] [rbp-E8h] BYREF
  WCHAR ProductBuf[40]; // [rsp+1A0h] [rbp-98h] BYREF

  v57 = a2;
  v58 = a3;
  v55 = a10;
  v59 = a10;
  v54 = a11;
  v60 = a11;
  v43 = a12;
  v44 = a13;
  v45 = a14;
  v46 = a15;
  v47 = a16;
  v48 = a17;
  v49 = a18;
  v50 = a19;
  v51 = a20;
  v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180075530 > *(_DWORD *)(v23 + 4) )
  {
    Init_thread_header(&dword_180075530);
    if ( dword_180075530 == -1 )
    {
      UTSemReadWrite::UTSemReadWrite((UTSemReadWrite *)qword_180075540);
      atexit(CCatalogServer::InternalApplicationUninstall_::_2_::_dynamic_atexit_destructor_for__s_semRWUninstall__);
      Init_thread_footer(&dword_180075530);
    }
  }
  if ( dword_180075558 > *(_DWORD *)(v23 + 4) )
  {
    Init_thread_header(&dword_180075558);
    if ( dword_180075558 == -1 )
    {
      rguid = GUID_NULL;
      Init_thread_footer(&dword_180075558);
    }
  }
  v61 = 0;
  v53 = 0;
  v36 = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v42 = 0;
  pv = 0;
  v35 = 0;
  v39 = 0;
  if ( (Src || !(_DWORD)Size)
    && (a7 || !a8)
    && a9 == 1
    && (v55 || !v54)
    && (v43 || !v44)
    && (v45 || !v46)
    && (v47 || !v48)
    && (v49 || !v50)
    && v51 )
  {
    if ( *((_DWORD *)this + 58) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    SimpleTableDispenser = PostMarshallQueryValues(
                             Src,
                             (unsigned int)Size,
                             a7,
                             a4,
                             *((_DWORD *)this + 59),
                             (struct __MIDL___MIDL_itf_stable_0000_0000_0002 **)&pv,
                             &v56,
                             &v35,
                             &v39);
    if ( SimpleTableDispenser >= 0 )
    {
      SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v53);
      if ( SimpleTableDispenser >= 0 )
      {
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, const struct _GUID *, LPVOID, _QWORD, int, unsigned int, __int64 *))(*(_QWORD *)v53 + 24LL))(
                                 v53,
                                 v57,
                                 a3,
                                 pv,
                                 v35,
                                 1,
                                 a4 | 8,
                                 &v36);
        if ( SimpleTableDispenser >= 0 )
        {
          SimpleTableDispenser = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v36)(
                                   v36,
                                   &IID_ISimpleTableControl,
                                   &v41);
          if ( SimpleTableDispenser >= 0 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v41 + 112LL))(
                                     v41,
                                     &v61,
                                     &v40);
            if ( SimpleTableDispenser >= 0 )
            {
              v25 = v54;
              v26 = v55;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, char *, _QWORD, char *, unsigned int, char *, unsigned int, char *, unsigned int, char *, unsigned int))(*(_QWORD *)v40 + 32LL))(
                                       v40,
                                       0x20000,
                                       *v55,
                                       *v54,
                                       *v43,
                                       *v44,
                                       *v45,
                                       *v46,
                                       *v47,
                                       *v48,
                                       *v49,
                                       *v50);
              if ( SimpleTableDispenser >= 0 )
              {
                v27 = 0;
                v35 = 0;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 104LL))(v36);
                if ( SimpleTableDispenser >= 0 )
                {
                  while ( 1 )
                  {
                    v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 112LL))(v36, &v38);
                    SimpleTableDispenser = v28;
                    if ( v28 == -2146367487 )
                      break;
                    if ( v28 < 0 )
                      goto LABEL_62;
                    if ( v38 == 3 )
                    {
                      v29 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&TID_APPLICATION.Data1;
                      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&TID_APPLICATION.Data1 )
                        v29 = *(_QWORD *)a3->Data4 - *(_QWORD *)TID_APPLICATION.Data4;
                      if ( !v29 )
                        goto LABEL_42;
                      v30 = *(_QWORD *)&a3->Data1 - TID_LT_APPLICATIONPARTITION;
                      if ( *(_QWORD *)&a3->Data1 == TID_LT_APPLICATIONPARTITION )
                        v30 = *(_QWORD *)a3->Data4 + 0x604A396552DF526BLL;
                      if ( v30 )
                        SimpleTableDispenser = -2147418113;
                      else
LABEL_42:
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)v36 + 152LL))(
                                                 v36,
                                                 0,
                                                 0,
                                                 0,
                                                 0,
                                                 &v42);
                      if ( SimpleTableDispenser < 0 )
                        goto LABEL_62;
                      v31 = *v42 - *(_QWORD *)&rguid.Data1;
                      if ( *v42 == *(_QWORD *)&rguid.Data1 )
                        v31 = v42[1] - *(_QWORD *)rguid.Data4;
                      if ( v31 )
                      {
                        if ( !v27 )
                        {
                          result = TxInitialize();
                          if ( (int)result < 0 )
                            return result;
                          v27 = 1;
                          v35 = 1;
                        }
                        v33 = 0;
                        v37 = 0;
                        UTSemReadWrite::LockWrite((UTSemReadWrite *)qword_180075540);
                        rguid = *(GUID *)v42;
                        v34 = StringFromGUID2(&rguid, sz, 40);
                        if ( v34 >= 0 )
                        {
                          v34 = CoImpersonateClient();
                          if ( v34 >= 0 )
                          {
                            v33 = 1;
                            v37 = 1;
                            if ( !MsiEnumRelatedProductsW(sz, 0, 0, ProductBuf) )
                            {
                              MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
                              if ( !MsiConfigureProductW(ProductBuf, 0, INSTALLSTATE_ABSENT) )
                                v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 64LL))(v41, 0);
                            }
                          }
                        }
                        if ( v33 )
                          CoRevertToSelf();
                        rguid = GUID_NULL;
                        UTSemReadWrite::UnlockWrite((UTSemReadWrite *)qword_180075540);
                        SimpleTableDispenser = v34;
                        if ( v34 < 0 )
                          goto LABEL_62;
                      }
                      else
                      {
                        *v51 = 1;
                      }
                    }
                  }
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *))(*(_QWORD *)v40 + 24LL))(
                                           v40,
                                           0x20000,
                                           v26,
                                           v25,
                                           v43,
                                           v44,
                                           v45,
                                           v46,
                                           v47,
                                           v48,
                                           v49,
                                           v50);
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    SimpleTableDispenser = -2147024809;
  }
LABEL_62:
  if ( v39 && pv )
    CoTaskMemFree(pv);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18000dc28  push    rbx
0x18000dc2a  push    rsi
0x18000dc2b  push    rdi
0x18000dc2c  push    r12
0x18000dc2e  push    r13
0x18000dc30  push    r14
0x18000dc32  push    r15
0x18000dc34  sub     rsp, 200h
0x18000dc3b  mov     rax, cs:__security_cookie
0x18000dc42  xor     rax, rsp
0x18000dc45  mov     [rsp+238h+var_48], rax
0x18000dc4d  mov     r12d, r9d
0x18000dc50  mov     r13, r8
0x18000dc53  mov     [rsp+238h+var_120], rdx
0x18000dc5b  mov     rsi, rcx
0x18000dc5e  mov     [rsp+238h+var_118], r8
0x18000dc66  mov     r15, [rsp+238h+Src]
0x18000dc6e  mov     rdi, [rsp+238h+arg_30]
0x18000dc76  mov     rax, [rsp+238h+arg_48]
0x18000dc7e  mov     [rsp+238h+var_130], rax
0x18000dc86  mov     [rsp+238h+var_110], rax
0x18000dc8e  mov     rax, [rsp+238h+arg_50]
0x18000dc96  mov     [rsp+238h+var_138], rax
0x18000dc9e  mov     [rsp+238h+var_108], rax
0x18000dca6  mov     rax, [rsp+238h+arg_58]
0x18000dcae  mov     [rsp+238h+var_190], rax
0x18000dcb6  mov     rax, [rsp+238h+arg_60]
0x18000dcbe  mov     [rsp+238h+var_188], rax
0x18000dcc6  mov     rax, [rsp+238h+arg_68]
0x18000dcce  mov     [rsp+238h+var_180], rax
0x18000dcd6  mov     rax, [rsp+238h+arg_70]
0x18000dcde  mov     [rsp+238h+var_178], rax
0x18000dce6  mov     rax, [rsp+238h+arg_78]
0x18000dcee  mov     [rsp+238h+var_170], rax
0x18000dcf6  mov     rax, [rsp+238h+arg_80]
0x18000dcfe  mov     [rsp+238h+var_168], rax
0x18000dd06  mov     rax, [rsp+238h+arg_88]
0x18000dd0e  mov     [rsp+238h+var_160], rax
0x18000dd16  mov     rax, [rsp+238h+arg_90]
0x18000dd1e  mov     [rsp+238h+var_158], rax
0x18000dd26  mov     rax, [rsp+238h+arg_98]
0x18000dd2e  mov     [rsp+238h+var_150], rax
0x18000dd36  mov     ecx, cs:_tls_index
0x18000dd3c  mov     rax, gs:58h
0x18000dd45  mov     r14d, 4
0x18000dd4b  mov     rbx, [rax+rcx*8]
0x18000dd4f  mov     eax, cs:dword_180075530
0x18000dd55  cmp     eax, [rbx+r14]
0x18000dd59  jle     short loc_18000DD94
0x18000dd5b  lea     rcx, dword_180075530
0x18000dd62  call    _Init_thread_header
0x18000dd67  cmp     cs:dword_180075530, 0FFFFFFFFh
0x18000dd6e  jnz     short loc_18000DD94
0x18000dd70  lea     rcx, qword_180075540; this
0x18000dd77  call    ??0UTSemReadWrite@@QEAA@K@Z; UTSemReadWrite::UTSemReadWrite(ulong)
0x18000dd7c  lea     rcx, _CCatalogServer__InternalApplicationUninstall____2____dynamic_atexit_destructor_for__s_semRWUninstall__; void (__cdecl *)()
0x18000dd83  call    atexit
0x18000dd88  lea     rcx, dword_180075530
0x18000dd8f  call    _Init_thread_footer
0x18000dd94  mov     eax, cs:dword_180075558
0x18000dd9a  cmp     eax, [rbx+r14]
0x18000dd9e  jle     short loc_18000DDD0
0x18000dda0  lea     rcx, dword_180075558
0x18000dda7  call    _Init_thread_header
0x18000ddac  cmp     cs:dword_180075558, 0FFFFFFFFh
0x18000ddb3  jnz     short loc_18000DDD0
0x18000ddb5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000ddbc  movdqu  xmmword ptr cs:rguid.Data1, xmm0
0x18000ddc4  lea     rcx, dword_180075558
0x18000ddcb  call    _Init_thread_footer
0x18000ddd0  xorps   xmm0, xmm0
0x18000ddd3  movups  [rsp+238h+var_100], xmm0
0x18000dddb  xor     ebx, ebx
0x18000dddd  mov     [rsp+238h+var_140], rbx
0x18000dde5  mov     [rsp+238h+var_1C0], rbx
0x18000ddea  mov     [rsp+238h+var_1A8], rbx
0x18000ddf2  mov     [rsp+238h+var_1A0], rbx
0x18000ddfa  mov     [rsp+238h+var_1B4], ebx
0x18000de01  mov     [rsp+238h+var_198], rbx
0x18000de09  mov     [rsp+238h+pv], rbx
0x18000de11  mov     [rsp+238h+var_1C4], ebx
0x18000de15  mov     [rsp+238h+var_1B0], ebx
0x18000de1c  test    r15, r15
0x18000de1f  jnz     short loc_18000DE2E
0x18000de21  cmp     dword ptr [rsp+238h+Size], ebx
0x18000de28  jnz     loc_18000E3A4
0x18000de2e  test    rdi, rdi
0x18000de31  jnz     short loc_18000DE40
0x18000de33  cmp     [rsp+238h+arg_38], ebx
0x18000de3a  jnz     loc_18000E3A4
0x18000de40  mov     r14d, 1
0x18000de46  cmp     [rsp+238h+arg_40], r14d
0x18000de4e  jnz     loc_18000E3A4
0x18000de54  cmp     [rsp+238h+var_130], rbx
0x18000de5c  jnz     short loc_18000DE6C
0x18000de5e  cmp     [rsp+238h+var_138], rbx
0x18000de66  jnz     loc_18000E3A4
0x18000de6c  cmp     [rsp+238h+var_190], rbx
0x18000de74  jnz     short loc_18000DE84
0x18000de76  cmp     [rsp+238h+var_188], rbx
0x18000de7e  jnz     loc_18000E3A4
0x18000de84  cmp     [rsp+238h+var_180], rbx
0x18000de8c  jnz     short loc_18000DE9C
0x18000de8e  cmp     [rsp+238h+var_178], rbx
0x18000de96  jnz     loc_18000E3A4
0x18000de9c  cmp     [rsp+238h+var_170], rbx
0x18000dea4  jnz     short loc_18000DEB4
0x18000dea6  cmp     [rsp+238h+var_168], rbx
0x18000deae  jnz     loc_18000E3A4
0x18000deb4  cmp     [rsp+238h+var_160], rbx
0x18000debc  jnz     short loc_18000DECC
0x18000debe  cmp     [rsp+238h+var_158], rbx
0x18000dec6  jnz     loc_18000E3A4
0x18000decc  cmp     [rsp+238h+var_150], rbx
0x18000ded4  jz      loc_18000E3A4
0x18000deda  cmp     [rsi+0E8h], r14d
0x18000dee1  jz      short loc_18000DEE8
0x18000dee3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dee8  lea     rax, [rsp+238h+var_1B0]
0x18000def0  mov     [rsp+238h+var_1F8], rax; int *
0x18000def5  lea     rax, [rsp+238h+var_1C4]
0x18000defa  mov     [rsp+238h+var_200], rax; unsigned int *
0x18000deff  lea     rax, [rsp+238h+var_128]
0x18000df07  mov     [rsp+238h+var_208], rax; unsigned int *
0x18000df0c  lea     rax, [rsp+238h+pv]
0x18000df14  mov     [rsp+238h+var_210], rax; struct __MIDL___MIDL_itf_stable_0000_0000_0002 **
0x18000df19  mov     eax, [rsi+0ECh]
0x18000df1f  mov     [rsp+238h+var_218], eax; int
0x18000df23  mov     r8, rdi; void *
0x18000df26  mov     edx, dword ptr [rsp+238h+Size]; Size
0x18000df2d  mov     rcx, r15; Src
0x18000df30  call    ?PostMarshallQueryValues@@YAJPEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@KPEAXKHPEAPEAU1@PEAK3PEAH@Z; PostMarshallQueryValues(__MIDL___MIDL_itf_stable_0000_0000_0002 *,ulong,void *,ulong,int,__MIDL___MIDL_itf_stable_0000_0000_0002 * *,ulong *,ulong *,int *)
0x18000df35  mov     edi, eax
0x18000df37  test    eax, eax
0x18000df39  js      loc_18000E3A9
0x18000df3f  lea     rdx, [rsp+238h+var_140]
0x18000df47  lea     rcx, IID_ISimpleTableDispenser
0x18000df4e  call    cs:__imp_GetSimpleTableDispenser
0x18000df54  mov     edi, eax
0x18000df56  test    eax, eax
0x18000df58  js      loc_18000E3A9
0x18000df5e  mov     rcx, [rsp+238h+var_140]
0x18000df66  mov     rax, [rcx]
0x18000df69  or      r12d, 8
0x18000df6d  mov     r8d, [rsp+238h+var_1C4]
0x18000df72  lea     rdx, [rsp+238h+var_1C0]
0x18000df77  mov     [rsp+238h+var_200], rdx
0x18000df7c  mov     dword ptr [rsp+238h+var_208], r12d
0x18000df81  mov     dword ptr [rsp+238h+var_210], r14d
0x18000df86  mov     qword ptr [rsp+238h+var_218], r8
0x18000df8b  mov     r9, [rsp+238h+pv]
0x18000df93  mov     r8, r13
0x18000df96  mov     rdx, [rsp+238h+var_120]
0x18000df9e  mov     rax, [rax+18h]
0x18000dfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa7  mov     edi, eax
0x18000dfa9  test    eax, eax
0x18000dfab  js      loc_18000E3A9
0x18000dfb1  mov     rcx, [rsp+238h+var_1C0]
0x18000dfb6  mov     rax, [rcx]
0x18000dfb9  lea     r8, [rsp+238h+var_1A0]
0x18000dfc1  lea     rdx, IID_ISimpleTableControl
0x18000dfc8  mov     rax, [rax]
0x18000dfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd0  mov     edi, eax
0x18000dfd2  test    eax, eax
0x18000dfd4  js      loc_18000E3A9
0x18000dfda  mov     rcx, [rsp+238h+var_1A0]
0x18000dfe2  mov     rax, [rcx]
0x18000dfe5  lea     r8, [rsp+238h+var_1A8]
0x18000dfed  lea     rdx, [rsp+238h+var_100]
0x18000dff5  mov     rax, [rax+70h]
0x18000dff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dffe  mov     edi, eax
0x18000e000  test    eax, eax
0x18000e002  js      loc_18000E3A9
0x18000e008  mov     rcx, [rsp+238h+var_1A8]
0x18000e010  mov     rax, [rcx]
0x18000e013  mov     r10, [rax+20h]
0x18000e017  mov     rax, [rsp+238h+var_158]
0x18000e01f  mov     eax, [rax]
0x18000e021  mov     dword ptr [rsp+238h+var_1E0], eax
0x18000e025  mov     rax, [rsp+238h+var_160]
0x18000e02d  mov     rax, [rax]
0x18000e030  mov     [rsp+238h+var_1E8], rax
0x18000e035  mov     rax, [rsp+238h+var_168]
0x18000e03d  mov     eax, [rax]
0x18000e03f  mov     dword ptr [rsp+238h+var_1F0], eax
0x18000e043  mov     rax, [rsp+238h+var_170]
0x18000e04b  mov     rax, [rax]
0x18000e04e  mov     [rsp+238h+var_1F8], rax
0x18000e053  mov     rax, [rsp+238h+var_178]
0x18000e05b  mov     eax, [rax]
0x18000e05d  mov     dword ptr [rsp+238h+var_200], eax
0x18000e061  mov     rax, [rsp+238h+var_180]
0x18000e069  mov     rax, [rax]
0x18000e06c  mov     [rsp+238h+var_208], rax
0x18000e071  mov     rax, [rsp+238h+var_188]
0x18000e079  mov     eax, [rax]
0x18000e07b  mov     dword ptr [rsp+238h+var_210], eax
0x18000e07f  mov     rax, [rsp+238h+var_190]
0x18000e087  mov     rax, [rax]
0x18000e08a  mov     qword ptr [rsp+238h+var_218], rax
0x18000e08f  mov     r12, [rsp+238h+var_138]
0x18000e097  mov     r9d, [r12]
0x18000e09b  mov     r15, [rsp+238h+var_130]
0x18000e0a3  mov     r8, [r15]
0x18000e0a6  mov     edx, 20000h
0x18000e0ab  mov     rax, r10
0x18000e0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b3  mov     edi, eax
0x18000e0b5  test    eax, eax
0x18000e0b7  js      loc_18000E3A9
0x18000e0bd  mov     esi, ebx
0x18000e0bf  mov     [rsp+238h+var_1C4], ebx
0x18000e0c3  mov     rcx, [rsp+238h+var_1C0]
0x18000e0c8  mov     rax, [rcx]
0x18000e0cb  mov     rax, [rax+68h]
0x18000e0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d4  mov     edi, eax
0x18000e0d6  test    eax, eax
0x18000e0d8  js      loc_18000E3A9
0x18000e0de  mov     rcx, [rsp+238h+var_1C0]
0x18000e0e3  mov     rax, [rcx]
0x18000e0e6  lea     rdx, [rsp+238h+var_1B4]
0x18000e0ee  mov     rax, [rax+70h]
0x18000e0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f7  mov     edi, eax
0x18000e0f9  cmp     eax, 80110801h
0x18000e0fe  jnz     loc_18000E192
0x18000e104  mov     rcx, [rsp+238h+var_1A8]
0x18000e10c  mov     rax, [rcx]
0x18000e10f  mov     rdx, [rsp+238h+var_158]
0x18000e117  mov     [rsp+238h+var_1E0], rdx
0x18000e11c  mov     rdx, [rsp+238h+var_160]
0x18000e124  mov     [rsp+238h+var_1E8], rdx
0x18000e129  mov     rdx, [rsp+238h+var_168]
0x18000e131  mov     [rsp+238h+var_1F0], rdx
0x18000e136  mov     rdx, [rsp+238h+var_170]
0x18000e13e  mov     [rsp+238h+var_1F8], rdx
0x18000e143  mov     rdx, [rsp+238h+var_178]
0x18000e14b  mov     [rsp+238h+var_200], rdx
0x18000e150  mov     rdx, [rsp+238h+var_180]
0x18000e158  mov     [rsp+238h+var_208], rdx
0x18000e15d  mov     rdx, [rsp+238h+var_188]
0x18000e165  mov     [rsp+238h+var_210], rdx
0x18000e16a  mov     rdx, [rsp+238h+var_190]
0x18000e172  mov     qword ptr [rsp+238h+var_218], rdx
0x18000e177  mov     r9, r12
0x18000e17a  mov     r8, r15
0x18000e17d  mov     edx, 20000h
0x18000e182  mov     rax, [rax+18h]
0x18000e186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e18b  mov     edi, eax
0x18000e18d  jmp     loc_18000E3A9
0x18000e192  test    eax, eax
0x18000e194  js      loc_18000E3A9
0x18000e19a  cmp     [rsp+238h+var_1B4], 3
0x18000e1a2  jnz     loc_18000E0DE
0x18000e1a8  mov     rax, [r13+0]
0x18000e1ac  sub     rax, qword ptr cs:TID_APPLICATION.Data1
0x18000e1b3  jnz     short loc_18000E1C0
0x18000e1b5  mov     rax, [r13+8]
0x18000e1b9  sub     rax, qword ptr cs:TID_APPLICATION.Data4
0x18000e1c0  test    rax, rax
0x18000e1c3  jz      short loc_18000E1E2
0x18000e1c5  mov     rax, [r13+0]
0x18000e1c9  sub     rax, cs:TID_LT_APPLICATIONPARTITION
0x18000e1d0  jnz     short loc_18000E1DD
0x18000e1d2  mov     rax, [r13+8]
0x18000e1d6  sub     rax, cs:qword_18005C600
0x18000e1dd  test    rax, rax
0x18000e1e0  jnz     short loc_18000E214
0x18000e1e2  mov     rcx, [rsp+238h+var_1C0]
0x18000e1e7  mov     rax, [rcx]
0x18000e1ea  lea     rdx, [rsp+238h+var_198]
0x18000e1f2  mov     [rsp+238h+var_210], rdx
0x18000e1f7  mov     qword ptr [rsp+238h+var_218], rbx
0x18000e1fc  xor     r9d, r9d
0x18000e1ff  xor     r8d, r8d
0x18000e202  xor     edx, edx
0x18000e204  mov     rax, [rax+98h]
0x18000e20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e210  mov     edi, eax
0x18000e212  jmp     short loc_18000E219
0x18000e214  mov     edi, 8000FFFFh
0x18000e219  mov     [rsp+238h+var_1C8], edi
0x18000e21d  test    edi, edi
0x18000e21f  js      loc_18000E3A9
0x18000e225  mov     rcx, [rsp+238h+var_198]
0x18000e22d  mov     rax, [rcx]
0x18000e230  sub     rax, qword ptr cs:rguid.Data1
0x18000e237  jnz     short loc_18000E244
0x18000e239  mov     rax, [rcx+8]
0x18000e23d  sub     rax, qword ptr cs:rguid.Data4
0x18000e244  test    rax, rax
0x18000e247  jnz     short loc_18000E259
0x18000e249  mov     rax, [rsp+238h+var_150]
0x18000e251  mov     [rax], r14d
0x18000e254  jmp     loc_18000E0DE
  ... truncated ...
```
