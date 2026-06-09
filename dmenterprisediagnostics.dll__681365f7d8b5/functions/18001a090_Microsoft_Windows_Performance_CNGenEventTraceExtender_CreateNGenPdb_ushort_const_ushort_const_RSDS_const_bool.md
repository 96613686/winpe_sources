# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x18001a090`
- end: `0x18001a2bb`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `555`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const struct _RSDS *@<r9>, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180019e28`

## callees

- `0x180001800`
- `0x18000938c`
- `0x180009d08`
- `0x18000ab4c`
- `0x18000c6e4`
- `0x180014dc0`
- `0x1800194c8`
- `0x18001957c`
- `0x180019bb0`
- `0x18001a090`
- `0x18001a2c4`
- `0x18001a388`
- `0x18001a4a8`
- `0x18001b0cc`
- `0x18001b184`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001a0cf`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001a0e6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001a0cf`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001a0e6`

## string_xrefs

- `0x18001a1b4`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
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
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+58h] [rbp-29h] BYREF
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
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v13,
    (unsigned int)&v27,
    (_DWORD)a2,
    (_DWORD)v12,
    (__int64)a4);
  ATL::CSimpleStringT<unsigned short,0>::Append(&v27, L"\\");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&v27, v12);
  v14 = v27;
  if ( Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v15, v27) )
  {
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v16, TraceMerge_NGEN_CandidateEncountered_ExistingPDB, v14);
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                          (char *)this + 56,
                          a2)
      || (v17 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4), v17 >= 0) )
    {
      v17 = 0;
    }
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v26,
      L"%wsngen.exe createpdb %ws %ws",
      *((_QWORD *)this + a5 + 5),
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
      McGenEventWrite_EventWriteTransfer(v25, (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_CreatingPDB_Stop, v22, 3u, &v30);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    if ( v17 >= 0 )
    {
      if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                            (char *)this + 56,
                            a2)
        || !Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v23, v14)
        || (v17 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4), v17 >= 0) )
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
0x18001a090  push    rbp
0x18001a092  push    rbx
0x18001a093  push    rsi
0x18001a094  push    rdi
0x18001a095  push    r12
0x18001a097  push    r13
0x18001a099  push    r14
0x18001a09b  push    r15
0x18001a09d  lea     rbp, [rsp-17h]
0x18001a0a2  sub     rsp, 98h
0x18001a0a9  mov     rax, cs:__security_cookie
0x18001a0b0  xor     rax, rsp
0x18001a0b3  mov     [rbp+4Fh+var_48], rax
0x18001a0b7  mov     r13, r9
0x18001a0ba  mov     r12, r8
0x18001a0bd  mov     r14, rdx
0x18001a0c0  mov     rsi, rcx
0x18001a0c3  lea     rdi, [r9+18h]
0x18001a0c7  mov     edx, 2Fh ; '/'; Ch
0x18001a0cc  mov     rcx, rdi; Str
0x18001a0cf  call    cs:__imp_strrchr
0x18001a0d6  nop     dword ptr [rax+rax+00h]
0x18001a0db  mov     rbx, rax
0x18001a0de  mov     edx, 5Ch ; '\'; Ch
0x18001a0e3  mov     rcx, rdi; Str
0x18001a0e6  call    cs:__imp_strrchr
0x18001a0ed  nop     dword ptr [rax+rax+00h]
0x18001a0f2  cmp     rbx, rax
0x18001a0f5  cmova   rax, rbx
0x18001a0f9  lea     r15, [rax+1]
0x18001a0fd  test    rax, rax
0x18001a100  cmovz   r15, rdi
0x18001a104  lea     rcx, [rbp+4Fh+var_90]
0x18001a108  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001a10d  nop
0x18001a10e  mov     [rsp+0D0h+var_B0], r13
0x18001a113  mov     r9, r15
0x18001a116  mov     r8, r14
0x18001a119  lea     rdx, [rbp+4Fh+var_90]
0x18001a11d  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x18001a122  lea     rdx, asc_18002A930; "\\"
0x18001a129  lea     rcx, [rbp+4Fh+var_90]
0x18001a12d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001a132  mov     rdx, r15
0x18001a135  lea     rcx, [rbp+4Fh+var_90]
0x18001a139  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18001a13e  mov     rbx, [rbp+4Fh+var_90]
0x18001a142  mov     rdx, rbx; unsigned __int16 *
0x18001a145  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x18001a14a  test    al, al
0x18001a14c  jz      short loc_18001A198
0x18001a14e  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001a155  jz      short loc_18001A166
0x18001a157  mov     r8, rbx
0x18001a15a  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x18001a161  call    McTemplateU0z_EventWriteTransfer
0x18001a166  lea     rcx, [rsi+38h]
0x18001a16a  mov     rdx, r14
0x18001a16d  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x18001a172  test    eax, eax
0x18001a174  jz      short loc_18001A191
0x18001a176  mov     r9, r13; struct _RSDS *
0x18001a179  mov     r8, r15; char *
0x18001a17c  mov     rdx, rbx; unsigned __int16 *
0x18001a17f  mov     rcx, rsi; this
0x18001a182  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x18001a187  mov     edi, eax
0x18001a189  test    eax, eax
0x18001a18b  js      loc_18001A28F
0x18001a191  xor     edi, edi
0x18001a193  jmp     loc_18001A28F
0x18001a198  lea     rcx, [rbp+4Fh+var_98]
0x18001a19c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001a1a1  nop
0x18001a1a2  movzx   r8d, [rbp+4Fh+arg_20]
0x18001a1a7  mov     [rsp+0D0h+var_B0], r14
0x18001a1ac  mov     r9, r12
0x18001a1af  mov     r8, [rsi+r8*8+28h]
0x18001a1b4  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x18001a1bb  lea     rcx, [rbp+4Fh+var_98]
0x18001a1bf  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001a1c4  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001a1cb  jz      short loc_18001A1DD
0x18001a1cd  mov     r8, [rbp+4Fh+var_98]
0x18001a1d1  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x18001a1d8  call    McTemplateU0z_EventWriteTransfer
0x18001a1dd  xor     r12d, r12d
0x18001a1e0  mov     [rbp+4Fh+var_A0], r12d
0x18001a1e4  lea     rcx, [rbp+4Fh+var_98]
0x18001a1e8  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18001a1ed  mov     rdx, rax; unsigned __int16 *
0x18001a1f0  lea     r8, [rbp+4Fh+var_A0]; unsigned int *
0x18001a1f4  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x18001a1f9  mov     edi, eax
0x18001a1fb  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001a202  jz      short loc_18001A248
0x18001a204  mov     ecx, [rbp+4Fh+var_A0]
0x18001a207  mov     [rbp+4Fh+var_80], ecx
0x18001a20a  mov     [rbp+4Fh+var_88], eax
0x18001a20d  lea     rax, [rbp+4Fh+var_88]
0x18001a211  mov     [rbp+4Fh+var_68], rax
0x18001a215  mov     [rbp+4Fh+var_60], 4
0x18001a21d  lea     rax, [rbp+4Fh+var_80]
0x18001a221  mov     [rbp+4Fh+var_58], rax
0x18001a225  mov     [rbp+4Fh+var_50], 4
0x18001a22d  lea     rax, [rbp+4Fh+var_78]
0x18001a231  mov     [rsp+0D0h+var_B0], rax
0x18001a236  lea     r9d, [r12+3]
0x18001a23b  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop
0x18001a242  call    McGenEventWrite_EventWriteTransfer
0x18001a247  nop
0x18001a248  mov     rcx, [rbp+4Fh+var_98]
0x18001a24c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a250  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a255  test    edi, edi
0x18001a257  js      short loc_18001A28F
0x18001a259  lea     rcx, [rsi+38h]
0x18001a25d  mov     rdx, r14
0x18001a260  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x18001a265  test    eax, eax
0x18001a267  jz      short loc_18001A28C
0x18001a269  mov     rdx, rbx; unsigned __int16 *
0x18001a26c  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x18001a271  test    al, al
0x18001a273  jz      short loc_18001A28C
0x18001a275  mov     r9, r13; struct _RSDS *
0x18001a278  mov     r8, r15; char *
0x18001a27b  mov     rdx, rbx; unsigned __int16 *
0x18001a27e  mov     rcx, rsi; this
0x18001a281  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x18001a286  test    eax, eax
0x18001a288  mov     edi, eax
0x18001a28a  js      short loc_18001A28F
0x18001a28c  mov     edi, r12d
0x18001a28f  lea     rcx, [rbx-18h]; this
0x18001a293  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a298  mov     eax, edi
0x18001a29a  mov     rcx, [rbp+4Fh+var_48]
0x18001a29e  xor     rcx, rsp; StackCookie
0x18001a2a1  call    __security_check_cookie
0x18001a2a6  add     rsp, 98h
0x18001a2ad  pop     r15
0x18001a2af  pop     r14
0x18001a2b1  pop     r13
0x18001a2b3  pop     r12
0x18001a2b5  pop     rdi
0x18001a2b6  pop     rsi
0x18001a2b7  pop     rbx
0x18001a2b8  pop     rbp
0x18001a2b9  retn
```
