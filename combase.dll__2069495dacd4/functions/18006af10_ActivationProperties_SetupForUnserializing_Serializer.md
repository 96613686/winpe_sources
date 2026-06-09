# ActivationProperties::SetupForUnserializing(Serializer *)

- ea: `0x18006af10`
- end: `0x18006b779`
- name: `?SetupForUnserializing@ActivationProperties@@QEAAJPEAVSerializer@@@Z`
- size: `2153`
- prototype: `__int64 __fastcall(ActivationProperties *this, Serializer *pSer)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006a590`
- `0x18006ba90`

## callees

- `0x18000fb24`
- `0x18003a8bc`
- `0x18006af10`
- `0x180255010`

## import_xrefs

- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006b04a`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006b512`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006b717`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006b04a`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006b512`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006b717`
- `RPCRT4!MesHandleFree` at `0x18006b016`
- `RPCRT4!MesHandleFree` at `0x18006b4da`
- `RPCRT4!MesHandleFree` at `0x18006b016`
- `RPCRT4!MesHandleFree` at `0x18006b4da`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006b483`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006b5f4`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006b60b`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006b483`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006b5f4`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006b60b`
- `RPCRT4!NdrMesTypeDecode2` at `0x18006af61`
- `RPCRT4!NdrMesTypeDecode2` at `0x18006af61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b3a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b3a8`

## string_xrefs

- `0x18006afbf`: `onecore\com\combase\actprops\actprops.cxx`
- `0x18006b65b`: `onecore\com\combase\actprops\actprops.cxx`

## pseudocode

```c
__int64 __fastcall ActivationProperties::SetupForUnserializing(ActivationProperties *this, Serializer *pSer)
{
  void **p_handle; // r14
  void *handle; // rcx
  unsigned int v6; // edx
  HRESULT v7; // ebx
  unsigned int v9; // esi
  unsigned int *p_operationSize; // r12
  unsigned int v11; // edx
  RPC_STATUS v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned int cIfs; // r9d
  unsigned int i; // r10d
  unsigned int *pSizes; // rax
  __int64 v19; // r11
  _GUID *pclsid; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  signed int v40; // ebx
  char *v41; // rax
  Serializer *v42; // rsi
  unsigned int dwMaxDestCtx; // ecx
  unsigned int dwMarshalFlags; // r8d
  unsigned int dwCurrentDestCtx; // edx
  IStream *v46; // rcx
  unsigned int direction; // ebp
  char **p_buffer; // r13
  unsigned int bufSize; // edx
  char *v50; // rcx
  handle_t *v51; // r14
  RPC_STATUS v52; // eax
  bool v53; // sf
  __int64 position; // rbp
  unsigned int operationSize; // edx
  RPC_STATUS v56; // eax
  unsigned int v57; // esi
  IStream *pOriginalStream; // rax
  unsigned int *p_nWritten; // rsi
  IStream *v60; // rcx
  __int64 v61; // r8
  unsigned __int8 *buffer; // rdx
  __int64 v63; // rax
  bool v64; // sf
  bool v65; // sf
  void *retaddr; // [rsp+78h] [rbp+0h]
  IStream *pStream; // [rsp+80h] [rbp+8h] BYREF

  p_handle = &pSer->_handle;
  handle = pSer->_handle;
  this->_unSerHeader.pSizes = 0;
  this->_unSerHeader.pclsid = 0;
  this->_unSerHeader.opaqueData = 0;
  NdrMesTypeDecode2(
    handle,
    &_MIDL_TypePicklingInfo,
    &IActivatorCustomMarshal_StubDesc,
    &custmact__MIDL_TypeFormatString.Format[322],
    &this->_unSerHeader);
  this->_serHeader.destCtx = this->_unSerHeader.destCtx;
  this->_serHeader.cOpaqueData = this->_unSerHeader.cOpaqueData;
  this->_serHeader.opaqueData = this->_unSerHeader.opaqueData;
  this->_unSerialized = 1;
  if ( !this->_unSerHeader.pSizes || !this->_unSerHeader.pclsid )
  {
    v6 = 602;
    goto LABEL_5;
  }
  if ( this->_unSerHeader.cIfs - 1 > 0xA )
  {
    v6 = 603;
    goto LABEL_5;
  }
  v9 = pSer->_position + this->_unSerHeader.headerSize;
  p_operationSize = &pSer->_operationSize;
  v7 = pSer->_pIBuff->SetPosition(pSer->_pIBuff, pSer->_bufSize, v9);
  if ( v7 )
    goto LABEL_129;
  MesHandleFree(*p_handle);
  v11 = *p_operationSize;
  *p_handle = 0;
  if ( v11 < v9 )
  {
    v7 = -2147024809;
    goto LABEL_127;
  }
  if ( pSer->_direction == 1 )
  {
    v12 = MesDecodeBufferHandleCreate((char *)&pSer->_buffer[v9], v11 - v9, p_handle);
  }
  else
  {
    pSer->_nWritten = 0;
    if ( v11 == v9 )
    {
LABEL_15:
      pSer->_position = v9;
      goto LABEL_16;
    }
    v12 = MesEncodeFixedBufferHandleCreate((char *)&pSer->_buffer[v9], v11 - v9, &pSer->_nWritten, p_handle);
  }
  v7 = v12;
  if ( !v12 )
  {
    if ( *p_handle )
      goto LABEL_15;
    v7 = -2147024882;
LABEL_127:
    v6 = 604;
    goto LABEL_6;
  }
  if ( (v12 & 0x1FFF0000) == 0x10000 )
    goto LABEL_129;
  v64 = v12 < 0;
  if ( v12 > 0 )
  {
    v7 = (unsigned __int16)v12 | 0x80070000;
LABEL_129:
    v64 = v7 < 0;
  }
  if ( v64 )
    goto LABEL_127;
LABEL_16:
  v13 = *p_operationSize;
  if ( *p_operationSize <= pSer->_bufSize && pSer->_position <= v13 )
  {
    v14 = v13 - pSer->_position;
    v15 = v14;
    if ( (v14 & 7) != 0 )
    {
      v6 = 609;
      goto LABEL_5;
    }
    cIfs = this->_unSerHeader.cIfs;
    for ( i = 0; i < cIfs; ++i )
    {
      pSizes = this->_unSerHeader.pSizes;
      if ( (pSizes[i] & 7) != 0 )
      {
        v6 = 614;
        goto LABEL_5;
      }
      v19 = pSizes[i];
      if ( v19 > v15 )
      {
        v6 = 615;
        goto LABEL_5;
      }
      pclsid = this->_unSerHeader.pclsid;
      v21 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IActivationSecurityInfo.Data1;
      if ( !v21 )
        v21 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IActivationSecurityInfo.Data4;
      if ( v21 )
      {
        v22 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_ILegacyInfo.Data1;
        if ( !v22 )
          v22 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_ILegacyInfo.Data4;
        if ( v22 )
        {
          v23 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IServerLocationInfo.Data1;
          if ( !v23 )
            v23 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IServerLocationInfo.Data4;
          if ( v23 )
          {
            v24 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IInstantiationInfo.Data1;
            if ( !v24 )
              v24 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IInstantiationInfo.Data4;
            if ( v24 )
            {
              v25 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IActivationContextInfo.Data1;
              if ( !v25 )
                v25 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IActivationContextInfo.Data4;
              if ( v25 )
              {
                v26 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IPrivActivationContextInfo.Data1;
                if ( !v26 )
                  v26 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IPrivActivationContextInfo.Data4;
                if ( v26 )
                {
                  v27 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IInstanceInfo.Data1;
                  if ( !v27 )
                    v27 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IInstanceInfo.Data4;
                  if ( v27 )
                  {
                    v28 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IScmRequestInfo.Data1;
                    if ( !v28 )
                      v28 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IScmRequestInfo.Data4;
                    if ( v28 )
                    {
                      v29 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_ISpecialSystemProperties.Data1;
                      if ( !v29 )
                        v29 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_ISpecialSystemProperties.Data4;
                      if ( v29 )
                      {
                        v30 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IOpaqueDataInfo.Data1;
                        if ( !v30 )
                          v30 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IOpaqueDataInfo.Data4;
                        if ( v30 )
                        {
                          v31 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&CLSID_ActivationPropertiesOut.Data1;
                          if ( !v31 )
                            v31 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)CLSID_ActivationPropertiesOut.Data4;
                          if ( v31 )
                          {
                            v32 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IScmReplyInfo.Data1;
                            if ( !v32 )
                              v32 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IScmReplyInfo.Data4;
                            if ( v32 )
                            {
                              v33 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IPrivActivationContextInfo.Data1;
                              if ( !v33 )
                                v33 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IPrivActivationContextInfo.Data4;
                              if ( v33 )
                              {
                                v34 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IActivationProperties.Data1;
                                if ( !v34 )
                                  v34 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IActivationProperties.Data4;
                                if ( v34 )
                                {
                                  v35 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IPrivActivationPropertiesOut.Data1;
                                  if ( !v35 )
                                    v35 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IPrivActivationPropertiesOut.Data4;
                                  if ( v35 )
                                  {
                                    v36 = *(_QWORD *)&pclsid[i].Data1
                                        - *(_QWORD *)&IID_IPrivActivationPropertiesIn.Data1;
                                    if ( !v36 )
                                      v36 = *(_QWORD *)pclsid[i].Data4
                                          - *(_QWORD *)IID_IPrivActivationPropertiesIn.Data4;
                                    if ( v36 )
                                    {
                                      v37 = *(_QWORD *)&pclsid[i].Data1
                                          - *(_QWORD *)&GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1;
                                      if ( !v37 )
                                        v37 = *(_QWORD *)pclsid[i].Data4
                                            - *(_QWORD *)GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4;
                                      if ( v37 )
                                      {
                                        v38 = *(_QWORD *)&pclsid[i].Data1 - *(_QWORD *)&IID_IUserContextProperties.Data1;
                                        if ( !v38 )
                                          v38 = *(_QWORD *)pclsid[i].Data4 - *(_QWORD *)IID_IUserContextProperties.Data4;
                                        if ( v38 )
                                        {
                                          v39 = *(_QWORD *)&pclsid[i].Data1
                                              - *(_QWORD *)&IID_IExtensionActivationContextProperties.Data1;
                                          if ( !v39 )
                                            v39 = *(_QWORD *)pclsid[i].Data4
                                                - *(_QWORD *)IID_IExtensionActivationContextProperties.Data4;
                                          if ( v39 )
                                          {
                                            v7 = -2147467262;
                                            v6 = 616;
                                            goto LABEL_6;
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      v15 -= v19;
    }
    this->_ifsIndex = cIfs;
    v40 = -2147467259;
    pStream = 0;
    if ( !pSer->_pStream )
    {
LABEL_110:
      v57 = v40;
      if ( v40 >= 0 )
      {
        pOriginalStream = pSer->_pOriginalStream;
        if ( !pOriginalStream || pOriginalStream == pSer->_pStream )
        {
          v7 = pSer->_pIBuff->SetPosition(pSer->_pIBuff, pSer->_bufSize, *p_operationSize);
        }
        else
        {
          p_nWritten = &pSer->_nWritten;
          do
          {
            v60 = pSer->_pOriginalStream;
            v61 = *p_operationSize;
            buffer = pSer->_buffer;
            *p_nWritten = 0;
            v7 = v60->Write(v60, buffer, v61, &pSer->_nWritten);
            if ( v7 )
              break;
            v63 = *p_nWritten;
            *p_operationSize -= v63;
            pSer->_buffer += v63;
          }
          while ( *p_operationSize );
        }
        if ( v7 >= 0 )
          return 0;
        v6 = 621;
        goto LABEL_6;
      }
LABEL_125:
      wil::details::in1diag3::Return_Hr(retaddr, 0x26Cu, "onecore\\com\\combase\\actprops\\actprops.cxx", v57);
      return v57;
    }
    pSer->_pIBuff->SetPosition(pSer->_pIBuff, pSer->_bufSize, 0);
    if ( pSer->_pOriginalStream )
    {
      pSer->_pIBuff->SetCopyAlignment(pSer->_pIBuff, 8u);
      v40 = pSer->_pStream->Clone(pSer->_pStream, &pStream);
      if ( v40 )
        goto LABEL_110;
    }
    else
    {
      pStream = pSer->_pStream;
    }
    v41 = (char *)HeapAlloc(g_hHeap, 0, 0x58u);
    v42 = (Serializer *)v41;
    if ( !v41 )
    {
      v57 = -2147024882;
      goto LABEL_125;
    }
    dwMaxDestCtx = pSer->_dwMaxDestCtx;
    dwMarshalFlags = pSer->_dwMarshalFlags;
    dwCurrentDestCtx = pSer->_dwCurrentDestCtx;
    *(_QWORD *)(v41 + 36) = 0;
    *((_QWORD *)v41 + 3) = 0;
    *((_DWORD *)v41 + 8) = 0;
    *((_QWORD *)v41 + 8) = 0;
    *(_QWORD *)v41 = 0;
    *((_QWORD *)v41 + 1) = 0;
    *((_QWORD *)v41 + 2) = 0;
    *((_QWORD *)v41 + 6) = 0;
    *((_DWORD *)v41 + 14) = 1;
    *((_DWORD *)v41 + 18) = dwMaxDestCtx;
    *((_DWORD *)v41 + 19) = dwCurrentDestCtx;
    *((_DWORD *)v41 + 20) = dwMarshalFlags;
    v46 = pStream;
    direction = pSer->_direction;
    *((_DWORD *)v41 + 10) = *p_operationSize;
    *((_DWORD *)v41 + 15) = direction;
    *((_QWORD *)v41 + 1) = 0;
    *(_QWORD *)v41 = v46;
    v46->AddRef(v46);
    if ( ((unsigned __int64 (__fastcall *)(IStream *, GUID *, IBufferInternal **))v42->_pStream->QueryInterface)(
           v42->_pStream,
           &IID_IBufferInternal,
           &v42->_pIBuff)
      || (p_buffer = (char **)&v42->_buffer, v42->_pIBuff->GetBuffer(v42->_pIBuff, &v42->_bufSize, &v42->_buffer))
      || (bufSize = v42->_bufSize, bufSize < v42->_operationSize) )
    {
      v40 = -2147467259;
      goto LABEL_106;
    }
    v50 = *p_buffer;
    v51 = &v42->_handle;
    v42->_handle = 0;
    if ( direction == 1 )
      v52 = MesDecodeBufferHandleCreate(v50, bufSize, &v42->_handle);
    else
      v52 = MesEncodeFixedBufferHandleCreate(v50, bufSize, &v42->_nWritten, &v42->_handle);
    v40 = v52;
    if ( !v52 )
    {
      if ( !*v51 )
      {
LABEL_93:
        v40 = -2147024882;
LABEL_106:
        if ( pStream != pSer->_pStream )
          pStream->Release(pStream);
        if ( v40 < 0 )
        {
          Serializer::Release(v42);
          this->_pUnSer = 0;
        }
        goto LABEL_110;
      }
      goto LABEL_96;
    }
    if ( (v52 & 0x1FFF0000) != 0x10000 )
    {
      v53 = v52 < 0;
      if ( v52 <= 0 )
      {
LABEL_95:
        if ( v53 )
          goto LABEL_106;
LABEL_96:
        position = pSer->_position;
        v40 = v42->_pIBuff->SetPosition(v42->_pIBuff, v42->_bufSize, position);
        if ( !v40 )
        {
          MesHandleFree(*v51);
          operationSize = v42->_operationSize;
          *v51 = 0;
          if ( operationSize < (unsigned int)position )
          {
            v40 = -2147024809;
            goto LABEL_106;
          }
          if ( v42->_direction == 1 )
          {
            v56 = MesDecodeBufferHandleCreate(&(*p_buffer)[position], operationSize - position, &v42->_handle);
          }
          else
          {
            v42->_nWritten = v40;
            if ( operationSize == (_DWORD)position )
            {
LABEL_103:
              v42->_position = position;
              goto LABEL_104;
            }
            v56 = MesEncodeFixedBufferHandleCreate(
                    &(*p_buffer)[(unsigned int)position],
                    operationSize - position,
                    &v42->_nWritten,
                    &v42->_handle);
          }
          v40 = v56;
          if ( !v56 )
          {
            if ( !*v51 )
              goto LABEL_93;
            goto LABEL_103;
          }
          if ( (v56 & 0x1FFF0000) != 0x10000 )
          {
            v65 = v56 < 0;
            if ( v56 <= 0 )
            {
LABEL_135:
              if ( v65 )
                goto LABEL_106;
LABEL_104:
              v40 = pSer->_pIBuff->SetPosition(pSer->_pIBuff, pSer->_bufSize, pSer->_position);
              if ( v40 >= 0 )
                this->_pUnSer = v42;
              goto LABEL_106;
            }
            v40 = (unsigned __int16)v56 | 0x80070000;
          }
        }
        v65 = v40 < 0;
        goto LABEL_135;
      }
      v40 = (unsigned __int16)v52 | 0x80070000;
    }
    v53 = v40 < 0;
    goto LABEL_95;
  }
  v6 = 606;
LABEL_5:
  v7 = -2147024809;
LABEL_6:
  wil::details::in1diag3::Return_Hr(retaddr, v6, "onecore\\com\\combase\\actprops\\actprops.cxx", v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006af10  push    rbx
0x18006af12  push    rbp
0x18006af13  push    rsi
0x18006af14  push    rdi
0x18006af15  push    r12
0x18006af17  push    r13
0x18006af19  push    r14
0x18006af1b  push    r15
0x18006af1d  sub     rsp, 38h
0x18006af21  mov     r15, this
0x18006af24  lea     r14, [pSer+30h]
0x18006af28  mov     this, [r14]; Handle
0x18006af2b  lea     r9, custmact__MIDL_TypeFormatString.Format+142h; pFormatString
0x18006af32  xor     r13d, r13d
0x18006af35  lea     r8, IActivatorCustomMarshal_StubDesc; pStubDesc
0x18006af3c  mov     rdi, pSer
0x18006af3f  lea     pSer, __MIDL_TypePicklingInfo; pPicklingInfo
0x18006af46  lea     rax, [r15+78h]
0x18006af4a  mov     [r15+0A8h], r13
0x18006af51  mov     [rax+28h], r13
0x18006af55  mov     [rsp+78h+pObject], rax; pObject
0x18006af5a  mov     [r15+0B0h], r13
0x18006af61  call    cs:__imp_NdrMesTypeDecode2
0x18006af67  lea     ebp, [r13+1]
0x18006af6b  mov     eax, [r15+84h]
0x18006af72  mov     [r15+44h], eax
0x18006af76  mov     eax, [r15+80h]
0x18006af7d  mov     [r15+40h], eax
0x18006af81  mov     rax, [r15+0B0h]
0x18006af88  mov     [r15+70h], rax
0x18006af8c  mov     [r15+2Ch], ebp
0x18006af90  cmp     [r15+0A8h], r13
0x18006af97  jz      short loc_18006AFE1
0x18006af99  cmp     [r15+0A0h], r13
0x18006afa0  jz      short loc_18006AFE1
0x18006afa2  mov     eax, [r15+88h]
0x18006afa9  sub     eax, ebp
0x18006afab  cmp     eax, 0Ah
0x18006afae  jbe     short loc_18006AFE8
0x18006afb0  mov     edx, 25Bh; lineNumber
0x18006afb5  mov     ebx, 80070057h
0x18006afba  mov     this, [rsp+78h]; callerReturnAddress
0x18006afbf  lea     r8, aOnecoreComComb_155; "onecore\\com\\combase\\actprops\\actpro"...
0x18006afc6  mov     r9d, ebx; hr
0x18006afc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006afce  mov     eax, ebx
0x18006afd0  add     rsp, 38h
0x18006afd4  pop     r15
0x18006afd6  pop     r14
0x18006afd8  pop     r13
0x18006afda  pop     r12
0x18006afdc  pop     rdi
0x18006afdd  pop     rsi
0x18006afde  pop     rbp
0x18006afdf  pop     rbx
0x18006afe0  retn
0x18006afe1  mov     edx, 25Ah
0x18006afe6  jmp     short loc_18006AFB5
0x18006afe8  mov     this, [rdi+10h]
0x18006afec  mov     esi, [r15+7Ch]
0x18006aff0  add     esi, [rdi+40h]
0x18006aff3  mov     edx, [rdi+24h]
0x18006aff6  mov     r8d, esi
0x18006aff9  mov     rax, [this]
0x18006affc  mov     rax, [rax+38h]
0x18006b000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b005  lea     r12, [rdi+28h]
0x18006b009  mov     ebx, eax
0x18006b00b  test    eax, eax
0x18006b00d  jnz     loc_18006B693
0x18006b013  mov     this, [r14]; Handle
0x18006b016  call    cs:__imp_MesHandleFree
0x18006b01c  mov     edx, [r12]
0x18006b020  mov     [r14], r13
0x18006b023  cmp     edx, esi
0x18006b025  jb      loc_18006B676
0x18006b02b  cmp     [rdi+3Ch], ebp
0x18006b02e  jz      loc_18006B5E9
0x18006b034  lea     r8, [rdi+20h]; pEncodedSize
0x18006b038  mov     [r8], r13d
0x18006b03b  cmp     edx, esi
0x18006b03d  jz      short loc_18006B063
0x18006b03f  mov     ecx, esi
0x18006b041  sub     edx, esi; BufferSize
0x18006b043  add     this, [rdi+18h]; pBuffer
0x18006b047  mov     r9, r14; pHandle
0x18006b04a  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x18006b050  mov     ebx, eax
0x18006b052  test    eax, eax
0x18006b054  jnz     loc_18006B685
0x18006b05a  cmp     [r14], r13
0x18006b05d  jz      loc_18006B6ED
0x18006b063  mov     [rdi+40h], esi
0x18006b066  mov     eax, [r12]
0x18006b06a  cmp     eax, [rdi+24h]
0x18006b06d  ja      loc_18006B76F
0x18006b073  cmp     [rdi+40h], eax
0x18006b076  ja      loc_18006B76F
0x18006b07c  sub     eax, [rdi+40h]
0x18006b07f  mov     r8d, eax
0x18006b082  test    al, 7
0x18006b084  jnz     loc_18006B6F4
0x18006b08a  mov     r9d, [r15+88h]
0x18006b091  mov     r10d, r13d
0x18006b094  mov     rbx, qword ptr cs:IID_IPrivActivationContextInfo.Data4
0x18006b09b  mov     rsi, qword ptr cs:IID_IPrivActivationContextInfo.Data1
0x18006b0a2  cmp     r10d, r9d
0x18006b0a5  jnb     loc_18006B34F
0x18006b0ab  mov     rax, [r15+0A8h]
0x18006b0b2  mov     ecx, r10d
0x18006b0b5  test    byte ptr [rax+this*4], 7
0x18006b0b9  jnz     loc_18006B6FE
0x18006b0bf  mov     r11d, [rax+this*4]
0x18006b0c3  cmp     r11, r8
0x18006b0c6  jg      loc_18006B69D
0x18006b0cc  mov     rax, [r15+0A0h]
0x18006b0d3  add     this, this
0x18006b0d6  mov     pSer, [rax+this*8]
0x18006b0da  sub     pSer, qword ptr cs:IID_IActivationSecurityInfo.Data1
0x18006b0e1  jnz     short loc_18006B0EF
0x18006b0e3  mov     pSer, [rax+this*8+8]
0x18006b0e8  sub     pSer, qword ptr cs:IID_IActivationSecurityInfo.Data4
0x18006b0ef  test    pSer, pSer
0x18006b0f2  jnz     short loc_18006B0FC
0x18006b0f4  sub     r8, r11
0x18006b0f7  add     r10d, ebp
0x18006b0fa  jmp     short loc_18006B0A2
0x18006b0fc  mov     pSer, [rax+this*8]
0x18006b100  sub     pSer, qword ptr cs:IID_ILegacyInfo.Data1
0x18006b107  jnz     short loc_18006B115
0x18006b109  mov     pSer, [rax+this*8+8]
0x18006b10e  sub     pSer, qword ptr cs:IID_ILegacyInfo.Data4
0x18006b115  test    pSer, pSer
0x18006b118  jz      short loc_18006B0F4
0x18006b11a  mov     pSer, [rax+this*8]
0x18006b11e  sub     pSer, qword ptr cs:IID_IServerLocationInfo.Data1
0x18006b125  jnz     short loc_18006B133
0x18006b127  mov     pSer, [rax+this*8+8]
0x18006b12c  sub     pSer, qword ptr cs:IID_IServerLocationInfo.Data4
0x18006b133  test    pSer, pSer
0x18006b136  jz      short loc_18006B0F4
0x18006b138  mov     pSer, [rax+this*8]
0x18006b13c  sub     pSer, qword ptr cs:IID_IInstantiationInfo.Data1
0x18006b143  jnz     short loc_18006B151
0x18006b145  mov     pSer, [rax+this*8+8]
0x18006b14a  sub     pSer, qword ptr cs:IID_IInstantiationInfo.Data4
0x18006b151  test    pSer, pSer
0x18006b154  jz      short loc_18006B0F4
0x18006b156  mov     pSer, [rax+this*8]
0x18006b15a  sub     pSer, qword ptr cs:IID_IActivationContextInfo.Data1
0x18006b161  jnz     short loc_18006B16F
0x18006b163  mov     pSer, [rax+this*8+8]
0x18006b168  sub     pSer, qword ptr cs:IID_IActivationContextInfo.Data4
0x18006b16f  test    pSer, pSer
0x18006b172  jz      short loc_18006B0F4
0x18006b174  mov     pSer, [rax+this*8]
0x18006b178  sub     pSer, rsi
0x18006b17b  jnz     short loc_18006B185
0x18006b17d  mov     pSer, [rax+this*8+8]
0x18006b182  sub     pSer, rbx
0x18006b185  test    pSer, pSer
0x18006b188  jz      loc_18006B0F4
0x18006b18e  mov     pSer, [rax+this*8]
0x18006b192  sub     pSer, qword ptr cs:IID_IInstanceInfo.Data1
0x18006b199  jnz     short loc_18006B1A7
0x18006b19b  mov     pSer, [rax+this*8+8]
0x18006b1a0  sub     pSer, qword ptr cs:IID_IInstanceInfo.Data4
0x18006b1a7  test    pSer, pSer
0x18006b1aa  jz      loc_18006B0F4
0x18006b1b0  mov     pSer, [rax+this*8]
0x18006b1b4  sub     pSer, qword ptr cs:IID_IScmRequestInfo.Data1
0x18006b1bb  jnz     short loc_18006B1C9
0x18006b1bd  mov     pSer, [rax+this*8+8]
0x18006b1c2  sub     pSer, qword ptr cs:IID_IScmRequestInfo.Data4
0x18006b1c9  test    pSer, pSer
0x18006b1cc  jz      loc_18006B0F4
0x18006b1d2  mov     pSer, [rax+this*8]
0x18006b1d6  sub     pSer, qword ptr cs:IID_ISpecialSystemProperties.Data1
0x18006b1dd  jnz     short loc_18006B1EB
0x18006b1df  mov     pSer, [rax+this*8+8]
0x18006b1e4  sub     pSer, qword ptr cs:IID_ISpecialSystemProperties.Data4
0x18006b1eb  test    pSer, pSer
0x18006b1ee  jz      loc_18006B0F4
0x18006b1f4  mov     pSer, [rax+this*8]
0x18006b1f8  sub     pSer, qword ptr cs:IID_IOpaqueDataInfo.Data1
0x18006b1ff  jnz     short loc_18006B20D
0x18006b201  mov     pSer, [rax+this*8+8]
0x18006b206  sub     pSer, qword ptr cs:IID_IOpaqueDataInfo.Data4
0x18006b20d  test    pSer, pSer
0x18006b210  jz      loc_18006B0F4
0x18006b216  mov     pSer, [rax+this*8]
0x18006b21a  sub     pSer, qword ptr cs:CLSID_ActivationPropertiesOut.Data1
0x18006b221  jnz     short loc_18006B22F
0x18006b223  mov     pSer, [rax+this*8+8]
0x18006b228  sub     pSer, qword ptr cs:CLSID_ActivationPropertiesOut.Data4
0x18006b22f  test    pSer, pSer
0x18006b232  jz      loc_18006B0F4
0x18006b238  mov     pSer, [rax+this*8]
0x18006b23c  sub     pSer, qword ptr cs:IID_IScmReplyInfo.Data1
0x18006b243  jnz     short loc_18006B251
0x18006b245  mov     pSer, [rax+this*8+8]
0x18006b24a  sub     pSer, qword ptr cs:IID_IScmReplyInfo.Data4
0x18006b251  test    pSer, pSer
0x18006b254  jz      loc_18006B0F4
0x18006b25a  mov     pSer, [rax+this*8]
0x18006b25e  sub     pSer, rsi
0x18006b261  jnz     short loc_18006B26B
0x18006b263  mov     pSer, [rax+this*8+8]
0x18006b268  sub     pSer, rbx
0x18006b26b  test    pSer, pSer
0x18006b26e  jz      loc_18006B0F4
0x18006b274  mov     pSer, [rax+this*8]
0x18006b278  sub     pSer, qword ptr cs:IID_IActivationProperties.Data1
0x18006b27f  jnz     short loc_18006B28D
0x18006b281  mov     pSer, [rax+this*8+8]
0x18006b286  sub     pSer, qword ptr cs:IID_IActivationProperties.Data4
0x18006b28d  test    pSer, pSer
0x18006b290  jz      loc_18006B0F4
0x18006b296  mov     pSer, [rax+this*8]
0x18006b29a  sub     pSer, qword ptr cs:IID_IPrivActivationPropertiesOut.Data1
0x18006b2a1  jnz     short loc_18006B2AF
0x18006b2a3  mov     pSer, [rax+this*8+8]
0x18006b2a8  sub     pSer, qword ptr cs:IID_IPrivActivationPropertiesOut.Data4
0x18006b2af  test    pSer, pSer
0x18006b2b2  jz      loc_18006B0F4
0x18006b2b8  mov     pSer, [rax+this*8]
0x18006b2bc  sub     pSer, qword ptr cs:IID_IPrivActivationPropertiesIn.Data1
0x18006b2c3  jnz     short loc_18006B2D1
0x18006b2c5  mov     pSer, [rax+this*8+8]
0x18006b2ca  sub     pSer, qword ptr cs:IID_IPrivActivationPropertiesIn.Data4
0x18006b2d1  test    pSer, pSer
0x18006b2d4  jz      loc_18006B0F4
0x18006b2da  mov     pSer, [rax+this*8]
0x18006b2de  sub     pSer, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data1
0x18006b2e5  jnz     short loc_18006B2F3
0x18006b2e7  mov     pSer, [rax+this*8+8]
0x18006b2ec  sub     pSer, qword ptr cs:_GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a.Data4
0x18006b2f3  test    pSer, pSer
0x18006b2f6  jz      loc_18006B0F4
0x18006b2fc  mov     pSer, [rax+this*8]
0x18006b300  sub     pSer, qword ptr cs:IID_IUserContextProperties.Data1
0x18006b307  jnz     short loc_18006B315
0x18006b309  mov     pSer, [rax+this*8+8]
0x18006b30e  sub     pSer, qword ptr cs:IID_IUserContextProperties.Data4
0x18006b315  test    pSer, pSer
0x18006b318  jz      loc_18006B0F4
0x18006b31e  mov     pSer, [rax+this*8]
0x18006b322  sub     pSer, qword ptr cs:IID_IExtensionActivationContextProperties.Data1
0x18006b329  jnz     short loc_18006B337
0x18006b32b  mov     pSer, [rax+this*8+8]
0x18006b330  sub     pSer, qword ptr cs:IID_IExtensionActivationContextProperties.Data4
0x18006b337  test    pSer, pSer
0x18006b33a  jz      loc_18006B0F4
0x18006b340  mov     ebx, 80004002h
0x18006b345  mov     edx, 268h
0x18006b34a  jmp     loc_18006AFBA
0x18006b34f  mov     [r15+130h], r9d
0x18006b356  mov     r14d, 80004005h
0x18006b35c  mov     ebx, r14d
0x18006b35f  mov     [rsp+78h+arg_0], r13
0x18006b367  cmp     [rdi], r13
0x18006b36a  jz      loc_18006B56F
0x18006b370  mov     this, [rdi+10h]
0x18006b374  xor     r8d, r8d
0x18006b377  mov     edx, [rdi+24h]
0x18006b37a  mov     rax, [this]
0x18006b37d  mov     rax, [rax+38h]
0x18006b381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b386  cmp     [rdi+8], r13
0x18006b38a  jnz     loc_18006B616
0x18006b390  mov     rax, [rdi]
0x18006b393  mov     [rsp+78h+arg_0], rax
0x18006b39b  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006b3a2  xor     edx, edx; dwFlags
0x18006b3a4  lea     r8d, [pSer+58h]; dwBytes
0x18006b3a8  call    cs:__imp_HeapAlloc
0x18006b3ae  mov     rsi, rax
0x18006b3b1  test    rax, rax
0x18006b3b4  jz      loc_18006B651
0x18006b3ba  mov     ecx, [rdi+48h]
0x18006b3bd  mov     r8d, [rdi+50h]
0x18006b3c1  mov     edx, [rdi+4Ch]
0x18006b3c4  mov     [rax+24h], r13
0x18006b3c8  mov     [rax+18h], r13
0x18006b3cc  mov     [rax+20h], r13d
0x18006b3d0  mov     [rax+40h], r13
0x18006b3d4  mov     [rax], r13
0x18006b3d7  mov     [rax+8], r13
0x18006b3db  mov     [rax+10h], r13
0x18006b3df  mov     [rax+30h], r13
0x18006b3e3  mov     [rax+38h], ebp
0x18006b3e6  mov     [rax+48h], ecx
0x18006b3e9  mov     [rax+4Ch], edx
0x18006b3ec  mov     [rax+50h], r8d
0x18006b3f0  mov     this, [rsp+78h+arg_0]
0x18006b3f8  mov     eax, [r12]
0x18006b3fc  mov     ebp, [rdi+3Ch]
0x18006b3ff  mov     [rsi+28h], eax
0x18006b402  mov     [rsi+3Ch], ebp
0x18006b405  mov     [rsi+8], r13
  ... truncated ...
```
