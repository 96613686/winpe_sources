# RxSetRenameLinkClusterInfo

- ea: `0x140069a20`
- end: `0x14006a2a8`
- name: `RxSetRenameLinkClusterInfo`
- size: `2184`
- prototype: `__int64(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14006f9e0`

## callees

- `0x14000d7c0`
- `0x140014e40`
- `0x140016e20`
- `0x140017310`
- `0x14001f6d0`
- `0x140025d00`
- `0x140025d80`
- `0x140069a20`
- `0x14006a2b0`
- `0x14006ab80`
- `0x14006aef0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140069b87`
- `ntoskrnl!ExAllocatePool2` at `0x140069d3c`
- `ntoskrnl!ExAllocatePool2` at `0x140069e56`
- `ntoskrnl!ExAllocatePool2` at `0x140069b87`
- `ntoskrnl!ExAllocatePool2` at `0x140069d3c`
- `ntoskrnl!ExAllocatePool2` at `0x140069e56`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140069c5f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140069c5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069eb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a031`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a126`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a179`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069eb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a031`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a126`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a179`

## pseudocode

```c
__int64 RxSetRenameLinkClusterInfo(__int64 a1, __int64 a2, __int64 a3, ...)
{
  __int64 v4; // rsi
  __int64 v7; // r12
  _QWORD *v8; // r13
  __int64 v9; // r14
  int v10; // r8d
  int v11; // r15d
  __int64 v12; // rax
  __int64 v13; // r14
  UNICODE_STRING *p_String2; // r15
  unsigned int v15; // r14d
  __int64 v16; // rax
  void *Pool2; // rax
  unsigned __int16 Length; // si
  UNICODE_STRING v19; // xmm6
  __int64 v20; // r8
  unsigned __int16 v21; // dx
  unsigned __int16 v22; // cx
  unsigned __int16 v23; // r12
  unsigned __int16 v24; // bp
  unsigned __int16 v25; // si
  void *v26; // r13
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // cx
  __int64 v29; // rsi
  bool v30; // zf
  char v31; // al
  char v32; // bp
  int v33; // ecx
  UNICODE_STRING String2; // [rsp+30h] [rbp-68h] BYREF
  PVOID v36[2]; // [rsp+40h] [rbp-58h]
  int v37; // [rsp+A0h] [rbp+8h]
  _QWORD *P; // [rsp+A8h] [rbp+10h]
  __int64 v39; // [rsp+B8h] [rbp+20h] BYREF
  va_list va; // [rsp+B8h] [rbp+20h]
  _QWORD *v41; // [rsp+C0h] [rbp+28h]
  va_list va1; // [rsp+C8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v39 = va_arg(va1, _QWORD);
  v41 = va_arg(va1, _QWORD *);
  v4 = *(_QWORD *)(a2 + 184);
  v7 = *(_QWORD *)(a3 + 120);
  v8 = v41;
  v9 = *(_QWORD *)(a2 + 24);
  String2 = 0;
  *v41 = 0;
  LOBYTE(v39) = 0;
  *(_OWORD *)v36 = 0;
  *(_BYTE *)(a1 + 476) = *(_BYTE *)(v4 + 32);
  if ( *(_DWORD *)(v9 + 16) > 0xFFFEu )
  {
    v10 = 1632;
    v11 = -1073741562;
    v37 = 1632;
    goto LABEL_76;
  }
  v11 = RxpBuildTargetFcbTableNameForRename(a1, a2, &String2, (__int64 *)va);
  if ( v11 < 0 )
  {
    v10 = 1647;
    v37 = 1647;
    goto LABEL_76;
  }
  v12 = *(_QWORD *)(v4 + 24);
  if ( v12 )
  {
    v13 = *(_QWORD *)(v12 + 24);
    p_String2 = (UNICODE_STRING *)(v13 + 360);
    if ( (unsigned __int8)RxFcbClaimedByLogicalRdr(a3) )
      p_String2 = &String2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, &String2);
    }
    if ( *(_QWORD *)(v13 + 120) != v7 || *(_QWORD *)(a3 + 128) != *(_QWORD *)(v13 + 128) )
    {
      v10 = 1688;
      v11 = -1073741612;
      v37 = 1688;
      goto LABEL_76;
    }
    v15 = p_String2->Length + 20;
    P = (_QWORD *)ExAllocatePool2(258, v15, 1061124178);
    if ( !P )
    {
      v10 = 1704;
      v11 = -1073741670;
      v37 = 1704;
      goto LABEL_76;
    }
    v16 = *(_QWORD *)(a2 + 24);
    *(_OWORD *)P = *(_OWORD *)v16;
    P[2] = *(_QWORD *)(v16 + 16);
    P[1] = 0;
    *((_DWORD *)P + 4) = p_String2->Length;
    memmove((char *)P + 20, p_String2->Buffer, p_String2->Length);
    *(_QWORD *)(a1 + 456) = P;
  }
  else
  {
    *(_QWORD *)(v9 + 8) = 0;
    *(_QWORD *)(a1 + 456) = *(_QWORD *)(a2 + 24);
    v15 = *(_DWORD *)(v9 + 16) + 20;
    P = 0;
    *(_BYTE *)(a1 + 479) = 1;
  }
  *(_DWORD *)(a1 + 472) = v15;
  if ( *(_DWORD *)(v4 + 16) != 11 && RtlEqualUnicodeString((PCUNICODE_STRING)(a3 + 336), &String2, 0) )
  {
    v10 = 1768;
    v37 = 1768;
    v11 = 0;
    goto LABEL_74;
  }
  v10 = 0;
  *(_DWORD *)(a1 + 448) = *(_DWORD *)(v4 + 16);
  v37 = 0;
  if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 392LL) + 208LL) )
  {
    v11 = -1073741822;
    goto LABEL_74;
  }
  if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
  {
    v11 = -1073741536;
  }
  else
  {
    *(_OWORD *)(a1 + 208) = 0;
    *(_OWORD *)(a1 + 224) = 0;
    *(_QWORD *)(a1 + 240) = 0;
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 392LL) + 208LL))(a1);
    if ( v11 >= 0 && *(_DWORD *)(v4 + 16) == 10 )
    {
      if ( (_BYTE)v39 )
      {
        v19 = String2;
        Length = _mm_cvtsi128_si32((__m128i)String2);
        v36[1] = (PVOID)_mm_srli_si128((__m128i)String2, 8).m128i_u64[0];
      }
      else
      {
        Pool2 = (void *)ExAllocatePool2(258, String2.Length, 1061124178);
        v36[1] = Pool2;
        if ( !Pool2 )
        {
          v10 = 1840;
          v11 = -1073741670;
          v37 = 1840;
          goto LABEL_74;
        }
        Length = String2.Length;
        WORD1(v36[0]) = String2.Length;
        LOWORD(v36[0]) = String2.Length;
        memmove(Pool2, String2.Buffer, String2.Length);
        v19 = *(UNICODE_STRING *)v36;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, a3 + 360);
      }
      v20 = *(_QWORD *)(a3 + 128);
      if ( v20 )
      {
        v21 = **(_WORD **)(*(_QWORD *)(a3 + 120) + 88LL);
        v22 = *(_WORD *)(v20 + 64);
        v23 = **(_WORD **)(v20 + 56);
        v24 = v22 - v21;
        if ( v22 <= v21 )
          v24 = 0;
      }
      else
      {
        v23 = 0;
        v24 = 0;
      }
      v25 = *(_WORD *)(a3 + 280) + v24 + Length - v23;
      if ( *(_WORD *)(a3 + 360) < v25 )
      {
        v26 = (void *)ExAllocatePool2(258, v25, 1061124178);
        if ( !v26 )
        {
          v10 = 1895;
          v11 = -1073741670;
          v37 = 1895;
          goto LABEL_74;
        }
        if ( *(_WORD *)(a3 + 280) )
          memmove(v26, *(const void **)(a3 + 368), *(unsigned __int16 *)(a3 + 280));
        if ( (*(_DWORD *)(a3 + 156) & 0x8000) != 0 )
        {
          ExFreePoolWithTag(*(PVOID *)(a3 + 368), 0);
          *(_QWORD *)(a3 + 368) = 0;
        }
        *(_DWORD *)(a3 + 156) |= 0x8000u;
        *(_QWORD *)(a3 + 368) = v26;
        v8 = v41;
        *(_WORD *)(a3 + 362) = v25;
      }
      *(_WORD *)(a3 + 360) = v25;
      if ( v24 )
        memmove(
          (void *)(*(_QWORD *)(a3 + 368) + *(unsigned __int16 *)(a3 + 280)),
          (const void *)(*(_QWORD *)(*(_QWORD *)(a3 + 128) + 72LL)
                       + **(unsigned __int16 **)(*(_QWORD *)(a3 + 120) + 88LL)),
          v24);
      v27 = *(_WORD *)(a3 + 280) + v24;
      if ( v27 < v24 )
      {
        v11 = -1073741675;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
            3221225621LL);
        }
        v10 = 1945;
        v37 = 1945;
        goto LABEL_74;
      }
      v28 = *(_WORD *)(a3 + 360);
      if ( v28 < v27 )
      {
        v11 = -1073741675;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
            3221225621LL);
        }
        v10 = 1959;
        v37 = 1959;
        goto LABEL_74;
      }
      memmove((void *)(*(_QWORD *)(a3 + 368) + v27), (char *)v36[1] + v23, (unsigned __int16)(v28 - v27));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids, a3 + 360);
      }
      RxRemoveNameNetFcb((PFCB)a3);
      v29 = *(_QWORD *)(a3 + 288);
      v30 = (*(_BYTE *)(a3 + 355) & 2) == 0;
      v32 = v31;
      *(_QWORD *)(a3 + 288) = 0;
      if ( !v30 )
        ExFreePoolWithTag(*(PVOID *)(a3 + 344), 0);
      *(_BYTE *)(a3 + 355) |= 2u;
      v36[1] = 0;
      *(UNICODE_STRING *)(a3 + 336) = v19;
      if ( v32 )
        RxFcbTableInsertFcb((PRX_FCB_TABLE)(*(_QWORD *)(a3 + 120) + 296LL), (PFCB)a3);
      RxpFindOrCreateParentFcb((PVOID)a3);
      if ( v29 && *(_QWORD *)(a3 + 288) == v29 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v29 + 152));
        v29 = 0;
      }
      *v8 = v29;
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 392LL) + 184LL) )
      {
        v33 = -1073741822;
        goto LABEL_84;
      }
      if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
      {
        v33 = -1073741536;
      }
      else
      {
        *(_OWORD *)(a1 + 208) = 0;
        *(_OWORD *)(a1 + 224) = 0;
        *(_QWORD *)(a1 + 240) = 0;
        v33 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 392LL) + 184LL))(
                a3,
                *(_QWORD *)(a3 + 288));
        if ( v33 >= 0 )
        {
          v10 = 0;
          goto LABEL_74;
        }
      }
LABEL_84:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
          (unsigned int)v33);
      }
      v10 = 2039;
      v37 = 2039;
      goto LABEL_74;
    }
    v10 = 0;
  }
LABEL_74:
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    v10 = v37;
  }
LABEL_76:
  if ( v36[1] )
  {
    ExFreePoolWithTag(v36[1], 0);
    v10 = v37;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
      (unsigned int)v11,
      v10);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140069a20  mov     rax, rsp
0x140069a23  mov     [rax+20h], r9
0x140069a27  push    r15
0x140069a29  sub     rsp, 90h
0x140069a30  mov     [rax+18h], rbx
0x140069a34  xorps   xmm0, xmm0
0x140069a37  mov     [rax-10h], rbp
0x140069a3b  xorps   xmm1, xmm1
0x140069a3e  mov     [rax-18h], rsi
0x140069a42  mov     rbp, rdx
0x140069a45  mov     rsi, [rdx+0B8h]
0x140069a4c  mov     rbx, rcx
0x140069a4f  mov     [rax-20h], rdi
0x140069a53  mov     rdi, r8
0x140069a56  mov     [rax-28h], r12
0x140069a5a  mov     r12, [r8+78h]
0x140069a5e  mov     [rax-30h], r13
0x140069a62  mov     r13, [rsp+98h+arg_20]
0x140069a6a  mov     [rax-38h], r14
0x140069a6e  mov     r14, [rdx+18h]
0x140069a72  lea     rdx, WPP_GLOBAL_Control
0x140069a79  movups  xmmword ptr [rax-68h], xmm0
0x140069a7d  mov     qword ptr [r13+0], 0
0x140069a85  mov     byte ptr [rax+20h], 0
0x140069a89  movups  xmmword ptr [rax-58h], xmm1
0x140069a8d  movzx   eax, byte ptr [rsi+20h]
0x140069a91  mov     [rcx+1DCh], al
0x140069a97  cmp     dword ptr [r14+10h], 0FFFEh
0x140069a9f  jbe     short loc_140069ABA
0x140069aa1  mov     r8d, 660h
0x140069aa7  mov     r15d, 0C0000106h
0x140069aad  mov     [rsp+98h+arg_0], r8d
0x140069ab5  jmp     loc_14006A141
0x140069aba  lea     r9, [rsp+98h+arg_18]
0x140069ac2  mov     rdx, rbp
0x140069ac5  lea     r8, [rsp+98h+String2]
0x140069aca  call    RxpBuildTargetFcbTableNameForRename
0x140069acf  mov     r15d, eax
0x140069ad2  test    eax, eax
0x140069ad4  jns     short loc_140069AE9
0x140069ad6  mov     r8d, 66Fh
0x140069adc  mov     [rsp+98h+arg_0], r8d
0x140069ae4  jmp     loc_14006A13A
0x140069ae9  mov     rax, [rsi+18h]
0x140069aed  test    rax, rax
0x140069af0  jz      loc_140069C1A
0x140069af6  mov     r14, [rax+18h]
0x140069afa  mov     rcx, rdi
0x140069afd  call    RxFcbClaimedByLogicalRdr
0x140069b02  lea     r15, [r14+168h]
0x140069b09  test    al, al
0x140069b0b  jz      short loc_140069B12
0x140069b0d  lea     r15, [rsp+98h+String2]
0x140069b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140069b19  lea     rdx, WPP_GLOBAL_Control
0x140069b20  cmp     rcx, rdx
0x140069b23  jz      short loc_140069B53
0x140069b25  mov     eax, [rcx+2Ch]
0x140069b28  test    al, 20h
0x140069b2a  jz      short loc_140069B53
0x140069b2c  cmp     byte ptr [rcx+29h], 2
0x140069b30  jb      short loc_140069B53
0x140069b32  mov     rcx, [rcx+18h]
0x140069b36  lea     r9, [rsp+98h+String2]
0x140069b3b  mov     edx, 20h ; ' '
0x140069b40  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x140069b47  call    WPP_SF_Z
0x140069b4c  lea     rdx, WPP_GLOBAL_Control
0x140069b53  cmp     [r14+78h], r12
0x140069b57  jnz     loc_140069C01
0x140069b5d  mov     rax, [r14+80h]
0x140069b64  cmp     [rdi+80h], rax
0x140069b6b  jnz     loc_140069C01
0x140069b71  movzx   r14d, word ptr [r15]
0x140069b75  mov     ecx, 102h
0x140069b7a  add     r14d, 14h
0x140069b7e  mov     r8d, 3F3F7852h
0x140069b84  mov     edx, r14d
0x140069b87  call    cs:__imp_ExAllocatePool2
0x140069b8e  nop     dword ptr [rax+rax+00h]
0x140069b93  mov     [rsp+98h+P], rax
0x140069b9b  mov     r12, rax
0x140069b9e  test    rax, rax
0x140069ba1  jnz     short loc_140069BBC
0x140069ba3  mov     r8d, 6A8h
0x140069ba9  mov     r15d, 0C000009Ah
0x140069baf  mov     [rsp+98h+arg_0], r8d
0x140069bb7  jmp     loc_14006A13A
0x140069bbc  mov     rax, [rbp+18h]
0x140069bc0  lea     rcx, [r12+14h]; void *
0x140069bc5  movups  xmm0, xmmword ptr [rax]
0x140069bc8  movups  xmmword ptr [r12], xmm0
0x140069bcd  movsd   xmm1, qword ptr [rax+10h]
0x140069bd2  movsd   qword ptr [r12+10h], xmm1
0x140069bd9  mov     qword ptr [r12+8], 0
0x140069be2  movzx   eax, word ptr [r15]
0x140069be6  mov     [r12+10h], eax
0x140069beb  movzx   r8d, word ptr [r15]; Size
0x140069bef  mov     rdx, [r15+8]; Src
0x140069bf3  call    memmove
0x140069bf8  mov     [rbx+1C8h], r12
0x140069bff  jmp     short loc_140069C43
0x140069c01  mov     r8d, 698h
0x140069c07  mov     r15d, 0C00000D4h
0x140069c0d  mov     [rsp+98h+arg_0], r8d
0x140069c15  jmp     loc_14006A141
0x140069c1a  xor     r12d, r12d
0x140069c1d  mov     [r14+8], r12
0x140069c21  mov     rax, [rbp+18h]
0x140069c25  mov     [rbx+1C8h], rax
0x140069c2c  mov     r14d, [r14+10h]
0x140069c30  add     r14d, 14h
0x140069c34  mov     [rsp+98h+P], r12
0x140069c3c  mov     byte ptr [rbx+1DFh], 1
0x140069c43  mov     [rbx+1D8h], r14d
0x140069c4a  cmp     dword ptr [rsi+10h], 0Bh
0x140069c4e  jz      short loc_140069C8C
0x140069c50  lea     rcx, [rdi+150h]; String1
0x140069c57  xor     r8d, r8d; CaseInSensitive
0x140069c5a  lea     rdx, [rsp+98h+String2]; String2
0x140069c5f  call    cs:__imp_RtlEqualUnicodeString
0x140069c66  nop     dword ptr [rax+rax+00h]
0x140069c6b  test    al, al
0x140069c6d  jz      short loc_140069C8C
0x140069c6f  mov     r8d, 6E8h
0x140069c75  lea     rdx, WPP_GLOBAL_Control
0x140069c7c  mov     [rsp+98h+arg_0], r8d
0x140069c84  xor     r15d, r15d
0x140069c87  jmp     loc_14006A117
0x140069c8c  mov     eax, [rsi+10h]
0x140069c8f  xor     r8d, r8d
0x140069c92  mov     [rbx+1C0h], eax
0x140069c98  mov     rax, [rbx+38h]
0x140069c9c  mov     [rsp+98h+arg_0], r8d
0x140069ca4  mov     rcx, [rax+188h]
0x140069cab  cmp     [rcx+0D0h], r8
0x140069cb2  jnz     short loc_140069CC6
0x140069cb4  mov     r15d, 0C0000002h
0x140069cba  lea     rdx, WPP_GLOBAL_Control
0x140069cc1  jmp     loc_14006A117
0x140069cc6  mov     eax, [rbx+80h]
0x140069ccc  test    al, 2
0x140069cce  jnz     loc_14006A296
0x140069cd4  xor     eax, eax
0x140069cd6  xorps   xmm0, xmm0
0x140069cd9  movups  xmmword ptr [rbx+0D0h], xmm0
0x140069ce0  movups  xmmword ptr [rbx+0E0h], xmm0
0x140069ce7  mov     [rbx+0F0h], rax
0x140069cee  mov     rax, [rbx+38h]
0x140069cf2  mov     rcx, [rax+188h]
0x140069cf9  mov     rax, [rcx+0D0h]
0x140069d00  mov     rcx, rbx
0x140069d03  call    _guard_dispatch_icall
0x140069d08  mov     r15d, eax
0x140069d0b  test    eax, eax
0x140069d0d  js      loc_14006A282
0x140069d13  cmp     dword ptr [rsi+10h], 0Ah
0x140069d17  jnz     loc_14006A282
0x140069d1d  cmp     byte ptr [rsp+98h+arg_18], 0
0x140069d25  movaps  [rsp+98h+var_48], xmm6
0x140069d2a  jnz     short loc_140069D91
0x140069d2c  movzx   edx, [rsp+98h+String2.Length]
0x140069d31  mov     ecx, 102h
0x140069d36  mov     r8d, 3F3F7852h
0x140069d3c  call    cs:__imp_ExAllocatePool2
0x140069d43  nop     dword ptr [rax+rax+00h]
0x140069d48  mov     [rsp+98h+var_58+8], rax
0x140069d4d  test    rax, rax
0x140069d50  jnz     short loc_140069D6B
0x140069d52  mov     r8d, 730h
0x140069d58  mov     r15d, 0C000009Ah
0x140069d5e  mov     [rsp+98h+arg_0], r8d
0x140069d66  jmp     loc_14006A10B
0x140069d6b  movzx   esi, [rsp+98h+String2.Length]
0x140069d70  mov     rcx, rax; void *
0x140069d73  mov     rdx, [rsp+98h+String2.Buffer]; Src
0x140069d78  mov     r8d, esi; Size
0x140069d7b  mov     word ptr [rsp+98h+var_58+2], si
0x140069d80  mov     word ptr [rsp+98h+var_58], si
0x140069d85  call    memmove
0x140069d8a  movaps  xmm6, xmmword ptr [rsp+98h+var_58]
0x140069d8f  jmp     short loc_140069DA9
0x140069d91  movaps  xmm6, xmmword ptr [rsp+98h+String2.Length]
0x140069d96  movdqa  xmm0, xmm6
0x140069d9a  movd    esi, xmm6
0x140069d9e  psrldq  xmm0, 8
0x140069da3  movq    [rsp+98h+var_58+8], xmm0
0x140069da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140069db0  lea     rdx, WPP_GLOBAL_Control
0x140069db7  cmp     rcx, rdx
0x140069dba  jz      short loc_140069DEC
0x140069dbc  mov     eax, [rcx+2Ch]
0x140069dbf  test    al, 20h
0x140069dc1  jz      short loc_140069DEC
0x140069dc3  cmp     byte ptr [rcx+29h], 2
0x140069dc7  jb      short loc_140069DEC
0x140069dc9  mov     rcx, [rcx+18h]
0x140069dcd  lea     r9, [rdi+168h]
0x140069dd4  mov     edx, 21h ; '!'
0x140069dd9  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x140069de0  call    WPP_SF_Z
0x140069de5  lea     rdx, WPP_GLOBAL_Control
0x140069dec  mov     r8, [rdi+80h]
0x140069df3  test    r8, r8
0x140069df6  jz      short loc_140069E28
0x140069df8  mov     rax, [rdi+78h]
0x140069dfc  mov     rcx, [rax+58h]
0x140069e00  mov     rax, [r8+38h]
0x140069e04  movzx   edx, word ptr [rcx]
0x140069e07  movzx   ecx, word ptr [r8+40h]
0x140069e0c  movzx   r12d, word ptr [rax]
0x140069e10  movzx   ebp, cx
0x140069e13  sub     bp, dx
0x140069e16  xor     eax, eax
0x140069e18  cmp     cx, dx
0x140069e1b  lea     rdx, WPP_GLOBAL_Control
0x140069e22  cmovbe  bp, ax
0x140069e26  jmp     short loc_140069E2D
0x140069e28  xor     r12d, r12d
0x140069e2b  xor     ebp, ebp
0x140069e2d  sub     si, r12w
0x140069e31  add     si, bp
0x140069e34  add     si, [rdi+118h]
0x140069e3b  cmp     [rdi+168h], si
0x140069e42  jnb     loc_140069EF6
0x140069e48  movzx   edx, si
0x140069e4b  mov     ecx, 102h
0x140069e50  mov     r8d, 3F3F7852h
0x140069e56  call    cs:__imp_ExAllocatePool2
0x140069e5d  nop     dword ptr [rax+rax+00h]
0x140069e62  mov     r13, rax
0x140069e65  test    rax, rax
0x140069e68  jnz     short loc_140069E83
0x140069e6a  mov     r8d, 767h
0x140069e70  mov     r15d, 0C000009Ah
0x140069e76  mov     [rsp+98h+arg_0], r8d
0x140069e7e  jmp     loc_14006A10B
0x140069e83  movzx   ecx, word ptr [rdi+118h]
0x140069e8a  xor     eax, eax
0x140069e8c  cmp     ax, cx
0x140069e8f  jz      short loc_140069EA3
0x140069e91  mov     rdx, [rdi+170h]; Src
0x140069e98  mov     r8d, ecx; Size
0x140069e9b  mov     rcx, r13; void *
0x140069e9e  call    memmove
0x140069ea3  test    dword ptr [rdi+9Ch], 8000h
0x140069ead  jz      short loc_140069ECF
0x140069eaf  mov     rcx, [rdi+170h]; P
0x140069eb6  xor     edx, edx; Tag
0x140069eb8  call    cs:__imp_ExFreePoolWithTag
0x140069ebf  nop     dword ptr [rax+rax+00h]
0x140069ec4  mov     qword ptr [rdi+170h], 0
0x140069ecf  or      dword ptr [rdi+9Ch], 8000h
0x140069ed9  lea     rdx, WPP_GLOBAL_Control
0x140069ee0  mov     [rdi+170h], r13
0x140069ee7  mov     r13, [rsp+98h+arg_20]
0x140069eef  mov     [rdi+16Ah], si
0x140069ef6  xor     eax, eax
0x140069ef8  mov     [rdi+168h], si
0x140069eff  cmp     ax, bp
0x140069f02  jz      short loc_140069F38
0x140069f04  mov     rax, [rdi+78h]
0x140069f08  movzx   r8d, bp; Size
0x140069f0c  mov     rcx, [rax+58h]
0x140069f10  mov     rax, [rdi+80h]
0x140069f17  movzx   edx, word ptr [rcx]
0x140069f1a  movzx   ecx, word ptr [rdi+118h]
0x140069f21  add     rcx, [rdi+170h]; void *
0x140069f28  add     rdx, [rax+48h]; Src
0x140069f2c  call    memmove
0x140069f31  lea     rdx, WPP_GLOBAL_Control
0x140069f38  movzx   eax, bp
0x140069f3b  add     ax, [rdi+118h]
0x140069f42  cmp     ax, bp
0x140069f45  jnb     short loc_140069F98
0x140069f47  mov     r15d, 0C0000095h
0x140069f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140069f54  cmp     rcx, rdx
0x140069f57  jz      short loc_140069F85
0x140069f59  mov     eax, [rcx+2Ch]
0x140069f5c  test    al, 1
0x140069f5e  jz      short loc_140069F85
0x140069f60  cmp     byte ptr [rcx+29h], 1
0x140069f64  jb      short loc_140069F85
0x140069f66  mov     rcx, [rcx+18h]
0x140069f6a  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x140069f71  mov     edx, 22h ; '"'
0x140069f76  mov     r9d, r15d
0x140069f79  call    WPP_SF_d
0x140069f7e  lea     rdx, WPP_GLOBAL_Control
0x140069f85  mov     r8d, 799h
0x140069f8b  mov     [rsp+98h+arg_0], r8d
0x140069f93  jmp     loc_14006A112
0x140069f98  movzx   ecx, word ptr [rdi+168h]
0x140069f9f  cmp     cx, ax
0x140069fa2  jb      loc_14006A231
0x140069fa8  sub     cx, ax
0x140069fab  movzx   edx, r12w
0x140069faf  add     rdx, [rsp+98h+var_58+8]; Src
0x140069fb4  movzx   r8d, cx; Size
  ... truncated ...
```
