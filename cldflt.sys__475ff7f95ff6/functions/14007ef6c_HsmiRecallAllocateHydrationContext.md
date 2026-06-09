# HsmiRecallAllocateHydrationContext

- ea: `0x14007ef6c`
- end: `0x14007f332`
- name: `HsmiRecallAllocateHydrationContext`
- size: `966`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, struct _FILE_OBJECT *, int, int, PFLT_CALLBACK_DATA CallbackData, __int64, __int64, __int64, __int64, __int64, _QWORD *)`
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
- `0x140017f44`
- `0x14001e600`
- `0x140058ddc`
- `0x14005f670`
- `0x14007ef6c`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14007f1b7`
- `ntoskrnl!ObfReferenceObject` at `0x14007f1b7`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14007f2b8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14007f2b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f18c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f18c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14007f0e4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14007f0e4`
- `FLTMGR!FltReferenceContext` at `0x14007f2e4`
- `FLTMGR!FltReferenceContext` at `0x14007f2fc`
- `FLTMGR!FltReferenceContext` at `0x14007f2e4`
- `FLTMGR!FltReferenceContext` at `0x14007f2fc`

## pseudocode

```c
__int64 __fastcall HsmiRecallAllocateHydrationContext(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        struct _FILE_OBJECT *a4,
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
  int FullFilePath; // ebp
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
  FullFilePath = HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a3, CallbackData);
  HsmDbgBreakOnStatus(FullFilePath);
  if ( FullFilePath < 0 )
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
    FullFilePath = HsmiQueryFullFilePath(*(_QWORD *)(v18 + 32), v20, a4, 0x101u, P);
    HsmDbgBreakOnStatus(FullFilePath);
    if ( FullFilePath < 0
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
    FullFilePath = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
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
0x14007ef6c  mov     [rsp+arg_8], rbx
0x14007ef71  mov     [rsp+arg_0], rcx
0x14007ef76  push    rbp
0x14007ef77  push    rsi
0x14007ef78  push    rdi
0x14007ef79  push    r12
0x14007ef7b  push    r13
0x14007ef7d  push    r14
0x14007ef7f  push    r15
0x14007ef81  sub     rsp, 70h
0x14007ef85  mov     rax, [r8+10h]
0x14007ef89  mov     r14, rdx
0x14007ef8c  mov     r13, [rsp+0A8h+CallbackData]
0x14007ef94  xorps   xmm0, xmm0
0x14007ef97  mov     rdx, r13; CallbackData
0x14007ef9a  mov     rcx, r8; Context
0x14007ef9d  mov     r12, r9
0x14007efa0  mov     rsi, r8
0x14007efa3  mov     rbx, [rax+20h]
0x14007efa7  mov     rdi, [rax+10h]
0x14007efab  mov     [rsp+0A8h+arg_10], rbx
0x14007efb3  movups  xmmword ptr [rsp+0A8h+P], xmm0
0x14007efb8  call    HsmpAcquireSyncOpRundownProtection
0x14007efbd  mov     ecx, eax
0x14007efbf  mov     ebp, eax
0x14007efc1  call    HsmDbgBreakOnStatus
0x14007efc6  test    ebp, ebp
0x14007efc8  jns     short loc_14007F035
0x14007efca  mov     r10, cs:WPP_GLOBAL_Control
0x14007efd1  lea     r15, WPP_GLOBAL_Control
0x14007efd8  cmp     r10, r15
0x14007efdb  jz      loc_14007F179
0x14007efe1  mov     ecx, [r10+2Ch]
0x14007efe5  test    cl, 1
0x14007efe8  jz      loc_14007F179
0x14007efee  cmp     byte ptr [r10+29h], 2
0x14007eff3  jb      loc_14007F179
0x14007eff9  mov     eax, [rsi+1Ch]
0x14007effc  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14007f003  mov     rcx, [r10+18h]
0x14007f007  mov     edx, 12h
0x14007f00c  mov     dword ptr [rsp+0A8h+var_60], ebp
0x14007f010  mov     r9, rdi
0x14007f013  mov     [rsp+0A8h+var_68], r13
0x14007f018  mov     [rsp+0A8h+var_70], rbx
0x14007f01d  mov     [rsp+0A8h+var_78], r12
0x14007f022  mov     dword ptr [rsp+0A8h+var_80], eax
0x14007f026  mov     [rsp+0A8h+var_88], rsi
0x14007f02b  call    WPP_SF_qqLqiqd
0x14007f030  jmp     loc_14007F179
0x14007f035  mov     ebx, [rsp+0A8h+arg_28]
0x14007f03c  lea     r15, WPP_GLOBAL_Control
0x14007f043  bt      ebx, 16h
0x14007f047  jnb     loc_14007F0DD
0x14007f04d  mov     rcx, [rdi+20h]
0x14007f051  lea     rax, [rsp+0A8h+P]
0x14007f056  mov     r9d, 101h
0x14007f05c  mov     [rsp+0A8h+var_88], rax
0x14007f061  mov     r8, r12
0x14007f064  call    HsmiQueryFullFilePath
0x14007f069  mov     ecx, eax
0x14007f06b  mov     ebp, eax
0x14007f06d  call    HsmDbgBreakOnStatus
0x14007f072  test    ebp, ebp
0x14007f074  jns     short loc_14007F0DD
0x14007f076  mov     r10, cs:WPP_GLOBAL_Control
0x14007f07d  cmp     r10, r15
0x14007f080  jz      short loc_14007F0DD
0x14007f082  mov     eax, [r10+2Ch]
0x14007f086  test    al, 1
0x14007f088  jz      short loc_14007F0DD
0x14007f08a  cmp     byte ptr [r10+29h], 3
0x14007f08f  jb      short loc_14007F0DD
0x14007f091  mov     rcx, rsi
0x14007f094  call    HsmpGetStreamSize
0x14007f099  mov     rcx, [rsp+0A8h+arg_10]
0x14007f0a1  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14007f0a8  mov     [rsp+0A8h+var_58], ebp
0x14007f0ac  mov     edx, 13h
0x14007f0b1  mov     [rsp+0A8h+var_60], r13
0x14007f0b6  mov     r9, rdi
0x14007f0b9  mov     [rsp+0A8h+var_68], rcx
0x14007f0be  mov     rcx, [r10+18h]
0x14007f0c2  mov     [rsp+0A8h+var_70], r12
0x14007f0c7  mov     [rsp+0A8h+var_78], rax
0x14007f0cc  mov     eax, [rsi+1Ch]
0x14007f0cf  mov     dword ptr [rsp+0A8h+var_80], eax
0x14007f0d3  mov     [rsp+0A8h+var_88], rsi
0x14007f0d8  call    WPP_SF_qqLiqiqd
0x14007f0dd  lea     rcx, stru_140029340; Lookaside
0x14007f0e4  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14007f0eb  nop     dword ptr [rax+rax+00h]
0x14007f0f0  mov     rdi, rax
0x14007f0f3  test    rax, rax
0x14007f0f6  jnz     loc_14007F19D
0x14007f0fc  mov     ebp, 0C000009Ah
0x14007f101  mov     ecx, ebp
0x14007f103  call    HsmDbgBreakOnStatus
0x14007f108  mov     r11, cs:WPP_GLOBAL_Control
0x14007f10f  cmp     r11, r15
0x14007f112  jz      short loc_14007F171
0x14007f114  mov     eax, [r11+2Ch]
0x14007f118  test    al, 1
0x14007f11a  jz      short loc_14007F171
0x14007f11c  cmp     byte ptr [r11+29h], 2
0x14007f121  jb      short loc_14007F171
0x14007f123  mov     rcx, rsi
0x14007f126  call    HsmpGetStreamSize
0x14007f12b  mov     r10, [rsp+0A8h+arg_48]
0x14007f133  lea     edx, [rdi+14h]
0x14007f136  mov     r8, [rsp+0A8h+arg_50]
0x14007f13e  mov     r9, r13
0x14007f141  mov     rcx, [r11+18h]
0x14007f145  add     r8, r10
0x14007f148  mov     [rsp+0A8h+var_58], ebp
0x14007f14c  mov     [rsp+0A8h+var_60], rax
0x14007f151  mov     eax, [rsi+1Ch]
0x14007f154  mov     dword ptr [rsp+0A8h+var_68], eax
0x14007f158  mov     [rsp+0A8h+var_70], rsi
0x14007f15d  mov     [rsp+0A8h+var_78], r14
0x14007f162  mov     [rsp+0A8h+var_80], r8
0x14007f167  mov     [rsp+0A8h+var_88], r10
0x14007f16c  call    WPP_SF_qiiqqLid
0x14007f171  mov     rcx, rsi; Context
0x14007f174  call    HsmpReleaseSyncOpRundownProtection
0x14007f179  mov     rcx, [rsp+0A8h+P+8]; P
0x14007f17e  test    rcx, rcx
0x14007f181  jz      loc_14007F317
0x14007f187  mov     edx, 73557348h; Tag
0x14007f18c  call    cs:__imp_ExFreePoolWithTag
0x14007f193  nop     dword ptr [rax+rax+00h]
0x14007f198  jmp     loc_14007F317
0x14007f19d  lea     rcx, [rax+4]; void *
0x14007f1a1  xor     edx, edx; Val
0x14007f1a3  mov     r8d, 0ACh; Size
0x14007f1a9  call    memset
0x14007f1ae  mov     rcx, r12; Object
0x14007f1b1  mov     dword ptr [rdi], 63527348h
0x14007f1b7  call    cs:__imp_ObfReferenceObject
0x14007f1be  nop     dword ptr [rax+rax+00h]
0x14007f1c3  mov     ecx, [rdi+30h]
0x14007f1c6  mov     eax, [rsp+0A8h+arg_20]
0x14007f1cd  and     ecx, 0FFFFFE60h
0x14007f1d3  and     eax, 1Fh
0x14007f1d6  mov     [rdi+10h], r12
0x14007f1da  xor     ecx, eax
0x14007f1dc  mov     qword ptr [rdi+8], 1
0x14007f1e4  mov     rax, [rsp+0A8h+arg_38]
0x14007f1ec  or      ecx, 40h
0x14007f1ef  mov     [rdi+38h], rax
0x14007f1f3  mov     rax, [rsp+0A8h+arg_40]
0x14007f1fb  mov     [rdi+40h], rax
0x14007f1ff  mov     rax, [rsp+0A8h+arg_48]
0x14007f207  mov     [rdi+48h], rax
0x14007f20b  mov     rax, [rsp+0A8h+arg_50]
0x14007f213  mov     [rdi+30h], ecx
0x14007f216  mov     ecx, [rdi+2Ch]
0x14007f219  mov     edx, ecx
0x14007f21b  mov     [rdi+50h], rax
0x14007f21f  mov     [rdi+18h], r13
0x14007f223  mov     qword ptr [rdi+20h], 0
0x14007f22b  mov     [rdi+28h], ebx
0x14007f22e  mov     rax, [r13+10h]
0x14007f232  xor     edx, [rax]
0x14007f234  and     edx, 1
0x14007f237  xor     edx, ecx
0x14007f239  mov     [rdi+2Ch], edx
0x14007f23c  and     edx, 0FFFFFFFDh
0x14007f23f  mov     rax, [r13+10h]
0x14007f243  mov     r8d, [rax]
0x14007f246  and     r8d, 2
0x14007f24a  or      r8d, edx
0x14007f24d  mov     [rdi+2Ch], r8d
0x14007f251  mov     rax, [r13+10h]
0x14007f255  mov     ecx, [rax]
0x14007f257  test    cl, 2
0x14007f25a  jnz     short loc_14007F270
0x14007f25c  test    r14, r14
0x14007f25f  jz      short loc_14007F270
0x14007f261  mov     eax, [r14+28h]
0x14007f265  test    al, 1
0x14007f267  jz      short loc_14007F270
0x14007f269  mov     eax, 10h
0x14007f26e  jmp     short loc_14007F272
0x14007f270  xor     eax, eax
0x14007f272  and     r8d, 0FFFFFFEFh
0x14007f276  or      r8d, eax
0x14007f279  mov     [rdi+2Ch], r8d
0x14007f27d  test    r14, r14
0x14007f280  jz      short loc_14007F291
0x14007f282  mov     eax, [r14+28h]
0x14007f286  test    al, 4
0x14007f288  jz      short loc_14007F291
0x14007f28a  mov     eax, 8
0x14007f28f  jmp     short loc_14007F293
0x14007f291  xor     eax, eax
0x14007f293  and     r8d, 0FFFFFFF7h
0x14007f297  mov     ecx, 80h
0x14007f29c  or      r8d, eax
0x14007f29f  xor     eax, eax
0x14007f2a1  btr     r8d, 7
0x14007f2a6  cmp     [rsp+0A8h+arg_20], 4
0x14007f2ae  cmovz   eax, ecx
0x14007f2b1  or      r8d, eax
0x14007f2b4  mov     [rdi+2Ch], r8d
0x14007f2b8  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14007f2bf  nop     dword ptr [rax+rax+00h]
0x14007f2c4  movups  xmm0, xmmword ptr [rsp+0A8h+P]
0x14007f2c9  mov     [rdi+98h], rax
0x14007f2d0  mov     rcx, rsi; Context
0x14007f2d3  mov     rax, [rsp+0A8h+arg_0]
0x14007f2db  movdqu  xmmword ptr [rdi+58h], xmm0
0x14007f2e0  mov     [rdi+68h], rax
0x14007f2e4  call    cs:__imp_FltReferenceContext
0x14007f2eb  nop     dword ptr [rax+rax+00h]
0x14007f2f0  mov     [rdi+78h], rsi
0x14007f2f4  test    r14, r14
0x14007f2f7  jz      short loc_14007F30C
0x14007f2f9  mov     rcx, r14; Context
0x14007f2fc  call    cs:__imp_FltReferenceContext
0x14007f303  nop     dword ptr [rax+rax+00h]
0x14007f308  mov     [rdi+70h], r14
0x14007f30c  mov     rax, [rsp+0A8h+arg_60]
0x14007f314  mov     [rax], rdi
0x14007f317  mov     rbx, [rsp+0A8h+arg_8]
0x14007f31f  mov     eax, ebp
0x14007f321  add     rsp, 70h
0x14007f325  pop     r15
0x14007f327  pop     r14
0x14007f329  pop     r13
0x14007f32b  pop     r12
0x14007f32d  pop     rdi
0x14007f32e  pop     rsi
0x14007f32f  pop     rbp
0x14007f330  retn
```
