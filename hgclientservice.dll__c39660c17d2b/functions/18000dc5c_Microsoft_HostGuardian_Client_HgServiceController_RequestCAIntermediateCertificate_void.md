# Microsoft::HostGuardian::Client::HgServiceController::RequestCAIntermediateCertificate(void)

- ea: `0x18000dc5c`
- end: `0x18000e001`
- name: `?RequestCAIntermediateCertificate@HgServiceController@Client@HostGuardian@Microsoft@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `933`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgServicePlugin *this, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dab8`

## callees

- `0x1800064b4`
- `0x180007394`
- `0x180008760`
- `0x18000b4c4`
- `0x18000c8ec`
- `0x18000dc5c`
- `0x18000e024`
- `0x180012a08`
- `0x1800136a4`
- `0x1800141a4`
- `0x180014298`
- `0x180017010`

## string_xrefs

- `0x18000dd46`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000dd7c`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000ddc1`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000df60`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000dfda`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000dfef`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000dd30`: `Plugin returned unexpected attestation results.`
- `0x18000df4a`: `Plugin returned unexpected results for VSM CA intermediate certificate.`
- `0x18000deb1`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::RequestCAIntermediateCertificate(
        Microsoft::HostGuardian::Client::HgServicePlugin *this,
        __int64 a2)
{
  char v4; // bl
  int AttestationResults; // eax
  char v6; // al
  int v7; // eax
  Microsoft::HostGuardian::Client::VsmCaAgent *v8; // rax
  __int64 (__fastcall *v9)(_QWORD, _QWORD, char *, _DWORD *); // rax
  int v10; // esi
  enum ShsAttestationFlag *v12; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  int *v16; // [rsp+20h] [rbp-E0h]
  char *v17; // [rsp+30h] [rbp-D0h]
  char *v18; // [rsp+30h] [rbp-D0h]
  struct AttestationResult *v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v21; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v22; // [rsp+70h] [rbp-90h] BYREF
  struct AttestationResult *v23; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v26; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 *v27; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 *v28; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v29; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+BCh] [rbp-44h]
  unsigned __int8 *v32; // [rsp+C0h] [rbp-40h]
  int v33[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v34; // [rsp+D0h] [rbp-30h]
  _DWORD v35[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int8 *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  __int64 v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  Microsoft::HostGuardian::Client::HgServicePlugin *v40; // [rsp+100h] [rbp+0h]
  wchar_t **v41; // [rsp+108h] [rbp+8h]
  unsigned int *v42; // [rsp+110h] [rbp+10h]
  struct AttestationResult **v43; // [rsp+118h] [rbp+18h]
  char v44; // [rsp+120h] [rbp+20h]
  Microsoft::HostGuardian::Client::HgServicePlugin *v45; // [rsp+128h] [rbp+28h]
  wchar_t **v46; // [rsp+130h] [rbp+30h]
  unsigned int *v47; // [rsp+138h] [rbp+38h]
  struct AttestationResult **v48; // [rsp+140h] [rbp+40h]
  char v49; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  unsigned int v51; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v52; // [rsp+190h] [rbp+90h] BYREF
  int v53; // [rsp+198h] [rbp+98h] BYREF

  v19 = 0;
  v51 = 0;
  v53 = 0;
  v24 = 0;
  v25 = 2;
  v40 = this;
  v41 = &v24;
  v42 = &v51;
  v43 = &v19;
  v4 = 1;
  v44 = 1;
  v12 = (enum ShsAttestationFlag *)&v53;
  AttestationResults = Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults(
                         this,
                         0,
                         1,
                         (enum AttestationResultType *)&v25);
  if ( AttestationResults < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)(unsigned int)AttestationResults,
      (int)&v53);
  if ( v51 != 1 || !v19 || !*((_QWORD *)v19 + 2) || (v6 = 0, !*((_DWORD *)v19 + 2)) )
    v6 = 1;
  LOBYTE(v12) = v6;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x217,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    (const char *)0x8000FFFFLL,
    (int)v12,
    (bool)"Plugin returned unexpected attestation results.",
    (const char *)&v51,
    &v19);
  LOBYTE(v13) = *(_DWORD *)v19 != 2;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x21B,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    (const char *)0x8000FFFFLL,
    v13,
    (bool)"Unexpected data from a successful attestation call.",
    v17);
  if ( v24 )
  {
    v7 = Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache(
           (__int64)this,
           v24,
           v53,
           v51,
           (__int64)v19);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x220,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
        (const char *)(unsigned int)v7,
        v14);
  }
  v27 = 0;
  v20 = 0;
  v28 = 0;
  v21 = 0;
  v29 = 0;
  v22 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v8 = Microsoft::HostGuardian::Client::VsmCaAgent::Instance();
  Microsoft::HostGuardian::Client::VsmCaAgent::CreateReportInternal(v8, &v27, &v20, &v28, &v21, &v29, &v22);
  v35[1] = 0;
  v33[1] = 0;
  v31 = 0;
  v35[0] = v20;
  v36 = v27;
  v33[0] = v21;
  v34 = v28;
  v30 = v22;
  v32 = v29;
  v23 = 0;
  v52 = 0;
  v26 = 0;
  v45 = this;
  v46 = &v26;
  v47 = &v52;
  v48 = &v23;
  v49 = 1;
  v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, char *, _DWORD *))*((_QWORD *)this + 7);
  if ( v9 )
  {
    v18 = (char *)&v53;
    v16 = v33;
    v10 = v9(*((_QWORD *)this + 2), 0, (char *)v19 + 8, v35);
  }
  else
  {
    v10 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      (const char *)0x80004001LL,
      v15);
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)(unsigned int)v10,
      (int)v16);
  if ( v52 == 1 && v23 && *((_QWORD *)v23 + 2) && *((_DWORD *)v23 + 2) )
    v4 = 0;
  LOBYTE(v16) = v4;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x253,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    (const char *)0x8000FFFFLL,
    (int)v16,
    (bool)"Plugin returned unexpected results for VSM CA intermediate certificate.",
    v18);
  std::vector<unsigned char>::vector<unsigned char>(
    a2,
    *((_QWORD *)v23 + 2),
    *((_QWORD *)v23 + 2) + *((unsigned int *)v23 + 2));
  Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(this, v26, v52, v23);
  Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(this, v24, v51, v19);
  return a2;
}

```

## disassembly

```asm
0x18000dc5c  mov     [rsp-8+arg_8], rbx
0x18000dc61  push    rbp
0x18000dc62  push    rsi
0x18000dc63  push    r12
0x18000dc65  push    r14
0x18000dc67  push    r15
0x18000dc69  lea     rbp, [rsp-50h]
0x18000dc6e  sub     rsp, 150h
0x18000dc75  mov     r15, rdx
0x18000dc78  mov     r14, rcx
0x18000dc7b  xor     r12d, r12d
0x18000dc7e  mov     [rsp+170h+var_110], r12
0x18000dc83  mov     [rbp+70h+arg_0], r12d
0x18000dc8a  mov     [rbp+70h+arg_18], r12d
0x18000dc91  mov     [rbp+70h+var_F0], r12
0x18000dc95  mov     [rbp+70h+var_E8], 2
0x18000dc9c  mov     [rbp+70h+var_70], rcx
0x18000dca0  lea     rax, [rbp+70h+var_F0]
0x18000dca4  mov     [rbp+70h+var_68], rax
0x18000dca8  lea     rax, [rbp+70h+arg_0]
0x18000dcaf  mov     [rbp+70h+var_60], rax
0x18000dcb3  lea     rax, [rsp+170h+var_110]
0x18000dcb8  mov     [rbp+70h+var_58], rax
0x18000dcbc  lea     ebx, [r12+1]
0x18000dcc1  mov     [rbp+70h+var_50], bl
0x18000dcc4  lea     rax, [rsp+170h+var_110]
0x18000dcc9  mov     [rsp+170h+var_138], rax; struct AttestationResult **
0x18000dcce  lea     rax, [rbp+70h+arg_0]
0x18000dcd5  mov     [rsp+170h+var_140], rax; char *
0x18000dcda  lea     rax, [rbp+70h+var_F0]
0x18000dcde  mov     [rsp+170h+var_148], rax; wchar_t **
0x18000dce3  lea     rax, [rbp+70h+arg_18]
0x18000dcea  mov     [rsp+170h+var_150], rax; int
0x18000dcef  lea     r9, [rbp+70h+var_E8]; enum AttestationResultType *
0x18000dcf3  mov     r8d, ebx; unsigned int
0x18000dcf6  xor     edx, edx; wchar_t *
0x18000dcf8  call    ?QueryAttestationResults@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJQEA_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults(wchar_t * const,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x18000dcfd  mov     rcx, [rbp+78h]; this
0x18000dd01  test    eax, eax
0x18000dd03  js      loc_18000DFEC
0x18000dd09  cmp     [rbp+70h+arg_0], ebx
0x18000dd0f  jnz     short loc_18000DD2A
0x18000dd11  mov     rax, [rsp+170h+var_110]
0x18000dd16  test    rax, rax
0x18000dd19  jz      short loc_18000DD2A
0x18000dd1b  cmp     [rax+10h], r12
0x18000dd1f  jz      short loc_18000DD2A
0x18000dd21  cmp     [rax+8], r12d
0x18000dd25  mov     al, r12b
0x18000dd28  jnz     short loc_18000DD2C
0x18000dd2a  mov     al, bl
0x18000dd2c  mov     rcx, [rbp+78h]; this
0x18000dd30  lea     rdx, aPluginReturned; "Plugin returned unexpected attestation "...
0x18000dd37  mov     [rsp+170h+var_148], rdx; bool
0x18000dd3c  mov     byte ptr [rsp+170h+var_150], al; int
0x18000dd40  mov     r9d, 8000FFFFh; char *
0x18000dd46  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000dd4d  mov     edx, 217h; void *
0x18000dd52  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000dd57  mov     rax, [rsp+170h+var_110]
0x18000dd5c  cmp     dword ptr [rax], 2
0x18000dd5f  setnz   al
0x18000dd62  mov     rcx, [rbp+78h]; this
0x18000dd66  lea     rdx, aUnexpectedData; "Unexpected data from a successful attes"...
0x18000dd6d  mov     [rsp+170h+var_148], rdx; bool
0x18000dd72  mov     byte ptr [rsp+170h+var_150], al; int
0x18000dd76  mov     r9d, 8000FFFFh; char *
0x18000dd7c  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000dd83  mov     edx, 21Bh; void *
0x18000dd88  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000dd8d  mov     rdx, [rbp+70h+var_F0]
0x18000dd91  test    rdx, rdx
0x18000dd94  jz      short loc_18000DDD2
0x18000dd96  mov     rax, [rsp+170h+var_110]
0x18000dd9b  mov     [rsp+170h+var_150], rax; int
0x18000dda0  mov     r9d, [rbp+70h+arg_0]
0x18000dda7  mov     r8d, [rbp+70h+arg_18]
0x18000ddae  mov     rcx, r14
0x18000ddb1  call    ?AddCertificatesToCache@HgServiceController@Client@HostGuardian@Microsoft@@AEAAJPEA_WW4ShsAttestationFlag@@IPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::AddCertificatesToCache(wchar_t *,ShsAttestationFlag,uint,AttestationResult *)
0x18000ddb6  mov     rcx, [rbp+78h]; this
0x18000ddba  test    eax, eax
0x18000ddbc  jns     short loc_18000DDD2
0x18000ddbe  mov     r9d, eax; char *
0x18000ddc1  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000ddc8  mov     edx, 220h; void *
0x18000ddcd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ddd2  mov     [rbp+70h+var_D8], r12
0x18000ddd6  mov     [rsp+170h+var_108], r12d
0x18000dddb  mov     [rbp+70h+var_D0], r12
0x18000dddf  mov     [rsp+170h+var_104], r12d
0x18000dde4  mov     [rbp+70h+var_C8], r12
0x18000dde8  mov     [rsp+170h+var_100], r12d
0x18000dded  mov     [rbp+70h+var_88], r12
0x18000ddf1  mov     [rbp+70h+var_80], r12
0x18000ddf5  mov     [rbp+70h+var_78], r12
0x18000ddf9  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18000ddfe  lea     rcx, [rsp+170h+var_100]
0x18000de03  mov     [rsp+170h+var_140], rcx; unsigned int *
0x18000de08  lea     rcx, [rbp+70h+var_C8]
0x18000de0c  mov     [rsp+170h+var_148], rcx; unsigned __int8 **
0x18000de11  lea     rcx, [rsp+170h+var_104]
0x18000de16  mov     [rsp+170h+var_150], rcx; int
0x18000de1b  lea     r9, [rbp+70h+var_D0]; unsigned __int8 **
0x18000de1f  lea     r8, [rsp+170h+var_108]; unsigned int *
0x18000de24  lea     rdx, [rbp+70h+var_D8]; unsigned __int8 **
0x18000de28  mov     rcx, rax; this
0x18000de2b  call    ?CreateReportInternal@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXPEAPEAEPEAI0101@Z; Microsoft::HostGuardian::Client::VsmCaAgent::CreateReportInternal(uchar * *,uint *,uchar * *,uint *,uchar * *,uint *)
0x18000de30  mov     [rbp+70h+var_94], r12d
0x18000de34  mov     [rbp+70h+var_A4], r12d
0x18000de38  mov     [rbp+70h+var_B4], r12d
0x18000de3c  mov     eax, [rsp+170h+var_108]
0x18000de40  mov     [rbp+70h+var_98], eax
0x18000de43  mov     rax, [rbp+70h+var_D8]
0x18000de47  mov     [rbp+70h+var_90], rax
0x18000de4b  mov     eax, [rsp+170h+var_104]
0x18000de4f  mov     [rbp+70h+var_A8], eax
0x18000de52  mov     rax, [rbp+70h+var_D0]
0x18000de56  mov     [rbp+70h+var_A0], rax
0x18000de5a  mov     eax, [rsp+170h+var_100]
0x18000de5e  mov     [rbp+70h+var_B8], eax
0x18000de61  mov     rax, [rbp+70h+var_C8]
0x18000de65  mov     [rbp+70h+var_B0], rax
0x18000de69  mov     [rsp+170h+var_F8], r12
0x18000de6e  mov     [rbp+70h+arg_10], r12d
0x18000de75  mov     [rbp+70h+var_E0], r12
0x18000de79  mov     [rbp+70h+var_48], r14
0x18000de7d  lea     rax, [rbp+70h+var_E0]
0x18000de81  mov     [rbp+70h+var_40], rax
0x18000de85  lea     rax, [rbp+70h+arg_10]
0x18000de8c  mov     [rbp+70h+var_38], rax
0x18000de90  lea     rax, [rsp+170h+var_F8]
0x18000de95  mov     [rbp+70h+var_30], rax
0x18000de99  mov     [rbp+70h+var_28], bl
0x18000de9c  mov     rax, [r14+38h]
0x18000dea0  test    rax, rax
0x18000dea3  jnz     short loc_18000DEC2
0x18000dea5  mov     rcx, [rbp+78h]; this
0x18000dea9  mov     esi, 80004001h
0x18000deae  mov     r9d, esi; char *
0x18000deb1  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x18000deb8  lea     edx, [rax+5Fh]; void *
0x18000debb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dec0  jmp     short loc_18000DF19
0x18000dec2  mov     r8, [rsp+170h+var_110]
0x18000dec7  add     r8, 8
0x18000decb  lea     rcx, [rsp+170h+var_F8]
0x18000ded0  mov     [rsp+170h+var_128], rcx
0x18000ded5  lea     rcx, [rbp+70h+arg_10]
0x18000dedc  mov     [rsp+170h+var_130], rcx
0x18000dee1  lea     rcx, [rbp+70h+var_E0]
0x18000dee5  mov     [rsp+170h+var_138], rcx
0x18000deea  lea     rcx, [rbp+70h+arg_18]
0x18000def1  mov     [rsp+170h+var_140], rcx; char *
0x18000def6  lea     rcx, [rbp+70h+var_B8]
0x18000defa  mov     [rsp+170h+var_148], rcx
0x18000deff  lea     rcx, [rbp+70h+var_A8]
0x18000df03  mov     [rsp+170h+var_150], rcx; int
0x18000df08  lea     r9, [rbp+70h+var_98]
0x18000df0c  xor     edx, edx
0x18000df0e  mov     rcx, [r14+10h]
0x18000df12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df17  mov     esi, eax
0x18000df19  mov     rcx, [rbp+78h]; this
0x18000df1d  test    esi, esi
0x18000df1f  js      loc_18000DFD7
0x18000df25  cmp     [rbp+70h+arg_10], ebx
0x18000df2b  jnz     short loc_18000DF46
0x18000df2d  mov     rax, [rsp+170h+var_F8]
0x18000df32  test    rax, rax
0x18000df35  jz      short loc_18000DF46
0x18000df37  cmp     [rax+10h], r12
0x18000df3b  jz      short loc_18000DF46
0x18000df3d  cmp     [rax+8], r12d
0x18000df41  jz      short loc_18000DF46
0x18000df43  mov     bl, r12b
0x18000df46  mov     rcx, [rbp+78h]; this
0x18000df4a  lea     rax, aPluginReturned_0; "Plugin returned unexpected results for "...
0x18000df51  mov     [rsp+170h+var_148], rax; bool
0x18000df56  mov     byte ptr [rsp+170h+var_150], bl; int
0x18000df5a  mov     r9d, 8000FFFFh; char *
0x18000df60  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000df67  mov     edx, 253h; void *
0x18000df6c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000df71  mov     rax, [rsp+170h+var_F8]
0x18000df76  mov     rdx, [rax+10h]
0x18000df7a  mov     r8d, [rax+8]
0x18000df7e  add     r8, rdx
0x18000df81  mov     rcx, r15
0x18000df84  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18000df89  nop
0x18000df8a  mov     r9, [rsp+170h+var_F8]; struct AttestationResult *
0x18000df8f  mov     r8d, [rbp+70h+arg_10]; unsigned int
0x18000df96  mov     rdx, [rbp+70h+var_E0]; wchar_t *
0x18000df9a  mov     rcx, r14; this
0x18000df9d  call    ?FreeAttestationResults@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJQEA_WIPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(wchar_t * const,uint,AttestationResult *)
0x18000dfa2  nop
0x18000dfa3  mov     r9, [rsp+170h+var_110]; struct AttestationResult *
0x18000dfa8  mov     r8d, [rbp+70h+arg_0]; unsigned int
0x18000dfaf  mov     rdx, [rbp+70h+var_F0]; wchar_t *
0x18000dfb3  mov     rcx, r14; this
0x18000dfb6  call    ?FreeAttestationResults@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJQEA_WIPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::FreeAttestationResults(wchar_t * const,uint,AttestationResult *)
0x18000dfbb  nop
0x18000dfbc  mov     rax, r15
0x18000dfbf  mov     rbx, [rsp+170h+arg_8]
0x18000dfc7  add     rsp, 150h
0x18000dfce  pop     r15
0x18000dfd0  pop     r14
0x18000dfd2  pop     r12
0x18000dfd4  pop     rsi
0x18000dfd5  pop     rbp
0x18000dfd6  retn
0x18000dfd7  mov     r9d, esi; char *
0x18000dfda  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000dfe1  mov     edx, 24Dh; void *
0x18000dfe6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000dfec  mov     r9d, eax; char *
0x18000dfef  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000dff6  mov     edx, 211h; void *
0x18000dffb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
