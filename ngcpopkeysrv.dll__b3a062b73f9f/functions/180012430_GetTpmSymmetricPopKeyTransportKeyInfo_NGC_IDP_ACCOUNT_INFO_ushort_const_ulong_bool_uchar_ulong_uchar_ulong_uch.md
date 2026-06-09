# GetTpmSymmetricPopKeyTransportKeyInfo(_NGC_IDP_ACCOUNT_INFO *,ushort const *,ulong,bool,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,ushort * *,_NGC_KEY_STATUS *)

- ea: `0x180012430`
- end: `0x1800127cd`
- name: `?GetTpmSymmetricPopKeyTransportKeyInfo@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBGK_NPEAPEAEPEAK3434PEAPEAGPEAW4_NGC_KEY_STATUS@@@Z`
- size: `925`
- prototype: `__int64 __fastcall(struct _NGC_IDP_ACCOUNT_INFO *, unsigned __int16 *, unsigned int, bool, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int16 **, enum _NGC_KEY_STATUS *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6b0`
- `0x18000edb4`

## callees

- `0x1800012e8`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000d980`
- `0x18000da94`
- `0x18000db34`
- `0x18000db5c`
- `0x18001069c`
- `0x18001070c`
- `0x180010730`
- `0x180010784`
- `0x180011f70`
- `0x1800122c8`
- `0x180012430`
- `0x18001608c`

## string_xrefs

- `0x18001259e`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`
- `0x18001268a`: `onecore\ds\security\ngc\ngcpopkey\lib\keytransportkey.cpp`

## pseudocode

```c
__int64 __fastcall GetTpmSymmetricPopKeyTransportKeyInfo(
        struct _NGC_IDP_ACCOUNT_INFO *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        bool a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        unsigned int *a10,
        unsigned __int16 **a11,
        enum _NGC_KEY_STATUS *a12)
{
  _DWORD *v15; // r9
  struct NgcKeyTransportKey *v16; // rbx
  int SymmetricPopKeyTransportKeyInfo; // eax
  unsigned int v18; // edi
  unsigned __int8 *v19; // r14
  unsigned __int16 *v20; // rsi
  int KeyAttestationInformation; // eax
  unsigned __int8 *v22; // rbx
  unsigned __int8 **v23; // rdi
  unsigned __int8 *v24; // rcx
  unsigned int *v25; // rdx
  unsigned int *v26; // rdx
  unsigned int *v27; // rdx
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v32; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v35; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 *v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 **v39; // [rsp+70h] [rbp-90h]
  __int64 v40; // [rsp+78h] [rbp-88h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v42; // [rsp+88h] [rbp-78h]
  unsigned int *v43; // [rsp+90h] [rbp-70h]
  struct NgcKeyTransportKey *v44; // [rsp+98h] [rbp-68h] BYREF
  struct _NGC_IDP_ACCOUNT_INFO *v45; // [rsp+A0h] [rbp-60h]
  unsigned int *v46; // [rsp+A8h] [rbp-58h]
  enum _NGC_KEY_STATUS *v47; // [rsp+B0h] [rbp-50h]
  int *v48; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+C8h] [rbp-38h] BYREF
  char v51; // [rsp+CCh] [rbp-34h]
  char v52[16]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v53[4]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v31 = a2;
  v45 = a1;
  v46 = a6;
  v39 = a7;
  v42 = a8;
  v43 = a10;
  v47 = a12;
  *(_DWORD *)a12 = 0;
  std::make_unique<TpmKeyTransKey,,0>(&v44);
  v34 = 0;
  v33 = 0;
  v32 = 0;
  v50 = 0;
  v51 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v50);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    if ( v51 && (v53[0] || v53[1] || v53[2] || v53[3]) )
      v15 = v53;
    else
      v15 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180037000,
      byte_18002EA75,
      v52,
      v15);
  }
  v48 = &v50;
  v49 = 256;
  v16 = v44;
  SymmetricPopKeyTransportKeyInfo = GetSymmetricPopKeyTransportKeyInfo(
                                      (NgcUtils **)v44,
                                      a1,
                                      v31,
                                      a3,
                                      a4,
                                      (unsigned __int8 **)((unsigned __int64)&v33 & -(__int64)(a5 != 0)),
                                      (unsigned int *)((unsigned __int64)&v34
                                                     & ((unsigned __int128)-(__int128)(unsigned __int64)a6 >> 64)),
                                      (unsigned __int16 **)((unsigned __int64)&v32 & -(__int64)(a11 != 0)));
  v18 = SymmetricPopKeyTransportKeyInfo;
  if ( SymmetricPopKeyTransportKeyInfo >= 0 )
  {
    v19 = 0;
    v38 = 0;
    if ( a5 )
    {
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v38,
        v33);
      v19 = v38;
    }
    v20 = 0;
    v33 = 0;
    if ( a11 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v33,
        v32);
      v20 = v33;
    }
    v35 = 0;
    v40 = 0;
    v36 = 0;
    v41 = 0;
    v37 = 0;
    KeyAttestationInformation = GetKeyAttestationInformation(
                                  v45,
                                  v31,
                                  *((_QWORD *)v16 + 1),
                                  (unsigned __int8 **)((unsigned __int64)&v40 & -(__int64)(v39 != 0)),
                                  (unsigned int *)((unsigned __int64)&v35 & -(__int64)(v42 != 0)),
                                  (unsigned __int8 **)((unsigned __int64)&v41 & -(__int64)(a9 != 0)),
                                  (unsigned int *)((unsigned __int64)&v36 & -(__int64)(v43 != 0)),
                                  (enum _NGC_KEY_STATUS *)&v37);
    if ( KeyAttestationInformation < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
        (const char *)(unsigned int)KeyAttestationInformation,
        v30);
    v22 = 0;
    v32 = 0;
    v23 = v39;
    if ( v39 )
    {
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v32,
        v40);
      v22 = v32;
    }
    v24 = 0;
    v31 = 0;
    if ( a9 )
    {
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v31,
        v41);
      v24 = (unsigned __int8 *)v31;
    }
    if ( a5 )
    {
      v25 = v46;
      if ( v46 )
      {
        v38 = 0;
        *a5 = v19;
        *v25 = v34;
      }
    }
    if ( v23 )
    {
      v26 = v42;
      if ( v42 )
      {
        v32 = 0;
        *v23 = v22;
        *v26 = v35;
      }
    }
    if ( a9 )
    {
      v27 = v43;
      if ( v43 )
      {
        v31 = 0;
        *a9 = v24;
        *v27 = v36;
      }
    }
    if ( a11 )
    {
      v33 = 0;
      *a11 = v20;
    }
    *(_DWORD *)v47 = v37;
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v31, 0);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v32, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v38, 0);
    v18 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\keytransportkey.cpp",
      (const char *)(unsigned int)SymmetricPopKeyTransportKeyInfo,
      v29);
  }
  wil::details::ScopeExitFnGuard__lambda_78ef72ae1329c6eab3b1fc51c7151060___::operator()(&v48);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v50);
  std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(&v44);
  return v18;
}

```

## disassembly

```asm
0x180012430  push    rbp
0x180012432  push    rbx
0x180012433  push    rsi
0x180012434  push    rdi
0x180012435  push    r12
0x180012437  push    r13
0x180012439  push    r14
0x18001243b  push    r15
0x18001243d  lea     rbp, [rsp-8]
0x180012442  sub     rsp, 108h
0x180012449  mov     rax, cs:__security_cookie
0x180012450  xor     rax, rsp
0x180012453  mov     [rbp+40h+var_50], rax
0x180012457  mov     sil, r9b
0x18001245a  mov     edi, r8d
0x18001245d  mov     [rsp+140h+var_100], rdx
0x180012462  mov     r14, rcx
0x180012465  mov     [rbp+40h+var_A0], rcx
0x180012469  mov     r13, [rbp+40h+arg_20]
0x18001246d  mov     rbx, [rbp+40h+arg_28]
0x180012471  mov     [rbp+40h+var_98], rbx
0x180012475  mov     rax, [rbp+40h+arg_30]
0x18001247c  mov     [rsp+140h+var_D0], rax
0x180012481  mov     rax, [rbp+40h+arg_38]
0x180012488  mov     [rbp+40h+var_B8], rax
0x18001248c  mov     r12, [rbp+40h+arg_40]
0x180012493  mov     rax, [rbp+40h+arg_48]
0x18001249a  mov     [rbp+40h+var_B0], rax
0x18001249e  mov     r15, [rbp+40h+arg_50]
0x1800124a5  mov     rax, [rbp+40h+arg_58]
0x1800124ac  mov     [rbp+40h+var_90], rax
0x1800124b0  mov     dword ptr [rax], 0
0x1800124b6  lea     rcx, [rbp+40h+var_A8]
0x1800124ba  call    ??$make_unique@VTpmKeyTransKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VTpmKeyTransKey@@U?$default_delete@VTpmKeyTransKey@@@std@@@0@XZ; std::make_unique<TpmKeyTransKey,,0>(void)
0x1800124bf  nop
0x1800124c0  xor     eax, eax
0x1800124c2  mov     [rsp+140h+var_E8], eax
0x1800124c6  mov     [rsp+140h+var_F0], rax
0x1800124cb  mov     [rsp+140h+var_F8], rax
0x1800124d0  mov     [rbp+40h+var_78], eax
0x1800124d3  mov     [rbp+40h+var_74], al
0x1800124d6  lea     rcx, [rbp+40h+var_78]
0x1800124da  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800124df  mov     eax, cs:dword_180037000
0x1800124e5  cmp     eax, 5
0x1800124e8  jbe     short loc_180012525
0x1800124ea  xor     eax, eax
0x1800124ec  cmp     [rbp+40h+var_74], al
0x1800124ef  jz      short loc_18001250B
0x1800124f1  cmp     [rbp+40h+var_60], eax
0x1800124f4  jnz     short loc_180012505
0x1800124f6  cmp     [rbp+40h+var_5C], eax
0x1800124f9  jnz     short loc_180012505
0x1800124fb  cmp     [rbp+40h+var_58], eax
0x1800124fe  jnz     short loc_180012505
0x180012500  cmp     [rbp+40h+var_54], eax
0x180012503  jz      short loc_18001250B
0x180012505  lea     r9, [rbp+40h+var_60]
0x180012509  jmp     short loc_18001250E
0x18001250b  mov     r9, rax
0x18001250e  lea     r8, [rbp+40h+var_70]
0x180012512  lea     rdx, byte_18002EA75
0x180012519  lea     rcx, dword_180037000
0x180012520  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180012525  lea     rax, [rbp+40h+var_78]
0x180012529  mov     [rbp+40h+var_88], rax
0x18001252d  mov     [rbp+40h+var_80], 100h
0x180012533  mov     rax, r15
0x180012536  neg     rax
0x180012539  sbb     r8, r8
0x18001253c  lea     rax, [rsp+140h+var_F8]
0x180012541  and     r8, rax
0x180012544  mov     rax, rbx
0x180012547  neg     rax
0x18001254a  sbb     rdx, rdx
0x18001254d  lea     rax, [rsp+140h+var_E8]
0x180012552  and     rdx, rax
0x180012555  mov     rax, r13
0x180012558  neg     rax
0x18001255b  sbb     rcx, rcx
0x18001255e  lea     rax, [rsp+140h+var_F0]
0x180012563  and     rcx, rax
0x180012566  mov     [rsp+140h+var_108], r8; unsigned __int16 **
0x18001256b  mov     [rsp+140h+var_110], rdx; unsigned int *
0x180012570  mov     [rsp+140h+var_118], rcx; unsigned __int8 **
0x180012575  mov     byte ptr [rsp+140h+var_120], sil; int
0x18001257a  mov     r9d, edi; unsigned int
0x18001257d  mov     r8, [rsp+140h+var_100]; unsigned __int16 *
0x180012582  mov     rdx, r14; struct _NGC_IDP_ACCOUNT_INFO *
0x180012585  mov     rbx, [rbp+40h+var_A8]
0x180012589  mov     rcx, rbx; this
0x18001258c  call    ?GetSymmetricPopKeyTransportKeyInfo@@YAJPEAVNgcKeyTransportKey@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBGK_NPEAPEAEPEAKPEAPEAG@Z; GetSymmetricPopKeyTransportKeyInfo(NgcKeyTransportKey *,_NGC_IDP_ACCOUNT_INFO *,ushort const *,ulong,bool,uchar * *,ulong *,ushort * *)
0x180012591  mov     edi, eax
0x180012593  test    eax, eax
0x180012595  jns     short loc_1800125B4
0x180012597  mov     rcx, [rbp+48h]; this
0x18001259b  mov     r9d, eax; char *
0x18001259e  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800125a5  mov     edx, 13Dh; void *
0x1800125aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125af  jmp     loc_18001278E
0x1800125b4  xor     edi, edi
0x1800125b6  mov     r14d, edi
0x1800125b9  mov     [rsp+140h+var_D8], rdi
0x1800125be  test    r13, r13
0x1800125c1  jz      short loc_1800125D7
0x1800125c3  mov     rdx, [rsp+140h+var_F0]
0x1800125c8  lea     rcx, [rsp+140h+var_D8]
0x1800125cd  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800125d2  mov     r14, [rsp+140h+var_D8]
0x1800125d7  mov     rsi, rdi
0x1800125da  mov     [rsp+140h+var_F0], rdi
0x1800125df  test    r15, r15
0x1800125e2  jz      short loc_1800125F8
0x1800125e4  mov     rdx, [rsp+140h+var_F8]
0x1800125e9  lea     rcx, [rsp+140h+var_F0]
0x1800125ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800125f3  mov     rsi, [rsp+140h+var_F0]
0x1800125f8  mov     [rsp+140h+var_E4], edi
0x1800125fc  mov     [rsp+140h+var_C8], rdi
0x180012601  mov     [rsp+140h+var_E0], edi
0x180012605  mov     [rbp+40h+var_C0], rdi
0x180012609  mov     [rsp+140h+var_DC], edi
0x18001260d  mov     rax, [rbp+40h+var_B0]
0x180012611  neg     rax
0x180012614  sbb     rdi, rdi
0x180012617  lea     rax, [rsp+140h+var_E0]
0x18001261c  and     rdi, rax
0x18001261f  mov     rax, r12
0x180012622  neg     rax
0x180012625  sbb     r11, r11
0x180012628  lea     rax, [rbp+40h+var_C0]
0x18001262c  and     r11, rax
0x18001262f  mov     rax, [rbp+40h+var_B8]
0x180012633  neg     rax
0x180012636  sbb     r10, r10
0x180012639  lea     rax, [rsp+140h+var_E4]
0x18001263e  and     r10, rax
0x180012641  mov     rax, [rsp+140h+var_D0]
0x180012646  neg     rax
0x180012649  sbb     r9, r9
0x18001264c  lea     rax, [rsp+140h+var_C8]
0x180012651  and     r9, rax; unsigned __int8 **
0x180012654  lea     rax, [rsp+140h+var_DC]
0x180012659  mov     [rsp+140h+var_108], rax; enum _NGC_KEY_STATUS *
0x18001265e  mov     [rsp+140h+var_110], rdi; unsigned int *
0x180012663  mov     [rsp+140h+var_118], r11; unsigned __int8 **
0x180012668  mov     [rsp+140h+var_120], r10; int
0x18001266d  mov     r8, [rbx+8]; unsigned __int64
0x180012671  mov     rdx, [rsp+140h+var_100]; unsigned __int16 *
0x180012676  mov     rcx, [rbp+40h+var_A0]; struct _NGC_IDP_ACCOUNT_INFO *
0x18001267a  call    ?GetKeyAttestationInformation@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_KPEAPEAEPEAK34PEAW4_NGC_KEY_STATUS@@@Z; GetKeyAttestationInformation(_NGC_IDP_ACCOUNT_INFO *,ushort const *,unsigned __int64,uchar * *,ulong *,uchar * *,ulong *,_NGC_KEY_STATUS *)
0x18001267f  mov     rcx, [rbp+48h]; this
0x180012683  test    eax, eax
0x180012685  jns     short loc_18001269B
0x180012687  mov     r9d, eax; char *
0x18001268a  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012691  mov     edx, 15Ah; void *
0x180012696  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001269b  xor     ebx, ebx
0x18001269d  mov     [rsp+140h+var_F8], rbx
0x1800126a2  mov     rdi, [rsp+140h+var_D0]
0x1800126a7  test    rdi, rdi
0x1800126aa  jz      short loc_1800126C0
0x1800126ac  mov     rdx, [rsp+140h+var_C8]
0x1800126b1  lea     rcx, [rsp+140h+var_F8]
0x1800126b6  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800126bb  mov     rbx, [rsp+140h+var_F8]
0x1800126c0  xor     ecx, ecx
0x1800126c2  mov     [rsp+140h+var_100], rcx
0x1800126c7  test    r12, r12
0x1800126ca  jz      short loc_1800126DF
0x1800126cc  mov     rdx, [rbp+40h+var_C0]
0x1800126d0  lea     rcx, [rsp+140h+var_100]
0x1800126d5  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800126da  mov     rcx, [rsp+140h+var_100]
0x1800126df  test    r13, r13
0x1800126e2  jz      short loc_180012700
0x1800126e4  mov     rdx, [rbp+40h+var_98]
0x1800126e8  test    rdx, rdx
0x1800126eb  jz      short loc_180012700
0x1800126ed  mov     [rsp+140h+var_D8], 0
0x1800126f6  mov     [r13+0], r14
0x1800126fa  mov     eax, [rsp+140h+var_E8]
0x1800126fe  mov     [rdx], eax
0x180012700  test    rdi, rdi
0x180012703  jz      short loc_180012720
0x180012705  mov     rdx, [rbp+40h+var_B8]
0x180012709  test    rdx, rdx
0x18001270c  jz      short loc_180012720
0x18001270e  mov     [rsp+140h+var_F8], 0
0x180012717  mov     [rdi], rbx
0x18001271a  mov     eax, [rsp+140h+var_E4]
0x18001271e  mov     [rdx], eax
0x180012720  test    r12, r12
0x180012723  jz      short loc_180012741
0x180012725  mov     rdx, [rbp+40h+var_B0]
0x180012729  test    rdx, rdx
0x18001272c  jz      short loc_180012741
0x18001272e  mov     [rsp+140h+var_100], 0
0x180012737  mov     [r12], rcx
0x18001273b  mov     eax, [rsp+140h+var_E0]
0x18001273f  mov     [rdx], eax
0x180012741  test    r15, r15
0x180012744  jz      short loc_180012752
0x180012746  mov     [rsp+140h+var_F0], 0
0x18001274f  mov     [r15], rsi
0x180012752  mov     eax, [rsp+140h+var_DC]
0x180012756  mov     rcx, [rbp+40h+var_90]
0x18001275a  mov     [rcx], eax
0x18001275c  xor     edx, edx
0x18001275e  lea     rcx, [rsp+140h+var_100]
0x180012763  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012768  xor     edx, edx
0x18001276a  lea     rcx, [rsp+140h+var_F8]
0x18001276f  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012774  nop
0x180012775  lea     rcx, [rsp+140h+var_F0]
0x18001277a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001277f  nop
0x180012780  xor     edx, edx
0x180012782  lea     rcx, [rsp+140h+var_D8]
0x180012787  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001278c  xor     edi, edi
0x18001278e  lea     rcx, [rbp+40h+var_88]
0x180012792  call    wil__details__ScopeExitFnGuard__lambda_78ef72ae1329c6eab3b1fc51c7151060_____operator__
0x180012797  nop
0x180012798  lea     rcx, [rbp+40h+var_78]
0x18001279c  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x1800127a1  nop
0x1800127a2  lea     rcx, [rbp+40h+var_A8]
0x1800127a6  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x1800127ab  mov     eax, edi
0x1800127ad  mov     rcx, [rbp+40h+var_50]
0x1800127b1  xor     rcx, rsp; StackCookie
0x1800127b4  call    __security_check_cookie
0x1800127b9  add     rsp, 108h
0x1800127c0  pop     r15
0x1800127c2  pop     r14
0x1800127c4  pop     r13
0x1800127c6  pop     r12
0x1800127c8  pop     rdi
0x1800127c9  pop     rsi
0x1800127ca  pop     rbx
0x1800127cb  pop     rbp
0x1800127cc  retn
```
