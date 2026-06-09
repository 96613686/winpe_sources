# BitsESE::BitsJetDatabaseSession::LoadDatabase(ushort const *)

- ea: `0x18003f03c`
- end: `0x18003f6e5`
- name: `?LoadDatabase@BitsJetDatabaseSession@BitsESE@@AEAAJPEBG@Z`
- size: `1705`
- prototype: `__int64 __fastcall(BitsESE::BitsJetDatabaseSession *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003efe0`

## callees

- `0x18003f03c`
- `0x1800407d0`
- `0x180040c68`
- `0x1800410b0`
- `0x18008e360`
- `0x18009285c`
- `0x1800961b8`
- `0x180099740`
- `0x18009a068`
- `0x18009d024`
- `0x1800a2180`
- `0x1800a3420`
- `0x1800df410`
- `0x1800e0330`
- `0x1800f9948`

## import_xrefs

- `ESENT!JetOpenDatabaseW` at `0x18003f542`
- `ESENT!JetOpenDatabaseW` at `0x18003f542`
- `ESENT!JetAttachDatabaseW` at `0x18003f3ba`
- `ESENT!JetAttachDatabaseW` at `0x18003f3ba`
- `ESENT!JetBeginSessionW` at `0x18003f321`
- `ESENT!JetBeginSessionW` at `0x18003f321`
- `ESENT!JetInit` at `0x18003f298`
- `ESENT!JetInit` at `0x18003f298`
- `ESENT!JetCreateInstanceW` at `0x18003f138`
- `ESENT!JetCreateInstanceW` at `0x18003f138`
- `ESENT!JetCreateDatabaseW` at `0x18003f422`
- `ESENT!JetCreateDatabaseW` at `0x18003f422`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BitsESE::BitsJetDatabaseSession::LoadDatabase(BitsESE::BitsJetDatabaseSession *this, BitsESE *a2)
{
  __int64 v4; // r8
  BitsESE::BitsJetDatabaseSession *v5; // rcx
  int v6; // eax
  JET_ERR InstanceW; // eax
  int v8; // esi
  const unsigned __int16 *v9; // rdx
  int v10; // eax
  int v11; // eax
  JET_ERR v12; // eax
  int v13; // edi
  JET_SESID *v14; // rsi
  JET_ERR v15; // eax
  int v16; // edi
  const WCHAR *v17; // rdx
  JET_ERR v18; // eax
  const WCHAR *v19; // rdx
  JET_ERR DatabaseW; // eax
  int v21; // edi
  char v22; // di
  int v23; // edi
  const WCHAR *v24; // rdx
  JET_ERR v25; // eax
  int v26; // esi
  int v27; // eax
  LSTATUS v28; // eax
  __int64 result; // rax
  const ComError *v30; // rbx
  int v31; // [rsp+30h] [rbp-488h] BYREF
  int v32; // [rsp+34h] [rbp-484h] BYREF
  const ComError *v33; // [rsp+38h] [rbp-480h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-478h] BYREF
  __int128 v35; // [rsp+48h] [rbp-470h]
  int v36; // [rsp+58h] [rbp-460h]
  int v37; // [rsp+5Ch] [rbp-45Ch]
  int v38; // [rsp+60h] [rbp-458h]
  void **v39; // [rsp+A0h] [rbp-418h] BYREF
  __int128 v40; // [rsp+A8h] [rbp-410h]
  int v41; // [rsp+B8h] [rbp-400h]
  int v42; // [rsp+BCh] [rbp-3FCh]
  int v43; // [rsp+C0h] [rbp-3F8h]
  void **v44; // [rsp+100h] [rbp-3B8h] BYREF
  __int128 v45; // [rsp+108h] [rbp-3B0h]
  int v46; // [rsp+118h] [rbp-3A0h]
  int v47; // [rsp+11Ch] [rbp-39Ch]
  int v48; // [rsp+120h] [rbp-398h]
  void **v49; // [rsp+160h] [rbp-358h] BYREF
  __int128 v50; // [rsp+168h] [rbp-350h]
  int v51; // [rsp+178h] [rbp-340h]
  int v52; // [rsp+17Ch] [rbp-33Ch]
  int v53; // [rsp+180h] [rbp-338h]
  void **v54; // [rsp+1C0h] [rbp-2F8h] BYREF
  __int128 v55; // [rsp+1C8h] [rbp-2F0h]
  int v56; // [rsp+1D8h] [rbp-2E0h]
  int v57; // [rsp+1DCh] [rbp-2DCh]
  int v58; // [rsp+1E0h] [rbp-2D8h]
  void **v59; // [rsp+220h] [rbp-298h] BYREF
  __int128 v60; // [rsp+228h] [rbp-290h]
  int v61; // [rsp+238h] [rbp-280h]
  int v62; // [rsp+23Ch] [rbp-27Ch]
  int v63; // [rsp+240h] [rbp-278h]
  void **v64; // [rsp+280h] [rbp-238h] BYREF
  __int128 v65; // [rsp+288h] [rbp-230h]
  int v66; // [rsp+298h] [rbp-220h]
  int v67; // [rsp+29Ch] [rbp-21Ch]
  int v68; // [rsp+2A0h] [rbp-218h]
  void **v69; // [rsp+2E0h] [rbp-1D8h] BYREF
  __int128 v70; // [rsp+2E8h] [rbp-1D0h]
  int v71; // [rsp+2F8h] [rbp-1C0h]
  int v72; // [rsp+2FCh] [rbp-1BCh]
  int v73; // [rsp+300h] [rbp-1B8h]
  void **v74; // [rsp+340h] [rbp-178h] BYREF
  __int128 v75; // [rsp+348h] [rbp-170h]
  int v76; // [rsp+358h] [rbp-160h]
  int v77; // [rsp+35Ch] [rbp-15Ch]
  int v78; // [rsp+360h] [rbp-158h]
  void **v79; // [rsp+3A0h] [rbp-118h] BYREF
  __int128 v80; // [rsp+3A8h] [rbp-110h]
  int v81; // [rsp+3B8h] [rbp-100h]
  int v82; // [rsp+3BCh] [rbp-FCh]
  int v83; // [rsp+3C0h] [rbp-F8h]
  void **v84; // [rsp+400h] [rbp-B8h] BYREF
  __int128 v85; // [rsp+408h] [rbp-B0h]
  LSTATUS v86; // [rsp+418h] [rbp-A0h]
  int v87; // [rsp+41Ch] [rbp-9Ch]
  int v88; // [rsp+420h] [rbp-98h]
  JET_PCWSTR szFilename[2]; // [rsp+460h] [rbp-58h] BYREF
  __int128 v90; // [rsp+470h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
  *(_OWORD *)szFilename = 0;
  v90 = 0;
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)a2 + v4) );
  try
  {
    std::wstring::_Construct<1,unsigned short const *>(szFilename, a2);
    std::wstring::_Append<unsigned short>(szFilename);
    v6 = BitsESE::BitsJetDatabaseSession::ConfigureGlobalJetParams(v5);
    if ( v6 < 0 )
    {
      v35 = 0;
      pExceptionObject = &ComError::`vftable';
      v36 = v6;
      v37 = 368;
      v38 = 1;
      throw (ComError *)&pExceptionObject;
    }
    InstanceW = JetCreateInstanceW((JET_INSTANCE *)this + 2, L"QmgrDatabaseInstance");
    v8 = BitsESE::BitsJetDatabaseSession::JetErrToHR(InstanceW);
    v32 = v8;
    if ( v8 < 0 )
    {
      v31 = 369;
      CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
        "BitsESE::BitsJetDatabaseSession::LoadDatabase",
        &v31,
        &v32);
      v40 = 0;
      v39 = &ComError::`vftable';
      v41 = v8;
      v42 = 369;
      v43 = 1;
      throw (ComError *)&v39;
    }
    if ( BitsESE::BitsJetDatabaseSession::GetCorruptionRegKeyValue() )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
      v10 = BitsESE::BitsJetDatabaseSession::HandleDatabaseCorruption(a2, v9);
      if ( v10 < 0 )
      {
        v45 = 0;
        v44 = &ComError::`vftable';
        v46 = v10;
        v47 = 374;
        v48 = 1;
        throw (ComError *)&v44;
      }
    }
    v11 = BitsESE::BitsJetDatabaseSession::ConfigureInstanceSpecificJetParams(
            (JET_INSTANCE *)this,
            (const unsigned __int16 *)a2);
    if ( v11 < 0 )
    {
      v50 = 0;
      v49 = &ComError::`vftable';
      v51 = v11;
      v52 = 377;
      v53 = 1;
      throw (ComError *)&v49;
    }
    v12 = JetInit((JET_INSTANCE *)this + 2);
    v13 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v12);
    v31 = v13;
    if ( v13 < 0 )
    {
      v32 = 378;
      CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
        "BitsESE::BitsJetDatabaseSession::LoadDatabase",
        &v32,
        &v31);
      v55 = 0;
      v54 = &ComError::`vftable';
      v56 = v13;
      v57 = 378;
      v58 = 1;
      throw (ComError *)&v54;
    }
    v14 = (JET_SESID *)((char *)this + 24);
    v15 = JetBeginSessionW(*((_QWORD *)this + 2), (JET_SESID *)this + 3, 0, 0);
    v16 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v15);
    v31 = v16;
    if ( v16 < 0 )
    {
      v32 = 379;
      CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
        "BitsESE::BitsJetDatabaseSession::LoadDatabase",
        &v32,
        &v31);
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = v16;
      v62 = 379;
      v63 = 1;
      throw (ComError *)&v59;
    }
    v17 = (const WCHAR *)szFilename;
    if ( *((_QWORD *)&v90 + 1) > 7u )
      v17 = szFilename[0];
    v18 = JetAttachDatabaseW(*v14, v17, 0);
    if ( v18 == -1811 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
      v19 = (const WCHAR *)szFilename;
      if ( *((_QWORD *)&v90 + 1) > 7u )
        v19 = szFilename[0];
      DatabaseW = JetCreateDatabaseW(*v14, v19, 0, (JET_DBID *)this + 8, 0);
      v21 = BitsESE::BitsJetDatabaseSession::JetErrToHR(DatabaseW);
      v31 = v21;
      if ( v21 < 0 )
      {
        v32 = 392;
        CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
          "BitsESE::BitsJetDatabaseSession::LoadDatabase",
          &v32,
          &v31);
        v65 = 0;
        v64 = &ComError::`vftable';
        v66 = v21;
        v67 = 392;
        v68 = 1;
        throw (ComError *)&v64;
      }
      v22 = 1;
    }
    else
    {
      v23 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v18);
      v31 = v23;
      if ( v23 < 0 )
      {
        v32 = 399;
        CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
          "BitsESE::BitsJetDatabaseSession::LoadDatabase",
          &v32,
          &v31);
        v70 = 0;
        v69 = &ComError::`vftable';
        v71 = v23;
        v72 = 399;
        v73 = 1;
        throw (ComError *)&v69;
      }
      v22 = 0;
      v24 = (const WCHAR *)szFilename;
      if ( *((_QWORD *)&v90 + 1) > 7u )
        v24 = szFilename[0];
      v25 = JetOpenDatabaseW(*v14, v24, 0, (JET_DBID *)this + 8, 0);
      v26 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v25);
      v31 = v26;
      if ( v26 < 0 )
      {
        v32 = 405;
        CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
          "BitsESE::BitsJetDatabaseSession::LoadDatabase",
          &v32,
          &v31);
        v75 = 0;
        v74 = &ComError::`vftable';
        v76 = v26;
        v77 = 405;
        v78 = 1;
        throw (ComError *)&v74;
      }
    }
    v27 = BitsESE::BitsJetDatabaseSession::PrepareTables(this);
    if ( v27 < 0 )
    {
      v80 = 0;
      v79 = &ComError::`vftable';
      v81 = v27;
      v82 = 409;
      v83 = 1;
      throw (ComError *)&v79;
    }
    if ( v22 )
    {
      v28 = BitsESE::BitsJetDatabaseSession::SetDatabaseVersionCurrentRegKey();
      if ( v28 < 0 )
      {
        v85 = 0;
        v84 = &ComError::`vftable';
        v86 = v28;
        v87 = 413;
        v88 = 1;
        throw (ComError *)&v84;
      }
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids);
    if ( *((_QWORD *)&v90 + 1) > 7u )
      std::_Deallocate<16>((void *)szFilename[0], 2LL * *((_QWORD *)&v90 + 1) + 2);
    result = 0;
  }
  catch ( const ComError *v33 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v30 = v33;
    }
    else
    {
      v30 = v33;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids,
        *((unsigned int *)v30 + 6),
        *((_DWORD *)v30 + 7));
    }
    return *((unsigned int *)v30 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x18003f03c  mov     [rsp+arg_10], rbx
0x18003f041  push    rsi
0x18003f042  push    rdi
0x18003f043  push    r12
0x18003f045  push    r14
0x18003f047  push    r15
0x18003f049  sub     rsp, 490h
0x18003f050  mov     rax, cs:__security_cookie
0x18003f057  xor     rax, rsp
0x18003f05a  mov     [rsp+4B8h+var_38], rax
0x18003f062  mov     rdi, rdx
0x18003f065  mov     r14, rcx
0x18003f068  lea     rax, WPP_GLOBAL_Control
0x18003f06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f076  mov     ebx, 1
0x18003f07b  cmp     rcx, rax
0x18003f07e  jz      short loc_18003F099
0x18003f080  test    [rcx+1Ch], bl
0x18003f083  jz      short loc_18003F099
0x18003f085  lea     edx, [rbx+13h]
0x18003f088  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18003f08f  mov     rcx, [rcx+10h]
0x18003f093  call    WPP_SF_
0x18003f098  nop
0x18003f099  xorps   xmm0, xmm0
0x18003f09c  movups  xmmword ptr [rsp+4B8h+szFilename], xmm0
0x18003f0a4  xorps   xmm1, xmm1
0x18003f0a7  movdqu  [rsp+4B8h+var_48], xmm1
0x18003f0b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f0b4  xor     r12d, r12d
0x18003f0b7  inc     r8
0x18003f0ba  cmp     [rdi+r8*2], r12w
0x18003f0bf  jnz     short loc_18003F0B7
0x18003f0c1  mov     rdx, rdi
0x18003f0c4  lea     rcx, [rsp+4B8h+szFilename]
0x18003f0cc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003f0d1  nop
0x18003f0d2  mov     r8d, 7
0x18003f0d8  lea     rdx, ?DatabaseFileName@BitsJetDatabaseSession@BitsESE@@0QBGB; "qmgr.db"
0x18003f0df  lea     rcx, [rsp+4B8h+szFilename]; Src
0x18003f0e7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003f0ec  call    ?ConfigureGlobalJetParams@BitsJetDatabaseSession@BitsESE@@AEAAJXZ; BitsESE::BitsJetDatabaseSession::ConfigureGlobalJetParams(void)
0x18003f0f1  test    eax, eax
0x18003f0f3  jns     short loc_18003F12A
0x18003f0f5  xorps   xmm0, xmm0
0x18003f0f8  movups  [rsp+4B8h+var_470], xmm0
0x18003f0fd  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f104  mov     [rsp+4B8h+pExceptionObject], rcx
0x18003f109  mov     [rsp+4B8h+var_460], eax
0x18003f10d  mov     [rsp+4B8h+var_45C], 170h
0x18003f115  mov     [rsp+4B8h+var_458], ebx
0x18003f119  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f120  lea     rcx, [rsp+4B8h+pExceptionObject]; pExceptionObject
0x18003f125  call    _CxxThrowException_0
0x18003f12a  lea     r15, [r14+10h]
0x18003f12e  lea     rdx, ?DatabaseInstanceName@BitsJetDatabaseSession@BitsESE@@0QBGB; "QmgrDatabaseInstance"
0x18003f135  mov     rcx, r15; pinstance
0x18003f138  call    cs:__imp_JetCreateInstanceW
0x18003f13e  mov     ecx, eax; int
0x18003f140  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003f145  mov     esi, eax
0x18003f147  mov     [rsp+4B8h+var_484], eax
0x18003f14b  test    eax, eax
0x18003f14d  jns     short loc_18003F1B1
0x18003f14f  mov     edi, 171h
0x18003f154  mov     [rsp+4B8h+var_488], edi
0x18003f158  lea     r8, [rsp+4B8h+var_484]
0x18003f15d  lea     rdx, [rsp+4B8h+var_488]
0x18003f162  lea     rcx, aBitseseBitsjet_7; "BitsESE::BitsJetDatabaseSession::LoadDa"...
0x18003f169  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003f16e  xorps   xmm0, xmm0
0x18003f171  movups  [rsp+4B8h+var_410], xmm0
0x18003f179  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f180  mov     [rsp+4B8h+var_418], rcx
0x18003f188  mov     [rsp+4B8h+var_400], esi
0x18003f18f  mov     [rsp+4B8h+var_3FC], edi
0x18003f196  mov     [rsp+4B8h+var_3F8], ebx
0x18003f19d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f1a4  lea     rcx, [rsp+4B8h+var_418]; pExceptionObject
0x18003f1ac  call    _CxxThrowException_0
0x18003f1b1  call    ?GetCorruptionRegKeyValue@BitsJetDatabaseSession@BitsESE@@SA_NXZ; BitsESE::BitsJetDatabaseSession::GetCorruptionRegKeyValue(void)
0x18003f1b6  test    al, al
0x18003f1b8  jz      loc_18003F23F
0x18003f1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1c5  lea     rax, WPP_GLOBAL_Control
0x18003f1cc  cmp     rcx, rax
0x18003f1cf  jz      short loc_18003F1EC
0x18003f1d1  test    byte ptr [rcx+1Ch], 2
0x18003f1d5  jz      short loc_18003F1EC
0x18003f1d7  mov     edx, 15h
0x18003f1dc  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18003f1e3  mov     rcx, [rcx+10h]
0x18003f1e7  call    WPP_SF_
0x18003f1ec  mov     rcx, rdi; this
0x18003f1ef  call    ?HandleDatabaseCorruption@BitsJetDatabaseSession@BitsESE@@CAJPEBG@Z; BitsESE::BitsJetDatabaseSession::HandleDatabaseCorruption(ushort const *)
0x18003f1f4  test    eax, eax
0x18003f1f6  jns     short loc_18003F23F
0x18003f1f8  xorps   xmm0, xmm0
0x18003f1fb  movups  [rsp+4B8h+var_3B0], xmm0
0x18003f203  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f20a  mov     [rsp+4B8h+var_3B8], rcx
0x18003f212  mov     [rsp+4B8h+var_3A0], eax
0x18003f219  mov     [rsp+4B8h+var_39C], 176h
0x18003f224  mov     [rsp+4B8h+var_398], ebx
0x18003f22b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f232  lea     rcx, [rsp+4B8h+var_3B8]; pExceptionObject
0x18003f23a  call    _CxxThrowException_0
0x18003f23f  mov     rdx, rdi; unsigned __int16 *
0x18003f242  mov     rcx, r14; this
0x18003f245  call    ?ConfigureInstanceSpecificJetParams@BitsJetDatabaseSession@BitsESE@@AEAAJPEBG@Z; BitsESE::BitsJetDatabaseSession::ConfigureInstanceSpecificJetParams(ushort const *)
0x18003f24a  test    eax, eax
0x18003f24c  jns     short loc_18003F295
0x18003f24e  xorps   xmm0, xmm0
0x18003f251  movups  [rsp+4B8h+var_350], xmm0
0x18003f259  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f260  mov     [rsp+4B8h+var_358], rcx
0x18003f268  mov     [rsp+4B8h+var_340], eax
0x18003f26f  mov     [rsp+4B8h+var_33C], 179h
0x18003f27a  mov     [rsp+4B8h+var_338], ebx
0x18003f281  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f288  lea     rcx, [rsp+4B8h+var_358]; pExceptionObject
0x18003f290  call    _CxxThrowException_0
0x18003f295  mov     rcx, r15; pinstance
0x18003f298  call    cs:__imp_JetInit
0x18003f29e  mov     ecx, eax; int
0x18003f2a0  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003f2a5  mov     edi, eax
0x18003f2a7  mov     [rsp+4B8h+var_488], eax
0x18003f2ab  test    eax, eax
0x18003f2ad  jns     short loc_18003F311
0x18003f2af  mov     esi, 17Ah
0x18003f2b4  mov     [rsp+4B8h+var_484], esi
0x18003f2b8  lea     r8, [rsp+4B8h+var_488]
0x18003f2bd  lea     rdx, [rsp+4B8h+var_484]
0x18003f2c2  lea     rcx, aBitseseBitsjet_7; "BitsESE::BitsJetDatabaseSession::LoadDa"...
0x18003f2c9  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003f2ce  xorps   xmm0, xmm0
0x18003f2d1  movups  [rsp+4B8h+var_2F0], xmm0
0x18003f2d9  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f2e0  mov     [rsp+4B8h+var_2F8], rcx
0x18003f2e8  mov     [rsp+4B8h+var_2E0], edi
0x18003f2ef  mov     [rsp+4B8h+var_2DC], esi
0x18003f2f6  mov     [rsp+4B8h+var_2D8], ebx
0x18003f2fd  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f304  lea     rcx, [rsp+4B8h+var_2F8]; pExceptionObject
0x18003f30c  call    _CxxThrowException_0
0x18003f311  lea     rsi, [r14+18h]
0x18003f315  xor     r9d, r9d; szPassword
0x18003f318  xor     r8d, r8d; szUserName
0x18003f31b  mov     rdx, rsi; psesid
0x18003f31e  mov     rcx, [r15]; instance
0x18003f321  call    cs:__imp_JetBeginSessionW
0x18003f327  mov     ecx, eax; int
0x18003f329  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003f32e  mov     edi, eax
0x18003f330  mov     [rsp+4B8h+var_488], eax
0x18003f334  test    eax, eax
0x18003f336  jns     short loc_18003F39A
0x18003f338  mov     esi, 17Bh
0x18003f33d  mov     [rsp+4B8h+var_484], esi
0x18003f341  lea     r8, [rsp+4B8h+var_488]
0x18003f346  lea     rdx, [rsp+4B8h+var_484]
0x18003f34b  lea     rcx, aBitseseBitsjet_7; "BitsESE::BitsJetDatabaseSession::LoadDa"...
0x18003f352  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003f357  xorps   xmm0, xmm0
0x18003f35a  movups  [rsp+4B8h+var_290], xmm0
0x18003f362  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f369  mov     [rsp+4B8h+var_298], rcx
0x18003f371  mov     [rsp+4B8h+var_280], edi
0x18003f378  mov     [rsp+4B8h+var_27C], esi
0x18003f37f  mov     [rsp+4B8h+var_278], ebx
0x18003f386  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f38d  lea     rcx, [rsp+4B8h+var_298]; pExceptionObject
0x18003f395  call    _CxxThrowException_0
0x18003f39a  lea     rdx, [rsp+4B8h+szFilename]
0x18003f3a2  cmp     qword ptr [rsp+4B8h+var_48+8], 7
0x18003f3ab  cmova   rdx, [rsp+4B8h+szFilename]; szFilename
0x18003f3b4  xor     r8d, r8d; grbit
0x18003f3b7  mov     rcx, [rsi]; sesid
0x18003f3ba  call    cs:__imp_JetAttachDatabaseW
0x18003f3c0  cmp     eax, 0FFFFF8EDh
0x18003f3c5  jnz     loc_18003F4A3
0x18003f3cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3d2  lea     r15, WPP_GLOBAL_Control
0x18003f3d9  cmp     rcx, r15
0x18003f3dc  jz      short loc_18003F3F9
0x18003f3de  test    byte ptr [rcx+1Ch], 2
0x18003f3e2  jz      short loc_18003F3F9
0x18003f3e4  mov     edx, 16h
0x18003f3e9  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x18003f3f0  mov     rcx, [rcx+10h]
0x18003f3f4  call    WPP_SF_
0x18003f3f9  lea     rdx, [rsp+4B8h+szFilename]
0x18003f401  cmp     qword ptr [rsp+4B8h+var_48+8], 7
0x18003f40a  cmova   rdx, [rsp+4B8h+szFilename]; szFilename
0x18003f413  lea     r9, [r14+20h]; pdbid
0x18003f417  mov     [rsp+4B8h+grbit], r12d; grbit
0x18003f41c  xor     r8d, r8d; szConnect
0x18003f41f  mov     rcx, [rsi]; sesid
0x18003f422  call    cs:__imp_JetCreateDatabaseW
0x18003f428  mov     ecx, eax; int
0x18003f42a  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003f42f  mov     edi, eax
0x18003f431  mov     [rsp+4B8h+var_488], eax
0x18003f435  test    eax, eax
0x18003f437  jns     short loc_18003F49B
0x18003f439  mov     esi, 188h
0x18003f43e  mov     [rsp+4B8h+var_484], esi
0x18003f442  lea     r8, [rsp+4B8h+var_488]
0x18003f447  lea     rdx, [rsp+4B8h+var_484]
0x18003f44c  lea     rcx, aBitseseBitsjet_7; "BitsESE::BitsJetDatabaseSession::LoadDa"...
0x18003f453  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003f458  xorps   xmm0, xmm0
0x18003f45b  movups  [rsp+4B8h+var_230], xmm0
0x18003f463  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f46a  mov     [rsp+4B8h+var_238], rcx
0x18003f472  mov     [rsp+4B8h+var_220], edi
0x18003f479  mov     [rsp+4B8h+var_21C], esi
0x18003f480  mov     [rsp+4B8h+var_218], ebx
0x18003f487  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f48e  lea     rcx, [rsp+4B8h+var_238]; pExceptionObject
0x18003f496  call    _CxxThrowException_0
0x18003f49b  mov     dil, bl
0x18003f49e  jmp     loc_18003F5C2
0x18003f4a3  mov     ecx, eax; int
0x18003f4a5  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003f4aa  mov     edi, eax
0x18003f4ac  mov     [rsp+4B8h+var_488], eax
0x18003f4b0  test    eax, eax
0x18003f4b2  jns     short loc_18003F516
0x18003f4b4  mov     esi, 18Fh
0x18003f4b9  mov     [rsp+4B8h+var_484], esi
0x18003f4bd  lea     r8, [rsp+4B8h+var_488]
0x18003f4c2  lea     rdx, [rsp+4B8h+var_484]
0x18003f4c7  lea     rcx, aBitseseBitsjet_7; "BitsESE::BitsJetDatabaseSession::LoadDa"...
0x18003f4ce  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003f4d3  xorps   xmm0, xmm0
0x18003f4d6  movups  [rsp+4B8h+var_1D0], xmm0
0x18003f4de  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f4e5  mov     [rsp+4B8h+var_1D8], rcx
0x18003f4ed  mov     [rsp+4B8h+var_1C0], edi
0x18003f4f4  mov     [rsp+4B8h+var_1BC], esi
0x18003f4fb  mov     [rsp+4B8h+var_1B8], ebx
0x18003f502  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f509  lea     rcx, [rsp+4B8h+var_1D8]; pExceptionObject
0x18003f511  call    _CxxThrowException_0
0x18003f516  mov     dil, r12b
0x18003f519  lea     rdx, [rsp+4B8h+szFilename]
0x18003f521  cmp     qword ptr [rsp+4B8h+var_48+8], 7
0x18003f52a  cmova   rdx, [rsp+4B8h+szFilename]; szFilename
0x18003f533  lea     r9, [r14+20h]; pdbid
0x18003f537  mov     [rsp+4B8h+grbit], r12d; grbit
0x18003f53c  xor     r8d, r8d; szConnect
0x18003f53f  mov     rcx, [rsi]; sesid
0x18003f542  call    cs:__imp_JetOpenDatabaseW
0x18003f548  mov     ecx, eax; int
0x18003f54a  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003f54f  mov     esi, eax
0x18003f551  mov     [rsp+4B8h+var_488], eax
0x18003f555  test    eax, eax
0x18003f557  jns     short loc_18003F5BB
0x18003f559  mov     edi, 195h
0x18003f55e  mov     [rsp+4B8h+var_484], edi
0x18003f562  lea     r8, [rsp+4B8h+var_488]
0x18003f567  lea     rdx, [rsp+4B8h+var_484]
0x18003f56c  lea     rcx, aBitseseBitsjet_7; "BitsESE::BitsJetDatabaseSession::LoadDa"...
0x18003f573  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003f578  xorps   xmm0, xmm0
0x18003f57b  movups  [rsp+4B8h+var_170], xmm0
0x18003f583  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f58a  mov     [rsp+4B8h+var_178], rcx
0x18003f592  mov     [rsp+4B8h+var_160], esi
0x18003f599  mov     [rsp+4B8h+var_15C], edi
0x18003f5a0  mov     [rsp+4B8h+var_158], ebx
0x18003f5a7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f5ae  lea     rcx, [rsp+4B8h+var_178]; pExceptionObject
0x18003f5b6  call    _CxxThrowException_0
0x18003f5bb  lea     r15, WPP_GLOBAL_Control
0x18003f5c2  mov     rcx, r14; this
0x18003f5c5  call    ?PrepareTables@BitsJetDatabaseSession@BitsESE@@AEAAJXZ; BitsESE::BitsJetDatabaseSession::PrepareTables(void)
0x18003f5ca  test    eax, eax
0x18003f5cc  jns     short loc_18003F615
0x18003f5ce  xorps   xmm0, xmm0
0x18003f5d1  movups  [rsp+4B8h+var_110], xmm0
0x18003f5d9  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f5e0  mov     [rsp+4B8h+var_118], rcx
0x18003f5e8  mov     [rsp+4B8h+var_100], eax
0x18003f5ef  mov     [rsp+4B8h+var_FC], 199h
0x18003f5fa  mov     [rsp+4B8h+var_F8], ebx
0x18003f601  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f608  lea     rcx, [rsp+4B8h+var_118]; pExceptionObject
0x18003f610  call    _CxxThrowException_0
0x18003f615  test    dil, dil
0x18003f618  jz      short loc_18003F66A
0x18003f61a  call    ?SetDatabaseVersionCurrentRegKey@BitsJetDatabaseSession@BitsESE@@CAJXZ; BitsESE::BitsJetDatabaseSession::SetDatabaseVersionCurrentRegKey(void)
0x18003f61f  test    eax, eax
0x18003f621  jns     short loc_18003F66A
0x18003f623  xorps   xmm0, xmm0
0x18003f626  movups  [rsp+4B8h+var_B0], xmm0
0x18003f62e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
  ... truncated ...
```
