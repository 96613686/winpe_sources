# BitsESE::BitsJetDatabaseSession::UpdateCurrentEntityValue(tagPROPVARIANT const *,ulong,unsigned __int64,ulong,bool)

- ea: `0x18003fab0`
- end: `0x18003fe0d`
- name: `?UpdateCurrentEntityValue@BitsJetDatabaseSession@BitsESE@@AEAAJPEBUtagPROPVARIANT@@K_KK_N@Z`
- size: `861`
- prototype: `int(BitsESE::BitsJetDatabaseSession *__hidden this, const struct tagPROPVARIANT *, unsigned int, unsigned __int64, unsigned int, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003ecfc`

## callees

- `0x18000db20`
- `0x18003fab0`
- `0x1800407d0`
- `0x1800544a0`
- `0x18009d024`
- `0x1800a3444`
- `0x1800df410`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003fd9f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003fd9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fdce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fdce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003fae7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003fae7`
- `ESENT!JetSetColumn` at `0x18003fc82`
- `ESENT!JetSetColumn` at `0x18003fc82`
- `ESENT!JetUpdate` at `0x18003fd14`
- `ESENT!JetUpdate` at `0x18003fd14`

## string_xrefs

- `0x18003fcab`: `BitsESE::BitsJetDatabaseSession::UpdateCurrentEntityValue`
- `0x18003fd3d`: `BitsESE::BitsJetDatabaseSession::UpdateCurrentEntityValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BitsESE::BitsJetDatabaseSession::UpdateCurrentEntityValue(
        BitsESE::BitsJetDatabaseSession *this,
        const struct tagPROPVARIANT *a2,
        unsigned int a3,
        JET_TABLEID a4,
        JET_COLUMNID columnid,
        bool a6)
{
  unsigned __int64 v7; // r15
  unsigned int LastError; // ecx
  VARTYPE vt; // ax
  BYTE *pbVal; // r9
  unsigned __int64 cbData; // rcx
  unsigned int v14; // ebx
  __int64 result; // rax
  JET_ERR v16; // eax
  int v17; // ebx
  JET_ERR v18; // eax
  int v19; // ebx
  void *v20; // rcx
  const ComError *v21; // rbx
  int v22; // [rsp+40h] [rbp-1B8h] BYREF
  int v23; // [rsp+44h] [rbp-1B4h] BYREF
  void *v24; // [rsp+48h] [rbp-1B0h] BYREF
  const ComError *v25; // [rsp+50h] [rbp-1A8h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-198h] BYREF
  __int128 v27; // [rsp+68h] [rbp-190h]
  unsigned int v28; // [rsp+78h] [rbp-180h]
  int v29; // [rsp+7Ch] [rbp-17Ch]
  int v30; // [rsp+80h] [rbp-178h]
  void **v31; // [rsp+C0h] [rbp-138h] BYREF
  __int128 v32; // [rsp+C8h] [rbp-130h]
  int v33; // [rsp+D8h] [rbp-120h]
  int v34; // [rsp+DCh] [rbp-11Ch]
  int v35; // [rsp+E0h] [rbp-118h]
  void **v36; // [rsp+120h] [rbp-D8h] BYREF
  __int128 v37; // [rsp+128h] [rbp-D0h]
  int v38; // [rsp+138h] [rbp-C0h]
  int v39; // [rsp+13Ch] [rbp-BCh]
  int v40; // [rsp+140h] [rbp-B8h]
  void **v41; // [rsp+180h] [rbp-78h] BYREF
  __int128 v42; // [rsp+188h] [rbp-70h]
  int v43; // [rsp+198h] [rbp-60h]
  int v44; // [rsp+19Ch] [rbp-5Ch]
  int v45; // [rsp+1A0h] [rbp-58h]

  v7 = a3;
  try
  {
    CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v24);
    if ( !RevertToSelf() )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v27 = 0;
      pExceptionObject = &ComError::`vftable';
      v28 = LastError;
      v29 = 839;
      v30 = 1;
      throw (ComError *)&pExceptionObject;
    }
    vt = a2->vt;
    if ( a2->vt == 72 )
    {
      pbVal = a2->pbVal;
      cbData = 16;
    }
    else if ( vt )
    {
      if ( vt != 65 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
        v32 = 0;
        v31 = &ComError::`vftable';
        v33 = -2147418113;
        v34 = 844;
        v35 = 1;
        throw (ComError *)&v31;
      }
      pbVal = a2->bstrblobVal.pData;
      cbData = a2->ulVal;
    }
    else
    {
      pbVal = 0;
      cbData = 0;
    }
    if ( (_DWORD)v7 && v7 < cbData )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
      v14 = BitsESE::BitsJetDatabaseSession::JetErrToHR(-1047);
      CSaveThreadToken::~CSaveThreadToken((CSaveThreadToken *)&v24);
      result = v14;
    }
    else
    {
      v16 = JetSetColumn(*((_QWORD *)this + 3), a4, columnid, pbVal, cbData, a6, 0);
      v17 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v16);
      v23 = v17;
      if ( v17 < 0 )
      {
        v22 = 861;
        CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
          "BitsESE::BitsJetDatabaseSession::UpdateCurrentEntityValue",
          &v22,
          &v23);
        v37 = 0;
        v36 = &ComError::`vftable';
        v38 = v17;
        v39 = 861;
        v40 = 1;
        throw (ComError *)&v36;
      }
      v18 = JetUpdate(*((_QWORD *)this + 3), a4, 0, 0, 0);
      v19 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v18);
      v22 = v19;
      if ( v19 < 0 )
      {
        v23 = 863;
        CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
          "BitsESE::BitsJetDatabaseSession::UpdateCurrentEntityValue",
          &v23,
          &v22);
        v42 = 0;
        v41 = &ComError::`vftable';
        v43 = v19;
        v44 = 863;
        v45 = 1;
        throw (ComError *)&v41;
      }
      SetThreadToken(0, *(HANDLE *)v24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
      {
        v20 = v24;
        if ( (unsigned __int64)(*(_QWORD *)v24 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v24);
          *(_QWORD *)v24 = 0;
          v20 = v24;
        }
        operator delete(v20, 0x10u);
      }
      result = 0;
    }
  }
  catch ( const ComError *v25 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v21 = v25;
    }
    else
    {
      v21 = v25;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids,
        *((unsigned int *)v21 + 6),
        *((_DWORD *)v21 + 7));
    }
    JetPrepareUpdate(*((_QWORD *)this + 3), a4, 3u);
    return *((unsigned int *)v21 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x18003fab0  mov     [rsp+arg_8], rbx
0x18003fab5  mov     [rsp+arg_10], rsi
0x18003faba  mov     [rsp+arg_18], r9
0x18003fabf  mov     [rsp+arg_0], rcx
0x18003fac4  push    rdi
0x18003fac5  push    r14
0x18003fac7  push    r15
0x18003fac9  sub     rsp, 1E0h
0x18003fad0  mov     rdi, r9
0x18003fad3  mov     r15d, r8d
0x18003fad6  mov     rbx, rdx
0x18003fad9  mov     rsi, rcx
0x18003fadc  lea     rcx, [rsp+1F8h+var_1B0]; this
0x18003fae1  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x18003fae6  nop
0x18003fae7  call    cs:__imp_RevertToSelf
0x18003faed  test    eax, eax
0x18003faef  jnz     short loc_18003FB50
0x18003faf1  call    cs:__imp_GetLastError
0x18003faf7  test    eax, eax
0x18003faf9  jg      short loc_18003FB05
0x18003fafb  call    cs:__imp_GetLastError
0x18003fb01  mov     ecx, eax
0x18003fb03  jmp     short loc_18003FB14
0x18003fb05  call    cs:__imp_GetLastError
0x18003fb0b  movzx   ecx, ax
0x18003fb0e  or      ecx, 80070000h
0x18003fb14  xorps   xmm0, xmm0
0x18003fb17  movups  [rsp+1F8h+var_190], xmm0
0x18003fb1c  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003fb23  mov     [rsp+1F8h+pExceptionObject], rax
0x18003fb28  mov     [rsp+1F8h+var_180], ecx
0x18003fb2c  mov     [rsp+1F8h+var_17C], 347h
0x18003fb34  mov     [rsp+1F8h+var_178], 1
0x18003fb3f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003fb46  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x18003fb4b  call    _CxxThrowException_0
0x18003fb50  movzx   eax, word ptr [rbx]
0x18003fb53  cmp     ax, 48h ; 'H'
0x18003fb57  jz      loc_18003FBFD
0x18003fb5d  test    ax, ax
0x18003fb60  jz      loc_18003FBF2
0x18003fb66  cmp     ax, 41h ; 'A'
0x18003fb6a  jz      short loc_18003FBE9
0x18003fb6c  lea     rax, WPP_GLOBAL_Control
0x18003fb73  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb7a  cmp     rcx, rax
0x18003fb7d  jz      short loc_18003FB9A
0x18003fb7f  test    byte ptr [rcx+1Ch], 4
0x18003fb83  jz      short loc_18003FB9A
0x18003fb85  mov     edx, 39h ; '9'
0x18003fb8a  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18003fb91  mov     rcx, [rcx+10h]
0x18003fb95  call    WPP_SF_
0x18003fb9a  xorps   xmm0, xmm0
0x18003fb9d  movups  [rsp+1F8h+var_130], xmm0
0x18003fba5  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003fbac  mov     [rsp+1F8h+var_138], rax
0x18003fbb4  mov     [rsp+1F8h+var_120], 8000FFFFh
0x18003fbbf  mov     [rsp+1F8h+var_11C], 34Ch
0x18003fbca  mov     [rsp+1F8h+var_118], 1
0x18003fbd5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003fbdc  lea     rcx, [rsp+1F8h+var_138]; pExceptionObject
0x18003fbe4  call    _CxxThrowException_0
0x18003fbe9  mov     r9, [rbx+10h]
0x18003fbed  mov     ecx, [rbx+8]
0x18003fbf0  jmp     short loc_18003FC06
0x18003fbf2  xor     r14d, r14d
0x18003fbf5  mov     r9d, r14d
0x18003fbf8  mov     ecx, r14d
0x18003fbfb  jmp     short loc_18003FC09
0x18003fbfd  mov     r9, [rbx+8]; pvData
0x18003fc01  mov     ecx, 10h
0x18003fc06  xor     r14d, r14d
0x18003fc09  test    r15d, r15d
0x18003fc0c  jz      short loc_18003FC5E
0x18003fc0e  cmp     r15, rcx
0x18003fc11  jnb     short loc_18003FC5E
0x18003fc13  lea     rax, WPP_GLOBAL_Control
0x18003fc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc21  cmp     rcx, rax
0x18003fc24  jz      short loc_18003FC41
0x18003fc26  test    byte ptr [rcx+1Ch], 4
0x18003fc2a  jz      short loc_18003FC41
0x18003fc2c  mov     edx, 2Bh ; '+'
0x18003fc31  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18003fc38  mov     rcx, [rcx+10h]
0x18003fc3c  call    WPP_SF_
0x18003fc41  mov     ecx, 0FFFFFBE9h; int
0x18003fc46  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003fc4b  mov     ebx, eax
0x18003fc4d  lea     rcx, [rsp+1F8h+var_1B0]; this
0x18003fc52  call    ??1CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::~CSaveThreadToken(void)
0x18003fc57  mov     eax, ebx
0x18003fc59  jmp     loc_18003FDF3
0x18003fc5e  movzx   eax, [rsp+1F8h+arg_28]
0x18003fc66  mov     [rsp+1F8h+psetinfo], r14; psetinfo
0x18003fc6b  mov     [rsp+1F8h+grbit], eax; grbit
0x18003fc6f  mov     [rsp+1F8h+cbData], ecx; cbData
0x18003fc73  mov     r8d, [rsp+1F8h+columnid]; columnid
0x18003fc7b  mov     rdx, rdi; tableid
0x18003fc7e  mov     rcx, [rsi+18h]; sesid
0x18003fc82  call    cs:__imp_JetSetColumn
0x18003fc88  mov     ecx, eax; int
0x18003fc8a  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003fc8f  mov     ebx, eax
0x18003fc91  mov     [rsp+1F8h+var_1B4], eax
0x18003fc95  test    eax, eax
0x18003fc97  jns     short loc_18003FD02
0x18003fc99  mov     [rsp+1F8h+var_1B8], 35Dh
0x18003fca1  lea     r8, [rsp+1F8h+var_1B4]
0x18003fca6  lea     rdx, [rsp+1F8h+var_1B8]
0x18003fcab  lea     rcx, aBitseseBitsjet_3; "BitsESE::BitsJetDatabaseSession::Update"...
0x18003fcb2  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003fcb7  xorps   xmm0, xmm0
0x18003fcba  movups  [rsp+1F8h+var_D0], xmm0
0x18003fcc2  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003fcc9  mov     [rsp+1F8h+var_D8], rax
0x18003fcd1  mov     [rsp+1F8h+var_C0], ebx
0x18003fcd8  mov     [rsp+1F8h+var_BC], 35Dh
0x18003fce3  mov     [rsp+1F8h+var_B8], 1
0x18003fcee  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003fcf5  lea     rcx, [rsp+1F8h+var_D8]; pExceptionObject
0x18003fcfd  call    _CxxThrowException_0
0x18003fd02  mov     qword ptr [rsp+1F8h+cbData], r14; pcbActual
0x18003fd07  xor     r9d, r9d; cbBookmark
0x18003fd0a  xor     r8d, r8d; pvBookmark
0x18003fd0d  mov     rdx, rdi; tableid
0x18003fd10  mov     rcx, [rsi+18h]; sesid
0x18003fd14  call    cs:__imp_JetUpdate
0x18003fd1a  mov     ecx, eax; int
0x18003fd1c  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003fd21  mov     ebx, eax
0x18003fd23  mov     [rsp+1F8h+var_1B8], eax
0x18003fd27  test    eax, eax
0x18003fd29  jns     short loc_18003FD95
0x18003fd2b  mov     [rsp+1F8h+var_1B4], 35Fh
0x18003fd33  lea     r8, [rsp+1F8h+var_1B8]
0x18003fd38  lea     rdx, [rsp+1F8h+var_1B4]
0x18003fd3d  lea     rcx, aBitseseBitsjet_3; "BitsESE::BitsJetDatabaseSession::Update"...
0x18003fd44  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003fd49  xorps   xmm0, xmm0
0x18003fd4c  movups  [rsp+1F8h+var_70], xmm0
0x18003fd54  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003fd5b  mov     [rsp+1F8h+var_78], rax
0x18003fd63  mov     [rsp+1F8h+var_60], ebx
0x18003fd6a  mov     [rsp+1F8h+var_5C], 35Fh
0x18003fd75  mov     [rsp+1F8h+var_58], 1
0x18003fd80  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003fd87  lea     rcx, [rsp+1F8h+var_78]; pExceptionObject
0x18003fd8f  call    _CxxThrowException_0
0x18003fd95  mov     rdx, [rsp+1F8h+var_1B0]
0x18003fd9a  mov     rdx, [rdx]; Token
0x18003fd9d  xor     ecx, ecx; Thread
0x18003fd9f  call    cs:__imp_SetThreadToken
0x18003fda5  mov     rcx, [rsp+1F8h+var_1B0]
0x18003fdaa  mov     eax, 0FFFFFFFFh
0x18003fdaf  lock xadd [rcx+8], eax
0x18003fdb4  cmp     eax, 1
0x18003fdb7  jnz     short loc_18003FDEB
0x18003fdb9  mov     rcx, [rsp+1F8h+var_1B0]
0x18003fdbe  mov     rdx, [rcx]
0x18003fdc1  lea     rax, [rdx-1]
0x18003fdc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003fdc9  ja      short loc_18003FDE1
0x18003fdcb  mov     rcx, rdx; hObject
0x18003fdce  call    cs:__imp_CloseHandle
0x18003fdd4  mov     rax, [rsp+1F8h+var_1B0]
0x18003fdd9  mov     [rax], r14
0x18003fddc  mov     rcx, [rsp+1F8h+var_1B0]; void *
0x18003fde1  mov     edx, 10h; unsigned __int64
0x18003fde6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003fdeb  xor     eax, eax
0x18003fded  jmp     short loc_18003FDF3
0x18003fdef  mov     eax, [rsp+1F8h+var_1B8]
0x18003fdf3  lea     r11, [rsp+1F8h+var_18]
0x18003fdfb  mov     rbx, [r11+28h]
0x18003fdff  mov     rsi, [r11+30h]
0x18003fe03  mov     rsp, r11
0x18003fe06  pop     r15
0x18003fe08  pop     r14
0x18003fe0a  pop     rdi
0x18003fe0b  retn
```
