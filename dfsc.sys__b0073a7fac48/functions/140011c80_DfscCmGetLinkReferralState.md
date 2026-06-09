# DfscCmGetLinkReferralState

- ea: `0x140011c80`
- end: `0x140011f3d`
- name: `DfscCmGetLinkReferralState`
- size: `701`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400015c0`
- `0x14001d9b0`

## callees

- `0x14000136c`
- `0x140002340`
- `0x140006380`
- `0x1400118b4`
- `0x1400119cc`
- `0x140011c80`
- `0x14001f040`
- `0x140020d10`
- `0x140021820`
- `0x140021c10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140011e40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f13`

## pseudocode

```c
__int64 __fastcall DfscCmGetLinkReferralState(__int64 a1)
{
  unsigned int v1; // r14d
  _OWORD *v2; // rdi
  _OWORD *v4; // rdx
  _OWORD *v5; // rax
  __int64 v6; // r15
  __int64 v7; // rcx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  unsigned int LinkReferral; // esi
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 CurrentTarget; // rax
  void *v19; // rcx
  __int64 v20; // r9
  void *v21; // rcx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  PVOID v30; // rcx
  _BYTE v32[96]; // [rsp+30h] [rbp-158h] BYREF
  PVOID P; // [rsp+90h] [rbp-F8h]
  UNICODE_STRING v34; // [rsp+F8h] [rbp-90h] BYREF

  v1 = 9;
  v2 = (_OWORD *)(a1 + 8);
  v4 = v32;
  v5 = (_OWORD *)(a1 + 8);
  v6 = 2;
  v7 = 2;
  do
  {
    v8 = v5[1];
    *v4 = *v5;
    v9 = v5[2];
    v4[1] = v8;
    v10 = v5[3];
    v4[2] = v9;
    v11 = v5[4];
    v4[3] = v10;
    v12 = v5[5];
    v4[4] = v11;
    v13 = v5[6];
    v4[5] = v12;
    v14 = v5[7];
    v5 += 8;
    v4[6] = v13;
    v4[7] = v14;
    v4 += 8;
    --v7;
  }
  while ( v7 );
  *(_QWORD *)v4 = *(_QWORD *)v5;
  memset((void *)(a1 + 16), 0, 0x60u);
  memset((void *)(a1 + 112), 0, 0x60u);
  *(_OWORD *)(a1 + 208) = 0;
  *(_WORD *)(a1 + 226) = 0;
  LinkReferral = DfscRewritePath(a1, (unsigned __int16 *)(*(_QWORD *)(a1 + 280) + 96LL), &v34, 1);
  if ( LinkReferral )
  {
LABEL_22:
    if ( P )
      ExFreePoolWithTag(P, 0);
    goto LABEL_24;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 292) - 2) <= 2 )
  {
    LinkReferral = -1073741634;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_05cba1b763293f8d98259e004f8588c9_Traceguids,
        a1,
        -1073741634);
    }
    goto LABEL_22;
  }
  v16 = *(_QWORD *)(a1 + 272);
  *(_QWORD *)(a1 + 272) = 0;
  LinkReferral = DfscGetLinkReferral((__int64)v2, (const UNICODE_STRING *)(a1 + 112), 0, (_QWORD *)(a1 + 272));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1, LinkReferral);
  if ( !LinkReferral )
  {
    DfscReferralSetCurrentAccessStatus(v16, 0);
    DfscReferralGetPrimaryTarget(v17);
    CurrentTarget = DfscReferralGetCurrentTarget(v16);
    if ( CurrentTarget != v20 )
      *(_WORD *)(*(_QWORD *)(v16 + 16) + 26LL) = *(_WORD *)(v16 + 32);
    DfscReferralRelease(v19);
    v1 = 5;
    goto LABEL_22;
  }
  if ( !(unsigned __int8)DfscIsErrorInList(LinkReferral, DfscFailoverErrorList, 30) )
  {
    DfscReferralSetCurrentAccessStatus(v16, 0);
    DfscReferralRelease(v30);
    goto LABEL_22;
  }
  DfscReferralSetCurrentAccessStatus(v16, LinkReferral);
  v21 = *(void **)(a1 + 104);
  if ( v21 )
    ExFreePoolWithTag(v21, 0);
  v22 = v32;
  do
  {
    v23 = v22[1];
    *v2 = *v22;
    v24 = v22[2];
    v2[1] = v23;
    v25 = v22[3];
    v2[2] = v24;
    v26 = v22[4];
    v2[3] = v25;
    v27 = v22[5];
    v2[4] = v26;
    v28 = v22[6];
    v2[5] = v27;
    v29 = v22[7];
    v22 += 8;
    v2[6] = v28;
    v2[7] = v29;
    v2 += 8;
    --v6;
  }
  while ( v6 );
  v1 = 5;
  *(_QWORD *)v2 = *(_QWORD *)v22;
  LinkReferral = -1073741634;
  *(_QWORD *)(a1 + 272) = v16;
LABEL_24:
  *(_DWORD *)(a1 + 316) = LinkReferral;
  return v1;
}

```

## disassembly

```asm
0x140011c80  push    rbx
0x140011c82  push    rbp
0x140011c83  push    rsi
0x140011c84  push    rdi
0x140011c85  push    r12
0x140011c87  push    r13
0x140011c89  push    r14
0x140011c8b  push    r15
0x140011c8d  sub     rsp, 148h
0x140011c94  mov     r14d, 9
0x140011c9a  lea     rdi, [rcx+8]
0x140011c9e  mov     rbp, rcx
0x140011ca1  lea     rdx, [rsp+188h+var_158]
0x140011ca6  mov     rax, rdi
0x140011ca9  lea     r15d, [r14-7]
0x140011cad  mov     ecx, r15d
0x140011cb0  lea     r8d, [r14+77h]
0x140011cb4  movups  xmm0, xmmword ptr [rax]
0x140011cb7  movups  xmm1, xmmword ptr [rax+10h]
0x140011cbb  movups  xmmword ptr [rdx], xmm0
0x140011cbe  movups  xmm0, xmmword ptr [rax+20h]
0x140011cc2  movups  xmmword ptr [rdx+10h], xmm1
0x140011cc6  movups  xmm1, xmmword ptr [rax+30h]
0x140011cca  movups  xmmword ptr [rdx+20h], xmm0
0x140011cce  movups  xmm0, xmmword ptr [rax+40h]
0x140011cd2  movups  xmmword ptr [rdx+30h], xmm1
0x140011cd6  movups  xmm1, xmmword ptr [rax+50h]
0x140011cda  movups  xmmword ptr [rdx+40h], xmm0
0x140011cde  movups  xmm0, xmmword ptr [rax+60h]
0x140011ce2  movups  xmmword ptr [rdx+50h], xmm1
0x140011ce6  movups  xmm1, xmmword ptr [rax+70h]
0x140011cea  add     rax, r8
0x140011ced  movups  xmmword ptr [rdx+60h], xmm0
0x140011cf1  movups  xmmword ptr [rdx+70h], xmm1
0x140011cf5  add     rdx, r8
0x140011cf8  sub     rcx, 1
0x140011cfc  jnz     short loc_140011CB4
0x140011cfe  mov     rax, [rax]
0x140011d01  lea     rcx, [rbp+10h]; void *
0x140011d05  mov     [rdx], rax
0x140011d08  mov     ebx, 60h ; '`'
0x140011d0d  xor     edx, edx; Val
0x140011d0f  mov     r8d, ebx; Size
0x140011d12  call    memset
0x140011d17  mov     r8d, ebx; Size
0x140011d1a  lea     rcx, [rbp+70h]; void *
0x140011d1e  xor     edx, edx; Val
0x140011d20  call    memset
0x140011d25  xorps   xmm0, xmm0
0x140011d28  lea     r8, [rsp+188h+var_90]
0x140011d30  movups  xmmword ptr [rbp+0D0h], xmm0
0x140011d37  xor     eax, eax
0x140011d39  mov     r9b, 1
0x140011d3c  mov     [rbp+0E2h], ax
0x140011d43  mov     rcx, rbp
0x140011d46  mov     rdx, [rbp+118h]
0x140011d4d  add     rdx, rbx
0x140011d50  call    DfscRewritePath
0x140011d55  mov     esi, eax
0x140011d57  test    eax, eax
0x140011d59  jnz     loc_140011F04
0x140011d5f  mov     eax, [rbp+124h]
0x140011d65  sub     eax, r15d
0x140011d68  cmp     eax, r15d
0x140011d6b  jbe     loc_140011EC3
0x140011d71  lea     r12, [rbp+110h]
0x140011d78  xor     r8d, r8d
0x140011d7b  mov     rbx, [r12]
0x140011d7f  lea     rdx, [rbp+70h]
0x140011d83  mov     r9, r12
0x140011d86  mov     qword ptr [r12], 0
0x140011d8e  mov     rcx, rdi
0x140011d91  call    DfscGetLinkReferral
0x140011d96  mov     esi, eax
0x140011d98  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d9f  lea     rax, WPP_GLOBAL_Control
0x140011da6  cmp     rcx, rax
0x140011da9  jz      short loc_140011DD0
0x140011dab  test    dword ptr [rcx+2Ch], 400000h
0x140011db2  jz      short loc_140011DD0
0x140011db4  mov     rcx, [rcx+18h]
0x140011db8  lea     r8, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids
0x140011dbf  mov     edx, 25h ; '%'
0x140011dc4  mov     [rsp+188h+var_168], esi
0x140011dc8  mov     r9, rbp
0x140011dcb  call    WPP_SF_qD
0x140011dd0  test    esi, esi
0x140011dd2  jnz     short loc_140011E0F
0x140011dd4  xor     edx, edx
0x140011dd6  mov     rcx, rbx
0x140011dd9  call    DfscReferralSetCurrentAccessStatus
0x140011dde  call    DfscReferralGetPrimaryTarget
0x140011de3  mov     rcx, rbx
0x140011de6  mov     r9, rax
0x140011de9  call    DfscReferralGetCurrentTarget
0x140011dee  cmp     rax, r9
0x140011df1  jz      short loc_140011DFF
0x140011df3  mov     rdx, [rbx+10h]
0x140011df7  movzx   eax, word ptr [rbx+20h]
0x140011dfb  mov     [rdx+1Ah], ax
0x140011dff  call    DfscReferralRelease
0x140011e04  mov     r14d, 5
0x140011e0a  jmp     loc_140011F04
0x140011e0f  mov     r8d, 1Eh
0x140011e15  lea     rdx, DfscFailoverErrorList
0x140011e1c  mov     ecx, esi
0x140011e1e  call    DfscIsErrorInList
0x140011e23  mov     rcx, rbx
0x140011e26  test    al, al
0x140011e28  jz      loc_140011EB5
0x140011e2e  mov     edx, esi
0x140011e30  call    DfscReferralSetCurrentAccessStatus
0x140011e35  mov     rcx, [rbp+68h]; P
0x140011e39  test    rcx, rcx
0x140011e3c  jz      short loc_140011E4C
0x140011e3e  xor     edx, edx; Tag
0x140011e40  call    cs:__imp_ExFreePoolWithTag
0x140011e47  nop     dword ptr [rax+rax+00h]
0x140011e4c  lea     rax, [rsp+188h+var_158]
0x140011e51  mov     ecx, 80h
0x140011e56  movups  xmm0, xmmword ptr [rax]
0x140011e59  movups  xmm1, xmmword ptr [rax+10h]
0x140011e5d  movups  xmmword ptr [rdi], xmm0
0x140011e60  movups  xmm0, xmmword ptr [rax+20h]
0x140011e64  movups  xmmword ptr [rdi+10h], xmm1
0x140011e68  movups  xmm1, xmmword ptr [rax+30h]
0x140011e6c  movups  xmmword ptr [rdi+20h], xmm0
0x140011e70  movups  xmm0, xmmword ptr [rax+40h]
0x140011e74  movups  xmmword ptr [rdi+30h], xmm1
0x140011e78  movups  xmm1, xmmword ptr [rax+50h]
0x140011e7c  movups  xmmword ptr [rdi+40h], xmm0
0x140011e80  movups  xmm0, xmmword ptr [rax+60h]
0x140011e84  movups  xmmword ptr [rdi+50h], xmm1
0x140011e88  movups  xmm1, xmmword ptr [rax+70h]
0x140011e8c  add     rax, rcx
0x140011e8f  movups  xmmword ptr [rdi+60h], xmm0
0x140011e93  movups  xmmword ptr [rdi+70h], xmm1
0x140011e97  add     rdi, rcx
0x140011e9a  sub     r15, 1
0x140011e9e  jnz     short loc_140011E56
0x140011ea0  mov     rax, [rax]
0x140011ea3  lea     r14d, [r15+5]
0x140011ea7  mov     [rdi], rax
0x140011eaa  mov     esi, 0C00000BEh
0x140011eaf  mov     [r12], rbx
0x140011eb3  jmp     short loc_140011F1F
0x140011eb5  xor     edx, edx
0x140011eb7  call    DfscReferralSetCurrentAccessStatus
0x140011ebc  call    DfscReferralRelease
0x140011ec1  jmp     short loc_140011F04
0x140011ec3  mov     esi, 0C00000BEh
0x140011ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ecf  lea     rax, WPP_GLOBAL_Control
0x140011ed6  cmp     rcx, rax
0x140011ed9  jz      short loc_140011F04
0x140011edb  test    dword ptr [rcx+2Ch], 100000h
0x140011ee2  jz      short loc_140011F04
0x140011ee4  mov     rcx, [rcx+18h]
0x140011ee8  lea     r8, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids
0x140011eef  mov     edx, 24h ; '$'
0x140011ef4  mov     [rsp+188h+var_168], 0C00000BEh
0x140011efc  mov     r9, rbp
0x140011eff  call    WPP_SF_qD
0x140011f04  mov     rcx, [rsp+188h+P]; P
0x140011f0c  test    rcx, rcx
0x140011f0f  jz      short loc_140011F1F
0x140011f11  xor     edx, edx; Tag
0x140011f13  call    cs:__imp_ExFreePoolWithTag
0x140011f1a  nop     dword ptr [rax+rax+00h]
0x140011f1f  mov     [rbp+13Ch], esi
0x140011f25  mov     eax, r14d
0x140011f28  add     rsp, 148h
0x140011f2f  pop     r15
0x140011f31  pop     r14
0x140011f33  pop     r13
0x140011f35  pop     r12
0x140011f37  pop     rdi
0x140011f38  pop     rsi
0x140011f39  pop     rbp
0x140011f3a  pop     rbx
0x140011f3b  retn
```
