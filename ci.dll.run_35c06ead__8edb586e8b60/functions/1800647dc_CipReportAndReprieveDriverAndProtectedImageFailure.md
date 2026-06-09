# CipReportAndReprieveDriverAndProtectedImageFailure

- ea: `0x1800647dc`
- end: `0x180064aea`
- name: `CipReportAndReprieveDriverAndProtectedImageFailure`
- size: `782`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e5fd0`

## callees

- `0x180062244`
- `0x1800647dc`
- `0x1800658e4`
- `0x18006dd5c`
- `0x180073b20`
- `0x180076ee8`
- `0x18007a5c4`
- `0x18008f038`
- `0x18008f0d0`
- `0x18008f2d0`
- `0x180090564`
- `0x1800a3d3c`
- `0x1800a4350`
- `0x1800b56d0`
- `0x1800c29a8`
- `0x1800cb940`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180064a1c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180064a1c`
- `ntoskrnl!KdDebuggerNotPresent` at `0x180064863`
- `ntoskrnl!KdDebuggerNotPresent` at `0x180064a9e`
- `ntoskrnl!DbgPrint` at `0x180064ab6`
- `ntoskrnl!DbgPrint` at `0x180064ab6`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x180064877`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x180064877`
- `ntoskrnl!KdDebuggerEnabled` at `0x180064857`
- `ntoskrnl!KdDebuggerEnabled` at `0x180064a92`

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
      v16 = off_180030578;
      v17 = off_180030570;
    }
    else
    {
      v16 = (__int64 (**)[2])&off_180030588;
      v15 = v14 == 0;
      v17 = &off_180030580;
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
      v21 = *(_QWORD *)(a1 + 2360);
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
      DbgPrint("Code Integrity violation:  %d\n", 9789);
      __debugbreak();
    }
    CipReleaseFileName(v27);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800647dc  mov     [rsp-38h+arg_18], rbx
0x1800647e1  mov     [rsp-38h+arg_10], r8
0x1800647e6  mov     [rsp-38h+Process], rdx
0x1800647eb  push    rbp
0x1800647ec  push    rsi
0x1800647ed  push    rdi
0x1800647ee  push    r12
0x1800647f0  push    r13
0x1800647f2  push    r14
0x1800647f4  push    r15
0x1800647f6  mov     rbp, rsp
0x1800647f9  sub     rsp, 80h
0x180064800  xor     r12d, r12d
0x180064803  mov     rbx, rcx
0x180064806  xorps   xmm0, xmm0
0x180064809  mov     [rbp+var_38], r12
0x18006480d  xorps   xmm1, xmm1
0x180064810  mov     [rbp+var_40], r12
0x180064814  add     rcx, 18h
0x180064818  mov     dword ptr [rbp+arg_0], r12d
0x18006481c  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x180064820  mov     r13d, r12d
0x180064823  mov     r15d, r9d
0x180064826  movups  xmmword ptr [rbp+StringIn.Length], xmm0
0x18006482a  mov     r14, r8
0x18006482d  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x180064831  call    CipIsAcPolicyViolation
0x180064836  mov     edi, [rbp+arg_28]
0x180064839  mov     esi, edi
0x18006483b  test    al, al
0x18006483d  jnz     short loc_18006488B
0x18006483f  test    r15d, 40000006h
0x180064846  setz    cl
0x180064849  test    byte ptr cs:g_CiOptions, 10h
0x180064850  setz    al
0x180064853  test    al, cl
0x180064855  jz      short loc_180064877
0x180064857  mov     rax, cs:KdDebuggerEnabled
0x18006485e  cmp     byte ptr [rax], 1
0x180064861  jnz     short loc_180064877
0x180064863  mov     rax, cs:KdDebuggerNotPresent
0x18006486a  cmp     [rax], r12b
0x18006486d  jnz     short loc_180064877
0x18006486f  lea     r13d, [r12+1]
0x180064874  mov     esi, r12d
0x180064877  call    cs:__imp_PsIsCurrentThreadPrefetching
0x18006487e  nop     dword ptr [rax+rax+00h]
0x180064883  test    al, al
0x180064885  jnz     loc_180064ACC
0x18006488b  lea     r8, [rbp+var_38]
0x18006488f  mov     rcx, r14
0x180064892  lea     rdx, [rbp+var_30]
0x180064896  call    CipQueryFileName
0x18006489b  mov     r14d, r15d
0x18006489e  mov     r12d, r13d
0x1800648a1  and     r14d, 2
0x1800648a5  shl     r12, 5
0x1800648a9  cmp     edi, 0C0000603h
0x1800648af  jnz     short loc_1800648D1
0x1800648b1  lea     rdx, [rbp+var_30]
0x1800648b5  mov     rcx, rbx
0x1800648b8  call    CiHvciCheckAndNotifyBlockedByHvciPolicy
0x1800648bd  test    r15b, 1
0x1800648c1  lea     rcx, off_180030578
0x1800648c8  lea     rax, off_180030570
0x1800648cf  jmp     short loc_1800648E2
0x1800648d1  lea     rcx, off_180030588
0x1800648d8  test    r14d, r14d
0x1800648db  lea     rax, off_180030580
0x1800648e2  mov     r9b, byte ptr [rbp+arg_20]; int
0x1800648e6  cmovz   rax, rcx
0x1800648ea  mov     r8d, r15d; int
0x1800648ed  lea     rcx, [rbp+var_30]; int
0x1800648f1  mov     rax, [r12+rax]
0x1800648f5  mov     r12, [rbp+Process]
0x1800648f9  mov     rdx, r12; Process
0x1800648fc  mov     [rsp+80h+var_60], rax; PCEVENT_DESCRIPTOR
0x180064901  call    CiLogFileRequestedValidationEvent
0x180064906  mov     rcx, rbx
0x180064909  call    CiLogSignatureInformation
0x18006490e  neg     r14d
0x180064911  lea     rcx, [rbp+var_30]
0x180064915  sbb     edx, edx
0x180064917  and     edx, 4DBh
0x18006491d  add     edx, 13AEh
0x180064923  call    CiAudit
0x180064928  xor     r14d, r14d
0x18006492b  test    esi, esi
0x18006492d  jns     loc_180064A81
0x180064933  lea     r8, [rbp+var_40]
0x180064937  mov     rcx, r12
0x18006493a  lea     rdx, [rbp+StringIn]
0x18006493e  call    CipQueryProcessName
0x180064943  cmp     [rbx+5FCh], r14d
0x18006494a  jnz     short loc_180064954
0x18006494c  mov     rcx, rbx
0x18006494f  call    CiCheckSmartScreenClaim
0x180064954  mov     rcx, [rbx+938h]
0x18006495b  test    rcx, rcx
0x18006495e  jz      short loc_18006496A
0x180064960  mov     eax, [rbx+3C8h]
0x180064966  mov     r14, [rcx+rax*8]
0x18006496a  test    cs:g_CiPolicyState, 4000h
0x180064974  jz      loc_180064A48
0x18006497a  test    r15b, 5
0x18006497e  jnz     loc_180064A48
0x180064984  call    SIPolicyVerifiedAndReputableUI
0x180064989  test    al, al
0x18006498b  jz      loc_180064A48
0x180064991  test    r14, r14
0x180064994  jz      loc_180064A48
0x18006499a  cmp     dword ptr [r14+28h], 6
0x18006499f  sbb     rax, rax
0x1800649a2  and     rax, 0FFFFFFFFFFFFFD50h
0x1800649a8  mov     rcx, [rax+r14+2C0h]
0x1800649b0  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop
0x1800649b7  jnz     short loc_1800649C8
0x1800649b9  mov     rcx, [rax+r14+2C8h]
0x1800649c1  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop+8
0x1800649c8  xor     r14d, r14d
0x1800649cb  test    rcx, rcx
0x1800649ce  jnz     short loc_180064A4B
0x1800649d0  cmp     [rbx+5F8h], r14d
0x1800649d7  jnz     short loc_180064A3C
0x1800649d9  lea     r9, [rbp+UnicodeString]
0x1800649dd  xor     edx, edx; StringOut
0x1800649df  mov     rcx, r12; PROCESS
0x1800649e2  call    CipTryGetProcessAppID
0x1800649e7  test    eax, eax
0x1800649e9  js      short loc_1800649F6
0x1800649eb  lea     rdx, [rbp+UnicodeString]
0x1800649ef  cmp     [rbp+UnicodeString.Length], r14w
0x1800649f4  ja      short loc_1800649F9
0x1800649f6  mov     rdx, r14; PCUNICODE_STRING
0x1800649f9  lea     rax, [rbp+arg_0]
0x1800649fd  mov     r9d, edi
0x180064a00  lea     r8, [rbp+var_30]; PCUNICODE_STRING
0x180064a04  mov     [rsp+80h+var_60], rax; __int64
0x180064a09  lea     rcx, [rbp+StringIn]; StringIn
0x180064a0d  call    CiCatDbSendSmartAppControlBlockToast2
0x180064a12  cmp     [rbp+UnicodeString.Buffer], r14
0x180064a16  jz      short loc_180064A28
0x180064a18  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180064a1c  call    cs:__imp_RtlFreeUnicodeString
0x180064a23  nop     dword ptr [rax+rax+00h]
0x180064a28  mov     eax, dword ptr [rbp+arg_0]
0x180064a2b  neg     eax
0x180064a2d  sbb     ecx, ecx
0x180064a2f  neg     ecx
0x180064a31  add     ecx, 2
0x180064a34  mov     [rbx+838h], ecx
0x180064a3a  jmp     short loc_180064A4B
0x180064a3c  mov     dword ptr [rbx+838h], 1
0x180064a46  jmp     short loc_180064A4B
0x180064a48  xor     r14d, r14d
0x180064a4b  mov     edx, edi
0x180064a4d  mov     rcx, rbx
0x180064a50  call    CiInstrumentDriverBlock
0x180064a55  mov     al, byte ptr [rbp+arg_20]
0x180064a58  lea     r8, [rbp+StringIn]
0x180064a5c  mov     rdx, [rbp+arg_10]
0x180064a60  mov     r9d, r15d
0x180064a63  mov     [rsp+80h+var_50], r14b
0x180064a68  mov     rcx, rbx
0x180064a6b  mov     [rsp+80h+var_58], edi
0x180064a6f  mov     byte ptr [rsp+80h+var_60], al
0x180064a73  call    CiInstrumentSignatureFailuresOnCleanStack
0x180064a78  mov     rcx, [rbp+var_40]
0x180064a7c  call    CipReleaseProcessName
0x180064a81  cmp     r13d, 1
0x180064a85  jnz     short loc_180064AC3
0x180064a87  mov     eax, cs:g_CiOptions
0x180064a8d  test    r13b, al
0x180064a90  jz      short loc_180064AC3
0x180064a92  mov     rax, cs:KdDebuggerEnabled
0x180064a99  cmp     [rax], r14b
0x180064a9c  jz      short loc_180064AC3
0x180064a9e  mov     rax, cs:KdDebuggerNotPresent
0x180064aa5  cmp     [rax], r13b
0x180064aa8  jz      short loc_180064AC3
0x180064aaa  mov     edx, 263Dh
0x180064aaf  lea     rcx, aCodeIntegrityV; "Code Integrity violation:  %d\n"
0x180064ab6  call    cs:__imp_DbgPrint
0x180064abd  nop     dword ptr [rax+rax+00h]
0x180064ac2  int     3; Trap to Debugger
0x180064ac3  mov     rcx, [rbp+var_38]
0x180064ac7  call    CipReleaseFileName
0x180064acc  mov     rbx, [rsp+80h+arg_18]
0x180064ad4  mov     eax, esi
0x180064ad6  add     rsp, 80h
0x180064add  pop     r15
0x180064adf  pop     r14
0x180064ae1  pop     r13
0x180064ae3  pop     r12
0x180064ae5  pop     rdi
0x180064ae6  pop     rsi
0x180064ae7  pop     rbp
0x180064ae8  retn
```
