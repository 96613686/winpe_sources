# CHttpWriter::CHttpWriter(GenericStringHandle<ushort>,_GUID const &,GenericStringHandle<ushort>,SidHandle,bool *,_GUID const &,PROXY_SETTINGS const *,CCredentialsContainer const *,TokenHandle const &,TokenHandle const &,ulong,bool,ulong,GenericStringHandle<ushort>,GenericStringHandle<ushort>,UPLOAD_DATA *,CClientCertificate *,CCustomHeaders const *,ulong,_TP_CALLBACK_ENVIRON_V3 *,bool,IServerCertificateValidator *)

- ea: `0x180051ea0`
- end: `0x180052355`
- name: `??0CHttpWriter@@QEAA@V?$GenericStringHandle@G@@AEBU_GUID@@0VSidHandle@@PEA_N1PEBUPROXY_SETTINGS@@PEBVCCredentialsContainer@@AEBVTokenHandle@@6K_NK00PEAUUPLOAD_DATA@@PEAVCClientCertificate@@PEBVCCustomHeaders@@KPEAU_TP_CALLBACK_ENVIRON_V3@@7PEAUIServerCertificateValidator@@@Z`
- size: `1205`
- prototype: `__int64 __fastcall(int, int, int, int, SidHandle *, __int64, __int64, __int64, struct CCredentialsContainer *, struct TokenHandle *, struct TokenHandle *, unsigned int, bool, int, __int64, __int64, __int64, struct CClientCertificate *, __int64, unsigned __int16 *, int, char, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800518d8`
- `0x1800f2e7c`

## callees

- `0x1800065ac`
- `0x180016d60`
- `0x18001d7f0`
- `0x18002037c`
- `0x180051ea0`
- `0x18005235c`
- `0x180052ef4`
- `0x180052f90`
- `0x18005352c`
- `0x18007aaf0`
- `0x18008de70`
- `0x18008df30`
- `0x18009d2e8`
- `0x1800a0738`
- `0x1800c0fac`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800522a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800522a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_QWORD *__fastcall CHttpWriter::CHttpWriter(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        _QWORD *a4,
        SidHandle *a5,
        __int64 a6,
        __int64 a7,
        enum BG_JOB_PROXY_USAGE *a8,
        struct CCredentialsContainer *a9,
        HANDLE **a10,
        HANDLE **a11,
        unsigned int a12,
        bool a13,
        int a14,
        _QWORD *a15,
        _QWORD *a16,
        _DWORD *a17,
        struct CClientCertificate *a18,
        __int64 a19,
        unsigned __int16 *a20,
        int a21,
        char a22,
        __int64 a23)
{
  __int64 v23; // r13
  bool v25; // dl
  HttpSecurityData *v26; // rcx
  struct CClientCertificate *v27; // rdi
  struct CCredentialsContainer *v28; // rbx
  unsigned int v29; // esi
  unsigned int v30; // r12d
  HANDLE **v31; // r15
  HANDLE **v32; // r14
  struct _SECURITY_ATTRIBUTES *v33; // r9
  struct _SECURITY_ATTRIBUTES *v34; // r9
  _QWORD *v35; // rcx
  _DWORD *v36; // rcx
  _QWORD *v37; // rsi
  SidHandle *v38; // r13
  volatile signed __int32 *v39; // rax
  HANDLE *v40; // rax
  HANDLE *v41; // rax
  _QWORD *v42; // r14
  __int64 v43; // r8
  PTP_WORK ThreadpoolWork; // rax
  unsigned int LastError; // eax
  PSID pSid[2]; // [rsp+48h] [rbp-71h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-61h] BYREF
  __int128 v49; // [rsp+60h] [rbp-59h]
  unsigned int v50; // [rsp+70h] [rbp-49h]
  int v51; // [rsp+74h] [rbp-45h]
  int v52; // [rsp+78h] [rbp-41h]
  __int64 v55; // [rsp+118h] [rbp+5Fh] BYREF
  _QWORD *v56; // [rsp+120h] [rbp+67h]

  v56 = a4;
  v23 = a3;
  _InterlockedIncrement((volatile signed __int32 *)(*a2 + 8));
  v55 = *a2;
  LOBYTE(a3) = a13;
  CAbstractFile::CAbstractFile(a1, &v55, a3);
  AbstractIoThreadAwareWinHttpCallbackHandler::AbstractIoThreadAwareWinHttpCallbackHandler((AbstractIoThreadAwareWinHttpCallbackHandler *)(a1 + 38));
  a1[65] = &AbstractHttpServerCertificateHandler::`vftable';
  a1[66] = a23;
  CCritSec2::CCritSec2((CCritSec2 *)(a1 + 67), v25);
  *((_BYTE *)a1 + 584) = 0;
  *(_QWORD *)((char *)a1 + 588) = 0;
  *a1 = &CHttpWriter::`vftable'{for `CAbstractFile'};
  a1[38] = &CHttpWriter::`vftable'{for `AbstractIoThreadAwareWinHttpCallbackHandler'};
  a1[65] = &CHttpWriter::`vftable'{for `AbstractHttpServerCertificateHandler'};
  std::wstring::wstring(a1 + 75);
  *((_BYTE *)a1 + 632) = ShouldUseLowPriorityTcp(a13);
  a1[80] = g_WinHttpInterface;
  v26 = (HttpSecurityData *)(a1 + 81);
  v27 = a18;
  v28 = a9;
  v29 = (unsigned int)a20;
  v30 = a12;
  v31 = a11;
  v32 = a10;
  HttpSecurityData::HttpSecurityData(v26, a10, a11, a12, (unsigned int)a20, a9, a18);
  *((_DWORD *)a1 + 174) = 0;
  a1[88] = 0;
  a1[89] = 0;
  *((_DWORD *)a1 + 180) = 0;
  CEvent::CEvent((CEvent *)(a1 + 91), 1, 1, v33);
  CEvent::CEvent((CEvent *)(a1 + 92), 1, 1, v34);
  a1[94] = a8;
  a1[95] = v28;
  a1[96] = v27;
  a1[97] = a19;
  *((_DWORD *)a1 + 196) = v29;
  *((_DWORD *)a1 + 197) = (v29 >> 11) & 1;
  *((_DWORD *)a1 + 198) = v29 & 0x700;
  _InterlockedAdd(&dword_180145058, 1u);
  a1[102] = &GenericStringHandle<unsigned short>::s_EmptyString;
  _InterlockedAdd(&dword_180145058, 1u);
  a1[105] = &GenericStringHandle<unsigned short>::s_EmptyString;
  *((_WORD *)a1 + 424) = 0;
  *((_DWORD *)a1 + 213) = 0;
  v35 = a16;
  _InterlockedAdd((volatile signed __int32 *)(*a16 + 8LL), 1u);
  a1[107] = *v35;
  v36 = a17;
  *((_DWORD *)a1 + 216) = *a17;
  *((_BYTE *)a1 + 868) = *((_BYTE *)v36 + 4);
  *(_OWORD *)(a1 + 109) = *(_OWORD *)(v36 + 2);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v36 + 3) + 8LL), 1u);
  a1[111] = *((_QWORD *)v36 + 3);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v36 + 4) + 8LL), 1u);
  a1[112] = *((_QWORD *)v36 + 4);
  a1[113] = *((_QWORD *)v36 + 5);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v36 + 6) + 8LL), 1u);
  a1[114] = *((_QWORD *)v36 + 6);
  *((_DWORD *)a1 + 230) = v36[14];
  *(_QWORD *)((char *)a1 + 924) = *(_QWORD *)(v36 + 15);
  *((_BYTE *)a1 + 936) = 0;
  *((_BYTE *)a1 + 944) = 0;
  EidAsyncHelper::EidAsyncHelper((EidAsyncHelper *)(a1 + 119));
  a1[133] = a6;
  a1[134] = v23;
  v37 = v56;
  _InterlockedAdd((volatile signed __int32 *)(*v56 + 8LL), 1u);
  a1[135] = *v37;
  v38 = a5;
  a1[136] = *(_QWORD *)a5;
  v39 = (volatile signed __int32 *)*((_QWORD *)v38 + 1);
  a1[137] = v39;
  _InterlockedAdd(v39, 1u);
  a1[138] = a7;
  v40 = *v32;
  a1[139] = *v32;
  _InterlockedAdd((volatile signed __int32 *)v40 + 2, 1u);
  v41 = *v31;
  a1[140] = *v31;
  _InterlockedIncrement((volatile signed __int32 *)v41 + 2);
  *((_DWORD *)a1 + 282) = v30;
  *((_DWORD *)a1 + 347) = a14;
  *((_BYTE *)a1 + 1392) = a22;
  *((_BYTE *)a1 + 1393) = 0;
  v42 = a15;
  _InterlockedIncrement((volatile signed __int32 *)(*a15 + 8LL));
  a1[176] = *v42;
  a1[175] = 0;
  InitSessionCache();
  if ( *((_DWORD *)a1 + 282) )
  {
    TokenHandle::GetSid(a1 + 140, pSid);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAEu, v43, *((_DWORD *)a1 + 282), (char *)pSid[0]);
    SidHandle::~SidHandle((SidHandle *)pSid);
  }
  *((_DWORD *)a1 + 43) = *(_DWORD *)*a2 + 500;
  if ( a8 )
  {
    if ( !ProxyUsageFromJobProxyUsage(*a8) )
    {
      ThreadpoolWork = CreateThreadpoolWork(
                         CHttpWriter::StaticProxyResolutionRoutine,
                         a1,
                         (PTP_CALLBACK_ENVIRON)((char *)g_Manager + 992));
      a1[175] = ThreadpoolWork;
      if ( !ThreadpoolWork )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0x80070000;
        else
          LastError = GetLastError();
        v49 = 0;
        pExceptionObject = &ComError::`vftable';
        v50 = LastError;
        v51 = 6070;
        v52 = 1;
        throw (ComError *)&pExceptionObject;
      }
    }
  }
  GenericStringHandle<unsigned short>::FreeIt(a2);
  GenericStringHandle<unsigned short>::FreeIt(v37);
  SidHandle::~SidHandle(v38);
  GenericStringHandle<unsigned short>::FreeIt(v42);
  GenericStringHandle<unsigned short>::FreeIt(a16);
  return a1;
}

```

## disassembly

```asm
0x180051ea0  mov     rax, rsp
0x180051ea3  mov     [rax+20h], r9
0x180051ea7  mov     [rax+10h], rdx
0x180051eab  mov     [rax+8], rcx
0x180051eaf  push    rbp
0x180051eb0  push    rbx
0x180051eb1  push    rsi
0x180051eb2  push    rdi
0x180051eb3  push    r12
0x180051eb5  push    r13
0x180051eb7  push    r14
0x180051eb9  push    r15
0x180051ebb  lea     rbp, [rax-47h]
0x180051ebf  sub     rsp, 0B8h
0x180051ec6  mov     r13, r8
0x180051ec9  mov     rdi, rcx
0x180051ecc  mov     rax, [rdx]
0x180051ecf  lock inc dword ptr [rax+8]
0x180051ed3  mov     rax, [rdx]
0x180051ed6  mov     [rbp+3Fh+arg_10], rax
0x180051eda  mov     r8b, [rbp+3Fh+arg_60]
0x180051ee1  lea     rdx, [rbp+3Fh+arg_10]
0x180051ee5  call    ??0CAbstractFile@@QEAA@V?$GenericStringHandle@G@@_NPEAU_TP_CALLBACK_ENVIRON_V3@@@Z; CAbstractFile::CAbstractFile(GenericStringHandle<ushort>,bool,_TP_CALLBACK_ENVIRON_V3 *)
0x180051eea  nop
0x180051eeb  lea     rbx, [rdi+130h]
0x180051ef2  mov     rcx, rbx; this
0x180051ef5  call    ??0AbstractIoThreadAwareWinHttpCallbackHandler@@QEAA@XZ; AbstractIoThreadAwareWinHttpCallbackHandler::AbstractIoThreadAwareWinHttpCallbackHandler(void)
0x180051efa  nop
0x180051efb  lea     rax, ??_7AbstractHttpServerCertificateHandler@@6B@; const AbstractHttpServerCertificateHandler::`vftable'
0x180051f02  mov     [rdi+208h], rax
0x180051f09  mov     rax, [rbp+3Fh+arg_B0]
0x180051f10  mov     [rdi+210h], rax
0x180051f17  lea     rcx, [rdi+218h]; this
0x180051f1e  call    ??0CCritSec2@@QEAA@_N@Z; CCritSec2::CCritSec2(bool)
0x180051f23  xor     eax, eax
0x180051f25  mov     [rdi+248h], al
0x180051f2b  mov     [rdi+24Ch], rax
0x180051f32  lea     rax, ??_7CHttpWriter@@6BCAbstractFile@@@; const CHttpWriter::`vftable'{for `CAbstractFile'}
0x180051f39  mov     [rdi], rax
0x180051f3c  lea     rax, ??_7CHttpWriter@@6BAbstractIoThreadAwareWinHttpCallbackHandler@@@; const CHttpWriter::`vftable'{for `AbstractIoThreadAwareWinHttpCallbackHandler'}
0x180051f43  mov     [rbx], rax
0x180051f46  lea     rax, ??_7CHttpWriter@@6BAbstractHttpServerCertificateHandler@@@; const CHttpWriter::`vftable'{for `AbstractHttpServerCertificateHandler'}
0x180051f4d  mov     [rdi+208h], rax
0x180051f54  lea     rcx, [rdi+258h]
0x180051f5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180051f60  nop
0x180051f61  mov     cl, [rbp+3Fh+arg_60]; bool
0x180051f67  call    ?ShouldUseLowPriorityTcp@@YA_N_N@Z; ShouldUseLowPriorityTcp(bool)
0x180051f6c  mov     [rdi+278h], al
0x180051f72  mov     rax, cs:?g_WinHttpInterface@@3REAVIHttpInterface@@EA; IHttpInterface * g_WinHttpInterface
0x180051f79  mov     [rdi+280h], rax
0x180051f80  lea     rcx, [rdi+288h]; this
0x180051f87  mov     rdi, [rbp+3Fh+arg_88]
0x180051f8e  mov     [rsp+30h], rdi; struct CClientCertificate *
0x180051f93  mov     rbx, [rbp+3Fh+arg_40]
0x180051f9a  mov     [rsp+0F0h+var_C8], rbx; struct CCredentialsContainer *
0x180051f9f  mov     esi, dword ptr [rbp+3Fh+arg_98]
0x180051fa5  mov     dword ptr [rsp+0F0h+pSid], esi; unsigned __int16 *
0x180051fa9  mov     r12d, [rbp+3Fh+arg_58]
0x180051fb0  mov     r9d, r12d; unsigned int
0x180051fb3  mov     r15, [rbp+3Fh+arg_50]
0x180051fba  mov     r8, r15; struct TokenHandle *
0x180051fbd  mov     r14, [rbp+3Fh+arg_48]
0x180051fc4  mov     rdx, r14; struct TokenHandle *
0x180051fc7  call    ??0HttpSecurityData@@QEAA@AEBVTokenHandle@@0KKAEBVCCredentialsContainer@@PEBVCClientCertificate@@@Z; HttpSecurityData::HttpSecurityData(TokenHandle const &,TokenHandle const &,ulong,ulong,CCredentialsContainer const &,CClientCertificate const *)
0x180051fcc  mov     rax, [rbp+3Fh+pv]
0x180051fd0  xor     ecx, ecx
0x180051fd2  mov     [rax+2B8h], ecx
0x180051fd8  mov     [rax+2C0h], rcx
0x180051fdf  mov     [rax+2C8h], rcx
0x180051fe6  mov     [rax+2D0h], ecx
0x180051fec  lea     rcx, [rax+2D8h]; this
0x180051ff3  mov     edx, 1; int
0x180051ff8  mov     r8d, edx; int
0x180051ffb  call    ??0CEvent@@QEAA@HHPEAU_SECURITY_ATTRIBUTES@@PEBG@Z; CEvent::CEvent(int,int,_SECURITY_ATTRIBUTES *,ushort const *)
0x180052000  nop
0x180052001  mov     rcx, [rbp+3Fh+pv]
0x180052005  add     rcx, 2E0h; this
0x18005200c  mov     eax, 1
0x180052011  mov     r8d, eax; int
0x180052014  mov     edx, eax; int
0x180052016  call    ??0CEvent@@QEAA@HHPEAU_SECURITY_ATTRIBUTES@@PEBG@Z; CEvent::CEvent(int,int,_SECURITY_ATTRIBUTES *,ushort const *)
0x18005201b  nop
0x18005201c  mov     rax, [rbp+3Fh+pv]
0x180052020  mov     rcx, [rbp+3Fh+arg_38]
0x180052027  mov     [rax+2F0h], rcx
0x18005202e  mov     [rax+2F8h], rbx
0x180052035  mov     rbx, rax
0x180052038  mov     [rax+300h], rdi
0x18005203f  mov     rax, [rbp+3Fh+arg_90]
0x180052046  mov     [rbx+308h], rax
0x18005204d  mov     [rbx+310h], esi
0x180052053  mov     eax, esi
0x180052055  shr     eax, 0Bh
0x180052058  mov     edi, 1
0x18005205d  and     eax, edi
0x18005205f  mov     [rbx+314h], eax
0x180052065  and     esi, 700h
0x18005206b  mov     [rbx+318h], esi
0x180052071  lock add cs:dword_180145058, edi
0x180052078  lea     rcx, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18005207f  mov     [rbx+330h], rcx
0x180052086  lock add cs:dword_180145058, edi
0x18005208d  mov     [rbx+348h], rcx
0x180052094  xor     edx, edx
0x180052096  mov     [rbx+350h], dx
0x18005209d  mov     [rbx+354h], edx
0x1800520a3  mov     rcx, [rbp+3Fh+arg_78]
0x1800520aa  mov     rax, [rcx]
0x1800520ad  lock add [rax+8], edi
0x1800520b1  mov     rax, [rcx]
0x1800520b4  mov     [rbx+358h], rax
0x1800520bb  mov     rcx, [rbp+3Fh+arg_80]
0x1800520c2  mov     eax, [rcx]
0x1800520c4  mov     [rbx+360h], eax
0x1800520ca  mov     al, [rcx+4]
0x1800520cd  mov     [rbx+364h], al
0x1800520d3  movups  xmm0, xmmword ptr [rcx+8]
0x1800520d7  movdqu  xmmword ptr [rbx+368h], xmm0
0x1800520df  mov     rax, [rcx+18h]
0x1800520e3  lock add [rax+8], edi
0x1800520e7  mov     rax, [rcx+18h]
0x1800520eb  mov     [rbx+378h], rax
0x1800520f2  mov     rax, [rcx+20h]
0x1800520f6  lock add [rax+8], edi
0x1800520fa  mov     rax, [rcx+20h]
0x1800520fe  mov     [rbx+380h], rax
0x180052105  mov     rax, [rcx+28h]
0x180052109  mov     [rbx+388h], rax
0x180052110  mov     rax, [rcx+30h]
0x180052114  lock add [rax+8], edi
0x180052118  mov     rax, [rcx+30h]
0x18005211c  mov     [rbx+390h], rax
0x180052123  mov     eax, [rcx+38h]
0x180052126  mov     [rbx+398h], eax
0x18005212c  mov     rax, [rcx+3Ch]
0x180052130  mov     [rbx+39Ch], rax
0x180052137  mov     [rbx+3A8h], dl
0x18005213d  mov     [rbx+3B0h], dl
0x180052143  lea     rcx, [rbx+3B8h]; this
0x18005214a  call    ??0EidAsyncHelper@@QEAA@XZ; EidAsyncHelper::EidAsyncHelper(void)
0x18005214f  nop
0x180052150  mov     rax, [rbp+3Fh+arg_28]
0x180052154  mov     [rbx+428h], rax
0x18005215b  mov     [rbx+430h], r13
0x180052162  mov     rsi, [rbp+3Fh+arg_18]
0x180052166  mov     rax, [rsi]
0x180052169  lock add [rax+8], edi
0x18005216d  mov     rax, [rsi]
0x180052170  mov     [rbx+438h], rax
0x180052177  mov     r13, [rbp+3Fh+arg_20]
0x18005217b  mov     rax, [r13+0]
0x18005217f  mov     [rbx+440h], rax
0x180052186  mov     rax, [r13+8]
0x18005218a  mov     [rbx+448h], rax
0x180052191  lock add [rax], edi
0x180052194  mov     rax, [rbp+3Fh+arg_30]
0x180052198  mov     [rbx+450h], rax
0x18005219f  mov     rax, [r14]
0x1800521a2  mov     [rbx+458h], rax
0x1800521a9  lock add [rax+8], edi
0x1800521ad  lea     rdi, [rbx+460h]
0x1800521b4  mov     rax, [r15]
0x1800521b7  mov     [rdi], rax
0x1800521ba  lock inc dword ptr [rax+8]
0x1800521be  mov     [rbx+468h], r12d
0x1800521c5  mov     eax, [rbp+3Fh+arg_68]
0x1800521cb  mov     [rbx+56Ch], eax
0x1800521d1  mov     al, [rbp+3Fh+arg_A8]
0x1800521d7  mov     [rbx+570h], al
0x1800521dd  xor     r15d, r15d
0x1800521e0  mov     [rbx+571h], r15b
0x1800521e7  mov     r14, [rbp+3Fh+arg_70]
0x1800521ee  mov     rax, [r14]
0x1800521f1  lock inc dword ptr [rax+8]
0x1800521f5  mov     rax, [r14]
0x1800521f8  mov     [rbx+580h], rax
0x1800521ff  mov     [rbx+578h], r15
0x180052206  call    ?InitSessionCache@@YAXXZ; InitSessionCache(void)
0x18005220b  cmp     [rbx+468h], r15d
0x180052212  jz      short loc_180052260
0x180052214  lea     rdx, [rbp+3Fh+var_B0]
0x180052218  mov     rcx, rdi
0x18005221b  call    ?GetSid@TokenHandle@@QEBA?AVSidHandle@@XZ; TokenHandle::GetSid(void)
0x180052220  lea     rax, WPP_GLOBAL_Control
0x180052227  mov     rcx, cs:WPP_GLOBAL_Control
0x18005222e  cmp     rcx, rax
0x180052231  jz      short loc_180052257
0x180052233  test    byte ptr [rcx+1Ch], 1
0x180052237  jz      short loc_180052257
0x180052239  mov     edx, 0AEh; int
0x18005223e  mov     rax, [rbp+3Fh+var_B0]
0x180052242  mov     [rsp+0F0h+pSid], rax; pSid
0x180052247  mov     r9d, [rbx+468h]; int
0x18005224e  mov     rcx, [rcx+10h]; int
0x180052252  call    WPP_SF_D_sid_
0x180052257  lea     rcx, [rbp+3Fh+var_B0]; this
0x18005225b  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x180052260  mov     rdi, [rbp+3Fh+arg_8]
0x180052264  mov     rax, [rdi]
0x180052267  mov     edx, [rax]
0x180052269  add     edx, 1F4h
0x18005226f  mov     [rbx+0ACh], edx
0x180052275  mov     rax, [rbp+3Fh+arg_38]
0x18005227c  test    rax, rax
0x18005227f  jz      loc_18005230E
0x180052285  mov     ecx, [rax]; enum BG_JOB_PROXY_USAGE
0x180052287  call    ?ProxyUsageFromJobProxyUsage@@YAKW4BG_JOB_PROXY_USAGE@@@Z; ProxyUsageFromJobProxyUsage(BG_JOB_PROXY_USAGE)
0x18005228c  test    eax, eax
0x18005228e  jnz     short loc_18005230E
0x180052290  mov     r8, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180052297  add     r8, 3E0h; pcbe
0x18005229e  mov     rdx, rbx; pv
0x1800522a1  lea     rcx, ?StaticProxyResolutionRoutine@CHttpWriter@@CAKPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800522a8  call    cs:__imp_CreateThreadpoolWork
0x1800522ae  mov     [rbx+578h], rax
0x1800522b5  test    rax, rax
0x1800522b8  jnz     short loc_18005230E
0x1800522ba  call    cs:__imp_GetLastError
0x1800522c0  test    eax, eax
0x1800522c2  jg      short loc_1800522CC
0x1800522c4  call    cs:__imp_GetLastError
0x1800522ca  jmp     short loc_1800522DA
0x1800522cc  call    cs:__imp_GetLastError
0x1800522d2  movzx   eax, ax
0x1800522d5  or      eax, 80070000h
0x1800522da  xorps   xmm0, xmm0
0x1800522dd  movups  [rbp+3Fh+var_98], xmm0
0x1800522e1  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800522e8  mov     [rbp+3Fh+pExceptionObject], rcx
0x1800522ec  mov     [rbp+3Fh+var_88], eax
0x1800522ef  mov     [rbp+3Fh+var_84], 17B6h
0x1800522f6  mov     [rbp+3Fh+var_80], 1
0x1800522fd  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180052304  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180052308  call    _CxxThrowException_0
0x18005230e  mov     rcx, rdi
0x180052311  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x180052316  nop
0x180052317  mov     rcx, rsi
0x18005231a  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18005231f  nop
0x180052320  mov     rcx, r13; this
0x180052323  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x180052328  nop
0x180052329  mov     rcx, r14
0x18005232c  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x180052331  nop
0x180052332  mov     rcx, [rbp+3Fh+arg_78]
0x180052339  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18005233e  mov     rax, rbx
0x180052341  add     rsp, 0B8h
0x180052348  pop     r15
0x18005234a  pop     r14
0x18005234c  pop     r13
0x18005234e  pop     r12
0x180052350  pop     rdi
0x180052351  pop     rsi
0x180052352  pop     rbx
0x180052353  pop     rbp
0x180052354  retn
```
