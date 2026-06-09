# CFile::CFile(CJob *,BG_JOB_TYPE,GenericStringHandle<ushort>,GenericStringHandle<ushort>,std::unique_ptr<CRangeCollection,std::default_delete<CRangeCollection>>,IUnknown *)

- ea: `0x18002887c`
- end: `0x180028d58`
- name: `??0CFile@@QEAA@PEAVCJob@@W4BG_JOB_TYPE@@V?$GenericStringHandle@G@@2V?$unique_ptr@VCRangeCollection@@U?$default_delete@VCRangeCollection@@@std@@@std@@PEAUIUnknown@@@Z`
- size: `1244`
- prototype: `CFile *__fastcall(CFile *this, CJob *, enum BG_JOB_TYPE, void **, void **, CRangeCollection **, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180016ee0`
- `0x18008abdc`
- `0x18008b9cc`
- `0x1800cbd90`

## callees

- `0x18001fe28`
- `0x18001ff00`
- `0x180023138`
- `0x18002887c`
- `0x180028d60`
- `0x18002a660`
- `0x18008df60`
- `0x180094de8`
- `0x1800956ec`
- `0x1800a3444`
- `0x1800a5e18`
- `0x1800d13f4`
- `0x1800eeba4`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289be`
- `RPCRT4!UuidCreate` at `0x1800289a0`
- `RPCRT4!UuidCreate` at `0x1800289a0`
- `ext-ms-win-connectionattribution-api-l1-1-0!AttributeComBrokeredConnection` at `0x180028ca1`
- `ext-ms-win-connectionattribution-api-l1-1-0!AttributeComBrokeredConnection` at `0x180028ca1`

## string_xrefs

- `0x180028c9a`: `BITS Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
CFile *__fastcall CFile::CFile(
        CFile *this,
        CJob *a2,
        enum BG_JOB_TYPE a3,
        void **a4,
        void **a5,
        CRangeCollection **a6,
        __int64 a7)
{
  RangeTracker *v10; // r12
  CRangeCollection *v11; // rax
  UUID v12; // xmm0
  __int64 v13; // rdx
  unsigned int LastError; // ecx
  void *v15; // r15
  __int64 v16; // rcx
  void *v17; // r15
  __int64 v18; // rcx
  bool v19; // zf
  char v20; // al
  unsigned __int8 *v21; // r14
  int ProtocolType; // r14d
  int v23; // ecx
  __int64 v24; // rax
  __int64 v25; // rax
  char v26; // r14
  int v27; // eax
  unsigned int v28; // edx
  void **pExceptionObject; // [rsp+30h] [rbp-91h] BYREF
  __int128 v32; // [rsp+38h] [rbp-89h]
  int v33; // [rsp+48h] [rbp-79h]
  int v34; // [rsp+4Ch] [rbp-75h]
  int v35; // [rsp+50h] [rbp-71h]
  CRangeCollection **v36; // [rsp+90h] [rbp-31h]
  UUID Uuid; // [rsp+A0h] [rbp-21h] BYREF
  CFile *v38; // [rsp+B0h] [rbp-11h]
  void **v39; // [rsp+B8h] [rbp-9h]
  void **v40; // [rsp+C0h] [rbp-1h]
  CRangeCollection **v41; // [rsp+C8h] [rbp+7h]

  v38 = this;
  v39 = a4;
  v40 = a5;
  v36 = a6;
  v41 = a6;
  *(_QWORD *)this = &CFile::`vftable';
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)this + 1) = &GenericStringHandle<unsigned short>::s_EmptyString;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)this + 2) = &GenericStringHandle<unsigned short>::s_EmptyString;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)this + 3) = &GenericStringHandle<unsigned short>::s_EmptyString;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v10 = (CFile *)((char *)this + 96);
  RangeTracker::RangeTracker((CFile *)((char *)this + 96));
  *((_WORD *)this + 129) = 0;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)this + 34) = &GenericStringHandle<unsigned short>::s_EmptyString;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)this + 35) = &GenericStringHandle<unsigned short>::s_EmptyString;
  v11 = *a6;
  *a6 = 0;
  *((_QWORD *)this + 39) = v11;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_DWORD *)this + 87) = 0;
  v12 = 0;
  *((_OWORD *)this + 22) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *(double *)&v12.Data1 = std::wstring::_Construct_empty((char *)this + 352);
  *((_QWORD *)this + 50) = v13;
  *((_BYTE *)this + 408) = v13;
  Uuid = v12;
  if ( UuidCreate(&Uuid) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = LastError;
    v34 = 1475;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
  *((UUID *)this + 24) = Uuid;
  *((_QWORD *)this + 33) = a2;
  _InterlockedIncrement((volatile signed __int32 *)*a4 + 2);
  v15 = *a4;
  v16 = *((_QWORD *)this + 1);
  if ( v16 && _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 8), 0xFFFFFFFF) == 1 )
    operator delete(*((void **)this + 1), 0x10u);
  *((_QWORD *)this + 1) = v15;
  _InterlockedIncrement((volatile signed __int32 *)*a5 + 2);
  v17 = *a5;
  v18 = *((_QWORD *)this + 2);
  if ( v18 && _InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 8), 0xFFFFFFFF) == 1 )
    operator delete(*((void **)this + 2), 0x10u);
  *((_QWORD *)this + 2) = v17;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_BYTE *)this + 88) = *((_DWORD *)g_GlobalInfo + 55) == 1;
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 7) = -1;
  *((_WORD *)this + 128) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 74) = 128;
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 89) = 0;
  *((_WORD *)this + 172) = 0;
  *((_BYTE *)this + 346) = 0;
  if ( *((_BYTE *)a2 + 936) || (v19 = !CJob::IsOwnedByAppContainerPackage(a2), v20 = 0, !v19) )
    v20 = 1;
  *((_BYTE *)this + 260) = v20;
  if ( !*(_DWORD *)(*((_QWORD *)this + 33) + 664LL) && !*((_QWORD *)this + 39) )
    RangeTracker::SetActive(v10, 1);
  v21 = (unsigned __int8 *)*a4 + 12;
  if ( *a4 == (void *)-12LL || !(unsigned __int8)URLParser::ParseURLW((unsigned __int16 *)*a4 + 6) )
    goto LABEL_50;
  ProtocolType = GetProtocolType(v21);
  if ( ProtocolType == 3 )
    RangeTracker::SetActive(v10, 0);
  if ( *(_DWORD *)(*((_QWORD *)this + 33) + 664LL) == 2 && (unsigned int)(ProtocolType - 3) <= 1
    || *((_QWORD *)this + 39) && (unsigned int)(ProtocolType - 3) <= 1 )
  {
LABEL_50:
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = -2147024809;
    v34 = 652;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v23 = CFile::VerifyLocalName((union _LARGE_INTEGER *)this, (const unsigned __int16 *)*a5 + 6, a3);
  if ( v23 < 0 )
  {
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = v23;
    v34 = 655;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v24 = *((_QWORD *)this + 39);
  if ( v24 )
    *((_QWORD *)this + 8) = *(_QWORD *)(v24 + 8);
  v25 = *((_QWORD *)this + 33);
  v26 = *(_BYTE *)(v25 + 1284);
  if ( (*(_BYTE *)(v25 + 804) & 0x20) != 0 || v26 == 1 )
  {
    *((_BYTE *)this + 345) = 1;
    CFile::TriggerSerialization(this, 1);
    if ( v26 == 1 )
      RangeTracker::SetOnDemand(v10, 1);
  }
  v27 = CFile::TriggerSerialization(this, 0);
  if ( v27 < 0 )
  {
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = v27;
    v34 = 682;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
  if ( (unsigned __int8)IsAttributeComBrokeredConnectionPresent((unsigned int)v27) && a7 )
    AttributeComBrokeredConnection(L"BITS Service", *((_QWORD *)this + 1) + 12LL, a7, &word_18011AC70, 0);
  if ( *a4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a4 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a4, 0x10u);
    *a4 = 0;
  }
  if ( *a5 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a5 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a5, 0x10u);
    *a5 = 0;
  }
  if ( *v36 )
    CRangeCollection::`scalar deleting destructor'(*v36, v28);
  return this;
}

```

## disassembly

```asm
0x18002887c  mov     [rsp-8+arg_8], rbx
0x180028881  push    rbp
0x180028882  push    rsi
0x180028883  push    rdi
0x180028884  push    r12
0x180028886  push    r13
0x180028888  push    r14
0x18002888a  push    r15
0x18002888c  lea     rbp, [rsp-0Fh]
0x180028891  sub     rsp, 0D0h
0x180028898  mov     rdi, r9
0x18002889b  mov     [rsp+100h+var_D8], r8d
0x1800288a0  mov     r14, rdx
0x1800288a3  mov     rbx, rcx
0x1800288a6  mov     [rbp+3Fh+var_50], rcx
0x1800288aa  mov     [rbp+3Fh+var_48], r9
0x1800288ae  mov     rsi, [rbp+3Fh+arg_20]
0x1800288b2  mov     [rbp+3Fh+var_40], rsi
0x1800288b6  mov     r15, [rbp+3Fh+arg_28]
0x1800288ba  mov     [rbp+3Fh+var_70], r15
0x1800288be  mov     [rbp+3Fh+var_38], r15
0x1800288c2  mov     r13, [rbp+3Fh+arg_30]
0x1800288c6  lea     rax, ??_7CFile@@6B@; const CFile::`vftable'
0x1800288cd  mov     [rcx], rax
0x1800288d0  lock inc cs:dword_180145058
0x1800288d7  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x1800288de  mov     [rcx+8], rax
0x1800288e2  lock inc cs:dword_180145058
0x1800288e9  mov     [rcx+10h], rax
0x1800288ed  lock inc cs:dword_180145058
0x1800288f4  mov     [rcx+18h], rax
0x1800288f8  mov     qword ptr [rcx+20h], 0
0x180028900  mov     qword ptr [rcx+28h], 0
0x180028908  lea     r12, [rcx+60h]
0x18002890c  mov     rcx, r12; this
0x18002890f  call    ??0RangeTracker@@QEAA@XZ; RangeTracker::RangeTracker(void)
0x180028914  nop
0x180028915  xor     edx, edx
0x180028917  mov     [rbx+102h], dx
0x18002891e  lock inc cs:dword_180145058
0x180028925  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18002892c  mov     [rbx+110h], rax
0x180028933  lock inc cs:dword_180145058
0x18002893a  mov     [rbx+118h], rax
0x180028941  mov     rax, [r15]
0x180028944  mov     [r15], rdx
0x180028947  mov     [rbx+138h], rax
0x18002894e  mov     [rbx+140h], rdx
0x180028955  mov     [rbx+148h], rdx
0x18002895c  mov     [rbx+150h], rdx
0x180028963  mov     [rbx+15Ch], edx
0x180028969  lea     rcx, [rbx+160h]
0x180028970  xorps   xmm0, xmm0
0x180028973  movups  xmmword ptr [rcx], xmm0
0x180028976  mov     [rcx+10h], rdx
0x18002897a  mov     [rcx+18h], rdx
0x18002897e  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180028983  nop
0x180028984  mov     [rsp+100h+var_E0], rdx
0x180028989  mov     eax, edx
0x18002898b  mov     [rbx+190h], rdx
0x180028992  mov     [rbx+198h], dl
0x180028998  movups  xmmword ptr [rbp+3Fh+Uuid.Data1], xmm0
0x18002899c  lea     rcx, [rbp+3Fh+Uuid]; Uuid
0x1800289a0  call    cs:__imp_UuidCreate
0x1800289a6  test    eax, eax
0x1800289a8  jz      short loc_180028A04
0x1800289aa  call    cs:__imp_GetLastError
0x1800289b0  test    eax, eax
0x1800289b2  jg      short loc_1800289BE
0x1800289b4  call    cs:__imp_GetLastError
0x1800289ba  mov     ecx, eax
0x1800289bc  jmp     short loc_1800289CD
0x1800289be  call    cs:__imp_GetLastError
0x1800289c4  movzx   ecx, ax
0x1800289c7  or      ecx, 80070000h
0x1800289cd  xorps   xmm0, xmm0
0x1800289d0  movups  [rsp+100h+var_C8], xmm0
0x1800289d5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800289dc  mov     [rsp+100h+pExceptionObject], rax
0x1800289e1  mov     [rbp+3Fh+var_B8], ecx
0x1800289e4  mov     [rbp+3Fh+var_B4], 5C3h
0x1800289eb  mov     [rbp+3Fh+var_B0], 1
0x1800289f2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800289f9  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x1800289fe  call    _CxxThrowException_0
0x180028a04  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x180028a08  movdqu  xmmword ptr [rbx+180h], xmm0
0x180028a10  mov     [rbx+108h], r14
0x180028a17  mov     rax, [rdi]
0x180028a1a  lock inc dword ptr [rax+8]
0x180028a1e  mov     r15, [rdi]
0x180028a21  mov     rcx, [rbx+8]
0x180028a25  test    rcx, rcx
0x180028a28  jz      short loc_180028A43
0x180028a2a  or      eax, 0FFFFFFFFh
0x180028a2d  lock xadd [rcx+8], eax
0x180028a32  cmp     eax, 1
0x180028a35  jnz     short loc_180028A43
0x180028a37  lea     edx, [rax+0Fh]; unsigned __int64
0x180028a3a  mov     rcx, [rbx+8]; void *
0x180028a3e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028a43  mov     [rbx+8], r15
0x180028a47  mov     rax, [rsi]
0x180028a4a  lock inc dword ptr [rax+8]
0x180028a4e  mov     r15, [rsi]
0x180028a51  mov     rcx, [rbx+10h]
0x180028a55  test    rcx, rcx
0x180028a58  jz      short loc_180028A73
0x180028a5a  or      eax, 0FFFFFFFFh
0x180028a5d  lock xadd [rcx+8], eax
0x180028a62  cmp     eax, 1
0x180028a65  jnz     short loc_180028A73
0x180028a67  lea     edx, [rax+0Fh]; unsigned __int64
0x180028a6a  mov     rcx, [rbx+10h]; void *
0x180028a6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028a73  mov     [rbx+10h], r15
0x180028a77  xor     r15d, r15d
0x180028a7a  mov     [rbx+48h], r15
0x180028a7e  mov     [rbx+50h], r15
0x180028a82  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180028a89  cmp     dword ptr [rax+0DCh], 1
0x180028a90  setz    al
0x180028a93  mov     [rbx+58h], al
0x180028a96  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028a9a  mov     [rbx+40h], rax
0x180028a9e  mov     [rbx+38h], rax
0x180028aa2  mov     [rbx+100h], r15w
0x180028aaa  mov     [rsp+100h+var_E0], r15
0x180028aaf  mov     eax, r15d
0x180028ab2  mov     [rbx+30h], rax
0x180028ab6  mov     dword ptr [rbx+128h], 80h
0x180028ac0  mov     [rbx+130h], r15
0x180028ac7  mov     [rbx+59h], r15b
0x180028acb  mov     [rbx+158h], r15w
0x180028ad3  mov     [rbx+15Ah], r15b
0x180028ada  cmp     [r14+3A8h], r15b
0x180028ae1  jnz     short loc_180028AF2
0x180028ae3  mov     rcx, r14; this
0x180028ae6  call    ?IsOwnedByAppContainerPackage@CJob@@QEBA_NXZ; CJob::IsOwnedByAppContainerPackage(void)
0x180028aeb  test    al, al
0x180028aed  mov     al, r15b
0x180028af0  jz      short loc_180028AF4
0x180028af2  mov     al, 1
0x180028af4  mov     [rbx+104h], al
0x180028afa  mov     rax, [rbx+108h]
0x180028b01  cmp     [rax+298h], r15d
0x180028b08  jnz     short loc_180028B1D
0x180028b0a  cmp     [rbx+138h], r15
0x180028b11  jnz     short loc_180028B1D
0x180028b13  mov     dl, 1; bool
0x180028b15  mov     rcx, r12; this
0x180028b18  call    ?SetActive@RangeTracker@@QEAAX_N@Z; RangeTracker::SetActive(bool)
0x180028b1d  mov     r14, [rdi]
0x180028b20  add     r14, 0Ch
0x180028b24  jz      loc_180028D1D
0x180028b2a  xor     r8d, r8d
0x180028b2d  xor     edx, edx
0x180028b2f  mov     rcx, r14; unsigned __int16 *
0x180028b32  call    ?ParseURLW@URLParser@@CA_NPEBGPEAV?$GenericStringHandle@G@@1@Z; URLParser::ParseURLW(ushort const *,GenericStringHandle<ushort> *,GenericStringHandle<ushort> *)
0x180028b37  test    al, al
0x180028b39  jz      loc_180028D1D
0x180028b3f  mov     rcx, r14
0x180028b42  call    ?GetProtocolType@@YA?AW4PROTOCOL_TYPE@@PEBG@Z; GetProtocolType(ushort const *)
0x180028b47  mov     r14d, eax
0x180028b4a  cmp     eax, 3
0x180028b4d  jnz     short loc_180028B59
0x180028b4f  xor     edx, edx; bool
0x180028b51  mov     rcx, r12; this
0x180028b54  call    ?SetActive@RangeTracker@@QEAAX_N@Z; RangeTracker::SetActive(bool)
0x180028b59  mov     rcx, [rbx+108h]
0x180028b60  cmp     dword ptr [rcx+298h], 2
0x180028b67  jnz     short loc_180028B76
0x180028b69  lea     ecx, [r14-3]
0x180028b6d  cmp     ecx, 1
0x180028b70  jbe     loc_180028D1D
0x180028b76  cmp     [rbx+138h], r15
0x180028b7d  jz      short loc_180028B8C
0x180028b7f  lea     eax, [r14-3]
0x180028b83  cmp     eax, 1
0x180028b86  jbe     loc_180028D1D
0x180028b8c  mov     rdx, [rsi]
0x180028b8f  add     rdx, 0Ch; unsigned __int16 *
0x180028b93  mov     r8d, [rsp+100h+var_D8]; enum BG_JOB_TYPE
0x180028b98  mov     rcx, rbx; this
0x180028b9b  call    ?VerifyLocalName@CFile@@QEAAJPEBGW4BG_JOB_TYPE@@@Z; CFile::VerifyLocalName(ushort const *,BG_JOB_TYPE)
0x180028ba0  mov     ecx, eax
0x180028ba2  test    eax, eax
0x180028ba4  jns     short loc_180028BDD
0x180028ba6  xorps   xmm0, xmm0
0x180028ba9  movups  [rsp+100h+var_C8], xmm0
0x180028bae  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180028bb5  mov     [rsp+100h+pExceptionObject], rax
0x180028bba  mov     [rbp+3Fh+var_B8], ecx
0x180028bbd  mov     [rbp+3Fh+var_B4], 28Fh
0x180028bc4  mov     [rbp+3Fh+var_B0], 1
0x180028bcb  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180028bd2  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x180028bd7  call    _CxxThrowException_0
0x180028bdd  mov     rax, [rbx+138h]
0x180028be4  test    rax, rax
0x180028be7  jz      short loc_180028BF1
0x180028be9  mov     rax, [rax+8]
0x180028bed  mov     [rbx+40h], rax
0x180028bf1  mov     rax, [rbx+108h]
0x180028bf8  mov     r14b, [rax+504h]
0x180028bff  test    byte ptr [rax+324h], 20h
0x180028c06  jnz     short loc_180028C0E
0x180028c08  cmp     r14b, 1
0x180028c0c  jnz     short loc_180028C33
0x180028c0e  mov     byte ptr [rbx+159h], 1
0x180028c15  mov     edx, 1
0x180028c1a  mov     rcx, rbx
0x180028c1d  call    ?TriggerSerialization@CFile@@QEAAJW4SerializationBehavior@1@@Z; CFile::TriggerSerialization(CFile::SerializationBehavior)
0x180028c22  cmp     r14b, 1
0x180028c26  jnz     short loc_180028C33
0x180028c28  mov     dl, r14b; bool
0x180028c2b  mov     rcx, r12; this
0x180028c2e  call    ?SetOnDemand@RangeTracker@@QEAAX_N@Z; RangeTracker::SetOnDemand(bool)
0x180028c33  xor     edx, edx
0x180028c35  mov     rcx, rbx
0x180028c38  call    ?TriggerSerialization@CFile@@QEAAJW4SerializationBehavior@1@@Z; CFile::TriggerSerialization(CFile::SerializationBehavior)
0x180028c3d  mov     ecx, eax
0x180028c3f  test    eax, eax
0x180028c41  jns     short loc_180028C7A
0x180028c43  xorps   xmm0, xmm0
0x180028c46  movups  [rsp+100h+var_C8], xmm0
0x180028c4b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180028c52  mov     [rsp+100h+pExceptionObject], rax
0x180028c57  mov     [rbp+3Fh+var_B8], ecx
0x180028c5a  mov     [rbp+3Fh+var_B4], 2AAh
0x180028c61  mov     [rbp+3Fh+var_B0], 1
0x180028c68  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180028c6f  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x180028c74  call    _CxxThrowException_0
0x180028c7a  call    IsAttributeComBrokeredConnectionPresent
0x180028c7f  test    al, al
0x180028c81  jz      short loc_180028CA8
0x180028c83  test    r13, r13
0x180028c86  jz      short loc_180028CA8
0x180028c88  mov     rdx, [rbx+8]
0x180028c8c  add     rdx, 0Ch
0x180028c90  lea     r9, word_18011AC70
0x180028c97  mov     r8, r13
0x180028c9a  lea     rcx, aBitsService; "BITS Service"
0x180028ca1  call    cs:__imp_AttributeComBrokeredConnection
0x180028ca7  nop
0x180028ca8  mov     rcx, [rdi]
0x180028cab  test    rcx, rcx
0x180028cae  jz      short loc_180028CCB
0x180028cb0  or      eax, 0FFFFFFFFh
0x180028cb3  lock xadd [rcx+8], eax
0x180028cb8  cmp     eax, 1
0x180028cbb  jnz     short loc_180028CC8
0x180028cbd  lea     edx, [rax+0Fh]; unsigned __int64
0x180028cc0  mov     rcx, [rdi]; void *
0x180028cc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028cc8  mov     [rdi], r15
0x180028ccb  mov     rcx, [rsi]
0x180028cce  test    rcx, rcx
0x180028cd1  jz      short loc_180028CEE
0x180028cd3  or      eax, 0FFFFFFFFh
0x180028cd6  lock xadd [rcx+8], eax
0x180028cdb  cmp     eax, 1
0x180028cde  jnz     short loc_180028CEB
0x180028ce0  lea     edx, [rax+0Fh]; unsigned __int64
0x180028ce3  mov     rcx, [rsi]; void *
0x180028ce6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028ceb  mov     [rsi], r15
0x180028cee  mov     rcx, [rbp+3Fh+var_70]
0x180028cf2  mov     rcx, [rcx]; this
0x180028cf5  test    rcx, rcx
0x180028cf8  jz      short loc_180028CFF
0x180028cfa  call    ??_GCRangeCollection@@QEAAPEAXI@Z; CRangeCollection::`scalar deleting destructor'(uint)
0x180028cff  mov     rax, rbx
0x180028d02  mov     rbx, [rsp+100h+arg_8]
0x180028d0a  add     rsp, 0D0h
0x180028d11  pop     r15
0x180028d13  pop     r14
0x180028d15  pop     r13
0x180028d17  pop     r12
0x180028d19  pop     rdi
0x180028d1a  pop     rsi
0x180028d1b  pop     rbp
0x180028d1c  retn
0x180028d1d  xorps   xmm0, xmm0
0x180028d20  movups  [rsp+100h+var_C8], xmm0
0x180028d25  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180028d2c  mov     [rsp+100h+pExceptionObject], rax
0x180028d31  mov     [rbp+3Fh+var_B8], 80070057h
0x180028d38  mov     [rbp+3Fh+var_B4], 28Ch
0x180028d3f  mov     [rbp+3Fh+var_B0], 1
0x180028d46  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180028d4d  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x180028d52  call    _CxxThrowException_0
```
