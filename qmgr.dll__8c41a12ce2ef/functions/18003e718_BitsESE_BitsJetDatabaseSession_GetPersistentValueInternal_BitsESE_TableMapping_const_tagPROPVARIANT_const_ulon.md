# BitsESE::BitsJetDatabaseSession::GetPersistentValueInternal(BitsESE::TableMapping const *,tagPROPVARIANT const *,ulong,ushort,tagPROPVARIANT *)

- ea: `0x18003e718`
- end: `0x18003ec38`
- name: `?GetPersistentValueInternal@BitsJetDatabaseSession@BitsESE@@AEAAJPEBUTableMapping@2@PEBUtagPROPVARIANT@@KGPEAU4@@Z`
- size: `1312`
- prototype: `__int64 __usercall@<rax>(BitsESE::BitsJetDatabaseSession *__hidden this@<rcx>, const struct BitsESE::TableMapping *@<rdx>, const struct tagPROPVARIANT *@<r8>, unsigned int@<r9d>, unsigned __int16, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003e670`

## callees

- `0x18003e718`
- `0x18003fee0`
- `0x1800407d0`
- `0x180099740`
- `0x18009c0e0`
- `0x18009d024`
- `0x1800df410`
- `0x1800f9948`
- `0x1800f9960`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ead8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003eb1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ead8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003eb1f`
- `ESENT!JetRetrieveColumn` at `0x18003e882`
- `ESENT!JetRetrieveColumn` at `0x18003e9a3`
- `ESENT!JetRetrieveColumn` at `0x18003e882`
- `ESENT!JetRetrieveColumn` at `0x18003e9a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BitsESE::BitsJetDatabaseSession::GetPersistentValueInternal(
        JET_SESID *this,
        const struct BitsESE::TableMapping *a2,
        const struct tagPROPVARIANT *a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct tagPROPVARIANT *a6)
{
  __int64 v9; // r10
  JET_TABLEID v10; // r14
  JET_COLUMNID v11; // r15d
  int v12; // eax
  int v13; // ebx
  JET_ERR Column; // eax
  int v15; // ebx
  unsigned int v16; // eax
  JET_ERR v17; // eax
  int v18; // ebx
  size_t v19; // rbx
  const void *v20; // r15
  unsigned __int16 v21; // r14
  int v22; // eax
  GUID *v23; // rax
  struct tagPROPVARIANT *v24; // rdi
  BYTE *v25; // rax
  int v26; // eax
  __int64 result; // rax
  const ComError *v28; // rbx
  void *pvData[2]; // [rsp+40h] [rbp-298h] BYREF
  __int64 v30; // [rsp+50h] [rbp-288h]
  const ComError *v31[2]; // [rsp+58h] [rbp-280h] BYREF
  char v32; // [rsp+68h] [rbp-270h]
  void **pExceptionObject; // [rsp+70h] [rbp-268h] BYREF
  __int128 v34; // [rsp+78h] [rbp-260h]
  int v35; // [rsp+88h] [rbp-250h]
  int v36; // [rsp+8Ch] [rbp-24Ch]
  int v37; // [rsp+90h] [rbp-248h]
  void **v38; // [rsp+D0h] [rbp-208h] BYREF
  __int128 v39; // [rsp+D8h] [rbp-200h]
  int v40; // [rsp+E8h] [rbp-1F0h]
  int v41; // [rsp+ECh] [rbp-1ECh]
  int v42; // [rsp+F0h] [rbp-1E8h]
  void **v43; // [rsp+130h] [rbp-1A8h] BYREF
  __int128 v44; // [rsp+138h] [rbp-1A0h]
  int v45; // [rsp+148h] [rbp-190h]
  int v46; // [rsp+14Ch] [rbp-18Ch]
  int v47; // [rsp+150h] [rbp-188h]
  void **v48; // [rsp+190h] [rbp-148h] BYREF
  __int128 v49; // [rsp+198h] [rbp-140h]
  int v50; // [rsp+1A8h] [rbp-130h]
  int v51; // [rsp+1ACh] [rbp-12Ch]
  int v52; // [rsp+1B0h] [rbp-128h]
  void **v53; // [rsp+1F0h] [rbp-E8h] BYREF
  __int128 v54; // [rsp+1F8h] [rbp-E0h]
  int v55; // [rsp+208h] [rbp-D0h]
  int v56; // [rsp+20Ch] [rbp-CCh]
  int v57; // [rsp+210h] [rbp-C8h]
  void **v58; // [rsp+250h] [rbp-88h] BYREF
  __int128 v59; // [rsp+258h] [rbp-80h]
  int v60; // [rsp+268h] [rbp-70h]
  int v61; // [rsp+26Ch] [rbp-6Ch]
  int v62; // [rsp+270h] [rbp-68h]
  int v63; // [rsp+2E0h] [rbp+8h] BYREF
  int v64; // [rsp+2E8h] [rbp+10h] BYREF
  size_t Size; // [rsp+2F8h] [rbp+20h] BYREF

  v9 = 56LL * *((unsigned int *)a2 + 1);
  v10 = *(_QWORD *)((char *)&unk_180144200 + v9 + 48);
  v11 = *(_DWORD *)(*(_QWORD *)((char *)&unk_180144200 + v9 + 16) + 48LL * a4 + 24);
  v31[1] = (const ComError *)this;
  v32 = 0;
  try
  {
    v12 = (*(__int64 (__fastcall **)(JET_SESID *))(*this + 40))(this);
    if ( v12 < 0 )
    {
      v34 = 0;
      pExceptionObject = &ComError::`vftable';
      v35 = v12;
      v36 = 15;
      v37 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v13 = BitsESE::BitsJetDatabaseSession::MoveToEntity((BitsESE::BitsJetDatabaseSession *)this, a3, a2);
    v63 = v13;
    if ( v13 < 0 )
    {
      v64 = 899;
      CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
        "BitsESE::BitsJetDatabaseSession::GetPersistentValueInternal",
        &v64,
        &v63);
      v39 = 0;
      v38 = &ComError::`vftable';
      v40 = v13;
      v41 = 900;
      v42 = 1;
      throw (ComError *)&v38;
    }
    LODWORD(Size) = 0;
    Column = JetRetrieveColumn(this[3], v10, v11, 0, 0, (unsigned int *)&Size, 0, 0);
    if ( Column )
    {
      if ( Column != -1047 && Column != 1006 && Column != -1038 && Column != 1004 )
      {
        v15 = BitsESE::BitsJetDatabaseSession::JetErrToHR(Column);
        v63 = v15;
        if ( v15 < 0 )
        {
          v64 = 921;
          CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
            "BitsESE::BitsJetDatabaseSession::GetPersistentValueInternal",
            &v64,
            &v63);
          v44 = 0;
          v43 = &ComError::`vftable';
          v45 = v15;
          v46 = 921;
          v47 = 1;
          throw (ComError *)&v43;
        }
      }
    }
    *(_OWORD *)pvData = 0;
    v30 = 0;
    std::vector<unsigned char>::_Construct_n<>(pvData, (unsigned int)Size);
    v16 = Size;
    if ( (_DWORD)Size )
    {
      v17 = JetRetrieveColumn(this[3], v10, v11, pvData[0], Size, (unsigned int *)&Size, 0, 0);
      v18 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v17);
      v63 = v18;
      if ( v18 < 0 )
      {
        v64 = 936;
        CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
          "BitsESE::BitsJetDatabaseSession::GetPersistentValueInternal",
          &v64,
          &v63);
        v49 = 0;
        v48 = &ComError::`vftable';
        v50 = v18;
        v51 = 936;
        v52 = 1;
        throw (ComError *)&v48;
      }
      v16 = Size;
    }
    v19 = v16;
    v20 = pvData[0];
    v21 = a5;
    if ( a5 == 72 )
    {
      if ( (v16 & 0xFFFFFFEF) != 0 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
        v22 = BitsESE::BitsJetDatabaseSession::JetErrToHR(-1047);
        goto LABEL_38;
      }
      v23 = (GUID *)CoTaskMemAlloc(0x10u);
      v24 = a6;
      a6->hVal.QuadPart = (LONGLONG)v23;
      if ( v23 )
      {
        if ( v19 )
          memcpy_0(v23, v20, v19);
        else
          *v23 = GUID_NULL;
        goto LABEL_37;
      }
    }
    else
    {
      if ( a5 != 65 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
        v22 = -2147418113;
LABEL_39:
        v54 = 0;
        v53 = &ComError::`vftable';
        v55 = v22;
        v56 = 940;
        v57 = 1;
        throw (ComError *)&v53;
      }
      if ( !v16 )
      {
        v24 = a6;
        goto LABEL_37;
      }
      v25 = (BYTE *)CoTaskMemAlloc(v16);
      v24 = a6;
      a6->bstrblobVal.pData = v25;
      if ( v25 )
      {
        memcpy_0(v25, v20, v19);
        v24->lVal = v19;
LABEL_37:
        v24->vt = v21;
        v22 = 0;
LABEL_38:
        if ( v22 < 0 )
          goto LABEL_39;
        v26 = (*(__int64 (__fastcall **)(JET_SESID *))(*this + 48))(this);
        if ( v26 < 0 )
        {
          v59 = 0;
          v58 = &ComError::`vftable';
          v60 = v26;
          v61 = 20;
          v62 = 1;
          throw (ComError *)&v58;
        }
        if ( pvData[0] )
          std::_Deallocate<16>(pvData[0], v30 - (unsigned __int64)pvData[0]);
        return 0;
      }
    }
    v22 = -2147024882;
    goto LABEL_39;
  }
  catch ( const ComError *v31 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v28 = v31[0];
    }
    else
    {
      v28 = v31[0];
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids,
        *((unsigned int *)v31[0] + 6),
        *((_DWORD *)v31[0] + 7));
    }
    LODWORD(Size) = *((_DWORD *)v28 + 6);
    return (unsigned int)Size;
  }
  return result;
}

```

## disassembly

```asm
0x18003e718  push    rbx
0x18003e71a  push    rsi
0x18003e71b  push    rdi
0x18003e71c  push    r14
0x18003e71e  push    r15
0x18003e720  sub     rsp, 2B0h
0x18003e727  mov     rdi, r8
0x18003e72a  mov     rbx, rdx
0x18003e72d  mov     rsi, rcx
0x18003e730  mov     eax, [rdx+4]
0x18003e733  imul    r10, rax, 38h ; '8'
0x18003e737  lea     rcx, unk_180144200
0x18003e73e  mov     r14, [r10+rcx+30h]
0x18003e743  mov     eax, r9d
0x18003e746  lea     r9, [rax+rax*2]
0x18003e74a  add     r9, r9
0x18003e74d  mov     rax, [r10+rcx+10h]
0x18003e752  mov     r15d, [rax+r9*8+18h]
0x18003e757  mov     [rsp+2D8h+var_278], rsi
0x18003e75c  mov     [rsp+2D8h+var_270], 0
0x18003e761  mov     rax, [rsi]
0x18003e764  mov     rcx, rsi
0x18003e767  mov     rax, [rax+28h]
0x18003e76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e770  test    eax, eax
0x18003e772  jns     short loc_18003E7B7
0x18003e774  xorps   xmm0, xmm0
0x18003e777  movups  [rsp+2D8h+var_260], xmm0
0x18003e77c  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003e783  mov     [rsp+2D8h+pExceptionObject], rcx
0x18003e788  mov     [rsp+2D8h+var_250], eax
0x18003e78f  mov     [rsp+2D8h+var_24C], 0Fh
0x18003e79a  mov     [rsp+2D8h+var_248], 1
0x18003e7a5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003e7ac  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x18003e7b1  call    _CxxThrowException_0
0x18003e7b7  mov     r8, rbx; struct BitsESE::TableMapping *
0x18003e7ba  mov     rdx, rdi; struct tagPROPVARIANT *
0x18003e7bd  mov     rcx, rsi; this
0x18003e7c0  call    ?MoveToEntity@BitsJetDatabaseSession@BitsESE@@AEAAJPEBUtagPROPVARIANT@@PEBUTableMapping@2@@Z; BitsESE::BitsJetDatabaseSession::MoveToEntity(tagPROPVARIANT const *,BitsESE::TableMapping const *)
0x18003e7c5  mov     ebx, eax
0x18003e7c7  mov     [rsp+2D8h+arg_0], eax
0x18003e7ce  test    eax, eax
0x18003e7d0  jns     short loc_18003E844
0x18003e7d2  mov     [rsp+2D8h+arg_8], 383h
0x18003e7dd  lea     r8, [rsp+2D8h+arg_0]
0x18003e7e5  lea     rdx, [rsp+2D8h+arg_8]
0x18003e7ed  lea     rcx, aBitseseBitsjet_10; "BitsESE::BitsJetDatabaseSession::GetPer"...
0x18003e7f4  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003e7f9  xorps   xmm0, xmm0
0x18003e7fc  movups  [rsp+2D8h+var_200], xmm0
0x18003e804  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003e80b  mov     [rsp+2D8h+var_208], rcx
0x18003e813  mov     [rsp+2D8h+var_1F0], ebx
0x18003e81a  mov     [rsp+2D8h+var_1EC], 384h
0x18003e825  mov     [rsp+2D8h+var_1E8], 1
0x18003e830  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003e837  lea     rcx, [rsp+2D8h+var_208]; pExceptionObject
0x18003e83f  call    _CxxThrowException_0
0x18003e844  mov     dword ptr [rsp+2D8h+Size], 0
0x18003e84f  mov     [rsp+2D8h+pretinfo], 0; pretinfo
0x18003e858  mov     [rsp+2D8h+grbit], 0; grbit
0x18003e860  lea     rax, [rsp+2D8h+Size]
0x18003e868  mov     [rsp+2D8h+pcbActual], rax; pcbActual
0x18003e86d  mov     [rsp+2D8h+cbData], 0; cbData
0x18003e875  xor     r9d, r9d; pvData
0x18003e878  mov     r8d, r15d; columnid
0x18003e87b  mov     rdx, r14; tableid
0x18003e87e  mov     rcx, [rsi+18h]; sesid
0x18003e882  call    cs:__imp_JetRetrieveColumn
0x18003e888  test    eax, eax
0x18003e88a  jz      loc_18003E93F
0x18003e890  cmp     eax, 0FFFFFBE9h
0x18003e895  jz      loc_18003E93F
0x18003e89b  cmp     eax, 3EEh
0x18003e8a0  jz      loc_18003E93F
0x18003e8a6  cmp     eax, 0FFFFFBF2h
0x18003e8ab  jz      loc_18003E93F
0x18003e8b1  cmp     eax, 3ECh
0x18003e8b6  jz      loc_18003E93F
0x18003e8bc  mov     ecx, eax; int
0x18003e8be  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003e8c3  mov     ebx, eax
0x18003e8c5  mov     [rsp+2D8h+arg_0], eax
0x18003e8cc  test    eax, eax
0x18003e8ce  jns     short loc_18003E93F
0x18003e8d0  mov     edi, 399h
0x18003e8d5  mov     [rsp+2D8h+arg_8], edi
0x18003e8dc  lea     r8, [rsp+2D8h+arg_0]
0x18003e8e4  lea     rdx, [rsp+2D8h+arg_8]
0x18003e8ec  lea     rcx, aBitseseBitsjet_10; "BitsESE::BitsJetDatabaseSession::GetPer"...
0x18003e8f3  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003e8f8  xorps   xmm0, xmm0
0x18003e8fb  movups  [rsp+2D8h+var_1A0], xmm0
0x18003e903  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003e90a  mov     [rsp+2D8h+var_1A8], rcx
0x18003e912  mov     [rsp+2D8h+var_190], ebx
0x18003e919  mov     [rsp+2D8h+var_18C], edi
0x18003e920  mov     [rsp+2D8h+var_188], 1
0x18003e92b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003e932  lea     rcx, [rsp+2D8h+var_1A8]; pExceptionObject
0x18003e93a  call    _CxxThrowException_0
0x18003e93f  xorps   xmm0, xmm0
0x18003e942  movdqu  xmmword ptr [rsp+2D8h+pvData], xmm0
0x18003e948  mov     [rsp+2D8h+var_288], 0
0x18003e951  mov     edx, dword ptr [rsp+2D8h+Size]
0x18003e958  lea     rcx, [rsp+2D8h+pvData]
0x18003e95d  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18003e962  nop
0x18003e963  mov     eax, dword ptr [rsp+2D8h+Size]
0x18003e96a  test    eax, eax
0x18003e96c  jz      loc_18003EA33
0x18003e972  mov     [rsp+2D8h+pretinfo], 0; pretinfo
0x18003e97b  mov     [rsp+2D8h+grbit], 0; grbit
0x18003e983  lea     rcx, [rsp+2D8h+Size]
0x18003e98b  mov     [rsp+2D8h+pcbActual], rcx; pcbActual
0x18003e990  mov     [rsp+2D8h+cbData], eax; cbData
0x18003e994  mov     r9, [rsp+2D8h+pvData]; pvData
0x18003e999  mov     r8d, r15d; columnid
0x18003e99c  mov     rdx, r14; tableid
0x18003e99f  mov     rcx, [rsi+18h]; sesid
0x18003e9a3  call    cs:__imp_JetRetrieveColumn
0x18003e9a9  mov     ecx, eax; int
0x18003e9ab  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003e9b0  mov     ebx, eax
0x18003e9b2  mov     [rsp+2D8h+arg_0], eax
0x18003e9b9  test    eax, eax
0x18003e9bb  jns     short loc_18003EA2C
0x18003e9bd  mov     edi, 3A8h
0x18003e9c2  mov     [rsp+2D8h+arg_8], edi
0x18003e9c9  lea     r8, [rsp+2D8h+arg_0]
0x18003e9d1  lea     rdx, [rsp+2D8h+arg_8]
0x18003e9d9  lea     rcx, aBitseseBitsjet_10; "BitsESE::BitsJetDatabaseSession::GetPer"...
0x18003e9e0  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003e9e5  xorps   xmm0, xmm0
0x18003e9e8  movups  [rsp+2D8h+var_140], xmm0
0x18003e9f0  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003e9f7  mov     [rsp+2D8h+var_148], rcx
0x18003e9ff  mov     [rsp+2D8h+var_130], ebx
0x18003ea06  mov     [rsp+2D8h+var_12C], edi
0x18003ea0d  mov     [rsp+2D8h+var_128], 1
0x18003ea18  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003ea1f  lea     rcx, [rsp+2D8h+var_148]; pExceptionObject
0x18003ea27  call    _CxxThrowException_0
0x18003ea2c  mov     eax, dword ptr [rsp+2D8h+Size]
0x18003ea33  mov     ebx, eax
0x18003ea35  mov     r15, [rsp+2D8h+pvData]
0x18003ea3a  movzx   r14d, [rsp+2D8h+arg_20]
0x18003ea43  cmp     r14w, 48h ; 'H'
0x18003ea48  jz      short loc_18003EA8D
0x18003ea4a  cmp     r14w, 41h ; 'A'
0x18003ea4f  jz      loc_18003EB18
0x18003ea55  lea     rax, WPP_GLOBAL_Control
0x18003ea5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea63  cmp     rcx, rax
0x18003ea66  jz      short loc_18003EA83
0x18003ea68  test    byte ptr [rcx+1Ch], 4
0x18003ea6c  jz      short loc_18003EA83
0x18003ea6e  mov     edx, 3Bh ; ';'
0x18003ea73  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18003ea7a  mov     rcx, [rcx+10h]
0x18003ea7e  call    WPP_SF_
0x18003ea83  mov     eax, 8000FFFFh
0x18003ea88  jmp     loc_18003EB5B
0x18003ea8d  test    rbx, 0FFFFFFFFFFFFFFEFh
0x18003ea94  jz      short loc_18003EAD3
0x18003ea96  lea     rax, WPP_GLOBAL_Control
0x18003ea9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eaa4  cmp     rcx, rax
0x18003eaa7  jz      short loc_18003EAC4
0x18003eaa9  test    byte ptr [rcx+1Ch], 4
0x18003eaad  jz      short loc_18003EAC4
0x18003eaaf  mov     edx, 3Ah ; ':'
0x18003eab4  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18003eabb  mov     rcx, [rcx+10h]
0x18003eabf  call    WPP_SF_
0x18003eac4  mov     ecx, 0FFFFFBE9h; int
0x18003eac9  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003eace  jmp     loc_18003EB57
0x18003ead3  mov     ecx, 10h; cb
0x18003ead8  call    cs:__imp_CoTaskMemAlloc
0x18003eade  mov     rdi, [rsp+2D8h+arg_28]
0x18003eae6  mov     [rdi+8], rax
0x18003eaea  test    rax, rax
0x18003eaed  jnz     short loc_18003EAF6
0x18003eaef  mov     eax, 8007000Eh
0x18003eaf4  jmp     short loc_18003EB5B
0x18003eaf6  test    rbx, rbx
0x18003eaf9  jz      short loc_18003EB0B
0x18003eafb  mov     r8, rbx; Size
0x18003eafe  mov     rdx, r15; Src
0x18003eb01  mov     rcx, rax; void *
0x18003eb04  call    memcpy_0
0x18003eb09  jmp     short loc_18003EB51
0x18003eb0b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003eb12  movdqu  xmmword ptr [rax], xmm0
0x18003eb16  jmp     short loc_18003EB51
0x18003eb18  test    eax, eax
0x18003eb1a  jz      short loc_18003EB49
0x18003eb1c  mov     rcx, rbx; cb
0x18003eb1f  call    cs:__imp_CoTaskMemAlloc
0x18003eb25  mov     rdi, [rsp+2D8h+arg_28]
0x18003eb2d  mov     [rdi+10h], rax
0x18003eb31  test    rax, rax
0x18003eb34  jz      short loc_18003EAEF
0x18003eb36  mov     r8, rbx; Size
0x18003eb39  mov     rdx, r15; Src
0x18003eb3c  mov     rcx, rax; void *
0x18003eb3f  call    memcpy_0
0x18003eb44  mov     [rdi+8], ebx
0x18003eb47  jmp     short loc_18003EB51
0x18003eb49  mov     rdi, [rsp+2D8h+arg_28]
0x18003eb51  mov     [rdi], r14w
0x18003eb55  xor     eax, eax
0x18003eb57  test    eax, eax
0x18003eb59  jns     short loc_18003EBA6
0x18003eb5b  xorps   xmm0, xmm0
0x18003eb5e  movups  [rsp+2D8h+var_E0], xmm0
0x18003eb66  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003eb6d  mov     [rsp+2D8h+var_E8], rcx
0x18003eb75  mov     [rsp+2D8h+var_D0], eax
0x18003eb7c  mov     [rsp+2D8h+var_CC], 3ACh
0x18003eb87  mov     [rsp+2D8h+var_C8], 1
0x18003eb92  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003eb99  lea     rcx, [rsp+2D8h+var_E8]; pExceptionObject
0x18003eba1  call    _CxxThrowException_0
0x18003eba6  mov     rax, [rsi]
0x18003eba9  mov     rcx, rsi
0x18003ebac  mov     rax, [rax+30h]
0x18003ebb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebb5  test    eax, eax
0x18003ebb7  jns     short loc_18003EC05
0x18003ebb9  xorps   xmm0, xmm0
0x18003ebbc  movups  [rsp+2D8h+var_80], xmm0
0x18003ebc4  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003ebcb  mov     [rsp+2D8h+var_88], rcx
0x18003ebd3  mov     [rsp+2D8h+var_70], eax
0x18003ebda  mov     [rsp+2D8h+var_6C], 14h
0x18003ebe5  mov     [rsp+2D8h+var_68], 1
0x18003ebf0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003ebf7  lea     rcx, [rsp+2D8h+var_88]; pExceptionObject
0x18003ebff  call    _CxxThrowException_0
0x18003ec05  mov     rcx, [rsp+2D8h+pvData]
0x18003ec0a  test    rcx, rcx
0x18003ec0d  jz      short loc_18003EC1D
0x18003ec0f  mov     rdx, [rsp+2D8h+var_288]
0x18003ec14  sub     rdx, rcx
0x18003ec17  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003ec1c  nop
0x18003ec1d  xor     eax, eax
0x18003ec1f  jmp     short loc_18003EC28
0x18003ec21  mov     eax, dword ptr [rsp+2D8h+Size]
0x18003ec28  add     rsp, 2B0h
0x18003ec2f  pop     r15
0x18003ec31  pop     r14
0x18003ec33  pop     rdi
0x18003ec34  pop     rsi
0x18003ec35  pop     rbx
0x18003ec36  retn
```
