# ImpersonateAndOpenRRQueue(QUEUE_FORMAT *,_GUID const &,ulong,ulong,wchar_t const *)

- ea: `0x18007dcd8`
- end: `0x18007e045`
- name: `?ImpersonateAndOpenRRQueue@@YAJPEAUQUEUE_FORMAT@@AEBU_GUID@@KKPEB_W@Z`
- size: `877`
- prototype: `__int64 __fastcall(struct QUEUE_FORMAT *, const struct _GUID *, unsigned int, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180036298`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x1800202e4`
- `0x18002c61c`
- `0x1800364fc`
- `0x180064f48`
- `0x18007dad8`
- `0x18007dcd8`
- `0x18007e04c`
- `0x18007e164`
- `0x18007e8d0`
- `0x18007e958`
- `0x1800e4010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18007df4e`
- `RPCRT4!NdrClientCall3` at `0x18007df4e`
- `mqsec!MQSec_GetImpersonationObject` at `0x18007dd08`
- `mqsec!MQSec_GetImpersonationObject` at `0x18007dd08`
- `mqsec!MQSec_TraceThreadTokenInfo` at `0x18007dd9b`
- `mqsec!MQSec_TraceThreadTokenInfo` at `0x18007dd9b`

## string_xrefs

- `0x18007ddfa`: `qmrtopen`
- `0x18007de21`: `qmrtopen`
- `0x18007ded0`: `qmrtopen`
- `0x18007df5e`: `qmrtopen`
- `0x18007dfec`: `qmrtopen`
- `0x18007e00e`: `qmrtopen`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ImpersonateAndOpenRRQueue(
        struct QUEUE_FORMAT *a1,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        const wchar_t *a5)
{
  unsigned int v9; // eax
  unsigned __int16 v10; // r8
  int v11; // ebx
  int v12; // eax
  int v13; // eax
  CQueueMgr *v14; // rcx
  CQueueMgr *v15; // rcx
  int v16; // eax
  void **v18; // [rsp+58h] [rbp-49h]
  CQueueMgr *v19; // [rsp+60h] [rbp-41h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v21; // [rsp+6Ch] [rbp-35h] BYREF
  unsigned int v22; // [rsp+70h] [rbp-31h] BYREF
  struct CImpersonate *v23; // [rsp+78h] [rbp-29h] BYREF
  __int64 v24; // [rsp+80h] [rbp-21h] BYREF
  __int64 v25; // [rsp+88h] [rbp-19h] BYREF
  unsigned __int64 v26; // [rsp+90h] [rbp-11h] BYREF
  __int64 v27; // [rsp+98h] [rbp-9h] BYREF
  _QWORD v28[2]; // [rsp+A0h] [rbp-1h] BYREF
  struct _GUID v29; // [rsp+B0h] [rbp+Fh] BYREF

  v23 = 0;
  MQSec_GetImpersonationObject(0, &v23);
  v9 = (*(__int64 (__fastcall **)(struct CImpersonate *))(*(_QWORD *)v23 + 8LL))(v23);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 17, WPP_87250885c95f397c31c605fa141b682f_Traceguids, v9);
    v10 = 1131;
    v11 = -1072824284;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 18, WPP_87250885c95f397c31c605fa141b682f_Traceguids);
  MQSec_TraceThreadTokenInfo();
  v19 = 0;
  v27 = 0;
  v26 = 0;
  if ( (unsigned __int8)UseOldRemoteRead() )
  {
    v11 = -2147023143;
  }
  else
  {
    v12 = OpenNewRemoteQueue(a5, a1, a3, a4, &v19, &v26, &v27);
    v11 = v12;
    if ( v12 >= 0 )
    {
      P<CImpersonate>::free(&v23);
      v29 = *a2;
      v15 = v19;
      v19 = 0;
      v28[0] = v27;
      v28[1] = v15;
      v16 = CQueueMgr::OpenRRQueue(
              v15,
              a1,
              &v29,
              a3,
              a4,
              0,
              0,
              0,
              v26,
              (struct CAutoCloseNewRemoteReadCtxAndBind *)v28,
              (struct CBindHandle *)&v19,
              v18);
      v11 = v16;
      if ( v16 < 0 )
        LogMsgHR(v16, (wchar_t *)L"qmrtopen", 0x1388u);
      CAutoCloseNewRemoteReadCtxAndBind::~CAutoCloseNewRemoteReadCtxAndBind((CAutoCloseNewRemoteReadCtxAndBind *)v28);
      if ( v11 < 0 )
        LogMsgHR(v11, (wchar_t *)L"qmrtopen", 0x1770u);
      CBindHandle::free((CBindHandle *)&v19);
      goto LABEL_31;
    }
    LogMsgHR(v12, (wchar_t *)L"qmrtopen", 0xFA0u);
  }
  CBindHandle::free((CBindHandle *)&v19);
  if ( v11 != -2147023143 )
  {
    v10 = 6100;
LABEL_15:
    LogMsgHR(v11, (wchar_t *)L"qmrtopen", v10);
    goto LABEL_31;
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v13 = OpenRemoteQueue(a5, a1, a3, a4, &v20, &v21, &v22, &v24, &v25);
  v11 = v13;
  if ( v13 >= 0 )
  {
    P<CImpersonate>::free(&v23);
    v11 = CQueueMgr::OpenRRQueue(v14, a1, a2, a3, a4, v22, v21, v20, 0, 0, (struct CBindHandle *)&v24, v18);
    NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800EAE70, 3u, 0, &v25);
    if ( v11 < 0 )
      LogMsgHR(v11, (wchar_t *)L"qmrtopen", 0x1F40u);
    CBindHandle::free((CBindHandle *)&v24);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        19,
        WPP_87250885c95f397c31c605fa141b682f_Traceguids,
        (unsigned int)v13);
    if ( v11 == -2147023143 )
      v11 = -1072824215;
    LogMsgHR(v11, (wchar_t *)L"qmrtopen", 0x46Du);
    CBindHandle::free((CBindHandle *)&v24);
  }
LABEL_31:
  P<CInSeqLogContext>::~P<CInSeqLogContext>(&v23);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007dcd8  push    rbp
0x18007dcda  push    rbx
0x18007dcdb  push    rsi
0x18007dcdc  push    r12
0x18007dcde  push    r13
0x18007dce0  push    r14
0x18007dce2  push    r15
0x18007dce4  lea     rbp, [rsp-1Fh]
0x18007dce9  sub     rsp, 0C0h
0x18007dcf0  mov     r14d, r9d
0x18007dcf3  mov     r15d, r8d
0x18007dcf6  mov     r13, rdx
0x18007dcf9  mov     r12, rcx
0x18007dcfc  xor     ebx, ebx
0x18007dcfe  mov     [rbp+4Fh+var_78], rbx
0x18007dd02  lea     rdx, [rbp+4Fh+var_78]
0x18007dd06  xor     ecx, ecx
0x18007dd08  call    cs:__imp_?MQSec_GetImpersonationObject@@YAXHPEAPEAVCImpersonate@@@Z; MQSec_GetImpersonationObject(int,CImpersonate * *)
0x18007dd0e  mov     rcx, [rbp+4Fh+var_78]
0x18007dd12  mov     rax, [rcx]
0x18007dd15  mov     rax, [rax+8]
0x18007dd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd1e  test    eax, eax
0x18007dd20  jz      short loc_18007DD67
0x18007dd22  lea     rsi, WPP_GLOBAL_Control
0x18007dd29  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd30  cmp     rcx, rsi
0x18007dd33  jz      short loc_18007DD57
0x18007dd35  test    byte ptr [rcx+0BCh], 1
0x18007dd3c  jz      short loc_18007DD57
0x18007dd3e  lea     edx, [rbx+11h]
0x18007dd41  mov     r9d, eax
0x18007dd44  lea     r8, WPP_87250885c95f397c31c605fa141b682f_Traceguids
0x18007dd4b  mov     rcx, [rcx+0B0h]
0x18007dd52  call    WPP_SF_d
0x18007dd57  mov     r8d, 46Bh
0x18007dd5d  mov     ebx, 0C00E0024h
0x18007dd62  jmp     loc_18007DE21
0x18007dd67  lea     rsi, WPP_GLOBAL_Control
0x18007dd6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd75  cmp     rcx, rsi
0x18007dd78  jz      short loc_18007DD9B
0x18007dd7a  test    byte ptr [rcx+0BCh], 4
0x18007dd81  jz      short loc_18007DD9B
0x18007dd83  mov     edx, 12h
0x18007dd88  lea     r8, WPP_87250885c95f397c31c605fa141b682f_Traceguids
0x18007dd8f  mov     rcx, [rcx+0B0h]
0x18007dd96  call    WPP_SF_
0x18007dd9b  call    cs:__imp_?MQSec_TraceThreadTokenInfo@@YAXXZ; MQSec_TraceThreadTokenInfo(void)
0x18007dda1  mov     [rbp+4Fh+var_90], rbx
0x18007dda5  mov     [rbp+4Fh+var_58], rbx
0x18007dda9  mov     [rbp+4Fh+var_60], rbx
0x18007ddad  call    UseOldRemoteRead
0x18007ddb2  test    al, al
0x18007ddb4  jz      short loc_18007DDBD
0x18007ddb6  mov     ebx, 800706D9h
0x18007ddbb  jmp     short loc_18007DE09
0x18007ddbd  lea     rax, [rbp+4Fh+var_58]
0x18007ddc1  mov     qword ptr [rsp+0F0h+var_C0], rax
0x18007ddc6  lea     rax, [rbp+4Fh+var_60]
0x18007ddca  mov     qword ptr [rsp+0F0h+var_C8], rax
0x18007ddcf  lea     rax, [rbp+4Fh+var_90]
0x18007ddd3  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18007ddd8  mov     r9d, r14d
0x18007dddb  mov     r8d, r15d
0x18007ddde  mov     rdx, r12
0x18007dde1  mov     rcx, [rbp+4Fh+arg_20]
0x18007dde5  call    OpenNewRemoteQueue
0x18007ddea  mov     ebx, eax
0x18007ddec  test    eax, eax
0x18007ddee  jns     loc_18007DF7C
0x18007ddf4  mov     r8d, 0FA0h; unsigned __int16
0x18007ddfa  lea     rdx, aQmrtopen; "qmrtopen"
0x18007de01  mov     ecx, eax; int
0x18007de03  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18007de08  nop
0x18007de09  lea     rcx, [rbp+4Fh+var_90]; this
0x18007de0d  call    ?free@CBindHandle@@QEAAXXZ; CBindHandle::free(void)
0x18007de12  nop
0x18007de13  cmp     ebx, 800706D9h
0x18007de19  jz      short loc_18007DE34
0x18007de1b  mov     r8d, 17D4h; unsigned __int16
0x18007de21  lea     rdx, aQmrtopen; "qmrtopen"
0x18007de28  mov     ecx, ebx; int
0x18007de2a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18007de2f  jmp     loc_18007E027
0x18007de34  xor     eax, eax
0x18007de36  mov     [rbp+4Fh+var_88], eax
0x18007de39  mov     [rbp+4Fh+var_84], eax
0x18007de3c  mov     [rbp+4Fh+var_80], eax
0x18007de3f  mov     [rbp+4Fh+var_70], rax
0x18007de43  mov     [rbp+4Fh+var_68], rax
0x18007de47  lea     rax, [rbp+4Fh+var_68]
0x18007de4b  mov     [rsp+0F0h+var_B0], rax
0x18007de50  lea     rax, [rbp+4Fh+var_70]
0x18007de54  mov     qword ptr [rsp+0F0h+var_B8], rax
0x18007de59  lea     rax, [rbp+4Fh+var_80]
0x18007de5d  mov     qword ptr [rsp+0F0h+var_C0], rax
0x18007de62  lea     rax, [rbp+4Fh+var_84]
0x18007de66  mov     qword ptr [rsp+0F0h+var_C8], rax
0x18007de6b  lea     rax, [rbp+4Fh+var_88]
0x18007de6f  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18007de74  mov     r9d, r14d
0x18007de77  mov     r8d, r15d
0x18007de7a  mov     rdx, r12
0x18007de7d  mov     rcx, [rbp+4Fh+arg_20]
0x18007de81  call    OpenRemoteQueue
0x18007de86  mov     ebx, eax
0x18007de88  test    eax, eax
0x18007de8a  jns     short loc_18007DEEE
0x18007de8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007de93  cmp     rcx, rsi
0x18007de96  jz      short loc_18007DEBC
0x18007de98  test    byte ptr [rcx+0BCh], 1
0x18007de9f  jz      short loc_18007DEBC
0x18007dea1  mov     edx, 13h
0x18007dea6  mov     r9d, eax
0x18007dea9  lea     r8, WPP_87250885c95f397c31c605fa141b682f_Traceguids
0x18007deb0  mov     rcx, [rcx+0B0h]
0x18007deb7  call    WPP_SF_d
0x18007debc  mov     eax, 0C00E0069h
0x18007dec1  cmp     ebx, 800706D9h
0x18007dec7  cmovz   ebx, eax
0x18007deca  mov     r8d, 46Dh; unsigned __int16
0x18007ded0  lea     rdx, aQmrtopen; "qmrtopen"
0x18007ded7  mov     ecx, ebx; int
0x18007ded9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18007dede  nop
0x18007dedf  lea     rcx, [rbp+4Fh+var_70]; this
0x18007dee3  call    ?free@CBindHandle@@QEAAXXZ; CBindHandle::free(void)
0x18007dee8  nop
0x18007dee9  jmp     loc_18007E027
0x18007deee  lea     rcx, [rbp+4Fh+var_78]
0x18007def2  call    ?free@?$P@VCImpersonate@@@@QEAAXXZ; P<CImpersonate>::free(void)
0x18007def7  lea     rax, [rbp+4Fh+var_70]
0x18007defb  mov     [rsp+0F0h+var_A0], rax; struct CBindHandle *
0x18007df00  mov     [rsp+0F0h+var_A8], 0; struct CAutoCloseNewRemoteReadCtxAndBind *
0x18007df09  mov     [rsp+0F0h+var_B0], 0; unsigned __int64
0x18007df12  mov     eax, [rbp+4Fh+var_88]
0x18007df15  mov     [rsp+0F0h+var_B8], eax; unsigned int
0x18007df19  mov     eax, [rbp+4Fh+var_84]
0x18007df1c  mov     [rsp+0F0h+var_C0], eax; unsigned int
0x18007df20  mov     eax, [rbp+4Fh+var_80]
0x18007df23  mov     [rsp+0F0h+var_C8], eax; unsigned int
0x18007df27  mov     [rsp+0F0h+var_D0], r14d; unsigned int
0x18007df2c  mov     r9d, r15d; unsigned int
0x18007df2f  mov     r8, r13; struct _GUID *
0x18007df32  mov     rdx, r12; struct QUEUE_FORMAT *
0x18007df35  call    ?OpenRRQueue@CQueueMgr@@QEAAJPEBUQUEUE_FORMAT@@AEBU_GUID@@KKKKK_KPEAVCAutoCloseNewRemoteReadCtxAndBind@@AEAVCBindHandle@@PEAPEAX@Z; CQueueMgr::OpenRRQueue(QUEUE_FORMAT const *,_GUID const &,ulong,ulong,ulong,ulong,ulong,unsigned __int64,CAutoCloseNewRemoteReadCtxAndBind *,CBindHandle &,void * *)
0x18007df3a  mov     ebx, eax
0x18007df3c  lea     r9, [rbp+4Fh+var_68]
0x18007df40  xor     r8d, r8d; pReturnValue
0x18007df43  lea     edx, [r8+3]; nProcNum
0x18007df47  lea     rcx, stru_1800EAE70; pProxyInfo
0x18007df4e  call    cs:__imp_NdrClientCall3
0x18007df54  test    ebx, ebx
0x18007df56  jns     short loc_18007DF6D
0x18007df58  mov     r8d, 1F40h; unsigned __int16
0x18007df5e  lea     rdx, aQmrtopen; "qmrtopen"
0x18007df65  mov     ecx, ebx; int
0x18007df67  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18007df6c  nop
0x18007df6d  lea     rcx, [rbp+4Fh+var_70]; this
0x18007df71  call    ?free@CBindHandle@@QEAAXXZ; CBindHandle::free(void)
0x18007df76  nop
0x18007df77  jmp     loc_18007E027
0x18007df7c  lea     rcx, [rbp+4Fh+var_78]
0x18007df80  call    ?free@?$P@VCImpersonate@@@@QEAAXXZ; P<CImpersonate>::free(void)
0x18007df85  movups  xmm0, xmmword ptr [r13+0]
0x18007df8a  movdqu  xmmword ptr [rbp+4Fh+var_40.Data1], xmm0
0x18007df8f  mov     rdx, [rbp+4Fh+var_60]
0x18007df93  mov     rcx, [rbp+4Fh+var_90]; this
0x18007df97  xor     esi, esi
0x18007df99  mov     [rbp+4Fh+var_90], rsi
0x18007df9d  mov     rax, [rbp+4Fh+var_58]
0x18007dfa1  mov     [rbp+4Fh+var_50], rax
0x18007dfa5  mov     [rbp+4Fh+var_48], rcx
0x18007dfa9  lea     rax, [rbp+4Fh+var_90]
0x18007dfad  mov     [rsp+0F0h+var_A0], rax; struct CBindHandle *
0x18007dfb2  lea     rax, [rbp+4Fh+var_50]
0x18007dfb6  mov     [rsp+0F0h+var_A8], rax; struct CAutoCloseNewRemoteReadCtxAndBind *
0x18007dfbb  mov     [rsp+0F0h+var_B0], rdx; unsigned __int64
0x18007dfc0  mov     [rsp+0F0h+var_B8], esi; unsigned int
0x18007dfc4  mov     [rsp+0F0h+var_C0], esi; unsigned int
0x18007dfc8  mov     [rsp+0F0h+var_C8], esi; unsigned int
0x18007dfcc  mov     [rsp+0F0h+var_D0], r14d; unsigned int
0x18007dfd1  mov     r9d, r15d; unsigned int
0x18007dfd4  lea     r8, [rbp+4Fh+var_40]; struct _GUID *
0x18007dfd8  mov     rdx, r12; struct QUEUE_FORMAT *
0x18007dfdb  call    ?OpenRRQueue@CQueueMgr@@QEAAJPEBUQUEUE_FORMAT@@AEBU_GUID@@KKKKK_KPEAVCAutoCloseNewRemoteReadCtxAndBind@@AEAVCBindHandle@@PEAPEAX@Z; CQueueMgr::OpenRRQueue(QUEUE_FORMAT const *,_GUID const &,ulong,ulong,ulong,ulong,ulong,unsigned __int64,CAutoCloseNewRemoteReadCtxAndBind *,CBindHandle &,void * *)
0x18007dfe0  mov     ebx, eax
0x18007dfe2  test    eax, eax
0x18007dfe4  jns     short loc_18007DFFB
0x18007dfe6  mov     r8d, 1388h; unsigned __int16
0x18007dfec  lea     rdx, aQmrtopen; "qmrtopen"
0x18007dff3  mov     ecx, eax; int
0x18007dff5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18007dffa  nop
0x18007dffb  lea     rcx, [rbp+4Fh+var_50]; this
0x18007dfff  call    ??1CAutoCloseNewRemoteReadCtxAndBind@@QEAA@XZ; CAutoCloseNewRemoteReadCtxAndBind::~CAutoCloseNewRemoteReadCtxAndBind(void)
0x18007e004  test    ebx, ebx
0x18007e006  jns     short loc_18007E01D
0x18007e008  mov     r8d, 1770h; unsigned __int16
0x18007e00e  lea     rdx, aQmrtopen; "qmrtopen"
0x18007e015  mov     ecx, ebx; int
0x18007e017  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18007e01c  nop
0x18007e01d  lea     rcx, [rbp+4Fh+var_90]; this
0x18007e021  call    ?free@CBindHandle@@QEAAXXZ; CBindHandle::free(void)
0x18007e026  nop
0x18007e027  lea     rcx, [rbp+4Fh+var_78]
0x18007e02b  call    ??1?$P@VCInSeqLogContext@@@@QEAA@XZ; P<CInSeqLogContext>::~P<CInSeqLogContext>(void)
0x18007e030  mov     eax, ebx
0x18007e032  add     rsp, 0C0h
0x18007e039  pop     r15
0x18007e03b  pop     r14
0x18007e03d  pop     r13
0x18007e03f  pop     r12
0x18007e041  pop     rsi
0x18007e042  pop     rbx
0x18007e043  pop     rbp
0x18007e044  retn
```
