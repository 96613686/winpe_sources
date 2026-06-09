# DfscGetUseInfo2

- ea: `0x140003a94`
- end: `0x140003eb8`
- name: `DfscGetUseInfo2`
- size: `1060`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140004314`

## callees

- `0x1400028f4`
- `0x140003a94`
- `0x1400040c8`
- `0x140004944`
- `0x1400141fc`
- `0x14001f8a0`
- `0x140025aa0`
- `0x140026ed0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003c31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003c31`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003c25`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003c25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003b3a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003b3a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003b12`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003b12`

## string_xrefs

- `0x140003e13`: `CompressionInfo`

## pseudocode

```c
__int64 __fastcall DfscGetUseInfo2(__int64 a1, int a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  unsigned int *v5; // r15
  struct _ERESOURCE *p_WaitListHead; // r13
  __int64 v7; // rsi
  int v8; // r12d
  __int64 v10; // r10
  bool v11; // cf
  int SearchKey; // edi
  struct _ERESOURCE *v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // r8d
  unsigned int v17; // r12d
  int v19; // ecx
  unsigned int v20; // r8d
  unsigned __int16 v21; // r9
  int v22; // r8d
  unsigned int v23; // r8d
  __int64 v24; // r9
  _WORD *v25; // rcx
  unsigned __int16 v26; // r9
  unsigned int v27; // eax
  int v28; // ecx
  int v29; // ecx
  unsigned int v30; // edx
  __int64 v31; // rdx
  unsigned int *v32; // rax
  __int64 Ea; // rax
  __int64 v34; // rdx
  __int64 v35; // rax
  _OWORD v36[3]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v38; // [rsp+C8h] [rbp+58h] BYREF

  v5 = a5;
  p_WaitListHead = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  v38 = 0;
  v7 = 0;
  v8 = 0;
  v10 = a3;
  v11 = *a5 < 0x30;
  memset(v36, 0, sizeof(v36));
  if ( !v11 )
  {
    SearchKey = DfscNetUseGetSearchKey(a1, a3, a2, (unsigned int)&v38, (__int64)v36);
    if ( SearchKey )
    {
LABEL_12:
      v10 = a3;
      goto LABEL_13;
    }
    KeEnterCriticalRegion();
    v14 = (struct _ERESOURCE *)(a1 + 152);
    if ( !a1 )
      v14 = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v8 = 1;
    ExAcquireResourceExclusiveLite(v14, 1u);
    v15 = DfscNetUseTableLookup(v38, v36, 0, 0);
    v7 = v15;
    if ( !v15 )
    {
      SearchKey = -1073741772;
      goto LABEL_12;
    }
    v16 = *v5;
    LODWORD(v38) = 44;
    *(_OWORD *)a4 = 0;
    *(_OWORD *)(a4 + 16) = 0;
    *(_OWORD *)(a4 + 32) = 0;
    SearchKey = DfscPackString((_WORD *)(v15 + 104), a4, v16, 4u, (unsigned int *)&v38, (unsigned __int16 *)(a4 + 16));
    if ( SearchKey >= 0 )
    {
      *(_DWORD *)(a4 + 32) = *(_DWORD *)(a4 + 28) + *(unsigned __int16 *)(a4 + 16);
      v17 = *(unsigned __int16 *)(v7 + 88) + 4;
      if ( v17 > 0xFFFF
        || (v19 = v38, v17 + (unsigned int)v38 < (unsigned int)v38)
        || (v20 = *v5, v17 + (unsigned int)v38 > *v5) )
      {
        SearchKey = -2147483643;
      }
      else
      {
        *(_WORD *)((unsigned int)v38 + a4) = 92;
        v21 = *(_WORD *)(v7 + 88);
        LODWORD(v38) = v19 + 2;
        SearchKey = DfscPackString(*(_WORD **)(v7 + 96), a4, v20, v21, (unsigned int *)&v38, (unsigned __int16 *)&a5);
        if ( SearchKey >= 0 )
        {
          v22 = v38;
          *(_WORD *)((unsigned int)v38 + a4) = 0;
          v23 = v22 + 2;
          *(_WORD *)(a4 + 18) = v17;
          *(_DWORD *)(a4 + 36) = *(_DWORD *)(a4 + 32) + (unsigned __int16)v17;
          v24 = *(_QWORD *)(v7 + 112);
          LODWORD(v38) = v23;
          if ( !v24 )
            goto LABEL_31;
          v25 = *(_WORD **)(v24 + 64);
          v26 = *(_WORD *)(v24 + 56);
          if ( *v25 == 92 )
          {
            ++v25;
            v26 -= 2;
          }
          SearchKey = DfscPackString(v25, a4, *v5, v26, (unsigned int *)&v38, (unsigned __int16 *)(a4 + 20));
          if ( SearchKey >= 0 )
          {
            v23 = v38;
LABEL_31:
            v8 = 1;
            *(_DWORD *)(a4 + 24) = *(_DWORD *)(v7 + 144);
            v27 = *(_DWORD *)(a4 + 12) & 0xFFFFFFFE;
            v28 = (*(_DWORD *)(v7 + 148) >> 1) & 1;
            *v5 = v23;
            v29 = v27 | v28;
            *(_DWORD *)(a4 + 12) = v29;
            v30 = v29 & 0xFFFFFFFD | (*(_DWORD *)(v7 + 148) >> 1) & 2;
            *(_DWORD *)(a4 + 12) = v30;
            *(_WORD *)(a4 + 4) = *(_WORD *)(v7 + 152);
            v31 = v30 & 0xFFFFFFFB;
            *(_DWORD *)(a4 + 12) = v31 | (*(_BYTE *)(v7 + 156) != 0 ? 4 : 0);
            *(_DWORD *)a4 = *(_DWORD *)(v7 + 164);
            *(_WORD *)(a4 + 6) = *(_WORD *)(v7 + 158);
            *(_WORD *)(a4 + 8) = *(_WORD *)(v7 + 160);
            *(_WORD *)(a4 + 10) = *(_WORD *)(v7 + 162);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_ZZD(
                WPP_GLOBAL_Control->AttachedDevice,
                25,
                v23,
                *(_QWORD *)(v7 + 112) != 0 ? *(_QWORD *)(v7 + 112) + 56 : 0,
                a3,
                v23);
            }
            v32 = *(unsigned int **)(v7 + 168);
            if ( v32 )
            {
              Ea = DfscFindEa((char *)v32 + *v32, v31, "CompressionInfo", 15);
              if ( Ea && *(_WORD *)(Ea + 6) == 8 )
                *(_DWORD *)(a4 + 12) = *(_DWORD *)(a4 + 12) & 0xFFFFFFF7
                                     | (*(_BYTE *)(*(unsigned __int8 *)(Ea + 5) + Ea + 9) != 0 ? 8 : 0);
              v35 = DfscFindEa(*(_QWORD *)(v7 + 168) + **(unsigned int **)(v7 + 168), v34, "BlockNTLMInfo", 13);
              if ( v35 && *(_WORD *)(v35 + 6) == 8 )
                *(_DWORD *)(a4 + 12) = *(_DWORD *)(a4 + 12) & 0xFFFFFFEF
                                     | (*(_BYTE *)(*(unsigned __int8 *)(v35 + 5) + v35 + 9) != 0 ? 0x10 : 0);
              *(_DWORD *)(a4 + 12) = *(_DWORD *)(a4 + 12) & 0xFFFFFFDF
                                   | (8 * (*(_DWORD *)(*(_QWORD *)(v7 + 168) + 12LL) & 4));
            }
            else
            {
              SearchKey = 0;
            }
            goto LABEL_12;
          }
        }
      }
    }
    v8 = 1;
    goto LABEL_12;
  }
  SearchKey = -2147483643;
LABEL_13:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    WPP_SF_DZ(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      (unsigned int)WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
      SearchKey,
      v10);
  if ( v8 )
  {
    if ( a1 )
      p_WaitListHead = (struct _ERESOURCE *)(a1 + 152);
    ExReleaseResourceLite(p_WaitListHead);
    KeLeaveCriticalRegion();
  }
  if ( v7 )
    DfscNetUseRelease(a1, v7, 0, 0);
  return (unsigned int)SearchKey;
}

```

## disassembly

```asm
0x140003a94  mov     [rsp-38h+arg_0], rbx
0x140003a99  mov     [rsp-38h+arg_10], r8
0x140003a9e  push    rbp
0x140003a9f  push    rsi
0x140003aa0  push    rdi
0x140003aa1  push    r12
0x140003aa3  push    r13
0x140003aa5  push    r14
0x140003aa7  push    r15
0x140003aa9  mov     rbp, rsp
0x140003aac  sub     rsp, 70h
0x140003ab0  mov     r15, [rbp+arg_20]
0x140003ab4  lea     r13, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140003abb  xorps   xmm0, xmm0
0x140003abe  mov     [rbp+arg_18], 0
0x140003ac6  xor     esi, esi
0x140003ac8  xor     r12d, r12d
0x140003acb  mov     rbx, r9
0x140003ace  mov     r10, r8
0x140003ad1  cmp     dword ptr [r15], 30h ; '0'
0x140003ad5  mov     r14, rcx
0x140003ad8  movups  [rbp+var_38], xmm0
0x140003adc  movups  [rbp+var_28], xmm0
0x140003ae0  movups  [rbp+var_18], xmm0
0x140003ae4  jnb     short loc_140003AF0
0x140003ae6  mov     edi, 80000005h
0x140003aeb  jmp     loc_140003BD8
0x140003af0  lea     rax, [rbp+var_38]
0x140003af4  mov     r8, rdx
0x140003af7  mov     rdx, r10
0x140003afa  mov     [rsp+70h+var_50], rax
0x140003aff  lea     r9, [rbp+arg_18]
0x140003b03  call    DfscNetUseGetSearchKey
0x140003b08  mov     edi, eax
0x140003b0a  test    eax, eax
0x140003b0c  jnz     loc_140003BD4
0x140003b12  call    cs:__imp_KeEnterCriticalRegion
0x140003b19  nop     dword ptr [rax+rax+00h]
0x140003b1e  lea     rcx, [r14+98h]
0x140003b25  test    r14, r14
0x140003b28  jnz     short loc_140003B2D
0x140003b2a  mov     rcx, r13; Resource
0x140003b2d  mov     r12d, 1
0x140003b33  mov     dl, r12b; Wait
0x140003b36  mov     [rbp+var_40], r12d
0x140003b3a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140003b41  nop     dword ptr [rax+rax+00h]
0x140003b46  mov     rcx, [rbp+arg_18]
0x140003b4a  lea     rdx, [rbp+var_38]
0x140003b4e  xor     r9d, r9d
0x140003b51  xor     r8d, r8d
0x140003b54  call    DfscNetUseTableLookup
0x140003b59  mov     rsi, rax
0x140003b5c  test    rax, rax
0x140003b5f  jnz     short loc_140003B68
0x140003b61  mov     edi, 0C0000034h
0x140003b66  jmp     short loc_140003BD4
0x140003b68  mov     r8d, [r15]
0x140003b6b  lea     rcx, [rax+68h]; Src
0x140003b6f  xorps   xmm0, xmm0
0x140003b72  mov     dword ptr [rbp+arg_18], 2Ch ; ','
0x140003b79  movups  xmmword ptr [rbx], xmm0
0x140003b7c  lea     rax, [rbp+arg_18]
0x140003b80  mov     r9d, 4
0x140003b86  movups  xmmword ptr [rbx+10h], xmm0
0x140003b8a  lea     r12, [rbx+10h]
0x140003b8e  mov     rdx, rbx
0x140003b91  mov     [rsp+70h+var_48], r12; __int64
0x140003b96  movups  xmmword ptr [rbx+20h], xmm0
0x140003b9a  mov     [rsp+70h+var_50], rax; __int64
0x140003b9f  call    DfscPackString
0x140003ba4  mov     edi, eax
0x140003ba6  test    eax, eax
0x140003ba8  js      short loc_140003BD0
0x140003baa  movzx   eax, word ptr [r12]
0x140003baf  add     eax, [rbx+1Ch]
0x140003bb2  mov     [rbx+20h], eax
0x140003bb5  movzx   r12d, word ptr [rsi+58h]
0x140003bba  add     r12d, 4
0x140003bbe  cmp     r12d, 0FFFFh
0x140003bc5  jbe     loc_140003C6E
0x140003bcb  mov     edi, 80000005h
0x140003bd0  mov     r12d, [rbp+var_40]
0x140003bd4  mov     r10, [rbp+arg_10]
0x140003bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bdf  lea     rax, WPP_GLOBAL_Control
0x140003be6  cmp     rcx, rax
0x140003be9  jz      short loc_140003C11
0x140003beb  test    dword ptr [rcx+2Ch], 100000h
0x140003bf2  jz      short loc_140003C11
0x140003bf4  mov     rcx, [rcx+18h]
0x140003bf8  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x140003bff  mov     edx, 1Ah
0x140003c04  mov     [rsp+70h+var_50], r10
0x140003c09  mov     r9d, edi
0x140003c0c  call    WPP_SF_DZ
0x140003c11  test    r12d, r12d
0x140003c14  jz      short loc_140003C3D
0x140003c16  test    r14, r14
0x140003c19  jz      short loc_140003C22
0x140003c1b  lea     r13, [r14+98h]
0x140003c22  mov     rcx, r13; Resource
0x140003c25  call    cs:__imp_ExReleaseResourceLite
0x140003c2c  nop     dword ptr [rax+rax+00h]
0x140003c31  call    cs:__imp_KeLeaveCriticalRegion
0x140003c38  nop     dword ptr [rax+rax+00h]
0x140003c3d  test    rsi, rsi
0x140003c40  jz      short loc_140003C53
0x140003c42  xor     r9d, r9d
0x140003c45  xor     r8d, r8d
0x140003c48  mov     rdx, rsi
0x140003c4b  mov     rcx, r14
0x140003c4e  call    DfscNetUseRelease
0x140003c53  mov     rbx, [rsp+70h+arg_0]
0x140003c5b  mov     eax, edi
0x140003c5d  add     rsp, 70h
0x140003c61  pop     r15
0x140003c63  pop     r14
0x140003c65  pop     r13
0x140003c67  pop     r12
0x140003c69  pop     rdi
0x140003c6a  pop     rsi
0x140003c6b  pop     rbp
0x140003c6c  retn
0x140003c6e  mov     ecx, dword ptr [rbp+arg_18]
0x140003c71  lea     eax, [r12+rcx]
0x140003c75  cmp     eax, ecx
0x140003c77  jb      loc_140003BCB
0x140003c7d  mov     r8d, [r15]
0x140003c80  cmp     eax, r8d
0x140003c83  ja      loc_140003BCB
0x140003c89  mov     word ptr [rcx+rbx], 5Ch ; '\'
0x140003c8f  lea     rax, [rbp+arg_20]
0x140003c93  movzx   r9d, word ptr [rsi+58h]
0x140003c98  add     ecx, 2
0x140003c9b  mov     [rsp+70h+var_48], rax; __int64
0x140003ca0  mov     rdx, rbx
0x140003ca3  mov     dword ptr [rbp+arg_18], ecx
0x140003ca6  lea     rax, [rbp+arg_18]
0x140003caa  mov     rcx, [rsi+60h]; Src
0x140003cae  mov     [rsp+70h+var_50], rax; __int64
0x140003cb3  call    DfscPackString
0x140003cb8  mov     edi, eax
0x140003cba  test    eax, eax
0x140003cbc  js      loc_140003BD0
0x140003cc2  mov     r8d, dword ptr [rbp+arg_18]
0x140003cc6  xor     eax, eax
0x140003cc8  mov     [r8+rbx], ax
0x140003ccd  lea     edx, [rax+2]
0x140003cd0  movzx   eax, r12w
0x140003cd4  add     r8d, edx
0x140003cd7  mov     [rbx+12h], ax
0x140003cdb  add     eax, [rbx+20h]
0x140003cde  mov     [rbx+24h], eax
0x140003ce1  mov     r9, [rsi+70h]
0x140003ce5  mov     dword ptr [rbp+arg_18], r8d
0x140003ce9  test    r9, r9
0x140003cec  jz      short loc_140003D33
0x140003cee  mov     rcx, [r9+40h]
0x140003cf2  lea     r10d, [rdx+5Ah]
0x140003cf6  mov     r8d, [r15]
0x140003cf9  lea     rax, [rbx+14h]
0x140003cfd  movzx   r9d, word ptr [r9+38h]
0x140003d02  cmp     [rcx], r10w
0x140003d06  jnz     short loc_140003D0F
0x140003d08  add     rcx, rdx; Src
0x140003d0b  sub     r9w, dx
0x140003d0f  mov     [rsp+70h+var_48], rax; __int64
0x140003d14  mov     rdx, rbx
0x140003d17  lea     rax, [rbp+arg_18]
0x140003d1b  mov     [rsp+70h+var_50], rax; __int64
0x140003d20  call    DfscPackString
0x140003d25  mov     edi, eax
0x140003d27  test    eax, eax
0x140003d29  js      loc_140003BD0
0x140003d2f  mov     r8d, dword ptr [rbp+arg_18]
0x140003d33  mov     eax, [rsi+90h]
0x140003d39  mov     r12d, [rbp+var_40]
0x140003d3d  mov     [rbx+18h], eax
0x140003d40  mov     ecx, [rsi+94h]
0x140003d46  mov     eax, [rbx+0Ch]
0x140003d49  and     eax, 0FFFFFFFEh
0x140003d4c  shr     ecx, 1
0x140003d4e  and     ecx, r12d
0x140003d51  mov     [r15], r8d
0x140003d54  or      ecx, eax
0x140003d56  mov     [rbx+0Ch], ecx
0x140003d59  and     ecx, 0FFFFFFFDh
0x140003d5c  mov     edx, [rsi+94h]
0x140003d62  shr     edx, 1
0x140003d64  and     edx, 2
0x140003d67  or      edx, ecx
0x140003d69  mov     [rbx+0Ch], edx
0x140003d6c  movzx   eax, word ptr [rsi+98h]
0x140003d73  mov     [rbx+4], ax
0x140003d77  mov     al, [rsi+9Ch]
0x140003d7d  neg     al
0x140003d7f  sbb     ecx, ecx
0x140003d81  and     edx, 0FFFFFFFBh
0x140003d84  and     ecx, 4
0x140003d87  or      ecx, edx
0x140003d89  mov     [rbx+0Ch], ecx
0x140003d8c  mov     eax, [rsi+0A4h]
0x140003d92  mov     [rbx], eax
0x140003d94  movzx   eax, word ptr [rsi+9Eh]
0x140003d9b  mov     [rbx+6], ax
0x140003d9f  movzx   eax, word ptr [rsi+0A0h]
0x140003da6  mov     [rbx+8], ax
0x140003daa  movzx   eax, word ptr [rsi+0A2h]
0x140003db1  mov     [rbx+0Ah], ax
0x140003db5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dbc  lea     rax, WPP_GLOBAL_Control
0x140003dc3  cmp     rcx, rax
0x140003dc6  jz      short loc_140003DFE
0x140003dc8  test    dword ptr [rcx+2Ch], 400000h
0x140003dcf  jz      short loc_140003DFE
0x140003dd1  mov     rax, [rsi+70h]
0x140003dd5  mov     rcx, [rcx+18h]
0x140003dd9  mov     dword ptr [rsp+70h+var_48], r8d
0x140003dde  lea     rdx, [rax+38h]
0x140003de2  neg     rax
0x140003de5  mov     rax, [rbp+arg_10]
0x140003de9  sbb     r9, r9
0x140003dec  mov     [rsp+70h+var_50], rax
0x140003df1  and     r9, rdx
0x140003df4  mov     edx, 19h
0x140003df9  call    WPP_SF_ZZD
0x140003dfe  mov     rax, [rsi+0A8h]
0x140003e05  test    rax, rax
0x140003e08  jnz     short loc_140003E11
0x140003e0a  xor     edi, edi
0x140003e0c  jmp     loc_140003BD4
0x140003e11  mov     ecx, [rax]
0x140003e13  lea     r8, aCompressioninf; "CompressionInfo"
0x140003e1a  add     rcx, rax
0x140003e1d  mov     r9d, 0Fh
0x140003e23  call    DfscFindEa
0x140003e28  mov     r15d, 8
0x140003e2e  test    rax, rax
0x140003e31  jz      short loc_140003E54
0x140003e33  cmp     [rax+6], r15w
0x140003e38  jnz     short loc_140003E54
0x140003e3a  movzx   ecx, byte ptr [rax+5]
0x140003e3e  mov     al, [rcx+rax+9]
0x140003e42  neg     al
0x140003e44  mov     eax, [rbx+0Ch]
0x140003e47  sbb     ecx, ecx
0x140003e49  and     eax, 0FFFFFFF7h
0x140003e4c  and     ecx, r15d
0x140003e4f  or      ecx, eax
0x140003e51  mov     [rbx+0Ch], ecx
0x140003e54  mov     rax, [rsi+0A8h]
0x140003e5b  lea     r8, aBlockntlminfo; "BlockNTLMInfo"
0x140003e62  mov     r9d, 0Dh
0x140003e68  mov     ecx, [rax]
0x140003e6a  add     rcx, rax
0x140003e6d  call    DfscFindEa
0x140003e72  test    rax, rax
0x140003e75  jz      short loc_140003E98
0x140003e77  cmp     [rax+6], r15w
0x140003e7c  jnz     short loc_140003E98
0x140003e7e  movzx   ecx, byte ptr [rax+5]
0x140003e82  mov     al, [rcx+rax+9]
0x140003e86  neg     al
0x140003e88  mov     eax, [rbx+0Ch]
0x140003e8b  sbb     ecx, ecx
0x140003e8d  and     eax, 0FFFFFFEFh
0x140003e90  and     ecx, 10h
0x140003e93  or      ecx, eax
0x140003e95  mov     [rbx+0Ch], ecx
0x140003e98  mov     rax, [rsi+0A8h]
0x140003e9f  mov     ecx, [rax+0Ch]
0x140003ea2  mov     eax, [rbx+0Ch]
0x140003ea5  and     ecx, 4
0x140003ea8  shl     ecx, 3
0x140003eab  and     eax, 0FFFFFFDFh
0x140003eae  or      ecx, eax
0x140003eb0  mov     [rbx+0Ch], ecx
0x140003eb3  jmp     loc_140003BD4
```
