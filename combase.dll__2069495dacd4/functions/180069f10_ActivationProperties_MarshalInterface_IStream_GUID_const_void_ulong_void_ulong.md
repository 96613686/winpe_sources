# ActivationProperties::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180069f10`
- end: `0x18006a57e`
- name: `?MarshalInterface@ActivationProperties@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `1646`
- prototype: `HRESULT __fastcall(ActivationProperties *this, IStream *pStm, const _GUID *riid, void *pv, unsigned int dwDestContext, void *pvDestContext, unsigned int mshlflags)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180069f10`
- `0x18006a7a0`
- `0x18006b780`
- `0x18006ba20`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006a0f1`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006a22a`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006a0f1`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18006a22a`
- `RPCRT4!MesHandleFree` at `0x18006a0b0`
- `RPCRT4!MesHandleFree` at `0x18006a1e9`
- `RPCRT4!MesHandleFree` at `0x18006a506`
- `RPCRT4!MesHandleFree` at `0x18006a0b0`
- `RPCRT4!MesHandleFree` at `0x18006a1e9`
- `RPCRT4!MesHandleFree` at `0x18006a506`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006a287`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006a36a`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006a287`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18006a36a`
- `RPCRT4!RpcExceptionFilter` at `0x18024398e`
- `RPCRT4!RpcExceptionFilter` at `0x18024398e`
- `RPCRT4!NdrMesTypeEncode2` at `0x18006a07d`
- `RPCRT4!NdrMesTypeEncode2` at `0x18006a07d`

## pseudocode

```c
__int64 __fastcall ActivationProperties::MarshalInterface(
        ActivationProperties *this,
        IStream *pStm,
        const _GUID *riid,
        void *pv,
        unsigned int dwDestContext)
{
  __int64 result; // rax
  int v8; // r13d
  __int64 operationSize; // rdx
  HRESULT inited; // edi
  __int64 v11; // r8
  unsigned int v12; // edi
  unsigned int v13; // ecx
  RPC_STATUS v14; // eax
  bool v15; // zf
  unsigned int headerSize; // r12d
  unsigned int v17; // r15d
  unsigned int v18; // edi
  unsigned int bufSize; // r9d
  unsigned __int64 v20; // r14
  SerializableProperty *v21; // rcx
  HRESULT v22; // eax
  unsigned int v23; // r14d
  signed int v24; // ecx
  RPC_STATUS v25; // eax
  Serializer *pUnSer; // rcx
  unsigned int v27; // eax
  IStream *pStream; // rax
  Serializer ser; // [rsp+30h] [rbp-B8h] BYREF
  HRESULT hr; // [rsp+90h] [rbp-58h]
  int fReleaseThis; // [rsp+94h] [rbp-54h]
  void *pvLocal; // [rsp+98h] [rbp-50h] BYREF
  unsigned int v33; // [rsp+A0h] [rbp-48h]
  unsigned int v34; // [rsp+A4h] [rbp-44h]
  unsigned __int64 v35; // [rsp+A8h] [rbp-40h]
  void *ppv; // [rsp+B0h] [rbp-38h] BYREF

  ppv = 0;
  result = this->QueryInterface(this, riid, &ppv);
  if ( (int)result < 0 )
    return result;
  v8 = 1;
  fReleaseThis = 1;
  *(_QWORD *)&ser._position = 0;
  memset(&ser, 0, 44);
  ser._handle = 0;
  ser._clRefs = 1;
  ser._dwMaxDestCtx = this->_serHeader.destCtx;
  ser._dwCurrentDestCtx = dwDestContext;
  ser._dwMarshalFlags = this->_marshalFlags;
  pvLocal = 0;
  if ( dwDestContext - 3 <= 1 )
  {
    pvLocal = this;
    v8 = 0;
    fReleaseThis = 0;
  }
  else
  {
    pvLocal = 0;
  }
  inited = Serializer::InitStream(&ser, pStm, &this->_serHeader.totalSize, 2u, &pvLocal);
  hr = inited;
  if ( inited < 0 )
  {
    if ( v8 )
      this->Release(this);
    Serializer::~Serializer(&ser);
    return (unsigned int)inited;
  }
  if ( pvLocal && !this->_fInprocSerializationRequired )
  {
    v18 = 0;
    hr = 0;
    goto LABEL_82;
  }
  v35 = 0;
  if ( this->_ifsIndex >= 0xC )
    goto LABEL_80;
  if ( ser._operationSize > ser._bufSize )
    goto LABEL_80;
  if ( ser._position > ser._operationSize )
    goto LABEL_80;
  v35 = ser._operationSize - ser._position;
  if ( v35 < this->_headerSize )
    goto LABEL_80;
  NdrMesTypeEncode2(
    ser._handle,
    &_MIDL_TypePicklingInfo,
    &IActivatorCustomMarshal_StubDesc,
    &custmact__MIDL_TypeFormatString.Format[322],
    &this->_serHeader);
  v12 = ser._position + this->_headerSize;
  v13 = ser._pIBuff->SetPosition(ser._pIBuff, ser._bufSize, v12);
  if ( v13 )
  {
LABEL_18:
    v15 = v13 == 0;
    goto LABEL_19;
  }
  MesHandleFree(ser._handle);
  ser._handle = 0;
  operationSize = ser._operationSize;
  if ( ser._operationSize < v12 )
  {
LABEL_80:
    v18 = -2147024809;
    goto LABEL_46;
  }
  if ( ser._direction == 1 )
  {
    v14 = MesDecodeBufferHandleCreate((char *)&ser._buffer[v12], ser._operationSize - v12, &ser._handle);
  }
  else
  {
    ser._nWritten = 0;
    if ( ser._operationSize == v12 )
    {
      ser._position = v12;
      goto LABEL_80;
    }
    v14 = MesEncodeFixedBufferHandleCreate(
            (char *)&ser._buffer[v12],
            ser._operationSize - v12,
            &ser._nWritten,
            &ser._handle);
  }
  v13 = v14;
  if ( !v14 )
  {
    if ( ser._handle )
    {
      ser._position = v12;
      v13 = 0;
      goto LABEL_18;
    }
    goto LABEL_80;
  }
  if ( (v14 & 0x1FFF0000) == 0x10000 )
    goto LABEL_18;
  v15 = v14 == 0;
  if ( v14 > 0 )
  {
    v13 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_18;
  }
LABEL_19:
  if ( !v15 )
    goto LABEL_80;
  headerSize = this->_unSerHeader.headerSize;
  v33 = headerSize;
  v17 = 0;
  v34 = 0;
  v18 = -2147024809;
  operationSize = ser._operationSize;
  bufSize = ser._bufSize;
  while ( v17 < this->_ifsIndex )
  {
    v20 = this->_sizeArray[v17];
    if ( !(_DWORD)v20 )
      goto LABEL_41;
    if ( (unsigned int)operationSize > bufSize )
      goto LABEL_46;
    if ( ser._position > (unsigned int)operationSize )
      goto LABEL_46;
    v35 = (unsigned int)(operationSize - ser._position);
    v11 = (unsigned int)v20;
    if ( v35 < v20 )
      goto LABEL_46;
    if ( !this->_unSerialized || this->serializableIfsCollection[v17] )
    {
      v21 = this->serializableIfsCollection[v17];
      v22 = ((__int64 (__fastcall *)(SerializableProperty *, Serializer *, _QWORD))v21->Serialize)(
              v21,
              &ser,
              (unsigned int)v20);
      if ( v22 )
        goto LABEL_45;
      v23 = ser._position + this->_sizeArray[v17];
      v24 = ser._pIBuff->SetPosition(ser._pIBuff, ser._bufSize, v23);
      if ( !v24 )
      {
        MesHandleFree(ser._handle);
        ser._handle = 0;
        operationSize = ser._operationSize;
        if ( ser._operationSize < v23 )
        {
          v24 = -2147024809;
          goto LABEL_37;
        }
        if ( ser._direction == 1 )
        {
          v25 = MesDecodeBufferHandleCreate((char *)&ser._buffer[v23], ser._operationSize - v23, &ser._handle);
        }
        else
        {
          ser._nWritten = 0;
          if ( ser._operationSize == v23 )
          {
            ser._position = v23;
            v24 = 1;
            goto LABEL_37;
          }
          v25 = MesEncodeFixedBufferHandleCreate(
                  (char *)&ser._buffer[v23],
                  ser._operationSize - v23,
                  &ser._nWritten,
                  &ser._handle);
        }
        v24 = v25;
        if ( v25 )
        {
          if ( (v25 & 0x1FFF0000) != 0x10000 && v25 > 0 )
            v24 = (unsigned __int16)v25 | 0x80070000;
        }
        else if ( ser._handle )
        {
          ser._position = v23;
          v24 = 0;
        }
        else
        {
          v24 = -2147024882;
        }
      }
    }
    else
    {
      pUnSer = this->_pUnSer;
      v27 = pUnSer->_bufSize;
      if ( headerSize >= v27 )
      {
        v24 = -2147024809;
        goto LABEL_38;
      }
      if ( (unsigned int)v20 > v27 - headerSize || (unsigned int)v20 > bufSize - ser._position )
      {
        v24 = -2147467259;
        goto LABEL_38;
      }
      memcpy_0(&ser._buffer[ser._position], &pUnSer->_buffer[headerSize], (unsigned int)v20);
      v24 = Serializer::SetPosition(&ser, v20 + ser._position);
    }
    operationSize = ser._operationSize;
LABEL_37:
    bufSize = ser._bufSize;
LABEL_38:
    if ( v24 < 0 )
    {
      v18 = v24;
      goto LABEL_46;
    }
    if ( v24 == 1 && v17 != this->_ifsIndex - 1 )
      goto LABEL_46;
    if ( this->_unSerialized )
    {
      if ( v17 < this->_unSerHeader.cIfs )
      {
        headerSize += this->_unSerHeader.pSizes[v17];
        v33 = headerSize;
      }
    }
LABEL_41:
    v34 = ++v17;
  }
  if ( !ser._pOriginalStream || ser._pOriginalStream == ser._pStream )
  {
    v22 = ser._pIBuff->SetPosition(ser._pIBuff, bufSize, operationSize);
LABEL_45:
    v18 = v22;
    goto LABEL_46;
  }
  do
  {
    ser._nWritten = 0;
    v18 = ser._pOriginalStream->Write(ser._pOriginalStream, ser._buffer, operationSize, &ser._nWritten);
    if ( v18 )
      break;
    operationSize = ser._operationSize - ser._nWritten;
    ser._operationSize = operationSize;
    ser._buffer += ser._nWritten;
  }
  while ( (_DWORD)operationSize );
LABEL_46:
  hr = v18;
LABEL_82:
  this->_marshalState = MARSHALLED;
  if ( v8 )
    ((void (__fastcall *)(ActivationProperties *, __int64, __int64))this->Release)(this, operationSize, v11);
  if ( ser._handle )
  {
    MesHandleFree(ser._handle);
    ser._handle = 0;
  }
  pStream = ser._pStream;
  if ( ser._pStream )
  {
    ((void (__fastcall *)(IBufferInternal *, __int64, __int64))ser._pIBuff->Release)(ser._pIBuff, operationSize, v11);
    ser._pStream->Release(ser._pStream);
    pStream = ser._pStream;
  }
  if ( ser._pOriginalStream && ser._pOriginalStream != pStream )
    ((void (__fastcall *)(IStream *, IStream_vtbl *, __int64))ser._pOriginalStream->Release)(
      ser._pOriginalStream,
      ser._pOriginalStream->__vftable,
      v11);
  return v18;
}

```

## disassembly

```asm
0x180069f10  mov     r11, rsp
0x180069f13  mov     [r11+10h], rbx
0x180069f17  mov     [r11+18h], rsi
0x180069f1b  mov     [r11+8], this
0x180069f1f  push    rdi
0x180069f20  push    r12
0x180069f22  push    r13
0x180069f24  push    r14
0x180069f26  push    r15
0x180069f28  sub     rsp, 0C0h
0x180069f2f  mov     pv, riid
0x180069f32  mov     rdi, pStm
0x180069f35  mov     rsi, this
0x180069f38  xor     ebx, ebx
0x180069f3a  mov     [r11-38h], rbx
0x180069f3e  mov     rax, [this]
0x180069f41  lea     riid, [r11-38h]
0x180069f45  mov     pStm, pv
0x180069f48  mov     rax, [rax]
0x180069f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f50  test    eax, eax
0x180069f52  js      loc_18006A54E
0x180069f58  lea     r15d, [rbx+1]
0x180069f5c  mov     r13d, r15d
0x180069f5f  mov     [rsp+0E8h+fReleaseThis], r15d
0x180069f67  lea     r14, [rsi+38h]
0x180069f6b  mov     qword ptr [rsp+0E8h+ser._bufSize], rbx
0x180069f70  mov     [rsp+0E8h+ser._buffer], rbx
0x180069f75  mov     [rsp+0E8h+ser._nWritten], ebx
0x180069f79  mov     qword ptr [rsp+0E8h+ser._position], rbx
0x180069f7e  xorps   xmm0, xmm0
0x180069f81  movdqa  xmmword ptr [rsp+0E8h+ser._pStream], xmm0
0x180069f87  mov     [rsp+0E8h+ser._pIBuff], rbx
0x180069f8c  mov     [rsp+0E8h+ser._handle], rbx
0x180069f91  mov     [rsp+0E8h+ser._clRefs], r15d
0x180069f96  mov     eax, [r14+0Ch]
0x180069f9a  mov     [rsp+0E8h+ser._dwMaxDestCtx], eax
0x180069f9e  mov     ecx, [rsp+0E8h+arg_20]
0x180069fa5  mov     [rsp+0E8h+ser._dwCurrentDestCtx], ecx
0x180069fa9  mov     eax, [rsi+0B8h]
0x180069faf  mov     [rsp+0E8h+ser._dwMarshalFlags], eax
0x180069fb6  mov     [rsp+0E8h+pvLocal], rbx
0x180069fbe  lea     eax, [this-3]
0x180069fc1  cmp     eax, r15d
0x180069fc4  jbe     loc_18006A488
0x180069fca  mov     [rsp+0E8h+pvLocal], rbx
0x180069fd2  lea     rax, [rsp+0E8h+pvLocal]
0x180069fda  mov     [rsp+0E8h+pMarshalPtr], rax; pMarshalPtr
0x180069fdf  mov     r9d, 2; direction
0x180069fe5  mov     riid, r14; dwSize
0x180069fe8  mov     pStm, rdi; pStream
0x180069feb  lea     this, [rsp+0E8h+ser]; this
0x180069ff0  call    ?InitStream@Serializer@@QEAAJPEAUIStream@@AEAKKAEAPEAX@Z; Serializer::InitStream(IStream *,ulong &,ulong,void * &)
0x180069ff5  mov     edi, eax
0x180069ff7  mov     [rsp+0E8h+hr], eax
0x180069ffe  test    eax, eax
0x18006a000  js      loc_18006A3ED
0x18006a006  cmp     [rsp+0E8h+pvLocal], rbx
0x18006a00e  jnz     loc_18006A412
0x18006a014  mov     [rsp+0E8h+var_40], rbx
0x18006a01c  cmp     dword ptr [rsi+130h], 0Ch
0x18006a023  jnb     loc_18006A4A3
0x18006a029  mov     eax, [rsp+0E8h+ser._operationSize]
0x18006a02d  cmp     eax, [rsp+0E8h+ser._bufSize]
0x18006a031  ja      loc_18006A4A3
0x18006a037  cmp     [rsp+0E8h+ser._position], eax
0x18006a03b  ja      loc_18006A4A3
0x18006a041  sub     eax, [rsp+0E8h+ser._position]
0x18006a045  mov     ecx, eax
0x18006a047  mov     [rsp+0E8h+var_40], this
0x18006a04f  mov     eax, [rsi+224h]
0x18006a055  cmp     this, rax
0x18006a058  jb      loc_18006A4A3
0x18006a05e  mov     [rsp+0E8h+pMarshalPtr], r14; pObject
0x18006a063  lea     pv, custmact__MIDL_TypeFormatString.Format+142h; pFormatString
0x18006a06a  lea     riid, IActivatorCustomMarshal_StubDesc; pStubDesc
0x18006a071  lea     pStm, __MIDL_TypePicklingInfo; pPicklingInfo
0x18006a078  mov     this, [rsp+0E8h+ser._handle]; Handle
0x18006a07d  call    cs:__imp_NdrMesTypeEncode2
0x18006a083  mov     edi, [rsi+224h]
0x18006a089  add     edi, [rsp+0E8h+ser._position]
0x18006a08d  mov     this, [rsp+0E8h+ser._pIBuff]
0x18006a092  mov     rax, [this]
0x18006a095  mov     r8d, edi
0x18006a098  mov     edx, [rsp+0E8h+ser._bufSize]
0x18006a09c  mov     rax, [rax+38h]
0x18006a0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a0a5  mov     ecx, eax
0x18006a0a7  test    eax, eax
0x18006a0a9  jnz     short loc_18006A112
0x18006a0ab  mov     this, [rsp+0E8h+ser._handle]; Handle
0x18006a0b0  call    cs:__imp_MesHandleFree
0x18006a0b6  mov     [rsp+0E8h+ser._handle], rbx
0x18006a0bb  mov     edx, [rsp+0E8h+ser._operationSize]
0x18006a0bf  cmp     edx, edi
0x18006a0c1  jb      loc_18006A4A3
0x18006a0c7  cmp     [rsp+0E8h+ser._direction], r15d
0x18006a0cc  jz      loc_18006A35C
0x18006a0d2  mov     [rsp+0E8h+ser._nWritten], ebx
0x18006a0d6  cmp     edx, edi
0x18006a0d8  jz      loc_18006A49F
0x18006a0de  sub     edx, edi; BufferSize
0x18006a0e0  mov     ecx, edi
0x18006a0e2  add     this, [rsp+0E8h+ser._buffer]; pBuffer
0x18006a0e7  lea     pv, [rsp+0E8h+ser._handle]; pHandle
0x18006a0ec  lea     riid, [rsp+0E8h+ser._nWritten]; pEncodedSize
0x18006a0f1  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x18006a0f7  mov     ecx, eax
0x18006a0f9  test    eax, eax
0x18006a0fb  jnz     loc_18006A433
0x18006a101  cmp     [rsp+0E8h+ser._handle], rbx
0x18006a106  jz      loc_18006A4A3
0x18006a10c  mov     [rsp+0E8h+ser._position], edi
0x18006a110  mov     ecx, ebx
0x18006a112  test    ecx, ecx
0x18006a114  jnz     loc_18006A4A3
0x18006a11a  mov     r12d, [rsi+7Ch]
0x18006a11e  mov     [rsp+0E8h+var_48], r12d
0x18006a126  mov     r15d, ebx
0x18006a129  mov     [rsp+0E8h+var_44], ebx
0x18006a130  mov     edi, 80070057h
0x18006a135  mov     edx, [rsp+0E8h+ser._operationSize]
0x18006a139  mov     r9d, [rsp+0E8h+ser._bufSize]
0x18006a13e  cmp     r15d, [rsi+130h]
0x18006a145  jnb     loc_18006A28F
0x18006a14b  mov     r10d, r15d
0x18006a14e  mov     r14d, [rsi+r10*4+1F4h]
0x18006a156  test    r14d, r14d
0x18006a159  jz      loc_18006A45B
0x18006a15f  cmp     edx, r9d
0x18006a162  ja      loc_18006A2B2
0x18006a168  cmp     [rsp+0E8h+ser._position], edx
0x18006a16c  ja      loc_18006A2B2
0x18006a172  mov     ecx, edx
0x18006a174  sub     ecx, [rsp+0E8h+ser._position]
0x18006a178  mov     [rsp+0E8h+var_40], this
0x18006a180  mov     r8d, r14d; Size
0x18006a183  cmp     this, r14
0x18006a186  jb      loc_18006A2B2
0x18006a18c  cmp     [rsi+2Ch], ebx
0x18006a18f  jnz     loc_18006A2D4
0x18006a195  mov     this, [rsi+r10*8+0D0h]
0x18006a19d  mov     rax, [this]
0x18006a1a0  lea     pStm, [rsp+0E8h+ser]
0x18006a1a5  mov     rax, [rax+18h]
0x18006a1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1ae  test    eax, eax
0x18006a1b0  jnz     loc_18006A2B0
0x18006a1b6  mov     eax, r15d
0x18006a1b9  mov     r14d, [rsi+rax*4+1F4h]
0x18006a1c1  add     r14d, [rsp+0E8h+ser._position]
0x18006a1c6  mov     this, [rsp+0E8h+ser._pIBuff]
0x18006a1cb  mov     rax, [this]
0x18006a1ce  mov     r8d, r14d
0x18006a1d1  mov     edx, [rsp+0E8h+ser._bufSize]
0x18006a1d5  mov     rax, [rax+38h]
0x18006a1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1de  mov     ecx, eax
0x18006a1e0  test    eax, eax
0x18006a1e2  jnz     short loc_18006A248
0x18006a1e4  mov     this, [rsp+0E8h+ser._handle]; Handle
0x18006a1e9  call    cs:__imp_MesHandleFree
0x18006a1ef  mov     [rsp+0E8h+ser._handle], rbx
0x18006a1f4  mov     edx, [rsp+0E8h+ser._operationSize]
0x18006a1f8  cmp     edx, r14d
0x18006a1fb  jb      loc_18006A375
0x18006a201  cmp     [rsp+0E8h+ser._direction], 1
0x18006a206  jz      short loc_18006A277
0x18006a208  mov     [rsp+0E8h+ser._nWritten], ebx
0x18006a20c  cmp     edx, r14d
0x18006a20f  jz      loc_18006A2FC
0x18006a215  sub     edx, r14d; BufferSize
0x18006a218  mov     ecx, r14d
0x18006a21b  add     this, [rsp+0E8h+ser._buffer]; pBuffer
0x18006a220  lea     pv, [rsp+0E8h+ser._handle]; pHandle
0x18006a225  lea     riid, [rsp+0E8h+ser._nWritten]; pEncodedSize
0x18006a22a  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x18006a230  mov     ecx, eax
0x18006a232  test    eax, eax
0x18006a234  jnz     loc_18006A3C5
0x18006a23a  cmp     [rsp+0E8h+ser._handle], rbx
0x18006a23f  jz      short loc_18006A2BE
0x18006a241  mov     [rsp+0E8h+ser._position], r14d
0x18006a246  mov     ecx, ebx
0x18006a248  mov     edx, [rsp+0E8h+ser._operationSize]
0x18006a24c  mov     r9d, [rsp+0E8h+ser._bufSize]
0x18006a251  test    ecx, ecx
0x18006a253  js      loc_18006A42C
0x18006a259  cmp     ecx, 1
0x18006a25c  jz      short loc_18006A2C5
0x18006a25e  cmp     [rsi+2Ch], ebx
0x18006a261  jnz     loc_18006A460
0x18006a267  inc     r15d
0x18006a26a  mov     [rsp+0E8h+var_44], r15d
0x18006a272  jmp     loc_18006A13E
0x18006a277  sub     edx, r14d; BufferSize
0x18006a27a  mov     ecx, r14d
0x18006a27d  add     this, [rsp+0E8h+ser._buffer]; Buffer
0x18006a282  lea     riid, [rsp+0E8h+ser._handle]; pHandle
0x18006a287  call    cs:__imp_MesDecodeBufferHandleCreate
0x18006a28d  jmp     short loc_18006A230
0x18006a28f  mov     this, [rsp+0E8h+ser._pOriginalStream]
0x18006a294  test    this, this
0x18006a297  jnz     short loc_18006A30B
0x18006a299  mov     this, [rsp+0E8h+ser._pIBuff]
0x18006a29e  mov     rax, [this]
0x18006a2a1  mov     r8d, edx
0x18006a2a4  mov     edx, r9d
0x18006a2a7  mov     rax, [rax+38h]
0x18006a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2b0  mov     edi, eax
0x18006a2b2  mov     [rsp+0E8h+hr], edi
0x18006a2b9  jmp     loc_18006A4B7
0x18006a2be  mov     ecx, 8007000Eh
0x18006a2c3  jmp     short loc_18006A248
0x18006a2c5  mov     eax, [rsi+130h]
0x18006a2cb  dec     eax
0x18006a2cd  cmp     r15d, eax
0x18006a2d0  jz      short loc_18006A25E
0x18006a2d2  jmp     short loc_18006A2B2
0x18006a2d4  cmp     [rsi+r10*8+0D0h], rbx
0x18006a2dc  jnz     loc_18006A195
0x18006a2e2  mov     this, [rsi+228h]
0x18006a2e9  mov     eax, [this+24h]
0x18006a2ec  cmp     r12d, eax
0x18006a2ef  jb      loc_18006A37C
0x18006a2f5  mov     ecx, edi
0x18006a2f7  jmp     loc_18006A251
0x18006a2fc  mov     [rsp+0E8h+ser._position], r14d
0x18006a301  mov     ecx, 1
0x18006a306  jmp     loc_18006A24C
0x18006a30b  cmp     this, [rsp+0E8h+ser._pStream]
0x18006a310  jz      short loc_18006A299
0x18006a312  mov     [rsp+0E8h+ser._nWritten], ebx
0x18006a316  mov     this, [rsp+0E8h+ser._pOriginalStream]
0x18006a31b  mov     rax, [this]
0x18006a31e  lea     pv, [rsp+0E8h+ser._nWritten]
0x18006a323  mov     r8d, edx
0x18006a326  mov     pStm, [rsp+0E8h+ser._buffer]
0x18006a32b  mov     rax, [rax+20h]
0x18006a32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a334  mov     edi, eax
0x18006a336  test    eax, eax
0x18006a338  jnz     loc_18006A2B2
0x18006a33e  mov     edx, [rsp+0E8h+ser._operationSize]
0x18006a342  sub     edx, [rsp+0E8h+ser._nWritten]
0x18006a346  mov     [rsp+0E8h+ser._operationSize], edx
0x18006a34a  mov     eax, [rsp+0E8h+ser._nWritten]
0x18006a34e  add     [rsp+0E8h+ser._buffer], rax
0x18006a353  test    edx, edx
0x18006a355  jnz     short loc_18006A312
0x18006a357  jmp     loc_18006A2B2
0x18006a35c  sub     edx, edi; BufferSize
0x18006a35e  mov     ecx, edi
0x18006a360  add     this, [rsp+0E8h+ser._buffer]; Buffer
0x18006a365  lea     riid, [rsp+0E8h+ser._handle]; pHandle
0x18006a36a  call    cs:__imp_MesDecodeBufferHandleCreate
0x18006a370  jmp     loc_18006A0F7
0x18006a375  mov     ecx, edi
0x18006a377  jmp     loc_18006A24C
0x18006a37c  sub     eax, r12d
0x18006a37f  cmp     r14d, eax
0x18006a382  ja      loc_18006A4AD
0x18006a388  mov     eax, r9d
0x18006a38b  sub     eax, [rsp+0E8h+ser._position]
0x18006a38f  cmp     r14d, eax
0x18006a392  ja      loc_18006A4AD
0x18006a398  mov     edx, r12d
0x18006a39b  add     pStm, [this+18h]; Src
0x18006a39f  mov     ecx, [rsp+0E8h+ser._position]
0x18006a3a3  add     this, [rsp+0E8h+ser._buffer]; void *
0x18006a3a8  call    memcpy_0
0x18006a3ad  mov     edx, [rsp+0E8h+ser._position]
0x18006a3b1  add     edx, r14d; dwPos
0x18006a3b4  lea     this, [rsp+0E8h+ser]; this
0x18006a3b9  call    ?SetPosition@Serializer@@QEAAJK@Z; Serializer::SetPosition(ulong)
0x18006a3be  mov     ecx, eax
0x18006a3c0  jmp     loc_18006A248
0x18006a3c5  mov     eax, ecx
0x18006a3c7  and     eax, 1FFF0000h
0x18006a3cc  cmp     eax, 10000h
0x18006a3d1  jz      loc_18006A248
0x18006a3d7  test    ecx, ecx
0x18006a3d9  jle     loc_18006A248
0x18006a3df  movzx   ecx, cx
0x18006a3e2  or      ecx, 80070000h
0x18006a3e8  jmp     loc_18006A248
0x18006a3ed  test    r13d, r13d
0x18006a3f0  jz      short loc_18006A401
0x18006a3f2  mov     this, [rsi]
0x18006a3f5  mov     rax, [this+10h]
0x18006a3f9  mov     this, rsi
0x18006a3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a401  lea     this, [rsp+0E8h+ser]; this
0x18006a406  call    ??1Serializer@@QEAA@XZ; Serializer::~Serializer(void)
0x18006a40b  mov     eax, edi
0x18006a40d  jmp     loc_18006A54E
0x18006a412  cmp     [rsi+0C8h], ebx
0x18006a418  jnz     loc_18006A014
0x18006a41e  mov     edi, ebx
  ... truncated ...
```
