# CscSetInfopCanFlowRenameToServer

- ea: `0x140050dc0`
- end: `0x140051335`
- name: `CscSetInfopCanFlowRenameToServer`
- size: `1397`
- prototype: `__int64 __fastcall(__int64, _BYTE *, int, const UNICODE_STRING *, int *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400837e0`

## callees

- `0x1400084f0`
- `0x1400179f8`
- `0x1400180f4`
- `0x140018b50`
- `0x1400190ec`
- `0x14001a624`
- `0x14001b568`
- `0x14001f75c`
- `0x14002f010`
- `0x14002f0f0`
- `0x140050dc0`
- `0x14008c2d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140050f1e`
- `ntoskrnl!ExAllocatePool2` at `0x140051054`
- `ntoskrnl!ExAllocatePool2` at `0x140050f1e`
- `ntoskrnl!ExAllocatePool2` at `0x140051054`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400512d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400512d3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051081`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400510a5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051081`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400510a5`
- `rdbss!RxLastComponentUnicodeString` at `0x140050fad`
- `rdbss!RxLastComponentUnicodeString` at `0x140050fad`

## pseudocode

```c
__int64 __fastcall CscSetInfopCanFlowRenameToServer(
        __int64 a1,
        _BYTE *a2,
        int a3,
        const UNICODE_STRING *a4,
        int *a5,
        int *a6)
{
  __int64 v7; // rcx
  __int16 v10; // r12
  __int64 v11; // r13
  int NRNameFromAbsoluteName; // ebx
  int v13; // ecx
  __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // edi
  __int64 v18; // r9
  __int64 v19; // r12
  __int64 v20; // r9
  unsigned __int16 v21; // ax
  int v22; // ecx
  unsigned int v23; // eax
  NTSTATUS appended; // eax
  int v25; // eax
  int v26; // eax
  char v28; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v29[5]; // [rsp+44h] [rbp-85h] BYREF
  int v30; // [rsp+58h] [rbp-71h]
  int v31[2]; // [rsp+60h] [rbp-69h]
  UNICODE_STRING Source; // [rsp+68h] [rbp-61h] BYREF
  __int128 v33; // [rsp+78h] [rbp-51h] BYREF
  __int128 v34; // [rsp+88h] [rbp-41h] BYREF
  __int128 v35; // [rsp+98h] [rbp-31h]
  __int128 v36; // [rsp+A8h] [rbp-21h]
  __int64 v37; // [rsp+B8h] [rbp-11h]

  v7 = *(_QWORD *)(a1 + 456);
  *(_QWORD *)v31 = v7;
  v10 = *(_WORD *)(v7 + 20);
  v11 = *(_QWORD *)(a1 + 56);
  v30 = *(_DWORD *)(a1 + 472);
  v37 = 0;
  *(_OWORD *)&v29[1] = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  NRNameFromAbsoluteName = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    if ( a5 )
      v13 = *a5;
    else
      LOBYTE(v13) = -1;
    WPP_SF_ZZDD(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      (unsigned int)WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
      a3,
      (__int64)a4,
      v13,
      *a6);
    v7 = *(_QWORD *)v31;
  }
  if ( (*a2 & 0x10) != 0 || (*a6 & 0x80417) == 0 )
  {
    v17 = 853;
    goto LABEL_65;
  }
  v14 = *(_QWORD *)(a1 + 56);
  if ( v10 == 92 )
  {
    v15 = *(_QWORD *)(v14 + 128);
    v16 = *(_QWORD *)(a1 + 72);
    v17 = 0;
    v29[0] = 0;
    if ( (unsigned int)CscSetInfopGetNRNameFromAbsoluteName(v14, v16, v15, v7, 0, v29) != -2147483643 )
    {
      NRNameFromAbsoluteName = -1073740768;
      v17 = 878;
      goto LABEL_65;
    }
    if ( v29[0] > 0xFFFE )
    {
      NRNameFromAbsoluteName = -1073740768;
      v17 = 885;
      goto LABEL_65;
    }
    HIWORD(v29[1]) = v29[0];
    *(_QWORD *)&v29[3] = ExAllocatePool2(258, LOWORD(v29[0]), 1061124178, v18);
    if ( !*(_QWORD *)&v29[3] )
    {
      NRNameFromAbsoluteName = -1073741670;
      v17 = 895;
      goto LABEL_65;
    }
    v19 = *(_QWORD *)v31;
    NRNameFromAbsoluteName = CscSetInfopGetNRNameFromAbsoluteName(
                               *(_QWORD *)(a1 + 56),
                               *(_QWORD *)(a1 + 72),
                               *(_QWORD *)(*(_QWORD *)(a1 + 56) + 128LL),
                               *(__int64 *)v31,
                               *(char **)&v29[3],
                               v29);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v17 = 904;
      goto LABEL_65;
    }
    LOWORD(v29[1]) = v29[0];
  }
  else
  {
    v33 = 0;
    Source = *(UNICODE_STRING *)(v14 + 360);
    RxLastComponentUnicodeString(v14 + 360, 92, &v33);
    if ( !(_WORD)v33 || (v21 = *(_WORD *)(v14 + 360), v21 < (unsigned __int16)v33) )
    {
      NRNameFromAbsoluteName = -1073740768;
      v17 = 922;
      goto LABEL_65;
    }
    v22 = (unsigned __int16)(v21 - v33);
    v23 = v22 + a4->Length;
    Source.Length = v22;
    if ( v23 > 0xFFFE )
    {
      NRNameFromAbsoluteName = -1073741767;
      v17 = 930;
      goto LABEL_65;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        (unsigned int)WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
        v14 + 360,
        (__int64)&Source);
      LOWORD(v22) = Source.Length;
    }
    HIWORD(v29[1]) = a4->Length + v22;
    *(_QWORD *)&v29[3] = ExAllocatePool2(258, HIWORD(v29[1]), 1061124178, v20);
    if ( !*(_QWORD *)&v29[3] )
    {
      NRNameFromAbsoluteName = -1073741670;
      v17 = 944;
      goto LABEL_65;
    }
    NRNameFromAbsoluteName = RtlAppendUnicodeStringToString((PUNICODE_STRING)&v29[1], &Source);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v17 = 948;
      goto LABEL_65;
    }
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)&v29[1], a4);
    v17 = 0;
    NRNameFromAbsoluteName = appended;
    if ( appended < 0 )
    {
      v17 = 951;
      goto LABEL_65;
    }
    v19 = *(_QWORD *)v31;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, &v29[1]);
  v25 = CscQueryNetInfoUsingEnum(a1, &v29[1], &v34);
  NRNameFromAbsoluteName = v25;
  if ( v25 >= 0 || v25 == -1073741809 || v25 == -1073741772 || v25 == -1073741766 )
  {
    v26 = *a6;
    if ( NRNameFromAbsoluteName >= 0 )
    {
      if ( (v26 & 0x400) == 0
        && (v26 & 0x10) == 0
        && ((v26 & 0x40000) == 0
         || (_QWORD)v35 == *((_QWORD *)a6 + 4)
         && *((_QWORD *)&v36 + 1) == *((_QWORD *)a6 + 7)
         && ((a6[16] ^ (unsigned int)v37) & 0x4800) == 0) )
      {
        goto LABEL_65;
      }
    }
    else
    {
      NRNameFromAbsoluteName = 0;
      if ( (v26 & 0x410) != 0 )
        goto LABEL_65;
    }
    v28 = 1;
    if ( !a5 || (*a5 & 0x20) != 0 )
    {
      NRNameFromAbsoluteName = -1073741108;
      v17 = 1052;
    }
    else
    {
      *(_DWORD *)(a1 + 448) = 13;
      *(_QWORD *)(a1 + 456) = &v28;
      *(_DWORD *)(a1 + 472) = 1;
      if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 120) + 32LL) + 48LL) + 352LL) + 208LL)
        && (*(_DWORD *)(a1 + 128) & 2) == 0 )
      {
        *(_OWORD *)(a1 + 208) = 0;
        *(_OWORD *)(a1 + 224) = 0;
        *(_QWORD *)(a1 + 240) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 120) + 32LL) + 48LL)
                                                    + 352LL)
                                        + 208LL))(a1);
      }
      *(_DWORD *)(a1 + 472) = v30;
      *(_DWORD *)(a1 + 448) = 10;
      *(_QWORD *)(a1 + 456) = v19;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, a1, v11);
      CscTransitionFcbOffline(v11, 0, 8);
      *a2 |= 0x12u;
    }
  }
  else
  {
    if ( (unsigned __int8)CscCheckRdrStatusTransitionIfNetErr((unsigned int)v25, a2, v11) && (*a2 & 0x20) != 0 )
      NRNameFromAbsoluteName = 0;
    v17 = 979;
  }
LABEL_65:
  if ( *(_QWORD *)&v29[3] )
  {
    ExFreePoolWithTag(*(PVOID *)&v29[3], 0);
    *(_QWORD *)&v29[3] = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
      (unsigned int)NRNameFromAbsoluteName,
      v17);
  return (unsigned int)NRNameFromAbsoluteName;
}

```

## disassembly

```asm
0x140050dc0  push    rbp
0x140050dc2  push    rbx
0x140050dc3  push    rsi
0x140050dc4  push    rdi
0x140050dc5  push    r12
0x140050dc7  push    r13
0x140050dc9  push    r14
0x140050dcb  push    r15
0x140050dcd  lea     rbp, [rsp-0Fh]
0x140050dd2  sub     rsp, 0D8h
0x140050dd9  mov     rax, cs:__security_cookie
0x140050de0  xor     rax, rsp
0x140050de3  mov     [rbp+47h+var_50], rax
0x140050de7  mov     rsi, rcx
0x140050dea  xorps   xmm1, xmm1
0x140050ded  mov     rcx, [rcx+1C8h]
0x140050df4  xorps   xmm0, xmm0
0x140050df7  mov     rdi, r9
0x140050dfa  mov     qword ptr [rbp+47h+var_B0], rcx
0x140050dfe  mov     r15, rdx
0x140050e01  mov     eax, [rsi+1D8h]
0x140050e07  movzx   r12d, word ptr [rcx+14h]
0x140050e0c  mov     r13, [rsi+38h]
0x140050e10  mov     [rbp+47h+var_B8], eax
0x140050e13  xor     eax, eax
0x140050e15  mov     [rbp+47h+var_58], rax
0x140050e19  movups  xmmword ptr [rsp+110h+var_CC+4], xmm0
0x140050e1e  movups  [rbp+47h+var_88], xmm1
0x140050e22  movups  [rbp+47h+var_78], xmm1
0x140050e26  movups  [rbp+47h+var_68], xmm1
0x140050e2a  mov     r10, cs:WPP_GLOBAL_Control
0x140050e31  lea     rax, WPP_GLOBAL_Control
0x140050e38  mov     r14, [rbp+47h+arg_28]
0x140050e3c  xor     ebx, ebx
0x140050e3e  cmp     r10, rax
0x140050e41  jz      short loc_140050E87
0x140050e43  mov     eax, [r10+2Ch]
0x140050e47  test    al, 20h
0x140050e49  jz      short loc_140050E87
0x140050e4b  mov     rcx, [rbp+47h+arg_20]
0x140050e4f  test    rcx, rcx
0x140050e52  jz      short loc_140050E58
0x140050e54  mov     ecx, [rcx]
0x140050e56  jmp     short loc_140050E5B
0x140050e58  or      ecx, 0FFFFFFFFh
0x140050e5b  mov     eax, [r14]
0x140050e5e  mov     r9, r8
0x140050e61  mov     [rsp+110h+var_E0], eax
0x140050e65  lea     r8, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids
0x140050e6c  mov     dword ptr [rsp+110h+var_E8], ecx
0x140050e70  mov     edx, 13h
0x140050e75  mov     rcx, [r10+18h]
0x140050e79  mov     [rsp+110h+var_F0], rdi
0x140050e7e  call    WPP_SF_ZZDD
0x140050e83  mov     rcx, qword ptr [rbp+47h+var_B0]
0x140050e87  test    byte ptr [r15], 10h
0x140050e8b  jnz     loc_1400512BA
0x140050e91  test    dword ptr [r14], 80417h
0x140050e98  jz      loc_1400512BA
0x140050e9e  mov     rbx, [rsi+38h]
0x140050ea2  mov     edx, 5Ch ; '\'
0x140050ea7  cmp     dx, r12w
0x140050eab  jnz     loc_140050F8F
0x140050eb1  mov     r8, [rbx+80h]; int
0x140050eb8  lea     rax, [rsp+110h+var_CC]
0x140050ebd  mov     rdx, [rsi+48h]; int
0x140050ec1  xor     edi, edi
0x140050ec3  mov     r9, rcx; int
0x140050ec6  mov     [rsp+110h+var_E8], rax; __int64
0x140050ecb  mov     rcx, rbx; int
0x140050ece  mov     [rsp+110h+var_F0], rdi; void *
0x140050ed3  mov     dword ptr [rsp+110h+var_CC], edi
0x140050ed7  call    CscSetInfopGetNRNameFromAbsoluteName
0x140050edc  cmp     eax, 80000005h
0x140050ee1  jz      short loc_140050EF2
0x140050ee3  mov     ebx, 0C0000420h
0x140050ee8  mov     edi, 36Eh
0x140050eed  jmp     loc_1400512BF
0x140050ef2  mov     eax, dword ptr [rsp+110h+var_CC]
0x140050ef6  cmp     eax, 0FFFEh
0x140050efb  jbe     short loc_140050F0C
0x140050efd  mov     ebx, 0C0000420h
0x140050f02  mov     edi, 375h
0x140050f07  jmp     loc_1400512BF
0x140050f0c  movzx   edx, ax
0x140050f0f  mov     ecx, 102h
0x140050f14  mov     r8d, 3F3F7852h
0x140050f1a  mov     word ptr [rbp+47h+var_CC+6], ax
0x140050f1e  call    cs:__imp_ExAllocatePool2
0x140050f25  nop     dword ptr [rax+rax+00h]
0x140050f2a  mov     qword ptr [rbp+47h+var_CC+0Ch], rax
0x140050f2e  test    rax, rax
0x140050f31  jnz     short loc_140050F42
0x140050f33  mov     ebx, 0C000009Ah
0x140050f38  mov     edi, 37Fh
0x140050f3d  jmp     loc_1400512BF
0x140050f42  mov     rcx, [rsi+38h]; int
0x140050f46  lea     rax, [rsp+110h+var_CC]
0x140050f4b  mov     r12, qword ptr [rbp+47h+var_B0]
0x140050f4f  mov     rdx, [rsi+48h]; int
0x140050f53  mov     r9, r12; int
0x140050f56  mov     [rsp+110h+var_E8], rax; __int64
0x140050f5b  mov     rax, qword ptr [rbp+47h+var_CC+0Ch]
0x140050f5f  mov     r8, [rcx+80h]; int
0x140050f66  mov     [rsp+110h+var_F0], rax; void *
0x140050f6b  call    CscSetInfopGetNRNameFromAbsoluteName
0x140050f70  mov     ebx, eax
0x140050f72  test    eax, eax
0x140050f74  jns     short loc_140050F80
0x140050f76  mov     edi, 388h
0x140050f7b  jmp     loc_1400512BF
0x140050f80  movzx   eax, word ptr [rsp+110h+var_CC]
0x140050f85  mov     word ptr [rsp+110h+var_CC+4], ax
0x140050f8a  jmp     loc_1400510C7
0x140050f8f  xorps   xmm0, xmm0
0x140050f92  lea     r8, [rbp+47h+var_98]
0x140050f96  movups  [rbp+47h+var_98], xmm0
0x140050f9a  lea     rcx, [rbx+168h]
0x140050fa1  movups  xmm1, xmmword ptr [rbx+168h]
0x140050fa8  movdqu  xmmword ptr [rbp+47h+Source.Length], xmm1
0x140050fad  call    cs:__imp_RxLastComponentUnicodeString
0x140050fb4  nop     dword ptr [rax+rax+00h]
0x140050fb9  movzx   ecx, word ptr [rbp+47h+var_98]
0x140050fbd  test    cx, cx
0x140050fc0  jz      loc_1400512AE
0x140050fc6  movzx   eax, word ptr [rbx+168h]
0x140050fcd  cmp     ax, cx
0x140050fd0  jb      loc_1400512AE
0x140050fd6  sub     ax, cx
0x140050fd9  movzx   ecx, ax
0x140050fdc  movzx   eax, word ptr [rdi]
0x140050fdf  add     eax, ecx
0x140050fe1  mov     [rbp+47h+Source.Length], cx
0x140050fe5  cmp     eax, 0FFFEh
0x140050fea  jbe     short loc_140050FFB
0x140050fec  mov     ebx, 0C0000039h
0x140050ff1  mov     edi, 3A2h
0x140050ff6  jmp     loc_1400512BF
0x140050ffb  mov     r10, cs:WPP_GLOBAL_Control
0x140051002  lea     rax, WPP_GLOBAL_Control
0x140051009  cmp     r10, rax
0x14005100c  jz      short loc_14005103F
0x14005100e  mov     eax, [r10+2Ch]
0x140051012  test    al, 40h
0x140051014  jz      short loc_14005103F
0x140051016  mov     rcx, [r10+18h]
0x14005101a  lea     rax, [rbp+47h+Source]
0x14005101e  mov     edx, 14h
0x140051023  mov     [rsp+110h+var_F0], rax
0x140051028  lea     r9, [rbx+168h]
0x14005102f  lea     r8, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids
0x140051036  call    WPP_SF_ZZ
0x14005103b  movzx   ecx, [rbp+47h+Source.Length]
0x14005103f  add     cx, [rdi]
0x140051042  mov     r8d, 3F3F7852h
0x140051048  movzx   edx, cx
0x14005104b  mov     ecx, 102h
0x140051050  mov     word ptr [rbp+47h+var_CC+6], dx
0x140051054  call    cs:__imp_ExAllocatePool2
0x14005105b  nop     dword ptr [rax+rax+00h]
0x140051060  mov     qword ptr [rbp+47h+var_CC+0Ch], rax
0x140051064  test    rax, rax
0x140051067  jnz     short loc_140051078
0x140051069  mov     ebx, 0C000009Ah
0x14005106e  mov     edi, 3B0h
0x140051073  jmp     loc_1400512BF
0x140051078  lea     rdx, [rbp+47h+Source]; Source
0x14005107c  lea     rcx, [rsp+110h+var_CC+4]; Destination
0x140051081  call    cs:__imp_RtlAppendUnicodeStringToString
0x140051088  nop     dword ptr [rax+rax+00h]
0x14005108d  mov     ebx, eax
0x14005108f  test    eax, eax
0x140051091  jns     short loc_14005109D
0x140051093  mov     edi, 3B4h
0x140051098  jmp     loc_1400512BF
0x14005109d  mov     rdx, rdi; Source
0x1400510a0  lea     rcx, [rsp+110h+var_CC+4]; Destination
0x1400510a5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400510ac  nop     dword ptr [rax+rax+00h]
0x1400510b1  xor     edi, edi
0x1400510b3  mov     ebx, eax
0x1400510b5  test    eax, eax
0x1400510b7  jns     short loc_1400510C3
0x1400510b9  mov     edi, 3B7h
0x1400510be  jmp     loc_1400512BF
0x1400510c3  mov     r12, qword ptr [rbp+47h+var_B0]
0x1400510c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400510ce  lea     rax, WPP_GLOBAL_Control
0x1400510d5  cmp     rcx, rax
0x1400510d8  jz      short loc_1400510FB
0x1400510da  mov     eax, [rcx+2Ch]
0x1400510dd  test    al, 40h
0x1400510df  jz      short loc_1400510FB
0x1400510e1  mov     rcx, [rcx+18h]
0x1400510e5  lea     r9, [rsp+110h+var_CC+4]
0x1400510ea  mov     edx, 15h
0x1400510ef  lea     r8, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids
0x1400510f6  call    WPP_SF_Z
0x1400510fb  lea     r8, [rbp+47h+var_88]
0x1400510ff  mov     rcx, rsi
0x140051102  lea     rdx, [rsp+110h+var_CC+4]
0x140051107  call    CscQueryNetInfoUsingEnum
0x14005110c  mov     ebx, eax
0x14005110e  test    eax, eax
0x140051110  jns     short loc_140051149
0x140051112  cmp     eax, 0C000000Fh
0x140051117  jz      short loc_140051149
0x140051119  cmp     eax, 0C0000034h
0x14005111e  jz      short loc_140051149
0x140051120  cmp     eax, 0C000003Ah
0x140051125  jz      short loc_140051149
0x140051127  mov     r8, r13
0x14005112a  mov     rdx, r15
0x14005112d  mov     ecx, eax
0x14005112f  call    CscCheckRdrStatusTransitionIfNetErr
0x140051134  test    al, al
0x140051136  jz      short loc_14005113F
0x140051138  test    byte ptr [r15], 20h
0x14005113c  cmovnz  ebx, edi
0x14005113f  mov     edi, 3D3h
0x140051144  jmp     loc_1400512BF
0x140051149  mov     eax, [r14]
0x14005114c  xor     ecx, ecx
0x14005114e  test    ebx, ebx
0x140051150  jns     short loc_140051161
0x140051152  mov     ebx, ecx
0x140051154  test    eax, 410h
0x140051159  jnz     loc_1400512BF
0x14005115f  jmp     short loc_14005119B
0x140051161  bt      eax, 0Ah
0x140051165  jb      short loc_14005119B
0x140051167  test    al, 10h
0x140051169  jnz     short loc_14005119B
0x14005116b  bt      eax, 12h
0x14005116f  jnb     loc_1400512BF
0x140051175  mov     rax, [r14+20h]
0x140051179  cmp     qword ptr [rbp+47h+var_78], rax
0x14005117d  jnz     short loc_14005119B
0x14005117f  mov     rax, [r14+38h]
0x140051183  cmp     qword ptr [rbp+47h+var_68+8], rax
0x140051187  jnz     short loc_14005119B
0x140051189  mov     eax, dword ptr [rbp+47h+var_58]
0x14005118c  xor     eax, [r14+40h]
0x140051190  test    eax, 4800h
0x140051195  jz      loc_1400512BF
0x14005119b  mov     rax, [rbp+47h+arg_20]
0x14005119f  mov     [rsp+110h+var_D0], 1
0x1400511a4  test    rax, rax
0x1400511a7  jz      loc_1400512A2
0x1400511ad  mov     eax, [rax]
0x1400511af  test    al, 20h
0x1400511b1  jnz     loc_1400512A2
0x1400511b7  mov     dword ptr [rsi+1C0h], 0Dh
0x1400511c1  lea     rax, [rsp+110h+var_D0]
0x1400511c6  mov     [rsi+1C8h], rax
0x1400511cd  mov     dword ptr [rsi+1D8h], 1
0x1400511d7  mov     rax, [r13+78h]
0x1400511db  mov     rcx, [rax+20h]
0x1400511df  mov     rax, [rcx+30h]
0x1400511e3  mov     rcx, [rax+160h]
0x1400511ea  cmp     qword ptr [rcx+0D0h], 0
0x1400511f2  jz      short loc_14005123A
0x1400511f4  mov     eax, [rsi+80h]
0x1400511fa  test    al, 2
0x1400511fc  jnz     short loc_14005123A
0x1400511fe  xor     eax, eax
0x140051200  xorps   xmm0, xmm0
0x140051203  movups  xmmword ptr [rsi+0D0h], xmm0
0x14005120a  movups  xmmword ptr [rsi+0E0h], xmm0
0x140051211  mov     [rsi+0F0h], rax
0x140051218  mov     rax, [r13+78h]
0x14005121c  mov     rcx, [rax+20h]
0x140051220  mov     rax, [rcx+30h]
0x140051224  mov     rcx, [rax+160h]
0x14005122b  mov     rax, [rcx+0D0h]
0x140051232  mov     rcx, rsi
0x140051235  call    _guard_dispatch_icall
0x14005123a  mov     eax, [rbp+47h+var_B8]
0x14005123d  mov     [rsi+1D8h], eax
0x140051243  mov     dword ptr [rsi+1C0h], 0Ah
0x14005124d  mov     [rsi+1C8h], r12
0x140051254  mov     rcx, cs:WPP_GLOBAL_Control
0x14005125b  lea     r14, WPP_GLOBAL_Control
0x140051262  cmp     rcx, r14
0x140051265  jz      short loc_14005128B
0x140051267  mov     eax, [rcx+2Ch]
0x14005126a  test    al, 20h
0x14005126c  jz      short loc_14005128B
0x14005126e  mov     rcx, [rcx+18h]
0x140051272  lea     r8, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids
0x140051279  mov     edx, 16h
0x14005127e  mov     [rsp+110h+var_F0], r13
0x140051283  mov     r9, rsi
0x140051286  call    WPP_SF_qq
0x14005128b  xor     r9d, r9d
0x14005128e  xor     edx, edx
0x140051290  mov     rcx, r13
0x140051293  lea     r8d, [r9+8]
0x140051297  call    CscTransitionFcbOffline
0x14005129c  or      byte ptr [r15], 12h
  ... truncated ...
```
