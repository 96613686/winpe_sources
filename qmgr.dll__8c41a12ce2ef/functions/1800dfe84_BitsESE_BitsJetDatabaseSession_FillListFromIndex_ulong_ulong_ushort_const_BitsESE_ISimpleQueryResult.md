# BitsESE::BitsJetDatabaseSession::FillListFromIndex(ulong,ulong,ushort const *,BitsESE::ISimpleQueryResult *)

- ea: `0x1800dfe84`
- end: `0x1800e0327`
- name: `?FillListFromIndex@BitsJetDatabaseSession@BitsESE@@AEAAJKKPEBGPEAVISimpleQueryResult@2@@Z`
- size: `1187`
- prototype: `__int64 __fastcall(BitsESE::BitsJetDatabaseSession *__hidden this, unsigned int, unsigned int, JET_PCWSTR szIndexName, struct BitsESE::ISimpleQueryResult *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e0440`

## callees

- `0x18002931c`
- `0x18002c6e0`
- `0x1800407d0`
- `0x18004905c`
- `0x18007ac00`
- `0x18007b838`
- `0x180087f90`
- `0x18009c0b4`
- `0x1800df410`
- `0x1800dfe84`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e023a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e023a`
- `ESENT!JetSetCurrentIndexW` at `0x1800dfeef`
- `ESENT!JetSetCurrentIndexW` at `0x1800dfeef`
- `ESENT!JetRetrieveColumn` at `0x1800dffda`
- `ESENT!JetRetrieveColumn` at `0x1800e00db`
- `ESENT!JetRetrieveColumn` at `0x1800dffda`
- `ESENT!JetRetrieveColumn` at `0x1800e00db`
- `ESENT!JetMove` at `0x1800dff89`
- `ESENT!JetMove` at `0x1800e0258`
- `ESENT!JetMove` at `0x1800dff89`
- `ESENT!JetMove` at `0x1800e0258`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BitsESE::BitsJetDatabaseSession::FillListFromIndex(
        JET_SESID *this,
        unsigned int a2,
        unsigned int a3,
        JET_PCWSTR szIndexName,
        struct BitsESE::ISimpleQueryResult *a5)
{
  __int64 v7; // r11
  JET_TABLEID v8; // r14
  JET_COLUMNID v9; // r12d
  const struct BitsESE::PersistentFieldMapping *PersistentFieldMapping; // rax
  const struct BitsESE::PersistentFieldMapping *v11; // r13
  JET_ERR v12; // eax
  int v13; // ebx
  JET_ERR v14; // eax
  struct BitsESE::ISimpleQueryResult *v15; // r15
  JET_ERR Column; // eax
  int v17; // esi
  unsigned int v18; // eax
  JET_ERR v19; // eax
  int v20; // esi
  int v21; // ecx
  int v22; // ecx
  int v23; // edi
  __int64 result; // rax
  const ComError *v25; // rbx
  int v26; // [rsp+40h] [rbp-2B8h] BYREF
  const ComError *v27; // [rsp+48h] [rbp-2B0h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+50h] [rbp-2A8h] BYREF
  _BYTE v29[16]; // [rsp+68h] [rbp-290h] BYREF
  void *pvData[3]; // [rsp+78h] [rbp-280h] BYREF
  void **pExceptionObject; // [rsp+90h] [rbp-268h] BYREF
  __int128 v32; // [rsp+98h] [rbp-260h]
  int v33; // [rsp+A8h] [rbp-250h]
  int v34; // [rsp+ACh] [rbp-24Ch]
  int v35; // [rsp+B0h] [rbp-248h]
  void **v36; // [rsp+F0h] [rbp-208h] BYREF
  __int128 v37; // [rsp+F8h] [rbp-200h]
  int v38; // [rsp+108h] [rbp-1F0h]
  int v39; // [rsp+10Ch] [rbp-1ECh]
  int v40; // [rsp+110h] [rbp-1E8h]
  void **v41; // [rsp+150h] [rbp-1A8h] BYREF
  __int128 v42; // [rsp+158h] [rbp-1A0h]
  int v43; // [rsp+168h] [rbp-190h]
  int v44; // [rsp+16Ch] [rbp-18Ch]
  int v45; // [rsp+170h] [rbp-188h]
  void **v46; // [rsp+1B0h] [rbp-148h] BYREF
  __int128 v47; // [rsp+1B8h] [rbp-140h]
  int v48; // [rsp+1C8h] [rbp-130h]
  int v49; // [rsp+1CCh] [rbp-12Ch]
  int v50; // [rsp+1D0h] [rbp-128h]
  void **v51; // [rsp+210h] [rbp-E8h] BYREF
  __int128 v52; // [rsp+218h] [rbp-E0h]
  int v53; // [rsp+228h] [rbp-D0h]
  int v54; // [rsp+22Ch] [rbp-CCh]
  int v55; // [rsp+230h] [rbp-C8h]
  void **v56; // [rsp+270h] [rbp-88h] BYREF
  __int128 v57; // [rsp+278h] [rbp-80h]
  int v58; // [rsp+288h] [rbp-70h]
  int v59; // [rsp+28Ch] [rbp-6Ch]
  int v60; // [rsp+290h] [rbp-68h]
  size_t Size; // [rsp+308h] [rbp+10h] BYREF
  int v62; // [rsp+310h] [rbp+18h] BYREF

  v7 = 56LL * a2;
  v8 = *(_QWORD *)((char *)&unk_180144200 + v7 + 48);
  v9 = *(_DWORD *)(*(_QWORD *)((char *)&unk_180144200 + v7 + 16) + 48LL * a3 + 24);
  PersistentFieldMapping = BitsESE::BitsJetDatabaseSession::GetPersistentFieldMapping(a2, a3);
  v11 = PersistentFieldMapping;
  try
  {
    BitsESE::ScopedBitsDatabaseSessionTransaction::ScopedBitsDatabaseSessionTransaction(
      (BitsESE::ScopedBitsDatabaseSessionTransaction *)v29,
      (struct BitsESE::IBitsDatabaseSession *)this);
    v12 = JetSetCurrentIndexW(this[3], v8, szIndexName);
    v13 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v12);
    LODWORD(Size) = v13;
    if ( v13 < 0 )
    {
      v62 = 972;
      CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
        "BitsESE::BitsJetDatabaseSession::FillListFromIndex",
        &v62,
        &Size);
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v13;
      v34 = 972;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v14 = JetMove(this[3], v8, 0x80000000, 0);
    v15 = a5;
    while ( !v14 )
    {
      LODWORD(Size) = 0;
      Column = JetRetrieveColumn(this[3], v8, v9, 0, 0, (unsigned int *)&Size, 0, 0);
      if ( Column )
      {
        if ( Column != -1047 && Column != 1006 && Column != -1038 && Column != 1004 )
        {
          v17 = BitsESE::BitsJetDatabaseSession::JetErrToHR(Column);
          v62 = v17;
          if ( v17 < 0 )
          {
            v26 = 998;
            CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
              "BitsESE::BitsJetDatabaseSession::FillListFromIndex",
              &v26,
              &v62);
            v37 = 0;
            v36 = &ComError::`vftable';
            v38 = v17;
            v39 = 998;
            v40 = 1;
            throw (ComError *)&v36;
          }
        }
      }
      std::vector<unsigned char>::vector<unsigned char>(pvData, (unsigned int)Size);
      v18 = Size;
      if ( (_DWORD)Size )
      {
        v19 = JetRetrieveColumn(this[3], v8, v9, pvData[0], Size, (unsigned int *)&Size, 0, 0);
        v20 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v19);
        v62 = v20;
        if ( v20 < 0 )
        {
          v26 = 1013;
          CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
            "BitsESE::BitsJetDatabaseSession::FillListFromIndex",
            &v26,
            &v62);
          v42 = 0;
          v41 = &ComError::`vftable';
          v43 = v20;
          v44 = 1013;
          v45 = 1;
          throw (ComError *)&v41;
        }
        v18 = Size;
      }
      memset(&pvar, 0, sizeof(pvar));
      v21 = BitsESE::BitsJetDatabaseSession::ByteBufferToPropVariant(pvData[0], v18, *((_WORD *)v11 + 4), &pvar);
      if ( v21 < 0 )
      {
        v47 = 0;
        v46 = &ComError::`vftable';
        v48 = v21;
        v49 = 1022;
        v50 = 1;
        throw (ComError *)&v46;
      }
      v22 = (*(__int64 (__fastcall **)(struct BitsESE::ISimpleQueryResult *, struct tagPROPVARIANT *))(*(_QWORD *)v15 + 8LL))(
              v15,
              &pvar);
      if ( v22 < 0 )
      {
        v52 = 0;
        v51 = &ComError::`vftable';
        v53 = v22;
        v54 = 1024;
        v55 = 1;
        throw (ComError *)&v51;
      }
      PropVariantClear((PROPVARIANT *)&pvar);
      std::vector<unsigned char>::_Tidy(pvData);
      v14 = JetMove(this[3], v8, 1, 0);
    }
    if ( v14 != -1603 )
    {
      v23 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v14);
      LODWORD(Size) = v23;
      if ( v23 < 0 )
      {
        v62 = 1030;
        CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
          "BitsESE::BitsJetDatabaseSession::FillListFromIndex",
          &v62,
          &Size);
        v57 = 0;
        v56 = &ComError::`vftable';
        v58 = v23;
        v59 = 1030;
        v60 = 1;
        throw (ComError *)&v56;
      }
    }
    BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction((BitsESE::ScopedBitsDatabaseSessionTransaction *)v29);
    BitsESE::ScopedBitsDatabaseSessionTransaction::~ScopedBitsDatabaseSessionTransaction((BitsESE::ScopedBitsDatabaseSessionTransaction *)v29);
    result = 0;
  }
  catch ( const ComError *v27 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v25 = v27;
    }
    else
    {
      v25 = v27;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        &WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids,
        *((unsigned int *)v25 + 6),
        *((_DWORD *)v25 + 7));
    }
    LODWORD(Size) = *((_DWORD *)v25 + 6);
    return (unsigned int)Size;
  }
  return result;
}

```

## disassembly

```asm
0x1800dfe84  mov     [rsp+arg_0], rbx
0x1800dfe89  mov     [rsp+arg_18], rsi
0x1800dfe8e  push    rdi
0x1800dfe8f  push    r12
0x1800dfe91  push    r13
0x1800dfe93  push    r14
0x1800dfe95  push    r15
0x1800dfe97  sub     rsp, 2D0h
0x1800dfe9e  mov     rsi, r9
0x1800dfea1  mov     ebx, edx
0x1800dfea3  mov     rdi, rcx
0x1800dfea6  imul    r11, rbx, 38h ; '8'
0x1800dfeaa  lea     rcx, unk_180144200
0x1800dfeb1  mov     r14, [r11+rcx+30h]
0x1800dfeb6  mov     eax, r8d
0x1800dfeb9  lea     r10, [rax+rax*2]
0x1800dfebd  add     r10, r10
0x1800dfec0  mov     rax, [r11+rcx+10h]
0x1800dfec5  mov     r12d, [rax+r10*8+18h]
0x1800dfeca  mov     edx, r8d; unsigned int
0x1800dfecd  mov     ecx, ebx; unsigned int
0x1800dfecf  call    ?GetPersistentFieldMapping@BitsJetDatabaseSession@BitsESE@@CAPEBUPersistentFieldMapping@2@KK@Z; BitsESE::BitsJetDatabaseSession::GetPersistentFieldMapping(ulong,ulong)
0x1800dfed4  mov     r13, rax
0x1800dfed7  mov     rdx, rdi; struct BitsESE::IBitsDatabaseSession *
0x1800dfeda  lea     rcx, [rsp+2F8h+var_290]; this
0x1800dfedf  call    ??0ScopedBitsDatabaseSessionTransaction@BitsESE@@QEAA@PEAVIBitsDatabaseSession@1@@Z; BitsESE::ScopedBitsDatabaseSessionTransaction::ScopedBitsDatabaseSessionTransaction(BitsESE::IBitsDatabaseSession *)
0x1800dfee4  nop
0x1800dfee5  mov     r8, rsi; szIndexName
0x1800dfee8  mov     rdx, r14; tableid
0x1800dfeeb  mov     rcx, [rdi+18h]; sesid
0x1800dfeef  call    cs:__imp_JetSetCurrentIndexW
0x1800dfef5  mov     ecx, eax; int
0x1800dfef7  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x1800dfefc  mov     ebx, eax
0x1800dfefe  mov     dword ptr [rsp+2F8h+Size], eax
0x1800dff05  test    eax, eax
0x1800dff07  jns     short loc_1800DFF79
0x1800dff09  mov     edi, 3CCh
0x1800dff0e  mov     [rsp+2F8h+arg_10], edi
0x1800dff15  lea     r8, [rsp+2F8h+Size]
0x1800dff1d  lea     rdx, [rsp+2F8h+arg_10]
0x1800dff25  lea     rcx, aBitseseBitsjet_6; "BitsESE::BitsJetDatabaseSession::FillLi"...
0x1800dff2c  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x1800dff31  xorps   xmm0, xmm0
0x1800dff34  movups  [rsp+2F8h+var_260], xmm0
0x1800dff3c  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800dff43  mov     [rsp+2F8h+pExceptionObject], rax
0x1800dff4b  mov     [rsp+2F8h+var_250], ebx
0x1800dff52  mov     [rsp+2F8h+var_24C], edi
0x1800dff59  mov     ebx, 1
0x1800dff5e  mov     [rsp+2F8h+var_248], ebx
0x1800dff65  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800dff6c  lea     rcx, [rsp+2F8h+pExceptionObject]; pExceptionObject
0x1800dff74  call    _CxxThrowException_0
0x1800dff79  xor     r9d, r9d; grbit
0x1800dff7c  mov     r8d, 80000000h; cRow
0x1800dff82  mov     rdx, r14; tableid
0x1800dff85  mov     rcx, [rdi+18h]; sesid
0x1800dff89  call    cs:__imp_JetMove
0x1800dff8f  mov     ebx, 1
0x1800dff94  mov     r15, [rsp+2F8h+arg_20]
0x1800dff9c  test    eax, eax
0x1800dff9e  jnz     loc_1800E0263
0x1800dffa4  mov     dword ptr [rsp+2F8h+Size], eax
0x1800dffab  mov     [rsp+2F8h+pretinfo], 0; pretinfo
0x1800dffb4  mov     [rsp+2F8h+grbit], eax; grbit
0x1800dffb8  lea     rax, [rsp+2F8h+Size]
0x1800dffc0  mov     [rsp+2F8h+pcbActual], rax; pcbActual
0x1800dffc5  mov     [rsp+2F8h+cbData], 0; cbData
0x1800dffcd  xor     r9d, r9d; pvData
0x1800dffd0  mov     r8d, r12d; columnid
0x1800dffd3  mov     rdx, r14; tableid
0x1800dffd6  mov     rcx, [rdi+18h]; sesid
0x1800dffda  call    cs:__imp_JetRetrieveColumn
0x1800dffe0  test    eax, eax
0x1800dffe2  jz      loc_1800E0089
0x1800dffe8  cmp     eax, 0FFFFFBE9h
0x1800dffed  jz      loc_1800E0089
0x1800dfff3  cmp     eax, 3EEh
0x1800dfff8  jz      loc_1800E0089
0x1800dfffe  cmp     eax, 0FFFFFBF2h
0x1800e0003  jz      loc_1800E0089
0x1800e0009  cmp     eax, 3ECh
0x1800e000e  jz      short loc_1800E0089
0x1800e0010  mov     ecx, eax; int
0x1800e0012  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x1800e0017  mov     esi, eax
0x1800e0019  mov     [rsp+2F8h+arg_10], eax
0x1800e0020  test    eax, eax
0x1800e0022  jns     short loc_1800E0089
0x1800e0024  mov     edi, 3E6h
0x1800e0029  mov     [rsp+2F8h+var_2B8], edi
0x1800e002d  lea     r8, [rsp+2F8h+arg_10]
0x1800e0035  lea     rdx, [rsp+2F8h+var_2B8]
0x1800e003a  lea     rcx, aBitseseBitsjet_6; "BitsESE::BitsJetDatabaseSession::FillLi"...
0x1800e0041  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x1800e0046  xorps   xmm0, xmm0
0x1800e0049  movups  [rsp+2F8h+var_200], xmm0
0x1800e0051  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e0058  mov     [rsp+2F8h+var_208], rax
0x1800e0060  mov     [rsp+2F8h+var_1F0], esi
0x1800e0067  mov     [rsp+2F8h+var_1EC], edi
0x1800e006e  mov     [rsp+2F8h+var_1E8], ebx
0x1800e0075  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e007c  lea     rcx, [rsp+2F8h+var_208]; pExceptionObject
0x1800e0084  call    _CxxThrowException_0
0x1800e0089  mov     edx, dword ptr [rsp+2F8h+Size]
0x1800e0090  lea     rcx, [rsp+2F8h+pvData]
0x1800e0095  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800e009a  nop
0x1800e009b  mov     eax, dword ptr [rsp+2F8h+Size]
0x1800e00a2  test    eax, eax
0x1800e00a4  jz      loc_1800E0161
0x1800e00aa  mov     [rsp+2F8h+pretinfo], 0; pretinfo
0x1800e00b3  mov     [rsp+2F8h+grbit], 0; grbit
0x1800e00bb  lea     rcx, [rsp+2F8h+Size]
0x1800e00c3  mov     [rsp+2F8h+pcbActual], rcx; pcbActual
0x1800e00c8  mov     [rsp+2F8h+cbData], eax; cbData
0x1800e00cc  mov     r9, [rsp+2F8h+pvData]; pvData
0x1800e00d1  mov     r8d, r12d; columnid
0x1800e00d4  mov     rdx, r14; tableid
0x1800e00d7  mov     rcx, [rdi+18h]; sesid
0x1800e00db  call    cs:__imp_JetRetrieveColumn
0x1800e00e1  mov     ecx, eax; int
0x1800e00e3  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x1800e00e8  mov     esi, eax
0x1800e00ea  mov     [rsp+2F8h+arg_10], eax
0x1800e00f1  test    eax, eax
0x1800e00f3  jns     short loc_1800E015A
0x1800e00f5  mov     edi, 3F5h
0x1800e00fa  mov     [rsp+2F8h+var_2B8], edi
0x1800e00fe  lea     r8, [rsp+2F8h+arg_10]
0x1800e0106  lea     rdx, [rsp+2F8h+var_2B8]
0x1800e010b  lea     rcx, aBitseseBitsjet_6; "BitsESE::BitsJetDatabaseSession::FillLi"...
0x1800e0112  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x1800e0117  xorps   xmm0, xmm0
0x1800e011a  movups  [rsp+2F8h+var_1A0], xmm0
0x1800e0122  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e0129  mov     [rsp+2F8h+var_1A8], rax
0x1800e0131  mov     [rsp+2F8h+var_190], esi
0x1800e0138  mov     [rsp+2F8h+var_18C], edi
0x1800e013f  mov     [rsp+2F8h+var_188], ebx
0x1800e0146  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e014d  lea     rcx, [rsp+2F8h+var_1A8]; pExceptionObject
0x1800e0155  call    _CxxThrowException_0
0x1800e015a  mov     eax, dword ptr [rsp+2F8h+Size]
0x1800e0161  xorps   xmm0, xmm0
0x1800e0164  xor     ecx, ecx
0x1800e0166  movups  xmmword ptr [rsp+2F8h+pvar], xmm0
0x1800e016b  mov     [rsp+2F8h+var_298], rcx
0x1800e0170  mov     edx, eax; Size
0x1800e0172  lea     r9, [rsp+2F8h+pvar]; struct tagPROPVARIANT *
0x1800e0177  movzx   r8d, word ptr [r13+8]; unsigned __int16
0x1800e017c  mov     rcx, [rsp+2F8h+pvData]; Src
0x1800e0181  call    ?ByteBufferToPropVariant@BitsJetDatabaseSession@BitsESE@@CAJPEAX_KGPEAUtagPROPVARIANT@@@Z; BitsESE::BitsJetDatabaseSession::ByteBufferToPropVariant(void *,unsigned __int64,ushort,tagPROPVARIANT *)
0x1800e0186  mov     ecx, eax
0x1800e0188  test    eax, eax
0x1800e018a  jns     short loc_1800E01D3
0x1800e018c  xorps   xmm0, xmm0
0x1800e018f  movups  [rsp+2F8h+var_140], xmm0
0x1800e0197  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e019e  mov     [rsp+2F8h+var_148], rax
0x1800e01a6  mov     [rsp+2F8h+var_130], ecx
0x1800e01ad  mov     [rsp+2F8h+var_12C], 3FEh
0x1800e01b8  mov     [rsp+2F8h+var_128], ebx
0x1800e01bf  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e01c6  lea     rcx, [rsp+2F8h+var_148]; pExceptionObject
0x1800e01ce  call    _CxxThrowException_0
0x1800e01d3  mov     rax, [r15]
0x1800e01d6  lea     rdx, [rsp+2F8h+pvar]
0x1800e01db  mov     rcx, r15
0x1800e01de  mov     rax, [rax+8]
0x1800e01e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e01e7  mov     ecx, eax
0x1800e01e9  test    eax, eax
0x1800e01eb  jns     short loc_1800E0235
0x1800e01ed  xorps   xmm0, xmm0
0x1800e01f0  movups  [rsp+2F8h+var_E0], xmm0
0x1800e01f8  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e01ff  mov     [rsp+2F8h+var_E8], rax
0x1800e0207  mov     [rsp+2F8h+var_D0], ecx
0x1800e020e  mov     [rsp+2F8h+var_CC], 400h
0x1800e0219  mov     [rsp+2F8h+var_C8], ebx
0x1800e0220  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e0227  lea     rcx, [rsp+2F8h+var_E8]; pExceptionObject
0x1800e022f  call    _CxxThrowException_0
0x1800e0235  lea     rcx, [rsp+2F8h+pvar]; pvar
0x1800e023a  call    cs:__imp_PropVariantClear
0x1800e0240  nop
0x1800e0241  lea     rcx, [rsp+2F8h+pvData]
0x1800e0246  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800e024b  xor     r9d, r9d; grbit
0x1800e024e  mov     r8d, ebx; cRow
0x1800e0251  mov     rdx, r14; tableid
0x1800e0254  mov     rcx, [rdi+18h]; sesid
0x1800e0258  call    cs:__imp_JetMove
0x1800e025e  jmp     loc_1800DFF9C
0x1800e0263  cmp     eax, 0FFFFF9BDh
0x1800e0268  jz      short loc_1800E02E9
0x1800e026a  mov     ecx, eax; int
0x1800e026c  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x1800e0271  mov     edi, eax
0x1800e0273  mov     dword ptr [rsp+2F8h+Size], eax
0x1800e027a  test    eax, eax
0x1800e027c  jns     short loc_1800E02E9
0x1800e027e  mov     esi, 406h
0x1800e0283  mov     [rsp+2F8h+arg_10], esi
0x1800e028a  lea     r8, [rsp+2F8h+Size]
0x1800e0292  lea     rdx, [rsp+2F8h+arg_10]
0x1800e029a  lea     rcx, aBitseseBitsjet_6; "BitsESE::BitsJetDatabaseSession::FillLi"...
0x1800e02a1  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x1800e02a6  xorps   xmm0, xmm0
0x1800e02a9  movups  [rsp+2F8h+var_80], xmm0
0x1800e02b1  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800e02b8  mov     [rsp+2F8h+var_88], rax
0x1800e02c0  mov     [rsp+2F8h+var_70], edi
0x1800e02c7  mov     [rsp+2F8h+var_6C], esi
0x1800e02ce  mov     [rsp+2F8h+var_68], ebx
0x1800e02d5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800e02dc  lea     rcx, [rsp+2F8h+var_88]; pExceptionObject
0x1800e02e4  call    _CxxThrowException_0
0x1800e02e9  lea     rcx, [rsp+2F8h+var_290]; this
0x1800e02ee  call    ?CommitTransaction@ScopedBitsDatabaseSessionTransaction@BitsESE@@QEAAXXZ; BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction(void)
0x1800e02f3  nop
0x1800e02f4  lea     rcx, [rsp+2F8h+var_290]; this
0x1800e02f9  call    ??1ScopedBitsDatabaseSessionTransaction@BitsESE@@QEAA@XZ; BitsESE::ScopedBitsDatabaseSessionTransaction::~ScopedBitsDatabaseSessionTransaction(void)
0x1800e02fe  xor     eax, eax
0x1800e0300  jmp     short loc_1800E0309
0x1800e0302  mov     eax, dword ptr [rsp+2F8h+Size]
0x1800e0309  lea     r11, [rsp+2F8h+var_28]
0x1800e0311  mov     rbx, [r11+30h]
0x1800e0315  mov     rsi, [r11+48h]
0x1800e0319  mov     rsp, r11
0x1800e031c  pop     r15
0x1800e031e  pop     r14
0x1800e0320  pop     r13
0x1800e0322  pop     r12
0x1800e0324  pop     rdi
0x1800e0325  retn
```
