# HsmiRecallAllocateHydrationContext

- ea: `0x14007edd4`
- end: `0x14007f19a`
- name: `HsmiRecallAllocateHydrationContext`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140002aec`

## callees

- `0x140003c50`
- `0x140009ed4`
- `0x14000a048`
- `0x14000aafc`
- `0x14000cd0c`
- `0x140017ec4`
- `0x14001e580`
- `0x140058cbc`
- `0x14005f550`
- `0x14007edd4`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14007f01f`
- `ntoskrnl!ObfReferenceObject` at `0x14007f01f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14007f120`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14007f120`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eff4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14007ef4c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14007ef4c`
- `FLTMGR!FltReferenceContext` at `0x14007f14c`
- `FLTMGR!FltReferenceContext` at `0x14007f164`
- `FLTMGR!FltReferenceContext` at `0x14007f14c`
- `FLTMGR!FltReferenceContext` at `0x14007f164`

## pseudocode

```c
__int64 __fastcall HsmiRecallAllocateHydrationContext(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        void *a4,
        int a5,
        int a6,
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        _QWORD *a13)
{
  __int64 v13; // rax
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int64 FullFilePath; // rbp
  __int64 v20; // rdx
  char StreamSize; // al
  __int64 v22; // r10
  char *v23; // rax
  char *v24; // rdi
  __int64 v25; // rax
  __int64 v26; // r11
  unsigned int v27; // ecx
  int v28; // ecx
  int v29; // edx
  unsigned int v30; // r8d
  int v31; // eax
  unsigned int v32; // r8d
  int v33; // eax
  unsigned int v34; // r8d
  int v35; // eax
  unsigned int v36; // r8d
  ULONGLONG UnbiasedInterruptTime; // rax
  __int128 v38; // xmm0
  PVOID P[2]; // [rsp+60h] [rbp-48h] BYREF

  v13 = *(_QWORD *)(a3 + 16);
  v17 = *(_QWORD *)(v13 + 32);
  v18 = *(_QWORD *)(v13 + 16);
  *(_OWORD *)P = 0;
  FullFilePath = (unsigned int)HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a3, CallbackData);
  HsmDbgBreakOnStatus(FullFilePath);
  if ( (int)FullFilePath < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqLqiqd(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        v18,
        a3,
        *(_DWORD *)(a3 + 28),
        (char)a4,
        v17,
        CallbackData,
        FullFilePath);
    }
LABEL_18:
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0x73557348u);
    return (unsigned int)FullFilePath;
  }
  if ( (a6 & 0x400000) != 0 )
  {
    FullFilePath = (unsigned int)HsmiQueryFullFilePath(*(_QWORD *)(v18 + 32), v20, a4, 257, P);
    HsmDbgBreakOnStatus(FullFilePath);
    if ( (int)FullFilePath < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      StreamSize = HsmpGetStreamSize(a3);
      WPP_SF_qqLiqiqd(
        *(_QWORD *)(v22 + 24),
        19,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        v18,
        a3,
        *(_DWORD *)(a3 + 28),
        StreamSize,
        (char)a4,
        v17,
        CallbackData,
        FullFilePath);
    }
  }
  v23 = (char *)ExAllocateFromPagedLookasideList(&stru_140029340);
  v24 = v23;
  if ( !v23 )
  {
    LODWORD(FullFilePath) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v25 = HsmpGetStreamSize(a3);
      WPP_SF_qiiqqLid(
        *(_QWORD *)(v26 + 24),
        20,
        a10 + a11,
        CallbackData,
        a10,
        a10 + a11,
        a2,
        a3,
        *(_DWORD *)(a3 + 28),
        v25,
        -1073741670);
    }
    HsmpReleaseSyncOpRundownProtection((PFLT_CONTEXT)a3);
    goto LABEL_18;
  }
  memset(v23 + 4, 0, 0xACu);
  *(_DWORD *)v24 = 1666347848;
  ObfReferenceObject(a4);
  v27 = *((_DWORD *)v24 + 12) & 0xFFFFFE60;
  *((_QWORD *)v24 + 2) = a4;
  *((_QWORD *)v24 + 1) = 1;
  *((_QWORD *)v24 + 7) = a8;
  *((_QWORD *)v24 + 8) = a9;
  *((_QWORD *)v24 + 9) = a10;
  *((_DWORD *)v24 + 12) = a5 & 0x1F ^ v27 | 0x40;
  v28 = *((_DWORD *)v24 + 11);
  *((_QWORD *)v24 + 10) = a11;
  *((_QWORD *)v24 + 3) = CallbackData;
  *((_QWORD *)v24 + 4) = 0;
  *((_DWORD *)v24 + 10) = a6;
  v29 = v28 ^ (CallbackData->Iopb->IrpFlags ^ v28) & 1;
  *((_DWORD *)v24 + 11) = v29;
  v30 = v29 & 0xFFFFFFFD | CallbackData->Iopb->IrpFlags & 2;
  *((_DWORD *)v24 + 11) = v30;
  if ( (CallbackData->Iopb->IrpFlags & 2) == 0 && a2 && (a2[10] & 1) != 0 )
    v31 = 16;
  else
    v31 = 0;
  v32 = v31 | v30 & 0xFFFFFFEF;
  *((_DWORD *)v24 + 11) = v32;
  if ( a2 && (a2[10] & 4) != 0 )
    v33 = 8;
  else
    v33 = 0;
  v34 = v33 | v32 & 0xFFFFFFF7;
  v35 = 0;
  v36 = v34 & 0xFFFFFF7F;
  if ( a5 == 4 )
    v35 = 128;
  *((_DWORD *)v24 + 11) = v35 | v36;
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  v38 = *(_OWORD *)P;
  *((_QWORD *)v24 + 19) = UnbiasedInterruptTime;
  *(_OWORD *)(v24 + 88) = v38;
  *((_QWORD *)v24 + 13) = a1;
  FltReferenceContext((PFLT_CONTEXT)a3);
  *((_QWORD *)v24 + 15) = a3;
  if ( a2 )
  {
    FltReferenceContext(a2);
    *((_QWORD *)v24 + 14) = a2;
  }
  *a13 = v24;
  return (unsigned int)FullFilePath;
}

```

## disassembly

```asm
0x14007edd4  mov     [rsp+arg_8], rbx
0x14007edd9  mov     [rsp+arg_0], rcx
0x14007edde  push    rbp
0x14007eddf  push    rsi
0x14007ede0  push    rdi
0x14007ede1  push    r12
0x14007ede3  push    r13
0x14007ede5  push    r14
0x14007ede7  push    r15
0x14007ede9  sub     rsp, 70h
0x14007eded  mov     rax, [r8+10h]
0x14007edf1  mov     r14, rdx
0x14007edf4  mov     r13, [rsp+0A8h+CallbackData]
0x14007edfc  xorps   xmm0, xmm0
0x14007edff  mov     rdx, r13; CallbackData
0x14007ee02  mov     rcx, r8; Context
0x14007ee05  mov     r12, r9
0x14007ee08  mov     rsi, r8
0x14007ee0b  mov     rbx, [rax+20h]
0x14007ee0f  mov     rdi, [rax+10h]
0x14007ee13  mov     [rsp+0A8h+arg_10], rbx
0x14007ee1b  movups  xmmword ptr [rsp+0A8h+P], xmm0
0x14007ee20  call    HsmpAcquireSyncOpRundownProtection
0x14007ee25  mov     ecx, eax
0x14007ee27  mov     ebp, eax
0x14007ee29  call    HsmDbgBreakOnStatus
0x14007ee2e  test    ebp, ebp
0x14007ee30  jns     short loc_14007EE9D
0x14007ee32  mov     r10, cs:WPP_GLOBAL_Control
0x14007ee39  lea     r15, WPP_GLOBAL_Control
0x14007ee40  cmp     r10, r15
0x14007ee43  jz      loc_14007EFE1
0x14007ee49  mov     ecx, [r10+2Ch]
0x14007ee4d  test    cl, 1
0x14007ee50  jz      loc_14007EFE1
0x14007ee56  cmp     byte ptr [r10+29h], 2
0x14007ee5b  jb      loc_14007EFE1
0x14007ee61  mov     eax, [rsi+1Ch]
0x14007ee64  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14007ee6b  mov     rcx, [r10+18h]
0x14007ee6f  mov     edx, 12h
0x14007ee74  mov     dword ptr [rsp+0A8h+var_60], ebp
0x14007ee78  mov     r9, rdi
0x14007ee7b  mov     [rsp+0A8h+var_68], r13
0x14007ee80  mov     [rsp+0A8h+var_70], rbx
0x14007ee85  mov     [rsp+0A8h+var_78], r12
0x14007ee8a  mov     dword ptr [rsp+0A8h+var_80], eax
0x14007ee8e  mov     [rsp+0A8h+var_88], rsi
0x14007ee93  call    WPP_SF_qqLqiqd
0x14007ee98  jmp     loc_14007EFE1
0x14007ee9d  mov     ebx, [rsp+0A8h+arg_28]
0x14007eea4  lea     r15, WPP_GLOBAL_Control
0x14007eeab  bt      ebx, 16h
0x14007eeaf  jnb     loc_14007EF45
0x14007eeb5  mov     rcx, [rdi+20h]
0x14007eeb9  lea     rax, [rsp+0A8h+P]
0x14007eebe  mov     r9d, 101h
0x14007eec4  mov     [rsp+0A8h+var_88], rax
0x14007eec9  mov     r8, r12
0x14007eecc  call    HsmiQueryFullFilePath
0x14007eed1  mov     ecx, eax
0x14007eed3  mov     ebp, eax
0x14007eed5  call    HsmDbgBreakOnStatus
0x14007eeda  test    ebp, ebp
0x14007eedc  jns     short loc_14007EF45
0x14007eede  mov     r10, cs:WPP_GLOBAL_Control
0x14007eee5  cmp     r10, r15
0x14007eee8  jz      short loc_14007EF45
0x14007eeea  mov     eax, [r10+2Ch]
0x14007eeee  test    al, 1
0x14007eef0  jz      short loc_14007EF45
0x14007eef2  cmp     byte ptr [r10+29h], 3
0x14007eef7  jb      short loc_14007EF45
0x14007eef9  mov     rcx, rsi
0x14007eefc  call    HsmpGetStreamSize
0x14007ef01  mov     rcx, [rsp+0A8h+arg_10]
0x14007ef09  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14007ef10  mov     [rsp+0A8h+var_58], ebp
0x14007ef14  mov     edx, 13h
0x14007ef19  mov     [rsp+0A8h+var_60], r13
0x14007ef1e  mov     r9, rdi
0x14007ef21  mov     [rsp+0A8h+var_68], rcx
0x14007ef26  mov     rcx, [r10+18h]
0x14007ef2a  mov     [rsp+0A8h+var_70], r12
0x14007ef2f  mov     [rsp+0A8h+var_78], rax
0x14007ef34  mov     eax, [rsi+1Ch]
0x14007ef37  mov     dword ptr [rsp+0A8h+var_80], eax
0x14007ef3b  mov     [rsp+0A8h+var_88], rsi
0x14007ef40  call    WPP_SF_qqLiqiqd
0x14007ef45  lea     rcx, stru_140029340; Lookaside
0x14007ef4c  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14007ef53  nop     dword ptr [rax+rax+00h]
0x14007ef58  mov     rdi, rax
0x14007ef5b  test    rax, rax
0x14007ef5e  jnz     loc_14007F005
0x14007ef64  mov     ebp, 0C000009Ah
0x14007ef69  mov     ecx, ebp
0x14007ef6b  call    HsmDbgBreakOnStatus
0x14007ef70  mov     r11, cs:WPP_GLOBAL_Control
0x14007ef77  cmp     r11, r15
0x14007ef7a  jz      short loc_14007EFD9
0x14007ef7c  mov     eax, [r11+2Ch]
0x14007ef80  test    al, 1
0x14007ef82  jz      short loc_14007EFD9
0x14007ef84  cmp     byte ptr [r11+29h], 2
0x14007ef89  jb      short loc_14007EFD9
0x14007ef8b  mov     rcx, rsi
0x14007ef8e  call    HsmpGetStreamSize
0x14007ef93  mov     r10, [rsp+0A8h+arg_48]
0x14007ef9b  lea     edx, [rdi+14h]
0x14007ef9e  mov     r8, [rsp+0A8h+arg_50]
0x14007efa6  mov     r9, r13
0x14007efa9  mov     rcx, [r11+18h]
0x14007efad  add     r8, r10
0x14007efb0  mov     [rsp+0A8h+var_58], ebp
0x14007efb4  mov     [rsp+0A8h+var_60], rax
0x14007efb9  mov     eax, [rsi+1Ch]
0x14007efbc  mov     dword ptr [rsp+0A8h+var_68], eax
0x14007efc0  mov     [rsp+0A8h+var_70], rsi
0x14007efc5  mov     [rsp+0A8h+var_78], r14
0x14007efca  mov     [rsp+0A8h+var_80], r8
0x14007efcf  mov     [rsp+0A8h+var_88], r10
0x14007efd4  call    WPP_SF_qiiqqLid
0x14007efd9  mov     rcx, rsi; Context
0x14007efdc  call    HsmpReleaseSyncOpRundownProtection
0x14007efe1  mov     rcx, [rsp+0A8h+P+8]; P
0x14007efe6  test    rcx, rcx
0x14007efe9  jz      loc_14007F17F
0x14007efef  mov     edx, 73557348h; Tag
0x14007eff4  call    cs:__imp_ExFreePoolWithTag
0x14007effb  nop     dword ptr [rax+rax+00h]
0x14007f000  jmp     loc_14007F17F
0x14007f005  lea     rcx, [rax+4]; void *
0x14007f009  xor     edx, edx; Val
0x14007f00b  mov     r8d, 0ACh; Size
0x14007f011  call    memset
0x14007f016  mov     rcx, r12; Object
0x14007f019  mov     dword ptr [rdi], 63527348h
0x14007f01f  call    cs:__imp_ObfReferenceObject
0x14007f026  nop     dword ptr [rax+rax+00h]
0x14007f02b  mov     ecx, [rdi+30h]
0x14007f02e  mov     eax, [rsp+0A8h+arg_20]
0x14007f035  and     ecx, 0FFFFFE60h
0x14007f03b  and     eax, 1Fh
0x14007f03e  mov     [rdi+10h], r12
0x14007f042  xor     ecx, eax
0x14007f044  mov     qword ptr [rdi+8], 1
0x14007f04c  mov     rax, [rsp+0A8h+arg_38]
0x14007f054  or      ecx, 40h
0x14007f057  mov     [rdi+38h], rax
0x14007f05b  mov     rax, [rsp+0A8h+arg_40]
0x14007f063  mov     [rdi+40h], rax
0x14007f067  mov     rax, [rsp+0A8h+arg_48]
0x14007f06f  mov     [rdi+48h], rax
0x14007f073  mov     rax, [rsp+0A8h+arg_50]
0x14007f07b  mov     [rdi+30h], ecx
0x14007f07e  mov     ecx, [rdi+2Ch]
0x14007f081  mov     edx, ecx
0x14007f083  mov     [rdi+50h], rax
0x14007f087  mov     [rdi+18h], r13
0x14007f08b  mov     qword ptr [rdi+20h], 0
0x14007f093  mov     [rdi+28h], ebx
0x14007f096  mov     rax, [r13+10h]
0x14007f09a  xor     edx, [rax]
0x14007f09c  and     edx, 1
0x14007f09f  xor     edx, ecx
0x14007f0a1  mov     [rdi+2Ch], edx
0x14007f0a4  and     edx, 0FFFFFFFDh
0x14007f0a7  mov     rax, [r13+10h]
0x14007f0ab  mov     r8d, [rax]
0x14007f0ae  and     r8d, 2
0x14007f0b2  or      r8d, edx
0x14007f0b5  mov     [rdi+2Ch], r8d
0x14007f0b9  mov     rax, [r13+10h]
0x14007f0bd  mov     ecx, [rax]
0x14007f0bf  test    cl, 2
0x14007f0c2  jnz     short loc_14007F0D8
0x14007f0c4  test    r14, r14
0x14007f0c7  jz      short loc_14007F0D8
0x14007f0c9  mov     eax, [r14+28h]
0x14007f0cd  test    al, 1
0x14007f0cf  jz      short loc_14007F0D8
0x14007f0d1  mov     eax, 10h
0x14007f0d6  jmp     short loc_14007F0DA
0x14007f0d8  xor     eax, eax
0x14007f0da  and     r8d, 0FFFFFFEFh
0x14007f0de  or      r8d, eax
0x14007f0e1  mov     [rdi+2Ch], r8d
0x14007f0e5  test    r14, r14
0x14007f0e8  jz      short loc_14007F0F9
0x14007f0ea  mov     eax, [r14+28h]
0x14007f0ee  test    al, 4
0x14007f0f0  jz      short loc_14007F0F9
0x14007f0f2  mov     eax, 8
0x14007f0f7  jmp     short loc_14007F0FB
0x14007f0f9  xor     eax, eax
0x14007f0fb  and     r8d, 0FFFFFFF7h
0x14007f0ff  mov     ecx, 80h
0x14007f104  or      r8d, eax
0x14007f107  xor     eax, eax
0x14007f109  btr     r8d, 7
0x14007f10e  cmp     [rsp+0A8h+arg_20], 4
0x14007f116  cmovz   eax, ecx
0x14007f119  or      r8d, eax
0x14007f11c  mov     [rdi+2Ch], r8d
0x14007f120  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14007f127  nop     dword ptr [rax+rax+00h]
0x14007f12c  movups  xmm0, xmmword ptr [rsp+0A8h+P]
0x14007f131  mov     [rdi+98h], rax
0x14007f138  mov     rcx, rsi; Context
0x14007f13b  mov     rax, [rsp+0A8h+arg_0]
0x14007f143  movdqu  xmmword ptr [rdi+58h], xmm0
0x14007f148  mov     [rdi+68h], rax
0x14007f14c  call    cs:__imp_FltReferenceContext
0x14007f153  nop     dword ptr [rax+rax+00h]
0x14007f158  mov     [rdi+78h], rsi
0x14007f15c  test    r14, r14
0x14007f15f  jz      short loc_14007F174
0x14007f161  mov     rcx, r14; Context
0x14007f164  call    cs:__imp_FltReferenceContext
0x14007f16b  nop     dword ptr [rax+rax+00h]
0x14007f170  mov     [rdi+70h], r14
0x14007f174  mov     rax, [rsp+0A8h+arg_60]
0x14007f17c  mov     [rax], rdi
0x14007f17f  mov     rbx, [rsp+0A8h+arg_8]
0x14007f187  mov     eax, ebp
0x14007f189  add     rsp, 70h
0x14007f18d  pop     r15
0x14007f18f  pop     r14
0x14007f191  pop     r13
0x14007f193  pop     r12
0x14007f195  pop     rdi
0x14007f196  pop     rsi
0x14007f197  pop     rbp
0x14007f198  retn
```
