# SampDsReplicateAccountEx

- ea: `0x1803f7648`
- end: `0x1803f7bec`
- name: `SampDsReplicateAccountEx`
- size: `1444`
- prototype: `__int64 __usercall@<rax>(PUNICODE_STRING DnsHostName@<rcx>, __int64, unsigned __int8, int, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803c8330`
- `0x1803f7610`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000bb80`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180021aa3`
- `0x180030af8`
- `0x180030b60`
- `0x1803af580`
- `0x1803af8ac`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803b2e08`
- `0x1803e00d0`
- `0x1803e042c`
- `0x1803e0760`
- `0x1803f3e28`
- `0x1803f7648`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1803f7a3a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1803f7a3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803f7830`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803f7830`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f7881`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f7898`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f78a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f7881`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f7898`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f78a6`
- `ntdll!RtlCopySid` at `0x1803f7a24`
- `ntdll!RtlCopySid` at `0x1803f7a24`
- `ntdll!RtlDnsHostNameToComputerName` at `0x1803f7722`
- `ntdll!RtlDnsHostNameToComputerName` at `0x1803f7722`
- `SAMSRV!SampUsingDsData` at `0x1803f777d`
- `SAMSRV!SampUsingDsData` at `0x1803f777d`
- `SAMSRV!SampGetDomainObjectFromIndex` at `0x1803f778c`
- `SAMSRV!SampGetDomainObjectFromIndex` at `0x1803f778c`

## pseudocode

```c
__int64 __fastcall SampDsReplicateAccountEx(
        PUNICODE_STRING DnsHostName,
        char a2,
        __int64 a3,
        ULONG a4,
        __int64 a5,
        unsigned __int8 a6,
        char a7,
        __int64 a8)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned __int16 *v12; // rdi
  void *v13; // rsi
  PSID v14; // r13
  int v15; // ebx
  int v16; // esi
  char v17; // al
  __int64 DomainObjectFromIndex; // r13
  int v19; // eax
  HLOCAL v20; // rax
  HLOCAL v21; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // r9
  BOOL v29; // ebx
  int v30; // eax
  void *ObjectSid; // rax
  PSID v32; // rdi
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // r9
  BOOL v37; // edi
  int v38; // eax
  int v39; // eax
  PSID SourceSid; // [rsp+50h] [rbp-B0h] BYREF
  void *v41; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v42; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v43; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING ComputerName; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+84h] [rbp-7Ch] BYREF
  void *Src; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h]
  __int128 v49; // [rsp+98h] [rbp-68h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-58h]
  __int128 v51; // [rsp+B8h] [rbp-48h]
  __int64 v52; // [rsp+C8h] [rbp-38h]
  __int64 v53; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING *v54; // [rsp+D8h] [rbp-28h]
  _OWORD v55[4]; // [rsp+E0h] [rbp-20h] BYREF
  char v56; // [rsp+120h] [rbp+20h] BYREF

  v52 = a5;
  v10 = a8;
  v42 = a4;
  v54 = DnsHostName;
  v11 = 0;
  v53 = a8;
  hMem = 0;
  v12 = 0;
  Src = 0;
  v13 = 0;
  v43 = 0;
  v14 = 0;
  v41 = 0;
  v46 = 0;
  v45 = a7 & 4;
  SourceSid = 0;
  ComputerName = 0;
  memset(v55, 0, 60);
  if ( a8 && (a7 & 4) == 0 )
  {
    v15 = -1073741811;
    goto LABEL_18;
  }
  v16 = 1;
  if ( (a7 & 1) == 0 )
  {
    ComputerName.MaximumLength = 32;
    ComputerName.Buffer = (PWSTR)&v56;
    v15 = RtlDnsHostNameToComputerName(&ComputerName, DnsHostName, 0);
    if ( v15 < 0 )
      goto LABEL_79;
    ComputerName.MaximumLength = 34;
    ComputerName.Buffer[(unsigned __int64)ComputerName.Length >> 1] = 36;
    ComputerName.Length += 2;
    ComputerName.Buffer[(unsigned __int64)ComputerName.Length >> 1] = 0;
  }
  v15 = SampMaybeBeginDsTransaction(0);
  if ( v15 >= 0 )
  {
    v17 = SampUsingDsData();
    DomainObjectFromIndex = SampGetDomainObjectFromIndex(v17 != 0 ? 3 : 1);
    if ( a2 )
    {
      v15 = SampDsLookupObjectByNameEx(DomainObjectFromIndex, 4, a3, &v43);
    }
    else
    {
      v15 = SampDsLookupObjectByRid(DomainObjectFromIndex, v42, &v43, 0x8000000);
      if ( v15 == -1073741275 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride(v24, v23)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v24, v23, v25, v26)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
        {
          v29 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v24, v23, v27, v28)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v24, v23)
            || (v30 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
          {
            v30 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522717448,
            3,
            13,
            v30,
            v29,
            40,
            (__int64)&WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        ObjectSid = (void *)SampDsGetObjectSid(DomainObjectFromIndex);
        if ( ObjectSid )
        {
          v15 = DsSamCreateFullSid(ObjectSid, v42, &SourceSid);
          if ( v15 >= 0 )
          {
            v32 = SourceSid;
            v15 = RtlCopySid(0x1Cu, (char *)&v55[1] + 8, SourceSid);
            if ( v15 >= 0 )
            {
              LODWORD(v55[0]) = 58;
              DWORD1(v55[0]) = GetLengthSid(v32);
              v12 = (unsigned __int16 *)v55;
LABEL_12:
              if ( (a7 & 1) != 0 )
              {
                v13 = v41;
                v21 = hMem;
              }
              else
              {
                v49 = 0;
                v50 = 0;
                v51 = 0;
                v19 = SampDsLookupObjectByNameEx(DomainObjectFromIndex, 4, &ComputerName, &v41);
                v13 = v41;
                v15 = v19;
                if ( v19 < 0 )
                  goto LABEL_17;
                LODWORD(v49) = 3;
                *((_QWORD *)&v49 + 1) = v41;
                v15 = SampDsControl(&v49, &Src);
                if ( v15 < 0 )
                  goto LABEL_17;
                v20 = LocalAlloc(0x40u, *(unsigned int *)Src);
                hMem = v20;
                v21 = v20;
                if ( !v20 )
                {
                  v15 = -1073741801;
LABEL_17:
                  v14 = SourceSid;
                  goto LABEL_18;
                }
                memcpy_0(v20, Src, *(unsigned int *)Src);
              }
              SampMaybeEndDsTransaction(3);
              if ( (a7 & 1) != 0 )
              {
                v39 = SampDsReplicateAccountOutbound(v54, v12 + 28, a6);
              }
              else
              {
                *((_QWORD *)&v50 + 1) = v52;
                *(_QWORD *)&v49 = 5;
                DWORD1(v51) = 0;
                *((_QWORD *)&v49 + 1) = v21;
                v38 = (a6 != 0) | 2;
                *(_QWORD *)&v50 = v12;
                if ( !v45 )
                  v38 = a6 != 0;
                LODWORD(v51) = v38;
                *((_QWORD *)&v51 + 1) = v53;
                v39 = SampDsControl(&v49, &v46);
              }
              v15 = v39;
              goto LABEL_17;
            }
          }
        }
        else
        {
          v15 = -1073741670;
        }
LABEL_53:
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(DnsHostName, v10)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(DnsHostName, v10)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(DnsHostName, v10, v33, v34)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v37 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(DnsHostName, v10)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(DnsHostName, v10, v35, v36)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( !(unsigned int)THStateCheckForTraceOverride(DnsHostName, v10)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
          {
            v16 = 0;
          }
          WPP_SF__ATTRTYP_LOG_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522717487,
            2,
            13,
            v16,
            v37,
            41,
            (__int64)&WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        v12 = v43;
        v13 = v41;
        goto LABEL_17;
      }
    }
    if ( v15 >= 0 )
    {
      v12 = v43;
      goto LABEL_12;
    }
    goto LABEL_53;
  }
LABEL_79:
  v13 = v41;
LABEL_18:
  if ( (unsigned int)SampExistsDsTransaction(DnsHostName, v10, v11) )
    SampMaybeEndDsTransaction(3);
  if ( v14 )
    DSFreeAux(v14, 522717584);
  if ( hMem )
    LocalFree(hMem);
  if ( v12 && v12 != (unsigned __int16 *)v55 )
    LocalFree(v12);
  if ( v13 )
    LocalFree(v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1803f7648  mov     [rsp-8+arg_8], rbx
0x1803f764d  push    rbp
0x1803f764e  push    rsi
0x1803f764f  push    rdi
0x1803f7650  push    r12
0x1803f7652  push    r13
0x1803f7654  push    r14
0x1803f7656  push    r15
0x1803f7658  lea     rbp, [rsp-50h]
0x1803f765d  sub     rsp, 150h
0x1803f7664  mov     rax, cs:__security_cookie
0x1803f766b  xor     rax, rsp
0x1803f766e  mov     [rbp+80h+var_38], rax
0x1803f7672  mov     rax, [rbp+80h+arg_20]
0x1803f7679  xorps   xmm0, xmm0
0x1803f767c  mov     r15d, dword ptr [rbp+80h+arg_30]
0x1803f7683  mov     r12, r8
0x1803f7686  mov     [rbp+80h+var_B8], rax
0x1803f768a  mov     r14b, dl
0x1803f768d  mov     rdx, [rbp+80h+arg_38]
0x1803f7694  mov     eax, r15d
0x1803f7697  and     eax, 4
0x1803f769a  mov     [rsp+180h+var_120], r9d
0x1803f769f  xor     r9d, r9d
0x1803f76a2  mov     [rbp+80h+var_A8], rcx
0x1803f76a6  xor     r8d, r8d; AllocateComputerNameString
0x1803f76a9  mov     [rbp+80h+var_B0], rdx
0x1803f76ad  mov     [rbp+80h+hMem], r9
0x1803f76b1  mov     edi, r9d
0x1803f76b4  mov     [rbp+80h+Src], r9
0x1803f76b8  mov     esi, r9d
0x1803f76bb  mov     [rsp+180h+var_118], r9
0x1803f76c0  mov     r13d, r9d
0x1803f76c3  mov     [rsp+180h+var_128], r9
0x1803f76c8  mov     [rbp+80h+var_FC], r9d
0x1803f76cc  mov     [rbp+80h+var_100], eax
0x1803f76cf  mov     [rsp+180h+SourceSid], r9
0x1803f76d4  movups  xmmword ptr [rbp+80h+var_80], xmm0
0x1803f76d8  movups  xmmword ptr [rsp+180h+ComputerName.Length], xmm0
0x1803f76dd  movups  [rbp+80h+var_A0], xmm0
0x1803f76e1  movups  [rbp+80h+DestinationSid], xmm0
0x1803f76e5  movups  xmmword ptr [rbp+80h+var_80+0Ch], xmm0
0x1803f76e9  test    rdx, rdx
0x1803f76ec  jz      short loc_1803F76FC
0x1803f76ee  test    eax, eax
0x1803f76f0  jnz     short loc_1803F76FC
0x1803f76f2  mov     ebx, 0C000000Dh
0x1803f76f7  jmp     loc_1803F7850
0x1803f76fc  not     r15b
0x1803f76ff  mov     esi, 1
0x1803f7704  and     r15b, sil
0x1803f7707  jz      short loc_1803F776C
0x1803f7709  lea     eax, [rsi+1Fh]
0x1803f770c  mov     rdx, rcx; DnsHostName
0x1803f770f  mov     [rsp+180h+ComputerName.MaximumLength], ax
0x1803f7714  lea     rcx, [rsp+180h+ComputerName]; ComputerName
0x1803f7719  lea     rax, [rbp+80h+var_60]
0x1803f771d  mov     [rsp+180h+ComputerName.Buffer], rax
0x1803f7722  call    cs:__imp_RtlDnsHostNameToComputerName
0x1803f7728  mov     ebx, eax
0x1803f772a  test    eax, eax
0x1803f772c  js      loc_1803F7BE2
0x1803f7732  movzx   ecx, [rsp+180h+ComputerName.Length]
0x1803f7737  lea     eax, [rsi+21h]
0x1803f773a  mov     [rsp+180h+ComputerName.MaximumLength], ax
0x1803f773f  mov     rax, [rsp+180h+ComputerName.Buffer]
0x1803f7744  shr     rcx, 1
0x1803f7747  mov     word ptr [rax+rcx*2], 24h ; '$'
0x1803f774d  movzx   eax, [rsp+180h+ComputerName.Length]
0x1803f7752  add     ax, 2
0x1803f7756  movzx   edx, ax
0x1803f7759  mov     [rsp+180h+ComputerName.Length], ax
0x1803f775e  mov     rax, [rsp+180h+ComputerName.Buffer]
0x1803f7763  shr     rdx, 1
0x1803f7766  xor     ecx, ecx
0x1803f7768  mov     [rax+rdx*2], cx
0x1803f776c  xor     ecx, ecx
0x1803f776e  call    SampMaybeBeginDsTransaction
0x1803f7773  mov     ebx, eax
0x1803f7775  test    eax, eax
0x1803f7777  js      loc_1803F7BE2
0x1803f777d  call    cs:__imp_SampUsingDsData
0x1803f7783  neg     al
0x1803f7785  sbb     ecx, ecx
0x1803f7787  and     ecx, 2
0x1803f778a  add     ecx, esi
0x1803f778c  call    cs:__imp_SampGetDomainObjectFromIndex
0x1803f7792  mov     edi, 0Dh
0x1803f7797  mov     r13, rax
0x1803f779a  mov     rcx, rax
0x1803f779d  test    r14b, r14b
0x1803f77a0  jz      loc_1803F78D5
0x1803f77a6  lea     r9, [rsp+180h+var_118]
0x1803f77ab  mov     r8, r12
0x1803f77ae  lea     edx, [rdi-9]
0x1803f77b1  call    SampDsLookupObjectByNameEx
0x1803f77b6  mov     r14d, [rsp+180h+var_120]
0x1803f77bb  mov     ebx, eax
0x1803f77bd  test    ebx, ebx
0x1803f77bf  js      loc_1803F7A51
0x1803f77c5  mov     rdi, [rsp+180h+var_118]
0x1803f77ca  mov     r12d, 3
0x1803f77d0  test    r15b, r15b
0x1803f77d3  jz      loc_1803F7B61
0x1803f77d9  xorps   xmm0, xmm0
0x1803f77dc  lea     r9, [rsp+180h+var_128]
0x1803f77e1  lea     r8, [rsp+180h+ComputerName]
0x1803f77e6  mov     edx, 4
0x1803f77eb  mov     rcx, r13
0x1803f77ee  movups  [rbp+80h+var_E8], xmm0
0x1803f77f2  movups  [rbp+80h+var_D8], xmm0
0x1803f77f6  movups  [rbp+80h+var_C8], xmm0
0x1803f77fa  call    SampDsLookupObjectByNameEx
0x1803f77ff  mov     rsi, [rsp+180h+var_128]
0x1803f7804  mov     ebx, eax
0x1803f7806  test    eax, eax
0x1803f7808  js      short loc_1803F784B
0x1803f780a  lea     rdx, [rbp+80h+Src]
0x1803f780e  mov     dword ptr [rbp+80h+var_E8], r12d
0x1803f7812  lea     rcx, [rbp+80h+var_E8]
0x1803f7816  mov     qword ptr [rbp+80h+var_E8+8], rsi
0x1803f781a  call    SampDsControl
0x1803f781f  mov     ebx, eax
0x1803f7821  test    eax, eax
0x1803f7823  js      short loc_1803F784B
0x1803f7825  mov     rax, [rbp+80h+Src]
0x1803f7829  mov     ecx, 40h ; '@'; uFlags
0x1803f782e  mov     edx, [rax]; uBytes
0x1803f7830  call    cs:__imp_LocalAlloc
0x1803f7836  mov     [rbp+80h+hMem], rax
0x1803f783a  mov     rbx, rax
0x1803f783d  test    rax, rax
0x1803f7840  jnz     loc_1803F7B50
0x1803f7846  mov     ebx, 0C0000017h
0x1803f784b  mov     r13, [rsp+180h+SourceSid]
0x1803f7850  call    SampExistsDsTransaction
0x1803f7855  test    eax, eax
0x1803f7857  jz      short loc_1803F7863
0x1803f7859  mov     ecx, 3
0x1803f785e  call    SampMaybeEndDsTransaction
0x1803f7863  test    r13, r13
0x1803f7866  jz      short loc_1803F7875
0x1803f7868  mov     edx, 1F280990h
0x1803f786d  mov     rcx, r13
0x1803f7870  call    DSFreeAux
0x1803f7875  mov     rax, [rbp+80h+hMem]
0x1803f7879  test    rax, rax
0x1803f787c  jz      short loc_1803F7887
0x1803f787e  mov     rcx, rax; hMem
0x1803f7881  call    cs:__imp_LocalFree
0x1803f7887  test    rdi, rdi
0x1803f788a  jz      short loc_1803F789E
0x1803f788c  lea     rax, [rbp+80h+var_A0]
0x1803f7890  cmp     rdi, rax
0x1803f7893  jz      short loc_1803F789E
0x1803f7895  mov     rcx, rdi; hMem
0x1803f7898  call    cs:__imp_LocalFree
0x1803f789e  test    rsi, rsi
0x1803f78a1  jz      short loc_1803F78AC
0x1803f78a3  mov     rcx, rsi; hMem
0x1803f78a6  call    cs:__imp_LocalFree
0x1803f78ac  mov     eax, ebx
0x1803f78ae  mov     rcx, [rbp+80h+var_38]
0x1803f78b2  xor     rcx, rsp; StackCookie
0x1803f78b5  call    __security_check_cookie
0x1803f78ba  mov     rbx, [rsp+180h+arg_8]
0x1803f78c2  add     rsp, 150h
0x1803f78c9  pop     r15
0x1803f78cb  pop     r14
0x1803f78cd  pop     r13
0x1803f78cf  pop     r12
0x1803f78d1  pop     rdi
0x1803f78d2  pop     rsi
0x1803f78d3  pop     rbp
0x1803f78d4  retn
0x1803f78d5  mov     r14d, [rsp+180h+var_120]
0x1803f78da  lea     r8, [rsp+180h+var_118]
0x1803f78df  mov     edx, r14d
0x1803f78e2  mov     r9d, 8000000h
0x1803f78e8  call    SampDsLookupObjectByRid
0x1803f78ed  mov     ebx, eax
0x1803f78ef  cmp     eax, 0C0000225h
0x1803f78f4  jnz     loc_1803F77BD
0x1803f78fa  mov     r12d, 3
0x1803f7900  mov     ecx, r12d
0x1803f7903  call    IncrementWPPPerfCountersForLevel
0x1803f7908  test    eax, eax
0x1803f790a  jnz     short loc_1803F795F
0x1803f790c  call    THStateCheckForTraceOverride
0x1803f7911  test    eax, eax
0x1803f7913  jnz     short loc_1803F795F
0x1803f7915  mov     r8d, edi
0x1803f7918  mov     edx, r12d
0x1803f791b  xor     ecx, ecx
0x1803f791d  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f7922  test    eax, eax
0x1803f7924  jnz     short loc_1803F795F
0x1803f7926  mov     eax, cs:gfTraceToSecondProvider
0x1803f792c  test    eax, eax
0x1803f792e  jz      loc_1803F79E9
0x1803f7934  call    THStateCheckForTraceOverride
0x1803f7939  test    eax, eax
0x1803f793b  jnz     short loc_1803F795F
0x1803f793d  call    ThStateCheckIfTraceToSecondProvier
0x1803f7942  test    eax, eax
0x1803f7944  jz      loc_1803F79E9
0x1803f794a  mov     r8d, edi
0x1803f794d  mov     edx, r12d
0x1803f7950  mov     ecx, esi
0x1803f7952  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f7957  test    eax, eax
0x1803f7959  jz      loc_1803F79E9
0x1803f795f  mov     eax, cs:gfTraceToSecondProvider
0x1803f7965  test    eax, eax
0x1803f7967  jz      short loc_1803F7990
0x1803f7969  call    THStateCheckForTraceOverride
0x1803f796e  test    eax, eax
0x1803f7970  jnz     short loc_1803F798C
0x1803f7972  call    ThStateCheckIfTraceToSecondProvier
0x1803f7977  test    eax, eax
0x1803f7979  jz      short loc_1803F7990
0x1803f797b  mov     r8d, edi
0x1803f797e  mov     edx, r12d
0x1803f7981  mov     ecx, esi
0x1803f7983  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f7988  test    eax, eax
0x1803f798a  jz      short loc_1803F7990
0x1803f798c  mov     ebx, esi
0x1803f798e  jmp     short loc_1803F7992
0x1803f7990  xor     ebx, ebx
0x1803f7992  call    THStateCheckForTraceOverride
0x1803f7997  test    eax, eax
0x1803f7999  jnz     short loc_1803F79AC
0x1803f799b  mov     r8d, edi
0x1803f799e  mov     edx, r12d
0x1803f79a1  xor     ecx, ecx
0x1803f79a3  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f79a8  test    eax, eax
0x1803f79aa  jz      short loc_1803F79AE
0x1803f79ac  mov     eax, esi
0x1803f79ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1803f79b5  lea     rdx, WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids
0x1803f79bc  mov     [rsp+180h+var_140], r14d
0x1803f79c1  mov     r9d, edi
0x1803f79c4  mov     [rsp+180h+var_148], rdx
0x1803f79c9  mov     r8d, r12d
0x1803f79cc  mov     [rsp+180h+var_150], 28h ; '('
0x1803f79d3  mov     edx, 1F280908h
0x1803f79d8  mov     rcx, [rcx+10h]
0x1803f79dc  mov     [rsp+180h+var_158], ebx
0x1803f79e0  mov     [rsp+180h+var_160], eax
0x1803f79e4  call    WPP_SF__ATTRTYP_LOG_
0x1803f79e9  mov     rcx, r13
0x1803f79ec  call    SampDsGetObjectSid
0x1803f79f1  test    rax, rax
0x1803f79f4  jnz     short loc_1803F79FD
0x1803f79f6  mov     ebx, 0C000009Ah
0x1803f79fb  jmp     short loc_1803F7A51
0x1803f79fd  lea     r8, [rsp+180h+SourceSid]
0x1803f7a02  mov     edx, r14d
0x1803f7a05  mov     rcx, rax; SourceSid
0x1803f7a08  call    DsSamCreateFullSid
0x1803f7a0d  mov     ebx, eax
0x1803f7a0f  test    eax, eax
0x1803f7a11  js      short loc_1803F7A51
0x1803f7a13  mov     rdi, [rsp+180h+SourceSid]
0x1803f7a18  lea     rdx, [rbp+80h+DestinationSid+8]; DestinationSid
0x1803f7a1c  mov     r8, rdi; SourceSid
0x1803f7a1f  mov     ecx, 1Ch; DestinationSidLength
0x1803f7a24  call    cs:__imp_RtlCopySid
0x1803f7a2a  mov     ebx, eax
0x1803f7a2c  test    eax, eax
0x1803f7a2e  js      short loc_1803F7A4C
0x1803f7a30  mov     rcx, rdi; pSid
0x1803f7a33  mov     dword ptr [rbp+80h+var_A0], 3Ah ; ':'
0x1803f7a3a  call    cs:__imp_GetLengthSid
0x1803f7a40  mov     dword ptr [rbp+80h+var_A0+4], eax
0x1803f7a43  lea     rdi, [rbp+80h+var_A0]
0x1803f7a47  jmp     loc_1803F77D0
0x1803f7a4c  mov     edi, 0Dh
0x1803f7a51  mov     r15d, 2
0x1803f7a57  mov     ecx, r15d
0x1803f7a5a  call    IncrementWPPPerfCountersForLevel
0x1803f7a5f  test    eax, eax
0x1803f7a61  jnz     short loc_1803F7AB9
0x1803f7a63  call    THStateCheckForTraceOverride
0x1803f7a68  test    eax, eax
0x1803f7a6a  jnz     short loc_1803F7AB9
0x1803f7a6c  mov     r8d, edi
0x1803f7a6f  mov     edx, r15d
0x1803f7a72  xor     ecx, ecx
0x1803f7a74  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f7a79  test    eax, eax
0x1803f7a7b  jnz     short loc_1803F7AB9
0x1803f7a7d  mov     eax, cs:gfTraceToSecondProvider
0x1803f7a83  test    eax, eax
0x1803f7a85  jz      short loc_1803F7AAA
0x1803f7a87  call    THStateCheckForTraceOverride
0x1803f7a8c  test    eax, eax
0x1803f7a8e  jnz     short loc_1803F7AB9
  ... truncated ...
```
