# Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertStoresCriteria(IConfigManager2URI *,Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *)

- ea: `0x140022fac`
- end: `0x1400233df`
- name: `?ParseSslClientCertStoresCriteria@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUIConfigManager2URI@@PEAUSslClientCertInfo@2345@@Z`
- size: `1075`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::CertificateManager *__hidden this, struct IConfigManager2URI *, struct Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022b70`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000e610`
- `0x140013404`
- `0x14001e8e4`
- `0x14001f3dc`
- `0x14001f9e4`
- `0x140022fac`
- `0x140023880`
- `0x140023c28`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140023118`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140023118`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400232b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023353`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400232b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023353`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023372`
- `DMCmnUtils!CopyString` at `0x14002327b`
- `DMCmnUtils!CopyString` at `0x14002327b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseSslClientCertStoresCriteria(
        Microsoft::Windows::MDM::OmadmClient::CertificateManager *this,
        struct IConfigManager2URI *a2,
        struct Microsoft::Windows::MDM::OmadmClient::SslClientCertInfo *a3)
{
  __int64 v5; // r8
  int v6; // eax
  unsigned int v7; // ebx
  wchar_t *v8; // r14
  wchar_t *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  wchar_t *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r9
  wchar_t *v15; // rsi
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  HLOCAL v21; // rax
  _OWORD *v22; // rdx
  int v23[2]; // [rsp+20h] [rbp-E8h]
  unsigned int v24; // [rsp+30h] [rbp-D8h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v27[3]; // [rsp+48h] [rbp-C0h] BYREF
  int v28; // [rsp+60h] [rbp-A8h]
  unsigned int *v29; // [rsp+68h] [rbp-A0h]
  __int128 v30; // [rsp+70h] [rbp-98h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h]
  __int128 v32; // [rsp+88h] [rbp-80h] BYREF
  __int64 v33; // [rsp+98h] [rbp-70h]
  _QWORD v34[4]; // [rsp+A0h] [rbp-68h] BYREF
  char v35; // [rsp+C0h] [rbp-48h]
  int v36[4]; // [rsp+C8h] [rbp-40h] BYREF
  HLOCAL *p_hMem; // [rsp+D8h] [rbp-30h]
  __int64 v38; // [rsp+E0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v24 = 0;
  v27[0] = 0;
  v27[1] = "ParseSslClientCertStoresCriteria";
  v27[2] = COmaDmLogger::GetLogger();
  v28 = 2;
  v29 = &v24;
  Str = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(hMem) = 53;
    p_hMem = &hMem;
    v38 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v5,
      2u,
      (PEVENT_DATA_DESCRIPTOR)v36);
  }
  v34[0] = &v24;
  v34[1] = &Str;
  v34[2] = &v32;
  v34[3] = &v30;
  v35 = 1;
  if ( !a2 )
    goto LABEL_31;
  v6 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, const wchar_t *, wchar_t **))(*(_QWORD *)a2 + 128LL))(
         a2,
         L"Stores",
         &Str);
  v7 = v6;
  v24 = v6;
  if ( v6 == -2147023728 )
  {
    v24 = 0;
  }
  else if ( v6 < 0 )
  {
    LODWORD(v27[0]) = 12027;
LABEL_27:
    HIDWORD(v27[0]) = v6;
    goto LABEL_34;
  }
  v8 = Str;
  if ( Str )
  {
    v7 = -2147024809;
    while ( 1 )
    {
      v9 = wcschr(v8, 0xF000u);
      if ( v9 )
      {
        *v9 = 0;
        v15 = v9 + 1;
      }
      else
      {
        if ( !v8 )
        {
          LODWORD(v13) = -2147024809;
          goto LABEL_24;
        }
        v11 = 0x7FFFFFFF;
        v12 = v8;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        v13 = v11 == 0 ? 0x80070057 : 0;
        v10 = 0x7FFFFFFF - v11;
        v14 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
        if ( !v11 )
        {
          v7 = -2147024809;
LABEL_24:
          v24 = v13;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6AF,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
            (const char *)0x80070057LL,
            v23[0]);
          goto LABEL_34;
        }
        v24 = v11 == 0 ? 0x80070057 : 0;
        v15 = &v8[v14];
        if ( *v15 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v10, v13, v11, v14, *(_QWORD *)v23);
      }
      v16 = Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseStoreInfo(v10, v8, &v32, &v30);
      v24 = v16;
      if ( v16 < 0 )
      {
        LODWORD(v27[0]) = 12041;
        HIDWORD(v27[0]) = v16;
        v7 = v16;
        goto LABEL_34;
      }
      if ( !*v15 )
        break;
      v8 = v15;
    }
    v6 = Microsoft::Windows::MDM::OmadmClient::CertificateManager::TransferStoreNames(
           v17,
           688128,
           &v32,
           (char *)a3 + 40);
    v7 = v6;
    v24 = v6;
    if ( v6 < 0 )
    {
      LODWORD(v27[0]) = 12052;
      goto LABEL_27;
    }
    v6 = Microsoft::Windows::MDM::OmadmClient::CertificateManager::TransferStoreNames(v18, 98304, &v30, (char *)a3 + 40);
    v7 = v6;
    v24 = v6;
    if ( v6 < 0 )
    {
      LODWORD(v27[0]) = 12053;
      goto LABEL_27;
    }
  }
  else
  {
LABEL_31:
    hMem = 0;
    v19 = CopyString(L"MY", 0xFFFFFFFF, (unsigned __int16 **)&hMem);
    v7 = v19;
    v24 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68B,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\certificatemanager.cpp",
        (const char *)(unsigned int)v19,
        v23[0]);
      if ( hMem )
        LocalFree(hMem);
      goto LABEL_34;
    }
    v36[0] = 114688;
    v21 = hMem;
    hMem = 0;
    *(_QWORD *)&v36[2] = v21;
    v22 = (_OWORD *)*((_QWORD *)a3 + 6);
    if ( v22 == *((_OWORD **)a3 + 7) )
    {
      try
      {
        std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>::_Emplace_reallocate<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore const &>(
          (char *)a3 + 40,
          v22,
          v36);
      }
      catch ( std::bad_alloc )
      {
        v24 = -2147024882;
        if ( hMem )
          LocalFree(hMem);
        wil::details::ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd___::_ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd___(v34);
        std::vector<unsigned short *>::~vector<unsigned short *>(&v30);
        std::vector<unsigned short *>::~vector<unsigned short *>(&v32);
        Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v27);
        return 2147942414LL;
      }
    }
    else
    {
      *v22 = *(_OWORD *)v36;
      *((_QWORD *)a3 + 6) += 16LL;
    }
    if ( hMem )
      LocalFree(hMem);
  }
  v7 = v24;
LABEL_34:
  wil::details::ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd___::_ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd___(v34);
  std::vector<unsigned short *>::~vector<unsigned short *>(&v30);
  std::vector<unsigned short *>::~vector<unsigned short *>(&v32);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v27);
  return v7;
}

```

## disassembly

```asm
0x140022fac  mov     [rsp+arg_0], rbx
0x140022fb1  mov     [rsp+arg_18], rsi
0x140022fb6  push    rdi
0x140022fb7  push    r14
0x140022fb9  push    r15
0x140022fbb  sub     rsp, 0F0h
0x140022fc2  mov     rax, cs:__security_cookie
0x140022fc9  xor     rax, rsp
0x140022fcc  mov     [rsp+108h+var_20], rax
0x140022fd4  mov     r15, r8
0x140022fd7  mov     rbx, rdx
0x140022fda  xor     edi, edi
0x140022fdc  mov     [rsp+108h+var_D8], edi
0x140022fe0  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140022fe5  mov     [rsp+108h+var_C0], rdi
0x140022fea  lea     rcx, aParsesslclient_2; "ParseSslClientCertStoresCriteria"
0x140022ff1  mov     [rsp+108h+var_B8], rcx
0x140022ff6  mov     [rsp+108h+var_B0], rax
0x140022ffb  mov     [rsp+108h+var_A8], 2
0x140023003  lea     rax, [rsp+108h+var_D8]
0x140023008  mov     [rsp+108h+var_A0], rax
0x14002300d  mov     [rsp+108h+Str], rdi
0x140023012  xorps   xmm0, xmm0
0x140023015  movdqu  [rsp+108h+var_80], xmm0
0x14002301e  mov     [rsp+108h+var_70], rdi
0x140023026  movdqu  [rsp+108h+var_98], xmm0
0x14002302c  mov     [rsp+108h+var_88], rdi
0x140023034  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14002303b  jz      short loc_140023082
0x14002303d  mov     dword ptr [rsp+108h+hMem], 35h ; '5'
0x140023045  lea     rax, [rsp+108h+hMem]
0x14002304a  mov     [rsp+108h+var_30], rax
0x140023052  mov     [rsp+108h+var_28], 4
0x14002305e  lea     rax, [rsp+108h+var_40]
0x140023066  mov     qword ptr [rsp+108h+var_E8], rax; int
0x14002306b  lea     r9d, [rdi+2]
0x14002306f  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x140023076  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14002307d  call    McGenEventWrite_EventWriteTransfer
0x140023082  lea     rax, [rsp+108h+var_D8]
0x140023087  mov     [rsp+108h+var_68], rax
0x14002308f  lea     rax, [rsp+108h+Str]
0x140023094  mov     [rsp+108h+var_60], rax
0x14002309c  lea     rax, [rsp+108h+var_80]
0x1400230a4  mov     [rsp+108h+var_58], rax
0x1400230ac  lea     rax, [rsp+108h+var_98]
0x1400230b1  mov     [rsp+108h+var_50], rax
0x1400230b9  mov     [rsp+108h+var_48], 1
0x1400230c1  test    rbx, rbx
0x1400230c4  jz      loc_140023267
0x1400230ca  mov     rax, [rbx]
0x1400230cd  lea     r8, [rsp+108h+Str]
0x1400230d2  lea     rdx, aStores; "Stores"
0x1400230d9  mov     rcx, rbx
0x1400230dc  mov     rax, [rax+80h]
0x1400230e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400230e8  mov     ebx, eax
0x1400230ea  mov     [rsp+108h+var_D8], eax
0x1400230ee  cmp     eax, 80070490h
0x1400230f3  jnz     loc_140023186
0x1400230f9  mov     [rsp+108h+var_D8], edi
0x1400230fd  mov     r14, [rsp+108h+Str]
0x140023102  test    r14, r14
0x140023105  jz      loc_140023267
0x14002310b  mov     ebx, 80070057h
0x140023110  mov     edx, 0F000h; Ch
0x140023115  mov     rcx, r14; Str
0x140023118  call    cs:__imp_wcschr
0x14002311f  nop     dword ptr [rax+rax+00h]
0x140023124  mov     rsi, rax
0x140023127  test    rax, rax
0x14002312a  jnz     short loc_14002319B
0x14002312c  test    r14, r14
0x14002312f  jz      loc_1400231D4
0x140023135  mov     r8d, 7FFFFFFFh
0x14002313b  mov     rax, r14
0x14002313e  cmp     [rax], di
0x140023141  jz      short loc_14002314D
0x140023143  add     rax, 2
0x140023147  sub     r8, 1
0x14002314b  jnz     short loc_14002313E
0x14002314d  mov     rax, r8
0x140023150  neg     rax
0x140023153  sbb     edx, edx
0x140023155  not     edx
0x140023157  and     edx, ebx
0x140023159  mov     rax, r8
0x14002315c  mov     ecx, 7FFFFFFFh
0x140023161  sub     rcx, r8
0x140023164  neg     rax
0x140023167  sbb     r9, r9
0x14002316a  and     r9, rcx
0x14002316d  test    r8, r8
0x140023170  jz      short loc_1400231D0
0x140023172  mov     [rsp+108h+var_D8], edx
0x140023176  lea     rsi, [r14+r9*2]
0x14002317a  cmp     di, [rsi]
0x14002317d  jz      short loc_1400231A2
0x14002317f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "L'\0' == *pszStoreInfoEnd")
0x140023184  jmp     short loc_1400231A2
0x140023186  test    eax, eax
0x140023188  jns     loc_1400230FD
0x14002318e  mov     dword ptr [rsp+108h+var_C0], 2EFBh
0x140023196  jmp     loc_140023223
0x14002319b  mov     [rax], di
0x14002319e  add     rsi, 2
0x1400231a2  lea     r9, [rsp+108h+var_98]
0x1400231a7  lea     r8, [rsp+108h+var_80]
0x1400231af  mov     rdx, r14
0x1400231b2  call    ?ParseStoreInfo@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGAEAV?$vector@PEAGV?$allocator@PEAG@std@@@std@@1@Z; Microsoft::Windows::MDM::OmadmClient::CertificateManager::ParseStoreInfo(ushort const *,std::vector<ushort *> &,std::vector<ushort *> &)
0x1400231b7  mov     [rsp+108h+var_D8], eax
0x1400231bb  test    eax, eax
0x1400231bd  js      loc_140023257
0x1400231c3  cmp     di, [rsi]
0x1400231c6  jz      short loc_1400231FB
0x1400231c8  mov     r14, rsi
0x1400231cb  jmp     loc_140023110
0x1400231d0  mov     ebx, edx
0x1400231d2  jmp     short loc_1400231D6
0x1400231d4  mov     edx, ebx
0x1400231d6  mov     [rsp+108h+var_D8], edx
0x1400231da  mov     rcx, [rsp+108h]; this
0x1400231e2  mov     r9d, ebx; char *
0x1400231e5  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400231ec  mov     edx, 6AFh; void *
0x1400231f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400231f6  jmp     loc_1400232C5
0x1400231fb  lea     r9, [r15+28h]
0x1400231ff  lea     r8, [rsp+108h+var_80]
0x140023207  mov     edx, 0A8000h
0x14002320c  call    ?TransferStoreNames@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJKAEAV?$vector@PEAGV?$allocator@PEAG@std@@@std@@AEAV?$vector@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@V?$allocator@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@@std@@@7@@Z; Microsoft::Windows::MDM::OmadmClient::CertificateManager::TransferStoreNames(ulong,std::vector<ushort *> &,std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore> &)
0x140023211  mov     ebx, eax
0x140023213  mov     [rsp+108h+var_D8], eax
0x140023217  test    eax, eax
0x140023219  jns     short loc_14002322C
0x14002321b  mov     dword ptr [rsp+108h+var_C0], 2F14h
0x140023223  mov     dword ptr [rsp+108h+var_C0+4], eax
0x140023227  jmp     loc_1400232C5
0x14002322c  lea     r9, [r15+28h]
0x140023230  lea     r8, [rsp+108h+var_98]
0x140023235  mov     edx, 18000h
0x14002323a  call    ?TransferStoreNames@CertificateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJKAEAV?$vector@PEAGV?$allocator@PEAG@std@@@std@@AEAV?$vector@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@V?$allocator@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@@std@@@7@@Z; Microsoft::Windows::MDM::OmadmClient::CertificateManager::TransferStoreNames(ulong,std::vector<ushort *> &,std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore> &)
0x14002323f  mov     ebx, eax
0x140023241  mov     [rsp+108h+var_D8], eax
0x140023245  test    eax, eax
0x140023247  jns     loc_14002335F
0x14002324d  mov     dword ptr [rsp+108h+var_C0], 2F15h
0x140023255  jmp     short loc_140023223
0x140023257  mov     dword ptr [rsp+108h+var_C0], 2F09h
0x14002325f  mov     dword ptr [rsp+108h+var_C0+4], eax
0x140023263  mov     ebx, eax
0x140023265  jmp     short loc_1400232C5
0x140023267  mov     [rsp+108h+hMem], rdi
0x14002326c  lea     r8, [rsp+108h+hMem]
0x140023271  or      edx, 0FFFFFFFFh
0x140023274  lea     rcx, aMy; "MY"
0x14002327b  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140023282  nop     dword ptr [rax+rax+00h]
0x140023287  mov     ebx, eax
0x140023289  mov     [rsp+108h+var_D8], eax
0x14002328d  test    eax, eax
0x14002328f  jns     short loc_1400232FD
0x140023291  mov     rcx, [rsp+108h]; this
0x140023299  mov     r9d, eax; char *
0x14002329c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400232a3  mov     edx, 68Bh; void *
0x1400232a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400232ad  nop
0x1400232ae  mov     rcx, [rsp+108h+hMem]; hMem
0x1400232b3  test    rcx, rcx
0x1400232b6  jz      short loc_1400232C5
0x1400232b8  call    cs:__imp_LocalFree
0x1400232bf  nop     dword ptr [rax+rax+00h]
0x1400232c4  nop
0x1400232c5  lea     rcx, [rsp+108h+var_68]
0x1400232cd  call    wil__details__ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd______ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd___
0x1400232d2  nop
0x1400232d3  lea     rcx, [rsp+108h+var_98]
0x1400232d8  call    ??1?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAA@XZ; std::vector<ushort *>::~vector<ushort *>(void)
0x1400232dd  nop
0x1400232de  lea     rcx, [rsp+108h+var_80]
0x1400232e6  call    ??1?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAA@XZ; std::vector<ushort *>::~vector<ushort *>(void)
0x1400232eb  nop
0x1400232ec  lea     rcx, [rsp+108h+var_C0]; this
0x1400232f1  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x1400232f6  mov     eax, ebx
0x1400232f8  jmp     loc_1400233B5
0x1400232fd  mov     [rsp+108h+var_40], 1C000h
0x140023308  mov     rax, [rsp+108h+hMem]
0x14002330d  mov     [rsp+108h+hMem], rdi
0x140023312  mov     qword ptr [rsp+108h+var_40+8], rax
0x14002331a  lea     rcx, [r15+28h]
0x14002331e  mov     rdx, [rcx+8]
0x140023322  cmp     rdx, [rcx+10h]
0x140023326  jz      short loc_14002333B
0x140023328  movups  xmm0, xmmword ptr [rsp+108h+var_40]
0x140023330  movdqu  xmmword ptr [rdx], xmm0
0x140023334  add     qword ptr [rcx+8], 10h
0x140023339  jmp     short loc_140023349
0x14002333b  lea     r8, [rsp+108h+var_40]
0x140023343  call    ??$_Emplace_reallocate@AEBUSslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@@?$vector@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@V?$allocator@USslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@@std@@@std@@AEAAPEAUSslClientCertStore@OmadmClient@MDM@Windows@Microsoft@@QEAU23456@AEBU23456@@Z; std::vector<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore>::_Emplace_reallocate<Microsoft::Windows::MDM::OmadmClient::SslClientCertStore const &>(Microsoft::Windows::MDM::OmadmClient::SslClientCertStore * const,Microsoft::Windows::MDM::OmadmClient::SslClientCertStore const &)
0x140023348  nop
0x140023349  mov     rcx, [rsp+108h+hMem]; hMem
0x14002334e  test    rcx, rcx
0x140023351  jz      short loc_14002335F
0x140023353  call    cs:__imp_LocalFree
0x14002335a  nop     dword ptr [rax+rax+00h]
0x14002335f  mov     ebx, [rsp+108h+var_D8]
0x140023363  jmp     loc_1400232C5
0x140023368  mov     rcx, [rsp+108h+hMem]; hMem
0x14002336d  test    rcx, rcx
0x140023370  jz      short loc_14002337F
0x140023372  call    cs:__imp_LocalFree
0x140023379  nop     dword ptr [rax+rax+00h]
0x14002337e  nop
0x14002337f  lea     rcx, [rsp+108h+var_68]
0x140023387  call    wil__details__ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd______ScopeExitFn__lambda_103f3f025aa630c3d8d230ed96e9ecdd___
0x14002338c  nop
0x14002338d  lea     rcx, [rsp+108h+var_98]
0x140023392  call    ??1?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAA@XZ; std::vector<ushort *>::~vector<ushort *>(void)
0x140023397  nop
0x140023398  lea     rcx, [rsp+108h+var_80]
0x1400233a0  call    ??1?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAA@XZ; std::vector<ushort *>::~vector<ushort *>(void)
0x1400233a5  nop
0x1400233a6  lea     rcx, [rsp+108h+var_C0]; this
0x1400233ab  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x1400233b0  mov     eax, 8007000Eh
0x1400233b5  mov     rcx, [rsp+108h+var_20]
0x1400233bd  xor     rcx, rsp; StackCookie
0x1400233c0  call    __security_check_cookie
0x1400233c5  lea     r11, [rsp+108h+var_18]
0x1400233cd  mov     rbx, [r11+20h]
0x1400233d1  mov     rsi, [r11+38h]
0x1400233d5  mov     rsp, r11
0x1400233d8  pop     r15
0x1400233da  pop     r14
0x1400233dc  pop     rdi
0x1400233dd  retn
```
