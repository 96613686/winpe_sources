# CTSThread::TSStaticThreadEntry(void *)

- ea: `0x180027150`
- end: `0x18002740b`
- name: `?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z`
- size: `699`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002720`
- `0x180005f9c`
- `0x18001c9d0`
- `0x18001d114`
- `0x18001f088`
- `0x18001f424`
- `0x1800233b8`
- `0x1800239b0`
- `0x180023fec`
- `0x1800259b4`
- `0x180025f34`
- `0x180027150`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x180027319`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800271e5`: `thread descriptor creation failed in bind path`
- `0x180027282`: `Fail to add thread to thread descriptor`
- `0x18002730e`: `TSStaticThreadEntry`
- `0x1800273bc`: `Failed to init in thread context`

## pseudocode

```c
__int64 __fastcall CTSThread::TSStaticThreadEntry(void (__fastcall **a1)(__int64), __int64 a2, __int64 a3, __int64 a4)
{
  void (__fastcall *v4)(__int64); // rbx
  void (__fastcall *v6)(__int64); // rdi
  void (__fastcall *v7)(__int64); // r15
  void (__fastcall *v8)(__int64); // r13
  void (__fastcall *v9)(__int64); // r12
  __int64 v10; // rcx
  __int64 v11; // rdx
  int Id; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  int ActivityIdPrefix; // eax
  int v16; // edx
  const char *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  CTS_TLS_ThreadDescriptor *v22; // r14
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 (__fastcall *v26)(__int64); // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // [rsp+28h] [rbp-50h]
  void (__fastcall *v38)(__int64); // [rsp+50h] [rbp-28h] BYREF
  const char *v39; // [rsp+58h] [rbp-20h] BYREF
  const char *v40; // [rsp+60h] [rbp-18h] BYREF
  const char *v41; // [rsp+68h] [rbp-10h] BYREF
  int v42; // [rsp+C0h] [rbp+48h] BYREF
  int v43; // [rsp+C8h] [rbp+50h] BYREF
  CTS_TLS_ThreadDescriptor *v44; // [rsp+D0h] [rbp+58h] BYREF
  void (__fastcall *v45)(__int64); // [rsp+D8h] [rbp+60h] BYREF

  v4 = 0;
  v45 = 0;
  v44 = 0;
  v6 = a1[4];
  v7 = 0;
  v8 = *a1;
  v9 = a1[3];
  if ( v6 )
  {
    TCntPtr<CTSThread>::SafeRelease(&v45, a2, a3, a4);
    v10 = *((_QWORD *)v6 + 5);
    v4 = v6;
    v45 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v7 = v6;
  }
  Id = CTS_TLS_ThreadDescriptor::CreateInstance(0, &v44, a3, a4);
  if ( Id < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v13, v14);
    v16 = 55;
    v17 = "thread descriptor creation failed in bind path";
    goto LABEL_8;
  }
  v22 = v44;
  Id = CTS_TLS_ThreadDescriptor::AddThreadToList(v44, (struct ITSThread *)v4);
  if ( Id < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v23, v24, v25);
    v16 = 56;
    v17 = "Fail to add thread to thread descriptor";
    goto LABEL_8;
  }
  if ( v22 != *((CTS_TLS_ThreadDescriptor **)v7 + 81) )
  {
    TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease((char *)v7 + 648);
    *((_QWORD *)v7 + 81) = v22;
    if ( v22 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 + 4) + 8LL))(*((_QWORD *)v22 + 4));
  }
  Id = PAL_System_ThreadGetId((char *)a1[4] + 56);
  if ( Id < 0 )
    goto LABEL_9;
  v26 = (__int64 (__fastcall *)(__int64))a1[1];
  if ( v26 )
  {
    Id = v26((__int64)v9);
    if ( Id < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v38 = a1[1];
        v39 = "TSStaticThreadEntry";
        v40 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v41 = "pfnOnPreInit[%p] failed hr[0x%x]";
        v42 = 1015;
        v43 = Id;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v27,
          (__int64)word_18003F9CA,
          v28,
          v29,
          (const unsigned __int16 **)&v41,
          (__int64)&v43,
          (const unsigned __int16 **)&v40,
          (__int64)&v42,
          (const unsigned __int16 **)&v39,
          (__int64)&v38);
      }
      goto LABEL_9;
    }
  }
  Id = CTSThread::InitializeInThreadContext((CTSThread *)v4);
  if ( Id < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v30, v31, v32);
    v16 = 57;
    v17 = "Failed to init in thread context";
LABEL_8:
    v37 = Id;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)v17,
      v37);
    goto LABEL_9;
  }
  v33 = *((_QWORD *)v4 + 92);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 24LL))(v33);
  Id = PAL_System_CondSignal(a1[2]);
  if ( Id >= 0 )
  {
    v8((__int64)v9);
    CTSThread::OnPostExitThreadProc((CTSThread *)v4, v34, v35, v36);
    goto LABEL_12;
  }
LABEL_9:
  if ( v4 )
    CTSThread::ClearThreadDescriptor((CTSThread *)v4);
  *((_DWORD *)a1 + 10) = Id;
LABEL_12:
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v44);
  TCntPtr<CTSThread>::SafeRelease(&v45, v18, v19, v20);
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x180027150  push    rbp
0x180027152  push    rbx
0x180027153  push    rsi
0x180027154  push    rdi
0x180027155  push    r12
0x180027157  push    r13
0x180027159  push    r14
0x18002715b  push    r15
0x18002715d  mov     rbp, rsp
0x180027160  sub     rsp, 78h
0x180027164  xor     ebx, ebx
0x180027166  mov     rsi, rcx
0x180027169  mov     [rbp+arg_18], rbx
0x18002716d  mov     [rbp+arg_10], rbx
0x180027171  mov     rdi, [rcx+20h]
0x180027175  xor     r15d, r15d
0x180027178  mov     r13, [rcx]
0x18002717b  mov     r12, [rcx+18h]
0x18002717f  test    rdi, rdi
0x180027182  jz      short loc_1800271A7
0x180027184  lea     rcx, [rbp+arg_18]
0x180027188  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x18002718d  mov     rcx, [rdi+28h]
0x180027191  mov     rbx, rdi
0x180027194  mov     [rbp+arg_18], rbx
0x180027198  mov     rax, [rcx]
0x18002719b  mov     rax, [rax+8]
0x18002719f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271a4  mov     r15, rdi
0x1800271a7  lea     rdx, [rbp+arg_10]; struct CTS_TLS_ThreadDescriptor **
0x1800271ab  xor     ecx, ecx; int
0x1800271ad  call    ?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z; CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)
0x1800271b2  mov     edi, eax
0x1800271b4  test    eax, eax
0x1800271b6  jns     loc_180027244
0x1800271bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271c3  lea     rax, WPP_GLOBAL_Control
0x1800271ca  cmp     rcx, rax
0x1800271cd  jz      short loc_18002720F
0x1800271cf  test    byte ptr [rcx+1Ch], 8
0x1800271d3  jz      short loc_18002720F
0x1800271d5  cmp     byte ptr [rcx+19h], 2
0x1800271d9  jb      short loc_18002720F
0x1800271db  call    RdpX_GetActivityIdPrefix
0x1800271e0  mov     edx, 37h ; '7'
0x1800271e5  lea     rcx, aThreadDescript_0; "thread descriptor creation failed in bi"...
0x1800271ec  mov     dword ptr [rsp+78h+var_50], edi
0x1800271f0  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800271f7  mov     [rsp+78h+var_58], rcx
0x1800271fc  mov     r9d, eax
0x1800271ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180027206  mov     rcx, [rcx+10h]
0x18002720a  call    WPP_SF_DsD
0x18002720f  test    rbx, rbx
0x180027212  jz      short loc_18002721C
0x180027214  mov     rcx, rbx; this
0x180027217  call    ?ClearThreadDescriptor@CTSThread@@IEAAXXZ; CTSThread::ClearThreadDescriptor(void)
0x18002721c  mov     [rsi+28h], edi
0x18002721f  lea     rcx, [rbp+arg_10]
0x180027223  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180027228  lea     rcx, [rbp+arg_18]
0x18002722c  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x180027231  mov     eax, edi
0x180027233  add     rsp, 78h
0x180027237  pop     r15
0x180027239  pop     r14
0x18002723b  pop     r13
0x18002723d  pop     r12
0x18002723f  pop     rdi
0x180027240  pop     rsi
0x180027241  pop     rbx
0x180027242  pop     rbp
0x180027243  retn
0x180027244  mov     r14, [rbp+arg_10]
0x180027248  mov     rdx, rbx; struct ITSThread *
0x18002724b  mov     rcx, r14; this
0x18002724e  call    ?AddThreadToList@CTS_TLS_ThreadDescriptor@@AEAAJPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::AddThreadToList(ITSThread *)
0x180027253  mov     edi, eax
0x180027255  test    eax, eax
0x180027257  jns     short loc_18002728E
0x180027259  mov     rcx, cs:WPP_GLOBAL_Control
0x180027260  lea     rax, WPP_GLOBAL_Control
0x180027267  cmp     rcx, rax
0x18002726a  jz      short loc_18002720F
0x18002726c  test    byte ptr [rcx+1Ch], 8
0x180027270  jz      short loc_18002720F
0x180027272  cmp     byte ptr [rcx+19h], 2
0x180027276  jb      short loc_18002720F
0x180027278  call    RdpX_GetActivityIdPrefix
0x18002727d  mov     edx, 38h ; '8'
0x180027282  lea     rcx, aFailToAddThrea; "Fail to add thread to thread descriptor"
0x180027289  jmp     loc_1800271EC
0x18002728e  lea     rdi, [r15+288h]
0x180027295  cmp     r14, [rdi]
0x180027298  jz      short loc_1800272BA
0x18002729a  mov     rcx, rdi
0x18002729d  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x1800272a2  mov     [rdi], r14
0x1800272a5  test    r14, r14
0x1800272a8  jz      short loc_1800272BA
0x1800272aa  mov     rcx, [r14+20h]
0x1800272ae  mov     rax, [rcx]
0x1800272b1  mov     rax, [rax+8]
0x1800272b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272ba  mov     rcx, [rsi+20h]
0x1800272be  add     rcx, 38h ; '8'
0x1800272c2  call    PAL_System_ThreadGetId
0x1800272c7  mov     edi, eax
0x1800272c9  test    eax, eax
0x1800272cb  js      loc_18002720F
0x1800272d1  mov     rax, [rsi+8]
0x1800272d5  test    rax, rax
0x1800272d8  jz      loc_180027379
0x1800272de  mov     rcx, r12
0x1800272e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272e6  mov     edi, eax
0x1800272e8  test    eax, eax
0x1800272ea  jns     loc_180027379
0x1800272f0  mov     eax, cs:dword_180044008
0x1800272f6  cmp     eax, 2
0x1800272f9  jbe     loc_18002720F
0x1800272ff  mov     rax, [rsi+8]
0x180027303  lea     rdx, word_18003F9CA
0x18002730a  mov     [rbp+var_28], rax
0x18002730e  lea     rax, aTsstaticthread; "TSStaticThreadEntry"
0x180027315  mov     [rbp+var_20], rax
0x180027319  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180027320  mov     [rbp+var_18], rax
0x180027324  lea     rax, aPfnonpreinitPF; "pfnOnPreInit[%p] failed hr[0x%x]"
0x18002732b  mov     [rbp+var_10], rax
0x18002732f  lea     rax, [rbp+var_28]
0x180027333  mov     [rsp+78h+var_30], rax
0x180027338  lea     rax, [rbp+var_20]
0x18002733c  mov     [rsp+78h+var_38], rax
0x180027341  lea     rax, [rbp+arg_0]
0x180027345  mov     [rsp+78h+var_40], rax
0x18002734a  lea     rax, [rbp+var_18]
0x18002734e  mov     [rsp+78h+var_48], rax
0x180027353  lea     rax, [rbp+arg_8]
0x180027357  mov     [rsp+78h+var_50], rax
0x18002735c  lea     rax, [rbp+var_10]
0x180027360  mov     [rsp+78h+var_58], rax
0x180027365  mov     [rbp+arg_0], 3F7h
0x18002736c  mov     [rbp+arg_8], edi
0x18002736f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180027374  jmp     loc_18002720F
0x180027379  mov     rcx, rbx; this
0x18002737c  call    ?InitializeInThreadContext@CTSThread@@AEAAJH@Z; CTSThread::InitializeInThreadContext(int)
0x180027381  mov     edi, eax
0x180027383  test    eax, eax
0x180027385  jns     short loc_1800273C8
0x180027387  mov     rcx, cs:WPP_GLOBAL_Control
0x18002738e  lea     rax, WPP_GLOBAL_Control
0x180027395  cmp     rcx, rax
0x180027398  jz      loc_18002720F
0x18002739e  test    byte ptr [rcx+1Ch], 8
0x1800273a2  jz      loc_18002720F
0x1800273a8  cmp     byte ptr [rcx+19h], 2
0x1800273ac  jb      loc_18002720F
0x1800273b2  call    RdpX_GetActivityIdPrefix
0x1800273b7  mov     edx, 39h ; '9'
0x1800273bc  lea     rcx, aFailedToInitIn; "Failed to init in thread context"
0x1800273c3  jmp     loc_1800271EC
0x1800273c8  mov     rcx, [rbx+2E0h]
0x1800273cf  test    rcx, rcx
0x1800273d2  jz      short loc_1800273E0
0x1800273d4  mov     rax, [rcx]
0x1800273d7  mov     rax, [rax+18h]
0x1800273db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273e0  mov     rcx, [rsi+10h]
0x1800273e4  call    PAL_System_CondSignal
0x1800273e9  mov     edi, eax
0x1800273eb  test    eax, eax
0x1800273ed  js      loc_18002720F
0x1800273f3  mov     rcx, r12
0x1800273f6  mov     rax, r13
0x1800273f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273fe  mov     rcx, rbx; this
0x180027401  call    ?OnPostExitThreadProc@CTSThread@@AEAAXXZ; CTSThread::OnPostExitThreadProc(void)
0x180027406  jmp     loc_18002721F
```
