# CipReportAndReprieveDriverAndProtectedImageFailure

- ea: `0x180063d3c`
- end: `0x180064061`
- name: `CipReportAndReprieveDriverAndProtectedImageFailure`
- size: `805`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800e55e0`

## callees

- `0x180010094`
- `0x18006189c`
- `0x180063d3c`
- `0x180064e80`
- `0x18006bbfc`
- `0x18006cca8`
- `0x180072590`
- `0x180075658`
- `0x180078d04`
- `0x18009dca8`
- `0x18009eac8`
- `0x18009eb60`
- `0x18009ed60`
- `0x1800a2270`
- `0x1800a2880`
- `0x1800b43b0`
- `0x1800c1518`
- `0x1800ca4b0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180063f7c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063f7c`
- `ntoskrnl!KdDebuggerNotPresent` at `0x180063dc3`
- `ntoskrnl!KdDebuggerNotPresent` at `0x180064015`
- `ntoskrnl!DbgPrint` at `0x18006402d`
- `ntoskrnl!DbgPrint` at `0x18006402d`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x180063dd7`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x180063dd7`
- `ntoskrnl!KdDebuggerEnabled` at `0x180063db7`
- `ntoskrnl!KdDebuggerEnabled` at `0x180064009`

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
  unsigned int v11; // esi
  int v12; // edi
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
      v16 = off_180030508;
      v17 = off_180030500;
    }
    else
    {
      v16 = (__int64 (**)[2])&off_180030518;
      v15 = v14 == 0;
      v17 = &off_180030510;
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
      if ( (unsigned int)Feature_Servicing_WhqlOnlyContainment__private_IsEnabledDeviceUsageNoInline() )
        CipProcessPicrootExceptionsPolicyFailures(a1, (unsigned int)v12, &v28);
      CiInstrumentSignatureFailuresOnCleanStack(a1, v33, (unsigned int)&StringIn, a4, a5, v11, 0);
      CipReleaseProcessName(v26);
    }
    if ( v7 == 1 && (g_CiOptions & 1) != 0 && (_BYTE)KdDebuggerEnabled && (_BYTE)KdDebuggerNotPresent != 1 )
    {
      DbgPrint("Code Integrity violation:  %d\n", 9744);
      __debugbreak();
    }
    CipReleaseFileName(v27);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180063d3c  mov     [rsp-38h+arg_18], rbx
0x180063d41  mov     [rsp-38h+arg_10], r8
0x180063d46  mov     [rsp-38h+Process], rdx
0x180063d4b  push    rbp
0x180063d4c  push    rsi
0x180063d4d  push    rdi
0x180063d4e  push    r12
0x180063d50  push    r13
0x180063d52  push    r14
0x180063d54  push    r15
0x180063d56  mov     rbp, rsp
0x180063d59  sub     rsp, 80h
0x180063d60  xor     r12d, r12d
0x180063d63  mov     rbx, rcx
0x180063d66  xorps   xmm0, xmm0
0x180063d69  mov     [rbp+var_38], r12
0x180063d6d  xorps   xmm1, xmm1
0x180063d70  mov     [rbp+var_40], r12
0x180063d74  add     rcx, 18h
0x180063d78  mov     dword ptr [rbp+arg_0], r12d
0x180063d7c  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x180063d80  mov     r13d, r12d
0x180063d83  mov     r15d, r9d
0x180063d86  movups  xmmword ptr [rbp+StringIn.Length], xmm0
0x180063d8a  mov     r14, r8
0x180063d8d  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x180063d91  call    CipIsAcPolicyViolation
0x180063d96  mov     esi, [rbp+arg_28]
0x180063d99  mov     edi, esi
0x180063d9b  test    al, al
0x180063d9d  jnz     short loc_180063DEB
0x180063d9f  test    r15d, 40000006h
0x180063da6  setz    cl
0x180063da9  test    byte ptr cs:g_CiOptions, 10h
0x180063db0  setz    al
0x180063db3  test    al, cl
0x180063db5  jz      short loc_180063DD7
0x180063db7  mov     rax, cs:KdDebuggerEnabled
0x180063dbe  cmp     byte ptr [rax], 1
0x180063dc1  jnz     short loc_180063DD7
0x180063dc3  mov     rax, cs:KdDebuggerNotPresent
0x180063dca  cmp     [rax], r12b
0x180063dcd  jnz     short loc_180063DD7
0x180063dcf  lea     r13d, [r12+1]
0x180063dd4  mov     edi, r12d
0x180063dd7  call    cs:__imp_PsIsCurrentThreadPrefetching
0x180063dde  nop     dword ptr [rax+rax+00h]
0x180063de3  test    al, al
0x180063de5  jnz     loc_180064043
0x180063deb  lea     r8, [rbp+var_38]
0x180063def  mov     rcx, r14
0x180063df2  lea     rdx, [rbp+var_30]
0x180063df6  call    CipQueryFileName
0x180063dfb  mov     r14d, r15d
0x180063dfe  mov     r12d, r13d
0x180063e01  and     r14d, 2
0x180063e05  shl     r12, 5
0x180063e09  cmp     esi, 0C0000603h
0x180063e0f  jnz     short loc_180063E31
0x180063e11  lea     rdx, [rbp+var_30]
0x180063e15  mov     rcx, rbx
0x180063e18  call    CiHvciCheckAndNotifyBlockedByHvciPolicy
0x180063e1d  test    r15b, 1
0x180063e21  lea     rcx, off_180030508
0x180063e28  lea     rax, off_180030500
0x180063e2f  jmp     short loc_180063E42
0x180063e31  lea     rcx, off_180030518
0x180063e38  test    r14d, r14d
0x180063e3b  lea     rax, off_180030510
0x180063e42  mov     r9b, byte ptr [rbp+arg_20]; int
0x180063e46  cmovz   rax, rcx
0x180063e4a  mov     r8d, r15d; int
0x180063e4d  lea     rcx, [rbp+var_30]; int
0x180063e51  mov     rax, [r12+rax]
0x180063e55  mov     r12, [rbp+Process]
0x180063e59  mov     rdx, r12; Process
0x180063e5c  mov     [rsp+80h+var_60], rax; PCEVENT_DESCRIPTOR
0x180063e61  call    CiLogFileRequestedValidationEvent
0x180063e66  mov     rcx, rbx
0x180063e69  call    CiLogSignatureInformation
0x180063e6e  neg     r14d
0x180063e71  lea     rcx, [rbp+var_30]
0x180063e75  sbb     edx, edx
0x180063e77  and     edx, 4DBh
0x180063e7d  add     edx, 13AEh
0x180063e83  call    CiAudit
0x180063e88  xor     r14d, r14d
0x180063e8b  test    edi, edi
0x180063e8d  jns     loc_180063FF8
0x180063e93  lea     r8, [rbp+var_40]
0x180063e97  mov     rcx, r12
0x180063e9a  lea     rdx, [rbp+StringIn]
0x180063e9e  call    CipQueryProcessName
0x180063ea3  cmp     [rbx+5FCh], r14d
0x180063eaa  jnz     short loc_180063EB4
0x180063eac  mov     rcx, rbx
0x180063eaf  call    CiCheckSmartScreenClaim
0x180063eb4  mov     rcx, [rbx+930h]
0x180063ebb  test    rcx, rcx
0x180063ebe  jz      short loc_180063ECA
0x180063ec0  mov     eax, [rbx+3C8h]
0x180063ec6  mov     r14, [rcx+rax*8]
0x180063eca  test    cs:g_CiPolicyState, 4000h
0x180063ed4  jz      loc_180063FA8
0x180063eda  test    r15b, 5
0x180063ede  jnz     loc_180063FA8
0x180063ee4  call    SIPolicyVerifiedAndReputableUI
0x180063ee9  test    al, al
0x180063eeb  jz      loc_180063FA8
0x180063ef1  test    r14, r14
0x180063ef4  jz      loc_180063FA8
0x180063efa  cmp     dword ptr [r14+28h], 6
0x180063eff  sbb     rax, rax
0x180063f02  and     rax, 0FFFFFFFFFFFFFD50h
0x180063f08  mov     rcx, [rax+r14+2C0h]
0x180063f10  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop
0x180063f17  jnz     short loc_180063F28
0x180063f19  mov     rcx, [rax+r14+2C8h]
0x180063f21  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop+8
0x180063f28  xor     r14d, r14d
0x180063f2b  test    rcx, rcx
0x180063f2e  jnz     short loc_180063FAB
0x180063f30  cmp     [rbx+5F8h], r14d
0x180063f37  jnz     short loc_180063F9C
0x180063f39  lea     r9, [rbp+UnicodeString]
0x180063f3d  xor     edx, edx; StringOut
0x180063f3f  mov     rcx, r12; PROCESS
0x180063f42  call    CipTryGetProcessAppID
0x180063f47  test    eax, eax
0x180063f49  js      short loc_180063F56
0x180063f4b  lea     rdx, [rbp+UnicodeString]
0x180063f4f  cmp     [rbp+UnicodeString.Length], r14w
0x180063f54  ja      short loc_180063F59
0x180063f56  mov     rdx, r14; PCUNICODE_STRING
0x180063f59  lea     rax, [rbp+arg_0]
0x180063f5d  mov     r9d, esi
0x180063f60  lea     r8, [rbp+var_30]; PCUNICODE_STRING
0x180063f64  mov     [rsp+80h+var_60], rax; __int64
0x180063f69  lea     rcx, [rbp+StringIn]; StringIn
0x180063f6d  call    CiCatDbSendSmartAppControlBlockToast2
0x180063f72  cmp     [rbp+UnicodeString.Buffer], r14
0x180063f76  jz      short loc_180063F88
0x180063f78  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180063f7c  call    cs:__imp_RtlFreeUnicodeString
0x180063f83  nop     dword ptr [rax+rax+00h]
0x180063f88  mov     eax, dword ptr [rbp+arg_0]
0x180063f8b  neg     eax
0x180063f8d  sbb     ecx, ecx
0x180063f8f  neg     ecx
0x180063f91  add     ecx, 2
0x180063f94  mov     [rbx+838h], ecx
0x180063f9a  jmp     short loc_180063FAB
0x180063f9c  mov     dword ptr [rbx+838h], 1
0x180063fa6  jmp     short loc_180063FAB
0x180063fa8  xor     r14d, r14d
0x180063fab  mov     edx, esi
0x180063fad  mov     rcx, rbx
0x180063fb0  call    CiInstrumentDriverBlock
0x180063fb5  call    Feature_Servicing_WhqlOnlyContainment__private_IsEnabledDeviceUsageNoInline
0x180063fba  test    eax, eax
0x180063fbc  jz      short loc_180063FCC
0x180063fbe  lea     r8, [rbp+var_30]
0x180063fc2  mov     edx, edi
0x180063fc4  mov     rcx, rbx
0x180063fc7  call    CipProcessPicrootExceptionsPolicyFailures
0x180063fcc  mov     al, byte ptr [rbp+arg_20]
0x180063fcf  lea     r8, [rbp+StringIn]
0x180063fd3  mov     rdx, [rbp+arg_10]
0x180063fd7  mov     r9d, r15d
0x180063fda  mov     [rsp+80h+var_50], r14b
0x180063fdf  mov     rcx, rbx
0x180063fe2  mov     [rsp+80h+var_58], esi
0x180063fe6  mov     byte ptr [rsp+80h+var_60], al
0x180063fea  call    CiInstrumentSignatureFailuresOnCleanStack
0x180063fef  mov     rcx, [rbp+var_40]
0x180063ff3  call    CipReleaseProcessName
0x180063ff8  cmp     r13d, 1
0x180063ffc  jnz     short loc_18006403A
0x180063ffe  mov     eax, cs:g_CiOptions
0x180064004  test    r13b, al
0x180064007  jz      short loc_18006403A
0x180064009  mov     rax, cs:KdDebuggerEnabled
0x180064010  cmp     [rax], r14b
0x180064013  jz      short loc_18006403A
0x180064015  mov     rax, cs:KdDebuggerNotPresent
0x18006401c  cmp     [rax], r13b
0x18006401f  jz      short loc_18006403A
0x180064021  mov     edx, 2610h
0x180064026  lea     rcx, aCodeIntegrityV; "Code Integrity violation:  %d\n"
0x18006402d  call    cs:__imp_DbgPrint
0x180064034  nop     dword ptr [rax+rax+00h]
0x180064039  int     3; Trap to Debugger
0x18006403a  mov     rcx, [rbp+var_38]
0x18006403e  call    CipReleaseFileName
0x180064043  mov     rbx, [rsp+80h+arg_18]
0x18006404b  mov     eax, edi
0x18006404d  add     rsp, 80h
0x180064054  pop     r15
0x180064056  pop     r14
0x180064058  pop     r13
0x18006405a  pop     r12
0x18006405c  pop     rdi
0x18006405d  pop     rsi
0x18006405e  pop     rbp
0x18006405f  retn
```
