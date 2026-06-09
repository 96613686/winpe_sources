# SSL_STREAM_CONTEXT::DoHandshake(DATA_STREAM_BUFFER *,ulong *,DATA_STREAM_BUFFER *,int *)

- ea: `0x18002dc2c`
- end: `0x18002e676`
- name: `?DoHandshake@SSL_STREAM_CONTEXT@@AEAAJPEAVDATA_STREAM_BUFFER@@PEAK0PEAH@Z`
- size: `2634`
- prototype: `__int64 __fastcall(SSL_STREAM_CONTEXT *this, struct DATA_STREAM_BUFFER *, unsigned int *, struct DATA_STREAM_BUFFER *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002f860`

## callees

- `0x18002dc2c`
- `0x18002e67c`
- `0x18002ff14`
- `0x18002ffe8`
- `0x1800300bc`
- `0x1800301cc`
- `0x180046feb`
- `0x180047003`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `Secur32!AcceptSecurityContext` at `0x18002e017`
- `Secur32!AcceptSecurityContext` at `0x18002e183`
- `Secur32!AcceptSecurityContext` at `0x18002e017`
- `Secur32!AcceptSecurityContext` at `0x18002e183`
- `Secur32!FreeContextBuffer` at `0x18002e3d4`
- `Secur32!FreeContextBuffer` at `0x18002e3d4`
- `iisutil!PuDbgPrint` at `0x18002dd35`
- `iisutil!PuDbgPrint` at `0x18002dd9d`
- `iisutil!PuDbgPrint` at `0x18002e087`
- `iisutil!PuDbgPrint` at `0x18002e1f6`
- `iisutil!PuDbgPrint` at `0x18002e2ac`
- `iisutil!PuDbgPrint` at `0x18002e4c5`
- `iisutil!PuDbgPrint` at `0x18002e5b9`
- `iisutil!PuDbgPrint` at `0x18002dd35`
- `iisutil!PuDbgPrint` at `0x18002dd9d`
- `iisutil!PuDbgPrint` at `0x18002e087`
- `iisutil!PuDbgPrint` at `0x18002e1f6`
- `iisutil!PuDbgPrint` at `0x18002e2ac`
- `iisutil!PuDbgPrint` at `0x18002e4c5`
- `iisutil!PuDbgPrint` at `0x18002e5b9`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002df2c`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002e375`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002df2c`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002e375`

## string_xrefs

- `0x18002e063`: `AcceptSecurityContext() secStatus=0x%x\n`
- `0x18002e1d2`: `AcceptSecurityContext() secStatus=0x%x\n`
- `0x18002e0cf`: `AcceptSecurityContext`
- `0x18002e23e`: `AcceptSecurityContext`
- `0x18002e28c`: `AcceptSecurityContext() returns context different from the one on input\n`
- `0x18002e4b9`: `AcceptSecurityContext returned extra buffer - %d bytes buffer type: %d\n`
- `0x18002e595`: `AcceptSecurityContext() failed with secStatus=0x%x\n`

## pseudocode

```c
__int64 __fastcall SSL_STREAM_CONTEXT::DoHandshake(
        SSL_STREAM_CONTEXT *this,
        struct DATA_STREAM_BUFFER *a2,
        unsigned int *a3,
        struct DATA_STREAM_BUFFER *a4,
        int *a5)
{
  struct DATA_STREAM_BUFFER *v8; // rsi
  __int64 v9; // rdx
  bool v10; // zf
  unsigned int v11; // ecx
  unsigned int v12; // r12d
  __int64 v13; // rax
  struct CEtwTracer *v14; // rax
  const char *v15; // r9
  unsigned int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  CEtwTracer *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int16 v24; // r14
  int v25; // ebx
  const char *v26; // rdi
  const char *v27; // rsi
  struct CEtwTracer *v28; // rax
  SECURITY_STATUS v29; // edi
  __int64 v30; // rax
  struct CEtwTracer *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  struct CEtwTracer *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  CEtwTracer *v37; // rbx
  __int64 v38; // rax
  struct CEtwTracer *v39; // rax
  const char *v40; // r9
  PVOID v41; // rbx
  int v42; // edi
  void (__fastcall *v43)(_QWORD, _QWORD); // rax
  char v44; // cl
  __int64 i; // rbx
  int v46; // edx
  __int64 v47; // rax
  struct CEtwTracer *v48; // rax
  const char *v49; // r9
  PVOID v50; // rbx
  int v51; // esi
  void (__fastcall *v52)(_QWORD, _QWORD); // rax
  const char *TargetDataRep; // [rsp+20h] [rbp-E0h]
  unsigned int pfContextAttr; // [rsp+50h] [rbp-B0h] BYREF
  int v55; // [rsp+58h] [rbp-A8h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v57; // [rsp+68h] [rbp-98h]
  struct _SecBufferDesc pOutput; // [rsp+70h] [rbp-90h] BYREF
  struct _SecBufferDesc pInput; // [rsp+80h] [rbp-80h] BYREF
  struct DATA_STREAM_BUFFER *v60; // [rsp+90h] [rbp-70h]
  int *v61; // [rsp+98h] [rbp-68h]
  struct _SecHandle Buf2; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_TRACE_HEADER v63; // [rsp+B0h] [rbp-50h] BYREF
  char *v64; // [rsp+E0h] [rbp-20h]
  int v65; // [rsp+E8h] [rbp-18h]
  int *v66; // [rsp+F0h] [rbp-10h]
  int v67; // [rsp+F8h] [rbp-8h]
  const char *v68; // [rsp+100h] [rbp+0h]
  int v69; // [rsp+108h] [rbp+8h]
  const char *v70; // [rsp+110h] [rbp+10h]
  int v71; // [rsp+118h] [rbp+18h]
  _DWORD v72[2]; // [rsp+120h] [rbp+20h] BYREF
  PVOID pvContextBuffer; // [rsp+128h] [rbp+28h]
  unsigned int v74; // [rsp+160h] [rbp+60h] BYREF
  int v75; // [rsp+164h] [rbp+64h]
  __int64 v76; // [rsp+168h] [rbp+68h]
  unsigned int Size; // [rsp+170h] [rbp+70h]
  int Size_4; // [rsp+174h] [rbp+74h]
  int v79; // [rsp+184h] [rbp+84h]
  int v80; // [rsp+194h] [rbp+94h]

  v60 = a4;
  v57 = a3;
  v61 = a5;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  v8 = a4;
  Buf2 = 0;
  pInput = 0;
  pOutput = 0;
  memset_0(&v74, 0, 0x40u);
  memset_0(v72, 0, 0x40u);
  if ( !a2 || !a3 || !v8 || !a5 )
  {
    v29 = -2147024809;
    goto LABEL_58;
  }
  v9 = (unsigned int)g_dwDebugFlags;
  v10 = (g_dwDebugFlags & 3) == 0;
  *a3 = 0;
  *a5 = 0;
  if ( !v10 && (v9 & 0x10000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ssl\\ssl_stream_context.cxx",
      805,
      "SSL_STREAM_CONTEXT::DoHandshake",
      "DoHandshake(): _cbDecrypted = %d, _cbToBeProcessedOffset=%d\n",
      *((_DWORD *)this + 17),
      *((_DWORD *)this + 16));
    v9 = (unsigned int)g_dwDebugFlags;
  }
  v11 = *((_DWORD *)a2 + 8);
  v12 = *((_DWORD *)this + 25) != 0 ? 98588 : 16875804;
  if ( v11 < *((_DWORD *)this + 16) )
  {
    if ( (v9 & 3) != 0 && (v9 & 8) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ssl\\ssl_stream_context.cxx",
        835,
        "SSL_STREAM_CONTEXT::DoHandshake",
        "Error: FTPSVC detected unexpected offset in it's internal data (connection will be closed)\n");
    v13 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v13 + 8) && (*(_BYTE *)(v13 + 40) & 0x14) != 0 && *(_DWORD *)(v13 + 44) >= 2u )
    {
      v14 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpSslInfoEvents::SslError_InternalInconsistency::RaiseEvent(
        v14,
        (const struct _GUID *)((char *)this + 156),
        0x8007000D,
        v15,
        TargetDataRep);
    }
    return 2147942413LL;
  }
  pInput.ulVersion = 0;
  pInput.pBuffers = (PSecBuffer)&v74;
  v17 = v11 - *((_DWORD *)this + 16);
  v76 = *((_QWORD *)a2 + 3) + *((unsigned int *)this + 16);
  v74 = v17;
  v18 = 0;
  pOutput.pBuffers = (PSecBuffer)v72;
  pInput.cBuffers = 4;
  v75 = 2;
  Size_4 = 0;
  v79 = 0;
  v80 = 0;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 4;
  do
  {
    v19 = v18++;
    v72[4 * v19 + 1] = 0;
  }
  while ( v18 != 4 );
  if ( *((_DWORD *)this + 24) )
    v12 |= 2u;
  if ( !*((_DWORD *)this + 3) )
  {
    v20 = (*(__int64 (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer, v9);
    if ( *(_DWORD *)(v20 + 8) && (*(_BYTE *)(v20 + 40) & 0x14) != 0 && *(_DWORD *)(v20 + 44) >= 4u )
    {
      v21 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      v55 = (v12 >> 1) & 1;
      memset_0(&v63.FieldTypeFlags, 0, 0x4Eu);
      v63.UserTime = 1703936;
      v63.Size = 80;
      v63.Class.Version = 1;
      v63.GuidPtr = (ULONGLONG)&`FtpSslInfoEvents::GetAreaGuid'::`2'::AreaGuid;
      v63.Class.Type = 1;
      v64 = (char *)this + 156;
      v66 = &v55;
      v65 = 16;
      v67 = 4;
      CEtwTracer::EtwTraceEvent(v21, &v63);
    }
    v22 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v22 + 8) && (*(_BYTE *)(v22 + 40) & 0x14) != 0 && *(_DWORD *)(v22 + 44) >= 5u )
    {
      v23 = *((_QWORD *)this + 11);
      v24 = *(_WORD *)(v23 + 40);
      v25 = *(_DWORD *)(v23 + 160);
      v26 = *(const char **)(v23 + 80);
      v27 = *(const char **)(v23 + 136);
      v28 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpSslInfoEvents::SslHandshakeInfo::RaiseEvent(
        v28,
        (const struct _GUID *)((char *)this + 156),
        v27,
        v26,
        v24,
        v25);
      v8 = v60;
    }
    if ( *(_DWORD *)(*((_QWORD *)this + 11) + 160LL) )
      _InterlockedAdd(
        (volatile signed __int32 *)(*(_QWORD *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 48LL))(g_pFtpServer)
                                  + 56LL),
        1u);
    v29 = AcceptSecurityContext(
            (PCredHandle)(*((_QWORD *)this + 11) + 168LL),
            0,
            &pInput,
            v12,
            0x10u,
            (PCtxtHandle)this + 1,
            &pOutput,
            &pfContextAttr,
            &ptsExpiry);
    if ( *(_DWORD *)(*((_QWORD *)this + 11) + 160LL) )
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 48LL))(g_pFtpServer)
                                                      + 56LL));
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ssl\\ssl_stream_context.cxx",
        947,
        "SSL_STREAM_CONTEXT::DoHandshake",
        "AcceptSecurityContext() secStatus=0x%x\n",
        v29);
    v30 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v30 + 8) && (*(_BYTE *)(v30 + 40) & 0x20) != 0 && *(_DWORD *)(v30 + 44) >= 5u )
    {
      v31 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpSslSchannelCallsEvents::SslSchannelCall::RaiseEvent(
        v31,
        (const struct _GUID *)((char *)this + 156),
        "AcceptSecurityContext",
        v29);
    }
    if ( v29 >= 0 )
    {
      *((_QWORD *)this + 6) = 0;
      *((_DWORD *)this + 8) = 1;
      *((_DWORD *)this + 3) = 1;
      *((_QWORD *)this + 7) = 0;
      goto LABEL_65;
    }
LABEL_84:
    if ( (pfContextAttr & 0x8000) == 0 )
    {
      pvContextBuffer = 0;
      v72[0] = 0;
    }
    if ( v29 == -2146893032 )
    {
      *v57 = 1000;
      goto LABEL_80;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ssl\\ssl_stream_context.cxx",
        1236,
        "SSL_STREAM_CONTEXT::DoHandshake",
        "AcceptSecurityContext() failed with secStatus=0x%x\n",
        v29);
    v47 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v47 + 8) && (*(_BYTE *)(v47 + 40) & 0x14) != 0 && *(_DWORD *)(v47 + 44) >= 2u )
    {
      v48 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpSslInfoEvents::SslError_Handshake::RaiseEvent(
        v48,
        (const struct _GUID *)((char *)this + 156),
        0x80004005,
        v49,
        TargetDataRep);
    }
    if ( (pfContextAttr & 0x8000) != 0 )
    {
      v50 = pvContextBuffer;
      if ( pvContextBuffer )
      {
        v51 = v72[0];
        if ( v72[0] )
        {
          v52 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)a2 + 5);
          if ( v52 )
            v52(*((_QWORD *)a2 + 1), *((unsigned int *)a2 + 9));
          *((_QWORD *)a2 + 1) = v50;
          *((_QWORD *)a2 + 5) = SSL_STREAM_CONTEXT::FreeSecurityContextBuffer;
          *((_DWORD *)a2 + 4) = 0;
          *((_QWORD *)a2 + 3) = v50;
          *((_DWORD *)a2 + 8) = v51;
          *((_DWORD *)a2 + 9) = v51;
          pvContextBuffer = 0;
          v72[0] = 0;
        }
      }
    }
LABEL_58:
    v38 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v38 + 8) && (*(_BYTE *)(v38 + 40) & 0x14) != 0 && *(_DWORD *)(v38 + 44) >= 2u )
    {
      v39 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      FtpSslInfoEvents::SslError_Handshake::RaiseEvent(
        v39,
        (const struct _GUID *)((char *)this + 156),
        v29,
        v40,
        TargetDataRep);
    }
    goto LABEL_62;
  }
  v32 = *((_QWORD *)this + 11);
  Buf2 = (struct _SecHandle)*((_OWORD *)this + 1);
  if ( *(_DWORD *)(v32 + 160) )
    _InterlockedAdd(
      (volatile signed __int32 *)(*(_QWORD *)(*(__int64 (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer
                                                                                               + 48LL))(
                                               g_pFtpServer,
                                               v9)
                                + 56LL),
      1u);
  v29 = AcceptSecurityContext(
          (PCredHandle)(*((_QWORD *)this + 11) + 168LL),
          (PCtxtHandle)this + 1,
          &pInput,
          v12,
          0x10u,
          &Buf2,
          &pOutput,
          &pfContextAttr,
          &ptsExpiry);
  if ( *(_DWORD *)(*((_QWORD *)this + 11) + 160LL) )
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 48LL))(g_pFtpServer)
                                                    + 56LL));
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ssl\\ssl_stream_context.cxx",
      1000,
      "SSL_STREAM_CONTEXT::DoHandshake",
      "AcceptSecurityContext() secStatus=0x%x\n",
      v29);
  v33 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v33 + 8) && (*(_BYTE *)(v33 + 40) & 0x20) != 0 && *(_DWORD *)(v33 + 44) >= 5u )
  {
    v34 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    FtpSslSchannelCallsEvents::SslSchannelCall::RaiseEvent(
      v34,
      (const struct _GUID *)((char *)this + 156),
      "AcceptSecurityContext",
      v29);
  }
  if ( v29 < 0 )
    goto LABEL_84;
  if ( memcmp_0((char *)this + 16, &Buf2, 0x10u) )
  {
    v29 = -2147024883;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ssl\\ssl_stream_context.cxx",
        1031,
        "SSL_STREAM_CONTEXT::DoHandshake",
        "AcceptSecurityContext() returns context different from the one on input\n");
    v35 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v35 + 8) && (*(_BYTE *)(v35 + 40) & 0x14) != 0 && *(_DWORD *)(v35 + 44) >= 2u )
    {
      v36 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      v55 = -2147024883;
      v37 = (CEtwTracer *)v36;
      memset_0(&v63.FieldTypeFlags, 0, 0x6Eu);
      v63.UserTime = 1703936;
      v63.Size = 112;
      v63.Class.Type = 105;
      v65 = 16;
      v67 = 4;
      v63.Class.Version = 1;
      v63.GuidPtr = (ULONGLONG)&`FtpSslInfoEvents::GetAreaGuid'::`2'::AreaGuid;
      v64 = (char *)this + 156;
      v66 = &v55;
      v68 = String;
      v70 = String;
      v69 = 1;
      v71 = 1;
      CEtwTracer::EtwTraceEvent(v37, &v63);
    }
    goto LABEL_58;
  }
LABEL_65:
  if ( !v29 )
  {
    v29 = SSL_STREAM_CONTEXT::DoHandshakeCompleted(this);
    if ( v29 < 0 )
      goto LABEL_58;
  }
  v41 = pvContextBuffer;
  if ( pvContextBuffer )
  {
    v42 = v72[0];
    if ( v72[0] )
    {
      v43 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)v8 + 5);
      if ( v43 )
        v43(*((_QWORD *)v8 + 1), *((unsigned int *)v8 + 9));
      *((_QWORD *)v8 + 1) = v41;
      *((_QWORD *)v8 + 5) = SSL_STREAM_CONTEXT::FreeSecurityContextBuffer;
      *((_DWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 3) = v41;
      *((_DWORD *)v8 + 8) = v42;
      *((_DWORD *)v8 + 9) = v42;
      pvContextBuffer = 0;
      v72[0] = 0;
    }
  }
  if ( Size_4 != 5 )
  {
    v29 = 0;
    *((_DWORD *)a2 + 8) = *((_DWORD *)this + 17);
    v10 = *((_DWORD *)this + 3) == 2;
    *((_DWORD *)this + 16) = *((_DWORD *)this + 17);
    if ( v10 )
      *((_QWORD *)this + 8) = 0;
    else
      *v57 = 1000;
    goto LABEL_62;
  }
  v44 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 0x10000) != 0 )
  {
    for ( i = 1; i != 4; ++i )
    {
      v46 = *(&v75 + 4 * i);
      if ( v46 && (v44 & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ssl\\ssl_stream_context.cxx",
          1116,
          "SSL_STREAM_CONTEXT::DoHandshake",
          "AcceptSecurityContext returned extra buffer - %d bytes buffer type: %d\n",
          *(&v74 + 4 * i),
          v46);
        v44 = g_dwDebugFlags;
      }
    }
  }
  memmove_0(
    (void *)(*((_QWORD *)a2 + 3) + *((unsigned int *)this + 17)),
    (const void *)(*((_QWORD *)a2 + 3) + *((unsigned int *)a2 + 8) - (unsigned __int64)Size),
    Size);
  *((_DWORD *)a2 + 8) = Size + *((_DWORD *)this + 17);
  *((_DWORD *)this + 16) = *((_DWORD *)this + 17);
  *v61 = 1;
LABEL_80:
  v29 = 0;
LABEL_62:
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x18002dc2c  push    rbp
0x18002dc2e  push    rbx
0x18002dc2f  push    rsi
0x18002dc30  push    rdi
0x18002dc31  push    r12
0x18002dc33  push    r13
0x18002dc35  push    r14
0x18002dc37  push    r15
0x18002dc39  lea     rbp, [rsp-0B8h]
0x18002dc41  sub     rsp, 1B8h
0x18002dc48  mov     rax, cs:__security_cookie
0x18002dc4f  xor     rax, rsp
0x18002dc52  mov     [rbp+0F0h+var_50], rax
0x18002dc59  mov     rdi, [rbp+0F0h+arg_20]
0x18002dc60  xor     r12d, r12d
0x18002dc63  mov     rbx, r8
0x18002dc66  mov     [rbp+0F0h+var_160], r9
0x18002dc6a  xorps   xmm0, xmm0
0x18002dc6d  mov     [rsp+1F0h+var_188], rbx
0x18002dc72  mov     r13, rdx
0x18002dc75  mov     [rbp+0F0h+var_158], rdi
0x18002dc79  mov     r15, rcx
0x18002dc7c  mov     [rsp+1F0h+var_1A0], r12d
0x18002dc81  xorps   xmm1, xmm1
0x18002dc84  mov     qword ptr [rsp+1F0h+var_190], r12
0x18002dc89  lea     r14d, [r12+40h]
0x18002dc8e  xor     edx, edx; Val
0x18002dc90  mov     r8d, r14d; Size
0x18002dc93  lea     rcx, [rbp+0F0h+var_90]; void *
0x18002dc97  mov     rsi, r9
0x18002dc9a  movups  xmmword ptr [rbp+0F0h+Buf2.dwLower], xmm0
0x18002dc9e  movups  xmmword ptr [rbp+0F0h+pInput.ulVersion], xmm1
0x18002dca2  movups  xmmword ptr [rsp+1F0h+var_180.ulVersion], xmm0
0x18002dca7  call    memset_0
0x18002dcac  mov     r8d, r14d; Size
0x18002dcaf  lea     rcx, [rbp+0F0h+var_D0]; void *
0x18002dcb3  xor     edx, edx; Val
0x18002dcb5  call    memset_0
0x18002dcba  xor     r14d, r14d
0x18002dcbd  test    r13, r13
0x18002dcc0  jz      loc_18002E66C
0x18002dcc6  test    rbx, rbx
0x18002dcc9  jz      loc_18002E66C
0x18002dccf  test    rsi, rsi
0x18002dcd2  jz      loc_18002E66C
0x18002dcd8  test    rdi, rdi
0x18002dcdb  jz      loc_18002E66C
0x18002dce1  mov     edx, cs:g_dwDebugFlags
0x18002dce7  test    dl, 3
0x18002dcea  mov     [rbx], r14d
0x18002dced  setnz   cl
0x18002dcf0  mov     [rdi], r14d
0x18002dcf3  bt      edx, 10h
0x18002dcf7  setb    al
0x18002dcfa  test    al, cl
0x18002dcfc  jz      short loc_18002DD41
0x18002dcfe  mov     eax, [r15+40h]
0x18002dd02  lea     r9, aSslStreamConte_5; "SSL_STREAM_CONTEXT::DoHandshake"
0x18002dd09  mov     rcx, cs:g_pDebug
0x18002dd10  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18002dd17  mov     dword ptr [rsp+1F0h+pOutput], eax
0x18002dd1b  mov     r8d, 325h
0x18002dd21  mov     eax, [r15+44h]
0x18002dd25  mov     dword ptr [rsp+1F0h+phNewContext], eax
0x18002dd29  lea     rax, aDohandshakeCbd; "DoHandshake(): _cbDecrypted = %d, _cbTo"...
0x18002dd30  mov     qword ptr [rsp+1F0h+TargetDataRep], rax
0x18002dd35  call    cs:__imp_PuDbgPrint
0x18002dd3b  mov     edx, cs:g_dwDebugFlags
0x18002dd41  mov     eax, [r15+64h]
0x18002dd45  mov     ecx, [r13+20h]
0x18002dd49  neg     eax
0x18002dd4b  sbb     r12d, r12d
0x18002dd4e  and     r12d, 0FF000000h
0x18002dd55  add     r12d, 101811Ch
0x18002dd5c  cmp     ecx, [r15+40h]
0x18002dd60  jnb     loc_18002DDFA
0x18002dd66  test    dl, 3
0x18002dd69  setnz   cl
0x18002dd6c  test    dl, 8
0x18002dd6f  setnz   al
0x18002dd72  test    al, cl
0x18002dd74  jz      short loc_18002DDA3
0x18002dd76  mov     rcx, cs:g_pDebug
0x18002dd7d  lea     rax, aErrorFtpsvcDet; "Error: FTPSVC detected unexpected offse"...
0x18002dd84  lea     r9, aSslStreamConte_5; "SSL_STREAM_CONTEXT::DoHandshake"
0x18002dd8b  mov     qword ptr [rsp+1F0h+TargetDataRep], rax; char *
0x18002dd90  mov     r8d, 343h
0x18002dd96  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18002dd9d  call    cs:__imp_PuDbgPrint
0x18002dda3  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002ddaa  mov     rax, [rcx]
0x18002ddad  mov     rax, [rax+20h]
0x18002ddb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddb6  cmp     [rax+8], r14d
0x18002ddba  jz      short loc_18002DDF0
0x18002ddbc  test    byte ptr [rax+28h], 14h
0x18002ddc0  jz      short loc_18002DDF0
0x18002ddc2  cmp     dword ptr [rax+2Ch], 2
0x18002ddc6  jb      short loc_18002DDF0
0x18002ddc8  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002ddcf  mov     rax, [rcx]
0x18002ddd2  mov     rax, [rax+20h]
0x18002ddd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dddb  lea     rdx, [r15+9Ch]; struct _GUID *
0x18002dde2  mov     r8d, 8007000Dh; unsigned int
0x18002dde8  mov     rcx, rax; struct CEtwTracer *
0x18002ddeb  call    ?RaiseEvent@SslError_InternalInconsistency@FtpSslInfoEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@KPEBD2@Z; FtpSslInfoEvents::SslError_InternalInconsistency::RaiseEvent(CEtwTracer *,_GUID const *,ulong,char const *,char const *)
0x18002ddf0  mov     eax, 8007000Dh
0x18002ddf5  jmp     loc_18002E3DC
0x18002ddfa  lea     rax, [rbp+0F0h+var_90]
0x18002ddfe  mov     [rbp+0F0h+pInput.ulVersion], r14d
0x18002de02  mov     [rbp+0F0h+pInput.pBuffers], rax
0x18002de06  mov     edi, 1
0x18002de0b  mov     eax, [r15+40h]
0x18002de0f  add     rax, [r13+18h]
0x18002de13  sub     ecx, [r15+40h]
0x18002de17  mov     [rbp+0F0h+var_88], rax
0x18002de1b  lea     rax, [rbp+0F0h+var_D0]
0x18002de1f  mov     [rbp+0F0h+var_90], ecx
0x18002de22  mov     rcx, r14
0x18002de25  mov     [rsp+1F0h+var_180.pBuffers], rax
0x18002de2a  mov     [rbp+0F0h+pInput.cBuffers], 4
0x18002de31  mov     [rbp+0F0h+var_8C], 2
0x18002de38  mov     [rbp+0F0h+Size+4], r14d
0x18002de3c  mov     [rbp+0F0h+var_6C], r14d
0x18002de43  mov     [rbp+0F0h+var_5C], r14d
0x18002de4a  mov     [rsp+1F0h+var_180.ulVersion], r14d
0x18002de4f  mov     [rsp+1F0h+var_180.cBuffers], 4
0x18002de57  mov     rax, rcx
0x18002de5a  add     rcx, rdi
0x18002de5d  add     rax, rax
0x18002de60  mov     [rbp+rax*8+0F0h+var_CC], r14d
0x18002de65  cmp     rcx, 4
0x18002de69  jnz     short loc_18002DE57
0x18002de6b  cmp     [r15+60h], r14d
0x18002de6f  jz      short loc_18002DE75
0x18002de71  or      r12d, 2
0x18002de75  cmp     [r15+0Ch], r14d
0x18002de79  jnz     loc_18002E109
0x18002de7f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002de86  mov     rax, [rcx]
0x18002de89  mov     rax, [rax+20h]
0x18002de8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de92  cmp     [rax+8], r14d
0x18002de96  jz      loc_18002DF32
0x18002de9c  test    byte ptr [rax+28h], 14h
0x18002dea0  jz      loc_18002DF32
0x18002dea6  cmp     dword ptr [rax+2Ch], 4
0x18002deaa  jb      loc_18002DF32
0x18002deb0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002deb7  mov     rax, [rcx]
0x18002deba  mov     rax, [rax+20h]
0x18002debe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dec3  mov     ecx, r12d
0x18002dec6  xor     edx, edx; Val
0x18002dec8  shr     ecx, 1
0x18002deca  mov     rbx, rax
0x18002decd  and     ecx, edi
0x18002decf  mov     [rsp+1F0h+var_198], ecx
0x18002ded3  lea     rcx, [rbp+0F0h+var_13E]; void *
0x18002ded7  lea     r8d, [rdx+4Eh]; Size
0x18002dedb  call    memset_0
0x18002dee0  mov     eax, 50h ; 'P'
0x18002dee5  mov     [rbp+0F0h+var_114], 1A0000h
0x18002deec  mov     [rbp+0F0h+var_140], ax
0x18002def0  lea     rdx, [rbp+0F0h+var_140]
0x18002def4  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpSslInfoEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpSslInfoEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18002defb  mov     [rbp+0F0h+var_13A], di
0x18002deff  mov     [rbp+0F0h+var_128], rax
0x18002df03  mov     rcx, rbx
0x18002df06  lea     rax, [r15+9Ch]
0x18002df0d  mov     [rbp+0F0h+var_13C], dil
0x18002df11  mov     [rbp+0F0h+var_110], rax
0x18002df15  lea     rax, [rsp+1F0h+var_198]
0x18002df1a  mov     [rbp+0F0h+var_100], rax
0x18002df1e  mov     [rbp+0F0h+var_108], 10h
0x18002df25  mov     [rbp+0F0h+var_F8], 4
0x18002df2c  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18002df32  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002df39  mov     rax, [rcx]
0x18002df3c  mov     rax, [rax+20h]
0x18002df40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df45  cmp     [rax+8], r14d
0x18002df49  jz      short loc_18002DFAD
0x18002df4b  test    byte ptr [rax+28h], 14h
0x18002df4f  jz      short loc_18002DFAD
0x18002df51  cmp     dword ptr [rax+2Ch], 5
0x18002df55  jb      short loc_18002DFAD
0x18002df57  mov     rax, [r15+58h]
0x18002df5b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002df62  movzx   r14d, word ptr [rax+28h]
0x18002df67  mov     ebx, [rax+0A0h]
0x18002df6d  mov     rdi, [rax+50h]
0x18002df71  mov     rsi, [rax+88h]
0x18002df78  mov     rax, [rcx]
0x18002df7b  mov     rax, [rax+20h]
0x18002df7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df84  lea     rdx, [r15+9Ch]; struct _GUID *
0x18002df8b  mov     dword ptr [rsp+1F0h+phNewContext], ebx; char
0x18002df8f  mov     r9, rdi; char *
0x18002df92  mov     [rsp+1F0h+TargetDataRep], r14d; char
0x18002df97  mov     r8, rsi; char *
0x18002df9a  mov     rcx, rax; struct CEtwTracer *
0x18002df9d  call    ?RaiseEvent@SslHandshakeInfo@FtpSslInfoEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBD2KH@Z; FtpSslInfoEvents::SslHandshakeInfo::RaiseEvent(CEtwTracer *,_GUID const *,char const *,char const *,ulong,int)
0x18002dfa2  mov     rsi, [rbp+0F0h+var_160]
0x18002dfa6  xor     r14d, r14d
0x18002dfa9  lea     edi, [r14+1]
0x18002dfad  mov     rax, [r15+58h]
0x18002dfb1  cmp     [rax+0A0h], r14d
0x18002dfb8  jz      short loc_18002DFD4
0x18002dfba  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002dfc1  mov     rax, [rcx]
0x18002dfc4  mov     rax, [rax+30h]
0x18002dfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfcd  mov     rcx, [rax]
0x18002dfd0  lock add [rcx+38h], edi
0x18002dfd4  mov     rcx, [r15+58h]
0x18002dfd8  lea     rdx, [rsp+1F0h+var_190]
0x18002dfdd  mov     [rsp+1F0h+ptsExpiry], rdx; ptsExpiry
0x18002dfe2  lea     rax, [r15+10h]
0x18002dfe6  lea     rdx, [rsp+1F0h+var_1A0]
0x18002dfeb  add     rcx, 0A8h; phCredential
0x18002dff2  mov     [rsp+1F0h+pfContextAttr], rdx; pfContextAttr
0x18002dff7  lea     r8, [rbp+0F0h+pInput]; pInput
0x18002dffb  lea     rdx, [rsp+1F0h+var_180]
0x18002e000  mov     r9d, r12d; fContextReq
0x18002e003  mov     [rsp+1F0h+pOutput], rdx; pOutput
0x18002e008  xor     edx, edx; phContext
0x18002e00a  mov     [rsp+1F0h+phNewContext], rax; phNewContext
0x18002e00f  mov     [rsp+1F0h+TargetDataRep], 10h; TargetDataRep
0x18002e017  call    cs:__imp_AcceptSecurityContext
0x18002e01d  mov     edi, eax
0x18002e01f  mov     rax, [r15+58h]
0x18002e023  cmp     [rax+0A0h], r14d
0x18002e02a  jz      short loc_18002E046
0x18002e02c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002e033  mov     rax, [rcx]
0x18002e036  mov     rax, [rax+30h]
0x18002e03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e03f  mov     rcx, [rax]
0x18002e042  lock dec dword ptr [rcx+38h]
0x18002e046  mov     eax, cs:g_dwDebugFlags
0x18002e04c  test    al, 3
0x18002e04e  setnz   cl
0x18002e051  bt      eax, 10h
0x18002e055  setb    al
0x18002e058  test    al, cl
0x18002e05a  jz      short loc_18002E08D
0x18002e05c  mov     rcx, cs:g_pDebug
0x18002e063  lea     rax, aAcceptsecurity; "AcceptSecurityContext() secStatus=0x%x"...
0x18002e06a  mov     dword ptr [rsp+1F0h+phNewContext], edi
0x18002e06e  lea     r9, aSslStreamConte_5; "SSL_STREAM_CONTEXT::DoHandshake"
0x18002e075  mov     r8d, 3B3h
0x18002e07b  mov     qword ptr [rsp+1F0h+TargetDataRep], rax
0x18002e080  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18002e087  call    cs:__imp_PuDbgPrint
0x18002e08d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002e094  mov     rax, [rcx]
0x18002e097  mov     rax, [rax+20h]
0x18002e09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0a0  cmp     [rax+8], r14d
0x18002e0a4  jz      short loc_18002E0DE
0x18002e0a6  test    byte ptr [rax+28h], 20h
0x18002e0aa  jz      short loc_18002E0DE
0x18002e0ac  cmp     dword ptr [rax+2Ch], 5
0x18002e0b0  jb      short loc_18002E0DE
0x18002e0b2  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002e0b9  mov     rax, [rcx]
0x18002e0bc  mov     rax, [rax+20h]
0x18002e0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0c5  lea     rdx, [r15+9Ch]; struct _GUID *
0x18002e0cc  mov     r9d, edi; unsigned int
0x18002e0cf  lea     r8, aAcceptsecurity_0; "AcceptSecurityContext"
0x18002e0d6  mov     rcx, rax; struct CEtwTracer *
0x18002e0d9  call    ?RaiseEvent@SslSchannelCall@FtpSslSchannelCallsEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBDK@Z; FtpSslSchannelCallsEvents::SslSchannelCall::RaiseEvent(CEtwTracer *,_GUID const *,char const *,ulong)
0x18002e0de  test    edi, edi
0x18002e0e0  js      loc_18002E552
0x18002e0e6  mov     r12d, 1
0x18002e0ec  mov     qword ptr [r15+30h], 0
0x18002e0f4  mov     [r15+20h], r12d
0x18002e0f8  mov     [r15+0Ch], r12d
0x18002e0fc  mov     qword ptr [r15+38h], 0
0x18002e104  jmp     loc_18002E406
0x18002e109  mov     rax, [r15+58h]
0x18002e10d  lea     rbx, [r15+10h]
0x18002e111  movups  xmm0, xmmword ptr [rbx]
0x18002e114  movdqu  xmmword ptr [rbp+0F0h+Buf2.dwLower], xmm0
0x18002e119  cmp     [rax+0A0h], r14d
0x18002e120  jz      short loc_18002E13C
0x18002e122  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18002e129  mov     rax, [rcx]
0x18002e12c  mov     rax, [rax+30h]
0x18002e130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e135  mov     rcx, [rax]
0x18002e138  lock add [rcx+38h], edi
0x18002e13c  mov     rcx, [r15+58h]
0x18002e140  lea     rax, [rsp+1F0h+var_190]
0x18002e145  mov     [rsp+1F0h+ptsExpiry], rax; ptsExpiry
0x18002e14a  lea     r8, [rbp+0F0h+pInput]; pInput
0x18002e14e  lea     rax, [rsp+1F0h+var_1A0]
  ... truncated ...
```
