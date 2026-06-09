# CipReportAndReprieveDriverAndProtectedImageFailure

- ea: `0x18006466c`
- end: `0x18006497a`
- name: `CipReportAndReprieveDriverAndProtectedImageFailure`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e5a50`

## callees

- `0x1800620e0`
- `0x18006466c`
- `0x180065774`
- `0x18006da7c`
- `0x180073840`
- `0x180076c08`
- `0x18007a2b4`
- `0x18009f2d8`
- `0x1800a00f8`
- `0x1800a0190`
- `0x1800a0390`
- `0x1800a38a0`
- `0x1800a3eb0`
- `0x1800b5830`
- `0x1800c2998`
- `0x1800cb930`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800648ac`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800648ac`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800646f3`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18006492e`
- `ntoskrnl!DbgPrint` at `0x180064946`
- `ntoskrnl!DbgPrint` at `0x180064946`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x180064707`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x180064707`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800646e7`
- `ntoskrnl!KdDebuggerEnabled` at `0x180064922`

## pseudocode

```c
__int64 __fastcall CipReportAndReprieveDriverAndProtectedImageFailure(
        __int64 a1,
        struct _KPROCESS *a2,
        __int64 a3,
        int a4,
        int a5,
        unsigned int a6)
{
  unsigned int v7; // r13d
  char IsAcPolicyViolation; // al
  unsigned int v11; // edi
  int v12; // esi
  int v13; // r9d
  int v14; // r14d
  bool v15; // zf
  __int64 (**v16)[2]; // rcx
  __int64 (**v17)[2]; // rax
  struct _KPROCESS *v18; // r12
  __int64 v19; // r14
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  struct _UNICODE_STRING *p_UnicodeString; // rdx
  __int64 v26; // [rsp+40h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  UNICODE_STRING v28; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-20h] BYREF
  UNICODE_STRING StringIn; // [rsp+70h] [rbp-10h] BYREF
  __int64 v31; // [rsp+C0h] [rbp+40h] BYREF
  PEPROCESS Process; // [rsp+C8h] [rbp+48h]
  __int64 v33; // [rsp+D0h] [rbp+50h]

  v33 = a3;
  Process = a2;
  v27 = 0;
  v26 = 0;
  LODWORD(v31) = 0;
  v28 = 0;
  v7 = 0;
  StringIn = 0;
  UnicodeString = 0;
  IsAcPolicyViolation = CipIsAcPolicyViolation(a1 + 24);
  v11 = a6;
  v12 = a6;
  if ( IsAcPolicyViolation )
    goto LABEL_7;
  if ( (a4 & 0x40000006) == 0
    && (g_CiOptions & 0x10) == 0
    && (_BYTE)KdDebuggerEnabled == 1
    && !(_BYTE)KdDebuggerNotPresent )
  {
    v7 = 1;
    v12 = 0;
  }
  if ( !PsIsCurrentThreadPrefetching() )
  {
LABEL_7:
    CipQueryFileName(a3, &v28, &v27);
    v14 = a4 & 2;
    if ( v11 == -1073740285 )
    {
      CiHvciCheckAndNotifyBlockedByHvciPolicy(a1, &v28);
      v15 = (a4 & 1) == 0;
      v16 = off_1800305A8;
      v17 = off_1800305A0;
    }
    else
    {
      v16 = (__int64 (**)[2])&off_1800305B8;
      v15 = v14 == 0;
      v17 = &off_1800305B0;
    }
    LOBYTE(v13) = a5;
    if ( v15 )
      v17 = v16;
    v18 = Process;
    CiLogFileRequestedValidationEvent((int)&v28, Process, a4, v13, (PCEVENT_DESCRIPTOR)v17[4 * v7]);
    CiLogSignatureInformation(a1);
    CiAudit(&v28, v14 != 0 ? 6281 : 5038);
    v19 = 0;
    if ( v12 < 0 )
    {
      CipQueryProcessName(v18, &StringIn, &v26);
      if ( !*(_DWORD *)(a1 + 1532) )
        CiCheckSmartScreenClaim(a1, v20);
      v21 = *(_QWORD *)(a1 + 2352);
      if ( v21 )
        v19 = *(_QWORD *)(v21 + 8LL * *(unsigned int *)(a1 + 968));
      if ( (g_CiPolicyState & 0x4000) != 0
        && (a4 & 5) == 0
        && (unsigned __int8)SIPolicyVerifiedAndReputableUI(v21, v20)
        && v19 )
      {
        v22 = -(__int64)(*(_DWORD *)(v19 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL;
        v23 = *(_QWORD *)(v22 + v19 + 704) - SiPolicyIDNightsWatchDesktop;
        if ( !v23 )
          v23 = *(_QWORD *)(v22 + v19 + 712) - *((_QWORD *)&SiPolicyIDNightsWatchDesktop + 1);
        if ( !v23 )
        {
          if ( *(_DWORD *)(a1 + 1528) )
          {
            *(_DWORD *)(a1 + 2104) = 1;
          }
          else
          {
            if ( (int)CipTryGetProcessAppID(v18, 0) < 0 || (p_UnicodeString = &UnicodeString, !UnicodeString.Length) )
              p_UnicodeString = 0;
            CiCatDbSendSmartAppControlBlockToast2(&StringIn, p_UnicodeString, &v28, v11, (__int64)&v31);
            if ( UnicodeString.Buffer )
              RtlFreeUnicodeString(&UnicodeString);
            *(_DWORD *)(a1 + 2104) = ((_DWORD)v31 != 0) + 2;
          }
        }
      }
      CiInstrumentDriverBlock(a1, v11);
      CiInstrumentSignatureFailuresOnCleanStack(a1, v33, (unsigned int)&StringIn, a4, a5, v11, 0);
      CipReleaseProcessName(v26);
    }
    if ( v7 == 1 && (g_CiOptions & 1) != 0 && (_BYTE)KdDebuggerEnabled && (_BYTE)KdDebuggerNotPresent != 1 )
    {
      DbgPrint("Code Integrity violation:  %d\n", 9779);
      __debugbreak();
    }
    CipReleaseFileName(v27);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006466c  mov     [rsp-38h+arg_18], rbx
0x180064671  mov     [rsp-38h+arg_10], r8
0x180064676  mov     [rsp-38h+Process], rdx
0x18006467b  push    rbp
0x18006467c  push    rsi
0x18006467d  push    rdi
0x18006467e  push    r12
0x180064680  push    r13
0x180064682  push    r14
0x180064684  push    r15
0x180064686  mov     rbp, rsp
0x180064689  sub     rsp, 80h
0x180064690  xor     r12d, r12d
0x180064693  mov     rbx, rcx
0x180064696  xorps   xmm0, xmm0
0x180064699  mov     [rbp+var_38], r12
0x18006469d  xorps   xmm1, xmm1
0x1800646a0  mov     [rbp+var_40], r12
0x1800646a4  add     rcx, 18h
0x1800646a8  mov     dword ptr [rbp+arg_0], r12d
0x1800646ac  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x1800646b0  mov     r13d, r12d
0x1800646b3  mov     r15d, r9d
0x1800646b6  movups  xmmword ptr [rbp+StringIn.Length], xmm0
0x1800646ba  mov     r14, r8
0x1800646bd  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x1800646c1  call    CipIsAcPolicyViolation
0x1800646c6  mov     edi, [rbp+arg_28]
0x1800646c9  mov     esi, edi
0x1800646cb  test    al, al
0x1800646cd  jnz     short loc_18006471B
0x1800646cf  test    r15d, 40000006h
0x1800646d6  setz    cl
0x1800646d9  test    byte ptr cs:g_CiOptions, 10h
0x1800646e0  setz    al
0x1800646e3  test    al, cl
0x1800646e5  jz      short loc_180064707
0x1800646e7  mov     rax, cs:KdDebuggerEnabled
0x1800646ee  cmp     byte ptr [rax], 1
0x1800646f1  jnz     short loc_180064707
0x1800646f3  mov     rax, cs:KdDebuggerNotPresent
0x1800646fa  cmp     [rax], r12b
0x1800646fd  jnz     short loc_180064707
0x1800646ff  lea     r13d, [r12+1]
0x180064704  mov     esi, r12d
0x180064707  call    cs:__imp_PsIsCurrentThreadPrefetching
0x18006470e  nop     dword ptr [rax+rax+00h]
0x180064713  test    al, al
0x180064715  jnz     loc_18006495C
0x18006471b  lea     r8, [rbp+var_38]
0x18006471f  mov     rcx, r14
0x180064722  lea     rdx, [rbp+var_30]
0x180064726  call    CipQueryFileName
0x18006472b  mov     r14d, r15d
0x18006472e  mov     r12d, r13d
0x180064731  and     r14d, 2
0x180064735  shl     r12, 5
0x180064739  cmp     edi, 0C0000603h
0x18006473f  jnz     short loc_180064761
0x180064741  lea     rdx, [rbp+var_30]
0x180064745  mov     rcx, rbx
0x180064748  call    CiHvciCheckAndNotifyBlockedByHvciPolicy
0x18006474d  test    r15b, 1
0x180064751  lea     rcx, off_1800305A8
0x180064758  lea     rax, off_1800305A0
0x18006475f  jmp     short loc_180064772
0x180064761  lea     rcx, off_1800305B8
0x180064768  test    r14d, r14d
0x18006476b  lea     rax, off_1800305B0
0x180064772  mov     r9b, byte ptr [rbp+arg_20]; int
0x180064776  cmovz   rax, rcx
0x18006477a  mov     r8d, r15d; int
0x18006477d  lea     rcx, [rbp+var_30]; int
0x180064781  mov     rax, [r12+rax]
0x180064785  mov     r12, [rbp+Process]
0x180064789  mov     rdx, r12; Process
0x18006478c  mov     [rsp+80h+var_60], rax; PCEVENT_DESCRIPTOR
0x180064791  call    CiLogFileRequestedValidationEvent
0x180064796  mov     rcx, rbx
0x180064799  call    CiLogSignatureInformation
0x18006479e  neg     r14d
0x1800647a1  lea     rcx, [rbp+var_30]
0x1800647a5  sbb     edx, edx
0x1800647a7  and     edx, 4DBh
0x1800647ad  add     edx, 13AEh
0x1800647b3  call    CiAudit
0x1800647b8  xor     r14d, r14d
0x1800647bb  test    esi, esi
0x1800647bd  jns     loc_180064911
0x1800647c3  lea     r8, [rbp+var_40]
0x1800647c7  mov     rcx, r12
0x1800647ca  lea     rdx, [rbp+StringIn]
0x1800647ce  call    CipQueryProcessName
0x1800647d3  cmp     [rbx+5FCh], r14d
0x1800647da  jnz     short loc_1800647E4
0x1800647dc  mov     rcx, rbx
0x1800647df  call    CiCheckSmartScreenClaim
0x1800647e4  mov     rcx, [rbx+930h]
0x1800647eb  test    rcx, rcx
0x1800647ee  jz      short loc_1800647FA
0x1800647f0  mov     eax, [rbx+3C8h]
0x1800647f6  mov     r14, [rcx+rax*8]
0x1800647fa  test    cs:g_CiPolicyState, 4000h
0x180064804  jz      loc_1800648D8
0x18006480a  test    r15b, 5
0x18006480e  jnz     loc_1800648D8
0x180064814  call    SIPolicyVerifiedAndReputableUI
0x180064819  test    al, al
0x18006481b  jz      loc_1800648D8
0x180064821  test    r14, r14
0x180064824  jz      loc_1800648D8
0x18006482a  cmp     dword ptr [r14+28h], 6
0x18006482f  sbb     rax, rax
0x180064832  and     rax, 0FFFFFFFFFFFFFD50h
0x180064838  mov     rcx, [rax+r14+2C0h]
0x180064840  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop
0x180064847  jnz     short loc_180064858
0x180064849  mov     rcx, [rax+r14+2C8h]
0x180064851  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop+8
0x180064858  xor     r14d, r14d
0x18006485b  test    rcx, rcx
0x18006485e  jnz     short loc_1800648DB
0x180064860  cmp     [rbx+5F8h], r14d
0x180064867  jnz     short loc_1800648CC
0x180064869  lea     r9, [rbp+UnicodeString]
0x18006486d  xor     edx, edx; StringOut
0x18006486f  mov     rcx, r12; PROCESS
0x180064872  call    CipTryGetProcessAppID
0x180064877  test    eax, eax
0x180064879  js      short loc_180064886
0x18006487b  lea     rdx, [rbp+UnicodeString]
0x18006487f  cmp     [rbp+UnicodeString.Length], r14w
0x180064884  ja      short loc_180064889
0x180064886  mov     rdx, r14; PCUNICODE_STRING
0x180064889  lea     rax, [rbp+arg_0]
0x18006488d  mov     r9d, edi
0x180064890  lea     r8, [rbp+var_30]; PCUNICODE_STRING
0x180064894  mov     [rsp+80h+var_60], rax; __int64
0x180064899  lea     rcx, [rbp+StringIn]; StringIn
0x18006489d  call    CiCatDbSendSmartAppControlBlockToast2
0x1800648a2  cmp     [rbp+UnicodeString.Buffer], r14
0x1800648a6  jz      short loc_1800648B8
0x1800648a8  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800648ac  call    cs:__imp_RtlFreeUnicodeString
0x1800648b3  nop     dword ptr [rax+rax+00h]
0x1800648b8  mov     eax, dword ptr [rbp+arg_0]
0x1800648bb  neg     eax
0x1800648bd  sbb     ecx, ecx
0x1800648bf  neg     ecx
0x1800648c1  add     ecx, 2
0x1800648c4  mov     [rbx+838h], ecx
0x1800648ca  jmp     short loc_1800648DB
0x1800648cc  mov     dword ptr [rbx+838h], 1
0x1800648d6  jmp     short loc_1800648DB
0x1800648d8  xor     r14d, r14d
0x1800648db  mov     edx, edi
0x1800648dd  mov     rcx, rbx
0x1800648e0  call    CiInstrumentDriverBlock
0x1800648e5  mov     al, byte ptr [rbp+arg_20]
0x1800648e8  lea     r8, [rbp+StringIn]
0x1800648ec  mov     rdx, [rbp+arg_10]
0x1800648f0  mov     r9d, r15d
0x1800648f3  mov     [rsp+80h+var_50], r14b
0x1800648f8  mov     rcx, rbx
0x1800648fb  mov     [rsp+80h+var_58], edi
0x1800648ff  mov     byte ptr [rsp+80h+var_60], al
0x180064903  call    CiInstrumentSignatureFailuresOnCleanStack
0x180064908  mov     rcx, [rbp+var_40]
0x18006490c  call    CipReleaseProcessName
0x180064911  cmp     r13d, 1
0x180064915  jnz     short loc_180064953
0x180064917  mov     eax, cs:g_CiOptions
0x18006491d  test    r13b, al
0x180064920  jz      short loc_180064953
0x180064922  mov     rax, cs:KdDebuggerEnabled
0x180064929  cmp     [rax], r14b
0x18006492c  jz      short loc_180064953
0x18006492e  mov     rax, cs:KdDebuggerNotPresent
0x180064935  cmp     [rax], r13b
0x180064938  jz      short loc_180064953
0x18006493a  mov     edx, 2633h
0x18006493f  lea     rcx, aCodeIntegrityV; "Code Integrity violation:  %d\n"
0x180064946  call    cs:__imp_DbgPrint
0x18006494d  nop     dword ptr [rax+rax+00h]
0x180064952  int     3; Trap to Debugger
0x180064953  mov     rcx, [rbp+var_38]
0x180064957  call    CipReleaseFileName
0x18006495c  mov     rbx, [rsp+80h+arg_18]
0x180064964  mov     eax, esi
0x180064966  add     rsp, 80h
0x18006496d  pop     r15
0x18006496f  pop     r14
0x180064971  pop     r13
0x180064973  pop     r12
0x180064975  pop     rdi
0x180064976  pop     rsi
0x180064977  pop     rbp
0x180064978  retn
```
