# MQSec_MergeSecurityDescriptors(ulong,int,ulong,void *,void *,void * *)

- ea: `0x180027ca0`
- end: `0x180027ec3`
- name: `?MQSec_MergeSecurityDescriptors@@YAJKHKPEAX0PEAPEAX@Z`
- size: `547`
- prototype: `__int64 __fastcall(unsigned int, int, unsigned int, void *, PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004074`
- `0x1800138c0`
- `0x180017430`
- `0x1800254a8`
- `0x180027500`
- `0x180027800`
- `0x180027a50`
- `0x180027ba0`
- `0x180027ca0`

## import_xrefs

- `msvcrt!free` at `0x180027dbf`
- `msvcrt!free` at `0x180027dfb`
- `msvcrt!free` at `0x180027ea1`
- `msvcrt!free` at `0x180027dbf`
- `msvcrt!free` at `0x180027dfb`
- `msvcrt!free` at `0x180027ea1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MQSec_MergeSecurityDescriptors(
        int a1,
        unsigned int a2,
        char a3,
        void *a4,
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        void **a6)
{
  signed int DefaultPublicQueueSecurityDescriptor; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int16 v14; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v15; // [rsp+68h] [rbp-21h] BYREF
  void *Block; // [rsp+70h] [rbp-19h] BYREF
  _OWORD v17[2]; // [rsp+78h] [rbp-11h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+98h] [rbp+Fh]

  memset(v17, 0, sizeof(v17));
  pAbsoluteSecurityDescriptor = 0;
  if ( MQSec_MakeAbsoluteSD(pSelfRelativeSecurityDescriptor, (struct CAbsSecurityDsecripror *)v17) )
  {
    Block = 0;
    if ( a1 == 1 )
    {
      DefaultPublicQueueSecurityDescriptor = MQSec_GetDefaultPublicQueueSecurityDescriptor(&Block, a2, a4, 0, 2, 0);
      if ( DefaultPublicQueueSecurityDescriptor < 0 )
      {
        v14 = 1100;
        v15 = DefaultPublicQueueSecurityDescriptor;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v11 = mqwcslen(L"acssctrl/secdscrp");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v11 + 1),
            L"acssctrl/secdscrp",
            2,
            &v14,
            4,
            &v15,
            0,
            0);
        }
        goto LABEL_15;
      }
      a4 = Block;
    }
    if ( !(unsigned int)MQSec_CopySecurityDescriptor(pAbsoluteSecurityDescriptor, a4, a3, 1) )
    {
      LogIllegalPoint((wchar_t *)L"acssctrl/secdscrp", 0x8Fu);
      free(Block);
      goto LABEL_11;
    }
    DefaultPublicQueueSecurityDescriptor = MQSec_MakeSelfRelative(pAbsoluteSecurityDescriptor, a6, &v15);
    if ( DefaultPublicQueueSecurityDescriptor < 0 )
    {
      v14 = 90;
      v15 = DefaultPublicQueueSecurityDescriptor;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v12 = mqwcslen(L"acssctrl/secdscrp");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v12 + 1),
          L"acssctrl/secdscrp",
          2,
          &v14,
          4,
          &v15,
          0,
          0);
      }
    }
LABEL_15:
    free(Block);
    goto LABEL_16;
  }
  LogIllegalPoint((wchar_t *)L"acssctrl/secdscrp", 0x8Cu);
LABEL_11:
  DefaultPublicQueueSecurityDescriptor = -1072821247;
LABEL_16:
  CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v17);
  return (unsigned int)DefaultPublicQueueSecurityDescriptor;
}

```

## disassembly

```asm
0x180027ca0  push    rbp
0x180027ca2  push    rbx
0x180027ca3  push    rsi
0x180027ca4  push    rdi
0x180027ca5  push    r12
0x180027ca7  push    r14
0x180027ca9  lea     rbp, [rsp-1Fh]
0x180027cae  sub     rsp, 0A8h
0x180027cb5  mov     rbx, r9
0x180027cb8  mov     r14d, r8d
0x180027cbb  mov     esi, edx
0x180027cbd  mov     edi, ecx
0x180027cbf  xorps   xmm0, xmm0
0x180027cc2  movdqu  [rbp+47h+var_58], xmm0
0x180027cc7  xorps   xmm1, xmm1
0x180027cca  movdqu  [rbp+47h+var_48], xmm1
0x180027ccf  mov     [rbp+47h+pAbsoluteSecurityDescriptor], 0
0x180027cd7  lea     rdx, [rbp+47h+var_58]; struct CAbsSecurityDsecripror *
0x180027cdb  mov     rcx, [rbp+47h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180027cdf  call    ?MQSec_MakeAbsoluteSD@@YA_NPEAXPEAUCAbsSecurityDsecripror@@@Z; MQSec_MakeAbsoluteSD(void *,CAbsSecurityDsecripror *)
0x180027ce4  test    al, al
0x180027ce6  jnz     short loc_180027CFE
0x180027ce8  mov     edx, 8Ch; unsigned __int16
0x180027ced  lea     rcx, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027cf4  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x180027cf9  jmp     loc_180027E02
0x180027cfe  mov     [rbp+47h+Block], 0
0x180027d06  mov     r12d, 1
0x180027d0c  cmp     edi, r12d
0x180027d0f  jnz     loc_180027DCF
0x180027d15  mov     [rsp+0D0h+var_A8], 0
0x180027d1e  mov     dword ptr [rsp+0D0h+var_B0], 2
0x180027d26  xor     r9d, r9d
0x180027d29  mov     r8, rbx
0x180027d2c  mov     edx, esi
0x180027d2e  lea     rcx, [rbp+47h+Block]
0x180027d32  call    ?MQSec_GetDefaultPublicQueueSecurityDescriptor@@YAJPEAPEAXHPEAXKW4enumDaclType@@1@Z; MQSec_GetDefaultPublicQueueSecurityDescriptor(void * *,int,void *,ulong,enumDaclType,void *)
0x180027d37  mov     ebx, eax
0x180027d39  test    eax, eax
0x180027d3b  jns     loc_180027DCB
0x180027d41  mov     eax, 44Ch
0x180027d46  mov     [rbp+47h+var_70], ax
0x180027d4a  mov     [rbp+47h+var_68], ebx
0x180027d4d  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027d55  jz      short loc_180027DBB
0x180027d57  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027d5e  mov     rcx, rdi; wchar_t *
0x180027d61  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027d66  lea     r9d, [r12+rax]
0x180027d6a  add     r9, r9
0x180027d6d  mov     [rsp+0D0h+var_80], 0
0x180027d76  mov     [rsp+0D0h+var_88], 0
0x180027d7f  lea     rax, [rbp+47h+var_68]
0x180027d83  mov     [rsp+0D0h+var_90], rax
0x180027d88  mov     [rsp+0D0h+var_98], 4
0x180027d91  lea     rax, [rbp+47h+var_70]
0x180027d95  mov     [rsp+0D0h+var_A0], rax
0x180027d9a  mov     [rsp+0D0h+var_A8], 2
0x180027da3  mov     [rsp+0D0h+var_B0], rdi
0x180027da8  mov     r8d, r12d
0x180027dab  mov     edx, r12d
0x180027dae  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027db5  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180027dba  nop
0x180027dbb  mov     rcx, [rbp+47h+Block]; Block
0x180027dbf  call    cs:__imp_free
0x180027dc5  nop
0x180027dc6  jmp     loc_180027EA8
0x180027dcb  mov     rbx, [rbp+47h+Block]
0x180027dcf  mov     r9d, r12d
0x180027dd2  mov     r8d, r14d
0x180027dd5  mov     rdx, rbx
0x180027dd8  mov     rcx, [rbp+47h+pAbsoluteSecurityDescriptor]
0x180027ddc  call    ?MQSec_CopySecurityDescriptor@@YAHPEAX0KW4enumCopyControl@@@Z; MQSec_CopySecurityDescriptor(void *,void *,ulong,enumCopyControl)
0x180027de1  test    eax, eax
0x180027de3  jnz     short loc_180027E0C
0x180027de5  mov     edx, 8Fh; unsigned __int16
0x180027dea  lea     rcx, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027df1  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x180027df6  nop
0x180027df7  mov     rcx, [rbp+47h+Block]; Block
0x180027dfb  call    cs:__imp_free
0x180027e01  nop
0x180027e02  mov     ebx, 0C00E0C01h
0x180027e07  jmp     loc_180027EA8
0x180027e0c  lea     r8, [rbp+47h+var_68]; unsigned int *
0x180027e10  mov     rdx, [rbp+47h+arg_28]; void **
0x180027e14  mov     rcx, [rbp+47h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180027e18  call    ?MQSec_MakeSelfRelative@@YAJPEAXPEAPEAXPEAK@Z; MQSec_MakeSelfRelative(void *,void * *,ulong *)
0x180027e1d  mov     ebx, eax
0x180027e1f  test    eax, eax
0x180027e21  jns     short loc_180027E9D
0x180027e23  mov     eax, 5Ah ; 'Z'
0x180027e28  mov     [rbp+47h+var_70], ax
0x180027e2c  mov     [rbp+47h+var_68], ebx
0x180027e2f  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027e37  jz      short loc_180027E9D
0x180027e39  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027e40  mov     rcx, rdi; wchar_t *
0x180027e43  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027e48  lea     r9d, [r12+rax]
0x180027e4c  add     r9, r9
0x180027e4f  mov     [rsp+0D0h+var_80], 0
0x180027e58  mov     [rsp+0D0h+var_88], 0
0x180027e61  lea     rax, [rbp+47h+var_68]
0x180027e65  mov     [rsp+0D0h+var_90], rax
0x180027e6a  mov     [rsp+0D0h+var_98], 4
0x180027e73  lea     rax, [rbp+47h+var_70]
0x180027e77  mov     [rsp+0D0h+var_A0], rax
0x180027e7c  mov     [rsp+0D0h+var_A8], 2
0x180027e85  mov     [rsp+0D0h+var_B0], rdi
0x180027e8a  mov     r8d, r12d
0x180027e8d  mov     edx, r12d
0x180027e90  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027e97  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180027e9c  nop
0x180027e9d  mov     rcx, [rbp+47h+Block]; Block
0x180027ea1  call    cs:__imp_free
0x180027ea7  nop
0x180027ea8  lea     rcx, [rbp+47h+var_58]; this
0x180027eac  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x180027eb1  mov     eax, ebx
0x180027eb3  add     rsp, 0A8h
0x180027eba  pop     r14
0x180027ebc  pop     r12
0x180027ebe  pop     rdi
0x180027ebf  pop     rsi
0x180027ec0  pop     rbx
0x180027ec1  pop     rbp
0x180027ec2  retn
```
