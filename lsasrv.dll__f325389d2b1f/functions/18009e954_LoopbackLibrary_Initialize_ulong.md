# LoopbackLibrary::Initialize(ulong)

- ea: `0x18009e954`
- end: `0x18009eeac`
- name: `?Initialize@LoopbackLibrary@@YAJK@Z`
- size: `1368`
- prototype: `__int64 __fastcall(LoopbackLibrary *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18009d704`

## callees

- `0x180001008`
- `0x180002040`
- `0x1800766b4`
- `0x180076760`
- `0x180089740`
- `0x18009a064`
- `0x18009e954`
- `0x1800b33d8`
- `0x1800b8b58`
- `0x18012df7c`
- `0x18012dfd4`
- `0x18012e1c8`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009ea02`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009ea4b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009ea02`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009ea4b`
- `bcrypt!BCryptCreateHash` at `0x18009edd1`
- `bcrypt!BCryptCreateHash` at `0x18009edd1`
- `bcrypt!BCryptGenRandom` at `0x18009ebf3`
- `bcrypt!BCryptGenRandom` at `0x18009eca6`
- `bcrypt!BCryptGenRandom` at `0x18009ed59`
- `bcrypt!BCryptGenRandom` at `0x18009ebf3`
- `bcrypt!BCryptGenRandom` at `0x18009eca6`
- `bcrypt!BCryptGenRandom` at `0x18009ed59`
- `bcrypt!BCryptGetProperty` at `0x18009eac2`
- `bcrypt!BCryptGetProperty` at `0x18009eb16`
- `bcrypt!BCryptGetProperty` at `0x18009eac2`
- `bcrypt!BCryptGetProperty` at `0x18009eb16`

## string_xrefs

- `0x18009ea2d`: `::BCryptOpenAlgorithmProvider( &hashAlg, BCRYPT_AES_CMAC_ALGORITHM, MS_PRIMITIVE_PROVIDER, 0)`
- `0x18009ea76`: `::BCryptOpenAlgorithmProvider( &rngAlg, BCRYPT_RNG_ALGORITHM, MS_PRIMITIVE_PROVIDER, 0)`
- `0x18009eaed`: `::BCryptGetProperty( hashAlg.get(), BCRYPT_OBJECT_LENGTH, (PUCHAR)&hashHandle.m_hashDataSize, sizeof(hashHandle.m_hashDataSize), &bytesRead, 0)`
- `0x18009eb41`: `::BCryptGetProperty( hashAlg.get(), BCRYPT_HASH_LENGTH, (PUCHAR)&hashHandle.m_hashResultSize, sizeof(hashHandle.m_hashResultSize), &bytesRead, 0)`
- `0x18009edf8`: `::BCryptCreateHash( hashAlg.get(), &hashHandle, hashHandle.m_hashData, hashHandle.m_hashDataSize, randomKey.get(), hashHandle.m_hashResultSize, 0)`

## pseudocode

```c
__int64 __fastcall LoopbackLibrary::Initialize(LoopbackLibrary *this)
{
  unsigned int v1; // r15d
  __int64 v2; // rcx
  NTSTATUS v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int16 *v9; // rdx
  const char *v10; // rax
  NTSTATUS v11; // eax
  NTSTATUS Property; // eax
  NTSTATUS v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  UCHAR *v20; // rdi
  NTSTATUS v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  PUCHAR v27; // rsi
  NTSTATUS v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  PUCHAR v34; // r14
  NTSTATUS v35; // eax
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rcx
  __int16 *v39; // rdx
  const char *v40; // rax
  NTSTATUS Hash; // eax
  __int64 v42; // rcx
  unsigned int v43; // edx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-39h] BYREF
  const char *v45; // [rsp+48h] [rbp-31h] BYREF
  PUCHAR v46; // [rsp+50h] [rbp-29h] BYREF
  __int64 v47; // [rsp+58h] [rbp-21h]
  PUCHAR pbBuffer[2]; // [rsp+60h] [rbp-19h] BYREF
  PUCHAR v49; // [rsp+70h] [rbp-9h] BYREF
  __int64 v50; // [rsp+78h] [rbp-1h]
  PUCHAR pbHashObject[2]; // [rsp+80h] [rbp+7h] BYREF
  ULONG pbOutput[16]; // [rsp+90h] [rbp+17h] BYREF
  ULONG pcbResult; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v54; // [rsp+F0h] [rbp+77h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = (unsigned int)this;
  if ( (unsigned int)dword_18019A2B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x400000000001LL) )
  {
    LODWORD(v54) = LoopbackLibrary::g_trackingState;
    v45 = (const char *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v2,
      (__int64)&dword_18018057C);
  }
  if ( !LoopbackLibrary::g_trackingState )
    return 0;
  phAlgorithm = 0;
  hAlgorithm = 0;
  *(_QWORD *)pbOutput = 0;
  pcbResult = 0;
  *(_OWORD *)pbHashObject = 0;
  v4 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES-CMAC", L"Microsoft Primitive Provider", 0);
  v7 = v4;
  if ( v4 < 0 )
  {
    v8 = (unsigned int)dword_18019A2B0;
    if ( (unsigned int)dword_18019A2B0 > 5 )
    {
      LODWORD(v54) = v4;
      v9 = &word_180180546;
      v10 = "::BCryptOpenAlgorithmProvider( &hashAlg, BCRYPT_AES_CMAC_ALGORITHM, MS_PRIMITIVE_PROVIDER, 0)";
LABEL_12:
      v45 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v8,
        (__int64)v9,
        v5,
        v6,
        &v45);
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  v11 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
  v7 = v11;
  if ( v11 >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)pbOutput, 4u, &pcbResult, 0);
    v7 = Property;
    if ( Property < 0 )
    {
      v8 = (unsigned int)dword_18019A2B0;
      if ( (unsigned int)dword_18019A2B0 <= 5 )
        goto LABEL_52;
      LODWORD(v54) = Property;
      v9 = (__int16 *)&dword_1801804A4;
      v10 = "::BCryptGetProperty( hashAlg.get(), BCRYPT_OBJECT_LENGTH, (PUCHAR)&hashHandle.m_hashDataSize, sizeof(hashHan"
            "dle.m_hashDataSize), &bytesRead, 0)";
      goto LABEL_12;
    }
    v13 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&pbOutput[1], 4u, &pcbResult, 0);
    v7 = v13;
    if ( v13 < 0 )
    {
      v8 = (unsigned int)dword_18019A2B0;
      if ( (unsigned int)dword_18019A2B0 <= 5 )
        goto LABEL_52;
      LODWORD(v54) = v13;
      v9 = word_1801804DA;
      v10 = "::BCryptGetProperty( hashAlg.get(), BCRYPT_HASH_LENGTH, (PUCHAR)&hashHandle.m_hashResultSize, sizeof(hashHan"
            "dle.m_hashResultSize), &bytesRead, 0)";
      goto LABEL_12;
    }
    pbHashObject[1] = (PUCHAR)operator new[](pbOutput[0], (const struct std::nothrow_t *)std::nothrow);
    if ( !pbHashObject[1] )
    {
      if ( (unsigned int)dword_18019A2B0 > 5 )
      {
        v54 = "hashHandle.m_hashData";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v14,
          (__int64)&unk_180180440,
          v15,
          v16,
          &v54);
      }
      goto LABEL_22;
    }
    LoopbackLibrary::ByteBuffer::ByteBuffer((LoopbackLibrary::ByteBuffer *)pbBuffer, pbOutput[1]);
    v20 = pbBuffer[0];
    if ( !pbBuffer[0] )
    {
      if ( (unsigned int)dword_18019A2B0 > 5 )
      {
        v54 = "randomKey.get()";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v17,
          (__int64)word_180180472,
          v18,
          v19,
          &v54);
      }
      goto LABEL_26;
    }
    v21 = BCryptGenRandom(hAlgorithm, pbBuffer[0], pbOutput[1], 0);
    v7 = v21;
    if ( v21 < 0 )
    {
      if ( (unsigned int)dword_18019A2B0 > 5 )
      {
        LODWORD(v54) = v21;
        v45 = "::BCryptGenRandom(rngAlg.get(), randomKey.get(), hashHandle.m_hashResultSize, 0)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_18019A2B0,
          (__int64)&unk_1801803D8,
          v22,
          v23,
          &v45);
      }
      goto LABEL_30;
    }
    LoopbackLibrary::ByteBuffer::ByteBuffer((LoopbackLibrary::ByteBuffer *)&v46, pbOutput[1]);
    v27 = v46;
    if ( !v46 )
    {
      if ( (unsigned int)dword_18019A2B0 > 5 )
      {
        v54 = "clientRandom.get()";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v24,
          (__int64)&word_18018040E,
          v25,
          v26,
          &v54);
      }
LABEL_34:
      LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&v46);
LABEL_26:
      LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)pbBuffer);
LABEL_22:
      v7 = -1073741801;
      goto LABEL_52;
    }
    v28 = BCryptGenRandom(hAlgorithm, v46, pbOutput[1], 0);
    v7 = v28;
    if ( v28 < 0 )
    {
      if ( (unsigned int)dword_18019A2B0 > 5 )
      {
        LODWORD(v54) = v28;
        v45 = "::BCryptGenRandom(rngAlg.get(), clientRandom.get(), hashHandle.m_hashResultSize, 0)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_18019A2B0,
          (__int64)&unk_180180370,
          v29,
          v30,
          &v45);
      }
      goto LABEL_38;
    }
    LoopbackLibrary::ByteBuffer::ByteBuffer((LoopbackLibrary::ByteBuffer *)&v49, pbOutput[1]);
    v34 = v49;
    if ( !v49 )
    {
      if ( (unsigned int)dword_18019A2B0 > 5 )
      {
        v54 = "serverRandom.get()";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v31,
          (__int64)&word_1801803A6,
          v32,
          v33,
          &v54);
      }
      LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&v49);
      goto LABEL_34;
    }
    v35 = BCryptGenRandom(hAlgorithm, v49, pbOutput[1], 0);
    v7 = v35;
    if ( v35 >= 0 )
    {
      Hash = BCryptCreateHash(
               phAlgorithm,
               (BCRYPT_HASH_HANDLE *)pbHashObject,
               pbHashObject[1],
               pbOutput[0],
               v20,
               pbOutput[1],
               0);
      v7 = Hash;
      if ( Hash >= 0 )
      {
        LoopbackLibrary::BCryptHashHandle::operator=(v42, pbHashObject);
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&qword_1801A1638);
        qword_1801A1640 = v47;
        qword_1801A1638 = v27;
        v46 = 0;
        v47 = 0;
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&qword_1801A1648);
        qword_1801A1650 = v50;
        qword_1801A1648 = v34;
        v49 = 0;
        v50 = 0;
        LoopbackLibrary::InitializeTables((LoopbackLibrary *)v1, v43);
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&v49);
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&v46);
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)pbBuffer);
        v7 = 0;
        goto LABEL_52;
      }
      v38 = (unsigned int)dword_18019A2B0;
      if ( (unsigned int)dword_18019A2B0 <= 5 )
        goto LABEL_47;
      LODWORD(v54) = Hash;
      v39 = word_18018033A;
      v40 = "::BCryptCreateHash( hashAlg.get(), &hashHandle, hashHandle.m_hashData, hashHandle.m_hashDataSize, randomKey."
            "get(), hashHandle.m_hashResultSize, 0)";
    }
    else
    {
      v38 = (unsigned int)dword_18019A2B0;
      if ( (unsigned int)dword_18019A2B0 <= 5 )
      {
LABEL_47:
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&v49);
LABEL_38:
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)&v46);
LABEL_30:
        LoopbackLibrary::ByteBuffer::~ByteBuffer((LoopbackLibrary::ByteBuffer *)pbBuffer);
        goto LABEL_52;
      }
      LODWORD(v54) = v35;
      v39 = (__int16 *)&dword_180180304;
      v40 = "::BCryptGenRandom(rngAlg.get(), serverRandom.get(), hashHandle.m_hashResultSize, 0)";
    }
    v45 = v40;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v38,
      (__int64)v39,
      v36,
      v37,
      &v45);
    goto LABEL_47;
  }
  v8 = (unsigned int)dword_18019A2B0;
  if ( (unsigned int)dword_18019A2B0 > 5 )
  {
    LODWORD(v54) = v11;
    v9 = (__int16 *)&unk_180180510;
    v10 = "::BCryptOpenAlgorithmProvider( &rngAlg, BCRYPT_RNG_ALGORITHM, MS_PRIMITIVE_PROVIDER, 0)";
    goto LABEL_12;
  }
LABEL_52:
  LoopbackLibrary::BCryptHashHandle::~BCryptHashHandle((LoopbackLibrary::BCryptHashHandle *)pbHashObject);
  LoopbackLibrary::BCryptAlgHandle::~BCryptAlgHandle((LoopbackLibrary::BCryptAlgHandle *)&hAlgorithm);
  LoopbackLibrary::BCryptAlgHandle::~BCryptAlgHandle((LoopbackLibrary::BCryptAlgHandle *)&phAlgorithm);
  return v7;
}

```

## disassembly

```asm
0x18009e954  push    rbp
0x18009e956  push    rbx
0x18009e957  push    rsi
0x18009e958  push    rdi
0x18009e959  push    r12
0x18009e95b  push    r14
0x18009e95d  push    r15
0x18009e95f  lea     rbp, [rsp-27h]
0x18009e964  sub     rsp, 0A0h
0x18009e96b  mov     eax, cs:dword_18019A2B0
0x18009e971  xor     r12d, r12d
0x18009e974  mov     r15d, ecx
0x18009e977  cmp     eax, 5
0x18009e97a  jbe     short loc_18009E9C5
0x18009e97c  mov     rdx, 400000000001h
0x18009e986  lea     rcx, dword_18019A2B0
0x18009e98d  call    _tlgKeywordOn
0x18009e992  test    al, al
0x18009e994  jz      short loc_18009E9C5
0x18009e996  mov     eax, cs:?g_trackingState@LoopbackLibrary@@3W4TrackingState@1@A; LoopbackLibrary::TrackingState LoopbackLibrary::g_trackingState
0x18009e99c  lea     rdx, dword_18018057C
0x18009e9a3  mov     dword ptr [rbp+57h+arg_10], eax
0x18009e9a6  lea     rax, [rbp+57h+arg_10]
0x18009e9aa  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x18009e9af  lea     rax, [rbp+57h+var_88]
0x18009e9b3  mov     [rsp+0D0h+pcbResult], rax
0x18009e9b8  mov     [rbp+57h+var_88], 1000000h
0x18009e9c0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18009e9c5  cmp     cs:?g_trackingState@LoopbackLibrary@@3W4TrackingState@1@A, r12d; LoopbackLibrary::TrackingState LoopbackLibrary::g_trackingState
0x18009e9cc  jnz     short loc_18009E9D5
0x18009e9ce  xor     eax, eax
0x18009e9d0  jmp     loc_18009EE99
0x18009e9d5  xorps   xmm0, xmm0
0x18009e9d8  mov     [rbp+57h+phAlgorithm], r12
0x18009e9dc  xor     r9d, r9d; dwFlags
0x18009e9df  mov     [rbp+57h+hAlgorithm], r12
0x18009e9e3  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009e9ea  mov     qword ptr [rbp+57h+pbOutput], r12
0x18009e9ee  lea     rdx, pszAlgId; "AES-CMAC"
0x18009e9f5  mov     [rbp+57h+arg_8], r12d
0x18009e9f9  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18009e9fd  movdqu  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x18009ea02  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009ea09  nop     dword ptr [rax+rax+00h]
0x18009ea0e  mov     ebx, eax
0x18009ea10  test    eax, eax
0x18009ea12  jns     short loc_18009EA36
0x18009ea14  mov     ecx, cs:dword_18019A2B0
0x18009ea1a  cmp     ecx, 5
0x18009ea1d  jbe     loc_18009EE7C
0x18009ea23  mov     dword ptr [rbp+57h+arg_10], eax
0x18009ea26  lea     rdx, word_180180546
0x18009ea2d  lea     rax, aBcryptopenalgo_0; "::BCryptOpenAlgorithmProvider( &hashAlg"...
0x18009ea34  jmp     short loc_18009EA7D
0x18009ea36  xor     r9d, r9d; dwFlags
0x18009ea39  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009ea40  lea     rdx, aRng; "RNG"
0x18009ea47  lea     rcx, [rbp+57h+hAlgorithm]; phAlgorithm
0x18009ea4b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009ea52  nop     dword ptr [rax+rax+00h]
0x18009ea57  mov     ebx, eax
0x18009ea59  test    eax, eax
0x18009ea5b  jns     short loc_18009EA9D
0x18009ea5d  mov     ecx, cs:dword_18019A2B0
0x18009ea63  cmp     ecx, 5
0x18009ea66  jbe     loc_18009EE7C
0x18009ea6c  mov     dword ptr [rbp+57h+arg_10], eax
0x18009ea6f  lea     rdx, unk_180180510
0x18009ea76  lea     rax, aBcryptopenalgo_1; "::BCryptOpenAlgorithmProvider( &rngAlg,"...
0x18009ea7d  mov     [rbp+57h+var_88], rax
0x18009ea81  lea     rax, [rbp+57h+arg_10]
0x18009ea85  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x18009ea8a  lea     rax, [rbp+57h+var_88]
0x18009ea8e  mov     [rsp+0D0h+pcbResult], rax
0x18009ea93  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009ea98  jmp     loc_18009EE7C
0x18009ea9d  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18009eaa1  lea     rax, [rbp+57h+arg_8]
0x18009eaa5  mov     edi, 4
0x18009eaaa  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x18009eaaf  mov     r9d, edi; cbOutput
0x18009eab2  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18009eab7  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18009eabb  lea     rdx, aObjectlength; "ObjectLength"
0x18009eac2  call    cs:__imp_BCryptGetProperty
0x18009eac9  nop     dword ptr [rax+rax+00h]
0x18009eace  mov     ebx, eax
0x18009ead0  test    eax, eax
0x18009ead2  jns     short loc_18009EAF6
0x18009ead4  mov     ecx, cs:dword_18019A2B0
0x18009eada  cmp     ecx, 5
0x18009eadd  jbe     loc_18009EE7C
0x18009eae3  mov     dword ptr [rbp+57h+arg_10], eax
0x18009eae6  lea     rdx, dword_1801804A4
0x18009eaed  lea     rax, aBcryptgetprope_1; "::BCryptGetProperty( hashAlg.get(), BCR"...
0x18009eaf4  jmp     short loc_18009EA7D
0x18009eaf6  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18009eafa  lea     rax, [rbp+57h+arg_8]
0x18009eafe  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x18009eb03  lea     r8, [rbp+57h+pbOutput+4]; pbOutput
0x18009eb07  mov     r9d, edi; cbOutput
0x18009eb0a  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18009eb0f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18009eb16  call    cs:__imp_BCryptGetProperty
0x18009eb1d  nop     dword ptr [rax+rax+00h]
0x18009eb22  mov     ebx, eax
0x18009eb24  test    eax, eax
0x18009eb26  jns     short loc_18009EB4D
0x18009eb28  mov     ecx, cs:dword_18019A2B0
0x18009eb2e  cmp     ecx, 5
0x18009eb31  jbe     loc_18009EE7C
0x18009eb37  mov     dword ptr [rbp+57h+arg_10], eax
0x18009eb3a  lea     rdx, word_1801804DA
0x18009eb41  lea     rax, aBcryptgetprope_0; "::BCryptGetProperty( hashAlg.get(), BCR"...
0x18009eb48  jmp     loc_18009EA7D
0x18009eb4d  mov     ecx, [rbp+57h+pbOutput]; unsigned __int64
0x18009eb50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009eb57  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009eb5c  mov     [rbp+57h+pbHashObject+8], rax
0x18009eb60  test    rax, rax
0x18009eb63  jnz     short loc_18009EB9A
0x18009eb65  mov     eax, cs:dword_18019A2B0
0x18009eb6b  cmp     eax, 5
0x18009eb6e  jbe     short loc_18009EB90
0x18009eb70  lea     rax, aHashhandleMHas; "hashHandle.m_hashData"
0x18009eb77  mov     [rbp+57h+arg_10], rax
0x18009eb7b  lea     rdx, unk_180180440
0x18009eb82  lea     rax, [rbp+57h+arg_10]
0x18009eb86  mov     [rsp+0D0h+pcbResult], rax
0x18009eb8b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009eb90  mov     ebx, 0C0000017h
0x18009eb95  jmp     loc_18009EE7C
0x18009eb9a  mov     edx, [rbp+57h+pbOutput+4]; unsigned __int64
0x18009eb9d  lea     rcx, [rbp+57h+pbBuffer]; this
0x18009eba1  call    ??0ByteBuffer@LoopbackLibrary@@QEAA@_K@Z; LoopbackLibrary::ByteBuffer::ByteBuffer(unsigned __int64)
0x18009eba6  mov     rdi, [rbp+57h+pbBuffer]
0x18009ebaa  test    rdi, rdi
0x18009ebad  jnz     short loc_18009EBE5
0x18009ebaf  mov     eax, cs:dword_18019A2B0
0x18009ebb5  cmp     eax, 5
0x18009ebb8  jbe     short loc_18009EBDA
0x18009ebba  lea     rax, aRandomkeyGet; "randomKey.get()"
0x18009ebc1  mov     [rbp+57h+arg_10], rax
0x18009ebc5  lea     rdx, word_180180472
0x18009ebcc  lea     rax, [rbp+57h+arg_10]
0x18009ebd0  mov     [rsp+0D0h+pcbResult], rax
0x18009ebd5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009ebda  lea     rcx, [rbp+57h+pbBuffer]; this
0x18009ebde  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ebe3  jmp     short loc_18009EB90
0x18009ebe5  mov     r8d, [rbp+57h+pbOutput+4]; cbBuffer
0x18009ebe9  xor     r9d, r9d; dwFlags
0x18009ebec  mov     rcx, [rbp+57h+hAlgorithm]; hAlgorithm
0x18009ebf0  mov     rdx, rdi; pbBuffer
0x18009ebf3  call    cs:__imp_BCryptGenRandom
0x18009ebfa  nop     dword ptr [rax+rax+00h]
0x18009ebff  mov     ebx, eax
0x18009ec01  test    eax, eax
0x18009ec03  jns     short loc_18009EC4A
0x18009ec05  mov     ecx, cs:dword_18019A2B0
0x18009ec0b  cmp     ecx, 5
0x18009ec0e  jbe     short loc_18009EC3C
0x18009ec10  mov     dword ptr [rbp+57h+arg_10], eax
0x18009ec13  lea     rdx, unk_1801803D8
0x18009ec1a  lea     rax, aBcryptgenrando_2; "::BCryptGenRandom(rngAlg.get(), randomK"...
0x18009ec21  mov     [rbp+57h+var_88], rax
0x18009ec25  lea     rax, [rbp+57h+arg_10]
0x18009ec29  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x18009ec2e  lea     rax, [rbp+57h+var_88]
0x18009ec32  mov     [rsp+0D0h+pcbResult], rax
0x18009ec37  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009ec3c  lea     rcx, [rbp+57h+pbBuffer]; this
0x18009ec40  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ec45  jmp     loc_18009EE7C
0x18009ec4a  mov     edx, [rbp+57h+pbOutput+4]; unsigned __int64
0x18009ec4d  lea     rcx, [rbp+57h+var_80]; this
0x18009ec51  call    ??0ByteBuffer@LoopbackLibrary@@QEAA@_K@Z; LoopbackLibrary::ByteBuffer::ByteBuffer(unsigned __int64)
0x18009ec56  mov     rsi, [rbp+57h+var_80]
0x18009ec5a  test    rsi, rsi
0x18009ec5d  jnz     short loc_18009EC98
0x18009ec5f  mov     eax, cs:dword_18019A2B0
0x18009ec65  cmp     eax, 5
0x18009ec68  jbe     short loc_18009EC8A
0x18009ec6a  lea     rax, aClientrandomGe; "clientRandom.get()"
0x18009ec71  mov     [rbp+57h+arg_10], rax
0x18009ec75  lea     rdx, word_18018040E
0x18009ec7c  lea     rax, [rbp+57h+arg_10]
0x18009ec80  mov     [rsp+0D0h+pcbResult], rax
0x18009ec85  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009ec8a  lea     rcx, [rbp+57h+var_80]; this
0x18009ec8e  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ec93  jmp     loc_18009EBDA
0x18009ec98  mov     r8d, [rbp+57h+pbOutput+4]; cbBuffer
0x18009ec9c  xor     r9d, r9d; dwFlags
0x18009ec9f  mov     rcx, [rbp+57h+hAlgorithm]; hAlgorithm
0x18009eca3  mov     rdx, rsi; pbBuffer
0x18009eca6  call    cs:__imp_BCryptGenRandom
0x18009ecad  nop     dword ptr [rax+rax+00h]
0x18009ecb2  mov     ebx, eax
0x18009ecb4  test    eax, eax
0x18009ecb6  jns     short loc_18009ECFD
0x18009ecb8  mov     ecx, cs:dword_18019A2B0
0x18009ecbe  cmp     ecx, 5
0x18009ecc1  jbe     short loc_18009ECEF
0x18009ecc3  mov     dword ptr [rbp+57h+arg_10], eax
0x18009ecc6  lea     rdx, unk_180180370
0x18009eccd  lea     rax, aBcryptgenrando_1; "::BCryptGenRandom(rngAlg.get(), clientR"...
0x18009ecd4  mov     [rbp+57h+var_88], rax
0x18009ecd8  lea     rax, [rbp+57h+arg_10]
0x18009ecdc  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x18009ece1  lea     rax, [rbp+57h+var_88]
0x18009ece5  mov     [rsp+0D0h+pcbResult], rax
0x18009ecea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009ecef  lea     rcx, [rbp+57h+var_80]; this
0x18009ecf3  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ecf8  jmp     loc_18009EC3C
0x18009ecfd  mov     edx, [rbp+57h+pbOutput+4]; unsigned __int64
0x18009ed00  lea     rcx, [rbp+57h+var_60]; this
0x18009ed04  call    ??0ByteBuffer@LoopbackLibrary@@QEAA@_K@Z; LoopbackLibrary::ByteBuffer::ByteBuffer(unsigned __int64)
0x18009ed09  mov     r14, [rbp+57h+var_60]
0x18009ed0d  test    r14, r14
0x18009ed10  jnz     short loc_18009ED4B
0x18009ed12  mov     eax, cs:dword_18019A2B0
0x18009ed18  cmp     eax, 5
0x18009ed1b  jbe     short loc_18009ED3D
0x18009ed1d  lea     rax, aServerrandomGe; "serverRandom.get()"
0x18009ed24  mov     [rbp+57h+arg_10], rax
0x18009ed28  lea     rdx, word_1801803A6
0x18009ed2f  lea     rax, [rbp+57h+arg_10]
0x18009ed33  mov     [rsp+0D0h+pcbResult], rax
0x18009ed38  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009ed3d  lea     rcx, [rbp+57h+var_60]; this
0x18009ed41  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ed46  jmp     loc_18009EC8A
0x18009ed4b  mov     r8d, [rbp+57h+pbOutput+4]; cbBuffer
0x18009ed4f  xor     r9d, r9d; dwFlags
0x18009ed52  mov     rcx, [rbp+57h+hAlgorithm]; hAlgorithm
0x18009ed56  mov     rdx, r14; pbBuffer
0x18009ed59  call    cs:__imp_BCryptGenRandom
0x18009ed60  nop     dword ptr [rax+rax+00h]
0x18009ed65  mov     ebx, eax
0x18009ed67  test    eax, eax
0x18009ed69  jns     short loc_18009EDB0
0x18009ed6b  mov     ecx, cs:dword_18019A2B0
0x18009ed71  cmp     ecx, 5
0x18009ed74  jbe     short loc_18009EDA2
0x18009ed76  mov     dword ptr [rbp+57h+arg_10], eax
0x18009ed79  lea     rdx, dword_180180304
0x18009ed80  lea     rax, aBcryptgenrando_0; "::BCryptGenRandom(rngAlg.get(), serverR"...
0x18009ed87  mov     [rbp+57h+var_88], rax
0x18009ed8b  lea     rax, [rbp+57h+arg_10]
0x18009ed8f  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x18009ed94  lea     rax, [rbp+57h+var_88]
0x18009ed98  mov     [rsp+0D0h+pcbResult], rax
0x18009ed9d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009eda2  lea     rcx, [rbp+57h+var_60]; this
0x18009eda6  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009edab  jmp     loc_18009ECEF
0x18009edb0  mov     eax, [rbp+57h+pbOutput+4]
0x18009edb3  lea     rdx, [rbp+57h+pbHashObject]; phHash
0x18009edb7  mov     r9d, [rbp+57h+pbOutput]; cbHashObject
0x18009edbb  mov     r8, [rbp+57h+pbHashObject+8]; pbHashObject
0x18009edbf  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18009edc3  mov     [rsp+0D0h+var_A0], r12d; dwFlags
0x18009edc8  mov     [rsp+0D0h+dwFlags], eax; cbSecret
0x18009edcc  mov     [rsp+0D0h+pcbResult], rdi; pbSecret
0x18009edd1  call    cs:__imp_BCryptCreateHash
0x18009edd8  nop     dword ptr [rax+rax+00h]
0x18009eddd  mov     ebx, eax
0x18009eddf  test    eax, eax
0x18009ede1  jns     short loc_18009EE01
0x18009ede3  mov     ecx, cs:dword_18019A2B0
0x18009ede9  cmp     ecx, 5
0x18009edec  jbe     short loc_18009EDA2
0x18009edee  mov     dword ptr [rbp+57h+arg_10], eax
0x18009edf1  lea     rdx, word_18018033A
0x18009edf8  lea     rax, aBcryptcreateha_0; "::BCryptCreateHash( hashAlg.get(), &has"...
0x18009edff  jmp     short loc_18009ED87
0x18009ee01  lea     rdx, [rbp+57h+pbHashObject]
0x18009ee05  call    ??4BCryptHashHandle@LoopbackLibrary@@QEAAAEAU01@$$QEAU01@@Z; LoopbackLibrary::BCryptHashHandle::operator=(LoopbackLibrary::BCryptHashHandle &&)
0x18009ee0a  lea     rcx, qword_1801A1638; this
0x18009ee11  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ee16  mov     rax, [rbp+57h+var_78]
0x18009ee1a  lea     rcx, qword_1801A1648; this
0x18009ee21  mov     cs:qword_1801A1640, rax
0x18009ee28  mov     cs:qword_1801A1638, rsi
0x18009ee2f  mov     [rbp+57h+var_80], r12
0x18009ee33  mov     [rbp+57h+var_78], r12
0x18009ee37  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ee3c  mov     rax, [rbp+57h+var_58]
0x18009ee40  mov     ecx, r15d; this
0x18009ee43  mov     cs:qword_1801A1650, rax
0x18009ee4a  mov     cs:qword_1801A1648, r14
0x18009ee51  mov     [rbp+57h+var_60], r12
0x18009ee55  mov     [rbp+57h+var_58], r12
0x18009ee59  call    ?InitializeTables@LoopbackLibrary@@YA_NK@Z; LoopbackLibrary::InitializeTables(ulong)
0x18009ee5e  lea     rcx, [rbp+57h+var_60]; this
0x18009ee62  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
0x18009ee67  lea     rcx, [rbp+57h+var_80]; this
0x18009ee6b  call    ??1ByteBuffer@LoopbackLibrary@@QEAA@XZ; LoopbackLibrary::ByteBuffer::~ByteBuffer(void)
  ... truncated ...
```
