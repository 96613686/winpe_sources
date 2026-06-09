# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x18001964c`
- end: `0x18001986a`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `542`
- prototype: `__int64 __fastcall(unsigned __int16 **this, const unsigned __int16 *, const unsigned __int16 *, const struct _RSDS *, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800193f0`

## callees

- `0x1800017e0`
- `0x180008f10`
- `0x180009838`
- `0x18000a5d4`
- `0x18000c120`
- `0x180014550`
- `0x180018ad0`
- `0x180018b6c`
- `0x180019194`
- `0x18001964c`
- `0x180019870`
- `0x180019934`
- `0x180019a34`
- `0x18001a62c`
- `0x18001a6dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001968b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001969c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001968b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001969c`

## string_xrefs

- `0x180019764`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _RSDS *a4,
        bool a5)
{
  const char *v9; // rdi
  char *v10; // rbx
  char *v11; // rax
  const char *v12; // r15
  int v13; // ecx
  unsigned __int16 *v14; // rbx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v15; // rcx
  __int64 v16; // rcx
  int v17; // edi
  __int64 v18; // rcx
  unsigned __int16 *Buffer; // rax
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v20; // rcx
  int v21; // eax
  __int64 v22; // r8
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v23; // rcx
  unsigned int v25; // [rsp+30h] [rbp-51h] BYREF
  __int64 v26; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-41h] BYREF
  int v28; // [rsp+48h] [rbp-39h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-31h] BYREF
  char v30[16]; // [rsp+58h] [rbp-29h] BYREF
  int *v31; // [rsp+68h] [rbp-19h]
  __int64 v32; // [rsp+70h] [rbp-11h]
  unsigned int *v33; // [rsp+78h] [rbp-9h]
  __int64 v34; // [rsp+80h] [rbp-1h]

  v9 = (char *)a4 + 24;
  v10 = strrchr((const char *)a4 + 24, 47);
  v11 = strrchr(v9, 92);
  if ( v10 > v11 )
    v11 = v10;
  v12 = v11 + 1;
  if ( !v11 )
    v12 = v9;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v27);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v13,
    (unsigned int)&v27,
    (_DWORD)a2,
    (_DWORD)v12,
    (__int64)a4);
  ATL::CSimpleStringT<unsigned short,0>::Append((__int64)&v27, (__int64)L"\\");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&v27, v12);
  v14 = v27;
  if ( Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v15, v27) )
  {
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v16, TraceMerge_NGEN_CandidateEncountered_ExistingPDB, v14);
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                          this + 7,
                          (__int64)a2)
      || (v17 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
                  (Microsoft::Windows::Performance::CNGenEventTraceExtender *)this,
                  v14,
                  v12,
                  a4),
          v17 >= 0) )
    {
      v17 = 0;
    }
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v26,
      L"%wsngen.exe createpdb %ws %ws",
      this[a5 + 5],
      a3,
      a2);
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v18, TraceMerge_NGEN_CreatingPDB_Start, v26);
    v25 = 0;
    Buffer = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v26);
    v21 = Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(v20, Buffer, &v25);
    v17 = v21;
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    {
      v29 = v25;
      v28 = v21;
      v31 = &v28;
      v32 = 4;
      v33 = &v29;
      v34 = 4;
      McGenEventWrite_EventWriteTransfer(v25, TraceMerge_NGEN_CreatingPDB_Stop, v22, 3, v30);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    if ( v17 >= 0 )
    {
      if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                            this + 7,
                            (__int64)a2)
        || !Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v23, v14)
        || (v17 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
                    (Microsoft::Windows::Performance::CNGenEventTraceExtender *)this,
                    v14,
                    v12,
                    a4),
            v17 >= 0) )
      {
        v17 = 0;
      }
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001964c  push    rbp
0x18001964e  push    rbx
0x18001964f  push    rsi
0x180019650  push    rdi
0x180019651  push    r12
0x180019653  push    r13
0x180019655  push    r14
0x180019657  push    r15
0x180019659  lea     rbp, [rsp-17h]
0x18001965e  sub     rsp, 98h
0x180019665  mov     rax, cs:__security_cookie
0x18001966c  xor     rax, rsp
0x18001966f  mov     [rbp+4Fh+var_48], rax
0x180019673  mov     r13, r9
0x180019676  mov     r12, r8
0x180019679  mov     r14, rdx
0x18001967c  mov     rsi, rcx
0x18001967f  lea     rdi, [r9+18h]
0x180019683  mov     edx, 2Fh ; '/'; Ch
0x180019688  mov     rcx, rdi; Str
0x18001968b  call    cs:__imp_strrchr
0x180019691  mov     rbx, rax
0x180019694  mov     edx, 5Ch ; '\'; Ch
0x180019699  mov     rcx, rdi; Str
0x18001969c  call    cs:__imp_strrchr
0x1800196a2  cmp     rbx, rax
0x1800196a5  cmova   rax, rbx
0x1800196a9  lea     r15, [rax+1]
0x1800196ad  test    rax, rax
0x1800196b0  cmovz   r15, rdi
0x1800196b4  lea     rcx, [rbp+4Fh+var_90]
0x1800196b8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800196bd  nop
0x1800196be  mov     [rsp+0D0h+var_B0], r13
0x1800196c3  mov     r9, r15
0x1800196c6  mov     r8, r14
0x1800196c9  lea     rdx, [rbp+4Fh+var_90]
0x1800196cd  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x1800196d2  lea     rdx, asc_180029930; "\\"
0x1800196d9  lea     rcx, [rbp+4Fh+var_90]
0x1800196dd  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800196e2  mov     rdx, r15
0x1800196e5  lea     rcx, [rbp+4Fh+var_90]
0x1800196e9  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x1800196ee  mov     rbx, [rbp+4Fh+var_90]
0x1800196f2  mov     rdx, rbx; unsigned __int16 *
0x1800196f5  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x1800196fa  test    al, al
0x1800196fc  jz      short loc_180019748
0x1800196fe  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180019705  jz      short loc_180019716
0x180019707  mov     r8, rbx
0x18001970a  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x180019711  call    McTemplateU0z_EventWriteTransfer
0x180019716  lea     rcx, [rsi+38h]
0x18001971a  mov     rdx, r14
0x18001971d  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x180019722  test    eax, eax
0x180019724  jz      short loc_180019741
0x180019726  mov     r9, r13; struct _RSDS *
0x180019729  mov     r8, r15; char *
0x18001972c  mov     rdx, rbx; unsigned __int16 *
0x18001972f  mov     rcx, rsi; this
0x180019732  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x180019737  mov     edi, eax
0x180019739  test    eax, eax
0x18001973b  js      loc_18001983F
0x180019741  xor     edi, edi
0x180019743  jmp     loc_18001983F
0x180019748  lea     rcx, [rbp+4Fh+var_98]
0x18001974c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019751  nop
0x180019752  movzx   r8d, [rbp+4Fh+arg_20]
0x180019757  mov     [rsp+0D0h+var_B0], r14
0x18001975c  mov     r9, r12
0x18001975f  mov     r8, [rsi+r8*8+28h]
0x180019764  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x18001976b  lea     rcx, [rbp+4Fh+var_98]
0x18001976f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180019774  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001977b  jz      short loc_18001978D
0x18001977d  mov     r8, [rbp+4Fh+var_98]
0x180019781  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x180019788  call    McTemplateU0z_EventWriteTransfer
0x18001978d  xor     r12d, r12d
0x180019790  mov     [rbp+4Fh+var_A0], r12d
0x180019794  lea     rcx, [rbp+4Fh+var_98]
0x180019798  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18001979d  mov     rdx, rax; unsigned __int16 *
0x1800197a0  lea     r8, [rbp+4Fh+var_A0]; unsigned int *
0x1800197a4  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x1800197a9  mov     edi, eax
0x1800197ab  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x1800197b2  jz      short loc_1800197F8
0x1800197b4  mov     ecx, [rbp+4Fh+var_A0]
0x1800197b7  mov     [rbp+4Fh+var_80], ecx
0x1800197ba  mov     [rbp+4Fh+var_88], eax
0x1800197bd  lea     rax, [rbp+4Fh+var_88]
0x1800197c1  mov     [rbp+4Fh+var_68], rax
0x1800197c5  mov     [rbp+4Fh+var_60], 4
0x1800197cd  lea     rax, [rbp+4Fh+var_80]
0x1800197d1  mov     [rbp+4Fh+var_58], rax
0x1800197d5  mov     [rbp+4Fh+var_50], 4
0x1800197dd  lea     rax, [rbp+4Fh+var_78]
0x1800197e1  mov     [rsp+0D0h+var_B0], rax
0x1800197e6  lea     r9d, [r12+3]
0x1800197eb  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop
0x1800197f2  call    McGenEventWrite_EventWriteTransfer
0x1800197f7  nop
0x1800197f8  mov     rcx, [rbp+4Fh+var_98]
0x1800197fc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019800  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019805  test    edi, edi
0x180019807  js      short loc_18001983F
0x180019809  lea     rcx, [rsi+38h]
0x18001980d  mov     rdx, r14
0x180019810  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x180019815  test    eax, eax
0x180019817  jz      short loc_18001983C
0x180019819  mov     rdx, rbx; unsigned __int16 *
0x18001981c  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x180019821  test    al, al
0x180019823  jz      short loc_18001983C
0x180019825  mov     r9, r13; struct _RSDS *
0x180019828  mov     r8, r15; char *
0x18001982b  mov     rdx, rbx; unsigned __int16 *
0x18001982e  mov     rcx, rsi; this
0x180019831  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x180019836  test    eax, eax
0x180019838  mov     edi, eax
0x18001983a  js      short loc_18001983F
0x18001983c  mov     edi, r12d
0x18001983f  lea     rcx, [rbx-18h]; this
0x180019843  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019848  mov     eax, edi
0x18001984a  mov     rcx, [rbp+4Fh+var_48]
0x18001984e  xor     rcx, rsp; StackCookie
0x180019851  call    __security_check_cookie
0x180019856  add     rsp, 98h
0x18001985d  pop     r15
0x18001985f  pop     r14
0x180019861  pop     r13
0x180019863  pop     r12
0x180019865  pop     rdi
0x180019866  pop     rsi
0x180019867  pop     rbx
0x180019868  pop     rbp
0x180019869  retn
```
