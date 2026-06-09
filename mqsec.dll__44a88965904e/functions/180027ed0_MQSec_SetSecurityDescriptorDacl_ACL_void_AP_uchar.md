# MQSec_SetSecurityDescriptorDacl(_ACL *,void *,AP<uchar> &)

- ea: `0x180027ed0`
- end: `0x1800280fd`
- name: `?MQSec_SetSecurityDescriptorDacl@@YA_NPEAU_ACL@@PEAXAEAV?$AP@E@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(PACL pDacl, PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x1800138c0`
- `0x180017430`
- `0x1800254a8`
- `0x180027500`
- `0x180027a50`
- `0x180027ba0`
- `0x180027ed0`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x180027f4e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180027f4e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180027fdc`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180027fdc`
- `KERNEL32!GetLastError` at `0x180027f58`
- `KERNEL32!GetLastError` at `0x180027fe6`
- `KERNEL32!GetLastError` at `0x180027f58`
- `KERNEL32!GetLastError` at `0x180027fe6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall MQSec_SetSecurityDescriptorDacl(
        PACL pDacl,
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        void **a3)
{
  unsigned __int16 v5; // dx
  char v7; // bl
  DWORD LastError; // edi
  __int16 v9; // ax
  unsigned int v10; // eax
  __int64 v11; // r8
  int SelfRelative; // eax
  DWORD v13; // [rsp+60h] [rbp-29h] BYREF
  _OWORD v14[2]; // [rsp+68h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+88h] [rbp-1h]
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+27h]
  unsigned int v18; // [rsp+108h] [rbp+7Fh] BYREF

  memset(v14, 0, sizeof(v14));
  pAbsoluteSecurityDescriptor = 0;
  if ( !MQSec_MakeAbsoluteSD(pSelfRelativeSecurityDescriptor, (struct CAbsSecurityDsecripror *)v14) )
  {
    v5 = 130;
LABEL_3:
    LogIllegalPoint((wchar_t *)L"acssctrl/secdscrp", v5);
    CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v14);
    return 0;
  }
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v17 = 0;
  v7 = 1;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 46, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, LastError);
    if ( !LastError )
      goto LABEL_24;
    v9 = 131;
LABEL_10:
    LOWORD(v18) = v9;
    v13 = LastError;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v10 = mqwcslen(L"acssctrl/secdscrp");
      v11 = 2;
LABEL_23:
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        v11,
        2LL * (v10 + 1),
        L"acssctrl/secdscrp",
        2,
        &v18,
        4,
        &v13,
        0,
        0);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 47, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, LastError);
    if ( !LastError )
      goto LABEL_24;
    v9 = 132;
    goto LABEL_10;
  }
  if ( !(unsigned int)MQSec_CopySecurityDescriptor(pAbsoluteSecurityDescriptor, pSecurityDescriptor, 4, 0) )
  {
    v5 = 133;
    goto LABEL_3;
  }
  SelfRelative = MQSec_MakeSelfRelative(pAbsoluteSecurityDescriptor, a3, &v18);
  if ( SelfRelative < 0 )
  {
    LOWORD(v18) = 134;
    v13 = SelfRelative;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v10 = mqwcslen(L"acssctrl/secdscrp");
      v11 = 1;
      goto LABEL_23;
    }
LABEL_24:
    v7 = 0;
  }
  CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v14);
  return v7;
}

```

## disassembly

```asm
0x180027ed0  push    rbp
0x180027ed2  push    rbx
0x180027ed3  push    rsi
0x180027ed4  push    rdi
0x180027ed5  lea     rbp, [rsp-3Fh]
0x180027eda  sub     rsp, 0C8h
0x180027ee1  mov     rsi, r8
0x180027ee4  mov     rax, rdx
0x180027ee7  mov     rdi, rcx
0x180027eea  xorps   xmm0, xmm0
0x180027eed  movdqu  [rbp+57h+var_78], xmm0
0x180027ef2  xorps   xmm1, xmm1
0x180027ef5  movdqu  [rbp+57h+var_68], xmm1
0x180027efa  mov     [rbp+57h+pAbsoluteSecurityDescriptor], 0
0x180027f02  lea     rdx, [rbp+57h+var_78]; struct CAbsSecurityDsecripror *
0x180027f06  mov     rcx, rax; pSelfRelativeSecurityDescriptor
0x180027f09  call    ?MQSec_MakeAbsoluteSD@@YA_NPEAXPEAUCAbsSecurityDsecripror@@@Z; MQSec_MakeAbsoluteSD(void *,CAbsSecurityDsecripror *)
0x180027f0e  test    al, al
0x180027f10  jnz     short loc_180027F34
0x180027f12  mov     edx, 82h; unsigned __int16
0x180027f17  lea     rcx, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027f1e  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x180027f23  nop
0x180027f24  lea     rcx, [rbp+57h+var_78]; this
0x180027f28  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x180027f2d  xor     al, al
0x180027f2f  jmp     loc_1800280F1
0x180027f34  xorps   xmm0, xmm0
0x180027f37  xor     eax, eax
0x180027f39  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180027f3d  movups  [rbp+57h+var_40], xmm0
0x180027f41  mov     [rbp+57h+var_30], rax
0x180027f45  lea     ebx, [rax+1]
0x180027f48  mov     edx, ebx; dwRevision
0x180027f4a  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180027f4e  call    cs:__imp_InitializeSecurityDescriptor
0x180027f54  test    eax, eax
0x180027f56  jnz     short loc_180027FD0
0x180027f58  call    cs:__imp_GetLastError
0x180027f5e  mov     edi, eax
0x180027f60  lea     rax, WPP_GLOBAL_Control
0x180027f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f6e  cmp     rcx, rax
0x180027f71  jz      short loc_180027F94
0x180027f73  test    [rcx+10Ch], bl
0x180027f79  jz      short loc_180027F94
0x180027f7b  lea     edx, [rbx+2Dh]
0x180027f7e  mov     r9d, edi
0x180027f81  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x180027f88  mov     rcx, [rcx+100h]
0x180027f8f  call    WPP_SF_d
0x180027f94  test    edi, edi
0x180027f96  jz      loc_1800280E4
0x180027f9c  mov     eax, 83h
0x180027fa1  mov     word ptr [rbp+57h+arg_18], ax
0x180027fa5  mov     [rbp+57h+var_80], edi
0x180027fa8  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027fb0  jz      loc_1800280E4
0x180027fb6  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027fbd  mov     rcx, rdi; wchar_t *
0x180027fc0  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027fc5  mov     r8d, 2
0x180027fcb  jmp     loc_180028094
0x180027fd0  xor     r9d, r9d; bDaclDefaulted
0x180027fd3  mov     r8, rdi; pDacl
0x180027fd6  mov     edx, ebx; bDaclPresent
0x180027fd8  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180027fdc  call    cs:__imp_SetSecurityDescriptorDacl
0x180027fe2  test    eax, eax
0x180027fe4  jnz     short loc_180028036
0x180027fe6  call    cs:__imp_GetLastError
0x180027fec  mov     edi, eax
0x180027fee  lea     rax, WPP_GLOBAL_Control
0x180027ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ffc  cmp     rcx, rax
0x180027fff  jz      short loc_180028024
0x180028001  test    [rcx+10Ch], bl
0x180028007  jz      short loc_180028024
0x180028009  mov     edx, 2Fh ; '/'
0x18002800e  mov     r9d, edi
0x180028011  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x180028018  mov     rcx, [rcx+100h]
0x18002801f  call    WPP_SF_d
0x180028024  test    edi, edi
0x180028026  jz      loc_1800280E4
0x18002802c  mov     eax, 84h
0x180028031  jmp     loc_180027FA1
0x180028036  xor     r9d, r9d
0x180028039  lea     r8d, [r9+4]
0x18002803d  lea     rdx, [rbp+57h+pSecurityDescriptor]
0x180028041  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]
0x180028045  call    ?MQSec_CopySecurityDescriptor@@YAHPEAX0KW4enumCopyControl@@@Z; MQSec_CopySecurityDescriptor(void *,void *,ulong,enumCopyControl)
0x18002804a  test    eax, eax
0x18002804c  jnz     short loc_180028058
0x18002804e  mov     edx, 85h
0x180028053  jmp     loc_180027F17
0x180028058  lea     r8, [rbp+57h+arg_18]; unsigned int *
0x18002805c  mov     rdx, rsi; void **
0x18002805f  mov     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180028063  call    ?MQSec_MakeSelfRelative@@YAJPEAXPEAPEAXPEAK@Z; MQSec_MakeSelfRelative(void *,void * *,ulong *)
0x180028068  test    eax, eax
0x18002806a  jns     short loc_1800280E6
0x18002806c  mov     ecx, 86h
0x180028071  mov     word ptr [rbp+57h+arg_18], cx
0x180028075  mov     [rbp+57h+var_80], eax
0x180028078  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180028080  jz      short loc_1800280E4
0x180028082  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180028089  mov     rcx, rdi; wchar_t *
0x18002808c  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180028091  mov     r8d, ebx
0x180028094  mov     [rsp+0E0h+var_90], 0
0x18002809d  lea     r9d, [rbx+rax]
0x1800280a1  mov     [rsp+0E0h+var_98], 0
0x1800280aa  lea     rax, [rbp+57h+var_80]
0x1800280ae  mov     [rsp+0E0h+var_A0], rax
0x1800280b3  mov     [rsp+0E0h+var_A8], 4
0x1800280bc  lea     rax, [rbp+57h+arg_18]
0x1800280c0  mov     [rsp+0E0h+var_B0], rax
0x1800280c5  mov     [rsp+0E0h+var_B8], 2
0x1800280ce  mov     [rsp+0E0h+var_C0], rdi
0x1800280d3  add     r9, r9
0x1800280d6  mov     edx, ebx
0x1800280d8  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800280df  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800280e4  xor     bl, bl
0x1800280e6  lea     rcx, [rbp+57h+var_78]; this
0x1800280ea  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x1800280ef  mov     al, bl
0x1800280f1  add     rsp, 0C8h
0x1800280f8  pop     rdi
0x1800280f9  pop     rsi
0x1800280fa  pop     rbx
0x1800280fb  pop     rbp
0x1800280fc  retn
```
