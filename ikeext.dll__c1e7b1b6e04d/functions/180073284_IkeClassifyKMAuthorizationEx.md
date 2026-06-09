# IkeClassifyKMAuthorizationEx

- ea: `0x180073284`
- end: `0x1800737ed`
- name: `IkeClassifyKMAuthorizationEx`
- size: `1385`
- prototype: `__int64 __fastcall(__int64, __int64, char, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180073048`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x180016534`
- `0x180016730`
- `0x1800488f0`
- `0x18004890c`
- `0x18004a578`
- `0x18004d2a8`
- `0x180050850`
- `0x1800510ee`
- `0x180052ae8`
- `0x18005bc40`
- `0x18005bce4`
- `0x180060b04`
- `0x180073284`
- `0x180073b74`
- `0x18007c768`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800733a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800733a5`
- `fwpuclnt!FwpsClassifyUser0` at `0x18007355f`
- `fwpuclnt!FwpsClassifyUser0` at `0x18007355f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007376f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800737a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007376f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800737a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007339b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007339b`

## string_xrefs

- `0x1800733b2`: `ConvertSidToStringSidW`

## pseudocode

```c
__int64 __fastcall IkeClassifyKMAuthorizationEx(__int64 a1, __int64 a2, char a3, _DWORD *a4, _DWORD *a5)
{
  _DWORD *v8; // r13
  void *v9; // r12
  __int64 QMFromMM; // rsi
  __int64 v11; // rcx
  DWORD LastError; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  const char *v15; // rsi
  __int64 v16; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v18; // rcx
  int TlsMmLuid; // eax
  __int64 v20; // rax
  int v21; // edx
  int AuthType; // eax
  char v23; // al
  char v24; // cl
  int v25; // eax
  __int64 v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  const WCHAR *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rcx
  const WCHAR *v42; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v48; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v49; // [rsp+58h] [rbp-A8h]
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h] BYREF
  int *v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v54; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v55[2]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v56[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  _BYTE v58[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  _BYTE v61[16]; // [rsp+100h] [rbp+0h] BYREF
  const char *v62; // [rsp+110h] [rbp+10h]
  __int64 v63; // [rsp+118h] [rbp+18h]
  int v64; // [rsp+120h] [rbp+20h] BYREF
  _OWORD *v65; // [rsp+128h] [rbp+28h]
  int v66; // [rsp+130h] [rbp+30h]
  int v67; // [rsp+138h] [rbp+38h]
  int v68; // [rsp+140h] [rbp+40h]
  int v69; // [rsp+148h] [rbp+48h]
  int v70; // [rsp+150h] [rbp+50h]
  int v71; // [rsp+158h] [rbp+58h]
  int v72; // [rsp+160h] [rbp+60h]
  BOOL v73; // [rsp+168h] [rbp+68h]
  int v74; // [rsp+170h] [rbp+70h]
  __int64 v75; // [rsp+178h] [rbp+78h]
  int v76; // [rsp+180h] [rbp+80h]
  int v77; // [rsp+188h] [rbp+88h]

  v48 = a5;
  v51 = 0;
  v49 = a4;
  LODWORD(v52) = 0;
  WORD2(v52) = 0;
  v54 = 0;
  StringSid = 0;
  memset(v55, 0, sizeof(v55));
  v8 = 0;
  Sid = 0;
  v57 = 0;
  memset(v56, 0, sizeof(v56));
  v53 = 0;
  memset_0(&v64, 0, 0x70u);
  *a4 = 0;
  if ( a2 && (*(_DWORD *)(a2 + 72) & 0x100000) != 0 )
  {
    v9 = *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 1096) + 24LL) + 232LL);
    QMFromMM = IkeGetQMFromMM(a1, &v53);
    if ( QMFromMM )
      goto LABEL_50;
  }
  else
  {
    v9 = *(void **)(a1 + 984);
    QMFromMM = 0;
  }
  if ( !v9 )
    goto LABEL_20;
  QMFromMM = GetSidFromToken(v9, &Sid);
  if ( QMFromMM )
    goto LABEL_50;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = GetLastError();
    v14 = WfpReportSysErrorAsWinError(v13, "ConvertSidToStringSidW", LastError, 1);
LABEL_10:
    QMFromMM = v14;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    if ( !a2 || (v15 = "EM", (*(_DWORD *)(a2 + 72) & 0x100000) == 0) )
      v15 = "MM";
    v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v11);
    TlsMmLuid = IkeGetTlsMmLuid(v18);
    WPP_SF_iSsS(
      v16,
      20,
      (unsigned int)WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids,
      TlsMmLuid,
      TlsPeerAddr,
      (__int64)v15,
      (__int64)StringSid);
  }
  v20 = IkeInitializeTokenInformation(v9);
  v8 = v54;
  QMFromMM = v20;
  if ( !v20 )
  {
    v64 = 15;
    v65 = v55;
LABEL_20:
    v21 = 3;
    v66 = 3;
    if ( a2 )
      AuthType = *(_DWORD *)(a2 + 88);
    else
      AuthType = IkeGetAuthType(*(_QWORD *)(a1 + 744));
    v67 = AuthType;
    v23 = ~*(_BYTE *)(a1 + 592);
    v70 = v21;
    v24 = v23;
    v25 = *(_DWORD *)(a1 + 584);
    v71 = v24 & 1;
    v68 = v21;
    v69 = v25;
    v72 = v21;
    v73 = 0;
    if ( v25 == 1 )
      v73 = (*(_DWORD *)(a2 + 72) & 0x100000) != 0;
    v74 = 11;
    if ( v53 )
      v26 = *(_QWORD *)(*(_QWORD *)(v53 + 448) + 32LL);
    else
      v26 = *(_QWORD *)(*(_QWORD *)(a1 + 736) + 64LL);
    v75 = v26;
    v76 = v21;
    v52 = &v64;
    v77 = 0;
    LOWORD(v51) = 98;
    HIDWORD(v51) = 7;
    v27 = FwpsClassifyUser0(gIkeExtGlobals[68].OwningThread, 98, &v51, 0, 0, v56, 0);
    if ( v27 )
    {
      v14 = WfpReportSysErrorAsNtStatus(v28, "FwpsClassifyUser0", v27);
      goto LABEL_10;
    }
    if ( LODWORD(v56[0]) == 4097 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v29 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v30 = IkeGetTlsPeerAddr(v28);
        v32 = IkeGetTlsMmLuid(v31);
        WPP_SF_iS(v29, 21, (unsigned int)WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids, v32, v30);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v53 = IkeGetTlsMmLuid(v28);
        v59 = &v53;
        v60 = 8;
        v34 = (const WCHAR *)IkeGetTlsPeerAddr(v33);
        tlgCreate1Sz_wchar_t((__int64)v61, v34);
        v63 = 38;
        v62 = "KM Auth classification returned BLOCK";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)&dword_180153AFC,
          v35,
          v36,
          5,
          (__int64)v58);
      }
      if ( v9 )
        DumpTokenGroups(v9);
      if ( a2 && *(_DWORD *)(a2 + 88) == 5 )
      {
        v14 = WfpReportSysErrorAsHResult(v28, "FwpsClassifyUser0", 2148074252LL, 1);
        goto LABEL_10;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v37 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v38 = IkeGetTlsPeerAddr(v28);
        v40 = IkeGetTlsMmLuid(v39);
        WPP_SF_iSL(v37, 22, (unsigned int)WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids, v40, v38, v56[0]);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v53 = IkeGetTlsMmLuid(v28);
        v59 = &v53;
        v60 = 8;
        v42 = (const WCHAR *)IkeGetTlsPeerAddr(v41);
        tlgCreate1Sz_wchar_t((__int64)v61, v42);
        v62 = (const char *)&v54;
        LODWORD(v54) = v56[0];
        v63 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)&word_180153AA6,
          v43,
          v44,
          5,
          (__int64)v58);
      }
      *v49 = 1;
      if ( (unsigned int)(LODWORD(v56[0]) - 7) <= 1 )
        *v48 = 1;
    }
  }
LABEL_50:
  WfpMemFree((LPCVOID *)&Sid);
  if ( StringSid )
    LocalFree(StringSid);
  v48 = v8;
  if ( v8 )
    WfpMemFree((LPCVOID *)&v48);
  if ( (a3 & 1) != 0 && LODWORD(v55[0]) )
  {
    LocalFree(*(HLOCAL *)(*((_QWORD *)&v55[0] + 1) + 16LL * (unsigned int)(LODWORD(v55[0]) - 1)));
    WfpMemFree((LPCVOID *)v55 + 1);
  }
  return IkeReturnError(QMFromMM, "IkeClassifyKMAuthorizationEx");
}

```

## disassembly

```asm
0x180073284  mov     [rsp-8+arg_8], rbx
0x180073289  push    rbp
0x18007328a  push    rsi
0x18007328b  push    rdi
0x18007328c  push    r12
0x18007328e  push    r13
0x180073290  push    r14
0x180073292  push    r15
0x180073294  lea     rbp, [rsp-0A0h]
0x18007329c  sub     rsp, 1A0h
0x1800732a3  mov     rax, cs:__security_cookie
0x1800732aa  xor     rax, rsp
0x1800732ad  mov     [rbp+0D0h+var_40], rax
0x1800732b4  mov     rax, [rbp+0D0h+arg_20]
0x1800732bb  xorps   xmm0, xmm0
0x1800732be  xor     edi, edi
0x1800732c0  mov     [rsp+1D0h+var_180], rax
0x1800732c5  xor     eax, eax
0x1800732c7  mov     [rsp+1D0h+var_190], r8d
0x1800732cc  mov     rbx, r9
0x1800732cf  mov     [rsp+1D0h+var_168], rax
0x1800732d4  mov     r14, rdx
0x1800732d7  mov     [rsp+1D0h+var_178], rbx
0x1800732dc  mov     r15, rcx
0x1800732df  mov     dword ptr [rsp+1D0h+var_160], eax
0x1800732e3  lea     r8d, [rax+70h]; Size
0x1800732e7  mov     word ptr [rsp+1D0h+var_160+4], ax
0x1800732ec  xor     edx, edx; Val
0x1800732ee  mov     [rbp+0D0h+var_150], rdi
0x1800732f2  lea     rcx, [rbp+0D0h+var_B0]; void *
0x1800732f6  mov     [rsp+1D0h+StringSid], rdi
0x1800732fb  movups  [rbp+0D0h+var_148], xmm0
0x1800732ff  mov     r13d, edi
0x180073302  mov     [rsp+1D0h+Sid], rdi
0x180073307  movups  [rbp+0D0h+var_138], xmm0
0x18007330b  mov     [rbp+0D0h+var_108], rax
0x18007330f  movups  [rbp+0D0h+var_128], xmm0
0x180073313  mov     [rsp+1D0h+var_158], rdi
0x180073318  movups  [rbp+0D0h+var_118], xmm0
0x18007331c  call    memset_0
0x180073321  mov     [rbx], edi
0x180073323  test    r14, r14
0x180073326  jz      short loc_18007335F
0x180073328  test    dword ptr [r14+48h], 100000h
0x180073330  jz      short loc_18007335F
0x180073332  mov     rax, [r15+448h]
0x180073339  lea     rdx, [rsp+1D0h+var_158]
0x18007333e  mov     rcx, [rax+18h]
0x180073342  mov     r12, [rcx+0E8h]
0x180073349  mov     rcx, r15
0x18007334c  call    IkeGetQMFromMM
0x180073351  mov     rsi, rax
0x180073354  test    rax, rax
0x180073357  jnz     loc_18007375B
0x18007335d  jmp     short loc_180073368
0x18007335f  mov     r12, [r15+3D8h]
0x180073366  xor     esi, esi
0x180073368  lea     rbx, WPP_GLOBAL_Control
0x18007336f  test    r12, r12
0x180073372  jz      loc_180073476
0x180073378  lea     rdx, [rsp+1D0h+Sid]
0x18007337d  mov     rcx, r12; TokenHandle
0x180073380  call    GetSidFromToken
0x180073385  mov     rsi, rax
0x180073388  test    rax, rax
0x18007338b  jnz     loc_18007375B
0x180073391  mov     rcx, [rsp+1D0h+Sid]; Sid
0x180073396  lea     rdx, [rsp+1D0h+StringSid]; StringSid
0x18007339b  call    cs:__imp_ConvertSidToStringSidW
0x1800733a1  test    eax, eax
0x1800733a3  jnz     short loc_1800733C6
0x1800733a5  call    cs:__imp_GetLastError
0x1800733ab  mov     r8d, eax
0x1800733ae  lea     r9d, [rsi+1]
0x1800733b2  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSidW"
0x1800733b9  call    WfpReportSysErrorAsWinError
0x1800733be  mov     rsi, rax
0x1800733c1  jmp     loc_18007375B
0x1800733c6  mov     rdi, cs:WPP_GLOBAL_Control
0x1800733cd  cmp     rdi, rbx
0x1800733d0  jz      short loc_18007343E
0x1800733d2  cmp     byte ptr [rdi+19h], 4
0x1800733d6  jb      short loc_18007343E
0x1800733d8  test    byte ptr [rdi+1Ch], 10h
0x1800733dc  jz      short loc_18007343E
0x1800733de  test    r14, r14
0x1800733e1  jz      short loc_1800733F4
0x1800733e3  test    dword ptr [r14+48h], 100000h
0x1800733eb  lea     rsi, aEm; "EM"
0x1800733f2  jnz     short loc_1800733FB
0x1800733f4  lea     rsi, aMm; "MM"
0x1800733fb  mov     rdi, [rdi+10h]
0x1800733ff  call    IkeGetTlsPeerAddr
0x180073404  mov     rbx, rax
0x180073407  call    IkeGetTlsMmLuid
0x18007340c  mov     r8, [rsp+1D0h+StringSid]
0x180073411  mov     r9, rax
0x180073414  mov     [rsp+1D0h+var_1A0], r8
0x180073419  mov     edx, 14h
0x18007341e  mov     [rsp+1D0h+var_1A8], rsi
0x180073423  lea     r8, WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids
0x18007342a  mov     rcx, rdi
0x18007342d  mov     [rsp+1D0h+var_1B0], rbx
0x180073432  call    WPP_SF_iSsS
0x180073437  lea     rbx, WPP_GLOBAL_Control
0x18007343e  mov     r9d, [rsp+1D0h+var_190]
0x180073443  lea     r8, [rbp+0D0h+var_150]
0x180073447  and     r9d, 1
0x18007344b  lea     rdx, [rbp+0D0h+var_148]
0x18007344f  mov     rcx, r12; TokenHandle
0x180073452  call    IkeInitializeTokenInformation
0x180073457  mov     r13, [rbp+0D0h+var_150]
0x18007345b  mov     rsi, rax
0x18007345e  test    rax, rax
0x180073461  jnz     loc_18007375B
0x180073467  lea     rax, [rbp+0D0h+var_148]
0x18007346b  mov     [rbp+0D0h+var_B0], 0Fh
0x180073472  mov     [rbp+0D0h+var_A8], rax
0x180073476  mov     edx, 3
0x18007347b  mov     [rbp+0D0h+var_A0], edx
0x18007347e  test    r14, r14
0x180073481  jz      short loc_180073489
0x180073483  mov     eax, [r14+58h]
0x180073487  jmp     short loc_180073495
0x180073489  mov     rcx, [r15+2E8h]
0x180073490  call    IkeGetAuthType
0x180073495  mov     [rbp+0D0h+var_98], eax
0x180073498  mov     al, [r15+250h]
0x18007349f  not     al
0x1800734a1  mov     [rbp+0D0h+var_80], edx
0x1800734a4  movzx   ecx, al
0x1800734a7  mov     eax, [r15+248h]
0x1800734ae  and     ecx, 1
0x1800734b1  mov     [rbp+0D0h+var_78], ecx
0x1800734b4  mov     [rbp+0D0h+var_90], edx
0x1800734b7  mov     [rbp+0D0h+var_88], eax
0x1800734ba  mov     [rbp+0D0h+var_70], edx
0x1800734bd  mov     [rbp+0D0h+var_68], 0
0x1800734c4  cmp     eax, 1
0x1800734c7  jnz     short loc_1800734D6
0x1800734c9  test    dword ptr [r14+48h], 100000h
0x1800734d1  jz      short loc_1800734D6
0x1800734d3  mov     [rbp+0D0h+var_68], eax
0x1800734d6  mov     rax, [rsp+1D0h+var_158]
0x1800734db  mov     [rbp+0D0h+var_60], 0Bh
0x1800734e2  test    rax, rax
0x1800734e5  jz      short loc_1800734F4
0x1800734e7  mov     rax, [rax+1C0h]
0x1800734ee  mov     rcx, [rax+20h]
0x1800734f2  jmp     short loc_1800734FF
0x1800734f4  mov     rax, [r15+2E0h]
0x1800734fb  mov     rcx, [rax+40h]
0x1800734ff  mov     [rbp+0D0h+var_58], rcx
0x180073503  lea     rax, [rbp+0D0h+var_B0]
0x180073507  mov     rcx, cs:gIkeExtGlobals
0x18007350e  lea     r8, [rsp+1D0h+var_168]
0x180073513  mov     [rbp+0D0h+var_50], edx
0x180073519  xor     r9d, r9d
0x18007351c  mov     [rsp+1D0h+var_160], rax
0x180073521  mov     edx, 62h ; 'b'
0x180073526  lea     rax, [rbp+0D0h+var_128]
0x18007352a  mov     [rbp+0D0h+var_48], 0
0x180073534  mov     word ptr [rsp+1D0h+var_168], dx
0x180073539  mov     dword ptr [rsp+1D0h+var_168+4], 7
0x180073541  mov     rcx, [rcx+0AB0h]
0x180073548  mov     [rsp+1D0h+var_1A0], 0
0x180073551  mov     [rsp+1D0h+var_1A8], rax
0x180073556  mov     [rsp+1D0h+var_1B0], 0
0x18007355f  call    cs:__imp_FwpsClassifyUser0
0x180073565  test    eax, eax
0x180073567  jz      short loc_18007357D
0x180073569  mov     r8d, eax
0x18007356c  lea     rdx, aFwpsclassifyus; "FwpsClassifyUser0"
0x180073573  call    WfpReportSysErrorAsNtStatus
0x180073578  jmp     loc_1800733BE
0x18007357d  cmp     dword ptr [rbp+0D0h+var_128], 1001h
0x180073584  jnz     loc_18007367B
0x18007358a  mov     rdi, cs:WPP_GLOBAL_Control
0x180073591  cmp     rdi, rbx
0x180073594  jz      short loc_1800735CF
0x180073596  cmp     byte ptr [rdi+19h], 4
0x18007359a  jb      short loc_1800735CF
0x18007359c  test    byte ptr [rdi+1Ch], 10h
0x1800735a0  jz      short loc_1800735CF
0x1800735a2  mov     rdi, [rdi+10h]
0x1800735a6  call    IkeGetTlsPeerAddr
0x1800735ab  mov     rbx, rax
0x1800735ae  call    IkeGetTlsMmLuid
0x1800735b3  mov     r9, rax
0x1800735b6  mov     [rsp+1D0h+var_1B0], rbx
0x1800735bb  mov     edx, 15h
0x1800735c0  lea     r8, WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids
0x1800735c7  mov     rcx, rdi
0x1800735ca  call    WPP_SF_iS
0x1800735cf  mov     eax, cs:dword_180173278
0x1800735d5  cmp     eax, 4
0x1800735d8  jbe     short loc_18007363D
0x1800735da  call    IkeGetTlsMmLuid
0x1800735df  mov     [rsp+1D0h+var_158], rax
0x1800735e4  lea     rax, [rsp+1D0h+var_158]
0x1800735e9  mov     [rbp+0D0h+var_E0], rax
0x1800735ed  mov     [rbp+0D0h+var_D8], 8
0x1800735f5  call    IkeGetTlsPeerAddr
0x1800735fa  mov     rdx, rax
0x1800735fd  lea     rcx, [rbp+0D0h+var_D0]
0x180073601  call    _tlgCreate1Sz_wchar_t
0x180073606  lea     rcx, aKmAuthClassifi; "KM Auth classification returned BLOCK"
0x18007360d  mov     [rbp+0D0h+var_B8], 26h ; '&'
0x180073615  lea     rax, [rbp+0D0h+var_100]
0x180073619  mov     [rbp+0D0h+var_C0], rcx
0x18007361d  mov     [rsp+1D0h+var_1A8], rax
0x180073622  lea     rcx, dword_180173278
0x180073629  lea     rdx, dword_180153AFC
0x180073630  mov     dword ptr [rsp+1D0h+var_1B0], 5
0x180073638  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007363d  test    r12, r12
0x180073640  jz      short loc_18007364A
0x180073642  mov     rcx, r12
0x180073645  call    DumpTokenGroups
0x18007364a  test    r14, r14
0x18007364d  jz      loc_18007375B
0x180073653  cmp     dword ptr [r14+58h], 5
0x180073658  jnz     loc_18007375B
0x18007365e  mov     r9d, 1
0x180073664  lea     rdx, aFwpsclassifyus; "FwpsClassifyUser0"
0x18007366b  mov     r8d, 8009030Ch
0x180073671  call    WfpReportSysErrorAsHResult
0x180073676  jmp     loc_1800733BE
0x18007367b  mov     rdi, cs:WPP_GLOBAL_Control
0x180073682  cmp     rdi, rbx
0x180073685  jz      short loc_1800736C9
0x180073687  cmp     byte ptr [rdi+19h], 4
0x18007368b  jb      short loc_1800736C9
0x18007368d  test    byte ptr [rdi+1Ch], 10h
0x180073691  jz      short loc_1800736C9
0x180073693  mov     rdi, [rdi+10h]
0x180073697  call    IkeGetTlsPeerAddr
0x18007369c  mov     rbx, rax
0x18007369f  call    IkeGetTlsMmLuid
0x1800736a4  mov     r8d, dword ptr [rbp+0D0h+var_128]
0x1800736a8  mov     r9, rax
0x1800736ab  mov     dword ptr [rsp+1D0h+var_1A8], r8d
0x1800736b0  mov     edx, 16h
0x1800736b5  lea     r8, WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids
0x1800736bc  mov     [rsp+1D0h+var_1B0], rbx
0x1800736c1  mov     rcx, rdi
0x1800736c4  call    WPP_SF_iSL
0x1800736c9  mov     eax, cs:dword_180173278
0x1800736cf  cmp     eax, 4
0x1800736d2  jbe     short loc_18007373A
0x1800736d4  call    IkeGetTlsMmLuid
0x1800736d9  mov     [rsp+1D0h+var_158], rax
0x1800736de  lea     rax, [rsp+1D0h+var_158]
0x1800736e3  mov     [rbp+0D0h+var_E0], rax
0x1800736e7  mov     [rbp+0D0h+var_D8], 8
0x1800736ef  call    IkeGetTlsPeerAddr
0x1800736f4  mov     rdx, rax
0x1800736f7  lea     rcx, [rbp+0D0h+var_D0]
0x1800736fb  call    _tlgCreate1Sz_wchar_t
0x180073700  mov     ecx, dword ptr [rbp+0D0h+var_128]
0x180073703  lea     rax, [rbp+0D0h+var_150]
0x180073707  mov     [rbp+0D0h+var_C0], rax
0x18007370b  lea     rdx, word_180153AA6
0x180073712  lea     rax, [rbp+0D0h+var_100]
0x180073716  mov     dword ptr [rbp+0D0h+var_150], ecx
0x180073719  mov     [rsp+1D0h+var_1A8], rax
0x18007371e  lea     rcx, dword_180173278
0x180073725  mov     dword ptr [rsp+1D0h+var_1B0], 5
0x18007372d  mov     [rbp+0D0h+var_B8], 4
0x180073735  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007373a  mov     rax, [rsp+1D0h+var_178]
0x18007373f  mov     dword ptr [rax], 1
0x180073745  mov     eax, dword ptr [rbp+0D0h+var_128]
0x180073748  add     eax, 0FFFFFFF9h
0x18007374b  cmp     eax, 1
0x18007374e  ja      short loc_18007375B
0x180073750  mov     rax, [rsp+1D0h+var_180]
0x180073755  mov     dword ptr [rax], 1
0x18007375b  lea     rcx, [rsp+1D0h+Sid]
0x180073760  call    WfpMemFree
0x180073765  mov     rcx, [rsp+1D0h+StringSid]; hMem
0x18007376a  test    rcx, rcx
0x18007376d  jz      short loc_180073775
0x18007376f  call    cs:__imp_LocalFree
0x180073775  mov     [rsp+1D0h+var_180], r13
0x18007377a  test    r13, r13
0x18007377d  jz      short loc_180073789
0x18007377f  lea     rcx, [rsp+1D0h+var_180]
0x180073784  call    WfpMemFree
0x180073789  test    byte ptr [rsp+1D0h+var_190], 1
0x18007378e  jz      short loc_1800737B4
0x180073790  mov     eax, dword ptr [rbp+0D0h+var_148]
0x180073793  test    eax, eax
0x180073795  jz      short loc_1800737B4
0x180073797  mov     rcx, qword ptr [rbp+0D0h+var_148+8]
0x18007379b  lea     edx, [rax-1]
0x18007379e  add     rdx, rdx
0x1800737a1  mov     rcx, [rcx+rdx*8]; hMem
0x1800737a5  call    cs:__imp_LocalFree
0x1800737ab  lea     rcx, [rbp+0D0h+var_148+8]
  ... truncated ...
```
