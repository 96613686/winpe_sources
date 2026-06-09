# FTP_DATA_CHANNEL::OnNewConnectionCompletion(FTP_ASYNC_CONTEXT *)

- ea: `0x180040118`
- end: `0x180040849`
- name: `?OnNewConnectionCompletion@FTP_DATA_CHANNEL@@AEAAXPEAVFTP_ASYNC_CONTEXT@@@Z`
- size: `1841`
- prototype: `void __fastcall(FTP_DATA_CHANNEL *__hidden this, struct FTP_ASYNC_CONTEXT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x1800070f8`
- `0x180008224`
- `0x180009090`
- `0x180034794`
- `0x180038ac0`
- `0x18003f9b4`
- `0x180040118`
- `0x180041160`
- `0x1800412e0`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `WS2_32!GetNameInfoW` at `0x180040280`
- `WS2_32!GetNameInfoW` at `0x1800402ae`
- `WS2_32!GetNameInfoW` at `0x18004057e`
- `WS2_32!GetNameInfoW` at `0x1800405a8`
- `WS2_32!GetNameInfoW` at `0x180040280`
- `WS2_32!GetNameInfoW` at `0x1800402ae`
- `WS2_32!GetNameInfoW` at `0x18004057e`
- `WS2_32!GetNameInfoW` at `0x1800405a8`
- `WS2_32!__imp_ntohs` at `0x1800402bc`
- `WS2_32!__imp_ntohs` at `0x1800402ce`
- `WS2_32!__imp_ntohs` at `0x1800404c8`
- `WS2_32!__imp_ntohs` at `0x1800402bc`
- `WS2_32!__imp_ntohs` at `0x1800402ce`
- `WS2_32!__imp_ntohs` at `0x1800404c8`
- `Secur32!DeleteSecurityContext` at `0x180040708`
- `Secur32!DeleteSecurityContext` at `0x180040708`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18004080f`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18004080f`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x18004076d`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x18004076d`
- `iisutil!PuDbgPrint` at `0x180040695`
- `iisutil!PuDbgPrint` at `0x180040695`
- `iisutil!WriteRefTraceLog` at `0x1800407f2`
- `iisutil!WriteRefTraceLog` at `0x1800407f2`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800403a9`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18004065f`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800403a9`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18004065f`
- `CRYPT32!CertFreeCertificateContext` at `0x180040721`
- `CRYPT32!CertFreeCertificateContext` at `0x180040721`

## string_xrefs

- `0x18004040d`: `DataChannelOpened`
- `0x18004067a`: `FTP_DATA_CHANNEL::OnNewConnectionCompletion`
- `0x180040687`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_data_channel.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FTP_DATA_CHANNEL::OnNewConnectionCompletion(FTP_DATA_CHANNEL *this, struct FTP_ASYNC_CONTEXT *a2)
{
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // r13
  FTP_ASYNC_SOCKET *v5; // rdi
  int updated; // ebx
  unsigned int v7; // esi
  const unsigned __int16 *v8; // rdi
  __int64 v9; // rax
  socklen_t v10; // edx
  socklen_t v11; // edx
  __int64 v12; // rbx
  CEtwTracer *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // rsi
  __int64 v20; // rax
  _WORD *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  const SOCKADDR *v24; // rcx
  socklen_t v25; // edx
  socklen_t v26; // edx
  __int64 v27; // rbx
  CEtwTracer *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  const CERT_CONTEXT *v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // rdx
  unsigned __int32 v34; // ebx
  __int64 v35; // [rsp+48h] [rbp-C8h]
  u_short v36; // [rsp+90h] [rbp-80h] BYREF
  u_short v37; // [rsp+98h] [rbp-78h] BYREF
  struct _EVENT_TRACE_HEADER v38; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v39; // [rsp+D0h] [rbp-40h]
  int v40; // [rsp+D8h] [rbp-38h]
  WCHAR *v41; // [rsp+E0h] [rbp-30h]
  int v42; // [rsp+E8h] [rbp-28h]
  u_short *v43; // [rsp+F0h] [rbp-20h]
  int v44; // [rsp+F8h] [rbp-18h]
  WCHAR *v45; // [rsp+100h] [rbp-10h]
  int v46; // [rsp+108h] [rbp-8h]
  u_short *v47; // [rsp+110h] [rbp+0h]
  int v48; // [rsp+118h] [rbp+8h]
  wchar_t v49[64]; // [rsp+120h] [rbp+10h] BYREF
  WCHAR pNodeBuffer[2]; // [rsp+1A0h] [rbp+90h] BYREF
  _BYTE v51[124]; // [rsp+1A4h] [rbp+94h] BYREF

  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(*((FTP_SESSION **)this + 9));
  FTP_DATA_CHANNEL::StopConnectionIdleMonitor(this);
  *((_QWORD *)this + 270) = 0;
  *((_QWORD *)this + 271) = 0;
  v5 = (FTP_DATA_CHANNEL *)((char *)this + 1344);
  if ( *((_QWORD *)this + 170) == -1 )
  {
LABEL_6:
    if ( *((_WORD *)this + 1198) )
    {
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 144LL))(g_pFtpServer);
      *((_WORD *)this + 1198) = 0;
    }
    if ( *((int *)a2 + 17) >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v9 + 8) && (*(_BYTE *)(v9 + 40) & 1) != 0 && *(_DWORD *)(v9 + 44) >= 4u )
      {
        wcscpy(v49, L"?");
        memset_0(&v49[2], 0, 0x7Cu);
        wcscpy(pNodeBuffer, L"?");
        memset_0(v51, 0, sizeof(v51));
        v10 = 16;
        if ( *((_WORD *)this + 432) != 2 )
          v10 = 28;
        GetNameInfoW((const SOCKADDR *)this + 54, v10, pNodeBuffer, 0x40u, 0, 0, 2);
        v11 = 16;
        if ( *((_WORD *)this + 496) != 2 )
          v11 = 28;
        GetNameInfoW((const SOCKADDR *)this + 62, v11, v49, 0x40u, 0, 0, 2);
        v37 = ntohs(*((_WORD *)this + 433));
        v36 = ntohs(*((_WORD *)this + 497));
        v12 = *((_QWORD *)this + 9) + 368LL;
        v13 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        memset_0(&v38.FieldTypeFlags, 0, 0x7Eu);
        v38.UserTime = 1703936;
        v38.Size = 128;
        v38.Class.Version = 1;
        v38.Class.Type = 5;
        v38.GuidPtr = (ULONGLONG)&`FtpConnectionEvents::GetAreaGuid'::`2'::AreaGuid;
        v39 = v12;
        v40 = 16;
        v41 = v49;
        v14 = -1;
        do
          ++v14;
        while ( v49[v14] );
        v42 = 2 * v14 + 2;
        v43 = &v36;
        v44 = 2;
        v45 = pNodeBuffer;
        v15 = -1;
        do
          ++v15;
        while ( pNodeBuffer[v15] );
        v46 = 2 * v15 + 2;
        v47 = &v37;
        v48 = 2;
        CEtwTracer::EtwTraceEvent(v13, &v38);
      }
      v16 = *((_QWORD *)this + 9);
      v17 = *((_QWORD *)this + 270);
      v18 = *((_QWORD *)this + 271);
      v19 = *(_QWORD *)(v16 + 904);
      v20 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v16 + 1056) + 48LL))(*(_QWORD *)(v16 + 1056));
      v35 = v17;
      v21 = (_WORD *)((char *)this + 992);
      FTP_SESSION::Log(
        v16,
        5,
        *(_QWORD *)(*((_QWORD *)this + 9) + 304LL),
        (char *)this + 992,
        (char *)this + 864,
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 96LL) + 48LL),
        v20,
        v19,
        v18,
        v35,
        L"DataChannelOpened");
      if ( *((_DWORD *)ReferencedSiteConfig + 177) )
      {
        v22 = *(_QWORD *)(*((_QWORD *)this + 9) + 1080LL);
        if ( *(_WORD *)(v22 + 448) == 23 )
        {
          if ( *v21 != 23
            || *(_DWORD *)(v22 + 472) != *((_DWORD *)this + 254)
            || *(_QWORD *)(v22 + 464) != *((_QWORD *)this + 126)
            || *(_QWORD *)(v22 + 456) != *((_QWORD *)this + 125) )
          {
            goto LABEL_31;
          }
        }
        else if ( *v21 != 2 || *(_DWORD *)(v22 + 452) != *((_DWORD *)this + 249) )
        {
          goto LABEL_31;
        }
        if ( ntohs(*((_WORD *)this + 497)) < 0x400u )
        {
LABEL_31:
          v23 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          if ( *(_DWORD *)(v23 + 8) && (*(_BYTE *)(v23 + 40) & 0x10) != 0 && *(_DWORD *)(v23 + 44) >= 3u )
          {
            wcscpy(pNodeBuffer, L"?");
            memset_0(v51, 0, sizeof(v51));
            *(_DWORD *)v49 = 63;
            memset_0(&v49[2], 0, 0x7Cu);
            v24 = (const SOCKADDR *)(*(_QWORD *)(*((_QWORD *)this + 9) + 1080LL) + 448LL);
            v25 = 16;
            if ( v24->sa_family != 2 )
              v25 = 28;
            GetNameInfoW(v24, v25, pNodeBuffer, 0x40u, 0, 0, 2);
            v26 = 16;
            if ( *v21 != 2 )
              v26 = 28;
            GetNameInfoW((const SOCKADDR *)this + 62, v26, v49, 0x40u, 0, 0, 2);
            v27 = *((_QWORD *)this + 9) + 368LL;
            v28 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            memset_0(&v38.FieldTypeFlags, 0, 0x5Eu);
            v38.UserTime = 1703936;
            v38.Size = 96;
            v38.Class.Version = 1;
            v38.Class.Type = 1;
            v38.GuidPtr = (ULONGLONG)&`FtpSecurityEvents::GetAreaGuid'::`2'::AreaGuid;
            v39 = v27;
            v40 = 16;
            v41 = pNodeBuffer;
            v29 = -1;
            do
              ++v29;
            while ( pNodeBuffer[v29] );
            v42 = 2 * v29 + 2;
            v43 = v49;
            v30 = -1;
            do
              ++v30;
            while ( v49[v30] );
            v44 = 2 * v30 + 2;
            CEtwTracer::EtwTraceEvent(v28, &v38);
          }
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_data_channel.cxx",
              1805,
              "FTP_DATA_CHANNEL::OnNewConnectionCompletion",
              "Denied connection because client connected to data channel doesn't match the IP address of the control channel\r\n");
          updated = -2147023660;
          v7 = 38;
          v8 = L"Client IP on the control channel didn't match the client IP on the data channel.";
          goto LABEL_46;
        }
      }
      if ( *((_DWORD *)this + 13) )
      {
        if ( *((_DWORD *)this + 36) )
        {
          DeleteSecurityContext((PCtxtHandle)this + 8);
          *((_DWORD *)this + 36) = 0;
        }
        v31 = (const CERT_CONTEXT *)*((_QWORD *)this + 24);
        if ( v31 )
        {
          CertFreeCertificateContext(v31);
          *((_QWORD *)this + 24) = 0;
        }
        *((_QWORD *)this + 22) = 0;
        *((_QWORD *)this + 23) = 0;
        *((_QWORD *)this + 20) = 0;
        *((_QWORD *)this + 21) = 0;
        *((_DWORD *)this + 31) = 0;
      }
      *(_QWORD *)((char *)this + 100) = 0;
      *(_QWORD *)((char *)this + 92) = 0;
      FTP_DATA_CHANNEL::StartIdealSendBacklogMonitoring(this);
    }
    updated = *((_DWORD *)a2 + 17);
    goto LABEL_57;
  }
  if ( *((int *)a2 + 17) < 0
    || (updated = FTP_ASYNC_SOCKET::UpdateAcceptedConnection((FTP_DATA_CHANNEL *)((char *)this + 544), v5), updated >= 0) )
  {
    FTP_ASYNC_SOCKET::Close(v5);
    goto LABEL_6;
  }
  v7 = 0;
  v8 = &WideCharStr;
LABEL_46:
  if ( *((_WORD *)this + 1198) )
  {
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 144LL))(g_pFtpServer);
    *((_WORD *)this + 1198) = 0;
  }
  FTP_DATA_CHANNEL::InitiateChannelShutdown(this, updated, v7, v8, 0);
LABEL_57:
  v32 = 0;
  CSpinLock::WriteLock((FTP_DATA_CHANNEL *)((char *)this + 2144));
  if ( *((_QWORD *)this + 10) )
  {
    v32 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = 0;
  }
  *((_DWORD *)this + 15) = 0;
  *((_DWORD *)this + 539) = updated;
  v33 = (unsigned int)_InterlockedExchange(
                        (volatile __int32 *)this + 536,
                        ((*((_BYTE *)this + 2144) - 1) & 3) != 0 ? *((_DWORD *)this + 536) - 1 : 0);
  if ( v32 )
  {
    *(_DWORD *)(v32 + 68) = updated;
    *(_QWORD *)(v32 + 72) = 0;
    (*(void (__fastcall **)(__int64, __int64))(v32 + 8))(v32, v33);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
  }
  if ( ReferencedSiteConfig )
  {
    v34 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v34);
    if ( !v34 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
    }
  }
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9), v33);
}

```

## disassembly

```asm
0x180040118  push    rbp
0x18004011a  push    rbx
0x18004011b  push    rsi
0x18004011c  push    rdi
0x18004011d  push    r12
0x18004011f  push    r13
0x180040121  push    r14
0x180040123  push    r15
0x180040125  lea     rbp, [rsp-128h]
0x18004012d  sub     rsp, 238h
0x180040134  mov     rax, cs:__security_cookie
0x18004013b  xor     rax, rsp
0x18004013e  mov     [rbp+160h+var_50], rax
0x180040145  mov     r12, rdx
0x180040148  mov     r15, rcx
0x18004014b  mov     rcx, [rcx+48h]; this
0x18004014f  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x180040154  mov     r13, rax
0x180040157  mov     rcx, r15; this
0x18004015a  call    ?StopConnectionIdleMonitor@FTP_DATA_CHANNEL@@AEAAXXZ; FTP_DATA_CHANNEL::StopConnectionIdleMonitor(void)
0x18004015f  xor     r14d, r14d
0x180040162  mov     [r15+870h], r14
0x180040169  mov     [r15+878h], r14
0x180040170  lea     rdi, [r15+540h]
0x180040177  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004017b  cmp     [rdi+10h], rsi
0x18004017f  jz      short loc_1800401B4
0x180040181  cmp     [r12+44h], r14d
0x180040186  jl      short loc_1800401AC
0x180040188  lea     rcx, [r15+220h]; this
0x18004018f  mov     rdx, rdi; struct FTP_ASYNC_SOCKET *
0x180040192  call    ?UpdateAcceptedConnection@FTP_ASYNC_SOCKET@@QEAAJPEAV1@@Z; FTP_ASYNC_SOCKET::UpdateAcceptedConnection(FTP_ASYNC_SOCKET *)
0x180040197  mov     ebx, eax
0x180040199  test    eax, eax
0x18004019b  jns     short loc_1800401AC
0x18004019d  mov     esi, r14d
0x1800401a0  lea     rdi, WideCharStr
0x1800401a7  jmp     loc_1800406AC
0x1800401ac  mov     rcx, rdi; this
0x1800401af  call    ?Close@FTP_ASYNC_SOCKET@@QEAAXXZ; FTP_ASYNC_SOCKET::Close(void)
0x1800401b4  movzx   edx, word ptr [r15+95Ch]
0x1800401bc  test    dx, dx
0x1800401bf  jz      short loc_1800401DF
0x1800401c1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800401c8  mov     rax, [rcx]
0x1800401cb  mov     rax, [rax+90h]
0x1800401d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401d7  mov     [r15+95Ch], r14w
0x1800401df  cmp     [r12+44h], r14d
0x1800401e4  jl      loc_18004075E
0x1800401ea  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800401f1  mov     rax, [rcx]
0x1800401f4  mov     rax, [rax+20h]
0x1800401f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401fd  mov     edi, 10h
0x180040202  lea     ebx, [rdi-0Eh]
0x180040205  cmp     [rax+8], r14d
0x180040209  jz      loc_1800403AF
0x18004020f  test    byte ptr [rax+28h], 1
0x180040213  jz      loc_1800403AF
0x180040219  cmp     dword ptr [rax+2Ch], 4
0x18004021d  jb      loc_1800403AF
0x180040223  mov     dword ptr [rbp+160h+var_150], 3Fh ; '?'
0x18004022a  xor     edx, edx; Val
0x18004022c  lea     r8d, [rdi+6Ch]; Size
0x180040230  lea     rcx, [rbp+160h+var_150+4]; void *
0x180040234  call    memset_0
0x180040239  mov     dword ptr [rbp+160h+pNodeBuffer], 3Fh ; '?'
0x180040243  xor     edx, edx; Val
0x180040245  lea     r8d, [rdi+6Ch]; Size
0x180040249  lea     rcx, [rbp+160h+var_CC]; void *
0x180040250  call    memset_0
0x180040255  lea     rcx, [r15+360h]; pSockaddr
0x18004025c  mov     edx, edi
0x18004025e  cmp     [rcx], bx
0x180040261  lea     eax, [rdi+0Ch]
0x180040264  cmovnz  edx, eax; SockaddrLength
0x180040267  mov     [rsp+270h+Flags], ebx; Flags
0x18004026b  mov     [rsp+270h+ServiceBufferSize], r14d; ServiceBufferSize
0x180040270  mov     [rsp+270h+pServiceBuffer], r14; pServiceBuffer
0x180040275  lea     r9d, [rdi+30h]; NodeBufferSize
0x180040279  lea     r8, [rbp+160h+pNodeBuffer]; pNodeBuffer
0x180040280  call    cs:__imp_GetNameInfoW
0x180040286  lea     rcx, [r15+3E0h]; pSockaddr
0x18004028d  mov     edx, edi
0x18004028f  cmp     [rcx], bx
0x180040292  lea     eax, [rdi+0Ch]
0x180040295  cmovnz  edx, eax; SockaddrLength
0x180040298  mov     [rsp+270h+Flags], ebx; Flags
0x18004029c  mov     [rsp+270h+ServiceBufferSize], r14d; ServiceBufferSize
0x1800402a1  mov     [rsp+270h+pServiceBuffer], r14; pServiceBuffer
0x1800402a6  lea     r9d, [rdi+30h]; NodeBufferSize
0x1800402aa  lea     r8, [rbp+160h+var_150]; pNodeBuffer
0x1800402ae  call    cs:__imp_GetNameInfoW
0x1800402b4  movzx   ecx, word ptr [r15+362h]; netshort
0x1800402bc  call    cs:__imp_ntohs
0x1800402c2  mov     [rbp+160h+var_1D8], ax
0x1800402c6  movzx   ecx, word ptr [r15+3E2h]; netshort
0x1800402ce  call    cs:__imp_ntohs
0x1800402d4  mov     [rbp+160h+var_1E0], ax
0x1800402d8  mov     rbx, [r15+48h]
0x1800402dc  add     rbx, 170h
0x1800402e3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800402ea  mov     rax, [rcx]
0x1800402ed  mov     rax, [rax+20h]
0x1800402f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402f6  mov     rdi, rax
0x1800402f9  xor     edx, edx; Val
0x1800402fb  lea     r8d, [rdx+7Eh]; Size
0x1800402ff  lea     rcx, [rbp+160h+var_1CE]; void *
0x180040303  call    memset_0
0x180040308  mov     [rbp+160h+var_1A4], 1A0000h
0x18004030f  mov     eax, 80h
0x180040314  mov     [rbp+160h+var_1D0], ax
0x180040318  mov     eax, 1
0x18004031d  mov     [rbp+160h+var_1CA], ax
0x180040321  mov     [rbp+160h+var_1CC], 5
0x180040325  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpConnectionEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpConnectionEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18004032c  mov     [rbp+160h+var_1B8], rax
0x180040330  mov     [rbp+160h+var_1A0], rbx
0x180040334  mov     [rbp+160h+var_198], 10h
0x18004033b  lea     rax, [rbp+160h+var_150]
0x18004033f  mov     [rbp+160h+var_190], rax
0x180040343  lea     rcx, [rbp+160h+var_150]
0x180040347  mov     rax, rsi
0x18004034a  inc     rax
0x18004034d  cmp     [rcx+rax*2], r14w
0x180040352  jnz     short loc_18004034A
0x180040354  lea     eax, ds:2[rax*2]
0x18004035b  mov     [rbp+160h+var_188], eax
0x18004035e  lea     rax, [rbp+160h+var_1E0]
0x180040362  mov     [rbp+160h+var_180], rax
0x180040366  mov     ecx, 2
0x18004036b  mov     [rbp+160h+var_178], ecx
0x18004036e  lea     rax, [rbp+160h+pNodeBuffer]
0x180040375  mov     [rbp+160h+var_170], rax
0x180040379  lea     rdx, [rbp+160h+pNodeBuffer]
0x180040380  mov     rax, rsi
0x180040383  inc     rax
0x180040386  cmp     [rdx+rax*2], r14w
0x18004038b  jnz     short loc_180040383
0x18004038d  lea     eax, ds:2[rax*2]
0x180040394  mov     [rbp+160h+var_168], eax
0x180040397  lea     rax, [rbp+160h+var_1D8]
0x18004039b  mov     [rbp+160h+var_160], rax
0x18004039f  mov     [rbp+160h+var_158], ecx
0x1800403a2  lea     rdx, [rbp+160h+var_1D0]
0x1800403a6  mov     rcx, rdi
0x1800403a9  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x1800403af  mov     r14, [r15+48h]
0x1800403b3  mov     rbx, [r15+870h]
0x1800403ba  mov     rdi, [r15+878h]
0x1800403c1  mov     rsi, [r14+388h]
0x1800403c8  mov     rcx, [r14+420h]
0x1800403cf  mov     rax, [rcx]
0x1800403d2  mov     rax, [rax+30h]
0x1800403d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403db  mov     r9, rax
0x1800403de  mov     r10, [r15+48h]
0x1800403e2  mov     rax, [r10+60h]
0x1800403e6  lea     r8, [r15+360h]
0x1800403ed  lea     rcx, WideCharStr
0x1800403f4  mov     [rsp+270h+var_1E8], rcx
0x1800403fc  xor     ecx, ecx
0x1800403fe  mov     [rsp+270h+var_1F0], ecx
0x180040405  mov     [rsp+270h+var_1F8], ecx
0x180040409  mov     [rsp+270h+var_200], ecx
0x18004040d  lea     rcx, aDatachannelope; "DataChannelOpened"
0x180040414  mov     [rsp+270h+var_220], rcx
0x180040419  mov     [rsp+270h+var_228], rbx
0x18004041e  mov     [rsp+270h+var_230], rdi
0x180040423  mov     [rsp+270h+var_238], rsi
0x180040428  mov     qword ptr [rsp+270h+Flags], r9
0x18004042d  mov     rax, [rax+30h]
0x180040431  mov     qword ptr [rsp+270h+ServiceBufferSize], rax
0x180040436  mov     [rsp+270h+pServiceBuffer], r8
0x18004043b  lea     rbx, [r15+3E0h]
0x180040442  mov     r9, rbx
0x180040445  mov     r8, [r10+130h]
0x18004044c  mov     edx, 5
0x180040451  mov     rcx, r14
0x180040454  call    ?Log@FTP_SESSION@@QEAAJW4_LOG_ENTRY_TYPE@@PEBDPEBUsockaddr@@2PEBG33_K43331KJK3@Z; FTP_SESSION::Log(_LOG_ENTRY_TYPE,char const *,sockaddr const *,sockaddr const *,ushort const *,ushort const *,ushort const *,unsigned __int64,unsigned __int64,ushort const *,ushort const *,ushort const *,char const *,ulong,long,ulong,ushort const *)
0x180040459  xor     r14d, r14d
0x18004045c  cmp     [r13+2C4h], r14d
0x180040463  jz      loc_1800406F2
0x180040469  mov     rax, [r15+48h]
0x18004046d  mov     rcx, [rax+438h]
0x180040474  cmp     word ptr [rcx+1C0h], 17h
0x18004047c  jnz     short loc_1800404AB
0x18004047e  cmp     word ptr [rbx], 17h
0x180040482  jnz     short loc_1800404DC
0x180040484  mov     eax, [rbx+18h]
0x180040487  cmp     [rcx+1D8h], eax
0x18004048d  jnz     short loc_1800404DC
0x18004048f  mov     rax, [rbx+10h]
0x180040493  cmp     [rcx+1D0h], rax
0x18004049a  jnz     short loc_1800404DC
0x18004049c  mov     rax, [rbx+8]
0x1800404a0  cmp     [rcx+1C8h], rax
0x1800404a7  jz      short loc_1800404C0
0x1800404a9  jmp     short loc_1800404DC
0x1800404ab  mov     eax, 2
0x1800404b0  cmp     [rbx], ax
0x1800404b3  jnz     short loc_1800404DC
0x1800404b5  mov     eax, [rbx+4]
0x1800404b8  cmp     [rcx+1C4h], eax
0x1800404be  jnz     short loc_1800404DC
0x1800404c0  movzx   ecx, word ptr [r15+3E2h]; netshort
0x1800404c8  call    cs:__imp_ntohs
0x1800404ce  mov     ecx, 400h
0x1800404d3  cmp     ax, cx
0x1800404d6  jnb     loc_1800406F2
0x1800404dc  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800404e3  mov     rax, [rcx]
0x1800404e6  mov     rax, [rax+20h]
0x1800404ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404ef  cmp     [rax+8], r14d
0x1800404f3  jz      loc_180040665
0x1800404f9  mov     esi, 10h
0x1800404fe  test    [rax+28h], sil
0x180040502  jz      loc_180040665
0x180040508  cmp     dword ptr [rax+2Ch], 3
0x18004050c  jb      loc_180040665
0x180040512  mov     dword ptr [rbp+160h+pNodeBuffer], 3Fh ; '?'
0x18004051c  lea     edi, [rsi+6Ch]
0x18004051f  mov     r8d, edi; Size
0x180040522  xor     edx, edx; Val
0x180040524  lea     rcx, [rbp+160h+var_CC]; void *
0x18004052b  call    memset_0
0x180040530  mov     dword ptr [rbp+160h+var_150], 3Fh ; '?'
0x180040537  mov     r8d, edi; Size
0x18004053a  xor     edx, edx; Val
0x18004053c  lea     rcx, [rbp+160h+var_150+4]; void *
0x180040540  call    memset_0
0x180040545  mov     rax, [r15+48h]
0x180040549  mov     rcx, [rax+438h]
0x180040550  add     rcx, 1C0h; pSockaddr
0x180040557  mov     edx, esi
0x180040559  lea     edi, [rsi-0Eh]
0x18004055c  cmp     [rcx], di
0x18004055f  lea     eax, [rsi+0Ch]
0x180040562  cmovnz  edx, eax; SockaddrLength
0x180040565  mov     [rsp+270h+Flags], edi; Flags
0x180040569  mov     [rsp+270h+ServiceBufferSize], r14d; ServiceBufferSize
0x18004056e  mov     [rsp+270h+pServiceBuffer], r14; pServiceBuffer
0x180040573  lea     r9d, [rsi+30h]; NodeBufferSize
0x180040577  lea     r8, [rbp+160h+pNodeBuffer]; pNodeBuffer
0x18004057e  call    cs:__imp_GetNameInfoW
0x180040584  mov     edx, esi
0x180040586  cmp     [rbx], di
0x180040589  lea     eax, [rsi+0Ch]
0x18004058c  cmovnz  edx, eax; SockaddrLength
0x18004058f  mov     [rsp+270h+Flags], edi; Flags
0x180040593  mov     [rsp+270h+ServiceBufferSize], r14d; ServiceBufferSize
0x180040598  mov     [rsp+270h+pServiceBuffer], r14; pServiceBuffer
0x18004059d  lea     r9d, [rsi+30h]; NodeBufferSize
0x1800405a1  lea     r8, [rbp+160h+var_150]; pNodeBuffer
0x1800405a5  mov     rcx, rbx; pSockaddr
0x1800405a8  call    cs:__imp_GetNameInfoW
0x1800405ae  mov     rbx, [r15+48h]
0x1800405b2  add     rbx, 170h
0x1800405b9  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800405c0  mov     rax, [rcx]
0x1800405c3  mov     rax, [rax+20h]
0x1800405c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405cc  mov     rdi, rax
0x1800405cf  xor     edx, edx; Val
0x1800405d1  lea     r8d, [rsi+4Eh]; Size
0x1800405d5  lea     rcx, [rbp+160h+var_1CE]; void *
0x1800405d9  call    memset_0
0x1800405de  mov     [rbp+160h+var_1A4], 1A0000h
0x1800405e5  lea     eax, [rsi+50h]
0x1800405e8  mov     [rbp+160h+var_1D0], ax
0x1800405ec  lea     eax, [rsi-0Fh]
0x1800405ef  mov     [rbp+160h+var_1CA], ax
0x1800405f3  mov     [rbp+160h+var_1CC], al
0x1800405f6  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpSecurityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpSecurityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800405fd  mov     [rbp+160h+var_1B8], rax
0x180040601  mov     [rbp+160h+var_1A0], rbx
0x180040605  mov     [rbp+160h+var_198], esi
0x180040608  lea     rax, [rbp+160h+pNodeBuffer]
0x18004060f  mov     [rbp+160h+var_190], rax
0x180040613  lea     rdx, [rbp+160h+pNodeBuffer]
0x18004061a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004061e  mov     rax, rcx
0x180040621  inc     rax
0x180040624  cmp     [rdx+rax*2], r14w
0x180040629  jnz     short loc_180040621
0x18004062b  lea     eax, ds:2[rax*2]
0x180040632  mov     [rbp+160h+var_188], eax
0x180040635  lea     rax, [rbp+160h+var_150]
0x180040639  mov     [rbp+160h+var_180], rax
0x18004063d  lea     rdx, [rbp+160h+var_150]
0x180040641  mov     rax, rcx
0x180040644  inc     rax
0x180040647  cmp     [rdx+rax*2], r14w
0x18004064c  jnz     short loc_180040644
0x18004064e  lea     eax, ds:2[rax*2]
0x180040655  mov     [rbp+160h+var_178], eax
0x180040658  lea     rdx, [rbp+160h+var_1D0]
  ... truncated ...
```
